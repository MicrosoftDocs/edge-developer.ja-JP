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
ms.openlocfilehash: 0cdb6dc17549022bac6ada366f5f54dd5b9b7e12
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654503"
---
# <span data-ttu-id="bc7e3-104">インターフェイス IWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="bc7e3-104">interface IWebView2CapturePreviewCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="bc7e3-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bc7e3-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="bc7e3-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc7e3-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="bc7e3-107">呼び出し元は、このメソッドを実装して CapturePreview メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="bc7e3-107">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="bc7e3-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="bc7e3-108">Summary</span></span>

 <span data-ttu-id="bc7e3-109">Members</span><span class="sxs-lookup"><span data-stu-id="bc7e3-109">Members</span></span>                        | <span data-ttu-id="bc7e3-110">説明</span><span class="sxs-lookup"><span data-stu-id="bc7e3-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bc7e3-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="bc7e3-111">Invoke</span></span>](#invoke) | <span data-ttu-id="bc7e3-112">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bc7e3-112">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="bc7e3-113">結果は、CapturePreview メソッド呼び出しで提供されたストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="bc7e3-113">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="bc7e3-114">Members</span><span class="sxs-lookup"><span data-stu-id="bc7e3-114">Members</span></span>

#### <span data-ttu-id="bc7e3-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="bc7e3-115">Invoke</span></span> 

<span data-ttu-id="bc7e3-116">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bc7e3-116">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="bc7e3-117">パブリック HRESULT[呼び出し](#invoke)(hresult 結果)</span><span class="sxs-lookup"><span data-stu-id="bc7e3-117">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

