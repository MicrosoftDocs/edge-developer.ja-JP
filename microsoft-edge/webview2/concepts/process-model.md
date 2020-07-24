---
description: プロセスモデル
title: プロセスモデル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 8548308896815266fbd1e150da979b56cfb268e2
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895564"
---
# プロセスモデル  

WebView2 は、Microsoft Edge ブラウザーと同じプロセスモデルを使用します。  ブラウザープロセスモデルの詳細については、「[最新の web ブラウザーを使用したブラウザーのアーキテクチャ][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]」を参照してください。 

1つのブラウザープロセスは、この記事で説明されているレンダラープロセスおよびその他のユーティリティプロセスと関連付けられています。  さらに、WebView2 の場合、WebView2 を使ってプロセスを要求するホストアプリもあります。  

:::image type="complex" source="../media/process-model-1.png" alt-text="プロセス1" lightbox="../media/process-model-1.png":::
   プロセス1  
:::image-end:::  

ユーザーデータフォルダーを指定する WebView2 要求処理を行うユーザーセッションのユーザーデータフォルダーごとに、1つのブラウザープロセスを指定します。  つまり、1つのブラウザープロセスが複数の要求プロセスを処理している可能性があり、1つのプロセスが複数のブラウザープロセスを使用している可能性があります。  

:::image type="complex" source="../media/process-model-2.png" alt-text="プロセス2" lightbox="../media/process-model-2.png":::
   プロセス2  
:::image-end:::  

ブラウザープロセスには、いくつかの関連するレンダラープロセスがあります。  WebView2 のさまざまなインスタンスで複数のフレームを処理するために、必要に応じてブラウザープロセスが作成されます。  レンダラープロセスの数は、サイト分離ブラウザー機能と、関連付けられている WebView2 のインスタンスでレンダリングされた個別の切断元の数によって異なります。  サイト分離ブラウザー機能については、前の内容を参照してください。  

は、 `CoreWebView2Environment` ユーザーデータフォルダーとブラウザープロセスを表します。  このは、 `CoreWebView2` 前に説明したように、サイトの分離に応じて、WebView2 によって、さまざまなレンダラープロセスが使用されるため、いずれかのプロセスのセットに直接対応することはできません。  

これらのブラウザーでのクラッシュとハングに対応し、のイベントを使用してレンダラープロセスを処理することができ `ProcessFailed` `CoreWebView2` ます。  

のメソッドを使用して、関連するブラウザーとレンダラープロセスを安全にシャットダウンすることができ `Close` `CoreWebView2Controller` ます。  

WebView2 インスタンスの [ **devtools** ] ウィンドウからブラウザータスクマネージャーウィンドウを開くには、 `Shift` + `Escape` devtools ウィンドウのタイトルバーを選択するか、または hover でポイントし、コンテキストメニュー \ (右クリック \) を開いて、を選択し `Browser task manager` ます。  WebView2 のブラウザープロセスに関連付けられたすべてのプロセスが、関連付けられた目的を含めて表示されます。  

<!-- links -->  

[GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]: https://developers.google.com/web/updates/2018/09/inside-browser-part1#browser-architecture "ブラウザーのアーキテクチャ-最新の web ブラウザーを表示する (パート 1)"  
