---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0. WebView2 Win32 C++ IWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: de8c8cc2c6c6f857a2889ad167061d2834c30c02
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885794"
---
# <span data-ttu-id="3a76d-104">0.8.355-インターフェイス IWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="3a76d-104">0.8.355 - interface IWebView2ScriptDialogOpeningEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="3a76d-105">[IWebView2WebView:: add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening)イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="3a76d-105">Event args for the [IWebView2WebView::add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening) event.</span></span>

## <span data-ttu-id="3a76d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3a76d-106">Summary</span></span>

 <span data-ttu-id="3a76d-107">Members</span><span class="sxs-lookup"><span data-stu-id="3a76d-107">Members</span></span>                        | <span data-ttu-id="3a76d-108">説明</span><span class="sxs-lookup"><span data-stu-id="3a76d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3a76d-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="3a76d-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="3a76d-110">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="3a76d-110">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="3a76d-111">get_Kind</span><span class="sxs-lookup"><span data-stu-id="3a76d-111">get_Kind</span></span>](#get_kind) | <span data-ttu-id="3a76d-112">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="3a76d-112">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="3a76d-113">get_Message</span><span class="sxs-lookup"><span data-stu-id="3a76d-113">get_Message</span></span>](#get_message) | <span data-ttu-id="3a76d-114">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="3a76d-114">The message of the dialog box.</span></span>
[<span data-ttu-id="3a76d-115">Accept</span><span class="sxs-lookup"><span data-stu-id="3a76d-115">Accept</span></span>](#accept) | <span data-ttu-id="3a76d-116">このメソッドを呼び出すことで、[OK] をクリックして確認とプロンプトを表示することができます。また、このメソッドを呼び出してキャンセルを示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="3a76d-116">The host may call this to respond with OK to confirm and prompt dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="3a76d-117">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="3a76d-117">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="3a76d-118">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="3a76d-118">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="3a76d-119">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="3a76d-119">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="3a76d-120">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="3a76d-120">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="3a76d-121">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="3a76d-121">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="3a76d-122">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3a76d-122">Set the ResultText property.</span></span>
[<span data-ttu-id="3a76d-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="3a76d-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="3a76d-124">GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3a76d-124">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="3a76d-125">Members</span><span class="sxs-lookup"><span data-stu-id="3a76d-125">Members</span></span>

#### <span data-ttu-id="3a76d-126">get_Uri</span><span class="sxs-lookup"><span data-stu-id="3a76d-126">get_Uri</span></span> 

<span data-ttu-id="3a76d-127">ダイアログボックスを要求したページの URI。</span><span class="sxs-lookup"><span data-stu-id="3a76d-127">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="3a76d-128">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="3a76d-128">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="3a76d-129">get_Kind</span><span class="sxs-lookup"><span data-stu-id="3a76d-129">get_Kind</span></span> 

<span data-ttu-id="3a76d-130">JavaScript ダイアログボックスの種類。</span><span class="sxs-lookup"><span data-stu-id="3a76d-130">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="3a76d-131">パブリック HRESULT [get_Kind](#get_kind)(WEBVIEW2_SCRIPT_DIALOG_KIND \* Kind)</span><span class="sxs-lookup"><span data-stu-id="3a76d-131">public HRESULT [get_Kind](#get_kind)(WEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

#### <span data-ttu-id="3a76d-132">get_Message</span><span class="sxs-lookup"><span data-stu-id="3a76d-132">get_Message</span></span> 

<span data-ttu-id="3a76d-133">ダイアログボックスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="3a76d-133">The message of the dialog box.</span></span>

> <span data-ttu-id="3a76d-134">パブリック HRESULT [get_Message](#get_message)(LPWSTR \* Message)</span><span class="sxs-lookup"><span data-stu-id="3a76d-134">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="3a76d-135">JavaScript から、警告、確認、プロンプトに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="3a76d-135">From JavaScript this is the first parameter passed to alert, confirm, and prompt.</span></span>

#### <span data-ttu-id="3a76d-136">Accept</span><span class="sxs-lookup"><span data-stu-id="3a76d-136">Accept</span></span> 

<span data-ttu-id="3a76d-137">このメソッドを呼び出すことで、[OK] をクリックして確認とプロンプトを表示することができます。また、このメソッドを呼び出してキャンセルを示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="3a76d-137">The host may call this to respond with OK to confirm and prompt dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="3a76d-138">パブリック HRESULT [Accept](#accept)()</span><span class="sxs-lookup"><span data-stu-id="3a76d-138">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="3a76d-139">JavaScript からは、Accept 関数が呼び出された場合に true が返されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3a76d-139">From JavaScript this means that the confirm function returns true if Accept is called.</span></span> <span data-ttu-id="3a76d-140">Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="3a76d-140">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="3a76d-141">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="3a76d-141">get_DefaultText</span></span> 

<span data-ttu-id="3a76d-142">JavaScript のプロンプトダイアログに渡された2番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="3a76d-142">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="3a76d-143">パブリック HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaulttext)</span><span class="sxs-lookup"><span data-stu-id="3a76d-143">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="3a76d-144">これは、プロンプト JavaScript 関数の結果として使用される既定値です。</span><span class="sxs-lookup"><span data-stu-id="3a76d-144">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="3a76d-145">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="3a76d-145">get_ResultText</span></span> 

<span data-ttu-id="3a76d-146">Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。</span><span class="sxs-lookup"><span data-stu-id="3a76d-146">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="3a76d-147">パブリック HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resulttext)</span><span class="sxs-lookup"><span data-stu-id="3a76d-147">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="3a76d-148">ダイアログ以外のダイアログでは、このメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="3a76d-148">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="3a76d-149">Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="3a76d-149">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="3a76d-150">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="3a76d-150">put_ResultText</span></span> 

<span data-ttu-id="3a76d-151">ResultText プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3a76d-151">Set the ResultText property.</span></span>

> <span data-ttu-id="3a76d-152">パブリック HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resulttext)</span><span class="sxs-lookup"><span data-stu-id="3a76d-152">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

#### <span data-ttu-id="3a76d-153">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="3a76d-153">GetDeferral</span></span> 

<span data-ttu-id="3a76d-154">GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3a76d-154">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="3a76d-155">パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="3a76d-155">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="3a76d-156">これは、後でイベントを完了するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a76d-156">You can use this to complete the event at a later time.</span></span>

