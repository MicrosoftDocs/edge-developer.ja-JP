---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2ScriptDialogOpeningEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 4e7cd20b982d829be6d304eea1f3f60759cc503f
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884856"
---
# <span data-ttu-id="61d4e-104">0.9.515 クラスの WebView2 クラス (CoreWebView2ScriptDialogOpeningEventArgs)</span><span class="sxs-lookup"><span data-stu-id="61d4e-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2ScriptDialogOpeningEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="61d4e-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="61d4e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="61d4e-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="61d4e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="61d4e-107">Scriptな開始イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="61d4e-107">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="61d4e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="61d4e-108">Summary</span></span>

 <span data-ttu-id="61d4e-109">Members</span><span class="sxs-lookup"><span data-stu-id="61d4e-109">Members</span></span>                        | <span data-ttu-id="61d4e-110">説明</span><span class="sxs-lookup"><span data-stu-id="61d4e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="61d4e-111">DefaultText</span><span class="sxs-lookup"><span data-stu-id="61d4e-111">DefaultText</span></span>](#defaulttext) | <span data-ttu-id="61d4e-112">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="61d4e-112">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="61d4e-113">種類</span><span class="sxs-lookup"><span data-stu-id="61d4e-113">Kind</span></span>](#kind) | <span data-ttu-id="61d4e-114">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="61d4e-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="61d4e-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="61d4e-115">Message</span></span>](#message) | <span data-ttu-id="61d4e-116">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="61d4e-116">The message of the dialog box.</span></span>
[<span data-ttu-id="61d4e-117">ResultText</span><span class="sxs-lookup"><span data-stu-id="61d4e-117">ResultText</span></span>](#resulttext) | <span data-ttu-id="61d4e-118">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="61d4e-118">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="61d4e-119">URI</span><span class="sxs-lookup"><span data-stu-id="61d4e-119">Uri</span></span>](#uri) | <span data-ttu-id="61d4e-120">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="61d4e-120">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="61d4e-121">Accept</span><span class="sxs-lookup"><span data-stu-id="61d4e-121">Accept</span></span>](#accept) | <span data-ttu-id="61d4e-122">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="61d4e-122">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="61d4e-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="61d4e-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="61d4e-124">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="61d4e-124">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="61d4e-125">Members</span><span class="sxs-lookup"><span data-stu-id="61d4e-125">Members</span></span>

#### <span data-ttu-id="61d4e-126">DefaultText</span><span class="sxs-lookup"><span data-stu-id="61d4e-126">DefaultText</span></span> 

<span data-ttu-id="61d4e-127">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="61d4e-127">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="61d4e-128">パブリック文字列の[Defaulttext](#defaulttext)</span><span class="sxs-lookup"><span data-stu-id="61d4e-128">public string [DefaultText](#defaulttext)</span></span>

<span data-ttu-id="61d4e-129">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="61d4e-129">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="61d4e-130">種類</span><span class="sxs-lookup"><span data-stu-id="61d4e-130">Kind</span></span> 

<span data-ttu-id="61d4e-131">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="61d4e-131">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="61d4e-132">パブリック CoreWebView2ScriptDialogKind [Kind](#kind)</span><span class="sxs-lookup"><span data-stu-id="61d4e-132">public CoreWebView2ScriptDialogKind [Kind](#kind)</span></span>

<span data-ttu-id="61d4e-133">[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。</span><span class="sxs-lookup"><span data-stu-id="61d4e-133">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="61d4e-134">メッセージ</span><span class="sxs-lookup"><span data-stu-id="61d4e-134">Message</span></span> 

<span data-ttu-id="61d4e-135">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="61d4e-135">The message of the dialog box.</span></span>

> <span data-ttu-id="61d4e-136">パブリック文字列[メッセージ](#message)</span><span class="sxs-lookup"><span data-stu-id="61d4e-136">public string [Message](#message)</span></span>

<span data-ttu-id="61d4e-137">JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。</span><span class="sxs-lookup"><span data-stu-id="61d4e-137">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="61d4e-138">ResultText</span><span class="sxs-lookup"><span data-stu-id="61d4e-138">ResultText</span></span> 

<span data-ttu-id="61d4e-139">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="61d4e-139">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="61d4e-140">パブリック文字列の[Resulttext](#resulttext)</span><span class="sxs-lookup"><span data-stu-id="61d4e-140">public string [ResultText](#resulttext)</span></span>

<span data-ttu-id="61d4e-141">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="61d4e-141">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="61d4e-142">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="61d4e-142">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="61d4e-143">URI</span><span class="sxs-lookup"><span data-stu-id="61d4e-143">Uri</span></span> 

<span data-ttu-id="61d4e-144">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="61d4e-144">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="61d4e-145">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="61d4e-145">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="61d4e-146">Accept</span><span class="sxs-lookup"><span data-stu-id="61d4e-146">Accept</span></span> 

<span data-ttu-id="61d4e-147">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="61d4e-147">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="61d4e-148">パブリック void [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="61d4e-148">public void [Accept](#accept)()</span></span>

<span data-ttu-id="61d4e-149">これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="61d4e-149">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="61d4e-150">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="61d4e-150">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="61d4e-151">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="61d4e-151">GetDeferral</span></span> 

<span data-ttu-id="61d4e-152">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="61d4e-152">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="61d4e-153">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="61d4e-153">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="61d4e-154">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="61d4e-154">You can use this to complete the event at a later time.</span></span>

