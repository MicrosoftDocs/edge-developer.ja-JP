---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 43becb7f4ec9903557ccd558319e233266ac2ea1
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654242"
---
# インターフェイス IWebView2Environment3 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2Environment3
  : public IWebView2Environment2
```

環境オブジェクトによって実装される追加機能。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[add_NewVersionAvailable](#add_newversionavailable) | NewVersionAvailable イベントは、新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに発生します。
[remove_NewVersionAvailable](#remove_newversionavailable) | Add_NewVersionAvailable で以前に追加されたイベントハンドラーを削除します。

詳細については、 [IWebView2Environment](IWebView2Environment.md)インターフェイスを参照してください。 このインターフェイスの QueryInterface は、 [IWebView2Environment](IWebView2Environment.md)を実装するオブジェクトから行うことができます。

## Members

#### add_NewVersionAvailable 

NewVersionAvailable イベントは、新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに発生します。

> パブリック HRESULT [add_NewVersionAvailable](#add_newversionavailable)([IWebView2NewVersionAvailableEventHandler](IWebView2NewVersionAvailableEventHandler.md) * eventHandler、EventRegistrationToken * token)

新しいバージョンのブラウザーを使用するには、新しい[IWebView2Environment](IWebView2Environment.md)と[IWebView2WebView](IWebView2WebView.md)を作成する必要があります。 イベントは、コードが実行されている同じエッジチャネルからの新しいバージョンでのみ発生します。 インストールされている Edge で実行されていない場合、イベントは発生しません。

ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している[IWebView2Environment](IWebView2Environment.md)と IWebView2WebViews を閉じる必要があります。 または、単に、アプリを再起動するようにユーザーに求めます。

```cpp
    // After the environment is successfully created,
    // register a handler for the NewVersionAvailable event.
    // This handler tells when there is a new Edge version available on the machine.
    CHECK_FAILURE(m_webViewEnvironment->add_NewVersionAvailable(
        Callback<IWebView2NewVersionAvailableEventHandler>(
            [this](IWebView2Environment* sender, IWebView2NewVersionAvailableEventArgs* args)
                -> HRESULT {
                // Get the version value from args
                wil::unique_cotaskmem_string newVersion;
                CHECK_FAILURE(args->get_NewVersion(&newVersion));
                std::wstring message = L"We detected there is a new version for the browser.";
                message += L"\n\nVersion number: ";
                message += newVersion.get();
                message += L"\n\n";
                if (m_webView)
                {
                    message += L"Do you want to restart the app? \n\n";
                    message += L"Click No if you only want to re-create the webviews. \n";
                    message += L"Click Cancel for no action. \n";
                }
                int response = MessageBox(
                    m_mainWindow, message.c_str(), L"New available version",
                    m_webView ? MB_YESNOCANCEL : MB_OK);

                if (response == IDYES)
                {
                    RestartApp();
                }
                else if (response == IDNO)
                {
                    ReinitializeWebViewWithNewBrowser();
                }
                else
                {
                    // do nothing
                }

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### remove_NewVersionAvailable 

Add_NewVersionAvailable で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_NewVersionAvailable](#remove_newversionavailable)(EventRegistrationToken token)

