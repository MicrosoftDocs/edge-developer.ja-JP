---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceRequestedEventArgs。
ms.openlocfilehash: 501483894a2abca58c5a1856ab587b93be904c8b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012238"
---
# WebView2 クラス (CoreWebView2WebResourceRequestedEventArgs クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

WebResourceRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[要求](#request) | Web リソース要求。
[ResourceContext](#resourcecontext) | Web リソース要求のコンテキスト。
[応答](#response) | Web リソース応答オブジェクトのプレースホルダー。
[GetDeferral](#getdeferral) | CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

## Members

#### 要求 

Web リソース要求。

> パブリック [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [要求](#request)

要求オブジェクトに、後でネットワークスタックによって追加された一部のヘッダーが欠落している可能性があります。

#### ResourceContext 

Web リソース要求のコンテキスト。

> パブリック [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [resourcecontext](#resourcecontext)

#### 応答 

Web リソース応答オブジェクトのプレースホルダー。

> パブリック [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [応答](#response)

このオブジェクトが設定されている場合、web リソース要求はこの応答で完了します。 空の Web リソース応答オブジェクトは、CreateWebResourceResponse を使って作成してから、その応答を構築するために変更することができます。

#### GetDeferral 

CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

> パブリック [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [getdeferral](#getdeferral)()

CoreWebView2Deferral オブジェクトを使って、後で要求を完了することができます。

