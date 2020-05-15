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
# <span data-ttu-id="cad42-104">インターフェイス IWebView2Environment3</span><span class="sxs-lookup"><span data-stu-id="cad42-104">interface IWebView2Environment3</span></span> 

> [!NOTE]
> <span data-ttu-id="cad42-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cad42-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="cad42-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad42-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Environment3
  : public IWebView2Environment2
```

<span data-ttu-id="cad42-107">環境オブジェクトによって実装される追加機能。</span><span class="sxs-lookup"><span data-stu-id="cad42-107">Additional functionality implemented by the Environment object.</span></span>

## <span data-ttu-id="cad42-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="cad42-108">Summary</span></span>

 <span data-ttu-id="cad42-109">Members</span><span class="sxs-lookup"><span data-stu-id="cad42-109">Members</span></span>                        | <span data-ttu-id="cad42-110">説明</span><span class="sxs-lookup"><span data-stu-id="cad42-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cad42-111">add_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="cad42-111">add_NewVersionAvailable</span></span>](#add_newversionavailable) | <span data-ttu-id="cad42-112">NewVersionAvailable イベントは、新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cad42-112">The NewVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>
[<span data-ttu-id="cad42-113">remove_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="cad42-113">remove_NewVersionAvailable</span></span>](#remove_newversionavailable) | <span data-ttu-id="cad42-114">Add_NewVersionAvailable で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cad42-114">Remove an event handler previously added with add_NewVersionAvailable.</span></span>

<span data-ttu-id="cad42-115">詳細については、 [IWebView2Environment](IWebView2Environment.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad42-115">See the [IWebView2Environment](IWebView2Environment.md) interface for more details.</span></span> <span data-ttu-id="cad42-116">このインターフェイスの QueryInterface は、 [IWebView2Environment](IWebView2Environment.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cad42-116">You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="cad42-117">Members</span><span class="sxs-lookup"><span data-stu-id="cad42-117">Members</span></span>

#### <span data-ttu-id="cad42-118">add_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="cad42-118">add_NewVersionAvailable</span></span> 

<span data-ttu-id="cad42-119">NewVersionAvailable イベントは、新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cad42-119">The NewVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>

> <span data-ttu-id="cad42-120">パブリック HRESULT [add_NewVersionAvailable](#add_newversionavailable)([IWebView2NewVersionAvailableEventHandler](IWebView2NewVersionAvailableEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cad42-120">public HRESULT [add_NewVersionAvailable](#add_newversionavailable)([IWebView2NewVersionAvailableEventHandler](IWebView2NewVersionAvailableEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cad42-121">新しいバージョンのブラウザーを使用するには、新しい[IWebView2Environment](IWebView2Environment.md)と[IWebView2WebView](IWebView2WebView.md)を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cad42-121">To use the newer version of the browser you must create a new [IWebView2Environment](IWebView2Environment.md) and [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="cad42-122">イベントは、コードが実行されている同じエッジチャネルからの新しいバージョンでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="cad42-122">Event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="cad42-123">インストールされている Edge で実行されていない場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="cad42-123">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="cad42-124">ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している[IWebView2Environment](IWebView2Environment.md)と IWebView2WebViews を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cad42-124">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the [IWebView2Environment](IWebView2Environment.md) and IWebView2WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="cad42-125">または、単に、アプリを再起動するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="cad42-125">Or simply prompt the user to restart the app.</span></span>

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

#### <span data-ttu-id="cad42-126">remove_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="cad42-126">remove_NewVersionAvailable</span></span> 

<span data-ttu-id="cad42-127">Add_NewVersionAvailable で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cad42-127">Remove an event handler previously added with add_NewVersionAvailable.</span></span>

> <span data-ttu-id="cad42-128">パブリック HRESULT [remove_NewVersionAvailable](#remove_newversionavailable)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cad42-128">public HRESULT [remove_NewVersionAvailable](#remove_newversionavailable)(EventRegistrationToken token)</span></span>

