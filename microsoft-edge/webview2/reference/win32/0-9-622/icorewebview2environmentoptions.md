---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2EnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2EnvironmentOptions
ms.openlocfilehash: a4e51dc08e2c31664cb77e4e6ee0136bab2f261d
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012371"
---
# <span data-ttu-id="253be-104">インターフェイス ICoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="253be-104">interface ICoreWebView2EnvironmentOptions</span></span> 

```
interface ICoreWebView2EnvironmentOptions
  : public IUnknown
```

<span data-ttu-id="253be-105">WebView2 環境の作成に使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="253be-105">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="253be-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="253be-106">Summary</span></span>

 <span data-ttu-id="253be-107">Members</span><span class="sxs-lookup"><span data-stu-id="253be-107">Members</span></span>                        | <span data-ttu-id="253be-108">説明</span><span class="sxs-lookup"><span data-stu-id="253be-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="253be-109">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="253be-109">get_AdditionalBrowserArguments</span></span>](#get_additionalbrowserarguments) | <span data-ttu-id="253be-110">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="253be-110">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="253be-111">get_AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="253be-111">get_AllowSingleSignOnUsingOSPrimaryAccount</span></span>](#get_allowsinglesignonusingosprimaryaccount) | <span data-ttu-id="253be-112">AllowSingleSignOnUsingOSPrimaryAccount プロパティは、Windows アカウントのログインに関連付けられている Microsoft アカウントを使用して、ログインしている Windows アカウントと web サイトでのシングルサインオンを使用して、WebView 内で Azure Active Directory (AAD) リソースとのシングルサインオンを有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="253be-112">The AllowSingleSignOnUsingOSPrimaryAccount property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>
