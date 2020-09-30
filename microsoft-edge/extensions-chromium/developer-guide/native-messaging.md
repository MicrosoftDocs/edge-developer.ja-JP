---
description: ネイティブメッセージングのドキュメント
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 9d33fc4e8c9449d539b6ea82cca87c3aad4d564e
ms.sourcegitcommit: 39636248d0266730089aa2e57b9cf04d9feb363d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088556"
---
# ネイティブ メッセージング  

拡張機能は、メッセージパッシング Api を使って、ユーザーのデバイスにインストールされているネイティブ Win32 アプリケーションと通信できます。 ネイティブのアプリケーションホストでは、標準の入力と標準の出力を使って、拡張機能を使ってメッセージを送受信できます。 ネイティブメッセージングを使用する拡張機能は、他の拡張機能と同様に Microsoft Edge にインストールされます。 ただし、ネイティブアプリケーションは Microsoft Edge でインストールまたは管理されません。

拡張機能とネイティブアプリケーションホストを取得するには、次の操作を行います。

1. 拡張機能とホストをまとめてパッケージ化します。 ユーザーがパッケージをインストールすると、拡張機能とホストの両方がインストールされます。
1. [Microsoft Edge][EdgeAddons]のアドオンストアから拡張機能をインストールし、拡張機能によって、ホストのインストールをユーザーに求めます。 

ネイティブアプリケーションホストでメッセージを送受信するための拡張機能を設定するには、次の手順を参照してください。

### 手順 1: 拡張機能マニフェストにアクセス許可を追加する

ファイルの拡張機能の **manifest.js** に nativeMessaging 権限を追加します。 次に、manifest.jsの例を示します。

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

### 手順 2: ネイティブメッセージングホストマニフェストファイルを作成する
    
ネイティブアプリケーションでは、ネイティブメッセージングホストマニフェストファイルを提供する必要があります。 このマニフェストファイルには、ネイティブメッセージングホストの実行可能ファイルへのパス、拡張機能との通信方法、および通信できる許可された拡張機能の一覧が含まれています。 ブラウザーはネイティブメッセージングホストマニフェストを読み取り、検証しますが、ブラウザーによってインストールまたは管理されることはありません。 ホストマニフェストファイルは、次のフィールドを含む有効な json ファイルである必要があります。

    
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




| 名前 | 説明 |  
|:--- |:--- |  
| `name` | ネイティブメッセージングホストの名前。 クライアントは、またはにこの文字列を渡し `runtime.connectNative` `runtime.sendNativeMessage` ます。  この名前には、小文字の英数字、アンダースコア、ドットを含める必要があります。  名前の先頭または末尾にドットを使用することはできません。ドットの後に別のドットを付けることはできません。 |  
| `description` | アプリケーションの簡単な説明。 |  
| `path` | ネイティブメッセージングホストバイナリへのパス。 Windows デバイスでは、マニフェストファイルを含むディレクトリへの相対パスを使うことができます。 MacOS と Linux では、パスは絶対パスにする必要があります。 ホストプロセスは、現在のディレクトリがホストバイナリを含むディレクトリに設定された状態で開始されます。 たとえば、このパラメーターがに設定されている場合、 `C:\Application\nm_host.exe` 現在のディレクトリを使ってバイナリが開始され `C:\Application\` ます。 |  
| `type` | ネイティブメッセージングホストとの通信に使用されるインターフェイスの種類。  現在、このパラメーターに指定できる値は1つだけ `stdio` です。  この値は、Microsoft Edge がホストとの通信に使用することを示し `stdin` `stdout` ます。 |  
| `allowed_origins` |  ネイティブメッセージングホストにアクセスできる拡張機能の一覧です。  アプリケーションで拡張機能を識別して通信できるようにするには、 `allowed_origins` `chrome-extension://[Microsoft-Catalog-extensionID]` ネイティブメッセージングホストマニフェストファイルにを設定します。 |  


開発中に、拡張機能をサイドローディングして、ホストとのネイティブメッセージングをテストすることができます。
1. に移動 `edge://extensions` して、[開発者モード] のトグルボタンをオンにします。 
1. [アンパックの読み込み] を選択し、サイドローディングに拡張パッケージを選択します。  
1. [OK] をクリックします。
1. ページに `edge://extensions` 拡張機能の一覧が表示されるようになったことを確認します。 
1. ページの内線番号リストからキーをコピーします。

内線番号をユーザーに配布する準備ができたら、Microsoft Edge のアドオンストアに拡張機能を公開します。 公開された拡張機能の拡張 ID は、サイドローディングの拡張機能で使用される ID と異なる場合があります。 ID が変更された場合は、公開された `allowed_origins` 拡張機能の id でホストマニフェストファイル内で更新します。 



### 手順 3: ネイティブメッセージングホストマニフェストファイルをシステムにコピーする

最後の手順では、ネイティブのメッセージングホストマニフェストファイルをコンピューターにコピーし、正しく構成されていることを確認します。 プラットフォームによって異なるため、ネイティブメッセージングホストファイルが予期した場所に配置されるようにするには、次の手順を実行します。
    
**Windows**。 マニフェストファイルは、ファイルシステム内の任意の場所に配置されている可能性があります。 アプリケーションのインストーラーでは、レジストリキーを作成し、そのキーの既定値をマニフェストファイルの完全パスに設定する必要があります。 次のコマンドは、レジストリキーの例です。
    
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`  
    または  
`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`,  
    
コマンドプロンプトで次のコマンドを実行して、マニフェストファイルを含むフォルダーにレジストリキーを追加します。
    
```shell
REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
```  
    
または、次のコマンドを .reg ファイルにコピーして実行し、レジストリキーを追加します。 
    
```shell
Windows Registry Editor Version 5.00
[HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
@="C:\\path\\to\\nmh-manifest.json"
``` 

  Microsoft Edge では、最初に32ビットレジストリが照会され、次に64ビットレジストリによってネイティブメッセージングホストが識別されます。 上記の .reg ファイルをバッチスクリプトの一部として実行する場合は、管理者のコマンドプロンプトを使用して実行していることを確認します。


**macOS**。 マニフェストファイルは、次のように保存する必要があります。

1. すべてのユーザーが使用できるシステム全体のネイティブメッセージングホストは、固定された場所に格納されます。 たとえば、マニフェストファイルが保存されている必要があります。 `/Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json`

1. 現在のユーザーのみが利用できる、ユーザー固有のネイティブメッセージホストは、ユーザープロファイルディレクトリの NativeMessagingHosts サブディレクトリにあります。 たとえば、マニフェストファイルが保存されている必要があります。  
    `~/Library/Application Support/Microsoft Edge <ChannelName>/NativeMessagingHosts/com.my_company.my_application.json`

    は `ChannelName` 、カナリア、Dev、またはβです。 安定したチャネルを使用する場合は、必須では `ChannelName` ありません。


**Linux** マニフェストファイルは、次のように保存する必要があります。

1. システム全体のネイティブメッセージングホスト:  `~/.config/microsoft-edge/NativeMessagingHosts`

1. ユーザー固有のネイティブメッセージホスト:  `/etc/opt/edge/native-messaging-hosts`


> [!NOTE]
> マニフェストファイルで読み取りアクセス許可を指定し、ホストの実行可能ファイルでアクセス許可を実行していることを確認します。


> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developer.chrome.com/extensions/nativeMessaging)にあります。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  


<!-- image links -->  

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge アドオン"
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
