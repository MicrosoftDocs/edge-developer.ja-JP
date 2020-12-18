---
description: ネイティブ メッセージングを使用して拡張機能をコンパニオン UWP アプリと通信する方法について説明します。
title: 拡張機能 - ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者, ネイティブ, メッセージング, UWP
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 983ae11822edabc0f27bd6c02f9397104b082ad6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234950"
---
# Microsoft Edge のネイティブ メッセージング  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## ネイティブ メッセージング アーキテクチャの概要

Windows 10 Creators Update を使用すると、Microsoft Edge 拡張機能はネイティブ メッセージングを使用して、コンパニオン ユニバーサル Windows プラットフォーム (UWP) アプリと通信できます。  大きなレベルでは、Microsoft Edge 拡張機能では、Chrome および Firefox 拡張機能と同じ API をネイティブ メッセージングに使用します。 ただし、ネイティブ メッセージング ホストは、ユニバーサル Windows プラットフォームを使用して実装する必要があります。

> [!NOTE]
> 次に示すメソッド (AppService 経由で UWP アプリに接続する) は、Microsoft Edge 拡張機能とネイティブ コンポーネント間の通信を可能にするための唯一のサポートされているメカニズムです。 従来の[](#adding-a-desktop-bridge-component)Win32 コンポーネントとの通信を有効にする方法の詳細については、このガイドの「デスクトップ ブリッジ コンポーネントの追加」セクションを参照してください。 

 Microsoft Edge のネイティブ メッセージング アーキテクチャは、基になるプロセス間通信 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) (IPC) インフラストラクチャとして既存の API を利用します。 UWP アプリは `AppService` 、API を使って相互に通信します。 これにより、Microsoft Edge 拡張機能は UWP アプリと通信できます。

![ネイティブ メッセージング アーキテクチャ](./../media/native-messaging-architecture.png)

### ネイティブ メッセージングを使用しない場合

ネイティブ メッセージングは、拡張機能に全く新しいレイヤーを追加します。 拡張機能用の UWP コンパニオン アプリを実装すると、次の可能性が利用できます。

* データ (資格情報など) をコンパニオン UWP アプリと同期します。
* Web API では使用できない強力な暗号化/暗号化解除アルゴリズムを実装します。
* Web API からアクセスできないリソース (ハードウェアや USB デバイスなど) にアクセスする

セキュリティやポリシーの制限によりネイティブ メッセージングを使用できない場合があります。

* Microsoft Edge または Windows のユーザー設定の変更 (既定のブラウザーまたは検索プロバイダーの変更など)。
* アプリと拡張機能の両方の Microsoft Store ポリシーに違反するアクション。
* ネイティブ メッセージ ホスト経由でリモート エンドポイントにデータを転送する。
* 拡張機能の動作を変更するコンテンツを他のアプリがダウンロードすることを許可します。

## デモ

コンパニオン UWP アプリとデスクトップ ブリッジの両方を含む Microsoft Edge ネイティブ メッセージング拡張機能の外観を確認するには、GitHub の [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) と [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) の例をご覧ください。

### 動作のしくみ

サンプルの Microsoft Edge 拡張機能コンポーネントは、コンテンツ スクリプトを使用して、ユーザーが暗号化する必要がある情報を入力している場合を検出します。 拡張機能は、ネイティブ メッセージングを介してデスクトップ ブリッジ コンポーネントにこれを通信します。 ユーザーがデータを送信する準備ができたら、拡張機能は暗号化された値を Web サイトに返します。

> [!NOTE]
> このサンプルは、カスタム イベントを使用して拡張機能のコンテンツ スクリプトと通信する Web ページでのみ動作します。 サンプル フォルダーには、拡張子をテスト [する .html](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) ファイルが含まれています。

