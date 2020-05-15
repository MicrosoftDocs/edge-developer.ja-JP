---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 480b79cce673be530219718fb7f4920f5d1e80ae
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654496"
---
# <span data-ttu-id="eac68-104">インターフェイス ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="eac68-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="eac68-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eac68-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="eac68-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eac68-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="eac68-107">呼び出し元は、このインターフェイスを実装して、ExecuteScript メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="eac68-107">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="eac68-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="eac68-108">Summary</span></span>

 <span data-ttu-id="eac68-109">Members</span><span class="sxs-lookup"><span data-stu-id="eac68-109">Members</span></span>                        | <span data-ttu-id="eac68-110">説明</span><span class="sxs-lookup"><span data-stu-id="eac68-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="eac68-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="eac68-111">Invoke</span></span>](#invoke) | <span data-ttu-id="eac68-112">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="eac68-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="eac68-113">Members</span><span class="sxs-lookup"><span data-stu-id="eac68-113">Members</span></span>

#### <span data-ttu-id="eac68-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="eac68-114">Invoke</span></span> 

<span data-ttu-id="eac68-115">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="eac68-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="eac68-116">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR resultObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="eac68-116">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR resultObjectAsJson)</span></span>

