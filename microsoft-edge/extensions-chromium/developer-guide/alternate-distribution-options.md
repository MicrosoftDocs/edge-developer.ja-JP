---
description: 検証済みストアを使用しない別の方法を使用して拡張機能を配布する方法について説明します。
title: 拡張機能を配布する別の方法
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
# 代替の拡張配布方法  

通常、拡張機能は Microsoft Edge アドオン ストアを通じて配布されます。 開発者が別の方法を使用して拡張機能を配布する必要がある場合があります。 次に、例を示します。

1.  拡張機能は他のソフトウェアに関連付けられているので、バンドルされているソフトウェアの残りの部分と共にインストールする必要があります。   
1.  ネットワーク管理者は、拡張機能を組織全体に配布する必要があります。   

エッジ アドオン ストアから読み込まれない拡張機能は、外部にインストールされた拡張機能と呼ばれます。 次の一覧に、外部にインストールされた拡張機能を配布する別の方法を示します。 

*   Windows レジストリを使用します (Windows のみ)。  
*   Preferences JSON ファイル (macOS と Linux) を使用します。  
    
## 始める前に  

Microsoft Edge アドオン ストアで拡張機能を公開するか、ファイルをパッケージ化して、コンピューターに正常にインストール `.crx` するようにします。  ファイルを使用して `.crx` インストールする場合 `update_URL` は、その URL で拡張機能に移動できます。  

また、次の情報を持っている必要があります。    

1.  ファイルのファイル `.crx` パス、または拡張子 `update_URL` 。
1.  拡張機能のバージョン。  バージョン情報は、マニフェスト ファイル、またはパックされた拡張機能を読み込む後の Microsoft Edge `edge://extensions` で利用できます。   
1.  拡張機能の ID。  ID 情報は、Microsoft Edge でパックされた拡張機能を読み `edge://extensions` 込み後に利用できます。  

> [!NOTE] 
> 次の例では、 `1.0` バージョンと ID `aaaaaaaaaabbbbbbbbbbcccccccccc` を使用します。  

## Windows レジストリを使用する (Windows のみ)  

Windows レジストリを使用して拡張機能を配布するには、次の手順を実行します。

1.  レジストリで次のキーを検索または作成します。  
    *   32 ビット Windows:  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions` .  
    *   64 ビット Windows:  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions` .  
1.  拡張機能の ID と同じ名前の **Extensions** の下に新しいキーまたはフォルダーを作成します。 たとえば、名前を持つキーを作成します `aaaaaaaaaabbbbbbbbbbcccccccccc` 。  
1.  **Extensions キーで**、プロパティを作成 `update_url` し、値を次に設定します `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。  この `update_url` プロパティは `.crx` 、Microsoft Edge アドオン ストア内の拡張機能のファイルをポイントします。  

    ```json
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
    > [!NOTE]
    > Chrome Web ストアから拡張機能をインストールする場合は、次の値を設定 `update_url` します `https://clients2.google.com/service/update2/crx` 。  
  
1.  に移動して、拡張機能が Microsoft Edge に一覧表示されるのを確認します `edge://extensions` 。  

## Preferences JSON ファイル (macOS および Linux) を使用する  

基本設定の JSON ファイルを使用して拡張機能を配布するには、次の手順を実行します。

1.  Linux を使用する場合は、拡張機能がインストールされるコンピューターで拡張機能 `.crx` ファイルが利用可能な場所を確認します。 拡張機能ファイル `.crx` をローカル ディレクトリにコピーするか、コンピューターから到達可能なネットワーク共有を使用します。 
1.  ファイルの名前が拡張子の ID に対応する JSON ファイルを作成します。 たとえば、ファイル名を含む JSON ファイルを作成します `aaaaaaaaaabbbbbbbbbbcccccccccc.json` 。  
1.  使用しているオペレーティング システムに応じて、JSON ファイルを次のいずれかのフォルダーに保存します。   
    *   **macOS**  
        *   ユーザー固有: `~USERNAME/Library/Application Support/Microsoft Edge/External Extensions/`  
        *   すべてのユーザー: `/Library/Application Support/Microsoft/Edge/External Extensions/`  
        
        承認されていないユーザーがすべてのユーザーに拡張機能をインストールするのを防ぐには、拡張子ファイルが読み取り専用に設定されている必要があります。 さらに、次の条件が満たされている必要があります。
        
        *   パス内のすべてのディレクトリは、ユーザー ルートによって所有されます。  
        *   パス内のすべてのディレクトリは、1 つ以上のグループに `admin` 割り当 `wheel` てられます。  
        *   パス内のすべてのディレクトリは、ワールド書き込み可能ではありません。  
        *   パスにはシンボリック リンクも含めずに指定する必要があります。  
        
    *   **Linux**  
        *   ユーザー固有: `~/.config/microsoft-edge/External Extensions/`  
        *   すべてのユーザー: `/usr/share/microsoft-edge/extensions/`  
1.  シナリオに応じて、JSON ファイルに続く適切なコードをコピーします。 
    *   Linux にのみ適用されます。 ファイルからインストールする場合は、使用する場所とバージョンを指定 `external_crx` し、 `external_version`  
            
        ```json
        {
            "external_crx": "/home/share/extension.crx",
            "external_version": "1.0"
        }
        ```  

    *   macOS および Linux に適用されます。 からインストールする場合 `update_URL` は、次を使用して更新 URL を指定します `external_update_url` 。 
        
        Linux 上のローカル ファイルからのみインストールする場合は、次のコードを `.crx` JSON ファイルにコピーします。  
    
        ```json
        {
            "external_update_url": "http://myhost.com/mytestextension/updates.xml"
        }
        ```  
 
    *  macOS と Linux 上の Microsoft Edge アドオン ストアからインストールするときに、次のコードを JSON ファイルにコピーします。
    
        ```json
        {
            "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
        }
        ```  
    
1.  特定のローカルの拡張機能をインストールするには、次を使用してサポートされているローカルを一覧表示します `supported_locale` 。  親を使用しているすべての言語のローカルに拡張機能をインストールする親のローカルを指定することもできます。 たとえば、親ロケールを使用する場合、拡張機能は、すべての英語ロケール (たとえば、" など) `en` `en-US` `en-GB` にインストールされます。  ユーザーがブラウザーでロケールを変更すると、外部にインストールされた拡張機能がアンインストールされます。  任意のロケールの拡張機能をインストールするには、使用しません `supported_locales` 。  

    ```json
    {
        "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx",
        "supported_locales": [ "en", "fr", "de" ]
    }
    ```  

1.  に移動して、拡張機能が Microsoft Edge にインストールされていることを確認します `edge://extensions` 。  

## 外部にインストールされた拡張機能を更新およびアンインストールする

Microsoft Edge は、ブラウザーが起動するごとにレジストリ内のメタデータ エントリをスキャンし、外部にインストールされている拡張機能に変更を加えます。  

拡張機能を新しいバージョンに更新するには、マニフェスト ファイル内のバージョンを更新し、レジストリ内のバージョンを更新します。  

以前にコンピューターにインストールされたソフトウェアのバンドルの一部としてインストールされた、外部にインストールされた拡張機能をアンインストールする必要がある場合があります。  拡張機能をアンインストールするには、ユーザー設定の JSON ファイルを削除するか、レジストリからキーを削除します。   

<!-- links -->  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  元のページはここ [です](https://developer.chrome.com/apps/external_extensions)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
