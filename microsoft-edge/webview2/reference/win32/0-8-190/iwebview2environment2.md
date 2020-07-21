---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2Environment2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: e3177f159ff397ee9d4781936aa32f2715d4af02
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886088"
---
# <span data-ttu-id="a6114-104">0.8.355-インターフェイス IWebView2Environment2</span><span class="sxs-lookup"><span data-stu-id="a6114-104">0.8.355 - interface IWebView2Environment2</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Environment2
  : public IWebView2Environment
```

<span data-ttu-id="a6114-105">環境オブジェクトによって実装される追加機能。</span><span class="sxs-lookup"><span data-stu-id="a6114-105">Additional functionality implemented by the Environment object.</span></span>

## <span data-ttu-id="a6114-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a6114-106">Summary</span></span>

 <span data-ttu-id="a6114-107">Members</span><span class="sxs-lookup"><span data-stu-id="a6114-107">Members</span></span>                        | <span data-ttu-id="a6114-108">説明</span><span class="sxs-lookup"><span data-stu-id="a6114-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a6114-109">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="a6114-109">get_BrowserVersionInfo</span></span>](#get_browserversioninfo) | <span data-ttu-id="a6114-110">IWebView2Environment が安定していない場合は、チャネル名を含む現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="a6114-110">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

<span data-ttu-id="a6114-111">詳細については、 [IWebView2Environment](IWebView2Environment.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6114-111">See the [IWebView2Environment](IWebView2Environment.md) interface for more details.</span></span> <span data-ttu-id="a6114-112">このインターフェイスの QueryInterface は、 [IWebView2Environment](IWebView2Environment.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6114-112">You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="a6114-113">Members</span><span class="sxs-lookup"><span data-stu-id="a6114-113">Members</span></span>

#### <span data-ttu-id="a6114-114">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="a6114-114">get_BrowserVersionInfo</span></span> 

<span data-ttu-id="a6114-115">IWebView2Environment が安定していない場合は、チャネル名を含む現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="a6114-115">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="a6114-116">パブリック HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span><span class="sxs-lookup"><span data-stu-id="a6114-116">public HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="a6114-117">これは、GetWebView2BrowserVersionInfo API の形式と一致します。</span><span class="sxs-lookup"><span data-stu-id="a6114-117">This matches the format of the GetWebView2BrowserVersionInfo API.</span></span> <span data-ttu-id="a6114-118">チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。</span><span class="sxs-lookup"><span data-stu-id="a6114-118">Channel names are 'beta', 'dev', and 'canary'.</span></span>

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

