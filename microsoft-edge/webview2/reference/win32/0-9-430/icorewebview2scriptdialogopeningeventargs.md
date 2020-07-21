---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: cd8f96787d289ab0fe649244ce665445efdbcecf
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884044"
---
# <span data-ttu-id="a9b39-104">0.9.430-インターフェイス ICoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="a9b39-104">0.9.430 - interface ICoreWebView2ScriptDialogOpeningEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="a9b39-105">Scriptな開始イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="a9b39-105">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="a9b39-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a9b39-106">Summary</span></span>

 <span data-ttu-id="a9b39-107">Members</span><span class="sxs-lookup"><span data-stu-id="a9b39-107">Members</span></span>                        | <span data-ttu-id="a9b39-108">説明</span><span class="sxs-lookup"><span data-stu-id="a9b39-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a9b39-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="a9b39-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="a9b39-110">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="a9b39-110">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="a9b39-111">get_Kind</span><span class="sxs-lookup"><span data-stu-id="a9b39-111">get_Kind</span></span>](#get_kind) | <span data-ttu-id="a9b39-112">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="a9b39-112">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="a9b39-113">get_Message</span><span class="sxs-lookup"><span data-stu-id="a9b39-113">get_Message</span></span>](#get_message) | <span data-ttu-id="a9b39-114">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="a9b39-114">The message of the dialog box.</span></span>
[<span data-ttu-id="a9b39-115">Accept</span><span class="sxs-lookup"><span data-stu-id="a9b39-115">Accept</span></span>](#accept) | <span data-ttu-id="a9b39-116">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a9b39-116">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="a9b39-117">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="a9b39-117">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="a9b39-118">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a9b39-118">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="a9b39-119">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="a9b39-119">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="a9b39-120">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="a9b39-120">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="a9b39-121">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="a9b39-121">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="a9b39-122">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9b39-122">Set the ResultText property.</span></span>
[<span data-ttu-id="a9b39-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="a9b39-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="a9b39-124">GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="a9b39-124">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="a9b39-125">Members</span><span class="sxs-lookup"><span data-stu-id="a9b39-125">Members</span></span>

#### <span data-ttu-id="a9b39-126">get_Uri</span><span class="sxs-lookup"><span data-stu-id="a9b39-126">get_Uri</span></span> 

<span data-ttu-id="a9b39-127">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="a9b39-127">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="a9b39-128">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="a9b39-128">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="a9b39-129">get_Kind</span><span class="sxs-lookup"><span data-stu-id="a9b39-129">get_Kind</span></span> 

<span data-ttu-id="a9b39-130">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="a9b39-130">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="a9b39-131">パブリック HRESULT [get_Kind](#get_kind)(CORE_WEBVIEW2_SCRIPT_DIALOG_KIND \* Kind)</span><span class="sxs-lookup"><span data-stu-id="a9b39-131">public HRESULT [get_Kind](#get_kind)(CORE_WEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

<span data-ttu-id="a9b39-132">[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a9b39-132">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="a9b39-133">get_Message</span><span class="sxs-lookup"><span data-stu-id="a9b39-133">get_Message</span></span> 

<span data-ttu-id="a9b39-134">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="a9b39-134">The message of the dialog box.</span></span>

> <span data-ttu-id="a9b39-135">パブリック HRESULT [get_Message](#get_message)(LPWSTR \* Message)</span><span class="sxs-lookup"><span data-stu-id="a9b39-135">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="a9b39-136">JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。</span><span class="sxs-lookup"><span data-stu-id="a9b39-136">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="a9b39-137">Accept</span><span class="sxs-lookup"><span data-stu-id="a9b39-137">Accept</span></span> 

<span data-ttu-id="a9b39-138">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a9b39-138">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="a9b39-139">パブリック HRESULT [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="a9b39-139">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="a9b39-140">これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a9b39-140">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="a9b39-141">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="a9b39-141">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="a9b39-142">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="a9b39-142">get_DefaultText</span></span> 

<span data-ttu-id="a9b39-143">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a9b39-143">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="a9b39-144">パブリック HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaulttext)</span><span class="sxs-lookup"><span data-stu-id="a9b39-144">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="a9b39-145">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="a9b39-145">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="a9b39-146">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="a9b39-146">get_ResultText</span></span> 

<span data-ttu-id="a9b39-147">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="a9b39-147">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="a9b39-148">パブリック HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resulttext)</span><span class="sxs-lookup"><span data-stu-id="a9b39-148">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="a9b39-149">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a9b39-149">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="a9b39-150">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="a9b39-150">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="a9b39-151">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="a9b39-151">put_ResultText</span></span> 

<span data-ttu-id="a9b39-152">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9b39-152">Set the ResultText property.</span></span>

> <span data-ttu-id="a9b39-153">パブリック HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resulttext)</span><span class="sxs-lookup"><span data-stu-id="a9b39-153">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

#### <span data-ttu-id="a9b39-154">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="a9b39-154">GetDeferral</span></span> 

<span data-ttu-id="a9b39-155">GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="a9b39-155">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="a9b39-156">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="a9b39-156">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="a9b39-157">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9b39-157">You can use this to complete the event at a later time.</span></span>

