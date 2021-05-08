---
description: 検証済みストアを使用しない代替メソッドを使用して拡張機能を配布する方法について説明します。
title: 拡張機能を配布する代替メソッド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 3b2c72e13488632e2fadea2a7e8eb95888f67170
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343151"
---
# 代替拡張機能の配布方法  

通常、拡張機能は Microsoft Edge アドオン ストアを通じて配布されます。 開発者が代替メソッドを使用して拡張機能を配布する必要がある場合があります。 以下に例を示します。

1.  拡張機能は他のソフトウェアに関連付けられているので、バンドルされているソフトウェアの残りの部分と共にインストールする必要があります。   
1.  ネットワーク管理者は、組織全体に拡張機能を配布する必要があります。   

エッジ アドオン ストアから読み込まれない拡張機能は、外部にインストールされた拡張機能と呼ばれます。 次の一覧では、外部にインストールされた拡張機能を配布する別の方法を示します。 

*   Windows レジストリを使用します (Windows のみ)。  
*   基本設定 JSON ファイル (macOS と Linux) を使用します。  
    
## 始める前に  

Microsoft Edge アドオン ストアで拡張機能を発行するか、ファイルをパッケージ化し、コンピューターに正常にインストール `.crx` されたことを確認します。  ファイルをインストールする `.crx` 場合は、その URL で拡張子に移動 `update_URL` できます。  

また、次の情報を持っている必要があります。    

1.  ファイルのファイル `.crx` パス、または拡張子 `update_URL` のファイル パス。
1.  拡張機能のバージョン。  バージョン情報は、マニフェスト ファイル、またはパックされた拡張機能の読み込み後の Microsoft Edge `edge://extensions` で使用できます。   
1.  拡張機能の ID。  ID 情報は、パックされた拡張機能を読み込み後に Microsoft Edge `edge://extensions` で使用できます。  

> [!NOTE] 
> 次の例では、 `1.0` バージョンと ID `aaaaaaaaaabbbbbbbbbbcccccccccc` を使用します。  

## Windows レジストリを使用する (Windows のみ)  

Windows レジストリを使用して拡張機能を配布するには、次の手順を実行します。

1.  レジストリで次のキーを検索または作成します。  
    *   32 ビット Windows:  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions` .  
    *   64 ビット Windows:  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions` .  
1.  拡張機能の ID と同じ名前**** の [拡張機能] の下に新しいキーまたはフォルダーを作成します。 たとえば、名前を持つキーを作成します `aaaaaaaaaabbbbbbbbbbcccccccccc` 。  
1.  Extensions **キーで** プロパティを作成 `update_url` し、値をに設定します `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。  プロパティ `update_url` は、Microsoft Edge アドオン `.crx` ストア内の拡張機能のファイルをポイントします。  

    ```json
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
    > [!NOTE]
    > Chrome Web ストアから拡張機能をインストールする場合は、の値をに設定 `update_url` します `https://clients2.google.com/service/update2/crx` 。  
  
1.  に移動して、拡張機能が Microsoft Edge に表示されるのを確認します `edge://extensions` 。  

## 基本設定 JSON ファイルを使用する (macOS と Linux)  

基本設定 JSON ファイルを使用して拡張機能を配布するには、次の手順を実行します。

1.  Linux を使用する場合は、拡張機能がインストールされるコンピューターで拡張機能 `.crx` ファイルを使用できます。 拡張機能ファイル `.crx` をローカル ディレクトリにコピーするか、コンピューターから到達可能なネットワーク共有を使用します。 
1.  ファイルの名前が拡張子の ID に対応する JSON ファイルを作成します。 たとえば、ファイル名を使用して JSON ファイルを作成します `aaaaaaaaaabbbbbbbbbbcccccccccc.json` 。  
1.  オペレーティング システムに応じて、JSON ファイルを次のいずれかのフォルダーに保存します。   
    *   **macOS**  
        *   ユーザー固有: `~USERNAME/Library/Application Support/Microsoft Edge/External Extensions/`  
        *   すべてのユーザー: `/Library/Application Support/Microsoft/Edge/External Extensions/`  
        
        権限のないユーザーがすべてのユーザーに拡張機能をインストールしに行かねない場合は、拡張機能ファイルの読み取り専用を確認してください。 さらに、次の条件が満たされている必要があります。
        
        *   パス内のすべてのディレクトリは、ユーザー ルートによって所有されます。  
        *   パス内のすべてのディレクトリが、またはグループに `admin` 割り当 `wheel` てられます。  
        *   パス内のすべてのディレクトリは、ワールド書き込み可能ではありません。  
        *   パスにはシンボリック リンクも含めずに指定する必要があります。  
        
    *   **Linux**  
        *   ユーザー固有: `~/.config/microsoft-edge/External Extensions/`  
        *   すべてのユーザー: `/usr/share/microsoft-edge/extensions/`  
1.  シナリオに応じて、JSON ファイルに続く適切なコードをコピーします。 
    *   Linux にのみ適用されます。 ファイルからインストールする場合は、場所とバージョンを使用して指定 `external_crx` します `external_version` 。  
            
        ```json
        {
            "external_crx": "/home/share/extension.crx",
            "external_version": "1.0"
        }
        ```  

    *   macOS と Linux に適用されます。 からインストールする場合は `update_URL` 、 を使用して更新 URL を指定します `external_update_url` 。 
        
        Linux 上のローカル ファイルからのみインストールする場合は、次のコードを `.crx` JSON ファイルにコピーします。  
    
        ```json
        {
            "external_update_url": "http://myhost.com/mytestextension/updates.xml"
        }
        ```  
 
    *  macOS と Linux の Microsoft Edge アドオン ストアからインストールする場合は、次のコードを JSON ファイルにコピーします。
    
        ```json
        {
            "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
        }
        ```  
    
1.  特定の地域の拡張機能をインストールするには、サポートされている地域を使用して一覧表示します `supported_locale` 。  親を使用しているすべての言語の地域に拡張機能をインストールする親のローカルを指定することもできます。 たとえば、親ロケールを使用する場合、拡張機能は 、など、すべての英語ロケールに `en` `en-US` `en-GB` インストールされます。  ユーザーがブラウザーでロケールを変更すると、外部にインストールされている拡張機能がアンインストールされます。  任意のロケールの拡張機能をインストールするには、使用しません `supported_locales` 。  

    ```json
    {
        "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx",
        "supported_locales": [ "en", "fr", "de" ]
    }
    ```  

1.  に移動して、拡張機能が Microsoft Edge にインストールされていることを確認します `edge://extensions` 。  

## 外部にインストールされている拡張機能の更新とアンインストール

Microsoft Edge は、ブラウザーが起動する度にレジストリ内のメタデータ エントリをスキャンし、外部にインストールされている拡張機能に変更を加えます。  

拡張機能を新しいバージョンに更新するには、マニフェスト ファイルのバージョンを更新し、レジストリのバージョンを更新します。  

以前にコンピューターにインストールされたソフトウェアのバンドルの一部としてインストールされた、外部にインストールされた拡張機能をアンインストールする必要がある場合があります。  拡張機能をアンインストールするには、基本設定の JSON ファイルを削除するか、レジストリからキーを削除します。   

<!-- links -->  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  元のページは次 [のページに表示されます](https://developer.chrome.com/apps/external_extensions)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
