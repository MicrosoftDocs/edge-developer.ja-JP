---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ZoomFactorChangedEventHandler
ms.openlocfilehash: 74cd0451e111780078714b17e5bd1097c56d6b2e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877575"
---
# <span data-ttu-id="be51c-104">インターフェイス ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="be51c-104">interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="be51c-105">呼び出し元は、このインターフェイスを実装して ZoomFactorChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="be51c-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="be51c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="be51c-106">Summary</span></span>

 <span data-ttu-id="be51c-107">Members</span><span class="sxs-lookup"><span data-stu-id="be51c-107">Members</span></span>                        | <span data-ttu-id="be51c-108">説明</span><span class="sxs-lookup"><span data-stu-id="be51c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="be51c-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="be51c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="be51c-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="be51c-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="be51c-111">変更されたズームファクターを取得するには、ICoreWebView2Controller プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="be51c-111">Use the ICoreWebView2Controller.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="be51c-112">Members</span><span class="sxs-lookup"><span data-stu-id="be51c-112">Members</span></span>

#### <span data-ttu-id="be51c-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="be51c-113">Invoke</span></span> 

<span data-ttu-id="be51c-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="be51c-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="be51c-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="be51c-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="be51c-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="be51c-116">There are no event args and the args parameter will be null.</span></span>

