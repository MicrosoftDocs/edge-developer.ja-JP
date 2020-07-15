---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2Environment3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: d16a12aae823c48b7dd4b0b5e8225cdd40c1dafc
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878527"
---
# 0.8.355-インターフェイス IWebView2Environment3 

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

