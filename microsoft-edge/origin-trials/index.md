---
ms.assetid: ''
description: 一定期間、安全なテストを行い、新しいプラットフォーム機能についてフィードバックを提供します。
title: オリジン試用版
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、元の試用、開発者
ms.openlocfilehash: 470896435ab348419749a7de00adcdb83b784df3
ms.sourcegitcommit: 5cbc9237363b3a8ba212ca128aa03c71a33ec86f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "10846529"
---
# Microsoft Edge で元の試用版を使用する  

開発者は、一定期間、実際のサイトで実験的な Api を試すために、オリジンの試用版を使用する場合があります。  元の試用版を使用している場合、サイトにアクセスする Microsoft Edge のユーザーは、実験的な Api を使うコードを実行する可能性があります。  各ユーザーコンピューターの実験的な Api にアクセスするには、機能のフラグを設定して有効にする必要はありません `edge://flags` 。  詳しくは、「[実験的な api][DeveloperMicrsoftEdgeOriginTrials]」をご覧ください。  さらに、API の設計、ユースケース、または Api を使用したブラウザーエンジニアと web standard コミュニティのエクスペリエンスについて、フィードバックを提供することができます。  

## 元の試用版の使用を開始する  

Microsoft Edge で利用できる実験的な Api の詳細については、 [Microsoft Edge オリジンの試用版の開発者コンソール][DeveloperMicrsoftEdgeOriginTrials]に関する情報を参照してください。  Web サイトで実験的な Api を使うことができないかどうかを評価するには、Microsoft Edge の最小バージョン要件とトライアル終了日を確認してください。  

> [!NOTE]
> 次のいずれかの状況が発生した場合、実験は計画よりも早く終了する可能性があります。  
> *   重大なセキュリティインシデント。  
> *   十分なフィードバックが収集された場合は、web 開発者のニーズを満たすために大きな再設計が必要であることを示します。  
> どちらの場合も、実験に現在登録されているすべての開発者に通知メールが送信されます。  

### 実験的な API の試用版に登録する  

実験的な API の試用版を登録するには、次の手順に従います。  

1.  [Microsoft Edge の [試用版の開発者用コンソール][DeveloperMicrsoftEdgeOriginTrials]] ページにアクセスします。  
1.  利用可能な実験のいずれかで [登録] ボタンを選択します。  
1.  GitHub のユーザー名とパスワードを使って、開発者コンソールにサインインします。  
1.  [**承認 MicrosoftEdge**] を選びます。  
1.  フォームに入力します。  
    
    > [!NOTE]
    > 1つまたはすべてのサブドメインを登録するには、[設定の設定] `Do you need to match all subdomains for the provided origin?` を選び `Yes` ます。  たとえば、 `https://dev.contoso.com` は単一ドメインであり、ワイルドカードを使ってすべてのサブドメインを `https://*.contoso.com` 表します。  
    
    > [!IMPORTANT]
    > 次の元の形式は使用できません。  
    > *   元のサブフォルダーを指定します。  以下に例を示します。 `https://contoso.com/path/subfolder`  
    > 
    > *   クエリ文字列パラメーターでの原点の使用。  以下に例を示します。 `https://contoso.com/path/feature?query_parameter=12345`  
    
1.  [**承諾して登録**] を選びます。  

### トークンを適用する  

トークンはすぐに生成され、 [Microsoft Edge の [開発者向け] 本体][DeveloperMicrsoftEdgeOriginTrials]のページに表示されます。  Web サイトの試用版の使用を開始するには、次のいずれかの方法を使用して、トークンをページに適用します。  

*   `origin-trial` `meta` 実験的 API を使用するすべてのページで、属性値とトークンをタグに追加します。  
    
    ```html
    <meta http-equiv="origin-trial" content="replace-with-your-token">
    ```  
    
*   `Origin-Trial`サーバーの HTTP 応答ヘッダーにを追加します。  
    
    ```json
    Origin-Trial: replace-with-your-token
    ```  
    
> [!NOTE]
> トークンは6週間有効です。  試用期間が終了する前に、フィードバックを求めるメッセージが送信され、トークンの有効期限が切れる前に試用版の更新を検討するように求められます。  

### 実験をやめる  

試験的機能を無効にするには、次のいずれかの方法を使用してトークンを削除します。  

*   `meta`実験的 API を使用したすべてのページからタグを削除します。  
    
    ```html
    <meta http-equiv="origin-trial" content="your-token">
    ```  
    
*   `Origin-Trial`サーバーの HTTP 応答ヘッダーから削除します。  
    
    ```json
    Origin-Trial: your-token
    ```  
    
### 実験的な機能を検出し、フォールバックを提供する  

実験的 Api を使用している場合は、web サイトの全利用者に対して動作環境を提供していることを確認します。  閲覧者は、コードに追加した実験的 Api をサポートしていないブラウザーを使用する可能性があります。  さらに、更新前にトークンの有効期限が切れた場合、実験的 API は使用できなくなり、エラーが発生する可能性があります。  この問題を回避するには、ブラウザーで利用できる機能を検出していることを確認します。  詳しくは、「[機能の検出の実装][MDNImplementingFeatureDetection]」をご覧ください。

### 許可元のロードマップ  

Microsoft Edge オリジンの試用版ポータルでは、現時点では SSL を有効にした元のサイトのみがサポートされています。つまり、実験の登録に HTTPS が適切に実装されている必要があります。  今後、次のセキュリティ保護元が計画されています。  

*   `http://localhost`実験の起点として登録します。  今日を使用するには `http://localhost` 、に移動 `edge://flags` して、実験を [**有効**] に設定します。  
*   "元の拡張子" というプレフィックスを使用して、試験的機能 `extensions://` に登録します。  
    
<!-- links -->  

[DeveloperMicrsoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Microsoft Edge オリジン試用開発者コンソール |Microsoft ドキュメント"  

[MDNImplementingFeatureDetection]: https://developer.mozilla.org/docs/learn/tools_and_testing/cross_browser_testing/feature_detection "機能検出の実装 |MDN"  
