---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2EnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2EnvironmentOptions。
ms.openlocfilehash: b5f940dedd513e15564d410e7edf0f94024f4e37
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012220"
---
# <span data-ttu-id="08363-104">WebView2 クラス (CoreWebView2EnvironmentOptions クラス)</span><span class="sxs-lookup"><span data-stu-id="08363-104">Microsoft.Web.WebView2.Core.CoreWebView2EnvironmentOptions class</span></span> 

<span data-ttu-id="08363-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="08363-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="08363-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="08363-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="08363-107">WebView2 環境の作成に使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="08363-107">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="08363-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="08363-108">Summary</span></span>

 <span data-ttu-id="08363-109">Members</span><span class="sxs-lookup"><span data-stu-id="08363-109">Members</span></span>                        | <span data-ttu-id="08363-110">説明</span><span class="sxs-lookup"><span data-stu-id="08363-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="08363-111">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="08363-111">AdditionalBrowserArguments</span></span>](#additionalbrowserarguments) | <span data-ttu-id="08363-112">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="08363-112">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="08363-113">AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="08363-113">AllowSingleSignOnUsingOSPrimaryAccount</span></span>](#allowsinglesignonusingosprimaryaccount) | <span data-ttu-id="08363-114">AllowSingleSignOnUsingOSPrimaryAccount プロパティは、Windows アカウントのログインに関連付けられている Microsoft アカウントを使用して、ログインしている Windows アカウントと web サイトでのシングルサインオンを使用して、WebView 内で Azure Active Directory (AAD) リソースとのシングルサインオンを有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="08363-114">The AllowSingleSignOnUsingOSPrimaryAccount property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>
