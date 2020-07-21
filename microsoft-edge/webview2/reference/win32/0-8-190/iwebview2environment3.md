---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2Environment3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 327a182c5298ed6de6b9e55b407d138857dbe659
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886095"
---
# <span data-ttu-id="7e7a2-104">0.8.355-インターフェイス IWebView2Environment3</span><span class="sxs-lookup"><span data-stu-id="7e7a2-104">0.8.355 - interface IWebView2Environment3</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Environment3
  : public IWebView2Environment2
```

<span data-ttu-id="7e7a2-105">環境オブジェクトによって実装される追加機能。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-105">Additional functionality implemented by the Environment object.</span></span>

## <span data-ttu-id="7e7a2-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="7e7a2-106">Summary</span></span>

 <span data-ttu-id="7e7a2-107">Members</span><span class="sxs-lookup"><span data-stu-id="7e7a2-107">Members</span></span>                        | <span data-ttu-id="7e7a2-108">説明</span><span class="sxs-lookup"><span data-stu-id="7e7a2-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7e7a2-109">add_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="7e7a2-109">add_NewVersionAvailable</span></span>](#add_newversionavailable) | <span data-ttu-id="7e7a2-110">NewVersionAvailable イベントは、新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-110">The NewVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>
[<span data-ttu-id="7e7a2-111">remove_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="7e7a2-111">remove_NewVersionAvailable</span></span>](#remove_newversionavailable) | <span data-ttu-id="7e7a2-112">Add_NewVersionAvailable で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-112">Remove an event handler previously added with add_NewVersionAvailable.</span></span>

<span data-ttu-id="7e7a2-113">詳細については、 [IWebView2Environment](IWebView2Environment.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-113">See the [IWebView2Environment](IWebView2Environment.md) interface for more details.</span></span> <span data-ttu-id="7e7a2-114">このインターフェイスの QueryInterface は、 [IWebView2Environment](IWebView2Environment.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-114">You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="7e7a2-115">Members</span><span class="sxs-lookup"><span data-stu-id="7e7a2-115">Members</span></span>

#### <span data-ttu-id="7e7a2-116">add_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="7e7a2-116">add_NewVersionAvailable</span></span> 

<span data-ttu-id="7e7a2-117">NewVersionAvailable イベントは、新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-117">The NewVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>

> <span data-ttu-id="7e7a2-118">パブリック HRESULT [add_NewVersionAvailable](#add_newversionavailable)([IWebView2NewVersionAvailableEventHandler](IWebView2NewVersionAvailableEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="7e7a2-118">public HRESULT [add_NewVersionAvailable](#add_newversionavailable)([IWebView2NewVersionAvailableEventHandler](IWebView2NewVersionAvailableEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="7e7a2-119">新しいバージョンのブラウザーを使用するには、新しい[IWebView2Environment](IWebView2Environment.md)と[IWebView2WebView](IWebView2WebView.md)を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-119">To use the newer version of the browser you must create a new [IWebView2Environment](IWebView2Environment.md) and [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="7e7a2-120">イベントは、コードが実行されている同じエッジチャネルからの新しいバージョンでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-120">Event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="7e7a2-121">インストールされている Edge で実行されていない場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-121">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="7e7a2-122">ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している[IWebView2Environment](IWebView2Environment.md)と IWebView2WebViews を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-122">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the [IWebView2Environment](IWebView2Environment.md) and IWebView2WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="7e7a2-123">または、単に、アプリを再起動するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-123">Or simply prompt the user to restart the app.</span></span>

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

#### <span data-ttu-id="7e7a2-124">remove_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="7e7a2-124">remove_NewVersionAvailable</span></span> 

<span data-ttu-id="7e7a2-125">Add_NewVersionAvailable で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7e7a2-125">Remove an event handler previously added with add_NewVersionAvailable.</span></span>

> <span data-ttu-id="7e7a2-126">パブリック HRESULT [remove_NewVersionAvailable](#remove_newversionavailable)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="7e7a2-126">public HRESULT [remove_NewVersionAvailable](#remove_newversionavailable)(EventRegistrationToken token)</span></span>

