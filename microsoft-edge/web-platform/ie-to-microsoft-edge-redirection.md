---
description: Internet Explorer から Microsoft Edge にユーザーを移動させる
title: Internet Explorer から Microsoft Edge にユーザーを移動させる
author: MSEdgeTeam
ms.date: 11/13/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge, 互換性, Web プラットフォーム, internet explorer
ms.openlocfilehash: c2106955ed79bd28dc1f847dee220944bb014689
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461137"
---
# <a name="moving-users-to-microsoft-edge-from-internet-explorer"></a>Internet Explorer から Microsoft Edge にユーザーを移動させる  

多くの最新の Web サイトには、Internet Explorer \(IE\) と互換性のないデザインがあります。  IE ユーザーが互換性のないパブリック Web サイトにアクセスすると、メッセージを受け取る可能性があります。  このメッセージには、Web サイトがブラウザーと互換性がないという旨が表示されます。  メッセージが表示された後、ユーザーは最新のブラウザーに手動で切り替える必要があります。  中断を最小限に抑えるために、バージョン 84 から、Microsoft Edge では、ユーザーを自動的にリダイレクトする新しい機能がサポートされています。  IE ユーザーが IE と互換性のない Web サイトに移動すると、Windows によってユーザーが自動的に Microsoft Edge にリダイレクトされます。  一覧の Web サイトを確認するには、[[Microsoft Edge　一覧が必要][MicrosoftEdgeNeededgeV1]] に移動します。

この記事では、次の概念について説明します。  

*   Web サイトがリストに追加されている理由  
*   リダイレクトのユーザー エクスペリエンス  
*   リストへの更新を要求する  
    
## <a name="why-is-a-website-added-to-the-ie-compatibility-list"></a>IE 互換性リストに Web サイトが追加される理由  

IE 互換性リストは、次のアクションが発生した場合にのみ Web サイトを追加します。  

*   互換性上の理由から、ユーザーが別のブラウザーを使用する必要があるというメッセージを IE ユーザーに表示します。  
*   所有者が、IE 互換性リストに Web サイトを追加する要求を行います。  

## <a name="redirection-experience"></a>リダイレクト エクスペリエンス

Microsoft Edge へのリダイレクト時に、ユーザーは次のスクリーンショットに示すような 1 回限りのダイアログを表示します。  このダイアログは、ユーザーに次の情報を提供します。  

*   Web サイトがリダイレクトされる理由について説明します。  
*   閲覧データとユーザー設定を IE から Microsoft Edge にコピーすることに同意するようにユーザーに求めます。  

:::row:::
   :::column span="":::
      次の参照データがインポートされます。  
      
      *   お気に入り  
      *   パスワード  
      *   検索エンジン  
      *   タブを開く  
      *   履歴  
      *   設定  
      *   Cookie  
      *   ホーム ページ  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/neededge-dialog1.msft.png" alt-text="閲覧通知とデータと基本設定のインポートを求めるプロンプト" lightbox="../media/neededge-dialog1.msft.png":::
         閲覧通知とデータと基本設定のインポートを求めるプロンプト  
      :::image-end:::  
   :::column-end:::
:::row-end:::

ユーザーが **[常に閲覧データとユーザー設定を Internet Explorer から引き継ぐ**] のチェック ボックスをオンにして同意しない場合、ユーザーは **[閲覧の続行]** を選択して閲覧セッションを続行できます。  

最後に、リダイレクトごとにアドレス バーの下に Web サイトの非互換性バナーが表示されます。  次の図に、Web サイトの非互換性バナーの例を示します。

:::image type="complex" source="../media/neededge-banner.msft.png" alt-text="最新のサイトに関する通知と、既定のブラウザーを Microsoft Edge に設定するか、Microsoft Edge を探索するかを促すプロンプト" lightbox="../media/neededge-banner.msft.png":::
   最新のサイトに関する通知と、既定のブラウザーを Microsoft Edge に設定するか、Microsoft Edge を探索するかを促すプロンプト  
:::image-end:::

Web サイトの非互換性バナーは、ユーザーに次の詳細を提供します。  

*   ユーザーに Microsoft Edge に切り替えることを推奨します。  
*   既定のブラウザー Microsoft Edge を設定するよう提案します。  
*   Microsoft Edge を探索するオプションをユーザーに提供します。    
    
Web サイトが Internet Explorer から Microsoft Edge にリダイレクトされると、次のいずれかのアクションが発生します。

*   アクティブな IE タブに以前のコンテンツがない場合は、閉じます。  
*   アクティブな IE タブに以前のコンテンツがある場合は、[Web サイトが Microsoft Edge にリダイレクトされた理由を説明する Microsoft サポート ページ][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer] に移動します。  

> [!NOTE]
> リダイレクト後、ユーザーは IE 互換性リストに含されていない Web サイトに引き続き IE を使用できます。  

## <a name="request-an-update-to-the-ie-compatibility-list"></a>IE 互換性リストへの更新を要求する  

IE 互換性リストは、[microsoft.com][MicrosoftOfficialHome] にある XML ファイルです。  このリストは、Web サイトを追加または削除するユーザーおよび Web サイト開発者の要求に応じて定期的に更新されます。  リストの更新プログラムは、ユーザーのコンピューターに自動的にダウンロードされます。  

IE 互換性リストに追加または削除される Web　サイトについては、次の情報を [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] にメールしてください。    

*   所有者名  
*   企業タイトル  
*   メール アドレス  
*   会社名  
*   住所  
*   Web サイトのアドレス  
    
IE 互換性リストは 1 週間以内に更新されます。

> [!NOTE]
> IE の互換性リストは、パブリック サイトでのみ動作するように設計されています。  

<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "メールを ietoedge@microsoft.com に送信する"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft Official Home"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "リスト v1 Microsoft Edge xml ファイルが必要 | Microsoft Edge"  

[MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]: https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554 "アクセスしようとしていた Web サイトは、ユーザーがアクセス Internet Explorer で動作しません | Microsoft Office サポート"  
