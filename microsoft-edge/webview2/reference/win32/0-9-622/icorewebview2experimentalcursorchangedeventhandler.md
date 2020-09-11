---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalCursorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalCursorChangedEventHandler
ms.openlocfilehash: 246fc6d23a003a346a20055fbf083421a6fb1b26
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012277"
---
# <span data-ttu-id="35d9f-104">インターフェイス ICoreWebView2ExperimentalCursorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="35d9f-104">interface ICoreWebView2ExperimentalCursorChangedEventHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCursorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="35d9f-105">呼び出し元は、このインターフェイスを実装して、カーソル変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="35d9f-105">The caller implements this interface to receive CursorChanged events.</span></span>

## <span data-ttu-id="35d9f-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="35d9f-106">Summary</span></span>

 <span data-ttu-id="35d9f-107">Members</span><span class="sxs-lookup"><span data-stu-id="35d9f-107">Members</span></span>                        | <span data-ttu-id="35d9f-108">説明</span><span class="sxs-lookup"><span data-stu-id="35d9f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="35d9f-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="35d9f-109">Invoke</span></span>](#invoke) | <span data-ttu-id="35d9f-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="35d9f-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="35d9f-111">新しいカーソルを取得するには、Cursor プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="35d9f-111">Use the Cursor property to get the new cursor.</span></span>

## <span data-ttu-id="35d9f-112">Members</span><span class="sxs-lookup"><span data-stu-id="35d9f-112">Members</span></span>

#### <span data-ttu-id="35d9f-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="35d9f-113">Invoke</span></span> 

<span data-ttu-id="35d9f-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="35d9f-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="35d9f-115">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="35d9f-115">public HRESULT [Invoke](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="35d9f-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="35d9f-116">There are no event args and the args parameter will be null.</span></span>