この例では、UWP アプリを使ってデスクトップ ブリッジから Microsoft Edge に応答を渡し、コールバック経由で Microsoft Edge 拡張機能に送信します。 この例では、メイン アプリでネイティブ メッセージング ホストを実行しますが、バックグラウンド タスクとして実行することもできます。 2 つのスクリプトを切り替えるには、拡張機能のバックグラウンド スクリプトを編集し、次に示す文字列を変更する必要 `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` があります `"NativeMessagingHostOutOfProcess"` 。

## Chrome と Microsoft Edge の実装

Chrome は、拡張機能がアプリと通信するためにメッセージを渡す API を使用するルートに進む一方で、Microsoft Edge は、Microsoft Edge 拡張機能と UWP アプリの通信を可能にする API を利用 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) します。

このセクションでは、Chrome と Microsoft Edge がネイティブ メッセージングの実装を処理する方法の違いについて説明します。

### 登録とホスト マニフェスト
拡張機能によってアプリがネイティブ メッセージング ホストとして認識されるには、アプリを登録する必要があります。

[Chrome ネイティブ メッセージング ホスト](https://developer.chrome.com/extensions/nativeMessaging)の登録では、アプリは、ネイティブ メッセージング ホストの構成を定義する Windows ファイル システムの任意の場所にマニフェスト ファイルをインストールする必要があります。

次の JSON は、構成ファイルのセットアップ方法の例です。

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

このファイルをインストールするには、アプリで次の手順を実行する必要があります。

1.  マニフェスト ファイルを、ホスト構成を定義するレジストリ内の定義済みの場所に登録します。
    -   ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application
        ```  
        
        または
        
    -   ```text
        HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application
        ```  
        
2.  そのキーの既定値をマニフェスト ファイルへの完全パス (例: 
    
    ```text
    [HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"
    ```  
    
Microsoft Edge の場合、(ネイティブ メッセージング ホスト) を登録するには、拡張機能と同じパッケージに UWP コンパニオン アプリを含め、プロジェクトのファイルに [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) [AppService](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)拡張機能を指定する必要があります。 `Package.appxmanifest` これらの `EntryPoint` 属性 `Name` は、次の方法で構成できます。

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


また、サービスへの接続を許可する拡張機能を設定する必要があります。 Microsoft Edge の AppxManifest には同等のマニフェスト プロパティはないので、これは実行時に UWP アプリによって決定され、適用される `"allowed_origins"` 必要があります。 Microsoft Edge は拡張機能の代わりに接続を確立します。アプリは、呼び出し元のパッケージ ファミリ名を検索して、発信者を制御または認証するために Microsoft Edge によって接続されていないかどうかを判断できます。 例: 

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

アプリと拡張機能が相互に通信するには、メッセージのやり取りが必要です。

Chrome 拡張機能は、API を使用してメッセージを開始し、非永続的なチャネルを使用してネイティブ ホスト [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) にメッセージを配信します。 

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```  

最初のパラメーターはネイティブ ホストの名前です。Chrome は、レジストリでマニフェストを検索します。 マニフェストは、Chrome がサンドボックス内で起動する .exe を指定し、メッセージは std i/o を使用して送信されます。 拡張機能は、API を使用して永続的なチャネルを確立することもできます。このチャネルは、ネイティブ ホストの名前を唯一の `runtime.connectNative` パラメーターとして受け取ります。 

Microsoft Edge では、Chrome のネイティブ メッセージング API と同じコンストラクトを使用して、Microsoft Edge 拡張機能で接続先のアプリ サービスを指定できます。 最初のパラメーターは `runtime.sendNativeMessage` 、アプリ サービス名を指定します。 [登録と [ホスト マニフェスト] セクションでは](#registration-and-host-manifest) 、次の情報が表示されます `"com.microsoft.inventory"` 。 Microsoft Edge 拡張機能プラットフォームでは、ネイティブ メッセージング ホストが拡張機能と同じ AppX にパッケージ化された UWP アプリに制限されます。 これにより、マニフェスト エントリを改ざんして Microsoft Edge を別のパッケージ ファミリ名に接続しようとする悪意のある攻撃に関連するセキュリティ リスクが軽減されます。 

つまり、Microsoft Edge は、アプリ サービスのプロバイダーを一意に識別するために、API で指定された名前に加えて、拡張機能と同じパッケージ ファミリ名を `AppService` 使用します。  

> [!NOTE]
> これは [、Microsoft Edge](./porting-chrome-extensions.md)Extension Toolkit によって簡単に変換Toolkit。 アクセス許可を指定する拡張機能には、このコンポーネントの手動変換を必要とするようにフラグ `"nativeMessaging"` が設定されます。

### 通信プロトコル

ネイティブ メッセージングの通信プロトコルは、送信前のメッセージの書式設定方法を決定します。

Chrome は、各ネイティブ メッセージング ホストを個別のプロセスで開始し、標準の入力と標準出力を使用して通信します。 両方向でメッセージを送信するために同じ形式が使用されます。各メッセージは JSON、UTF-8 エンコードを使用してシリアル化され、ネイティブバイト順で 32 ビットのメッセージ長が先行します。

Microsoft Edge では、アプリ サービスを実装するバックグラウンド タスク/メイン アプリがプラットフォームによって開始されます。 起動時に、バックグラウンド タスクのメソッド `Run` が呼び出されます。  

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

拡張機能が UWP アプリにメッセージを送信すると、 [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) イベントが発生します。 この JSON 形式のメッセージは、オブジェクトの最初の KeyValue ペアに文字列化 [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) されます。 :

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```  

UWP アプリが拡張機能に応答を返す場合、a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) がオブジェクトに追加 `ValueSet` されます。 この `Key` プロパティは Microsoft Edge では無視されますが、プロパティには `Value` 有効な JSON 文字列が含まれます。

### Callback

コールバックの場合、Chrome は、コールバック関数がメッセージの送信からの非同期応答を処理するために [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 使用します。

Microsoft Edge では、 [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) オブジェクトのメソッド [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) を使って、アプリがオブジェクトを拡張機能に [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 送り返します。


### メッセージ サイズの制限
拡張機能とアプリの間で送信されるメッセージのメッセージサイズの制限は、Chrome と Microsoft Edge では異なります。

Chrome には、次のメッセージ サイズ制限があります。
-   ネイティブ メッセージング ホストからの単一メッセージの制限: 1 MB
-   ネイティブ メッセージング ホストに送信される単一のメッセージ制限: 4 GB
    
Microsoft Edge では、メッセージ サイズに制限はありません (メモリに依存)、Microsoft Edge は次のメッセージ サイズ制限を課して、ネイティブ アプリの動作の誤りから自分自身を `AppService` 保護します。
-   UWP アプリから拡張機能への単一メッセージの制限: 1 MB
-   拡張機能から UWP アプリへの単一メッセージの制限: 100 MB
    
### ネイティブ メッセージング接続

ネイティブ メッセージングには 2 種類の接続があります。永続的および非永続的。
固定 **接続** とは、ポートが破棄されるまで実行され続けた接続です。 永続的 **でない接続とは** 、一度に 1 つのメッセージに対して開き、配信後に閉じる接続です。

#### 永続的

Chrome の場合、永続的な接続は、次を使用してメッセージング ポートを作成することで行います [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) 。 ポートが作成されると、Chrome はネイティブメッセージング ホスト プロセスを開始し、破棄されたポートまで実行を続ける。

Microsoft Edge の場合、メッセージング ポートが作成されると、Microsoft Edge はポートを開始し、ポートが破棄されるまで実行 `runtime.connectNative` [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) を維持します。 次のスニペットは、UWP アプリ内から永続的な接続が確立される方法を示しています。 

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

メッセージを Chrome で使用して送信すると、メッセージング ポートを作成せずに、Chrome はメッセージごとに新しいネイティブ メッセージング [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) ホスト プロセスを開始します。 ホスト プロセスによって生成された最初のメッセージは、元の要求に対する応答として処理され、その後の他のすべてのメッセージは無視されます。

Microsoft Edge は、すべてのメッセージの応答を受信した後、接続を終了します。 次のスニペットは、要求を受信して UWP アプリ内で終了する非永続的な接続を示しています `AppServiceConnection` [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse) 。

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

拡張機能でネイティブ メッセージングの使用を有効にするには、Chrome と Microsoft Edge の両方について、ファイルでアクセス許可を `"nativeMessaging"` 宣言する必要 `manifest.json` があります。

## アプリ サービス
このセクションでは、アプリ サービスが Microsoft Edge ネイティブ メッセージングのパフォーマンスとメモリに与える影響について詳しい説明します。

### パフォーマンス

アプリ サービスは、ネイティブ メッセージングの目的で Microsoft Edge を呼び出すフォアグラウンド アプリによって "スポンサー付け" されます。 つまり、Microsoft Edge が実行されている限り、アプリ サービスを実行できます。

待機時間に関して、アプリ サービスは名前付きパイプを使用します。このパイプは、最初の接続後に 2 つのアプリが直接通信できます。 この通信方法により、待機時間が短くなる。 CPU が遅いデバイスでは、アプリ サービスをホストするプロセスを開始した後、初期遅延が発生します (一部のデバイスではバックグラウンド タスクを起動するために約 80ms)。 起動後は、低速な CPU デバイスのパフォーマンスが良好である必要があります。 

### メモリ
アプリ サービスに割り当てられたメモリは、Microsoft Edge に割り当てられたクォータから取り出されます。 つまり、Microsoft Edge が起動するアプリ サービスが多すぎると、メモリが使い切れる可能性があります。 通常のバックグラウンド タスクのメモリ制限は、アプリ サービスに適用されます。 たとえば、512 MB デバイスでは、アプリ サービスのバックグラウンド タスクは 16 MB 以下に設定できます。 この数は、デバイスのスケール アップに合って上がっています。

## ネイティブ メッセージングを使用した拡張機能の作成

ネイティブ メッセージングをテストするには、拡張機能にパッケージ ファミリ名が必要です。 Microsoft Edge はこれを使用してネイティブ メッセージホスト ID を決定します。つまり、拡張機能をパッケージ化する必要があります。 

ネイティブ メッセージングを使用して拡張機能を作成するには、次Visual Studio。

1.  アプリで UWP プロジェクトをVisual Studio。
2.  [ `AppService` UWP アプリに追加します](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)。
    -   必要に応じて [、 `AppService` この](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) 時点でバックグラウンド タスクとしてではなくメイン アプリでホストされる構成を行います。
3.  UWP プロジェクトをビルドしてテストします。
    -   必要に応じて、デスクトップ ブリッジ [コンポーネントを追加できます](#adding-a-desktop-bridge-component)。
4.  ネイティブ メッセージングを使用して UWP コンパニオン アプリと通信する Microsoft Edge 拡張機能を作成します。 拡張ファイルは、UWP プロジェクトで指定された `Extension` フォルダーに追加できます。 サブフォルダーを含む、このフォルダーの下のすべてのファイルは、それらのプロパティを構成する必要 `Build Action=Content` があります `Copy to Output Directory=Copy Always` 。 これらのプロパティ `manifest.json` も構成されていることを確認します。
5.  プロジェクト内のファイルを変更して拡張機能のメタデータを含め、以下を追加してヘッドレス `package.manifest.xml` アプリに変換します `AppListEntry="none"` 。
    
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
    
6.  ネイティブ メッセージング `AppService` API で UWP 用に構成された名前を使用します。
7.  UWP [プロジェクトを](#deploying) ビルドして展開します (オプションのデスクトップ ブリッジ コンポーネントを使用)。
8.  [ストア](#packaging) 申請の準備ができたら、ネイティブ メッセージング拡張機能をパッケージ化する
    
> [!NOTE]
> 完全な [ネイティブ メッセージング拡張機能](#demos) の例については、「Demos」セクションを参照してください。

## デスクトップ ブリッジ コンポーネントの追加 
デスクトップ ブリッジ コンポーネントをパッケージに追加する場合は、Win32 プロジェクトを作成してビルドする必要Visual Studio。 win32 アプリを UWP に変換する方法について詳しくは、「デスクトップ ブリッジを使った [Windows 10](/windows/uwp/porting/desktop-to-uwp-root)へのアプリの移植」をご覧ください。 組み込みVisual Studio、次の手順を実行して、Win32 実行可能ファイルをパッケージに追加できます。

1.  Win32 プロジェクトを UWP プロジェクトと同じソリューションに追加します。 
2.  Win32 プロジェクトを UWP プロジェクトの依存プロジェクトとして設定します。
    
    ![プロジェクトの依存関係の設定](./../media/project-dependencies.PNG)
    
3.  `Win32`UWP プロジェクト内にフォルダーを作成します。 プロジェクトに必要なバイナリを `Win32` このフォルダーにコピーします。 すべてのバイナリのプロパティを構成します `Build Action=Content` `Copy to Output Directory=Copy Always` 。
    
    ![フォルダーに win32 と UWP アプリ ファイルがある](./../media/desktop-bridge.png)
    
4.  PostBuild イベント コマンドを使用して、UWP プロジェクト ファイルを変更して、プロジェクトに必要なすべてのバイナリをこの `Win32` フォルダーにコピーします。 これにより、ソリューションが再構築されるたび、更新されたバイナリがフォルダーにコピーされます。
    
    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```
    
5.  要素 `package.manifest.xml` に要素を `<desktop:Extension>` 追加して変更 `<Extensions>` します。
    
    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```
    
## 展開
上記で説明したように UWP プロジェクト (およびオプションで Win32 プロジェクト) を構成したら、次の手順を使用してソリューションを展開Visual Studio。

![ビルド inprocess プロジェクト](../media/native-message-uwp-debug.PNG)

ソリューションを正しく展開すると、Microsoft Edge に拡張機能が表示されます。

![Microsoft Edge に表示される拡張機能](../media/secureextension.png)

## パッケージ化

> [!NOTE]
> Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。 Microsoft Store[の一](https://aka.ms/extension-request)部としてお客様からのリクエストをお問い合わせください。今後の更新について検討します。

Windows デベロッパー センターへの申請用にストア パッケージを生成するには、次の組み込みのVisual Studioできます。

![ストア パッケージの作成](../media/create-store-package.PNG)

## デバッグ
デバッグの手順は、テストするコンポーネントによって異なります。

### 拡張機能のデバッグ
ソリューションを展開すると、拡張機能が Microsoft Edge にインストールされます。 拡張機能をデバッグ [する](./debugging-extensions.md) 方法については、デバッグ ガイドを参照してください。


### UWP アプリのデバッグ
拡張機能がネイティブ メッセージング API を使用して接続しようとすると、UWP アプリ [が起動します](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)。 プロセスが開始された後にのみ、UWP アプリをデバッグする必要があります。 これは、プロジェクトの [プロパティ] ページから構成できます。

1.  次Visual Studio、UWP アプリ プロジェクトを右クリックします。
2.  プロパティの選択
3.  [起動しないが、起動時にコードをデバッグする] をオンにしてください。
    
    ![[起動しない] ボックスを選択する](../media/native-message-do-not-launch.png)
    
このVisual Studio、デバッグするコードにブレークポイントを設定し、F5 キーを押してデバッガーを起動できます。 拡張機能を操作して UWP アプリに接続すると、Visual Studioプロセスに自動的にアタッチされます。

### デスクトップ ブリッジのデバッグ
デスクトップ ブリッジ [(変換](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) された Win32 アプリ) をデバッグする方法はさまざまな場合でも、このシナリオに該当する唯一の方法は PLMDebug オプションです。 また、デバッグ コードをスタートアップ関数に追加して、特定の時間の待機時間を実行し、プロセスにVisual Studioを追加できます。
