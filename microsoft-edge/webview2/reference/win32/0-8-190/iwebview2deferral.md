---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: f40d0baa415ccc76747993c4070bb05eaf76fe56
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878611"
---
# <span data-ttu-id="dfcac-104">0.8.355-インターフェイス IWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="dfcac-104">0.8.355 - interface IWebView2Deferral</span></span> 

> [!NOTE]
> <span data-ttu-id="dfcac-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfcac-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="dfcac-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfcac-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="dfcac-107">このインターフェイスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="dfcac-107">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="dfcac-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="dfcac-108">Summary</span></span>

 <span data-ttu-id="dfcac-109">Members</span><span class="sxs-lookup"><span data-stu-id="dfcac-109">Members</span></span>                        | <span data-ttu-id="dfcac-110">説明</span><span class="sxs-lookup"><span data-stu-id="dfcac-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dfcac-111">Complete</span><span class="sxs-lookup"><span data-stu-id="dfcac-111">Complete</span></span>](#complete) | <span data-ttu-id="dfcac-112">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="dfcac-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="dfcac-113">Members</span><span class="sxs-lookup"><span data-stu-id="dfcac-113">Members</span></span>

#### <span data-ttu-id="dfcac-114">Complete</span><span class="sxs-lookup"><span data-stu-id="dfcac-114">Complete</span></span> 

<span data-ttu-id="dfcac-115">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="dfcac-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="dfcac-116">パブリック HRESULT[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="dfcac-116">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="dfcac-117">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dfcac-117">Complete should only be called once for each deferral taken.</span></span>

