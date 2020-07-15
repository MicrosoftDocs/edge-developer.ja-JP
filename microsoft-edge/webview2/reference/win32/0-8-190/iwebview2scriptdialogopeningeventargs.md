---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 052f380caadf08814cc9364f3ccfbb5251fa7c7e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878198"
---
# <span data-ttu-id="98b03-104">0.8.355-インターフェイス IWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="98b03-104">0.8.355 - interface IWebView2ScriptDialogOpeningEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="98b03-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98b03-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="98b03-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98b03-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="98b03-107">[IWebView2WebView:: add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening)イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="98b03-107">Event args for the [IWebView2WebView::add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening) event.</span></span>

## <span data-ttu-id="98b03-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="98b03-108">Summary</span></span>

 <span data-ttu-id="98b03-109">Members</span><span class="sxs-lookup"><span data-stu-id="98b03-109">Members</span></span>                        | <span data-ttu-id="98b03-110">説明</span><span class="sxs-lookup"><span data-stu-id="98b03-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="98b03-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="98b03-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="98b03-112">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="98b03-112">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="98b03-113">get_Kind</span><span class="sxs-lookup"><span data-stu-id="98b03-113">get_Kind</span></span>](#get_kind) | <span data-ttu-id="98b03-114">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="98b03-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="98b03-115">get_Message</span><span class="sxs-lookup"><span data-stu-id="98b03-115">get_Message</span></span>](#get_message) | <span data-ttu-id="98b03-116">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="98b03-116">The message of the dialog box.</span></span>
[<span data-ttu-id="98b03-117">Accept</span><span class="sxs-lookup"><span data-stu-id="98b03-117">Accept</span></span>](#accept) | <span data-ttu-id="98b03-118">このメソッドを呼び出すことで、[OK] をクリックして確認とプロンプトを表示することができます。また、このメソッドを呼び出してキャンセルを示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="98b03-118">The host may call this to respond with OK to confirm and prompt dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="98b03-119">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="98b03-119">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="98b03-120">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="98b03-120">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="98b03-121">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="98b03-121">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="98b03-122">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="98b03-122">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="98b03-123">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="98b03-123">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="98b03-124">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="98b03-124">Set the ResultText property.</span></span>
[<span data-ttu-id="98b03-125">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="98b03-125">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="98b03-126">GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="98b03-126">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="98b03-127">Members</span><span class="sxs-lookup"><span data-stu-id="98b03-127">Members</span></span>

#### <span data-ttu-id="98b03-128">get_Uri</span><span class="sxs-lookup"><span data-stu-id="98b03-128">get_Uri</span></span> 

<span data-ttu-id="98b03-129">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="98b03-129">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="98b03-130">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="98b03-130">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="98b03-131">get_Kind</span><span class="sxs-lookup"><span data-stu-id="98b03-131">get_Kind</span></span> 

<span data-ttu-id="98b03-132">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="98b03-132">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="98b03-133">パブリック HRESULT [get_Kind](#get_kind)(WEBVIEW2_SCRIPT_DIALOG_KIND \* Kind)</span><span class="sxs-lookup"><span data-stu-id="98b03-133">public HRESULT [get_Kind](#get_kind)(WEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

#### <span data-ttu-id="98b03-134">get_Message</span><span class="sxs-lookup"><span data-stu-id="98b03-134">get_Message</span></span> 

<span data-ttu-id="98b03-135">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="98b03-135">The message of the dialog box.</span></span>

> <span data-ttu-id="98b03-136">パブリック HRESULT [get_Message](#get_message)(LPWSTR \* Message)</span><span class="sxs-lookup"><span data-stu-id="98b03-136">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="98b03-137">JavaScript から、警告、確認、プロンプトに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="98b03-137">From JavaScript this is the first parameter passed to alert, confirm, and prompt.</span></span>

#### <span data-ttu-id="98b03-138">Accept</span><span class="sxs-lookup"><span data-stu-id="98b03-138">Accept</span></span> 

<span data-ttu-id="98b03-139">このメソッドを呼び出すことで、[OK] をクリックして確認とプロンプトを表示することができます。また、このメソッドを呼び出してキャンセルを示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="98b03-139">The host may call this to respond with OK to confirm and prompt dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="98b03-140">パブリック HRESULT [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="98b03-140">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="98b03-141">JavaScript からは、Accept 関数が呼び出された場合に true が返されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="98b03-141">From JavaScript this means that the confirm function returns true if Accept is called.</span></span> <span data-ttu-id="98b03-142">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="98b03-142">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="98b03-143">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="98b03-143">get_DefaultText</span></span> 

<span data-ttu-id="98b03-144">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="98b03-144">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="98b03-145">パブリック HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaulttext)</span><span class="sxs-lookup"><span data-stu-id="98b03-145">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="98b03-146">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="98b03-146">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="98b03-147">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="98b03-147">get_ResultText</span></span> 

<span data-ttu-id="98b03-148">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="98b03-148">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="98b03-149">パブリック HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resulttext)</span><span class="sxs-lookup"><span data-stu-id="98b03-149">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="98b03-150">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="98b03-150">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="98b03-151">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="98b03-151">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="98b03-152">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="98b03-152">put_ResultText</span></span> 

<span data-ttu-id="98b03-153">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="98b03-153">Set the ResultText property.</span></span>

> <span data-ttu-id="98b03-154">パブリック HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resulttext)</span><span class="sxs-lookup"><span data-stu-id="98b03-154">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

#### <span data-ttu-id="98b03-155">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="98b03-155">GetDeferral</span></span> 

<span data-ttu-id="98b03-156">GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="98b03-156">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="98b03-157">パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="98b03-157">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="98b03-158">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="98b03-158">You can use this to complete the event at a later time.</span></span>

