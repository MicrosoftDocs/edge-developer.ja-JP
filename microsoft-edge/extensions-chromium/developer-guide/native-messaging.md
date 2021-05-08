---
description: ネイティブ メッセージングのドキュメント
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/31/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: e6233289794bc1c3ef235af46402c23173c09857
ms.sourcegitcommit: e6a4f73be57439149e3cc56491d7364831d0079e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "11475212"
---
# <a name="native-messaging"></a>ネイティブ メッセージング  

拡張機能は、API を渡すメッセージを使用して、ユーザーのデバイスにインストールされているネイティブの Win32 アプリと通信します。  ネイティブ アプリ ホストは、標準の入力と標準出力を使用して、拡張機能付きメッセージを送信および受信します。  ネイティブ メッセージングを使用する拡張機能は、Microsoft Edgeにインストールされます。  ただし、ネイティブ アプリは、ユーザーがインストールまたは管理Microsoft Edge。  

拡張機能とネイティブ アプリ ホストを取得するには、2 つの配布モデルがあります。  

*   拡張機能とホストをまとめてパッケージ化します。  ユーザーがパッケージをインストールすると、拡張機能とホストの両方がインストールされます。  
*   アドオン ストアを使用Microsoft Edge[拡張機能][MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]をインストールすると、ホストのインストールをユーザーに求めるメッセージが表示されます。  

ネイティブ アプリ ホストを使用してメッセージを送受信する拡張機能を作成するには、次の手順を実行します。  

## <a name="step-1---add-permissions-to-the-extension-manifest"></a>手順 1 - 拡張機能マニフェストにアクセス許可を追加する  

拡張子の `nativeMessaging` ファイルmanifest.js** にアクセス** 許可を追加します。  次のコード スニペットは、on のコードmanifest.js** です**。  

```json
{
    "name": "Native Messaging Example",
    "version": "1.0",
    "manifest_version": 2, 
    "description": "Send a message to a native app.",
    "app": { 
        "launch": { 
            "local_path": "main.html" 
        } 
    }, 
    "icons": { 
        "128": "icon-128.png"
    }, 
    "permissions": ["nativeMessaging"] 
}
```  

## <a name="step-2---create-your-native-messaging-host-manifest-file"></a>手順 2 - ネイティブ メッセージング ホスト マニフェスト ファイルを作成する  

ネイティブ アプリは、ネイティブ メッセージング ホスト マニフェスト ファイルを提供する必要があります。  マニフェスト ファイルには、次の情報が含まれています。  

*   ネイティブ メッセージング ホスト ランタイムへのパス。  
*   拡張機能との通信方法。  
*   通信先の許可された拡張機能の一覧。  
    
ブラウザーは、ネイティブ メッセージング ホスト マニフェストを読み取り、検証します。  ブラウザーは、ネイティブ メッセージング ホスト マニフェスト ファイルをインストールまたは管理しない。  

```json
{
    "name": "com.my_company.my_app",
    "description": "My App",
    "path": "C:\\Program Files\\My App\\chrome_native_messaging_host.exe",
    "type": "stdio",
    "allowed_origins": [
        "chrome-extension://knldjmfmopnpolahpmmgbagdohdnhkik/"
    ]
}
```  

ホスト マニフェスト ファイルは、次のキーを含む有効な JSON ファイルである必要があります。  

:::row:::
   :::column span="1":::
      **キー**  
   :::column-end:::
   :::column span="3":::
      **詳細**  
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `name`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      ネイティブ メッセージング ホストの名前を指定します。  クライアントは、文字列を `runtime.connectNative` または `runtime.sendNativeMessage` に渡します。  
      
      *   この値には、小文字の英数字、アンダースコア、ドットのみを含む必要があります。  
      *   値はドットで開始または終了し、ドットの後に別のドットを付けずに設定する必要があります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `description`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      アプリについて説明します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `path`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      ネイティブ メッセージング ホスト バイナリへのパスを指定します。  
      
      *   デバイスWindowsマニフェスト ファイルを含むディレクトリへの相対パスを使用できます。  
      *   macOS および Linux では、パスは絶対パスである必要があります。  
          
      ホスト プロセスは、ホスト バイナリを含むディレクトリに設定されている現在のディレクトリから始まります。  たとえば、\(Windows\) の場合、パラメーターがに設定されている場合、バイナリはカレント ディレクトリ `C:\App\nm_host.exe` \( \) を使用して開始 `C:\App\` されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `type`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      ネイティブ メッセージング ホストとの通信に使用するインターフェイスの種類を指定します。  この値は、Microsoft Edgeを使用し `stdin` 、ホストと `stdout` 通信するように指示します。  
      受け入れ可能な唯一の値は `stdio` です。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `allowed_origins` 
   :::column-end:::
   :::column span="3":::
      ---  
      
      ネイティブ メッセージング ホストにアクセスできる拡張機能の一覧を指定します。  アプリを有効にし、拡張機能を識別して通信するには、ネイティブ メッセージング ホスト マニフェスト ファイルで次の値を設定します。  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

拡張機能をサイドロードして、ホストとのネイティブ メッセージングをテストします。  
開発中に拡張機能をサイドロードして取得するには `microsoft_catalog_extension_id` 、次のアクションを実行します。  

1.  に移動 `edge://extensions` し、[開発者モード] トグル ボタンをオンにします。  
1.  [ **アンパックの読み込み**] を選択し、サイドロードする拡張パッケージを選択します。  
1.  **[OK]** をクリックします。  
1.  ページに移動 `edge://extensions` し、拡張機能が一覧に表示されるのを確認します。  
1.  ページの内線 `microsoft_catalog_extension_id` 番号の一覧から \(ID\) からキーをコピーします。  
    
