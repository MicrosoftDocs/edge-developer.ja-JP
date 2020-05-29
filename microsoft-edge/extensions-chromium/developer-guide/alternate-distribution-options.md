---
description: 検証済みストア以外のメカニズムによって内線番号を配布するプロセス
title: 内線番号を配布する別の方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/02/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: a1a3ffe7a54f96df7e665ab5dc6f5b99bacb8b8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569585"
---
# 内線番号を配布する別の方法  

他のソフトウェアのインストールプロセスの一環として、または組織全体で拡張機能を配布するネットワーク管理者を配布する場合は、Microsoft Edge は次の拡張インストール方法をサポートしています。  

*   **Windows レジストリを使用する \ (Windows のみ)**  

Microsoft Edge では、でホストされている拡張機能のインストールをサポート `update_URL` しています。  Windows では、 `update_URL` 拡張機能がホストされている必要がある Microsoft Edge アドオンカタログ (Microsoft Edge アドオン \) をポイントする必要があります。  

> [!NOTE]
> MacOS 用の設定 json ファイルを使用した拡張の外部インストール <!--and Linux--> はまだサポートされていません。  この機能のサポートは間もなく利用可能になります。

## Windows レジストリを使用する  

まず、Microsoft Edge のアドオンで拡張機能を公開するか、または crx ファイルをパッケージ化して正常にインストールされることを確認します。  

Windows のレジストリ経由で拡張機能をインストールするには、次の手順を実行します。  

*   レジストリで次のキーを検索または作成します。  
    *   32ビット版の Windows:  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions`  
    *   64ビット版の Windows:  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions`  
*   拡張機能の ID と同じ名前 (\ など) で、Extensions キーの下に新しいキー \ (フォルダー \) を作成 `aaaaaaaaaabbbbbbbbbbcccccccccc` します。  
*   内線キーで、プロパティを作成し、 `update_url` 次の値に設定します。 `https://edge.microsoft.com/extensionwebstorebase/v1/crx` \ (これは、Microsoft Edge アドオンの内線番号の crx を指します)。 Chrome Web ストアから拡張機能をインストールする場合は、Chrome Web ストアの更新 URL を入力してください `https://clients2.google.com/service/update2/crx` 。  
    
    ```javascript
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
*   ブラウザを起動して「」に移動し `edge://extensions` ます。表示される拡張子が表示されます。  

## 更新とアンインストール  

Microsoft Edge は、ブラウザーが起動するたびに、レジストリのメタデータエントリをスキャンし、インストールされている外部拡張機能に必要な変更を加えます。  

拡張機能を新しいバージョンに更新するには、ファイルを更新してから、レジストリのバージョンを更新します。  

拡張機能をアンインストールするには (たとえば、ソフトウェアがアンインストールされた場合など)、設定ファイル \ ( `aaaaaaaaaabbbbbbbbbbcccccccccc.json` \) またはレジストリからメタデータを削除します。  

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developer.chrome.com/apps/external_extensions)にあります。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
