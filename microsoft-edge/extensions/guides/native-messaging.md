---
description: ネイティブメッセージングを使って、拡張機能とコンパニオン UWP アプリとの通信を行う方法について説明します。
title: 拡張機能-ネイティブメッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者、ネイティブ、メッセージング、uwp
ms.openlocfilehash: 83f80e112180317c38763225c1cdd015da4238b0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569477"
---
# Microsoft Edge のネイティブメッセージング  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## ネイティブメッセージングアーキテクチャの概要

Windows 10 の作成者の更新プログラムでは、Microsoft Edge extensions はネイティブメッセージングを使って、コンパニオンユニバーサル Windows プラットフォーム (UWP) アプリと通信できます。  高レベルでは、Microsoft Edge extensions は、Chrome および Firefox 拡張機能と同じ Api をネイティブメッセージに使用します。 ただし、ネイティブメッセージングホストは、ユニバーサル Windows プラットフォームを使って実装する必要があります。

> [!NOTE]
> 次のように、Microsoft Edge extensions とネイティブコンポーネントの間の通信を有効にするためにサポートされているメカニズム (AppService 経由の UWP アプリへの接続) がサポートされている方法について説明します。 従来の Win32 コンポーネントとの通信を有効にする方法の詳細については、このガイドの「[デスクトップブリッジコンポーネントを追加](#adding-a-desktop-bridge-component)する」セクションを参照してください。 

 Microsoft Edge のネイティブメッセージングアーキテクチャは、 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) 基礎となるプロセス間通信 (IPC) インフラストラクチャとして既存の API を活用します。 UWP アプリは、 `AppService` API を使って互いに通信します。 このため、Microsoft Edge extensions は UWP アプリと通信できるようになりました。

![ネイティブメッセージングアーキテクチャ](./../media/native-messaging-architecture.png)


### ネイティブメッセージングを使用するタイミング

ネイティブメッセージは、新しいレイヤー全体を拡張機能に追加します。 拡張機能用の UWP コンパニオンアプリを実装することによって、次の可能性が利用可能になります。

* データ (資格情報など) をコンパニオン UWP アプリと同期します。
* Web Api では、より強力な暗号化/暗号化アルゴリズムを実装することはできません。
* ハードウェアや USB デバイスなどの web Api を介してアクセスできないリソースにアクセスする

セキュリティまたはポリシーの制限により、ネイティブメッセージングを使用できない場合もあります。

* Microsoft Edge または Windows のいずれかでユーザー設定を変更する (例: 既定のブラウザーまたは検索プロバイダーの変更)。
* アプリと拡張機能の両方について、Microsoft ストアのポリシーに違反するアクション。
* ネイティブメッセージホスト経由でリモートエンドポイントにデータを転送します。
* 拡張機能の動作を変更するコンテンツを他のアプリからダウンロードできるようにします。

## デモ

コンパニオン UWP アプリと Desktop Bridge の両方を備えた Microsoft Edge のネイティブメッセージング拡張機能の外観を確認するには、GitHub の[Secureinput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput)と[DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning)の例を参照してください。

### 動作のしくみ

サンプルの Microsoft Edge 拡張コンポーネントは、コンテンツスクリプトを使って、ユーザーが暗号化する必要がある情報を入力したときに検出します。 拡張機能は、ネイティブメッセージ経由で、これを Desktop Bridge コンポーネントに伝えます。 ユーザーがデータを送信する準備ができたら、拡張機能は暗号化された値を web サイトに戻します。

> [!NOTE]
> このサンプルは、拡張機能のコンテンツスクリプトと通信するためにカスタムイベントを使う web ページでのみ機能します。 サンプルのフォルダーには、拡張子をテストするための[.html ファイル](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html)が含まれています。

この例では、UWP アプリを使って、Desktop Bridge から Microsoft Edge に応答を渡します。これは、コールバックによって Microsoft Edge extension に送信されます。 この例では、ネイティブメッセージングホストがメインアプリで実行されていますが、バックグラウンドタスクとして実行することもできます。 この2つの切り替えを行うには、拡張機能のバックグラウンドスクリプトを編集する必要があり `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` `"NativeMessagingHostOutOfProcess"` ます。

## Chrome vs Microsoft Edge の実装

Chrome は、アプリと通信するための拡張機能のためにメッセージパッシング Api を使用するルートになっていますが、Microsoft Edge では、 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) Microsoft edge extensions と UWP アプリの通信を可能にする api を利用しています。

このセクションでは、Chrome と Microsoft Edge がネイティブメッセージングの実装を処理する方法の違いについて詳しく説明します。

