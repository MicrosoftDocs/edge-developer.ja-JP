---
description: ユーザーを Microsoft Edge から Microsoft Edge に移動Internet Explorer
title: ユーザーを Microsoft Edge から Microsoft Edge に移動Internet Explorer
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
# <a name="moving-users-to-microsoft-edge-from-internet-explorer"></a>ユーザーを Microsoft Edge から Microsoft Edge に移動Internet Explorer  

多くの最新の Web サイトには、\(IE\) Internet Explorer互換性のないデザインがあります。  IE ユーザーが互換性のないパブリック Web サイトにアクセスすると、ユーザーがメッセージを受け取る可能性があります。  このメッセージには、Web サイトがブラウザーと互換性がないというメッセージが表示されます。  メッセージが表示された後、ユーザーは最新のブラウザーに手動で切り替える必要があります。  Microsoft Edge は、バージョン 84 から中断を最小限に抑えるために、ユーザーを自動的にリダイレクトする新しい機能をサポートしています。  IE ユーザーが IE と互換性のない Web サイトに移動すると、Windows は自動的にユーザーを Microsoft Edge にリダイレクトします。  リストの Web サイトを確認するには、[Microsoft Edge リストを必要とする [] に移動します][MicrosoftEdgeNeededgeV1]。

この記事では、次の概念について説明します。  

*   Web サイトがリストに追加される理由  
*   リダイレクトのユーザー エクスペリエンス  
*   リストへの更新を要求する  
    
## <a name="why-is-a-website-added-to-the-ie-compatibility-list"></a>IE 互換性リストに Web サイトが追加される理由  

IE 互換性リストは、次のアクションが発生した場合にのみ Web サイトを追加します。  

*   互換性上の理由から、ユーザーが別のブラウザーを使用する必要があるというメッセージを IE ユーザーに表示します。  
*   所有者は、IE 互換性リストに Web サイトを追加する要求を行います。  

## <a name="redirection-experience"></a>リダイレクト エクスペリエンス

Microsoft Edge へのリダイレクト時に、ユーザーは次のスクリーンショットで 1 回のダイアログを表示します。  ダイアログは、ユーザーに次の情報を提供します。  

*   Web サイトがリダイレクトされる理由について説明します。  
*   閲覧データと設定を IE から Microsoft Edge にコピーする同意を求めるメッセージがユーザーに表示されます。  

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

**[常**に閲覧データと基本設定を Internet Explorer から引き継ぐ] チェック ボックスをオンにしてユーザーが同意しない場合、**** ユーザーは [閲覧の続行] を選択して閲覧セッションを続行できます   。  

最後に、リダイレクトごとにアドレス バーの下に Web サイトの非互換性バナーが表示されます。  次の図に、Web サイトの非互換性バナーの例を示します。

:::image type="complex" source="../media/neededge-banner.msft.png" alt-text="最新のサイトに関する通知と、既定のブラウザーとして Microsoft Edge を設定するか、Microsoft Edge を探索するように求めるメッセージ" lightbox="../media/neededge-banner.msft.png":::
   最新のサイトに関する通知と、既定のブラウザーとして Microsoft Edge を設定するか、Microsoft Edge を探索するように求めるメッセージ  
:::image-end:::

Web サイトの非互換性バナーは、ユーザーに次の詳細を提供します。  

*   ユーザーが Microsoft Edge に切り替える必要があります。  
*   既定のブラウザーとして Microsoft Edge を設定する機能を提供します。  
*   Microsoft Edge を探索するオプションをユーザーに提供します。    
    
Web サイトが Microsoft Edge にリダイレクトInternet Explorer、次のいずれかのアクションが実行されます。

*   アクティブな IE タブに以前のコンテンツがない場合は、閉じます。  
*   アクティブな IE タブに以前のコンテンツがある場合は、Web サイトが Microsoft Edge にリダイレクトされた理由を説明する Microsoft サポート ページ [に移動します][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]。  

> [!NOTE]
> リダイレクト後、ユーザーは IE 互換性リストに含されていない Web サイトに対して引き続き IE を使用できます。  

## <a name="request-an-update-to-the-ie-compatibility-list"></a>IE 互換性リストへの更新を要求する  

IE 互換性リストは、次のバージョンの XML[ファイル microsoft.com。][MicrosoftOfficialHome]  このリストは、Web サイトを追加または削除するユーザーおよび Web サイト開発者の要求に応じて定期的に更新されます。  リストの更新プログラムは、ユーザー コンピューターに自動的にダウンロードされます。  

次の情報を電子メールで送信 [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] IE 互換性リストに追加または削除する Web サイトの情報を送信します。    

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

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "メールをメールに送信 ietoedge@microsoft.com"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft Official Home"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "Microsoft Edge リスト v1 xml が必要|Microsoft Edge"  

[MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]: https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554 "アクセスしようとしていた Web サイトは、ユーザーがアクセスInternet Explorer |Microsoft Officeサポート"  
