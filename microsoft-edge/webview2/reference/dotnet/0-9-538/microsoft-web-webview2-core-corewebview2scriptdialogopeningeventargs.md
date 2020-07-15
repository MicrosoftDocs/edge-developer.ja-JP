---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2ScriptDialogOpeningEventArgs。
ms.openlocfilehash: cbff39e9393026f51471bdfb3189600e2d7bf109
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879696"
---
# <span data-ttu-id="6c211-104">WebView2 クラス (CoreWebView2ScriptDialogOpeningEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="6c211-104">Microsoft.Web.WebView2.Core.CoreWebView2ScriptDialogOpeningEventArgs class</span></span> 

<span data-ttu-id="6c211-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="6c211-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="6c211-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="6c211-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="6c211-107">Scriptな開始イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="6c211-107">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="6c211-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6c211-108">Summary</span></span>

 <span data-ttu-id="6c211-109">Members</span><span class="sxs-lookup"><span data-stu-id="6c211-109">Members</span></span>                        | <span data-ttu-id="6c211-110">説明</span><span class="sxs-lookup"><span data-stu-id="6c211-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6c211-111">DefaultText</span><span class="sxs-lookup"><span data-stu-id="6c211-111">DefaultText</span></span>](#defaulttext) | <span data-ttu-id="6c211-112">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="6c211-112">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="6c211-113">種類</span><span class="sxs-lookup"><span data-stu-id="6c211-113">Kind</span></span>](#kind) | <span data-ttu-id="6c211-114">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="6c211-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="6c211-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6c211-115">Message</span></span>](#message) | <span data-ttu-id="6c211-116">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="6c211-116">The message of the dialog box.</span></span>
[<span data-ttu-id="6c211-117">ResultText</span><span class="sxs-lookup"><span data-stu-id="6c211-117">ResultText</span></span>](#resulttext) | <span data-ttu-id="6c211-118">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="6c211-118">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="6c211-119">URI</span><span class="sxs-lookup"><span data-stu-id="6c211-119">Uri</span></span>](#uri) | <span data-ttu-id="6c211-120">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="6c211-120">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="6c211-121">Accept</span><span class="sxs-lookup"><span data-stu-id="6c211-121">Accept</span></span>](#accept) | <span data-ttu-id="6c211-122">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="6c211-122">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="6c211-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6c211-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="6c211-124">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="6c211-124">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="6c211-125">Members</span><span class="sxs-lookup"><span data-stu-id="6c211-125">Members</span></span>

#### <span data-ttu-id="6c211-126">DefaultText</span><span class="sxs-lookup"><span data-stu-id="6c211-126">DefaultText</span></span> 

<span data-ttu-id="6c211-127">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="6c211-127">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="6c211-128">パブリック文字列の[Defaulttext](#defaulttext)</span><span class="sxs-lookup"><span data-stu-id="6c211-128">public string [DefaultText](#defaulttext)</span></span>

<span data-ttu-id="6c211-129">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="6c211-129">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="6c211-130">種類</span><span class="sxs-lookup"><span data-stu-id="6c211-130">Kind</span></span> 

<span data-ttu-id="6c211-131">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="6c211-131">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="6c211-132">パブリック CoreWebView2ScriptDialogKind [Kind](#kind)</span><span class="sxs-lookup"><span data-stu-id="6c211-132">public CoreWebView2ScriptDialogKind [Kind](#kind)</span></span>

<span data-ttu-id="6c211-133">[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6c211-133">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="6c211-134">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6c211-134">Message</span></span> 

<span data-ttu-id="6c211-135">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="6c211-135">The message of the dialog box.</span></span>

> <span data-ttu-id="6c211-136">パブリック文字列[メッセージ](#message)</span><span class="sxs-lookup"><span data-stu-id="6c211-136">public string [Message](#message)</span></span>

<span data-ttu-id="6c211-137">JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。</span><span class="sxs-lookup"><span data-stu-id="6c211-137">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="6c211-138">ResultText</span><span class="sxs-lookup"><span data-stu-id="6c211-138">ResultText</span></span> 

<span data-ttu-id="6c211-139">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="6c211-139">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="6c211-140">パブリック文字列の[Resulttext](#resulttext)</span><span class="sxs-lookup"><span data-stu-id="6c211-140">public string [ResultText](#resulttext)</span></span>

<span data-ttu-id="6c211-141">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="6c211-141">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="6c211-142">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="6c211-142">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="6c211-143">URI</span><span class="sxs-lookup"><span data-stu-id="6c211-143">Uri</span></span> 

<span data-ttu-id="6c211-144">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="6c211-144">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="6c211-145">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="6c211-145">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="6c211-146">Accept</span><span class="sxs-lookup"><span data-stu-id="6c211-146">Accept</span></span> 

<span data-ttu-id="6c211-147">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="6c211-147">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="6c211-148">パブリック void [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="6c211-148">public void [Accept](#accept)()</span></span>

<span data-ttu-id="6c211-149">これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6c211-149">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="6c211-150">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="6c211-150">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="6c211-151">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6c211-151">GetDeferral</span></span> 

<span data-ttu-id="6c211-152">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="6c211-152">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="6c211-153">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="6c211-153">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="6c211-154">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c211-154">You can use this to complete the event at a later time.</span></span>

