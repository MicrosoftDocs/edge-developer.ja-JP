---
description: ネイティブメッセージングのドキュメント
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/06/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: c5da9acf79225c88ad5829c2b7f57d1d833ca49b
ms.sourcegitcommit: 75c200a029d19fe372c1505c0006dbfbfad90bf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "11100253"
---
# ネイティブ メッセージング  

拡張機能は、メッセージパッシング Api を使って、ユーザーのデバイスにインストールされているネイティブ Win32 アプリケーションと通信します。  ネイティブのアプリケーションホストは、標準の入力と標準の出力を使って、拡張機能を使ってメッセージを送受信します。  ネイティブメッセージングを使用する拡張機能は、他の拡張機能と同様に Microsoft Edge にインストールされます。  ただし、ネイティブアプリケーションは Microsoft Edge でインストールまたは管理されません。  

拡張機能とネイティブアプリケーションホストを取得するには、2つの配布モデルがあります。  

*   拡張機能とホストをまとめてパッケージ化します。  ユーザーがパッケージをインストールすると、拡張機能とホストの両方がインストールされます。
*   [Microsoft Edge アドオンストア][EdgeAddons]を使用して拡張機能をインストールすると、拡張機能により、ユーザーにホストをインストールするように求められます。  

ネイティブアプリケーションホストでメッセージを送受信するための拡張機能を作成するには、次の手順を参照してください。  

## 手順 1-拡張機能マニフェストにアクセス許可を追加する  

`nativeMessaging`拡張子のファイルの**manifest.js**にアクセス許可を追加します。  次のコードスニペットは、 **manifest.js**の例です。  

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

## 手順 2-ネイティブメッセージングホストマニフェストファイルを作成する  

ネイティブアプリケーションでは、ネイティブメッセージングホストマニフェストファイルを提供する必要があります。  マニフェストファイルには、ネイティブメッセージングホストランタイムへのパス、拡張機能との通信方法、および通信先として使用できる拡張機能の一覧が含まれます。  ブラウザーは、ネイティブのメッセージングホストマニフェストを読み取り、検証します。  ブラウザーは、ネイティブメッセージングホストマニフェストファイルをインストールまたは管理しません。  

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

ホストマニフェストファイルは、次のキーを含む有効な JSON ファイルである必要があります。  

:::row:::
   :::column span="1":::
      `name`  
   :::column-end:::
   :::column span="2":::
      ネイティブメッセージングホストの名前を指定します。  クライアントは、またはにこの文字列を渡し `runtime.connectNative` `runtime.sendNativeMessage` ます。  
      
      *   この値には、小文字の英数字、アンダースコア、ドットを含める必要があります。  
      *   この値は、先頭と末尾以外のドットで指定する必要があります。ドットの後に別のドットを付けることはできません。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `description`  
   :::column-end:::
   :::column span="2":::
      アプリケーションについて説明します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `path`  
   :::column-end:::
   :::column span="2":::
      ネイティブメッセージングホストバイナリへのパスを指定します。  
      
      *   Windows デバイスでは、マニフェストファイルを含むディレクトリへの相対パスを使うことができます。  
      *   MacOS と Linux では、パスは絶対パスにする必要があります。  
      
      ホストプロセスは、現在のディレクトリがホストバイナリを含むディレクトリに設定された状態で開始されます。  たとえば、\ (Windows \) では、このパラメーターがに設定されている場合、 `C:\Application\nm_host.exe` 現在のディレクトリ \ (\) を使ってバイナリが開始され `C:\Application\` ます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `type`  
   :::column-end:::
   :::column span="2":::
      ネイティブメッセージングホストとの通信に使用されるインターフェイスの型を指定します。  この値は、Microsoft Edge がホストとの通信を行うために使用することを指示 `stdin` し `stdout` ます。  
      指定できる値は、だけ `stdio` です。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `allowed_origins` 
   :::column-end:::
   :::column span="2":::
      ネイティブメッセージングホストにアクセスできる拡張子の一覧を指定します。  アプリケーションで拡張機能を認識して通信できるようにするには、ネイティブメッセージングホストマニフェストファイルで次の値を設定します。  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

ホストとのネイティブメッセージングをテストするために拡張機能をサイドローディングします。  
開発中に拡張機能をサイドローディングして取得するには `microsoft_catalog_extension_id` 、次の手順を実行します。  

1.  に移動し `edge://extensions` て、[開発者モード] トグルボタンをオンにします。  
1.  [ **アンパックの読み込み**] を選択し、サイドローディングに拡張パッケージを選択します。  
1.  **[OK]** をクリックします。
1.  ページに移動して、 `edge://extensions` 拡張子が表示されていることを確認します。  
1.  `microsoft_catalog_extension_id`ページの内線番号リストからキーを \ (ID) からコピーします。

