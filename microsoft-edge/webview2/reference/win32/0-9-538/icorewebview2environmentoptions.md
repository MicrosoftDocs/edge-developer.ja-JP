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
ms.openlocfilehash: 3de9cd454f693179a0d1dc63e6ccb1332f80c875
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698996"
---
# <span data-ttu-id="5aafb-104">インターフェイス ICoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="5aafb-104">interface ICoreWebView2EnvironmentOptions</span></span> 

```
interface ICoreWebView2EnvironmentOptions
  : public IUnknown
```

<span data-ttu-id="5aafb-105">WebView2 環境の作成に使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="5aafb-105">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="5aafb-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="5aafb-106">Summary</span></span>

 <span data-ttu-id="5aafb-107">Members</span><span class="sxs-lookup"><span data-stu-id="5aafb-107">Members</span></span>                        | <span data-ttu-id="5aafb-108">説明</span><span class="sxs-lookup"><span data-stu-id="5aafb-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5aafb-109">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="5aafb-109">get_AdditionalBrowserArguments</span></span>](#get_additionalbrowserarguments) | <span data-ttu-id="5aafb-110">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-110">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="5aafb-111">get_Language</span><span class="sxs-lookup"><span data-stu-id="5aafb-111">get_Language</span></span>](#get_language) | <span data-ttu-id="5aafb-112">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="5aafb-112">The default language that WebView will run with.</span></span>
[<span data-ttu-id="5aafb-113">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="5aafb-113">get_TargetCompatibleBrowserVersion</span></span>](#get_targetcompatiblebrowserversion) | <span data-ttu-id="5aafb-114">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aafb-114">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="5aafb-115">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="5aafb-115">put_AdditionalBrowserArguments</span></span>](#put_additionalbrowserarguments) | <span data-ttu-id="5aafb-116">AdditionalBrowserArguments プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5aafb-116">Set the AdditionalBrowserArguments property.</span></span>
[<span data-ttu-id="5aafb-117">put_Language</span><span class="sxs-lookup"><span data-stu-id="5aafb-117">put_Language</span></span>](#put_language) | <span data-ttu-id="5aafb-118">Language プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5aafb-118">Set the Language property.</span></span>
[<span data-ttu-id="5aafb-119">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="5aafb-119">put_TargetCompatibleBrowserVersion</span></span>](#put_targetcompatiblebrowserversion) | <span data-ttu-id="5aafb-120">Target互換の Sion を設定します。</span><span class="sxs-lookup"><span data-stu-id="5aafb-120">Set the TargetCompatibleBrowserVersion.</span></span>

<span data-ttu-id="5aafb-121">WebView2EnvironmentOptions には既定の実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5aafb-121">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

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

## <span data-ttu-id="5aafb-122">Members</span><span class="sxs-lookup"><span data-stu-id="5aafb-122">Members</span></span>

#### <span data-ttu-id="5aafb-123">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="5aafb-123">get_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="5aafb-124">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-124">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="5aafb-125">パブリック HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR \* 値)</span><span class="sxs-lookup"><span data-stu-id="5aafb-125">public HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR \* value)</span></span>

<span data-ttu-id="5aafb-126">これらは、コマンドラインの一部としてブラウザープロセスに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-126">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="5aafb-127">ブラウザプロセスへのコマンドラインスイッチの詳細については、「[フラグを使って Chromium を実行](https://aka.ms/RunChromiumWithFlags)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aafb-127">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="5aafb-128">コマンドラインスイッチを使用してアプリを起動すると、 `--edge-webview-switches=xxx` そのスイッチの値 (上の例では xxx) もブラウザープロセスのコマンドラインに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-128">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="5aafb-129">次のような一部 `--user-data-dir` のスイッチは、WebView として内部的で重要です。</span><span class="sxs-lookup"><span data-stu-id="5aafb-129">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="5aafb-130">これらのスイッチは、指定した場合でも無視されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-130">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="5aafb-131">同じスイッチが複数回指定されている場合は、最後のスイッチが優先されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-131">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="5aafb-132">無効および有効な機能を除き、同じスイッチの異なる値をマージしようとすることはありません。</span><span class="sxs-lookup"><span data-stu-id="5aafb-132">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="5aafb-133">およびで指定された機能は、 `--enable-features` `--disable-features` 単純なロジックにマージされます。これらの機能は、指定された機能と組み込み機能の和集合であり、機能が無効になっている場合は、[有効な機能] の一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-133">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="5aafb-134">アプリプロセスのコマンドライン `--edge-webview-switches` 値は、additionalBrowserArguments パラメーターが処理された後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-134">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="5aafb-135">一部の機能は内部で無効にされているため、有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5aafb-135">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="5aafb-136">指定したスイッチの解析に失敗した場合、それらは無視されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-136">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="5aafb-137">既定では、追加のフラグなしでブラウザープロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="5aafb-137">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="5aafb-138">get_Language</span><span class="sxs-lookup"><span data-stu-id="5aafb-138">get_Language</span></span> 

<span data-ttu-id="5aafb-139">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="5aafb-139">The default language that WebView will run with.</span></span>

> <span data-ttu-id="5aafb-140">パブリック HRESULT [get_Language](#get_language)(LPWSTR \* 値)</span><span class="sxs-lookup"><span data-stu-id="5aafb-140">public HRESULT [get_Language](#get_language)(LPWSTR \* value)</span></span>

<span data-ttu-id="5aafb-141">これは、コンテキストメニューやダイアログなどのブラウザー Ui に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-141">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="5aafb-142">また、WebView が web サイトに送信する受け入れ言語の HTTP ヘッダーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-142">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="5aafb-143">この形式は、 `language[-country]` `language` iso 639 の2文字コードであり、 `country` iso 3166 の2文字のコードです。</span><span class="sxs-lookup"><span data-stu-id="5aafb-143">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="5aafb-144">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="5aafb-144">get_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="5aafb-145">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aafb-145">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="5aafb-146">パブリック HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR \* 値)</span><span class="sxs-lookup"><span data-stu-id="5aafb-146">public HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR \* value)</span></span>

<span data-ttu-id="5aafb-147">これは、アプリケーションで使用されている SDK のバージョンと対応する Edge WebView2 ランタイムバージョンに既定値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="5aafb-147">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="5aafb-148">この値の形式は、"この値" と "他の型 Serversion" の値の形式と同じです。</span><span class="sxs-lookup"><span data-stu-id="5aafb-148">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="5aafb-149">対象となるのは、のバージョン部分だけです。</span><span class="sxs-lookup"><span data-stu-id="5aafb-149">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="5aafb-150">チャネルのサフィックス (存在する場合) は無視されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-150">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="5aafb-151">実際に使用されている Edge WebView2 ランタイムバイナリのバージョンは、指定された Target互換のバージョンとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5aafb-151">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="5aafb-152">互換性が保証されるだけであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-152">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="5aafb-153">ICoreWebView2Environment の参照サーバーの文字列プロパティで実際のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5aafb-153">You can check the actual version on the BrowserVersionString property on the ICoreWebView2Environment.</span></span>

#### <span data-ttu-id="5aafb-154">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="5aafb-154">put_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="5aafb-155">AdditionalBrowserArguments プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5aafb-155">Set the AdditionalBrowserArguments property.</span></span>

> <span data-ttu-id="5aafb-156">パブリック HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR 値)</span><span class="sxs-lookup"><span data-stu-id="5aafb-156">public HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR value)</span></span>

#### <span data-ttu-id="5aafb-157">put_Language</span><span class="sxs-lookup"><span data-stu-id="5aafb-157">put_Language</span></span> 

<span data-ttu-id="5aafb-158">Language プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5aafb-158">Set the Language property.</span></span>

> <span data-ttu-id="5aafb-159">パブリック HRESULT [put_Language](#put_language)(LPCWSTR 値)</span><span class="sxs-lookup"><span data-stu-id="5aafb-159">public HRESULT [put_Language](#put_language)(LPCWSTR value)</span></span>

#### <span data-ttu-id="5aafb-160">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="5aafb-160">put_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="5aafb-161">Target互換の Sion を設定します。</span><span class="sxs-lookup"><span data-stu-id="5aafb-161">Set the TargetCompatibleBrowserVersion.</span></span>

> <span data-ttu-id="5aafb-162">パブリック HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR 値)</span><span class="sxs-lookup"><span data-stu-id="5aafb-162">public HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR value)</span></span>
