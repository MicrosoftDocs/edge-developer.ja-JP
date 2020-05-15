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
ms.openlocfilehash: 00b19d1174a5d5ac643a04038ecdd60c82211194
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654420"
---
# <span data-ttu-id="f7f85-104">インターフェイス IWebView2Environment2</span><span class="sxs-lookup"><span data-stu-id="f7f85-104">interface IWebView2Environment2</span></span> 

> [!NOTE]
> <span data-ttu-id="f7f85-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7f85-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="f7f85-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7f85-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Environment2
  : public IWebView2Environment
```

<span data-ttu-id="f7f85-107">環境オブジェクトによって実装される追加機能。</span><span class="sxs-lookup"><span data-stu-id="f7f85-107">Additional functionality implemented by the Environment object.</span></span>

## <span data-ttu-id="f7f85-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="f7f85-108">Summary</span></span>

 <span data-ttu-id="f7f85-109">Members</span><span class="sxs-lookup"><span data-stu-id="f7f85-109">Members</span></span>                        | <span data-ttu-id="f7f85-110">説明</span><span class="sxs-lookup"><span data-stu-id="f7f85-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f7f85-111">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="f7f85-111">get_BrowserVersionInfo</span></span>](#get_browserversioninfo) | <span data-ttu-id="f7f85-112">IWebView2Environment が安定していない場合は、チャネル名を含む現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="f7f85-112">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

<span data-ttu-id="f7f85-113">詳細については、 [IWebView2Environment](IWebView2Environment.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7f85-113">See the [IWebView2Environment](IWebView2Environment.md) interface for more details.</span></span> <span data-ttu-id="f7f85-114">このインターフェイスの QueryInterface は、 [IWebView2Environment](IWebView2Environment.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f7f85-114">You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="f7f85-115">Members</span><span class="sxs-lookup"><span data-stu-id="f7f85-115">Members</span></span>

#### <span data-ttu-id="f7f85-116">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="f7f85-116">get_BrowserVersionInfo</span></span> 

<span data-ttu-id="f7f85-117">IWebView2Environment が安定していない場合は、チャネル名を含む現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="f7f85-117">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="f7f85-118">パブリック HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span><span class="sxs-lookup"><span data-stu-id="f7f85-118">public HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="f7f85-119">これは、GetWebView2BrowserVersionInfo API の形式と一致します。</span><span class="sxs-lookup"><span data-stu-id="f7f85-119">This matches the format of the GetWebView2BrowserVersionInfo API.</span></span> <span data-ttu-id="f7f85-120">チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。</span><span class="sxs-lookup"><span data-stu-id="f7f85-120">Channel names are 'beta', 'dev', and 'canary'.</span></span>

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

