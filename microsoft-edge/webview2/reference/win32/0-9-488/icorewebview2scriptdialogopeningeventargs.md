---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: a0372e9319a3dd260092b8bc96c693976b7f1fec
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880321"
---
# <span data-ttu-id="4af62-104">0.9.515-インターフェイス ICoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="4af62-104">0.9.515 - interface ICoreWebView2ScriptDialogOpeningEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="4af62-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4af62-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="4af62-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af62-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="4af62-107">Scriptな開始イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="4af62-107">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="4af62-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="4af62-108">Summary</span></span>

 <span data-ttu-id="4af62-109">Members</span><span class="sxs-lookup"><span data-stu-id="4af62-109">Members</span></span>                        | <span data-ttu-id="4af62-110">説明</span><span class="sxs-lookup"><span data-stu-id="4af62-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4af62-111">Accept</span><span class="sxs-lookup"><span data-stu-id="4af62-111">Accept</span></span>](#accept) | <span data-ttu-id="4af62-112">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="4af62-112">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="4af62-113">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="4af62-113">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="4af62-114">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4af62-114">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="4af62-115">get_Kind</span><span class="sxs-lookup"><span data-stu-id="4af62-115">get_Kind</span></span>](#get_kind) | <span data-ttu-id="4af62-116">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="4af62-116">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="4af62-117">get_Message</span><span class="sxs-lookup"><span data-stu-id="4af62-117">get_Message</span></span>](#get_message) | <span data-ttu-id="4af62-118">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4af62-118">The message of the dialog box.</span></span>
[<span data-ttu-id="4af62-119">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="4af62-119">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="4af62-120">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="4af62-120">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="4af62-121">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4af62-121">get_Uri</span></span>](#get_uri) | <span data-ttu-id="4af62-122">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="4af62-122">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="4af62-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4af62-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="4af62-124">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="4af62-124">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="4af62-125">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="4af62-125">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="4af62-126">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4af62-126">Set the ResultText property.</span></span>

## <span data-ttu-id="4af62-127">Members</span><span class="sxs-lookup"><span data-stu-id="4af62-127">Members</span></span>

#### <span data-ttu-id="4af62-128">Accept</span><span class="sxs-lookup"><span data-stu-id="4af62-128">Accept</span></span> 

<span data-ttu-id="4af62-129">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="4af62-129">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="4af62-130">パブリック HRESULT [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="4af62-130">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="4af62-131">これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4af62-131">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="4af62-132">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="4af62-132">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="4af62-133">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="4af62-133">get_DefaultText</span></span> 

<span data-ttu-id="4af62-134">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4af62-134">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="4af62-135">パブリック HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaulttext)</span><span class="sxs-lookup"><span data-stu-id="4af62-135">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="4af62-136">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="4af62-136">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="4af62-137">get_Kind</span><span class="sxs-lookup"><span data-stu-id="4af62-137">get_Kind</span></span> 

<span data-ttu-id="4af62-138">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="4af62-138">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="4af62-139">パブリック HRESULT [get_Kind](#get_kind)(COREWEBVIEW2_SCRIPT_DIALOG_KIND \* Kind)</span><span class="sxs-lookup"><span data-stu-id="4af62-139">public HRESULT [get_Kind](#get_kind)(COREWEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

<span data-ttu-id="4af62-140">[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4af62-140">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="4af62-141">get_Message</span><span class="sxs-lookup"><span data-stu-id="4af62-141">get_Message</span></span> 

<span data-ttu-id="4af62-142">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4af62-142">The message of the dialog box.</span></span>

> <span data-ttu-id="4af62-143">パブリック HRESULT [get_Message](#get_message)(LPWSTR \* Message)</span><span class="sxs-lookup"><span data-stu-id="4af62-143">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="4af62-144">JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。</span><span class="sxs-lookup"><span data-stu-id="4af62-144">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="4af62-145">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="4af62-145">get_ResultText</span></span> 

<span data-ttu-id="4af62-146">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="4af62-146">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="4af62-147">パブリック HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resulttext)</span><span class="sxs-lookup"><span data-stu-id="4af62-147">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="4af62-148">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="4af62-148">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="4af62-149">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="4af62-149">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="4af62-150">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4af62-150">get_Uri</span></span> 

<span data-ttu-id="4af62-151">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="4af62-151">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="4af62-152">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="4af62-152">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="4af62-153">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4af62-153">GetDeferral</span></span> 

<span data-ttu-id="4af62-154">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="4af62-154">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="4af62-155">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="4af62-155">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="4af62-156">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="4af62-156">You can use this to complete the event at a later time.</span></span>

#### <span data-ttu-id="4af62-157">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="4af62-157">put_ResultText</span></span> 

<span data-ttu-id="4af62-158">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4af62-158">Set the ResultText property.</span></span>

> <span data-ttu-id="4af62-159">パブリック HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resulttext)</span><span class="sxs-lookup"><span data-stu-id="4af62-159">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

