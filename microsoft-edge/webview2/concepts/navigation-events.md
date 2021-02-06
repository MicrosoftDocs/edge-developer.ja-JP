---
description: ナビゲーション
title: ナビゲーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/05/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: ac15b9f32a29c64bbdc2a7886fa654a2d71a5453
ms.sourcegitcommit: 4cea8cf99b5f12db9d2daba99bbf48f3ccc537fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314798"
---
# ナビゲーションイベント  

ナビゲーション イベントの通常のシーケンスは `NavigationStarting` 、 , , , , , and then `SourceChanged` `ContentLoading` `HistoryChanged` です `NavigationCompleted` 。  次のイベントは、各ナビゲーション中の WebView2 の状態を示しています。  

| Sequence | [Event Name] | 詳細 |  
|:--- |:--- |:--- |  
| 1 | `NavigationStarting`  |  WebView2 は移動を開始し、ナビゲーションの結果はネットワーク要求になります。  ホストは、イベント中に要求を禁止できます。  |  
| 2 | `SourceChanged`  |  WebView2 のソースが新しい URL に変更されます。  このイベントは、フラグメント ナビゲーションなどのネットワーク要求を引き起こしていないナビゲーションによって発生する可能性があります。  |  
| 3 | `HistoryChanged`  |  ナビゲーションの結果として WebView2 の履歴が更新されます。  |  
| 4 | `ContentLoading`  |  WebView2 は、新しいページのコンテンツの読み込みを開始します。  |  
| 5 | `NavigationCompleted`  |  WebView2 は、新しいページでのコンテンツの読み込みを完了します。  |  

ナビゲーション ID \( \) を使用して、新しい `navigations` 各ドキュメントに `NavigationId` 追跡します。  新 `NavigationId` しいドキュメントへのナビゲーションが正常に行うたび、WebView の変更点が変わります。

:::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 ナビゲーション イベント" lightbox="../media/navigation-graph.png":::
   Microsoft Edge WebView2 ナビゲーション イベント  
:::image-end:::  

> [!NOTE]
> 前の図は、それぞれのイベント引数で同じ `NavigationId` プロパティを持つナビゲーション イベントを表しています。  

 `Navigations` イベントのインスタンスが異なると、 `NavigationId` イベントが重複する可能性があります。  たとえば、ナビゲーションを開始するときに、関連するイベントを待つ必要 `NavigationStarting` があります。  その後、別のナビゲーションを開始すると、最初のナビゲーションのイベントが表示され、次に 2 番目のナビゲーションのイベントが表示され、次に最初のナビゲーションのイベントが表示され、次に 2 番目のナビゲーションに適したナビゲーション イベントの残りのすべてが表示されます。 `NavigationStarting` `NavigationStarting` `NavigationCompleted`  
 
 エラーの場合、ナビゲーションがエラー ページに続くかどうかによって、イベントが発生する場合とない `ContentLoading` 場合があります。  
 
 HTTP リダイレクトの場合、1 行に複数のイベントがあります。後続のイベント引数にはプロパティが設定されます。ただし、イベントは `NavigationStarting` `IsRedirect` `NavigationId` 同じままです。  
 
 フラグメントへの移動など、同じドキュメントではイベントが発生し、インクリメント `navigations` `NavigationStarting` は行わりません `NavigationId` 。  

WebView のサブフレーム内で監視またはキャンセルするには、対応する同等の非フレーム イベントと同様に機能するイベント `navigations` `FrameNavigationStarting` `FrameNavigationCompleted` とイベントを使用します。  

<!-- links -->  
