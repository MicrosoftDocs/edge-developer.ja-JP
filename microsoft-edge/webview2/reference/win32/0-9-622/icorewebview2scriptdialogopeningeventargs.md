---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ScriptDialogOpeningEventArgs
ms.openlocfilehash: 442bd26caeb78804ceb202b302123b0ee1127f09
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012330"
---
# <span data-ttu-id="1e904-104">インターフェイス ICoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="1e904-104">interface ICoreWebView2ScriptDialogOpeningEventArgs</span></span> 

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="1e904-105">Scriptな開始イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="1e904-105">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="1e904-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="1e904-106">Summary</span></span>

 <span data-ttu-id="1e904-107">Members</span><span class="sxs-lookup"><span data-stu-id="1e904-107">Members</span></span>                        | <span data-ttu-id="1e904-108">説明</span><span class="sxs-lookup"><span data-stu-id="1e904-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1e904-109">Accept</span><span class="sxs-lookup"><span data-stu-id="1e904-109">Accept</span></span>](#accept) | <span data-ttu-id="1e904-110">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1e904-110">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="1e904-111">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="1e904-111">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="1e904-112">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="1e904-112">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="1e904-113">get_Kind</span><span class="sxs-lookup"><span data-stu-id="1e904-113">get_Kind</span></span>](#get_kind) | <span data-ttu-id="1e904-114">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="1e904-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="1e904-115">get_Message</span><span class="sxs-lookup"><span data-stu-id="1e904-115">get_Message</span></span>](#get_message) | <span data-ttu-id="1e904-116">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="1e904-116">The message of the dialog box.</span></span>
[<span data-ttu-id="1e904-117">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="1e904-117">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="1e904-118">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="1e904-118">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="1e904-119">get_Uri</span><span class="sxs-lookup"><span data-stu-id="1e904-119">get_Uri</span></span>](#get_uri) | <span data-ttu-id="1e904-120">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="1e904-120">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="1e904-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="1e904-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="1e904-122">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md) オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="1e904-122">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="1e904-123">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="1e904-123">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="1e904-124">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="1e904-124">Set the ResultText property.</span></span>

## <span data-ttu-id="1e904-125">Members</span><span class="sxs-lookup"><span data-stu-id="1e904-125">Members</span></span>

#### <span data-ttu-id="1e904-126">Accept</span><span class="sxs-lookup"><span data-stu-id="1e904-126">Accept</span></span> 

<span data-ttu-id="1e904-127">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1e904-127">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="1e904-128">パブリック HRESULT [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="1e904-128">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="1e904-129">これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1e904-129">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="1e904-130">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="1e904-130">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="1e904-131">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="1e904-131">get_DefaultText</span></span> 

<span data-ttu-id="1e904-132">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="1e904-132">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="1e904-133">パブリック HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaulttext)</span><span class="sxs-lookup"><span data-stu-id="1e904-133">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="1e904-134">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="1e904-134">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="1e904-135">get_Kind</span><span class="sxs-lookup"><span data-stu-id="1e904-135">get_Kind</span></span> 

<span data-ttu-id="1e904-136">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="1e904-136">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="1e904-137">パブリック HRESULT [get_Kind](#get_kind)(COREWEBVIEW2_SCRIPT_DIALOG_KIND \* Kind)</span><span class="sxs-lookup"><span data-stu-id="1e904-137">public HRESULT [get_Kind](#get_kind)(COREWEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

<span data-ttu-id="1e904-138">[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1e904-138">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="1e904-139">get_Message</span><span class="sxs-lookup"><span data-stu-id="1e904-139">get_Message</span></span> 

<span data-ttu-id="1e904-140">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="1e904-140">The message of the dialog box.</span></span>

> <span data-ttu-id="1e904-141">パブリック HRESULT [get_Message](#get_message)(LPWSTR \* Message)</span><span class="sxs-lookup"><span data-stu-id="1e904-141">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="1e904-142">JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。</span><span class="sxs-lookup"><span data-stu-id="1e904-142">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="1e904-143">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="1e904-143">get_ResultText</span></span> 

<span data-ttu-id="1e904-144">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="1e904-144">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="1e904-145">パブリック HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resulttext)</span><span class="sxs-lookup"><span data-stu-id="1e904-145">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="1e904-146">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="1e904-146">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="1e904-147">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="1e904-147">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="1e904-148">get_Uri</span><span class="sxs-lookup"><span data-stu-id="1e904-148">get_Uri</span></span> 

<span data-ttu-id="1e904-149">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="1e904-149">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="1e904-150">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="1e904-150">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="1e904-151">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="1e904-151">GetDeferral</span></span> 

<span data-ttu-id="1e904-152">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md) オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="1e904-152">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="1e904-153">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="1e904-153">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="1e904-154">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e904-154">You can use this to complete the event at a later time.</span></span>

#### <span data-ttu-id="1e904-155">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="1e904-155">put_ResultText</span></span> 

<span data-ttu-id="1e904-156">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="1e904-156">Set the ResultText property.</span></span>

> <span data-ttu-id="1e904-157">パブリック HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resulttext)</span><span class="sxs-lookup"><span data-stu-id="1e904-157">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>
