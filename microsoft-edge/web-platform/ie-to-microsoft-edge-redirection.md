---
description: Internet Explorer から Microsoft Edge にユーザーを移動する
title: Internet Explorer から Microsoft Edge にユーザーを移動する
author: MSEdgeTeam
ms.date: 11/13/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム、internet explorer
ms.openlocfilehash: 872bd5ec52f471e4958ef7354c046ec30f1ba72e
ms.sourcegitcommit: 62258ce0ef469948ca8af42141d02aa9719243f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168368"
---
# Internet Explorer から Microsoft Edge にユーザーを移動する  

最新の web サイトの多くには、Internet Explorer \ (IE \) と互換性のないデザインが用意されています。  IE ユーザーが互換性のない一般向け web サイトにアクセスすると、ユーザーにメッセージが表示されることがあります。  このメッセージは、web サイトがブラウザーに対応していないことを示します。  メッセージが表示された後、ユーザーは、最新のブラウザーに手動で切り替えるように求められます。  バージョン84以降では、中断を最小限にするために、Microsoft Edge はユーザーを自動的にリダイレクトする新機能をサポートしています。  Ie と互換性のない web サイトに IE ユーザーが移動すると、Windows はユーザーを Microsoft Edge に自動的にリダイレクトします。  リスト上の web サイトを確認するには、「 [Microsoft Edge リストが必要][MicrosoftEdgeNeededgeV1]ですか?」を参照してください。

この記事では、次の概念について説明します。  

*   Web サイトがリストに追加される理由  
*   リダイレクトのユーザーエクスペリエンス  
*   リストの更新を要求する  
    
## Web サイトが IE 互換性リストに追加されているのはなぜですか?  

IE 互換性リストは、次の操作が発生した場合にのみ web サイトを追加します。  

*   互換性の理由により、ユーザーが別のブラウザーを使用する必要があることを示すメッセージが IE ユーザーに表示されます。  
*   所有者要求。 IE 互換性の一覧に web サイトを追加します。  

## リダイレクト エクスペリエンス

Microsoft Edge へのリダイレクトでは、ユーザーは次のスクリーンショットに1回限りのダイアログを表示します。  このダイアログボックスでは、次の情報をユーザーに提供します。  

*   Web サイトがリダイレクトされる理由について説明します。  
*   IE から Microsoft Edge への参照データと基本設定のコピーに同意することをユーザーに求めます。  

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
      *   ホームページ  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/neededge-dialog1.msft.png" alt-text="閲覧通知とデータと基本設定のインポートを求めるメッセージ" lightbox="../media/neededge-dialog1.msft.png":::
         閲覧通知とデータと基本設定のインポートを求めるメッセージ  
      :::image-end:::  
   :::column-end:::
:::row-end:::

ユーザーが **[Internet Explorer からデータと基本設定を常に**表示する] チェックボックスをオンにしても同意しない場合、ユーザーは [**参照の続行**] を選んで   閲覧セッションを続行できます。  

最後に、web サイトの非互換性のバナーは、各リダイレクションのアドレスバーの下に表示されます。  Web サイトの互換性のないバナーの例は、次の図のように表示されます。

:::image type="complex" source="../media/neededge-banner.msft.png" alt-text="モダンサイトに関する通知と Microsoft edge を既定のブラウザーとして設定するか、Microsoft Edge を調査するように求めるメッセージ" lightbox="../media/neededge-banner.msft.png":::
   モダンサイトに関する通知と Microsoft edge を既定のブラウザーとして設定するか、Microsoft Edge を調査するように求めるメッセージ  
:::image-end:::

Web サイトの非互換性のバナーには、ユーザーに対して次の情報が表示されます。  

*   ユーザーによる Microsoft Edge への切り替えをお勧めします。  
*   Microsoft Edge を既定のブラウザーとして設定することを提供します。  
*   Microsoft Edge を調査するためのオプションをユーザーに提供します。    
    
Web サイトが Internet Explorer から Microsoft Edge にリダイレクトされると、次のいずれかの操作が行われます。

*   アクティブな IE タブに以前の内容が含まれていない場合は、閉じられます。  
*   アクティブな IE タブに以前の内容が含まれている場合は、microsoft [Edge に web サイトがリダイレクトされた理由を説明する microsoft サポートページ][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]に移動します。  

> [!NOTE]
> リダイレクト後、IE の互換性の一覧にない web サイトでは、ユーザーが引き続き IE を使用する可能性があります。  

## IE 互換性の一覧の更新を要求する  

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

[MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]: https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554 "接続しようとしていた web サイトは、Internet Explorer で動作しません |Microsoft Office サポート"  
