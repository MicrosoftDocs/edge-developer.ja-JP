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
ms.openlocfilehash: da7b12d382776bb1755e90b0ce1c2728b555c8c8
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654474"
---
# <span data-ttu-id="f1230-104">インターフェイス ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="f1230-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span></span> 

```
interface ICoreWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="f1230-105">呼び出し元は、このインターフェイスを実装して、ExecuteScript メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f1230-105">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="f1230-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f1230-106">Summary</span></span>

 <span data-ttu-id="f1230-107">Members</span><span class="sxs-lookup"><span data-stu-id="f1230-107">Members</span></span>                        | <span data-ttu-id="f1230-108">説明</span><span class="sxs-lookup"><span data-stu-id="f1230-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f1230-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f1230-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f1230-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f1230-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="f1230-111">Members</span><span class="sxs-lookup"><span data-stu-id="f1230-111">Members</span></span>

#### <span data-ttu-id="f1230-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="f1230-112">Invoke</span></span> 

<span data-ttu-id="f1230-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f1230-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="f1230-114">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR resultObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="f1230-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR resultObjectAsJson)</span></span>

