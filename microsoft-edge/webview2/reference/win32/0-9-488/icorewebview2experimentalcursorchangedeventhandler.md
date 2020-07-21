---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ExperimentalCursorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: ee6de606d6ed8a9e00dbdacee9bb07b341a6d04e
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886487"
---
# <span data-ttu-id="62840-104">0.9.515-インターフェイス ICoreWebView2ExperimentalCursorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="62840-104">0.9.515 - interface ICoreWebView2ExperimentalCursorChangedEventHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCursorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="62840-105">呼び出し元は、このインターフェイスを実装して、カーソル変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="62840-105">The caller implements this interface to receive CursorChanged events.</span></span>

## <span data-ttu-id="62840-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="62840-106">Summary</span></span>

 <span data-ttu-id="62840-107">Members</span><span class="sxs-lookup"><span data-stu-id="62840-107">Members</span></span>                        | <span data-ttu-id="62840-108">説明</span><span class="sxs-lookup"><span data-stu-id="62840-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="62840-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="62840-109">Invoke</span></span>](#invoke) | <span data-ttu-id="62840-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="62840-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="62840-111">新しいカーソルを取得するには、Cursor プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="62840-111">Use the Cursor property to get the new cursor.</span></span>

## <span data-ttu-id="62840-112">Members</span><span class="sxs-lookup"><span data-stu-id="62840-112">Members</span></span>

#### <span data-ttu-id="62840-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="62840-113">Invoke</span></span> 

<span data-ttu-id="62840-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="62840-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="62840-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="62840-115">public HRESULT [Invoke](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="62840-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="62840-116">There are no event args and the args parameter will be null.</span></span>

