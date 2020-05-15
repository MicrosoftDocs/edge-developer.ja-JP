---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 8ed1a10a65a07fc359deea18b8aadd4df3a7b055
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654595"
---
# <span data-ttu-id="8a08a-104">インターフェイス ICoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="8a08a-104">interface ICoreWebView2ScriptDialogOpeningEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="8a08a-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a08a-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="8a08a-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a08a-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="8a08a-107">Scriptな開始イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="8a08a-107">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="8a08a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8a08a-108">Summary</span></span>

 <span data-ttu-id="8a08a-109">Members</span><span class="sxs-lookup"><span data-stu-id="8a08a-109">Members</span></span>                        | <span data-ttu-id="8a08a-110">説明</span><span class="sxs-lookup"><span data-stu-id="8a08a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8a08a-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="8a08a-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="8a08a-112">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="8a08a-112">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="8a08a-113">get_Kind</span><span class="sxs-lookup"><span data-stu-id="8a08a-113">get_Kind</span></span>](#get_kind) | <span data-ttu-id="8a08a-114">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="8a08a-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="8a08a-115">get_Message</span><span class="sxs-lookup"><span data-stu-id="8a08a-115">get_Message</span></span>](#get_message) | <span data-ttu-id="8a08a-116">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8a08a-116">The message of the dialog box.</span></span>
[<span data-ttu-id="8a08a-117">Accept</span><span class="sxs-lookup"><span data-stu-id="8a08a-117">Accept</span></span>](#accept) | <span data-ttu-id="8a08a-118">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8a08a-118">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="8a08a-119">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="8a08a-119">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="8a08a-120">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="8a08a-120">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="8a08a-121">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="8a08a-121">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="8a08a-122">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="8a08a-122">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="8a08a-123">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="8a08a-123">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="8a08a-124">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8a08a-124">Set the ResultText property.</span></span>
[<span data-ttu-id="8a08a-125">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8a08a-125">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="8a08a-126">GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8a08a-126">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="8a08a-127">Members</span><span class="sxs-lookup"><span data-stu-id="8a08a-127">Members</span></span>

#### <span data-ttu-id="8a08a-128">get_Uri</span><span class="sxs-lookup"><span data-stu-id="8a08a-128">get_Uri</span></span> 

<span data-ttu-id="8a08a-129">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="8a08a-129">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="8a08a-130">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="8a08a-130">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="8a08a-131">get_Kind</span><span class="sxs-lookup"><span data-stu-id="8a08a-131">get_Kind</span></span> 

<span data-ttu-id="8a08a-132">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="8a08a-132">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="8a08a-133">パブリック HRESULT [get_Kind](#get_kind)(CORE_WEBVIEW2_SCRIPT_DIALOG_KIND \* Kind)</span><span class="sxs-lookup"><span data-stu-id="8a08a-133">public HRESULT [get_Kind](#get_kind)(CORE_WEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

<span data-ttu-id="8a08a-134">[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8a08a-134">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="8a08a-135">get_Message</span><span class="sxs-lookup"><span data-stu-id="8a08a-135">get_Message</span></span> 

<span data-ttu-id="8a08a-136">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8a08a-136">The message of the dialog box.</span></span>

> <span data-ttu-id="8a08a-137">パブリック HRESULT [get_Message](#get_message)(LPWSTR \* Message)</span><span class="sxs-lookup"><span data-stu-id="8a08a-137">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="8a08a-138">JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。</span><span class="sxs-lookup"><span data-stu-id="8a08a-138">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="8a08a-139">Accept</span><span class="sxs-lookup"><span data-stu-id="8a08a-139">Accept</span></span> 

<span data-ttu-id="8a08a-140">このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8a08a-140">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="8a08a-141">パブリック HRESULT [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="8a08a-141">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="8a08a-142">これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8a08a-142">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="8a08a-143">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="8a08a-143">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="8a08a-144">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="8a08a-144">get_DefaultText</span></span> 

<span data-ttu-id="8a08a-145">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="8a08a-145">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="8a08a-146">パブリック HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaulttext)</span><span class="sxs-lookup"><span data-stu-id="8a08a-146">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="8a08a-147">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="8a08a-147">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="8a08a-148">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="8a08a-148">get_ResultText</span></span> 

<span data-ttu-id="8a08a-149">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="8a08a-149">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="8a08a-150">パブリック HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resulttext)</span><span class="sxs-lookup"><span data-stu-id="8a08a-150">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="8a08a-151">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="8a08a-151">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="8a08a-152">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="8a08a-152">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="8a08a-153">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="8a08a-153">put_ResultText</span></span> 

<span data-ttu-id="8a08a-154">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8a08a-154">Set the ResultText property.</span></span>

> <span data-ttu-id="8a08a-155">パブリック HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resulttext)</span><span class="sxs-lookup"><span data-stu-id="8a08a-155">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

#### <span data-ttu-id="8a08a-156">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8a08a-156">GetDeferral</span></span> 

<span data-ttu-id="8a08a-157">GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8a08a-157">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="8a08a-158">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="8a08a-158">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="8a08a-159">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a08a-159">You can use this to complete the event at a later time.</span></span>