### 登録とホストマニフェスト
アプリが拡張機能によってネイティブメッセージングホストとして認識されるためには、アプリを登録する必要があります。


[Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration の場合、アプリでは、ネイティブメッセージングホスト構成を定義する Windows ファイルシステム内の任意の場所にマニフェストファイルをインストールする必要があります。

次の JSON は、構成ファイルを設定する方法の例です。

```json
{
   "name": "com.my_company.my_application",
   "description": "My Application",
   "path": "C:\\ProgramFiles\\MyApplication\\chrome_native_messaging_host.exe",
   "type": "stdio",
   "allowed_origins": [
      "chrome-extension://knldjmfmopnpolahpmmgbagdohdnhkik/"
    ]
}
```

このファイルをインストールするには、アプリで次のことを行う必要があります。

1. ホスト構成を定義するレジストリ内の事前定義された場所にマニフェストファイルを登録します。
   - `HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

     または
   - `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

2. このキーの既定値をマニフェストファイルへの完全パスに設定します (例:  `[HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"`




Microsoft Edge では、(ネイティブメッセージホスト) を登録するために、 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) UWP コンパニオンアプリを拡張機能と同じパッケージに含める必要があります。また、プロジェクトのファイルで[AppService の拡張子](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)を指定する必要があり `Package.appxmanifest` ます。 `EntryPoint`および属性は、 `Name` 次の方法で構成できます。

```xml
...
<Applications>    
    <Application Id="App"         
        <Extensions>        
            <uap:Extension Category="windows.appService" EntryPoint="MyAppService.Inventory">          
            <uap:AppService Name="com.microsoft.inventory"/>        
            </uap:Extension>      
        </Extensions>      
        ...    
    </Application>
</Applications>
```


また、サービスへの接続を許可する拡張機能を設定する必要があります。 Microsoft Edge では、 `"allowed_origins"` package.appxmanifest に同等のマニフェストプロパティがないため、これは UWP アプリによって実行時に決定され、適用される必要があります。 Microsoft Edge は、拡張機能の代わりに接続を確立するため、アプリは呼び出し元のパッケージファミリ名を検索して、Microsoft Edge によって接続されているため、呼び出し元を制御または認証することができます。 例: 

```csharp
protected async override void
OnBackgroundActivated(BackgroundActivatedEventArgs args)
{
    IBackgroundTaskInstance taskInstance = args.TaskInstance;
    if (taskInstance.TriggerDetails is AppServiceTriggerDetails)
    {
        AppServiceTriggerDetails appService = taskInstance.TriggerDetails as AppServiceTriggerDetails;
        if (appService.CallerPackageFamilyName == EdgePFN)
        {
            // Establish the connection
        }
        else
        {
            // Reject the connection
        }
    }
}
```



### メッセージ送信

アプリと拡張機能が相互に通信するためには、メッセージを送受信する必要があります。

Chrome 拡張機能 API を使ってメッセージを開始し、 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 非永続的なチャネルを使ってネイティブホストにメッセージを配信します。 

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```

最初のパラメーターは、マニフェストのレジストリで Chrome が検索されるネイティブホストの名前です。 マニフェストでは、Chrome がサンドボックスで起動する .exe を指定します。このマニフェストでは、標準 i/o を使ってメッセージが送信されます。 また、拡張機能は API を使って永続的なチャネルを確立することもでき `runtime.connectNative` ます。これは、ネイティブホストの名前を唯一のパラメーターとして受け取ります。 

Microsoft Edge では、Chrome のネイティブメッセージング API と同じ構成を使用して、Microsoft Edge 拡張機能が接続するアプリサービスを指定できるようにします。 の最初のパラメーターは、 `runtime.sendNativeMessage` アプリサービス名を指定します。 [[登録とホストマニフェスト](#registration-and-host-manifest)] セクションで、これは `"com.microsoft.inventory"` です。 Microsoft Edge extension platform は、拡張機能と同じ AppX にパッケージ化されている UWP アプリとしてネイティブメッセージングホストを制限します。 これにより、マニフェストエントリが改ざんされ、Microsoft Edge を別のパッケージファミリ名に接続しようとしている悪意のある攻撃に関連するセキュリティリスクが軽減されます。 

つまり、Microsoft Edge では、API で指定された名前と同じパッケージファミリ名が、 `AppService` アプリサービスのプロバイダーを一意に識別するために使用されます。  

> [!NOTE]
> これは、 [Microsoft Edge 拡張ツールキット](./porting-chrome-extensions.md)によって簡単に変換されることはありません。 アクセス許可を指定するすべての拡張機能に `"nativeMessaging"` は、このコンポーネントの手動変換が必要であるというマークが付けられます。





### 通信プロトコル

ネイティブメッセージングの通信プロトコルによって、送信前にメッセージの書式設定方法が決まります。

Chrome では、各ネイティブメッセージングホストが個別のプロセスで開始され、標準の入力と標準の出力を使って通信します。 この形式は、両方の方向でメッセージを送信するために使用されます。各メッセージは JSON、UTF-8 encoded を使ってシリアル化され、その前に32ビットのメッセージ長がネイティブのバイト順に表示されます。


Microsoft Edge では、アプリサービスを実装するバックグラウンドタスク/メインアプリはプラットフォームによって開始されます。 起動時に、バックグラウンドタスクの `Run` メソッドが呼び出されます。  

```csharp
public void Run(IBackgroundTaskInstance taskInstance)    
{
    this.backgroundTaskDeferral = taskInstance.GetDeferral();
    // Get a deferral so that the service isn't terminated.
    taskInstance.Canceled += OnTaskCanceled;
    // Associate a cancellation handler with the background task.
    // Retrieve the app service connection and set up a listener for incoming app service requests.
    var details = taskInstance.TriggerDetails as AppServiceTriggerDetails;
    appServiceconnection = details.AppServiceConnection;
    appServiceconnection.RequestReceived += OnRequestReceived;
}
```

拡張機能によって UWP アプリにメッセージが送信されると、 [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) イベントが発生します。 この JSON 形式のメッセージは、オブジェクトの最初の KeyValue ペアに stringified され [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) ます。 :

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```

UWP アプリから拡張機能に返信が返されると、が [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) オブジェクトに追加され `ValueSet` ます。 プロパティは、 `Key` Microsoft Edge では無視されますが、プロパティには `Value` 有効な JSON 文字列が含まれます。

### Callback

コールバックの場合、Chrome では、コールバック関数を使って、 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) メッセージの送信による非同期応答を処理できるようにします。

