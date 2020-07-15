---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ExperimentalCursorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 6fbcc82409791bc3d2da3bb2f7985732cb344a97
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880627"
---
# <span data-ttu-id="c0a00-104">0.9.515-インターフェイス ICoreWebView2ExperimentalCursorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c0a00-104">0.9.515 - interface ICoreWebView2ExperimentalCursorChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="c0a00-105">これは、プレリリース SDK バージョン0.9.488 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="c0a00-105">This an experimental API that is shipped with our prerelease SDK version 0.9.488.</span></span>

```
interface ICoreWebView2ExperimentalCursorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="c0a00-106">呼び出し元は、このインターフェイスを実装して、カーソル変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c0a00-106">The caller implements this interface to receive CursorChanged events.</span></span>

## <span data-ttu-id="c0a00-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="c0a00-107">Summary</span></span>

 <span data-ttu-id="c0a00-108">Members</span><span class="sxs-lookup"><span data-stu-id="c0a00-108">Members</span></span>                        | <span data-ttu-id="c0a00-109">説明</span><span class="sxs-lookup"><span data-stu-id="c0a00-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c0a00-110">Invoke</span><span class="sxs-lookup"><span data-stu-id="c0a00-110">Invoke</span></span>](#invoke) | <span data-ttu-id="c0a00-111">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c0a00-111">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="c0a00-112">新しいカーソルを取得するには、Cursor プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="c0a00-112">Use the Cursor property to get the new cursor.</span></span>

## <span data-ttu-id="c0a00-113">Members</span><span class="sxs-lookup"><span data-stu-id="c0a00-113">Members</span></span>

#### <span data-ttu-id="c0a00-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="c0a00-114">Invoke</span></span> 

<span data-ttu-id="c0a00-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c0a00-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c0a00-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="c0a00-116">public HRESULT [Invoke](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="c0a00-117">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="c0a00-117">There are no event args and the args parameter will be null.</span></span>

