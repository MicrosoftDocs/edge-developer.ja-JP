---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 290d82666e5b9c5062132e1eb7515e39e2deb978
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699023"
---
# <span data-ttu-id="46e07-104">インターフェイス ICoreWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="46e07-104">interface ICoreWebView2CapturePreviewCompletedHandler</span></span> 

```
interface ICoreWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="46e07-105">呼び出し元は、このメソッドを実装して CapturePreview メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="46e07-105">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="46e07-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="46e07-106">Summary</span></span>

 <span data-ttu-id="46e07-107">Members</span><span class="sxs-lookup"><span data-stu-id="46e07-107">Members</span></span>                        | <span data-ttu-id="46e07-108">説明</span><span class="sxs-lookup"><span data-stu-id="46e07-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="46e07-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="46e07-109">Invoke</span></span>](#invoke) | <span data-ttu-id="46e07-110">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="46e07-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="46e07-111">結果は、CapturePreview メソッド呼び出しで提供されたストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="46e07-111">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="46e07-112">Members</span><span class="sxs-lookup"><span data-stu-id="46e07-112">Members</span></span>

#### <span data-ttu-id="46e07-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="46e07-113">Invoke</span></span> 

<span data-ttu-id="46e07-114">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="46e07-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="46e07-115">パブリック HRESULT[呼び出し](#invoke)(hresult 結果)</span><span class="sxs-lookup"><span data-stu-id="46e07-115">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

