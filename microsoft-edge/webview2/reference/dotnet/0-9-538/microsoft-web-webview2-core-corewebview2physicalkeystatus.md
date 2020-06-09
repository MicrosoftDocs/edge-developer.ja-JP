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
ms.openlocfilehash: e0fb3f9ff7114b0c4f2a42893adabfd72e9616de
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698954"
---
# <span data-ttu-id="66813-104">CoreWebView2PhysicalKeyStatus 構造体 (WebView2)</span><span class="sxs-lookup"><span data-stu-id="66813-104">Microsoft.Web.WebView2.Core.CoreWebView2PhysicalKeyStatus struct</span></span> 

<span data-ttu-id="66813-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="66813-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="66813-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="66813-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="66813-107">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="66813-107">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

## <span data-ttu-id="66813-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="66813-108">Summary</span></span>

 <span data-ttu-id="66813-109">Members</span><span class="sxs-lookup"><span data-stu-id="66813-109">Members</span></span>                        | <span data-ttu-id="66813-110">説明</span><span class="sxs-lookup"><span data-stu-id="66813-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="66813-111">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="66813-111">IsExtendedKey</span></span>](#isextendedkey) | <span data-ttu-id="66813-112">キーが拡張キーかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="66813-112">Indicates whether the key is an extended key.</span></span>
[<span data-ttu-id="66813-113">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="66813-113">IsKeyReleased</span></span>](#iskeyreleased) | <span data-ttu-id="66813-114">切り替えの状態。</span><span class="sxs-lookup"><span data-stu-id="66813-114">The transition state.</span></span>
[<span data-ttu-id="66813-115">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="66813-115">IsMenuKeyDown</span></span>](#ismenukeydown) | <span data-ttu-id="66813-116">コンテキストコード。</span><span class="sxs-lookup"><span data-stu-id="66813-116">The context code.</span></span>
[<span data-ttu-id="66813-117">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="66813-117">RepeatCount</span></span>](#repeatcount) | <span data-ttu-id="66813-118">現在のメッセージの繰り返し回数。</span><span class="sxs-lookup"><span data-stu-id="66813-118">The repeat count for the current message.</span></span>
[<span data-ttu-id="66813-119">ScanCode</span><span class="sxs-lookup"><span data-stu-id="66813-119">ScanCode</span></span>](#scancode) | <span data-ttu-id="66813-120">スキャンコード。</span><span class="sxs-lookup"><span data-stu-id="66813-120">The scan code.</span></span>
[<span data-ttu-id="66813-121">通常の方法</span><span class="sxs-lookup"><span data-stu-id="66813-121">WasKeyDown</span></span>](#waskeydown) | <span data-ttu-id="66813-122">前のキーの状態。</span><span class="sxs-lookup"><span data-stu-id="66813-122">The previous key state.</span></span>

<span data-ttu-id="66813-123">詳細については、WM_KEYDOWN のドキュメントを参照してください [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown) 。</span><span class="sxs-lookup"><span data-stu-id="66813-123">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown).</span></span>

## <span data-ttu-id="66813-124">Members</span><span class="sxs-lookup"><span data-stu-id="66813-124">Members</span></span>

#### <span data-ttu-id="66813-125">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="66813-125">IsExtendedKey</span></span> 

<span data-ttu-id="66813-126">キーが拡張キーかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="66813-126">Indicates whether the key is an extended key.</span></span>

> <span data-ttu-id="66813-127">パブリック int [IsExtendedKey](#isextendedkey)</span><span class="sxs-lookup"><span data-stu-id="66813-127">public int [IsExtendedKey](#isextendedkey)</span></span>

#### <span data-ttu-id="66813-128">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="66813-128">IsKeyReleased</span></span> 

<span data-ttu-id="66813-129">切り替えの状態。</span><span class="sxs-lookup"><span data-stu-id="66813-129">The transition state.</span></span>

> <span data-ttu-id="66813-130">公開 int [Iskeyreleased](#iskeyreleased)</span><span class="sxs-lookup"><span data-stu-id="66813-130">public int [IsKeyReleased](#iskeyreleased)</span></span>

#### <span data-ttu-id="66813-131">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="66813-131">IsMenuKeyDown</span></span> 

<span data-ttu-id="66813-132">コンテキストコード。</span><span class="sxs-lookup"><span data-stu-id="66813-132">The context code.</span></span>

> <span data-ttu-id="66813-133">パブリック int [Ismenukeydown](#ismenukeydown)</span><span class="sxs-lookup"><span data-stu-id="66813-133">public int [IsMenuKeyDown](#ismenukeydown)</span></span>

#### <span data-ttu-id="66813-134">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="66813-134">RepeatCount</span></span> 

<span data-ttu-id="66813-135">現在のメッセージの繰り返し回数。</span><span class="sxs-lookup"><span data-stu-id="66813-135">The repeat count for the current message.</span></span>

> <span data-ttu-id="66813-136">パブリック uint [Repeatcount](#repeatcount)</span><span class="sxs-lookup"><span data-stu-id="66813-136">public uint [RepeatCount](#repeatcount)</span></span>

#### <span data-ttu-id="66813-137">ScanCode</span><span class="sxs-lookup"><span data-stu-id="66813-137">ScanCode</span></span> 

<span data-ttu-id="66813-138">スキャンコード。</span><span class="sxs-lookup"><span data-stu-id="66813-138">The scan code.</span></span>

> <span data-ttu-id="66813-139">パブリック uint[スキャンコード](#scancode)</span><span class="sxs-lookup"><span data-stu-id="66813-139">public uint [ScanCode](#scancode)</span></span>

#### <span data-ttu-id="66813-140">通常の方法</span><span class="sxs-lookup"><span data-stu-id="66813-140">WasKeyDown</span></span> 

<span data-ttu-id="66813-141">前のキーの状態。</span><span class="sxs-lookup"><span data-stu-id="66813-141">The previous key state.</span></span>

> <span data-ttu-id="66813-142">公開 int [WasKeyDown](#waskeydown)</span><span class="sxs-lookup"><span data-stu-id="66813-142">public int [WasKeyDown](#waskeydown)</span></span>
