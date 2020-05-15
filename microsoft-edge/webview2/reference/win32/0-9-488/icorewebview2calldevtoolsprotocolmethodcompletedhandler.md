---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: fda3ab31405a7d6353af1a670a2804e973577c8e
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654372"
---
# <span data-ttu-id="a578c-104">インターフェイス ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="a578c-104">interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span></span> 

```
interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
  : public IUnknown
```

<span data-ttu-id="a578c-105">呼び出し元はこのインターフェイスを実装して、Calldevcompletion Protocolメソッドの完了結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a578c-105">The caller implements this interface to receive CallDevToolsProtocolMethod completion results.</span></span>

## <span data-ttu-id="a578c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a578c-106">Summary</span></span>

 <span data-ttu-id="a578c-107">Members</span><span class="sxs-lookup"><span data-stu-id="a578c-107">Members</span></span>                        | <span data-ttu-id="a578c-108">説明</span><span class="sxs-lookup"><span data-stu-id="a578c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a578c-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="a578c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="a578c-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a578c-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="a578c-111">Members</span><span class="sxs-lookup"><span data-stu-id="a578c-111">Members</span></span>

#### <span data-ttu-id="a578c-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="a578c-112">Invoke</span></span> 

<span data-ttu-id="a578c-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a578c-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="a578c-114">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR returnObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="a578c-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR returnObjectAsJson)</span></span>

