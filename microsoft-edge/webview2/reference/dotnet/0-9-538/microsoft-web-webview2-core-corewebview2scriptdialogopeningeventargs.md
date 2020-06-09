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
ms.openlocfilehash: 93e662088ae1561b5dcb33390f46a41c19ca0aaf
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698953"
---
# <span data-ttu-id="9f687-104">WebView2 クラス (CoreWebView2ScriptDialogOpeningEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="9f687-104">Microsoft.Web.WebView2.Core.CoreWebView2ScriptDialogOpeningEventArgs class</span></span> 

<span data-ttu-id="9f687-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="9f687-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="9f687-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f687-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="9f687-107">Scriptな開始イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="9f687-107">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="9f687-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="9f687-108">Summary</span></span>

 <span data-ttu-id="9f687-109">Members</span><span class="sxs-lookup"><span data-stu-id="9f687-109">Members</span></span>                        | <span data-ttu-id="9f687-110">説明</span><span class="sxs-lookup"><span data-stu-id="9f687-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9f687-111">DefaultText</span><span class="sxs-lookup"><span data-stu-id="9f687-111">DefaultText</span></span>](#defaulttext) | <span data-ttu-id="9f687-112">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="9f687-112">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="9f687-113">種類</span><span class="sxs-lookup"><span data-stu-id="9f687-113">Kind</span></span>](#kind) | <span data-ttu-id="9f687-114">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="9f687-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="9f687-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9f687-115">Message</span></span>](#message) | <span data-ttu-id="9f687-116">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="9f687-116">The message of the dialog box.</span></span>
[<span data-ttu-id="9f687-117">ResultText</span><span class="sxs-lookup"><span data-stu-id="9f687-117">ResultText</span></span>](#resulttext) | <span data-ttu-id="9f687-118">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="9f687-118">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="9f687-119">URI</span><span class="sxs-lookup"><span data-stu-id="9f687-119">Uri</span></span>](#uri) | <span data-ttu-id="9f687-120">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="9f687-120">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="9f687-121">Accept</span><span class="sxs-lookup"><span data-stu-id="9f687-121">Accept</span></span>](#accept) | <span data-ttu-id="9f687-122">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="9f687-122">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="9f687-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="9f687-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="9f687-124">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="9f687-124">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="9f687-125">Members</span><span class="sxs-lookup"><span data-stu-id="9f687-125">Members</span></span>

#### <span data-ttu-id="9f687-126">DefaultText</span><span class="sxs-lookup"><span data-stu-id="9f687-126">DefaultText</span></span> 

<span data-ttu-id="9f687-127">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="9f687-127">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="9f687-128">パブリック文字列の[Defaulttext](#defaulttext)</span><span class="sxs-lookup"><span data-stu-id="9f687-128">public string [DefaultText](#defaulttext)</span></span>

<span data-ttu-id="9f687-129">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="9f687-129">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="9f687-130">種類</span><span class="sxs-lookup"><span data-stu-id="9f687-130">Kind</span></span> 

<span data-ttu-id="9f687-131">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="9f687-131">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="9f687-132">パブリック CoreWebView2ScriptDialogKind [Kind](#kind)</span><span class="sxs-lookup"><span data-stu-id="9f687-132">public CoreWebView2ScriptDialogKind [Kind](#kind)</span></span>

<span data-ttu-id="9f687-133">[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9f687-133">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="9f687-134">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9f687-134">Message</span></span> 

<span data-ttu-id="9f687-135">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="9f687-135">The message of the dialog box.</span></span>

> <span data-ttu-id="9f687-136">パブリック文字列[メッセージ](#message)</span><span class="sxs-lookup"><span data-stu-id="9f687-136">public string [Message](#message)</span></span>

<span data-ttu-id="9f687-137">JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。</span><span class="sxs-lookup"><span data-stu-id="9f687-137">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="9f687-138">ResultText</span><span class="sxs-lookup"><span data-stu-id="9f687-138">ResultText</span></span> 

<span data-ttu-id="9f687-139">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="9f687-139">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="9f687-140">パブリック文字列の[Resulttext](#resulttext)</span><span class="sxs-lookup"><span data-stu-id="9f687-140">public string [ResultText](#resulttext)</span></span>

<span data-ttu-id="9f687-141">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="9f687-141">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="9f687-142">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="9f687-142">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="9f687-143">URI</span><span class="sxs-lookup"><span data-stu-id="9f687-143">Uri</span></span> 

<span data-ttu-id="9f687-144">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="9f687-144">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="9f687-145">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="9f687-145">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="9f687-146">Accept</span><span class="sxs-lookup"><span data-stu-id="9f687-146">Accept</span></span> 

<span data-ttu-id="9f687-147">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="9f687-147">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="9f687-148">パブリック void [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="9f687-148">public void [Accept](#accept)()</span></span>

<span data-ttu-id="9f687-149">これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9f687-149">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="9f687-150">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="9f687-150">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="9f687-151">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="9f687-151">GetDeferral</span></span> 

<span data-ttu-id="9f687-152">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="9f687-152">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="9f687-153">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="9f687-153">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="9f687-154">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f687-154">You can use this to complete the event at a later time.</span></span>

