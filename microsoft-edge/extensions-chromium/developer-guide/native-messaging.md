---
description: Chrome のドキュメントとのネイティブメッセージの違い
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 811468e5f92319107c60606bc9268a9f7a25e560
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015678"
---
# ネイティブ メッセージング  

Microsoft Edge では、microsoft edge アドオンカタログ (Microsoft Edge アドオン \) からの拡張機能が、メッセージパッシング Api を使用してネイティブアプリケーションでメッセージを交換できるようになりました。  この機能を有効にするには、ネイティブアプリケーションのネイティブメッセージングホストを実装するときに、次の点を確認する必要があります。  

<!--
 > [!NOTE]
> Native messaging is currently not supported on macOS and Linux version of Microsoft Edge.  This feature support is planned to be implemented soon.  -->  

1.  **ネイティブメッセージングホスト**:  
    
    ネイティブメッセージングホストを登録するために、アプリケーションは、ネイティブメッセージングホスト構成を定義するマニフェストファイルをインストールする必要があります。  マニフェストファイルの例を次に示します。  
    
    ```xml
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
    
ネイティブメッセージングホストマニフェストファイルは、有効な JSON であり、次のフィールドが含まれている必要があります。  

| 名前 | 説明 |  
|:--- |:--- |  
| `name` | ネイティブメッセージングホストの名前。 クライアントは、またはにこの文字列を渡し `runtime.connectNative` `runtime.sendNativeMessage` ます。  この名前には、小文字の英数字、アンダースコア、ドットを含める必要があります。  名前の先頭または末尾にドットを使用することはできません。ドットの後に別のドットを付けることはできません。 |  
| `description` | 短いアプリケーションの説明。 |  
| `path` | ネイティブメッセージングホストバイナリへのパス。  Windows では、パスはマニフェストファイルが配置されているディレクトリに関連している場合があります。  MacOS では、パスは絶対パスにする必要があります。  ホストプロセスは、現在のディレクトリがホストバイナリを含むディレクトリに設定された状態で開始されます。 たとえば、このパラメーターがに設定されている場合、 `C:\Application\nm_host.exe` 現在のディレクトリを使ってバイナリが開始され `C:\Application\` ます。 |  
| `type` | ネイティブメッセージングホストとの通信に使用されるインターフェイスの種類。  現在、このパラメーターに指定できる値は1つだけ `stdio` です。  この値は、Chrome で `stdin` ホストと `stdout` 通信するために使用することを示します。 |  
| `allowed_origins` |  ネイティブメッセージングホストにアクセスする必要がある拡張機能の一覧。  ネイティブアプリケーションで Microsoft Edge のアドオン拡張機能を使用できるようにするには、 `allowedorigins` `extension://[Microsoft-Catalog-extensionID]` ネイティブのメッセージングホストマニフェストファイルにを設定します。 |  

1.  **ネイティブメッセージングホストの場所**  
    
    マニフェストファイルの場所はプラットフォームによって異なります。  
    
    Windows では、マニフェストファイルはファイルシステムの任意の場所に配置されている可能性があります。  アプリケーションインストーラーは、レジストリキーを作成する必要がある  
    
    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`  
    または  
    `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`,  
    
    そのキーの既定値をマニフェストファイルの完全パスに設定します。  たとえば、次のコマンドを使用します。  
    
    ```shell
    REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
    ```  
    
    または、次の .reg ファイルを使用します。  
    
    ```shell
    Windows Registry Editor Version 5.00
    [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
    @="C:\\path\\to\\nmh-manifest.json"
    ```  
    
    Microsoft Edge でネイティブメッセージホストを検索すると、32ビットのレジストリが最初に照会され、次に64ビットのレジストリが照会されます。  

MacOS では、システム全体のネイティブメッセージングホストは固定された場所で検索されますが、ユーザーレベルのネイティブメッセージングホストは、という名前のユーザープロファイルディレクトリ内のサブディレクトリで検索され `NativeMessagingHosts` ます。  

MacOS での Microsoft Edge \ (システム全体 \):  
`/Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json`  

MacOS での Microsoft Edge \ (ユーザー固有、既定のパス \):  
`~/Library/Application Support/Microsoft Edge <ChannelName>/ NativeMessagingHosts/com.my_company.my_application.json`  

`<ChannelName>` は、カナリア、Dev、またはベータ版の可能性があります。 安定したチャネルの場合にのみ `Microsoft Edge` 使用する必要があり `<ChannelName` ます。>' は必要ありません。

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developer.chrome.com/extensions/nativeMessaging)にあります。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
