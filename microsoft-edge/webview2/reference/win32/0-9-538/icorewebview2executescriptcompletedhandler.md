---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExecuteScriptCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExecuteScriptCompletedHandler
ms.openlocfilehash: ee59ef42852fc8f0b0529b9a3ca08e53972dee1a
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879941"
---
# <span data-ttu-id="c015c-104">インターフェイス ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="c015c-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span></span> 

```
interface ICoreWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="c015c-105">呼び出し元は、このインターフェイスを実装して、ExecuteScript メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c015c-105">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="c015c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="c015c-106">Summary</span></span>

 <span data-ttu-id="c015c-107">Members</span><span class="sxs-lookup"><span data-stu-id="c015c-107">Members</span></span>                        | <span data-ttu-id="c015c-108">説明</span><span class="sxs-lookup"><span data-stu-id="c015c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c015c-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="c015c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="c015c-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c015c-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="c015c-111">Members</span><span class="sxs-lookup"><span data-stu-id="c015c-111">Members</span></span>

#### <span data-ttu-id="c015c-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="c015c-112">Invoke</span></span> 

<span data-ttu-id="c015c-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c015c-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="c015c-114">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR resultObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="c015c-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR resultObjectAsJson)</span></span>

