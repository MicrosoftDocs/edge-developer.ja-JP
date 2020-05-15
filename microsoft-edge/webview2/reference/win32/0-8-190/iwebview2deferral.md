---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: d43cbe741cc9cd8b027a21115133db9377a95658
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654352"
---
# <span data-ttu-id="353ab-104">インターフェイス IWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="353ab-104">interface IWebView2Deferral</span></span> 

> [!NOTE]
> <span data-ttu-id="353ab-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="353ab-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="353ab-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="353ab-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="353ab-107">このインターフェイスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="353ab-107">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="353ab-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="353ab-108">Summary</span></span>

 <span data-ttu-id="353ab-109">Members</span><span class="sxs-lookup"><span data-stu-id="353ab-109">Members</span></span>                        | <span data-ttu-id="353ab-110">説明</span><span class="sxs-lookup"><span data-stu-id="353ab-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="353ab-111">Complete</span><span class="sxs-lookup"><span data-stu-id="353ab-111">Complete</span></span>](#complete) | <span data-ttu-id="353ab-112">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="353ab-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="353ab-113">Members</span><span class="sxs-lookup"><span data-stu-id="353ab-113">Members</span></span>

#### <span data-ttu-id="353ab-114">Complete</span><span class="sxs-lookup"><span data-stu-id="353ab-114">Complete</span></span> 

<span data-ttu-id="353ab-115">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="353ab-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="353ab-116">パブリック HRESULT[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="353ab-116">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="353ab-117">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="353ab-117">Complete should only be called once for each deferral taken.</span></span>