[<span data-ttu-id="253be-113">get_Language</span><span class="sxs-lookup"><span data-stu-id="253be-113">get_Language</span></span>](#get_language) | <span data-ttu-id="253be-114">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="253be-114">The default language that WebView will run with.</span></span>
[<span data-ttu-id="253be-115">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="253be-115">get_TargetCompatibleBrowserVersion</span></span>](#get_targetcompatiblebrowserversion) | <span data-ttu-id="253be-116">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="253be-116">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="253be-117">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="253be-117">put_AdditionalBrowserArguments</span></span>](#put_additionalbrowserarguments) | <span data-ttu-id="253be-118">AdditionalBrowserArguments プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="253be-118">Set the AdditionalBrowserArguments property.</span></span>
[<span data-ttu-id="253be-119">put_AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="253be-119">put_AllowSingleSignOnUsingOSPrimaryAccount</span></span>](#put_allowsinglesignonusingosprimaryaccount) | <span data-ttu-id="253be-120">AllowSingleSignOnUsingOSPrimaryAccount プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="253be-120">Set the AllowSingleSignOnUsingOSPrimaryAccount property.</span></span>
[<span data-ttu-id="253be-121">put_Language</span><span class="sxs-lookup"><span data-stu-id="253be-121">put_Language</span></span>](#put_language) | <span data-ttu-id="253be-122">Language プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="253be-122">Set the Language property.</span></span>
[<span data-ttu-id="253be-123">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="253be-123">put_TargetCompatibleBrowserVersion</span></span>](#put_targetcompatiblebrowserversion) | <span data-ttu-id="253be-124">Target・の Sion プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="253be-124">Set the TargetCompatibleBrowserVersion property.</span></span>

<span data-ttu-id="253be-125">WebView2EnvironmentOptions には既定の実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="253be-125">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

```cpp
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    CHECK_FAILURE(options->put_AllowSingleSignOnUsingOSPrimaryAccount(
        m_AADSSOEnabled ? TRUE : FALSE));
    if (!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
```

## <span data-ttu-id="253be-126">Members</span><span class="sxs-lookup"><span data-stu-id="253be-126">Members</span></span>

#### <span data-ttu-id="253be-127">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="253be-127">get_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="253be-128">WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="253be-128">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="253be-129">パブリック HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR \* 値)</span><span class="sxs-lookup"><span data-stu-id="253be-129">public HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR \* value)</span></span>

<span data-ttu-id="253be-130">これらは、コマンドラインの一部としてブラウザープロセスに渡されます。</span><span class="sxs-lookup"><span data-stu-id="253be-130">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="253be-131">ブラウザプロセスへのコマンドラインスイッチの詳細については、「 [フラグを使って Chromium を実行](https://aka.ms/RunChromiumWithFlags) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="253be-131">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="253be-132">コマンドラインスイッチを使用してアプリを起動すると、 `--edge-webview-switches=xxx` そのスイッチの値 (上の例では xxx) もブラウザープロセスのコマンドラインに追加されます。</span><span class="sxs-lookup"><span data-stu-id="253be-132">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="253be-133">次のような一部 `--user-data-dir` のスイッチは、WebView として内部的で重要です。</span><span class="sxs-lookup"><span data-stu-id="253be-133">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="253be-134">これらのスイッチは、指定した場合でも無視されます。</span><span class="sxs-lookup"><span data-stu-id="253be-134">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="253be-135">同じスイッチが複数回指定されている場合は、最後のスイッチが優先されます。</span><span class="sxs-lookup"><span data-stu-id="253be-135">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="253be-136">無効および有効な機能を除き、同じスイッチの異なる値をマージしようとすることはありません。</span><span class="sxs-lookup"><span data-stu-id="253be-136">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="253be-137">およびで指定された機能は、 `--enable-features` `--disable-features` 単純なロジックにマージされます。これらの機能は、指定された機能と組み込み機能の和集合であり、機能が無効になっている場合は、[有効な機能] の一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="253be-137">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="253be-138">アプリプロセスのコマンドライン `--edge-webview-switches` 値は、additionalBrowserArguments パラメーターが処理された後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="253be-138">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="253be-139">一部の機能は内部で無効にされているため、有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="253be-139">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="253be-140">指定したスイッチの解析に失敗した場合、それらは無視されます。</span><span class="sxs-lookup"><span data-stu-id="253be-140">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="253be-141">既定では、追加のフラグなしでブラウザープロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="253be-141">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="253be-142">get_AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="253be-142">get_AllowSingleSignOnUsingOSPrimaryAccount</span></span> 

<span data-ttu-id="253be-143">AllowSingleSignOnUsingOSPrimaryAccount プロパティは、Windows アカウントのログインに関連付けられている Microsoft アカウントを使用して、ログインしている Windows アカウントと web サイトでのシングルサインオンを使用して、WebView 内で Azure Active Directory (AAD) リソースとのシングルサインオンを有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="253be-143">The AllowSingleSignOnUsingOSPrimaryAccount property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>

> <span data-ttu-id="253be-144">パブリック HRESULT [get_AllowSingleSignOnUsingOSPrimaryAccount](#get_allowsinglesignonusingosprimaryaccount)(ブール \* 許可)</span><span class="sxs-lookup"><span data-stu-id="253be-144">public HRESULT [get_AllowSingleSignOnUsingOSPrimaryAccount](#get_allowsinglesignonusingosprimaryaccount)(BOOL \* allow)</span></span>

<span data-ttu-id="253be-145">既定値は無効です。</span><span class="sxs-lookup"><span data-stu-id="253be-145">Default is disabled.</span></span> <span data-ttu-id="253be-146">ユニバーサル Windows プラットフォームアプリでは、シングルサインオンが機能するために enterpriseCloudSSO の制限された [機能](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) も宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="253be-146">Universal Windows Platform apps must also declare enterpriseCloudSSO [restricted capability](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) for the single sign on to work.</span></span>

#### <span data-ttu-id="253be-147">get_Language</span><span class="sxs-lookup"><span data-stu-id="253be-147">get_Language</span></span> 

<span data-ttu-id="253be-148">WebView が実行される既定の言語。</span><span class="sxs-lookup"><span data-stu-id="253be-148">The default language that WebView will run with.</span></span>

> <span data-ttu-id="253be-149">パブリック HRESULT [get_Language](#get_language)(LPWSTR \* 値)</span><span class="sxs-lookup"><span data-stu-id="253be-149">public HRESULT [get_Language](#get_language)(LPWSTR \* value)</span></span>

<span data-ttu-id="253be-150">これは、コンテキストメニューやダイアログなどのブラウザー Ui に適用されます。</span><span class="sxs-lookup"><span data-stu-id="253be-150">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="253be-151">また、WebView が web サイトに送信する受け入れ言語の HTTP ヘッダーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="253be-151">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="253be-152">この形式は、 `language[-country]` `language` iso 639 の2文字コードであり、 `country` iso 3166 の2文字のコードです。</span><span class="sxs-lookup"><span data-stu-id="253be-152">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="253be-153">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="253be-153">get_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="253be-154">Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="253be-154">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="253be-155">パブリック HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR \* 値)</span><span class="sxs-lookup"><span data-stu-id="253be-155">public HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR \* value)</span></span>

<span data-ttu-id="253be-156">これは、アプリケーションで使用されている SDK のバージョンと対応する Edge WebView2 ランタイムバージョンに既定値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="253be-156">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="253be-157">この値の形式は、"この値" と "他の型 Serversion" の値の形式と同じです。</span><span class="sxs-lookup"><span data-stu-id="253be-157">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="253be-158">対象となるのは、のバージョン部分だけです。</span><span class="sxs-lookup"><span data-stu-id="253be-158">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="253be-159">チャネルのサフィックス (存在する場合) は無視されます。</span><span class="sxs-lookup"><span data-stu-id="253be-159">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="253be-160">実際に使用されている Edge WebView2 ランタイムバイナリのバージョンは、指定された Target互換のバージョンとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="253be-160">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="253be-161">互換性が保証されるだけであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="253be-161">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="253be-162">ICoreWebView2Environment の参照サーバーの文字列プロパティで実際のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="253be-162">You can check the actual version on the BrowserVersionString property on the ICoreWebView2Environment.</span></span>

#### <span data-ttu-id="253be-163">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="253be-163">put_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="253be-164">AdditionalBrowserArguments プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="253be-164">Set the AdditionalBrowserArguments property.</span></span>

> <span data-ttu-id="253be-165">パブリック HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR 値)</span><span class="sxs-lookup"><span data-stu-id="253be-165">public HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR value)</span></span>

#### <span data-ttu-id="253be-166">put_AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="253be-166">put_AllowSingleSignOnUsingOSPrimaryAccount</span></span> 

<span data-ttu-id="253be-167">AllowSingleSignOnUsingOSPrimaryAccount プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="253be-167">Set the AllowSingleSignOnUsingOSPrimaryAccount property.</span></span>

> <span data-ttu-id="253be-168">パブリック HRESULT [put_AllowSingleSignOnUsingOSPrimaryAccount](#put_allowsinglesignonusingosprimaryaccount)(BOOL allow)</span><span class="sxs-lookup"><span data-stu-id="253be-168">public HRESULT [put_AllowSingleSignOnUsingOSPrimaryAccount](#put_allowsinglesignonusingosprimaryaccount)(BOOL allow)</span></span>

#### <span data-ttu-id="253be-169">put_Language</span><span class="sxs-lookup"><span data-stu-id="253be-169">put_Language</span></span> 

<span data-ttu-id="253be-170">Language プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="253be-170">Set the Language property.</span></span>

> <span data-ttu-id="253be-171">パブリック HRESULT [put_Language](#put_language)(LPCWSTR 値)</span><span class="sxs-lookup"><span data-stu-id="253be-171">public HRESULT [put_Language](#put_language)(LPCWSTR value)</span></span>

#### <span data-ttu-id="253be-172">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="253be-172">put_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="253be-173">Target・の Sion プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="253be-173">Set the TargetCompatibleBrowserVersion property.</span></span>

> <span data-ttu-id="253be-174">パブリック HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR 値)</span><span class="sxs-lookup"><span data-stu-id="253be-174">public HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR value)</span></span>