内線番号をユーザーに配布する準備ができたら、Microsoft Edge のアドオンストアに拡張機能を公開します。  公開された拡張機能の拡張 ID は、拡張機能のサイドローディング時に使用した ID とは異なる場合があります。  ID が変更された場合は、公開された `allowed_origins` 拡張機能の id でホストマニフェストファイル内で更新します。  

## 手順 3-ネイティブのメッセージングホストマニフェストファイルをシステムにコピーする  

最後の手順では、ネイティブのメッセージングホストマニフェストファイルをコンピューターにコピーし、正しく構成されていることを確認します。  マニフェストファイルが予期した場所に配置されるようにするには、次の手順を実行します。  場所はプラットフォームによって異なります。  

### [Windows](#tab/windows/)  

<a id="copy-manifest-file"></a>  

マニフェストファイルは、ファイルシステム内の任意の場所に配置されている可能性があります。  アプリケーションのインストーラーでは、レジストリキーを作成し、そのキーの既定値をマニフェストファイルの完全パスに設定する必要があります。  次のコマンドは、レジストリキーの例です。  

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

```text
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

マニフェストキーを使ってディレクトリにレジストリキーを追加します。  

*   コマンドプロンプトでコマンドを実行します。    
    
    1.  次のコマンドを実行します。  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
    
*   ファイルを作成 `.reg` して実行します。  
    
    1.  次のコマンドをファイルにコピー `.reg` します。  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  ファイルを実行 `.reg` します。  
    
Microsoft Edge では、最初に32ビットレジストリが照会され、次に64ビットレジストリによってネイティブメッセージングホストが識別されます。  上記 `.reg` のファイルをバッチスクリプトの一部として実行する場合は、管理者のコマンドプロンプトを使用して実行していることを確認します。  

### [macOS](#tab/macos/)  

<a id="copy-manifest-file"></a>  

マニフェストファイルを保存するには、次のいずれかの操作を実行します。  

*   すべてのユーザーが使用できるシステム全体のネイティブメッセージングホストは、固定された場所に格納されます。  たとえば、マニフェストファイルは、次の場所に格納されている必要があります。 
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
*   現在のユーザーのみが利用できる、ユーザー固有のネイティブメッセージホストは、 `NativeMessagingHosts` ユーザープロファイルディレクトリのサブディレクトリにあります。  たとえば、マニフェストファイルは、次の場所に格納されている必要があります。  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
    In は、  `{Channel_Name}` `Microsoft Edge {Channel_Name}` 次のいずれかの値である必要があります。  
    
    *   Canary  
    *   Dev  
    *   Beta  

    安定したチャネルを使用する場合 `{Channel_Name}` は必須ではありません。  

### [Linux](#tab/linux/)  

<a id="copy-manifest-file"></a>  

マニフェストファイルを保存するには、次のいずれかの操作を実行します。  

*   すべてのユーザーが使用できるシステム全体のネイティブメッセージングホストは、固定された場所に格納されます。  マニフェストファイルは、次の場所に格納されている必要があります。  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   現在のユーザーのみが利用できる、ユーザー固有のネイティブメッセージホストは、 `NativeMessagingHosts` ユーザープロファイルディレクトリのサブディレクトリにあります。  マニフェストファイルは、次の場所に格納されている必要があります。  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

> [!NOTE]
> マニフェストファイルで読み取りアクセス許可を指定し、ホストランタイムでアクセス許可を実行していることを確認します。  

<!-- links -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developer.chrome.com/extensions/nativeMessaging)にあります。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge アドオン"
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
