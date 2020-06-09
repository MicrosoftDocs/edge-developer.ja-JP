---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 1359e9472455acf2949cc329de4280ad970a3b68
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697309"
---
# <span data-ttu-id="2b132-104">WebView2 クラス (CoreWebView2ScriptDialogOpeningEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="2b132-104">Microsoft.Web.WebView2.Core.CoreWebView2ScriptDialogOpeningEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="2b132-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b132-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="2b132-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b132-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="2b132-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="2b132-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="2b132-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b132-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="2b132-109">Scriptな開始イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="2b132-109">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="2b132-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="2b132-110">Summary</span></span>

 <span data-ttu-id="2b132-111">Members</span><span class="sxs-lookup"><span data-stu-id="2b132-111">Members</span></span>                        | <span data-ttu-id="2b132-112">説明</span><span class="sxs-lookup"><span data-stu-id="2b132-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2b132-113">DefaultText</span><span class="sxs-lookup"><span data-stu-id="2b132-113">DefaultText</span></span>](#defaulttext) | <span data-ttu-id="2b132-114">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="2b132-114">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="2b132-115">種類</span><span class="sxs-lookup"><span data-stu-id="2b132-115">Kind</span></span>](#kind) | <span data-ttu-id="2b132-116">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="2b132-116">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="2b132-117">メッセージ</span><span class="sxs-lookup"><span data-stu-id="2b132-117">Message</span></span>](#message) | <span data-ttu-id="2b132-118">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b132-118">The message of the dialog box.</span></span>
[<span data-ttu-id="2b132-119">ResultText</span><span class="sxs-lookup"><span data-stu-id="2b132-119">ResultText</span></span>](#resulttext) | <span data-ttu-id="2b132-120">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="2b132-120">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="2b132-121">URI</span><span class="sxs-lookup"><span data-stu-id="2b132-121">Uri</span></span>](#uri) | <span data-ttu-id="2b132-122">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="2b132-122">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="2b132-123">Accept</span><span class="sxs-lookup"><span data-stu-id="2b132-123">Accept</span></span>](#accept) | <span data-ttu-id="2b132-124">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="2b132-124">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="2b132-125">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="2b132-125">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="2b132-126">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="2b132-126">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="2b132-127">Members</span><span class="sxs-lookup"><span data-stu-id="2b132-127">Members</span></span>

#### <span data-ttu-id="2b132-128">DefaultText</span><span class="sxs-lookup"><span data-stu-id="2b132-128">DefaultText</span></span> 

<span data-ttu-id="2b132-129">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="2b132-129">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="2b132-130">パブリック文字列の[Defaulttext](#defaulttext)</span><span class="sxs-lookup"><span data-stu-id="2b132-130">public string [DefaultText](#defaulttext)</span></span>

<span data-ttu-id="2b132-131">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b132-131">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="2b132-132">種類</span><span class="sxs-lookup"><span data-stu-id="2b132-132">Kind</span></span> 

<span data-ttu-id="2b132-133">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="2b132-133">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="2b132-134">パブリック CoreWebView2ScriptDialogKind [Kind](#kind)</span><span class="sxs-lookup"><span data-stu-id="2b132-134">public CoreWebView2ScriptDialogKind [Kind](#kind)</span></span>

<span data-ttu-id="2b132-135">[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b132-135">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="2b132-136">メッセージ</span><span class="sxs-lookup"><span data-stu-id="2b132-136">Message</span></span> 

<span data-ttu-id="2b132-137">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b132-137">The message of the dialog box.</span></span>

> <span data-ttu-id="2b132-138">パブリック文字列[メッセージ](#message)</span><span class="sxs-lookup"><span data-stu-id="2b132-138">public string [Message](#message)</span></span>

<span data-ttu-id="2b132-139">JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。</span><span class="sxs-lookup"><span data-stu-id="2b132-139">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="2b132-140">ResultText</span><span class="sxs-lookup"><span data-stu-id="2b132-140">ResultText</span></span> 

<span data-ttu-id="2b132-141">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="2b132-141">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="2b132-142">パブリック文字列の[Resulttext](#resulttext)</span><span class="sxs-lookup"><span data-stu-id="2b132-142">public string [ResultText](#resulttext)</span></span>

<span data-ttu-id="2b132-143">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="2b132-143">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="2b132-144">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="2b132-144">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="2b132-145">URI</span><span class="sxs-lookup"><span data-stu-id="2b132-145">Uri</span></span> 

<span data-ttu-id="2b132-146">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="2b132-146">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="2b132-147">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="2b132-147">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="2b132-148">Accept</span><span class="sxs-lookup"><span data-stu-id="2b132-148">Accept</span></span> 

<span data-ttu-id="2b132-149">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="2b132-149">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="2b132-150">パブリック void [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="2b132-150">public void [Accept](#accept)()</span></span>

<span data-ttu-id="2b132-151">これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2b132-151">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="2b132-152">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="2b132-152">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="2b132-153">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="2b132-153">GetDeferral</span></span> 

<span data-ttu-id="2b132-154">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="2b132-154">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="2b132-155">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="2b132-155">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="2b132-156">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b132-156">You can use this to complete the event at a later time.</span></span>

