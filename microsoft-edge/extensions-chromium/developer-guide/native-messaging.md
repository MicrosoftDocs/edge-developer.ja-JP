---
description: ネイティブ メッセージングに関するドキュメント
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: d9c2370d6a4f9f7cd25001c1c58ce266423af19a
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343067"
---
# ネイティブ メッセージング  

拡張機能は、メッセージを渡す API を使用して、ユーザーのデバイスにインストールされているネイティブの Win32 アプリケーションと通信します。  ネイティブ アプリケーション ホストは、標準の入力と標準出力を使用して、拡張機能を使用してメッセージを送信および受信します。  ネイティブ メッセージングを使用する拡張機能は、他の拡張機能と同様に Microsoft Edge にインストールされます。  ただし、ネイティブ アプリケーションは Microsoft Edge によってインストールまたは管理されません。  

拡張機能とネイティブ アプリケーション ホストを取得するには、2 つの配布モデルがあります。  

*   拡張機能とホストを一緒にパッケージ化します。  ユーザーがパッケージをインストールすると、拡張機能とホストの両方がインストールされます。  
*   Microsoft Edge アドオン ストアを [使用して] [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]拡張機能をインストールすると、拡張機能によってホストのインストールを求めるメッセージが表示されます。  

ネイティブ アプリケーション ホストとの間でメッセージを送受信する拡張機能を作成するには、次の手順を参照してください。  

## 手順 1 - 拡張機能マニフェストにアクセス許可を追加する  

拡張子の `nativeMessaging` ファイルのmanifest.js** に** アクセス許可を追加します。  次のコード スニペットは、次に示すmanifest.js** です**。  

```json
    {
          "name": "Native Messaging Example",
          "version": "1.0",
          "manifest_version": 2, 
          "description": "Send a message to a native application.",
          "app": { 
              "launch": { 
                  "local_path": "main.html" } 
                 }, 
          "icons": { 
              "128": "icon-128.png"}, 
          "permissions": ["nativeMessaging"] 
    }
```  

## 手順 2 - ネイティブ メッセージング ホスト マニフェスト ファイルを作成する  

ネイティブ アプリケーションは、ネイティブ のメッセージング ホスト マニフェスト ファイルを提供する必要があります。  マニフェスト ファイルには、次の情報が含まれています。  

*   ネイティブ メッセージング ホスト ランタイムへのパス。  
*   拡張機能との通信方法。  
*   通信先の許可された拡張機能の一覧。  
    
ブラウザーは、ネイティブ メッセージング ホスト マニフェストを読み取って検証します。  ブラウザーは、ネイティブ のメッセージング ホスト マニフェスト ファイルをインストールまたは管理しない。  

```json
    {
        "name": "com.my_company.my_application",
        "description": "My Application",
        "path": "C:\\Program Files\\My Application\\chrome_native_messaging_host.exe",
        "type": "stdio",
        "allowed_origins": [
            "chrome-extension://knldjmfmopnpolahpmmgbagdohdnhkik/"
        ]
    }
```  

ホスト マニフェスト ファイルは、次のキーを含む有効な JSON ファイルである必要があります。  

:::row:::
   :::column span="1":::
      `name`  
   :::column-end:::
   :::column span="2":::
      ネイティブ メッセージング ホストの名前を指定します。  クライアントは、この文字列を渡す、または `runtime.connectNative` `runtime.sendNativeMessage` .  
      
      *   この値には、小文字の英数字、アンダースコア、ドットのみを含めることができます。  
      *   この値は、ドットで開始または終了し、ドットの後に別のドットを付けずにしてください。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `description`  
   :::column-end:::
   :::column span="2":::
      アプリケーションを記述します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `path`  
   :::column-end:::
   :::column span="2":::
      ネイティブ メッセージング ホスト バイナリへのパスを指定します。  
      
      *   Windows デバイスでは、マニフェスト ファイルを含むディレクトリへの相対パスを使用できます。  
      *   macOS と Linux では、パスは絶対パスである必要があります。  
      
      ホスト プロセスは、ホスト バイナリを含むディレクトリに設定された現在のディレクトリから始まります。  たとえば、\(Windows\) の場合、このパラメーターが設定されている場合、バイナリは現在のディレクトリ `C:\Application\nm_host.exe` \( \) を使用して `C:\Application\` 開始されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `type`  
   :::column-end:::
   :::column span="2":::
      ネイティブ メッセージング ホストとの通信に使用するインターフェイスの種類を指定します。  この値は、Microsoft Edge がホストを使用 `stdin` し、 `stdout` ホストと通信するように指示します。  
      唯一の許容値は次の値です `stdio` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `allowed_origins` 
   :::column-end:::
   :::column span="2":::
      ネイティブ メッセージング ホストにアクセスできる拡張機能の一覧を指定します。  アプリケーションで拡張機能を識別して通信するには、ネイティブ メッセージング ホスト マニフェスト ファイルで次の値を設定します。  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

拡張機能をサイドロードして、ホストとのネイティブ メッセージングをテストします。  
開発中に拡張機能をサイドロードして取得するには、 `microsoft_catalog_extension_id` 次の手順を実行します。  

1.  [開発モード `edge://extensions` ] トグル ボタンに移動し、オンにします。  
1.  [ **展開されていない読み込み**] を選択し、サイドロードする拡張機能パッケージを選択します。  
1.  **[OK]** をクリックします。  
1.  ページに `edge://extensions` 移動し、拡張機能が一覧に表示されます。  
1.  ページの拡張機能の `microsoft_catalog_extension_id` 一覧から \(ID\) からキーをコピーします。  