拡張機能をユーザーに配布する準備ができたら、拡張機能をアドオン ストアMicrosoft Edge発行します。  発行された拡張機能の内線番号 ID は、拡張機能のサイドロード中に使用される ID と異なる場合があります。  ID が変更された場合は、発行された拡張子の ID を使用してホスト マニフェスト `allowed_origins` ファイルを更新します。  

## <a name="step-3---copy-the-native-messaging-host-manifest-file-to-your-system"></a>手順 3 - ネイティブ メッセージング ホスト マニフェスト ファイルをシステムにコピーする  

最後の手順では、ネイティブ メッセージング ホスト マニフェスト ファイルをコンピューターにコピーし、マニフェスト ファイルが正しく構成されていることを確認します。  マニフェスト ファイルが予期した場所に配置されるのを確認するには、次の操作を実行します。  場所はプラットフォームによって異なります。

> [!NOTE]
> マニフェスト ファイルに対する読み取りアクセス許可を指定し、ホスト ランタイムでアクセス許可を実行します。  

### [<a name="windows"></a>Windows](#tab/windows/)  

<a id="copy-manifest-file"></a>  

マニフェスト ファイルは、ファイル システム内の任意の場所に配置できます。  アプリ インストーラーは、レジストリ キーを作成し、キーの既定値をマニフェスト ファイルの完全なパスに設定する必要があります。  レジストリ キーの例を次に示します。  

```output
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app
```  

マニフェスト キーを使用してレジストリ キーをディレクトリに追加するには、次のいずれかの操作を実行します。  

*   コマンド プロンプトでコマンドを実行します。  
    
    1.  次のコマンドを実行します。  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
        
*   ファイルを `.reg` 作成して実行します。  
    
    1.  次のコマンドをファイルに `.reg` コピーします。  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  ファイルを実行 `.reg` します。  
        
Microsoft Edgeキーの後 `HKEY_CURRENT_USER` にクエリを実行します `HKEY_LOCAL_MACHINE` 。  どちらのキーでも、最初に 32 ビット レジストリが検索され、次に 64 ビット レジストリが検索され、ネイティブ メッセージング ホストが識別されます。  レジストリ キーは、ネイティブ メッセージング ホスト マニフェストの場所を指定します。  Microsoft Edgeのレジストリ エントリにホスト マニフェストの場所がない場合は、Chromium レジストリの場所と Chrome レジストリの場所がフォールバック オプションとして使用されます。  レジストリ Microsoft Edgeが以前に表示された場所で見つけた場合、次のコード スニペットに記載されている場所はクエリされません。  作成したファイルをバッチ スクリプトの一部として実行する場合は、管理者のコマンド プロンプトを使用 `.reg` して実行してください。

次の一覧は、レジストリの場所の検索順序です。  

```output
HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Microsoft\Edge\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Chromium\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Google\Chrome\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\Chromium\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\

HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Edge\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Chromium\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Google\Chrome\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\Chromium\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\
```  
 
> [!NOTE] 
> Microsoft Edge アドオンと Chrome Web ストアに拡張機能がある場合は、最初に見つかったレジストリの場所に対応するホスト マニフェストだけが読み取れるので、ホスト マニフェスト ファイルの両方のストアに対応する拡張機能の ID を追加する必要があります。 `allowed_origins`  

### [<a name="macos"></a>macOS](#tab/macos/)  

<a id="copy-manifest-file"></a>  

マニフェスト ファイルを保存するには、次のいずれかの操作を実行します。  

*   システム全体のネイティブ メッセージング ホスト (すべてのユーザーが利用できる) は、固定の場所に格納されます。  たとえば、マニフェスト ファイルを次の場所に保存する必要があります。  
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_app.json
    ```  
    
*   現在のユーザーだけが使用できるユーザー固有のネイティブ メッセージング ホストは、ユーザー プロファイル ディレクトリのサブ `NativeMessagingHosts` ディレクトリにあります。  たとえば、マニフェスト ファイルを次の場所に保存する必要があります。  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_app.json
    ```  
    
    in  `{Channel_Name}` は `Microsoft Edge {Channel_Name}` 、次のいずれかの値である必要があります。  
    
    *   `Canary`  
    *   `Dev`  
    *   `Beta`  
        
    Stable チャネルを使用する ` {Channel_Name}` 場合は、必須ではありません。  
    
### [<a name="linux"></a>Linux](#tab/linux/)  

<a id="copy-manifest-file"></a>  

マニフェスト ファイルを保存するには、次のいずれかの操作を実行します。  

*   システム全体のネイティブ メッセージング ホスト (すべてのユーザーが利用できる) は、固定の場所に格納されます。  マニフェスト ファイルは、次の場所に保存する必要があります。  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   現在のユーザーだけが使用できるユーザー固有のネイティブ メッセージング ホストは、ユーザー プロファイル ディレクトリのサブ `NativeMessagingHosts` ディレクトリにあります。  マニフェスト ファイルは、次の場所に保存する必要があります。  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

<!-- links -->  

[MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge アドオン"

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページは次 [のページに表示されます](https://developer.chrome.com/extensions/nativeMessaging)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
