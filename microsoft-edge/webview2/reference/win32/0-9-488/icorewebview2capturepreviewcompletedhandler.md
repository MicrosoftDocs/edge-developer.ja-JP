---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2CapturePreviewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 8a9e3c1c5d2e9b7053d09518e3086f9e038e181a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883925"
---
# <span data-ttu-id="8367d-104">0.9.515-インターフェイス ICoreWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="8367d-104">0.9.515 - interface ICoreWebView2CapturePreviewCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="8367d-105">呼び出し元は、このメソッドを実装して CapturePreview メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8367d-105">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="8367d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="8367d-106">Summary</span></span>

 <span data-ttu-id="8367d-107">Members</span><span class="sxs-lookup"><span data-stu-id="8367d-107">Members</span></span>                        | <span data-ttu-id="8367d-108">説明</span><span class="sxs-lookup"><span data-stu-id="8367d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8367d-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="8367d-109">Invoke</span></span>](#invoke) | <span data-ttu-id="8367d-110">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8367d-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="8367d-111">結果は、CapturePreview メソッド呼び出しで提供されたストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="8367d-111">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="8367d-112">Members</span><span class="sxs-lookup"><span data-stu-id="8367d-112">Members</span></span>

#### <span data-ttu-id="8367d-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="8367d-113">Invoke</span></span> 

<span data-ttu-id="8367d-114">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8367d-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="8367d-115">パブリック HRESULT[呼び出し](#invoke)(hresult 結果)</span><span class="sxs-lookup"><span data-stu-id="8367d-115">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

