---
description: Internet Explorer から Microsoft Edge にユーザーを移動する
title: Internet Explorer から Microsoft Edge にユーザーを移動する
author: MSEdgeTeam
ms.date: 11/06/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム、internet explorer
ms.openlocfilehash: 2e1488359e405247e290ad8f6300c480a7e20af6
ms.sourcegitcommit: 6ef48c8cda392c6bf8217cff5f696ac620d10739
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163208"
---
# Internet Explorer から Microsoft Edge にユーザーを移動する 

最新の web サイトの多くには、Internet Explorer \ (IE \) と互換性のないデザインが用意されています。  IE ユーザーが互換性のない一般向け web サイトにアクセスすると、ユーザーにメッセージが表示されることがあります。  このメッセージは、web サイトがブラウザーに対応していないことを示します。  メッセージが表示された後、ユーザーは、最新のブラウザーに手動で切り替えるように求められます。  バージョン84以降では、中断を最小限にするために、Microsoft Edge はユーザーを自動的にリダイレクトする新機能をサポートしています。  Ie と互換性のない web サイトに IE ユーザーが移動すると、Windows はユーザーを Microsoft Edge に自動的にリダイレクトします。  リスト上の web サイトを確認するには、「 [Microsoft Edge リストが必要][MicrosoftEdgeNeededgeV1]ですか?」を参照してください。

この記事では、次の概念について説明します。  

*   リダイレクトのユーザーエクスペリエンス  
*   リストの更新を要求する方法  
    
## Web サイトが IE 互換性リストに追加されているのはなぜですか?  

IE 互換性リストは、次の操作が発生した場合にのみ web サイトを追加します。  

*   互換性の理由により、ユーザーが別のブラウザーを使用する必要があることを示すメッセージが IE ユーザーに表示されます。  
*   所有者要求。 IE 互換性の一覧に web サイトを追加します。  
    
## IE 互換性の一覧を更新する  

IE 互換性リストは、 [microsoft.com][MicrosoftOfficialHome]上の XML ファイルです。  リストは、ユーザーと web サイトの開発者からの要求に応じて定期的に更新され、web サイトを追加または削除します。  リストの更新は、ユーザーのコンピューターに自動的にダウンロードされます。  

Web サイトを IE 互換リストから追加または削除するには、次の情報を [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] にメールで送信します。    

*   所有者の名前  
*   企業タイトル  
*   メール アドレス  
*   会社名  
*   住所  
*   Web サイトのアドレス  
    
> [!NOTE]
> IE 互換性リストは、パブリックサイトでのみ動作するように設計されています。  

<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "Ietoedge@microsoft.com にメールを送信する"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft オフィシャルホーム"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "Microsoft Edge リスト v1 xml が必要です |Microsoft Edge"  
