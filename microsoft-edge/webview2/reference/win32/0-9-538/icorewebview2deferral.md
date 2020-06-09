---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b5fcd04d702483778ef31549c2e7d989ebfe3689
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699007"
---
# <span data-ttu-id="b336e-104">インターフェイス ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="b336e-104">interface ICoreWebView2Deferral</span></span> 

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="b336e-105">このインターフェイスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="b336e-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="b336e-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b336e-106">Summary</span></span>

 <span data-ttu-id="b336e-107">Members</span><span class="sxs-lookup"><span data-stu-id="b336e-107">Members</span></span>                        | <span data-ttu-id="b336e-108">説明</span><span class="sxs-lookup"><span data-stu-id="b336e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b336e-109">Complete</span><span class="sxs-lookup"><span data-stu-id="b336e-109">Complete</span></span>](#complete) | <span data-ttu-id="b336e-110">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="b336e-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="b336e-111">Members</span><span class="sxs-lookup"><span data-stu-id="b336e-111">Members</span></span>

#### <span data-ttu-id="b336e-112">Complete</span><span class="sxs-lookup"><span data-stu-id="b336e-112">Complete</span></span> 

<span data-ttu-id="b336e-113">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="b336e-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="b336e-114">パブリック HRESULT[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="b336e-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="b336e-115">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b336e-115">Complete should only be called once for each deferral taken.</span></span>

