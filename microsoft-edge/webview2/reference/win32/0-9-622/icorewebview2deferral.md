---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2Deferral
ms.openlocfilehash: d8abff93df317a42c1bfe89dd32ac1d5f7e8c329
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012376"
---
# <span data-ttu-id="a81ba-104">インターフェイス ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="a81ba-104">interface ICoreWebView2Deferral</span></span> 

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="a81ba-105">このインターフェイスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="a81ba-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="a81ba-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a81ba-106">Summary</span></span>

 <span data-ttu-id="a81ba-107">Members</span><span class="sxs-lookup"><span data-stu-id="a81ba-107">Members</span></span>                        | <span data-ttu-id="a81ba-108">説明</span><span class="sxs-lookup"><span data-stu-id="a81ba-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a81ba-109">Complete</span><span class="sxs-lookup"><span data-stu-id="a81ba-109">Complete</span></span>](#complete) | <span data-ttu-id="a81ba-110">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="a81ba-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="a81ba-111">Members</span><span class="sxs-lookup"><span data-stu-id="a81ba-111">Members</span></span>

#### <span data-ttu-id="a81ba-112">Complete</span><span class="sxs-lookup"><span data-stu-id="a81ba-112">Complete</span></span> 

<span data-ttu-id="a81ba-113">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="a81ba-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="a81ba-114">パブリック HRESULT [完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="a81ba-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="a81ba-115">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a81ba-115">Complete should only be called once for each deferral taken.</span></span>

