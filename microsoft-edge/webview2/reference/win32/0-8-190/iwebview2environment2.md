---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2Environment2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: d127af61bfdc9bf692fa48489d7982bf2c6cad86
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878548"
---
# <span data-ttu-id="842af-104">0.8.355-インターフェイス IWebView2Environment2</span><span class="sxs-lookup"><span data-stu-id="842af-104">0.8.355 - interface IWebView2Environment2</span></span> 

> [!NOTE]
> <span data-ttu-id="842af-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="842af-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="842af-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="842af-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Environment2
  : public IWebView2Environment
```

<span data-ttu-id="842af-107">環境オブジェクトによって実装される追加機能。</span><span class="sxs-lookup"><span data-stu-id="842af-107">Additional functionality implemented by the Environment object.</span></span>

## <span data-ttu-id="842af-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="842af-108">Summary</span></span>

 <span data-ttu-id="842af-109">Members</span><span class="sxs-lookup"><span data-stu-id="842af-109">Members</span></span>                        | <span data-ttu-id="842af-110">説明</span><span class="sxs-lookup"><span data-stu-id="842af-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="842af-111">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="842af-111">get_BrowserVersionInfo</span></span>](#get_browserversioninfo) | <span data-ttu-id="842af-112">IWebView2Environment が安定していない場合は、チャネル名を含む現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="842af-112">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

<span data-ttu-id="842af-113">詳細については、 [IWebView2Environment](IWebView2Environment.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="842af-113">See the [IWebView2Environment](IWebView2Environment.md) interface for more details.</span></span> <span data-ttu-id="842af-114">このインターフェイスの QueryInterface は、 [IWebView2Environment](IWebView2Environment.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="842af-114">You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="842af-115">Members</span><span class="sxs-lookup"><span data-stu-id="842af-115">Members</span></span>

#### <span data-ttu-id="842af-116">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="842af-116">get_BrowserVersionInfo</span></span> 

<span data-ttu-id="842af-117">IWebView2Environment が安定していない場合は、チャネル名を含む現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="842af-117">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="842af-118">パブリック HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span><span class="sxs-lookup"><span data-stu-id="842af-118">public HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="842af-119">これは、GetWebView2BrowserVersionInfo API の形式と一致します。</span><span class="sxs-lookup"><span data-stu-id="842af-119">This matches the format of the GetWebView2BrowserVersionInfo API.</span></span> <span data-ttu-id="842af-120">チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。</span><span class="sxs-lookup"><span data-stu-id="842af-120">Channel names are 'beta', 'dev', and 'canary'.</span></span>

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

