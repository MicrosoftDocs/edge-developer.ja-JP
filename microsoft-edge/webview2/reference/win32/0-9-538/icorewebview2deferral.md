---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2Deferral
ms.openlocfilehash: 533aefe8b14ae3cabfddd32cb588014067bfdd42
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010286"
---
# <span data-ttu-id="79fa3-104">0.9.579-インターフェイス ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="79fa3-104">0.9.579 - interface ICoreWebView2Deferral</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="79fa3-105">このインターフェイスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="79fa3-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="79fa3-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="79fa3-106">Summary</span></span>

 <span data-ttu-id="79fa3-107">Members</span><span class="sxs-lookup"><span data-stu-id="79fa3-107">Members</span></span>                        | <span data-ttu-id="79fa3-108">説明</span><span class="sxs-lookup"><span data-stu-id="79fa3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="79fa3-109">Complete</span><span class="sxs-lookup"><span data-stu-id="79fa3-109">Complete</span></span>](#complete) | <span data-ttu-id="79fa3-110">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="79fa3-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="79fa3-111">Members</span><span class="sxs-lookup"><span data-stu-id="79fa3-111">Members</span></span>

#### <span data-ttu-id="79fa3-112">Complete</span><span class="sxs-lookup"><span data-stu-id="79fa3-112">Complete</span></span> 

<span data-ttu-id="79fa3-113">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="79fa3-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="79fa3-114">パブリック HRESULT [完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="79fa3-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="79fa3-115">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="79fa3-115">Complete should only be called once for each deferral taken.</span></span>