Microsoft Edge では、オブジェクトのメソッドを使って、 [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) アプリが [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) オブジェクトを拡張機能に戻すことができるようにします。


### メッセージサイズの制限
内線番号とアプリの間でやり取りされるメッセージには、Chrome と Microsoft Edge では異なるメッセージサイズの制限があります。

Chrome には、次のようなメッセージサイズの制限があります。
- ネイティブメッセージングホストからの1つのメッセージ制限: 1 MB
- ネイティブメッセージングホストに送信される1つのメッセージ制限: 4 GB

Microsoft Edge では、 `AppService` (メモリに依存する) メッセージサイズに制限はありませんが、Microsoft edge では、次のようなメッセージサイズの制限を課すことによって、不適切なネイティブアプリから保護されます。
- UWP アプリから拡張機能への1つのメッセージの制限: 1 MB
- 拡張子から UWP アプリへの1つのメッセージ制限: 100 MB



### ネイティブメッセージング接続

ネイティブメッセージングには2種類の接続があります。常設と非永続的。
**固定**接続は、ポートが破棄されるまで実行されたままの接続です。 **非永続的**な接続とは、一度に1つのメッセージに対して開かれ、配信後に終了する接続のことです。

#### 永続的

Chrome の場合、固定接続は、を使ってメッセージポートを作成することによって行われ [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) ます。 ポートが確立されると、Chrome は、ポートが破棄されるまで実行し続けているネイティブメッセージングホストプロセスを開始します。

