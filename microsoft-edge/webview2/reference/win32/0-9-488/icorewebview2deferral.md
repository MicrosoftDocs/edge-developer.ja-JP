---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b30b6e35388ab01433b2c879db82d9c4136fae99
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885425"
---
# <span data-ttu-id="d54da-104">0.9.515-インターフェイス ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="d54da-104">0.9.515 - interface ICoreWebView2Deferral</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="d54da-105">このインターフェイスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="d54da-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="d54da-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d54da-106">Summary</span></span>

 <span data-ttu-id="d54da-107">Members</span><span class="sxs-lookup"><span data-stu-id="d54da-107">Members</span></span>                        | <span data-ttu-id="d54da-108">説明</span><span class="sxs-lookup"><span data-stu-id="d54da-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d54da-109">Complete</span><span class="sxs-lookup"><span data-stu-id="d54da-109">Complete</span></span>](#complete) | <span data-ttu-id="d54da-110">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="d54da-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="d54da-111">Members</span><span class="sxs-lookup"><span data-stu-id="d54da-111">Members</span></span>

#### <span data-ttu-id="d54da-112">Complete</span><span class="sxs-lookup"><span data-stu-id="d54da-112">Complete</span></span> 

<span data-ttu-id="d54da-113">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="d54da-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="d54da-114">パブリック HRESULT[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="d54da-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="d54da-115">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d54da-115">Complete should only be called once for each deferral taken.</span></span>

