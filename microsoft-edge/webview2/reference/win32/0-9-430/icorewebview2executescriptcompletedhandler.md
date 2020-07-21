---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2ExecuteScriptCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 9a96e18b8c0b56cd75d4f0fe7b0c90c0634fe68b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884198"
---
# <span data-ttu-id="9d14d-104">0.9.430-インターフェイス ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="9d14d-104">0.9.430 - interface ICoreWebView2ExecuteScriptCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="9d14d-105">呼び出し元は、このインターフェイスを実装して、ExecuteScript メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9d14d-105">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="9d14d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="9d14d-106">Summary</span></span>

 <span data-ttu-id="9d14d-107">Members</span><span class="sxs-lookup"><span data-stu-id="9d14d-107">Members</span></span>                        | <span data-ttu-id="9d14d-108">説明</span><span class="sxs-lookup"><span data-stu-id="9d14d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9d14d-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="9d14d-109">Invoke</span></span>](#invoke) | <span data-ttu-id="9d14d-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9d14d-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="9d14d-111">Members</span><span class="sxs-lookup"><span data-stu-id="9d14d-111">Members</span></span>

#### <span data-ttu-id="9d14d-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="9d14d-112">Invoke</span></span> 

<span data-ttu-id="9d14d-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9d14d-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="9d14d-114">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR resultObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="9d14d-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR resultObjectAsJson)</span></span>

