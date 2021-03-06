---
ms.assetid: ''
description: 一定の期間安全に実験し、新しいプラットフォーム機能に関するフィードバックを提供します。
title: 元の試用版
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, origin trials, developer
ms.openlocfilehash: cc03ec556d4b32ca37cebcd4ee7ba155bfe4404b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397546"
---
# <a name="use-origin-trials-in-microsoft-edge"></a>Microsoft Edge で Origin Trials を使用する  

開発者は、Origin Trials を使用して、限られた期間、ライブ サイトで実験的な API を試用できます。  Origin Trials を使用する場合、サイトにアクセスした Microsoft Edge のユーザーは、実験的な API を使用するコードを実行できます。  各ユーザー コンピューター上の実験的な API にアクセスするには、機能フラグに移動して有効 `edge://flags` にする必要があります。  詳細については、実験的な [API に移動します][DeveloperMicrsoftEdgeOriginTrials]。  さらに、API の設計、使用例、API の使用経験に関するフィードバックをブラウザー エンジニアや Web 標準コミュニティに提供することもできます。  

## <a name="get-started-using-origin-trials"></a>Origin Trials の使用を開始する  

Microsoft Edge で使用できる実験的 API の詳細については [、「Microsoft Edge Origin Trials Developer Console」に移動します][DeveloperMicrsoftEdgeOriginTrials]。  Microsoft Edge の最小バージョン要件と試用終了日を確認して、Web サイトで実験的な API を使用する適合性を評価してください。  

> [!NOTE]
> 次の状況が発生した場合、実験は計画より早く終了する可能性があります。  
> *   大規模なセキュリティ インシデント。  
> *   Web 開発者のニーズを満たすために大幅な再設計が必要な十分なフィードバックが収集された場合。  
> いずれの場合も、テストに現在登録されているすべての開発者に通知メールが送信されます。  

### <a name="register-for-a-trial-of-an-experimental-api"></a>実験的な API の試用版に登録する  

実験的な API の試用版に登録するには、次の手順を使用します。  

1.  Microsoft [Edge Origin Trials Developer Console ページにアクセス][DeveloperMicrsoftEdgeOriginTrials] します。  
1.  使用可能な実験の [登録] ボタンを選択します。  
1.  GitHub のユーザー名とパスワードを使用して開発者コンソールにサインインします。  
1.  **[MicrosoftEdge の承認] を選択します**。  
1.  フォームに入力します。  
    
    > [!NOTE]
    > 単一またはすべてのサブドメインを登録するには、[設定] を [ に設定] `Do you need to match all subdomains for the provided origin?` を選択します `Yes` 。  たとえば、単 `https://dev.contoso.com` 一のドメインであり、ワイルドカード `https://*.contoso.com` を使用してすべてのサブドメインを表します。  
    
    > [!IMPORTANT]
    > 次の元の形式は使用されません。  
    > *   原点のサブフォルダーを指定する。  以下に例を示します。 `https://contoso.com/path/subfolder`  
    > 
    > *   クエリ文字列パラメーターでオリジンを使用する。  以下に例を示します。 `https://contoso.com/path/feature?query_parameter=12345`  
    
1.  **[ACCEPT] と [登録] を選択します**。  
    
### <a name="apply-your-token"></a>トークンを適用する  

トークンは即座に生成され [、Microsoft Edge Origin Trials Developer Console ページに表示][DeveloperMicrsoftEdgeOriginTrials] されます。  Web サイトで試用版の使用を開始するには、次のいずれかの方法でトークンをページに適用します。  

*   実験的 `origin-trial` な API を使用する各ページのタグに属性値とトークン `meta` を追加します。  
    
    ```html
    <meta http-equiv="origin-trial" content="replace-with-your-token">
    ```  
    
*   サーバー `Origin-Trial` の HTTP 応答ヘッダーに追加します。  
    
    ```json
    Origin-Trial: replace-with-your-token
    ```  
    
> [!NOTE]
> トークンは 6 週間有効です。  試用版が終了する前に、フィードバックを求める通知メールが送信され、トークンの有効期限が切れる前に試用版の更新を検討してください。  

### <a name="opt-out-of-an-experiment"></a>実験をオプトアウトする  

実験をオプトアウトするには、次のいずれかの方法を使用してトークンを削除します。  

*   実験 `meta` API を使用したページごとにタグを削除します。  
    
    ```html
    <meta http-equiv="origin-trial" content="your-token">
    ```  
    
*   サーバー `Origin-Trial` の HTTP 応答ヘッダーから削除します。  
    
    ```json
    Origin-Trial: your-token
    ```  
    
### <a name="detect-experimental-features-and-provide-a-fallback"></a>実験的な機能を検出し、フォールバックを提供する  

実験的な API を使用する場合は、Web サイトのすべての訪問者に作業エクスペリエンスを提供してください。  訪問者は、コードに追加した実験的な API をサポートしていないブラウザーを使用できます。  さらに、トークンを更新する前にトークンの有効期限が切れると、実験的な API は使用できなくなったので、エラーが発生する可能性があります。  このような状況を回避するには、ブラウザーで使用可能な機能を検出してください。  詳細については、「機能検出の実装 [」に移動します][MDNImplementingFeatureDetection]。

### <a name="roadmap-for-allowed-origins"></a>許可されたオリジンのロードマップ  

今日の Microsoft Edge Origin Trials ポータルでは SSL Enabled Origins のみをサポートしています。つまり、テストに登録するには、WEB サイトに HTTPS が適切に実装されている必要があります。  将来、次のセキュリティで保護された発生元が計画されています。  

*   実験 `http://localhost` の原点として登録します。  今日使用 `http://localhost` するには、実験に移動 `edge://flags` して [有効] に **設定します**。  
*   プレフィックスが付いたオ `extensions://` リジンを持つ拡張機能を使用して、実験に登録します。  
    
<!-- links -->  

[DeveloperMicrsoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Microsoft Edge Origin Trials Developer Console |Microsoft Docs"  

[MDNImplementingFeatureDetection]: https://developer.mozilla.org/docs/learn/tools_and_testing/cross_browser_testing/feature_detection "機能検出機能の実装|MDN"  
