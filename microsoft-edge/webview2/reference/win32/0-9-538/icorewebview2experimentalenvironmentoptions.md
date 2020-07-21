---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalEnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalEnvironmentOptions
ms.openlocfilehash: 3e18c15e23338404720dae917cb6d009c41c3c04
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886554"
---
# <span data-ttu-id="d201b-104">インターフェイス ICoreWebView2ExperimentalEnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="d201b-104">interface ICoreWebView2ExperimentalEnvironmentOptions</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalEnvironmentOptions
  : public IUnknown
```

<span data-ttu-id="d201b-105">WebView2 環境を作成するために使用される実験的なオプション。</span><span class="sxs-lookup"><span data-stu-id="d201b-105">Experimental options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="d201b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d201b-106">Summary</span></span>

 <span data-ttu-id="d201b-107">Members</span><span class="sxs-lookup"><span data-stu-id="d201b-107">Members</span></span>                        | <span data-ttu-id="d201b-108">説明</span><span class="sxs-lookup"><span data-stu-id="d201b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d201b-109">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="d201b-109">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span>](#get_issinglesignonusingosprimaryaccountenabled) | <span data-ttu-id="d201b-110">IsSingleSignOnUsingOSPrimaryAccountEnabled プロパティは、Windows アカウントのログインに関連付けられている Microsoft アカウントを使用して、ログインしている Windows アカウントと web サイトでのシングルサインオンを使用して、WebView 内で Azure Active Directory (AAD) リソースとのシングルサインオンを有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d201b-110">The IsSingleSignOnUsingOSPrimaryAccountEnabled property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>
[<span data-ttu-id="d201b-111">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="d201b-111">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span>](#put_issinglesignonusingosprimaryaccountenabled) | <span data-ttu-id="d201b-112">IsSingleSignOnUsingOSPrimaryAccountEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d201b-112">Set the IsSingleSignOnUsingOSPrimaryAccountEnabled property.</span></span>

<span data-ttu-id="d201b-113">WebView2ExperimentalEnvironmentOptions には既定の実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d201b-113">A default implementation is provided in WebView2ExperimentalEnvironmentOptions.h.</span></span>

```cpp
    auto options = Microsoft::WRL::Make<CoreWebView2ExperimentalEnvironmentOptions>();
    CHECK_FAILURE(options->put_IsSingleSignOnUsingOSPrimaryAccountEnabled(
        m_AADSSOEnabled ? TRUE : FALSE));
    if (!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
```

## <span data-ttu-id="d201b-114">Members</span><span class="sxs-lookup"><span data-stu-id="d201b-114">Members</span></span>

#### <span data-ttu-id="d201b-115">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="d201b-115">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span> 

<span data-ttu-id="d201b-116">IsSingleSignOnUsingOSPrimaryAccountEnabled プロパティは、Windows アカウントのログインに関連付けられている Microsoft アカウントを使用して、ログインしている Windows アカウントと web サイトでのシングルサインオンを使用して、WebView 内で Azure Active Directory (AAD) リソースとのシングルサインオンを有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d201b-116">The IsSingleSignOnUsingOSPrimaryAccountEnabled property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>

> <span data-ttu-id="d201b-117">パブリック HRESULT [get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="d201b-117">public HRESULT [get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="d201b-118">既定値は無効です。</span><span class="sxs-lookup"><span data-stu-id="d201b-118">Default is disabled.</span></span> <span data-ttu-id="d201b-119">ユニバーサル Windows プラットフォームアプリでは、シングルサインオンが機能するために enterpriseCloudSSO の制限された[機能](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities)も宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d201b-119">Universal Windows Platform apps must also declare enterpriseCloudSSO [restricted capability](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) for the single sign on to work.</span></span>

#### <span data-ttu-id="d201b-120">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="d201b-120">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span> 

<span data-ttu-id="d201b-121">IsSingleSignOnUsingOSPrimaryAccountEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d201b-121">Set the IsSingleSignOnUsingOSPrimaryAccountEnabled property.</span></span>

> <span data-ttu-id="d201b-122">パブリック HRESULT [put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="d201b-122">public HRESULT [put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled)(BOOL enabled)</span></span>

