---
description: この記事では、ユーザー エージェント クライアント Microsoft Edgeおよびユーザー エージェント文字列に関するドキュメントを提供します。
title: Web サイトのMicrosoft Edge検出する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、Web プラットフォーム、ユーザー エージェント文字列、ua 文字列、ua オーバーライド、ユーザー エージェント クライアント ヒント、ユーザー エージェント クライアント ヒント、ua クライアント ヒント、ua ch
ms.openlocfilehash: 1957bb5bd33d9d921d8a12e16a4a52a23836027b
ms.sourcegitcommit: e90bbc210b5d510004bbc2145d49e14fe72ed54b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2021
ms.locfileid: "11578781"
---
# <a name="how-to-detect-microsoft-edge-in-your-website"></a>Web サイトのMicrosoft Edge検出する方法  

ブラウザーは、Web サイトがブランドやバージョン番号などのブラウザー情報を検出するメカニズムを提供します。  このメカニズムは、ホスト オペレーティング システムなどの他のデバイス特性も検出します。  ユーザー エージェントでサポートされる 2 つのMicrosoft Edgeは[、User-Agent クライアント](#user-agent-client-hints)ヒントと[User-Agent 文字列です](#user-agent-string)。  数十年の使用の後、User-Agent文字列は古く、Web サイトの互換性の問題の原因として長い歴史を持っています。  代わりに、Microsoft Edgeチームは[、User-Agent クライアント](#user-agent-client-hints)ヒントという名前のブラウザー情報を取得するために、改善されたメカニズムを使用してください。  この記事では、ユーザー エージェント情報の取得Microsoft Edgeサポートする 2 つのメカニズムについて説明します。  

|  | サーバー側 | クライアント側 |  
|:--- |:--- |:--- | 
| **User-Agent クライアント ヒント** \(recommended\) | `Sec-CH-UA` HTTPS ヘッダー | `navigator.userAgentData` JavaScript メソッド |  
| **User-Agent 文字列** \(legacy\) | `User-Agent` HTTPS ヘッダー | `navigator.userAgent` JavaScript メソッド |  

Microsoft では、以下 [の理由により][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] 、可能な限り機能検出を使用してください。  

*   コードの保守性を向上します。  
*   コードのフラグ設定を減らします。  
*   文字列の変更によるコードのUser-Agentします。  
    
機能[の検出が][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]適用できない場合で、ユーザー エージェントの検出を使用する必要がある場合は、次の形式を使用して、Microsoft Edgeおよび Android のユーザー エージェントWindows検出します。  

## <a name="user-agent-client-hints"></a>User-Agent クライアント ヒント  

バージョン 90 Microsoft Edgeから、よりクリーンでプライバシーを保持する方法でブラウザー情報にアクセスします。  

### <a name="user-agent-client-hints-https-header"></a>User-Agent クライアント ヒント HTTPS ヘッダー  

既定では、Chromium含むMicrosoft Edge次の形式 `Accept-CH-UA` で応答ヘッダーを送信します。  

```https
Sec-CH-UA: "Chromium";v="91", "Microsoft Edge";v="91","Dummy;Browser Brand";v="99"
Sec-CH-UA-Mobile: ?0
```  

> [!NOTE]
> クライアント ヒントは、 を使用してセキュリティで保護された接続でのみ送信されます `HTTPS` 。  

既定では、次の低エントロピー ヒントが送信されます。  詳細にアクセスする必要がある場合は、次のいずれかの要求ヘッダーを送信します。  

#### <a name="user-agent-request-and-response-headers"></a>User-Agentヘッダーと応答ヘッダー  

| 要求ヘッダー | 応答値の例 |  
|:--- |:--- |  
| `Sec-CH-UA` | `"Chromium";v="91", "Microsoft Edge";v="91","GREASE";v="99"` |  
| `Sec-CH-UA-Mobile` | `false` |  
| `Sec-CH-UA-Full-Version` | `91.0.866.0` |  
| `Sec-CH-UA-Platform` | `Windows` |  
| `Sec-CH-UA Platform-Version` | `10.0` |  
| `Sec-CH-UA-Arch` | `x86` |  
| `Sec-CH-UA-Model` |  |  

### <a name="user-agent-client-hints-javascript-api"></a>User-Agent クライアント ヒント JavaScript API  

既定の応答の値は `navigator.userAgentData` 、次の形式を使用します。  

```javascript
{ brands: [ {brand: "Chromium","version":"91"}, {brand: "Microsoft Edge","version":"91"}, {brand: "GREASE","version":"99"}, ]
mobile: false }
```  

詳細な情報にアクセスする必要がある場合は [、getHighEntropyValues() メソッドを使用][GithubWicgUaClientHintsGethighentropyvalues] します。  

:::row:::
   :::column span="":::
      次のコード スニペットは要求を送信します。  
   :::column-end:::
   :::column span="":::
      次の応答を受け取る。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      ```javascript
         navigator.userAgentData.getHighEntropyValues(
             ["architecture", "model", "platform", "platformVersion", "uaFullVersion"])
             .then(ua => { console.log(ua) });
      ```  
   :::column-end:::
   :::column span="":::
      ```javascript
      {architecture: "x86", 
      model: "", 
      platform: "Windows", 
      platformVersion: "10.0", 
      uaFullVersion: "92.0.866.0"}
      ```  
   :::column-end:::
:::row-end:::  

## <a name="recommended-uses-of-user-agent-client-hints"></a>クライアント ヒントのUser-Agent使用  

ブランドのセットと関連付けられた表示順序は時間の間に変化しますので、返されるブランドの配列にインデックスをハードコードしたことがない必要があります。  Web サイトで同様の問題を早期に見つけるのに役立つため、ブラウザーには、一般的な文字列解析の問題のために、時間の間に変化し、破損する形式のブランド値が含 `GREASE` まれています。  

機能の検出を使用できない場合は[][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]、既知のブラウザーのハードコードされたリストChromium使用して検証を行う必要があります。  ハードコードされたブラウザー名の例には、 `Microsoft Edge` と が含まれます `Google Chrome` 。  機能の検出 [が適用][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] できない理由には、次のような状況が含まれる場合があります。  

*   新しいバージョンのChromium修正は避ける必要があります。影響を受けるブラウザーは、ブランドとバージョンの検証以外では検出が困難です。  
    
代わりに、ブランドを確認する必要があります。これにより、影響を受けるすべてのユーザーベースのブラウザーにChromium `Chromium` が適用されます。  


```javascript
function isChromium() {
    for (brand_version_pair in navigator.userAgentData.brands) {
        if (brand_version_pair.brand == "Chromium") {
            return true;
        }
    }
    return false;
}
```  

## <a name="user-agent-string"></a>ユーザー エージェント文字列  

可能な限り、Microsoft では、ユーザー エージェント文字列に基Microsoft Edgeブラウザー検出ロジックの使用を最小限に抑える必要があります。  ユーザー エージェントを検出する理由がある場合は、Microsoft Edgeクライアント ヒントをプライマリ検出ロジックとして[](#user-agent-client-hints)使用してください。  [User-Agent クライアント ヒントでは、](#user-agent-client-hints) 解析された文字列の必要な数も減らします。  ただし、従来の参照では、次の形式が文字列にUser-Agentされます。  

:::row:::
   :::column span="":::
      このWindows HTTP 要求 `User-Agent` ヘッダーは、次の形式を使用します。  
   :::column-end:::
   :::column span="":::
      Android では `User-Agent` 、HTTP 要求ヘッダーは次の形式を使用します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      ```https
      User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.85 Safari/537.36 Edg/90.0.818.46
      ```  
   :::column-end:::
   :::column span="":::
      ```https
      User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.85 Mobile Safari/537.36 Edg/90.0.818.46
      ```  
   :::column-end:::
:::row-end:::  

メソッドからの応答値 `navigator.userAgent` は、次の形式を使用します。  

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4501.0 Safari/537.36 Edg/91.0.866.0"
```  

プラットフォーム識別子は使用されるオペレーティング システムに基づいて変更され、バージョン番号も時間が経過すると増加します。  形式は、新しいトークンChromium追加したユーザー エージェントの形式 `Edg` と同じです。  Microsoft は、EdgeHTML に基づく従来のブラウザーで使用された文字列による互換性 `Edg` `Edge` の問題を回避Microsoft Edge選択しました。  トークン `Edg` は、iOS および Android で [使用される][WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper] 既存のトークンと一致しています。

## <a name="map-the-user-agent-string-to-browser-name"></a>ユーザー エージェント文字列をブラウザー名にマップする  

コードで使用する、より人間が読み取り可能なブラウザー名にユーザー エージェント文字列トークンをマップします。  これは、今日の Web 上の一般的なパターンです。  新しいトークンをブラウザー名にマップする場合、従来の Microsoft Edge ブラウザーで使用される名前とは異なる名前を使用して、Chromium ベースのブラウザーに適用されない従来の回避策を誤って適用しないようにお勧めします。 `Edg`

## <a name="user-agent-overrides"></a>ユーザー エージェントのオーバーライド  

Web サイトが新しいユーザー エージェントを認識Microsoft Edge場合があります。  その結果、Web サイトの機能のセットが正しく動作しない可能性があります。  Microsoft が問題の種類について通知を受け取った場合、Microsoft から \(a web サイトの所有者\) に連絡し、更新されたユーザー エージェントについて通知します。  

Microsoft が報告した問題に対処するには、Web サイトのユーザー エージェント検出ロジックを更新してテストする時間が必要な場合があります。  ユーザーの互換性を最大化するために、Microsoft Edge Beta安定チャネルはユーザー エージェントのオーバーライドの一覧を使用します。  Web サイトを更新する場合は、ユーザー エージェントの上書きを使用します。  Microsoft によって提供されるユーザー エージェントの上書きの一覧。  

オーバーライドは、特定の Web サイトの既定のユーザー エージェントMicrosoft Edge送信する新しいユーザー エージェント値を指定します。  現在適用されているユーザー エージェントオーバーライドの一覧を表示するには、次の操作を実行します。  

1.  [ファイル] または [Microsoft Edge Beta] チャネルを開きます。  
1.  `edge://compat/useragent` に移動します。  
    
Canary Microsoft Edge Dev チャネルは現在、ユーザー エージェントの上書きを受け取らない。  Canary Microsoft Edge開発チャネルには、既定のユーザー エージェントを使用するMicrosoft Edge提供されます。  Canary Microsoft Edge Dev チャネルを使用して、既定のユーザー エージェントによって発生する web サイトの問題を簡単Microsoft Edge再現します。  クライアント チャネルまたは Stable チャネルでユーザー エージェントの上書Microsoft Edge Beta無効にするには、次のアクションを実行します。  

1.  コマンド ライン アプリを開きます。  
1.  次のコード スニペットをコピーして貼り付けます。  
    
    ```shell
    --disable-domain-action-user-agent-override
    ```  
    
1.  コード スニペットをMicrosoft Edgeアプリを実行します。  
    
    ```shell
    {path/to/microsoft/edge.ext} --disable-domain-action-user-agent-override
    ```  
    
<!-- links -->  

[WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper]: https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer "Microsoft Edge iOS と Android 用: 開発者が知る必要がある|Microsoft Windowsブログ"  

[GithubWicgUaClientHintsGethighentropyvalues]: https://wicg.github.io/ua-client-hints#getHighEntropyValues "4.1.5. getHighEntropyValues メソッド - User-Agent クライアント ヒント |GitHub"  

[MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection "機能検出機能の実装|MDN"  
