---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2EnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2EnvironmentOptions。
ms.openlocfilehash: e1ff99d7993aec875a5bf79b863f0824ca50d337
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878905"
---
# <span data-ttu-id="abbed-104">WebView2 クラス (CoreWebView2EnvironmentOptions クラス)</span><span class="sxs-lookup"><span data-stu-id="abbed-104">Microsoft.Web.WebView2.Core.CoreWebView2EnvironmentOptions class</span></span> 

<span data-ttu-id="abbed-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="abbed-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="abbed-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="abbed-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="abbed-107">WebView2 環境の作成に使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="abbed-107">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="abbed-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="abbed-108">Summary</span></span>

 <span data-ttu-id="abbed-109">Members</span><span class="sxs-lookup"><span data-stu-id="abbed-109">Members</span></span>                        | <span data-ttu-id="abbed-110">説明</span><span class="sxs-lookup"><span data-stu-id="abbed-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="abbed-111">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="abbed-111">AdditionalBrowserArguments</span></span>](#additionalbrowserarguments) | <span data-ttu-id="abbed-112">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="abbed-112">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="abbed-113">言語</span><span class="sxs-lookup"><span data-stu-id="abbed-113">Language</span></span>](#language) | <span data-ttu-id="abbed-114">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="abbed-114">The default language that WebView will run with.</span></span>
[<span data-ttu-id="abbed-115">Targetserversion</span><span class="sxs-lookup"><span data-stu-id="abbed-115">TargetCompatibleBrowserVersion</span></span>](#targetcompatiblebrowserversion) | <span data-ttu-id="abbed-116">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="abbed-116">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="abbed-117">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="abbed-117">CoreWebView2EnvironmentOptions</span></span>](#corewebview2environmentoptions) | <span data-ttu-id="abbed-118">CoreWebView2EnvironmentOptions クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="abbed-118">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

<span data-ttu-id="abbed-119">WebView2EnvironmentOptions には既定の実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="abbed-119">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

## <span data-ttu-id="abbed-120">Members</span><span class="sxs-lookup"><span data-stu-id="abbed-120">Members</span></span>

#### <span data-ttu-id="abbed-121">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="abbed-121">AdditionalBrowserArguments</span></span> 

<span data-ttu-id="abbed-122">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="abbed-122">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="abbed-123">パブリック文字列の[Additionalbrowserarguments](#additionalbrowserarguments)</span><span class="sxs-lookup"><span data-stu-id="abbed-123">public string [AdditionalBrowserArguments](#additionalbrowserarguments)</span></span>

<span data-ttu-id="abbed-124">これらは、コマンドラインの一部としてブラウザープロセスに渡されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-124">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="abbed-125">ブラウザプロセスへのコマンドラインスイッチの詳細については、「[フラグを使って Chromium を実行](https://aka.ms/RunChromiumWithFlags)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abbed-125">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="abbed-126">コマンドラインスイッチを使用してアプリを起動すると、 `--edge-webview-switches=xxx` そのスイッチの値 (上の例では xxx) もブラウザープロセスのコマンドラインに追加されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-126">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="abbed-127">次のような一部 `--user-data-dir` のスイッチは、WebView として内部的で重要です。</span><span class="sxs-lookup"><span data-stu-id="abbed-127">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="abbed-128">これらのスイッチは、指定した場合でも無視されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-128">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="abbed-129">同じスイッチが複数回指定されている場合は、最後のスイッチが優先されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-129">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="abbed-130">無効および有効な機能を除き、同じスイッチの異なる値をマージしようとすることはありません。</span><span class="sxs-lookup"><span data-stu-id="abbed-130">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="abbed-131">およびで指定された機能は、 `--enable-features` `--disable-features` 単純なロジックにマージされます。これらの機能は、指定された機能と組み込み機能の和集合であり、機能が無効になっている場合は、[有効な機能] の一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-131">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="abbed-132">アプリプロセスのコマンドライン `--edge-webview-switches` 値は、additionalBrowserArguments パラメーターが処理された後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-132">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="abbed-133">一部の機能は内部で無効にされているため、有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="abbed-133">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="abbed-134">指定したスイッチの解析に失敗した場合、それらは無視されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-134">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="abbed-135">既定では、追加のフラグなしでブラウザープロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="abbed-135">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="abbed-136">言語</span><span class="sxs-lookup"><span data-stu-id="abbed-136">Language</span></span> 

<span data-ttu-id="abbed-137">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="abbed-137">The default language that WebView will run with.</span></span>

> <span data-ttu-id="abbed-138">公開文字列の[言語](#language)</span><span class="sxs-lookup"><span data-stu-id="abbed-138">public string [Language](#language)</span></span>

<span data-ttu-id="abbed-139">これは、コンテキストメニューやダイアログなどのブラウザー Ui に適用されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-139">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="abbed-140">また、WebView が web サイトに送信する受け入れ言語の HTTP ヘッダーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-140">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="abbed-141">この形式は、 `language[-country]` `language` iso 639 の2文字コードであり、 `country` iso 3166 の2文字のコードです。</span><span class="sxs-lookup"><span data-stu-id="abbed-141">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="abbed-142">Targetserversion</span><span class="sxs-lookup"><span data-stu-id="abbed-142">TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="abbed-143">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="abbed-143">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="abbed-144">パブリック文字列[ターゲット](#targetcompatiblebrowserversion)/セルの sion</span><span class="sxs-lookup"><span data-stu-id="abbed-144">public string [TargetCompatibleBrowserVersion](#targetcompatiblebrowserversion)</span></span>

<span data-ttu-id="abbed-145">これは、アプリケーションで使用されている SDK のバージョンと対応する Edge WebView2 ランタイムバージョンに既定値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="abbed-145">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="abbed-146">この値の形式は、"この値" と "他の型 Serversion" の値の形式と同じです。</span><span class="sxs-lookup"><span data-stu-id="abbed-146">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="abbed-147">対象となるのは、のバージョン部分だけです。</span><span class="sxs-lookup"><span data-stu-id="abbed-147">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="abbed-148">チャネルのサフィックス (存在する場合) は無視されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-148">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="abbed-149">実際に使用されている Edge WebView2 ランタイムバイナリのバージョンは、指定された Target互換のバージョンとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="abbed-149">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="abbed-150">互換性が保証されるだけであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="abbed-150">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="abbed-151">CoreWebView2Environment の参照サーバーの文字列プロパティで実際のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="abbed-151">You can check the actual version on the BrowserVersionString property on the CoreWebView2Environment.</span></span>

#### <span data-ttu-id="abbed-152">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="abbed-152">CoreWebView2EnvironmentOptions</span></span> 

<span data-ttu-id="abbed-153">CoreWebView2EnvironmentOptions クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="abbed-153">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

> <span data-ttu-id="abbed-154">パブリック[CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(文字列 additionalBrowserArguments、文字列言語、文字列ターゲット)</span><span class="sxs-lookup"><span data-stu-id="abbed-154">public  [CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(string additionalBrowserArguments, string language, string targetCompatibleBrowserVersion)</span></span>

##### <span data-ttu-id="abbed-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="abbed-155">Parameters</span></span>
* `additionalBrowserArguments` <span data-ttu-id="abbed-156">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="abbed-156">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span> 

* `language` <span data-ttu-id="abbed-157">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="abbed-157">The default language that WebView will run with.</span></span> 

* `targetCompatibleBrowserVersion` <span data-ttu-id="abbed-158">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="abbed-158">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