Microsoft Edge では、を使ってメッセージポートを作成する `runtime.connectNative` と、Microsoft edge が起動し、 [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) ポートが破棄されるまで実行されたままになります。 次のスニペットは、UWP アプリ内から永続的な接続が確立される方法を示しています。 

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```

#### 非永続的

メッセージが Chrome で送信された場合 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 、メッセージポートを作成することなく、chrome は各メッセージに対して新しいネイティブメッセージングホストプロセスを開始します。 ホストプロセスによって生成された最初のメッセージは、元の要求に対する応答として処理され、他のすべてのメッセージは無視されます。

Microsoft Edge は、すべてのメッセージの応答が受信されるたびに接続を終了します。 次のスニペットは、 `AppServiceConnection` 要求が受信され、ととして保存された後に、UWP アプリ内で確立される非永続的な接続を示して [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse) います。

```csharp
using (var connection = new AppServiceConnection())
{    
    //Set up a new app service connection
    connection.AppServiceName = "com.microsoft.randomnumbergenerator";
    connection.PackageFamilyName = "Microsoft.SDKSamples.AppServicesProvider.CS_8wekyb3d8bbwe";
    AppServiceConnectionStatus status = await connection.OpenAsync();
    AppServiceResponse response = await connection.SendMessageAsync(inputs);
}
```

### 許可

ネイティブメッセージングで拡張機能を使用できるようにするには、Chrome と Microsoft Edge の両方について、ファイルにアクセス許可を宣言する必要があり `"nativeMessaging"` `manifest.json` ます。


## アプリ サービス
このセクションでは、Microsoft Edge のネイティブメッセージングのパフォーマンスとメモリに影響を与えるアプリサービスの詳細について説明します。

### パフォーマンス

アプリサービスは、ネイティブメッセージングの目的で呼び出されるフォアグラウンドアプリによって "スポンサー" されます。これは Microsoft Edge です。 これは、Microsoft Edge が実行されている間、アプリサービスを実行できることを意味します。

待機時間については、アプリサービスは、最初の接続後、2つのアプリが直接通信できるようにする名前付きパイプを使います。 この通信方法では、待機時間が短くなります。 低速の Cpu を搭載したデバイスでは、アプリサービスをホストするプロセスを起動してから、いくつかの初期待ち時間が発生します (一部のデバイスでは、バックグラウンドタスクの起動に対しては、最大80ms 秒)。 起動後、スロー CPU デバイスのパフォーマンスは良好である必要があります。 


### メモリ
アプリサービスに割り当てられたメモリは、Microsoft Edge に割り当てられているクォータから差し引かれます。 これは、Microsoft Edge でアプリサービスが多すぎると、メモリが不足する可能性があることを意味します。 通常のバックグラウンドタスクのメモリキャップは、アプリサービスに適用されます。 たとえば、512MB デバイスでは、アプリサービスのバックグラウンドタスクが16MB を超えることはできません。 この番号は、デバイスのスケールアップに合わせて表示されます。


## ネイティブメッセージングを使用した拡張機能の作成

ネイティブメッセージングをテストするには、拡張機能にパッケージファミリ名を指定する必要があります。 Microsoft Edge は、これを使ってネイティブメッセージホスト id を判断します。これは、拡張機能をパッケージ化する必要があることを意味します。 


Visual Studio でネイティブメッセージングで拡張機能を作成するには、次の操作を行います。

1. Visual Studio で UWP プロジェクトを作成します。
2. [ `AppService` UWP アプリにを追加](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)します。
   - 必要に応じて、この時点でバックグラウンドタスクとしてではなく[ `AppService` 、メインアプリでホストするように構成](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process)することができます。
3. UWP プロジェクトをビルドしてテストします。
   - 必要に応じて、 [Desktop Bridge コンポーネント](#adding-a-desktop-bridge-component)を追加できます。
4. UWP コンパニオンアプリと通信するためにネイティブメッセージングを使う Microsoft Edge 拡張機能を作成します。 拡張機能ファイルは、UWP プロジェクトで指定したフォルダーに追加でき `Extension` ます。 サブフォルダーを含む、このフォルダーの下にあるすべてのファイルには、およびを構成するプロパティを設定する必要があり `Build Action=Content` `Copy to Output Directory=Copy Always` ます。 これらの `manifest.json` プロパティでも構成されていることを確認してください。
5. プロジェクト内のファイルを変更して、 `package.manifest.xml` 拡張機能のメタデータを含め、次のように追加して、そのファイルをヘッドレスアプリに変換し `AppListEntry="none"` ます。

    ```xml
    <Package
    xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10" 
    xmlns:rescap="http://schemas.microsoft.com/appx/manifest/foundation/windows10/restrictedcapabilities" 
    xmlns:mp="http://schemas.microsoft.com/appx/2014/phone/manifest" 
    xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10" 
    xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
    IgnorableNamespaces="uap uap3 mp rescap build" 
    xmlns:build="http://schemas.microsoft.com/developer/appx/2015/build">

    <Dependencies>
        <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.15063.0" MaxVersionTested="10.0.15063.0" />
    </Dependencies>

       <Application Id="App" Executable="$targetnametoken$.exe" EntryPoint="NativeMessagingHostInProcess.App">
          <uap:VisualElements AppListEntry="none"
            DisplayName="SecureInput"
            Square150x150Logo="Assets\Square150x150Logo.png"
            Square44x44Logo="Assets\Square44x44Logo.png"
            Description="NativeMessagingHostInProcess"
            BackgroundColor="transparent">
          </uap:VisualElements>
          <Extensions>
            <uap3:Extension Category="windows.appExtension">
                <uap3:AppExtension
                    Name="com.microsoft.edge.extension"
                    Id="EdgeExtension"
                    PublicFolder="Extension"
                    DisplayName="ms-resource:DisplayName">
                </uap3:AppExtension>
            </uap3:Extension>
          </Extensions>
    </Application>
    ```

6. `AppService`ネイティブメッセージング api で、UWP に対して構成された名前を使用します。
7. UWP プロジェクトをビルドして[展開](#deploying)します (オプションの Desktop Bridge コンポーネントを使用します)。
8. ストアへの申請の準備ができたら、ネイティブメッセージングの拡張機能を[パッケージ化](#packaging)する

> [!NOTE]
> 完全なネイティブメッセージング拡張機能の例については、「[デモ](#demos)」セクションを参照してください。


## Desktop Bridge コンポーネントの追加 
パッケージに Desktop Bridge コンポーネントを追加する場合は、Win32 プロジェクトを Visual Studio で作成してビルドする必要があります。 Win32 アプリを UWP に変換する方法について詳しくは、「 [Desktop Bridge を使った Windows 10 へのアプリの移植](/windows/uwp/porting/desktop-to-uwp-root)」をご覧ください。 Visual Studio でビルドされた後、次の手順に従って Win32 実行可能ファイルをパッケージに追加できます。

1. UWP プロジェクトと同じソリューションに Win32 プロジェクトを追加します。 

2. Win32 プロジェクトを UWP プロジェクトの依存プロジェクトとして設定します。

    ![プロジェクトの依存関係を設定する](./../media/project-dependencies.PNG)

3. `Win32`UWP プロジェクト内にフォルダーを作成します。 プロジェクトに必要なバイナリを `Win32` このフォルダーにコピーします。 などのすべてのバイナリのプロパティを構成 `Build Action=Content` し `Copy to Output Directory=Copy Always` ます。

    ![win32 と UWP アプリのファイルが含まれるフォルダー](./../media/desktop-bridge.png)

4. UWP プロジェクトファイルを変更して、プロジェクトに必要なすべてのバイナリを `Win32` このフォルダーにポストビルドイベントコマンドを使用してコピーします。 これにより、ソリューションが再構築されるたびに、更新されたバイナリがフォルダーにコピーされます。

    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```


