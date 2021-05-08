---
description: ナビゲーション
title: ナビゲーション |WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: d133bfb99808d0e036c4b46be9ef82039aee49eb
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535707"
---
# <a name="navigation-events"></a>ナビゲーションイベント  

:::row:::
   :::column span="1":::
      サポートされているプラットフォーム:
   :::column-end:::
   :::column span="2":::
      Win32, Windows Forms, WinUi, WPF
   :::column-end:::
:::row-end:::  

ナビゲーション イベントは、WebView2 インスタンスに表示されるコンテンツに対して特定の非同期アクションが発生すると実行されます。  たとえば、WebView2 ユーザーが新しい Web サイトに移動すると、ネイティブ コンテンツはイベントを使用して変更をリッスン `NavigationStarting` します。  ナビゲーション アクションが完了すると、実行 `NavigationCompleted` されます。  ナビゲーション イベントの良い例については [、「WebView2 Get Started guide」に移動します][Webview2IndexGetStarted]。  

<!--todo:  Move the relevant information out of the get started guide to better focus the content and leave the most concise elements in the get started guide.  -->   

ナビゲーション イベントの通常のシーケンス `NavigationStarting` は `SourceChanged` 、、、、、、 `ContentLoading` `HistoryChanged` です `NavigationCompleted` 。  次のイベントは、各ナビゲーション中の WebView2 の状態について説明します。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 ナビゲーション イベント" lightbox="../media/navigation-graph.png":::
         Microsoft Edge WebView2 ナビゲーション イベント  
      :::image-end:::  
      
      > [!NOTE]
      > 図は、それぞれのイベント引数に同じ `NavigationId` プロパティを持つナビゲーション イベントを表します。  
   :::column-end:::
   :::column span="2":::
      | シーケンス | [Event Name] | 詳細 |  
      |:--- |:--- |:--- |  
      | 1 | `NavigationStarting`  |  WebView2 は移動を開始し、ナビゲーションはネットワーク要求になります。  ホストは、イベント中に要求を禁止する場合があります。  |  
      | 2 | `SourceChanged`  |  WebView2 のソースが新しい URL に変更されます。  このイベントは、フラグメント ナビゲーションなどのネットワーク要求を引き起こしていないナビゲーション アクションによって発生する可能性があります。  |  
      | 3 | `ContentLoading`  |  WebView は、新しいページのコンテンツの読み込みを開始します。  |  
      | 4 | `HistoryChanged`  |  ナビゲーションによって、WebView2 の履歴が更新されます。  |  
      | 5 | `NavigationCompleted`  |  WebView2 は、新しいページでのコンテンツの読み込みを完了します。  |  
   :::column-end:::
:::row-end:::

ナビゲーション ID \( event\) を使用して、新しい各ドキュメントへのナビゲーション `NavigationId` イベントを追跡します。  WebView `NavigationId` のイベントは、新しいドキュメントへの正常なナビゲーションが完了する度に変更されます。  

 イベントのインスタンスが異なるナビゲーション `NavigationId` イベントが重複する場合があります。  たとえば、ナビゲーション イベントを開始する場合は、関連するイベントを待つ必要 `NavigationStarting` があります。  その後、別のナビゲーションを開始すると、最初のナビゲーションのイベントが表示され、その後に 2 番目のナビゲーションのイベントが表示され、次に最初のナビゲーションのイベントが続き、2 番目のナビゲーションに適したナビゲーション イベントの残りの部分が表示されます。 `NavigationStarting` `NavigationStarting` `NavigationCompleted`  
 
 エラーの場合、ナビゲーションがエラー ページに続いているかどうかによって、イベントが発生する場合とできない `ContentLoading` 場合があります。  
 
 HTTP リダイレクトが発生した場合、1 行に複数のイベントが発生し、後でイベントの引数にプロパティが設定されているが、イベント `NavigationStarting` `IsRedirect` は同 `NavigationId` じままです。  
 
 フラグメントへの移動など、同じドキュメント ナビゲーション イベントはイベントを発生しないし、イベント `NavigationStarting` をインクリメント `NavigationId` しない。  

WebView2 インスタンス内のサブフレーム内のナビゲーション イベントを監視またはキャンセルするには、同等のフレーム以外の対応するイベントと同様に機能するイベント `FrameNavigationStarting` `FrameNavigationCompleted` を使用します。  

## <a name="see-also"></a>関連項目  

*   WebView2 の使用を開始するには [、「WebView2 Get Started Guides guides」に][Webview2IndexGetStarted] 移動します。  
*   WebView2 機能の包括的な例については、GitHub の [WebView2Samples リポジトリ][GithubMicrosoftedgeWebview2samples] に移動します。  
*   WebView2 API の詳細については、「API リファレンス」 [に移動します][DotnetApiMicrosoftWebWebview2WpfWebview2]。  
*   WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGetStarted]: ../index.md#get-started "はじめに - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス | Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