拡張機能をユーザーに配布する準備ができたら、拡張機能を Microsoft Edge アドオン ストアに公開します。  公開された拡張機能の拡張 ID は、拡張機能のサイドロード中に使用される ID とは異なる場合があります。  ID が変更された場合は、公開された拡張機能の ID を使用してホスト `allowed_origins` マニフェスト ファイルを更新します。  

## 手順 3 - ネイティブ メッセージング ホスト マニフェスト ファイルをシステムにコピーする  

最後の手順では、ネイティブのメッセージング ホスト マニフェスト ファイルをコンピューターにコピーし、マニフェスト ファイルが正しく構成されていることを確認します。  マニフェスト ファイルが想定される場所に配置されるのを確認するには、次の手順を実行します。  場所はプラットフォームによって異なります。  

### [Windows](#tab/windows/)  

<a id="copy-manifest-file"></a>  

マニフェスト ファイルは、ファイル システムの任意の場所に配置できます。  アプリケーション インストーラーは、レジストリ キーを作成し、そのキーの既定値をマニフェスト ファイルの完全なパスに設定する必要があります。  レジストリ キーの例を次に示します。  

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

```text
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

マニフェスト キーを使用してディレクトリにレジストリ キーを追加する。  

*   コマンド プロンプトでコマンドを実行します。  
    
    1.  次のコマンドを実行します。  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
    
*   ファイルを `.reg` 作成して実行します。  
    
    1.  次のコマンドをファイルにコピー `.reg` します。  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  ファイルを実行 `.reg` します。  
    
Microsoft Edge は、ルート `HKEY_CURRENT_USER` キーの後に続くキーを照会 `HKEY_LOCAL_MACHINE` します。  どちらのキーでも、最初に 32 ビット レジストリが検索され、次に 64 ビット レジストリが検索され、ネイティブ メッセージング ホストが識別されます。  レジストリ キーは、ネイティブ メッセージング ホスト マニフェストの場所を指定します。  Microsoft Edge は、前に示した場所でレジストリ キーを見つけた場合、この段落に記載されている場所に対してクエリを実行します。  上記のファイルをバッチ スクリプトの一部として実行する場合は、管理者のコマンド プロンプトを使用 `.reg` して実行してください。  

### [macOS](#tab/macos/)  

<a id="copy-manifest-file"></a>  

マニフェスト ファイルを保存するには、次のいずれかの操作を実行します。  

*   すべてのユーザーが利用できるシステム全体のネイティブ メッセージング ホストは、固定の場所に格納されます。  たとえば、マニフェスト ファイルは次の場所に保存する必要があります。  
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
*   現在のユーザーだけが使用できる、ユーザー固有のネイティブ メッセージング ホストは、ユーザー プロファイル ディレクトリのサブ `NativeMessagingHosts` ディレクトリにあります。  たとえば、マニフェスト ファイルは次の場所に保存する必要があります。  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
    in  `{Channel_Name}` は `Microsoft Edge {Channel_Name}` 、次のいずれかの値である必要があります。  
    
    *   Canary  
    *   Dev  
    *   Beta  

    Stable チャネルを使用する `{Channel_Name}` 場合、必須ではありません。  

### [Linux](#tab/linux/)  

<a id="copy-manifest-file"></a>  

マニフェスト ファイルを保存するには、次のいずれかの操作を実行します。  

*   すべてのユーザーが利用できるシステム全体のネイティブ メッセージング ホストは、固定の場所に格納されます。  マニフェスト ファイルは、次の場所に格納する必要があります。  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   現在のユーザーだけが使用できる、ユーザー固有のネイティブ メッセージング ホストは、ユーザー プロファイル ディレクトリのサブ `NativeMessagingHosts` ディレクトリにあります。  マニフェスト ファイルは、次の場所に格納する必要があります。  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

> [!NOTE]
> マニフェスト ファイルに対する読み取りアクセス許可を提供し、ホスト ランタイムでアクセス許可を実行します。  

<!-- links -->  


 [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge アドオン"

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここ [です](https://developer.chrome.com/extensions/nativeMessaging)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
