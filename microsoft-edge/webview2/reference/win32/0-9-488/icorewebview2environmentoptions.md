---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2EnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 1cac030b27164222bd1c11240cf4a92aee91ff01
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880676"
---
# <span data-ttu-id="329e4-104">0.9.515-インターフェイス ICoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="329e4-104">0.9.515 - interface ICoreWebView2EnvironmentOptions</span></span> 

> [!NOTE]
> <span data-ttu-id="329e4-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="329e4-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="329e4-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="329e4-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2EnvironmentOptions
  : public IUnknown
```

<span data-ttu-id="329e4-107">WebView2 環境の作成に使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="329e4-107">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="329e4-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="329e4-108">Summary</span></span>

 <span data-ttu-id="329e4-109">Members</span><span class="sxs-lookup"><span data-stu-id="329e4-109">Members</span></span>                        | <span data-ttu-id="329e4-110">説明</span><span class="sxs-lookup"><span data-stu-id="329e4-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="329e4-111">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="329e4-111">get_AdditionalBrowserArguments</span></span>](#get_additionalbrowserarguments) | <span data-ttu-id="329e4-112">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="329e4-112">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="329e4-113">get_Language</span><span class="sxs-lookup"><span data-stu-id="329e4-113">get_Language</span></span>](#get_language) | <span data-ttu-id="329e4-114">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="329e4-114">The default language that WebView will run with.</span></span>
[<span data-ttu-id="329e4-115">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="329e4-115">get_TargetCompatibleBrowserVersion</span></span>](#get_targetcompatiblebrowserversion) | <span data-ttu-id="329e4-116">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="329e4-116">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="329e4-117">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="329e4-117">put_AdditionalBrowserArguments</span></span>](#put_additionalbrowserarguments) | <span data-ttu-id="329e4-118">AdditionalBrowserArguments プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="329e4-118">Set the AdditionalBrowserArguments property.</span></span>
[<span data-ttu-id="329e4-119">put_Language</span><span class="sxs-lookup"><span data-stu-id="329e4-119">put_Language</span></span>](#put_language) | <span data-ttu-id="329e4-120">Language プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="329e4-120">Set the Language property.</span></span>
[<span data-ttu-id="329e4-121">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="329e4-121">put_TargetCompatibleBrowserVersion</span></span>](#put_targetcompatiblebrowserversion) | <span data-ttu-id="329e4-122">Target互換の Sion を設定します。</span><span class="sxs-lookup"><span data-stu-id="329e4-122">Set the TargetCompatibleBrowserVersion.</span></span>

<span data-ttu-id="329e4-123">WebView2EnvironmentOptions には既定の実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="329e4-123">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

```cpp
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    if(!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
```

## <span data-ttu-id="329e4-124">Members</span><span class="sxs-lookup"><span data-stu-id="329e4-124">Members</span></span>

#### <span data-ttu-id="329e4-125">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="329e4-125">get_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="329e4-126">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="329e4-126">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="329e4-127">パブリック HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR \* 値)</span><span class="sxs-lookup"><span data-stu-id="329e4-127">public HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR \* value)</span></span>

<span data-ttu-id="329e4-128">これらは、コマンドラインの一部としてブラウザープロセスに渡されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-128">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="329e4-129">ブラウザプロセスへのコマンドラインスイッチの詳細については、「[フラグを使って Chromium を実行](https://aka.ms/RunChromiumWithFlags)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="329e4-129">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="329e4-130">コマンドラインスイッチを使用してアプリを起動すると、 `--edge-webview-switches=xxx` そのスイッチの値 (上の例では xxx) もブラウザープロセスのコマンドラインに追加されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-130">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="329e4-131">次のような一部 `--user-data-dir` のスイッチは、WebView として内部的で重要です。</span><span class="sxs-lookup"><span data-stu-id="329e4-131">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="329e4-132">これらのスイッチは、指定した場合でも無視されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-132">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="329e4-133">同じスイッチが複数回指定されている場合は、最後のスイッチが優先されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-133">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="329e4-134">無効および有効な機能を除き、同じスイッチの異なる値をマージしようとすることはありません。</span><span class="sxs-lookup"><span data-stu-id="329e4-134">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="329e4-135">およびで指定された機能は、 `--enable-features` `--disable-features` 単純なロジックにマージされます。これらの機能は、指定された機能と組み込み機能の和集合であり、機能が無効になっている場合は、[有効な機能] の一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-135">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="329e4-136">アプリプロセスのコマンドライン `--edge-webview-switches` 値は、additionalBrowserArguments パラメーターが処理された後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-136">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="329e4-137">一部の機能は内部で無効にされているため、有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="329e4-137">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="329e4-138">指定したスイッチの解析に失敗した場合、それらは無視されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-138">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="329e4-139">既定では、追加のフラグなしでブラウザープロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="329e4-139">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="329e4-140">get_Language</span><span class="sxs-lookup"><span data-stu-id="329e4-140">get_Language</span></span> 

<span data-ttu-id="329e4-141">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="329e4-141">The default language that WebView will run with.</span></span>

> <span data-ttu-id="329e4-142">パブリック HRESULT [get_Language](#get_language)(LPWSTR \* 値)</span><span class="sxs-lookup"><span data-stu-id="329e4-142">public HRESULT [get_Language](#get_language)(LPWSTR \* value)</span></span>

<span data-ttu-id="329e4-143">これは、コンテキストメニューやダイアログなどのブラウザー Ui に適用されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-143">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="329e4-144">また、WebView が web サイトに送信する受け入れ言語の HTTP ヘッダーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-144">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="329e4-145">この形式は、 `language[-country]` `language` iso 639 の2文字コードであり、 `country` iso 3166 の2文字のコードです。</span><span class="sxs-lookup"><span data-stu-id="329e4-145">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="329e4-146">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="329e4-146">get_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="329e4-147">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="329e4-147">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="329e4-148">パブリック HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR \* 値)</span><span class="sxs-lookup"><span data-stu-id="329e4-148">public HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR \* value)</span></span>

<span data-ttu-id="329e4-149">これは、アプリケーションで使用されている SDK のバージョンと対応する Edge WebView2 ランタイムバージョンに既定値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="329e4-149">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="329e4-150">この値の形式は、"この値" と "他の型 Serversion" の値の形式と同じです。</span><span class="sxs-lookup"><span data-stu-id="329e4-150">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="329e4-151">対象となるのは、のバージョン部分だけです。</span><span class="sxs-lookup"><span data-stu-id="329e4-151">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="329e4-152">チャネルのサフィックス (存在する場合) は無視されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-152">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="329e4-153">実際に使用されている Edge WebView2 ランタイムバイナリのバージョンは、指定された Target互換のバージョンとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="329e4-153">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="329e4-154">互換性が保証されるだけであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="329e4-154">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="329e4-155">ICoreWebView2Environment の参照サーバーの文字列プロパティで実際のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="329e4-155">You can check the actual version on the BrowserVersionString property on the ICoreWebView2Environment.</span></span>

#### <span data-ttu-id="329e4-156">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="329e4-156">put_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="329e4-157">AdditionalBrowserArguments プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="329e4-157">Set the AdditionalBrowserArguments property.</span></span>

> <span data-ttu-id="329e4-158">パブリック HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR 値)</span><span class="sxs-lookup"><span data-stu-id="329e4-158">public HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR value)</span></span>

#### <span data-ttu-id="329e4-159">put_Language</span><span class="sxs-lookup"><span data-stu-id="329e4-159">put_Language</span></span> 

<span data-ttu-id="329e4-160">Language プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="329e4-160">Set the Language property.</span></span>

> <span data-ttu-id="329e4-161">パブリック HRESULT [put_Language](#put_language)(LPCWSTR 値)</span><span class="sxs-lookup"><span data-stu-id="329e4-161">public HRESULT [put_Language](#put_language)(LPCWSTR value)</span></span>

#### <span data-ttu-id="329e4-162">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="329e4-162">put_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="329e4-163">Target互換の Sion を設定します。</span><span class="sxs-lookup"><span data-stu-id="329e4-163">Set the TargetCompatibleBrowserVersion.</span></span>

> <span data-ttu-id="329e4-164">パブリック HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR 値)</span><span class="sxs-lookup"><span data-stu-id="329e4-164">public HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR value)</span></span>

