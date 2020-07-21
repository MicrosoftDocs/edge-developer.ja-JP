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
# インターフェイス ICoreWebView2ExperimentalEnvironmentOptions 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalEnvironmentOptions
  : public IUnknown
```

WebView2 環境を作成するために使用される実験的なオプション。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled) | IsSingleSignOnUsingOSPrimaryAccountEnabled プロパティは、Windows アカウントのログインに関連付けられている Microsoft アカウントを使用して、ログインしている Windows アカウントと web サイトでのシングルサインオンを使用して、WebView 内で Azure Active Directory (AAD) リソースとのシングルサインオンを有効にするために使用されます。
[put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled) | IsSingleSignOnUsingOSPrimaryAccountEnabled プロパティを設定します。

WebView2ExperimentalEnvironmentOptions には既定の実装が用意されています。

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

## Members

#### get_IsSingleSignOnUsingOSPrimaryAccountEnabled 

IsSingleSignOnUsingOSPrimaryAccountEnabled プロパティは、Windows アカウントのログインに関連付けられている Microsoft アカウントを使用して、ログインしている Windows アカウントと web サイトでのシングルサインオンを使用して、WebView 内で Azure Active Directory (AAD) リソースとのシングルサインオンを有効にするために使用されます。

> パブリック HRESULT [get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled)(ブール * enabled)

既定値は無効です。 ユニバーサル Windows プラットフォームアプリでは、シングルサインオンが機能するために enterpriseCloudSSO の制限された[機能](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities)も宣言する必要があります。

#### put_IsSingleSignOnUsingOSPrimaryAccountEnabled 

IsSingleSignOnUsingOSPrimaryAccountEnabled プロパティを設定します。

> パブリック HRESULT [put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled)(BOOL enabled)

