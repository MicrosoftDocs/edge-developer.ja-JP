---
description: スレッド化
title: スレッド化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 61e3b7fc8d25e2a1ce9c60fb84f5f39ba43f281b
ms.sourcegitcommit: efdc6369c48942bfa39e45c713300ed70f0e3655
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "11013738"
---
# スレッド化 

WebView2 コントロールは、 [コンポーネントオブジェクトモデル (COM)](https://docs.microsoft.com/windows/win32/com/the-component-object-model) に基づいており、 [シングルスレッドアパートメント (STA)](https://docs.microsoft.com/windows/win32/com/single-threaded-apartments) スレッドで実行する必要があります。

## スレッド セーフティ  

WebView2 は、UI スレッドで作成する必要があります。  特にメッセージポンプを持つスレッド。  このスレッドですべてのコールバックが発生し、WebView2 への要求はそのスレッドで実行する必要があります。  別のスレッドから WebView2 を使うことは安全ではありません。  

このプロパティの唯一の例外は `Content` `CoreWebView2WebResourceRequest` です。  `Content`プロパティストリームは、バックグラウンドスレッドから読み取ります。  UI スレッドへのパフォーマンスへの影響を防ぐために、ストリームは、バックグラウンド STA から作成するか、または作成してください。  

## 再  

イベントハンドラーと完了ハンドラーを含むコールバックは逐次実行されます。  イベントハンドラーを実行していて、メッセージループを開始した場合、他のイベントハンドラーまたは完了コールバックは再入可能な方法で開始できません。  

## 保留  

一部の WebView2 イベントは、イベント引数で設定された値を読み取ります。または、イベントハンドラーの完了後に何らかの操作を実行します。  また、イベントハンドラーなどの非同期操作も実行する必要がある場合は、 `GetDeferral` 関連付けられているイベントのイベント引数でメソッドを使うことができます。  返された繰延オブジェクトは、のメソッドが要求されるまで、イベントハンドラーが完了したと見なされないようにし `Complete` `Deferral` ます。  

たとえば、イベントを使うと、 `NewWindowRequested` `CoreWebView2` イベントハンドラーが完了したときに、子ウィンドウとして接続することができます。  ただし、を非同期的に作成する必要がある場合は、 `CoreWebView2` `GetDeferral` のメソッドをに要求し `NewWindowRequestedEventArgs` ます。  非同期的にを作成 `CoreWebView2` してプロパティをに設定すると `NewWindow` 、その `NewWindowRequestedEventArgs` `Complete` `Deferral` メソッドを使ってオブジェクトの要求が返され `GetDeferral` ます。  

<!-- links -->  