5. 要素 `package.manifest.xml` に要素を追加して変更し `<desktop:Extension>` `<Extensions>` ます。

    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```

## 展開
前に説明したように UWP プロジェクト (および必要に応じて Win32 プロジェクト) を構成したら、Visual Studio を使ってソリューションを展開することができます。

![inprocess プロジェクトを構築する](../media/native-message-uwp-debug.PNG)

ソリューションが正しく展開されると、Microsoft Edge に拡張機能が表示されます。

![Microsoft Edge に表示される拡張機能](../media/secureextension.png)

## パッケージ化

> [!NOTE]
> Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。 Microsoft Store の一部として要求が送信された場合は、skype[に](https://aka.ms/extension-request)連絡して、将来の更新についてご検討ください。


組み込みの Visual Studio 機能を使用して、Windows デベロッパーセンターに申請するためのストアパッケージを生成できます。


![ストアパッケージを作成する](../media/create-store-package.PNG)

## デバッグ
デバッグの手順は、テストするコンポーネントによって異なります。

### 拡張機能のデバッグ
ソリューションが展開されると、Microsoft Edge に拡張機能がインストールされます。 拡張機能のデバッグ方法について詳しくは、「[デバッグ](./debugging-extensions.md)ガイド」をご覧ください。


### UWP アプリのデバッグ
UWP アプリは、拡張機能が[ネイティブメッセージング api](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)を使って接続しようとしたときに起動します。 プロセスが開始された場合にのみ、UWP アプリをデバッグする必要があります。 この設定は、プロジェクトのプロパティページで行うことができます。

1.  Visual Studio で、UWP アプリプロジェクトを右クリックします。
2.  プロパティを選ぶ
3.  [起動しないが、開始時にコードをデバッグする] チェックボックスをオンにします。

    ![[起動しない] ボックスを選択する](../media/native-message-do-not-launch.png)

Visual Studio で、デバッグするコードにブレークポイントを設定して、F5 キーを押してデバッガーを起動できるようになりました。 UWP アプリに接続するために拡張機能を操作すると、Visual Studio が自動的にプロセスにアタッチされます。


### Desktop Bridge のデバッグ
Desktop Bridge (変換された Win32 アプリ)[をデバッグするに](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug)はさまざまな方法がありますが、このシナリオでは、PLMDebug オプションのみに該当します。 また、スタートアップ関数にデバッグコードを追加して、特定の時間の待機を実行し、Visual Studio をプロセスにアタッチすることもできます。
