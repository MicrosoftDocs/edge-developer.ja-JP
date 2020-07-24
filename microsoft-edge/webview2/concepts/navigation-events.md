---
description: ナビゲーション
title: ナビゲーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 0df8e12acb11824006515ac711250d776d276e36
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895579"
---
# ナビゲーションイベント  

通常のナビゲーションイベントのシーケンスは、、、、、ということです `NavigationStarting` `SourceChanged` `ContentLoading` `HistoryChanged` `NavigationCompleted` 。  次のイベントは、各ナビゲーションでの WebView2 の状態を示しています。  

| 動作 | [Event Name] | 詳細 |  
|:--- |:--- |:--- |  
| 件 | `NavigationStarting`  |  WebView2 が移動を開始し、ナビゲーションの結果がネットワーク要求になります。  ホストは、イベント中に要求を許可することはできません。  |  
| 両面 | `SourceChanged`  |  WebView2 のソースが新しい URL に変更されます。  このイベントは、フラグメントナビゲーションなどのネットワーク要求が発生しないナビゲーションによって発生する可能性があります。  |  
| - | `HistoryChanged`  |  ナビゲーションの結果としての WebView2 の更新履歴。  |  
| 4d | `ContentLoading`  |  WebView で、新しいページのコンテンツの読み込みが開始されます。  |  
| 個 | `NavigationCompleted`  |  WebView2 は、新しいページのコンテンツの読み込みを完了します。  |  

`navigations`ナビゲーション ID \ (\) を使用して、新しいドキュメントごとに追跡 `NavigationId` します。  `NavigationId`新しい文書へのナビゲーションが正常に完了するたびに、WebView の内容が変更されます。

:::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 ナビゲーションイベント" lightbox="../media/navigation-graph.png":::
   Microsoft Edge WebView2 ナビゲーションイベント  
:::image-end:::  

> [!NOTE]
> 上の図は、それぞれのイベント arg で同じプロパティを持つナビゲーションイベントを示して `NavigationId` います。  

 `Navigations` イベントのインスタンスが異なるイベント `NavigationId` は、重複する可能性があります。  たとえば、ナビゲーションを開始する場合は、関連するイベントを待つ必要があり `NavigationStarting` ます。  別のナビゲーションを開始した場合は、最初のナビゲートのイベントと2番目の移動のイベントが表示され、最初のナビゲーションにイベントが `NavigationStarting` `NavigationStarting` 続き、2番目のナビゲーションで該当する `NavigationCompleted` ナビゲーションイベントの残りすべてが表示されます。  
 
 エラーが発生した場合は、 `ContentLoading` ナビゲーションがエラーページに続いているかどうかによって、イベントが発生する可能性があります。  
 
 HTTP リダイレクトの場合、1つの行に複数のイベントがあります。その場合は、次のイベント引数にプロパティが設定されていますが、値は `NavigationStarting` `IsRedirect` `NavigationId` 変わりません。  
 
 同じドキュメント (フラグメントへの移動など) では、 `navigations` イベントは発生せず、 `NavigationStarting` をインクリメントしません `NavigationId` 。  

WebView でサブフレームの内部を監視またはキャンセルするには、と等価の、フレームに対応して `navigations` `FrameNavigationStarting` いないイベントと同じように動作するイベントを使用し `FrameNavigationCompleted` ます。  

<!-- links -->  