[<span data-ttu-id="08363-115">言語</span><span class="sxs-lookup"><span data-stu-id="08363-115">Language</span></span>](#language) | <span data-ttu-id="08363-116">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="08363-116">The default language that WebView will run with.</span></span>
[<span data-ttu-id="08363-117">Targetserversion</span><span class="sxs-lookup"><span data-stu-id="08363-117">TargetCompatibleBrowserVersion</span></span>](#targetcompatiblebrowserversion) | <span data-ttu-id="08363-118">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="08363-118">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="08363-119">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="08363-119">CoreWebView2EnvironmentOptions</span></span>](#corewebview2environmentoptions) | <span data-ttu-id="08363-120">CoreWebView2EnvironmentOptions クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="08363-120">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

<span data-ttu-id="08363-121">WebView2EnvironmentOptions には既定の実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="08363-121">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

## <span data-ttu-id="08363-122">Members</span><span class="sxs-lookup"><span data-stu-id="08363-122">Members</span></span>

#### <span data-ttu-id="08363-123">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="08363-123">AdditionalBrowserArguments</span></span> 

<span data-ttu-id="08363-124">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="08363-124">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="08363-125">パブリック文字列の [Additionalbrowserarguments](#additionalbrowserarguments)</span><span class="sxs-lookup"><span data-stu-id="08363-125">public string [AdditionalBrowserArguments](#additionalbrowserarguments)</span></span>

<span data-ttu-id="08363-126">これらは、コマンドラインの一部としてブラウザープロセスに渡されます。</span><span class="sxs-lookup"><span data-stu-id="08363-126">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="08363-127">ブラウザプロセスへのコマンドラインスイッチの詳細については、「 [フラグを使って Chromium を実行](https://aka.ms/RunChromiumWithFlags) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08363-127">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="08363-128">コマンドラインスイッチを使用してアプリを起動すると、 `--edge-webview-switches=xxx` そのスイッチの値 (上の例では xxx) もブラウザープロセスのコマンドラインに追加されます。</span><span class="sxs-lookup"><span data-stu-id="08363-128">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="08363-129">次のような一部 `--user-data-dir` のスイッチは、WebView として内部的で重要です。</span><span class="sxs-lookup"><span data-stu-id="08363-129">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="08363-130">これらのスイッチは、指定した場合でも無視されます。</span><span class="sxs-lookup"><span data-stu-id="08363-130">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="08363-131">同じスイッチが複数回指定されている場合は、最後のスイッチが優先されます。</span><span class="sxs-lookup"><span data-stu-id="08363-131">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="08363-132">無効および有効な機能を除き、同じスイッチの異なる値をマージしようとすることはありません。</span><span class="sxs-lookup"><span data-stu-id="08363-132">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="08363-133">およびで指定された機能は、 `--enable-features` `--disable-features` 単純なロジックにマージされます。これらの機能は、指定された機能と組み込み機能の和集合であり、機能が無効になっている場合は、[有効な機能] の一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="08363-133">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="08363-134">アプリプロセスのコマンドライン `--edge-webview-switches` 値は、additionalBrowserArguments パラメーターが処理された後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="08363-134">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="08363-135">一部の機能は内部で無効にされているため、有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="08363-135">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="08363-136">指定したスイッチの解析に失敗した場合、それらは無視されます。</span><span class="sxs-lookup"><span data-stu-id="08363-136">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="08363-137">既定では、追加のフラグなしでブラウザープロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="08363-137">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="08363-138">AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="08363-138">AllowSingleSignOnUsingOSPrimaryAccount</span></span> 

<span data-ttu-id="08363-139">AllowSingleSignOnUsingOSPrimaryAccount プロパティは、Windows アカウントのログインに関連付けられている Microsoft アカウントを使用して、ログインしている Windows アカウントと web サイトでのシングルサインオンを使用して、WebView 内で Azure Active Directory (AAD) リソースとのシングルサインオンを有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="08363-139">The AllowSingleSignOnUsingOSPrimaryAccount property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>

> <span data-ttu-id="08363-140">public bool [AllowSingleSignOnUsingOSPrimaryAccount](#allowsinglesignonusingosprimaryaccount)</span><span class="sxs-lookup"><span data-stu-id="08363-140">public bool [AllowSingleSignOnUsingOSPrimaryAccount](#allowsinglesignonusingosprimaryaccount)</span></span>

<span data-ttu-id="08363-141">既定値は無効です。</span><span class="sxs-lookup"><span data-stu-id="08363-141">Default is disabled.</span></span> <span data-ttu-id="08363-142">ユニバーサル Windows プラットフォームアプリでは、シングルサインオンが機能するために enterpriseCloudSSO の制限された [機能](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) も宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08363-142">Universal Windows Platform apps must also declare enterpriseCloudSSO [restricted capability](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) for the single sign on to work.</span></span>

#### <span data-ttu-id="08363-143">言語</span><span class="sxs-lookup"><span data-stu-id="08363-143">Language</span></span> 

<span data-ttu-id="08363-144">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="08363-144">The default language that WebView will run with.</span></span>

> <span data-ttu-id="08363-145">公開文字列の [言語](#language)</span><span class="sxs-lookup"><span data-stu-id="08363-145">public string [Language](#language)</span></span>

<span data-ttu-id="08363-146">これは、コンテキストメニューやダイアログなどのブラウザー Ui に適用されます。</span><span class="sxs-lookup"><span data-stu-id="08363-146">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="08363-147">また、WebView が web サイトに送信する受け入れ言語の HTTP ヘッダーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="08363-147">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="08363-148">この形式は、 `language[-country]` `language` iso 639 の2文字コードであり、 `country` iso 3166 の2文字のコードです。</span><span class="sxs-lookup"><span data-stu-id="08363-148">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="08363-149">Targetserversion</span><span class="sxs-lookup"><span data-stu-id="08363-149">TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="08363-150">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="08363-150">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="08363-151">パブリック文字列[ターゲット](#targetcompatiblebrowserversion)/セルの sion</span><span class="sxs-lookup"><span data-stu-id="08363-151">public string [TargetCompatibleBrowserVersion](#targetcompatiblebrowserversion)</span></span>

<span data-ttu-id="08363-152">これは、アプリケーションで使用されている SDK のバージョンと対応する Edge WebView2 ランタイムバージョンに既定値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="08363-152">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="08363-153">この値の形式は、"この値" と "他の型 Serversion" の値の形式と同じです。</span><span class="sxs-lookup"><span data-stu-id="08363-153">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="08363-154">対象となるのは、のバージョン部分だけです。</span><span class="sxs-lookup"><span data-stu-id="08363-154">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="08363-155">チャネルのサフィックス (存在する場合) は無視されます。</span><span class="sxs-lookup"><span data-stu-id="08363-155">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="08363-156">実際に使用されている Edge WebView2 ランタイムバイナリのバージョンは、指定された Target互換のバージョンとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08363-156">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="08363-157">互換性が保証されるだけであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="08363-157">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="08363-158">CoreWebView2Environment の参照サーバーの文字列プロパティで実際のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="08363-158">You can check the actual version on the BrowserVersionString property on the CoreWebView2Environment.</span></span>

#### <span data-ttu-id="08363-159">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="08363-159">CoreWebView2EnvironmentOptions</span></span> 

<span data-ttu-id="08363-160">CoreWebView2EnvironmentOptions クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="08363-160">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

> <span data-ttu-id="08363-161">パブリック [CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(文字列 additionalBrowserArguments、文字列言語、文字列ターゲット、文字列)</span><span class="sxs-lookup"><span data-stu-id="08363-161">public [CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(string additionalBrowserArguments, string language, string targetCompatibleBrowserVersion, bool allowSingleSignOnUsingOSPrimaryAccount)</span></span>

##### <span data-ttu-id="08363-162">パラメーター</span><span class="sxs-lookup"><span data-stu-id="08363-162">Parameters</span></span>
* `additionalBrowserArguments` <span data-ttu-id="08363-163">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="08363-163">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span> 

* `language` <span data-ttu-id="08363-164">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="08363-164">The default language that WebView will run with.</span></span> 

* `targetCompatibleBrowserVersion` <span data-ttu-id="08363-165">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="08363-165">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span> 

* `allowSingleSignOnUsingOSPrimaryAccount` <span data-ttu-id="08363-166">エンドユーザーの OS プライマリアカウントを使用してシングルサインオンを有効にする場合は、true に設定します。</span><span class="sxs-lookup"><span data-stu-id="08363-166">Set to true if single sign on be enabled using the end user's OS primary account.</span></span> <span data-ttu-id="08363-167">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="08363-167">Defaults to false.</span></span>

