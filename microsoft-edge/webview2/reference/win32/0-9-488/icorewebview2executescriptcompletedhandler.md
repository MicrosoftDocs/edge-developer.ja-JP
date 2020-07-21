---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ExecuteScriptCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: da66c70724a6ce2c1102fcc2ef248963c11f0d1d
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885304"
---
# <span data-ttu-id="b627b-104">0.9.515-インターフェイス ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="b627b-104">0.9.515 - interface ICoreWebView2ExecuteScriptCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="b627b-105">呼び出し元は、このインターフェイスを実装して、ExecuteScript メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b627b-105">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="b627b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b627b-106">Summary</span></span>

 <span data-ttu-id="b627b-107">Members</span><span class="sxs-lookup"><span data-stu-id="b627b-107">Members</span></span>                        | <span data-ttu-id="b627b-108">説明</span><span class="sxs-lookup"><span data-stu-id="b627b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b627b-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="b627b-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b627b-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b627b-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="b627b-111">Members</span><span class="sxs-lookup"><span data-stu-id="b627b-111">Members</span></span>

#### <span data-ttu-id="b627b-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="b627b-112">Invoke</span></span> 

<span data-ttu-id="b627b-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b627b-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="b627b-114">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR resultObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="b627b-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR resultObjectAsJson)</span></span>

