---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2EnvironmentOptions の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e5b5392ef4b681f3aec3b7850f4ad9e2d9b595e8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877673"
---
# <span data-ttu-id="ef8b8-104">0.9.515 クラスの WebView2 クラス (CoreWebView2EnvironmentOptions)</span><span class="sxs-lookup"><span data-stu-id="ef8b8-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2EnvironmentOptions class</span></span> 

> [!NOTE]
> <span data-ttu-id="ef8b8-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="ef8b8-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="ef8b8-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="ef8b8-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="ef8b8-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="ef8b8-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="ef8b8-109">WebView2 環境の作成に使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-109">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="ef8b8-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="ef8b8-110">Summary</span></span>

 <span data-ttu-id="ef8b8-111">Members</span><span class="sxs-lookup"><span data-stu-id="ef8b8-111">Members</span></span>                        | <span data-ttu-id="ef8b8-112">説明</span><span class="sxs-lookup"><span data-stu-id="ef8b8-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ef8b8-113">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="ef8b8-113">AdditionalBrowserArguments</span></span>](#additionalbrowserarguments) | <span data-ttu-id="ef8b8-114">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-114">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="ef8b8-115">言語</span><span class="sxs-lookup"><span data-stu-id="ef8b8-115">Language</span></span>](#language) | <span data-ttu-id="ef8b8-116">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-116">The default language that WebView will run with.</span></span>
[<span data-ttu-id="ef8b8-117">Targetserversion</span><span class="sxs-lookup"><span data-stu-id="ef8b8-117">TargetCompatibleBrowserVersion</span></span>](#targetcompatiblebrowserversion) | <span data-ttu-id="ef8b8-118">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-118">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="ef8b8-119">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="ef8b8-119">CoreWebView2EnvironmentOptions</span></span>](#corewebview2environmentoptions) | <span data-ttu-id="ef8b8-120">CoreWebView2EnvironmentOptions クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-120">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

<span data-ttu-id="ef8b8-121">WebView2EnvironmentOptions には既定の実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-121">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

## <span data-ttu-id="ef8b8-122">Members</span><span class="sxs-lookup"><span data-stu-id="ef8b8-122">Members</span></span>

#### <span data-ttu-id="ef8b8-123">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="ef8b8-123">AdditionalBrowserArguments</span></span> 

<span data-ttu-id="ef8b8-124">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-124">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="ef8b8-125">パブリック文字列の[Additionalbrowserarguments](#additionalbrowserarguments)</span><span class="sxs-lookup"><span data-stu-id="ef8b8-125">public string [AdditionalBrowserArguments](#additionalbrowserarguments)</span></span>

<span data-ttu-id="ef8b8-126">これらは、コマンドラインの一部としてブラウザープロセスに渡されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-126">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="ef8b8-127">ブラウザプロセスへのコマンドラインスイッチの詳細については、「[フラグを使って Chromium を実行](https://aka.ms/RunChromiumWithFlags)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-127">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="ef8b8-128">コマンドラインスイッチを使用してアプリを起動すると、 `--edge-webview-switches=xxx` そのスイッチの値 (上の例では xxx) もブラウザープロセスのコマンドラインに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-128">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="ef8b8-129">次のような一部 `--user-data-dir` のスイッチは、WebView として内部的で重要です。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-129">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="ef8b8-130">これらのスイッチは、指定した場合でも無視されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-130">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="ef8b8-131">同じスイッチが複数回指定されている場合は、最後のスイッチが優先されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-131">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="ef8b8-132">無効および有効な機能を除き、同じスイッチの異なる値をマージしようとすることはありません。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-132">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="ef8b8-133">およびで指定された機能は、 `--enable-features` `--disable-features` 単純なロジックにマージされます。これらの機能は、指定された機能と組み込み機能の和集合であり、機能が無効になっている場合は、[有効な機能] の一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-133">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="ef8b8-134">アプリプロセスのコマンドライン `--edge-webview-switches` 値は、additionalBrowserArguments パラメーターが処理された後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-134">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="ef8b8-135">一部の機能は内部で無効にされているため、有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-135">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="ef8b8-136">指定したスイッチの解析に失敗した場合、それらは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-136">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="ef8b8-137">既定では、追加のフラグなしでブラウザープロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-137">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="ef8b8-138">言語</span><span class="sxs-lookup"><span data-stu-id="ef8b8-138">Language</span></span> 

<span data-ttu-id="ef8b8-139">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-139">The default language that WebView will run with.</span></span>

> <span data-ttu-id="ef8b8-140">公開文字列の[言語](#language)</span><span class="sxs-lookup"><span data-stu-id="ef8b8-140">public string [Language](#language)</span></span>

<span data-ttu-id="ef8b8-141">これは、コンテキストメニューやダイアログなどのブラウザー Ui に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-141">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="ef8b8-142">また、WebView が web サイトに送信する受け入れ言語の HTTP ヘッダーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-142">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="ef8b8-143">この形式は、 `language[-country]` `language` iso 639 の2文字コードであり、 `country` iso 3166 の2文字のコードです。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-143">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="ef8b8-144">Targetserversion</span><span class="sxs-lookup"><span data-stu-id="ef8b8-144">TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="ef8b8-145">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-145">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="ef8b8-146">パブリック文字列[ターゲット](#targetcompatiblebrowserversion)/セルの sion</span><span class="sxs-lookup"><span data-stu-id="ef8b8-146">public string [TargetCompatibleBrowserVersion](#targetcompatiblebrowserversion)</span></span>

<span data-ttu-id="ef8b8-147">これは、アプリケーションで使用されている SDK のバージョンと対応する Edge WebView2 ランタイムバージョンに既定値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-147">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="ef8b8-148">この値の形式は、"この値" と "他の型 Serversion" の値の形式と同じです。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-148">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="ef8b8-149">対象となるのは、のバージョン部分だけです。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-149">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="ef8b8-150">チャネルのサフィックス (存在する場合) は無視されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-150">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="ef8b8-151">実際に使用されている Edge WebView2 ランタイムバイナリのバージョンは、指定された Target互換のバージョンとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-151">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="ef8b8-152">互換性が保証されるだけであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-152">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="ef8b8-153">CoreWebView2Environment の参照サーバーの文字列プロパティで実際のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-153">You can check the actual version on the BrowserVersionString property on the CoreWebView2Environment.</span></span>

#### <span data-ttu-id="ef8b8-154">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="ef8b8-154">CoreWebView2EnvironmentOptions</span></span> 

<span data-ttu-id="ef8b8-155">CoreWebView2EnvironmentOptions クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-155">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

> <span data-ttu-id="ef8b8-156">パブリック[CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(文字列 additionalBrowserArguments、文字列言語、文字列ターゲット)</span><span class="sxs-lookup"><span data-stu-id="ef8b8-156">public  [CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(string additionalBrowserArguments, string language, string targetCompatibleBrowserVersion)</span></span>

##### <span data-ttu-id="ef8b8-157">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef8b8-157">Parameters</span></span>
* `additionalBrowserArguments` <span data-ttu-id="ef8b8-158">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-158">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span> 

* `language` <span data-ttu-id="ef8b8-159">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-159">The default language that WebView will run with.</span></span> 

* `targetCompatibleBrowserVersion` <span data-ttu-id="ef8b8-160">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef8b8-160">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

