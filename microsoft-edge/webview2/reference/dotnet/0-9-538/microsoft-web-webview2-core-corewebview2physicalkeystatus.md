---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2PhysicalKeyStatus の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2PhysicalKeyStatus。
ms.openlocfilehash: 17ed4a578234a056a7e6ff347829a12e39fa93bd
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010923"
---
# <span data-ttu-id="dfb4a-104">WebView2 構造体 0.9.579-CoreWebView2PhysicalKeyStatus 構造体</span><span class="sxs-lookup"><span data-stu-id="dfb4a-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2PhysicalKeyStatus struct</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="dfb4a-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="dfb4a-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="dfb4a-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="dfb4a-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="dfb4a-107">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-107">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

## <span data-ttu-id="dfb4a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="dfb4a-108">Summary</span></span>

 <span data-ttu-id="dfb4a-109">Members</span><span class="sxs-lookup"><span data-stu-id="dfb4a-109">Members</span></span>                        | <span data-ttu-id="dfb4a-110">説明</span><span class="sxs-lookup"><span data-stu-id="dfb4a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dfb4a-111">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="dfb4a-111">IsExtendedKey</span></span>](#isextendedkey) | <span data-ttu-id="dfb4a-112">キーが拡張キーかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-112">Indicates whether the key is an extended key.</span></span>
[<span data-ttu-id="dfb4a-113">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="dfb4a-113">IsKeyReleased</span></span>](#iskeyreleased) | <span data-ttu-id="dfb4a-114">切り替えの状態。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-114">The transition state.</span></span>
[<span data-ttu-id="dfb4a-115">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="dfb4a-115">IsMenuKeyDown</span></span>](#ismenukeydown) | <span data-ttu-id="dfb4a-116">コンテキストコード。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-116">The context code.</span></span>
[<span data-ttu-id="dfb4a-117">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="dfb4a-117">RepeatCount</span></span>](#repeatcount) | <span data-ttu-id="dfb4a-118">現在のメッセージの繰り返し回数。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-118">The repeat count for the current message.</span></span>
[<span data-ttu-id="dfb4a-119">ScanCode</span><span class="sxs-lookup"><span data-stu-id="dfb4a-119">ScanCode</span></span>](#scancode) | <span data-ttu-id="dfb4a-120">スキャンコード。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-120">The scan code.</span></span>
[<span data-ttu-id="dfb4a-121">通常の方法</span><span class="sxs-lookup"><span data-stu-id="dfb4a-121">WasKeyDown</span></span>](#waskeydown) | <span data-ttu-id="dfb4a-122">前のキーの状態。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-122">The previous key state.</span></span>

<span data-ttu-id="dfb4a-123">詳細については、WM_KEYDOWN のドキュメントを参照してください [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown) 。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-123">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown).</span></span>

## <span data-ttu-id="dfb4a-124">Members</span><span class="sxs-lookup"><span data-stu-id="dfb4a-124">Members</span></span>

#### <span data-ttu-id="dfb4a-125">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="dfb4a-125">IsExtendedKey</span></span> 

<span data-ttu-id="dfb4a-126">キーが拡張キーかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-126">Indicates whether the key is an extended key.</span></span>

> <span data-ttu-id="dfb4a-127">パブリック int [IsExtendedKey](#isextendedkey)</span><span class="sxs-lookup"><span data-stu-id="dfb4a-127">public int [IsExtendedKey](#isextendedkey)</span></span>

#### <span data-ttu-id="dfb4a-128">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="dfb4a-128">IsKeyReleased</span></span> 

<span data-ttu-id="dfb4a-129">切り替えの状態。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-129">The transition state.</span></span>

> <span data-ttu-id="dfb4a-130">公開 int [Iskeyreleased](#iskeyreleased)</span><span class="sxs-lookup"><span data-stu-id="dfb4a-130">public int [IsKeyReleased](#iskeyreleased)</span></span>

#### <span data-ttu-id="dfb4a-131">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="dfb4a-131">IsMenuKeyDown</span></span> 

<span data-ttu-id="dfb4a-132">コンテキストコード。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-132">The context code.</span></span>

> <span data-ttu-id="dfb4a-133">パブリック int [Ismenukeydown](#ismenukeydown)</span><span class="sxs-lookup"><span data-stu-id="dfb4a-133">public int [IsMenuKeyDown](#ismenukeydown)</span></span>

#### <span data-ttu-id="dfb4a-134">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="dfb4a-134">RepeatCount</span></span> 

<span data-ttu-id="dfb4a-135">現在のメッセージの繰り返し回数。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-135">The repeat count for the current message.</span></span>

> <span data-ttu-id="dfb4a-136">パブリック uint [Repeatcount](#repeatcount)</span><span class="sxs-lookup"><span data-stu-id="dfb4a-136">public uint [RepeatCount](#repeatcount)</span></span>

#### <span data-ttu-id="dfb4a-137">ScanCode</span><span class="sxs-lookup"><span data-stu-id="dfb4a-137">ScanCode</span></span> 

<span data-ttu-id="dfb4a-138">スキャンコード。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-138">The scan code.</span></span>

> <span data-ttu-id="dfb4a-139">パブリック uint [スキャンコード](#scancode)</span><span class="sxs-lookup"><span data-stu-id="dfb4a-139">public uint [ScanCode](#scancode)</span></span>

#### <span data-ttu-id="dfb4a-140">通常の方法</span><span class="sxs-lookup"><span data-stu-id="dfb4a-140">WasKeyDown</span></span> 

<span data-ttu-id="dfb4a-141">前のキーの状態。</span><span class="sxs-lookup"><span data-stu-id="dfb4a-141">The previous key state.</span></span>

> <span data-ttu-id="dfb4a-142">公開 int [WasKeyDown](#waskeydown)</span><span class="sxs-lookup"><span data-stu-id="dfb4a-142">public int [WasKeyDown](#waskeydown)</span></span>

