---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2CapturePreviewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2CapturePreviewCompletedHandler
ms.openlocfilehash: e526b723f111d7212a5da4b25840c89b69eb2e52
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012200"
---
# <span data-ttu-id="268e2-104">インターフェイス ICoreWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="268e2-104">interface ICoreWebView2CapturePreviewCompletedHandler</span></span> 

```
interface ICoreWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="268e2-105">呼び出し元は、このメソッドを実装して CapturePreview メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="268e2-105">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="268e2-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="268e2-106">Summary</span></span>

 <span data-ttu-id="268e2-107">Members</span><span class="sxs-lookup"><span data-stu-id="268e2-107">Members</span></span>                        | <span data-ttu-id="268e2-108">説明</span><span class="sxs-lookup"><span data-stu-id="268e2-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="268e2-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="268e2-109">Invoke</span></span>](#invoke) | <span data-ttu-id="268e2-110">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="268e2-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="268e2-111">結果は、CapturePreview メソッド呼び出しで提供されたストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="268e2-111">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="268e2-112">Members</span><span class="sxs-lookup"><span data-stu-id="268e2-112">Members</span></span>

#### <span data-ttu-id="268e2-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="268e2-113">Invoke</span></span> 

<span data-ttu-id="268e2-114">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="268e2-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="268e2-115">パブリック HRESULT [呼び出し](#invoke)(hresult errorCode)</span><span class="sxs-lookup"><span data-stu-id="268e2-115">public HRESULT [Invoke](#invoke)(HRESULT errorCode)</span></span>

