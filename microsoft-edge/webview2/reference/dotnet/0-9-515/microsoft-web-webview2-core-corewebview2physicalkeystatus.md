---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2PhysicalKeyStatus の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: da7069fb4dad164720bb697a250a216a0bd452ad
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881201"
---
# <span data-ttu-id="a1838-104">WebView2 構造体 0.9.515-CoreWebView2PhysicalKeyStatus 構造体</span><span class="sxs-lookup"><span data-stu-id="a1838-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2PhysicalKeyStatus struct</span></span> 

> [!NOTE]
> <span data-ttu-id="a1838-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1838-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="a1838-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1838-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="a1838-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="a1838-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a1838-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a1838-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a1838-109">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="a1838-109">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

## <span data-ttu-id="a1838-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="a1838-110">Summary</span></span>

 <span data-ttu-id="a1838-111">Members</span><span class="sxs-lookup"><span data-stu-id="a1838-111">Members</span></span>                        | <span data-ttu-id="a1838-112">説明</span><span class="sxs-lookup"><span data-stu-id="a1838-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a1838-113">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="a1838-113">IsExtendedKey</span></span>](#isextendedkey) | <span data-ttu-id="a1838-114">キーが拡張キーかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a1838-114">Indicates whether the key is an extended key.</span></span>
[<span data-ttu-id="a1838-115">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="a1838-115">IsKeyReleased</span></span>](#iskeyreleased) | <span data-ttu-id="a1838-116">切り替えの状態。</span><span class="sxs-lookup"><span data-stu-id="a1838-116">The transition state.</span></span>
[<span data-ttu-id="a1838-117">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="a1838-117">IsMenuKeyDown</span></span>](#ismenukeydown) | <span data-ttu-id="a1838-118">コンテキストコード。</span><span class="sxs-lookup"><span data-stu-id="a1838-118">The context code.</span></span>
[<span data-ttu-id="a1838-119">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="a1838-119">RepeatCount</span></span>](#repeatcount) | <span data-ttu-id="a1838-120">現在のメッセージの繰り返し回数。</span><span class="sxs-lookup"><span data-stu-id="a1838-120">The repeat count for the current message.</span></span>
[<span data-ttu-id="a1838-121">ScanCode</span><span class="sxs-lookup"><span data-stu-id="a1838-121">ScanCode</span></span>](#scancode) | <span data-ttu-id="a1838-122">スキャンコード。</span><span class="sxs-lookup"><span data-stu-id="a1838-122">The scan code.</span></span>
[<span data-ttu-id="a1838-123">通常の方法</span><span class="sxs-lookup"><span data-stu-id="a1838-123">WasKeyDown</span></span>](#waskeydown) | <span data-ttu-id="a1838-124">前のキーの状態。</span><span class="sxs-lookup"><span data-stu-id="a1838-124">The previous key state.</span></span>

<span data-ttu-id="a1838-125">詳細については、WM_KEYDOWN のドキュメントを参照してください [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown) 。</span><span class="sxs-lookup"><span data-stu-id="a1838-125">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown).</span></span>

## <span data-ttu-id="a1838-126">Members</span><span class="sxs-lookup"><span data-stu-id="a1838-126">Members</span></span>

#### <span data-ttu-id="a1838-127">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="a1838-127">IsExtendedKey</span></span> 

<span data-ttu-id="a1838-128">キーが拡張キーかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a1838-128">Indicates whether the key is an extended key.</span></span>

> <span data-ttu-id="a1838-129">パブリック int [IsExtendedKey](#isextendedkey)</span><span class="sxs-lookup"><span data-stu-id="a1838-129">public int [IsExtendedKey](#isextendedkey)</span></span>

#### <span data-ttu-id="a1838-130">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="a1838-130">IsKeyReleased</span></span> 

<span data-ttu-id="a1838-131">切り替えの状態。</span><span class="sxs-lookup"><span data-stu-id="a1838-131">The transition state.</span></span>

> <span data-ttu-id="a1838-132">公開 int [Iskeyreleased](#iskeyreleased)</span><span class="sxs-lookup"><span data-stu-id="a1838-132">public int [IsKeyReleased](#iskeyreleased)</span></span>

#### <span data-ttu-id="a1838-133">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="a1838-133">IsMenuKeyDown</span></span> 

<span data-ttu-id="a1838-134">コンテキストコード。</span><span class="sxs-lookup"><span data-stu-id="a1838-134">The context code.</span></span>

> <span data-ttu-id="a1838-135">パブリック int [Ismenukeydown](#ismenukeydown)</span><span class="sxs-lookup"><span data-stu-id="a1838-135">public int [IsMenuKeyDown](#ismenukeydown)</span></span>

#### <span data-ttu-id="a1838-136">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="a1838-136">RepeatCount</span></span> 

<span data-ttu-id="a1838-137">現在のメッセージの繰り返し回数。</span><span class="sxs-lookup"><span data-stu-id="a1838-137">The repeat count for the current message.</span></span>

> <span data-ttu-id="a1838-138">パブリック uint [Repeatcount](#repeatcount)</span><span class="sxs-lookup"><span data-stu-id="a1838-138">public uint [RepeatCount](#repeatcount)</span></span>

#### <span data-ttu-id="a1838-139">ScanCode</span><span class="sxs-lookup"><span data-stu-id="a1838-139">ScanCode</span></span> 

<span data-ttu-id="a1838-140">スキャンコード。</span><span class="sxs-lookup"><span data-stu-id="a1838-140">The scan code.</span></span>

> <span data-ttu-id="a1838-141">パブリック uint[スキャンコード](#scancode)</span><span class="sxs-lookup"><span data-stu-id="a1838-141">public uint [ScanCode](#scancode)</span></span>

#### <span data-ttu-id="a1838-142">通常の方法</span><span class="sxs-lookup"><span data-stu-id="a1838-142">WasKeyDown</span></span> 

<span data-ttu-id="a1838-143">前のキーの状態。</span><span class="sxs-lookup"><span data-stu-id="a1838-143">The previous key state.</span></span>

> <span data-ttu-id="a1838-144">公開 int [WasKeyDown](#waskeydown)</span><span class="sxs-lookup"><span data-stu-id="a1838-144">public int [WasKeyDown](#waskeydown)</span></span>

