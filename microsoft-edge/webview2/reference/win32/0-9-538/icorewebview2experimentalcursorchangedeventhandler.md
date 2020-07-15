---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalCursorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalCursorChangedEventHandler
ms.openlocfilehash: f58279d1a3c404715be5aad8bf1be5ef120e1d94
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880004"
---
# <span data-ttu-id="33b3a-104">インターフェイス ICoreWebView2ExperimentalCursorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="33b3a-104">interface ICoreWebView2ExperimentalCursorChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="33b3a-105">これは、プレリリース SDK バージョン0.9.538 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="33b3a-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalCursorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="33b3a-106">呼び出し元は、このインターフェイスを実装して、カーソル変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="33b3a-106">The caller implements this interface to receive CursorChanged events.</span></span>

## <span data-ttu-id="33b3a-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="33b3a-107">Summary</span></span>

 <span data-ttu-id="33b3a-108">Members</span><span class="sxs-lookup"><span data-stu-id="33b3a-108">Members</span></span>                        | <span data-ttu-id="33b3a-109">説明</span><span class="sxs-lookup"><span data-stu-id="33b3a-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="33b3a-110">Invoke</span><span class="sxs-lookup"><span data-stu-id="33b3a-110">Invoke</span></span>](#invoke) | <span data-ttu-id="33b3a-111">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="33b3a-111">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="33b3a-112">新しいカーソルを取得するには、Cursor プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="33b3a-112">Use the Cursor property to get the new cursor.</span></span>

## <span data-ttu-id="33b3a-113">Members</span><span class="sxs-lookup"><span data-stu-id="33b3a-113">Members</span></span>

#### <span data-ttu-id="33b3a-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="33b3a-114">Invoke</span></span> 

<span data-ttu-id="33b3a-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="33b3a-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="33b3a-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="33b3a-116">public HRESULT [Invoke](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="33b3a-117">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="33b3a-117">There are no event args and the args parameter will be null.</span></span>

