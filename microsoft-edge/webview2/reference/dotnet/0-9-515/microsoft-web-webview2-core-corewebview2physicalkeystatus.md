---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2PhysicalKeyStatus の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: eecf4dd59d12c30667defd4e078e8624718bde26
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884590"
---
# <span data-ttu-id="d8e45-104">WebView2 構造体 0.9.515-CoreWebView2PhysicalKeyStatus 構造体</span><span class="sxs-lookup"><span data-stu-id="d8e45-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2PhysicalKeyStatus struct</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="d8e45-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="d8e45-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d8e45-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="d8e45-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d8e45-107">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="d8e45-107">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

## <span data-ttu-id="d8e45-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d8e45-108">Summary</span></span>

 <span data-ttu-id="d8e45-109">Members</span><span class="sxs-lookup"><span data-stu-id="d8e45-109">Members</span></span>                        | <span data-ttu-id="d8e45-110">説明</span><span class="sxs-lookup"><span data-stu-id="d8e45-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d8e45-111">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="d8e45-111">IsExtendedKey</span></span>](#isextendedkey) | <span data-ttu-id="d8e45-112">キーが拡張キーかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d8e45-112">Indicates whether the key is an extended key.</span></span>
[<span data-ttu-id="d8e45-113">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="d8e45-113">IsKeyReleased</span></span>](#iskeyreleased) | <span data-ttu-id="d8e45-114">切り替えの状態。</span><span class="sxs-lookup"><span data-stu-id="d8e45-114">The transition state.</span></span>
[<span data-ttu-id="d8e45-115">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="d8e45-115">IsMenuKeyDown</span></span>](#ismenukeydown) | <span data-ttu-id="d8e45-116">コンテキストコード。</span><span class="sxs-lookup"><span data-stu-id="d8e45-116">The context code.</span></span>
[<span data-ttu-id="d8e45-117">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="d8e45-117">RepeatCount</span></span>](#repeatcount) | <span data-ttu-id="d8e45-118">現在のメッセージの繰り返し回数。</span><span class="sxs-lookup"><span data-stu-id="d8e45-118">The repeat count for the current message.</span></span>
[<span data-ttu-id="d8e45-119">ScanCode</span><span class="sxs-lookup"><span data-stu-id="d8e45-119">ScanCode</span></span>](#scancode) | <span data-ttu-id="d8e45-120">スキャンコード。</span><span class="sxs-lookup"><span data-stu-id="d8e45-120">The scan code.</span></span>
[<span data-ttu-id="d8e45-121">通常の方法</span><span class="sxs-lookup"><span data-stu-id="d8e45-121">WasKeyDown</span></span>](#waskeydown) | <span data-ttu-id="d8e45-122">前のキーの状態。</span><span class="sxs-lookup"><span data-stu-id="d8e45-122">The previous key state.</span></span>

<span data-ttu-id="d8e45-123">詳細については、WM_KEYDOWN のドキュメントを参照してください [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown) 。</span><span class="sxs-lookup"><span data-stu-id="d8e45-123">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown).</span></span>

## <span data-ttu-id="d8e45-124">Members</span><span class="sxs-lookup"><span data-stu-id="d8e45-124">Members</span></span>

#### <span data-ttu-id="d8e45-125">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="d8e45-125">IsExtendedKey</span></span> 

<span data-ttu-id="d8e45-126">キーが拡張キーかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d8e45-126">Indicates whether the key is an extended key.</span></span>

> <span data-ttu-id="d8e45-127">パブリック int [IsExtendedKey](#isextendedkey)</span><span class="sxs-lookup"><span data-stu-id="d8e45-127">public int [IsExtendedKey](#isextendedkey)</span></span>

#### <span data-ttu-id="d8e45-128">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="d8e45-128">IsKeyReleased</span></span> 

<span data-ttu-id="d8e45-129">切り替えの状態。</span><span class="sxs-lookup"><span data-stu-id="d8e45-129">The transition state.</span></span>

> <span data-ttu-id="d8e45-130">公開 int [Iskeyreleased](#iskeyreleased)</span><span class="sxs-lookup"><span data-stu-id="d8e45-130">public int [IsKeyReleased](#iskeyreleased)</span></span>

#### <span data-ttu-id="d8e45-131">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="d8e45-131">IsMenuKeyDown</span></span> 

<span data-ttu-id="d8e45-132">コンテキストコード。</span><span class="sxs-lookup"><span data-stu-id="d8e45-132">The context code.</span></span>

> <span data-ttu-id="d8e45-133">パブリック int [Ismenukeydown](#ismenukeydown)</span><span class="sxs-lookup"><span data-stu-id="d8e45-133">public int [IsMenuKeyDown](#ismenukeydown)</span></span>

#### <span data-ttu-id="d8e45-134">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="d8e45-134">RepeatCount</span></span> 

<span data-ttu-id="d8e45-135">現在のメッセージの繰り返し回数。</span><span class="sxs-lookup"><span data-stu-id="d8e45-135">The repeat count for the current message.</span></span>

> <span data-ttu-id="d8e45-136">パブリック uint [Repeatcount](#repeatcount)</span><span class="sxs-lookup"><span data-stu-id="d8e45-136">public uint [RepeatCount](#repeatcount)</span></span>

#### <span data-ttu-id="d8e45-137">ScanCode</span><span class="sxs-lookup"><span data-stu-id="d8e45-137">ScanCode</span></span> 

<span data-ttu-id="d8e45-138">スキャンコード。</span><span class="sxs-lookup"><span data-stu-id="d8e45-138">The scan code.</span></span>

> <span data-ttu-id="d8e45-139">パブリック uint[スキャンコード](#scancode)</span><span class="sxs-lookup"><span data-stu-id="d8e45-139">public uint [ScanCode](#scancode)</span></span>

#### <span data-ttu-id="d8e45-140">通常の方法</span><span class="sxs-lookup"><span data-stu-id="d8e45-140">WasKeyDown</span></span> 

<span data-ttu-id="d8e45-141">前のキーの状態。</span><span class="sxs-lookup"><span data-stu-id="d8e45-141">The previous key state.</span></span>

> <span data-ttu-id="d8e45-142">公開 int [WasKeyDown](#waskeydown)</span><span class="sxs-lookup"><span data-stu-id="d8e45-142">public int [WasKeyDown](#waskeydown)</span></span>

