---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 464192c119ddb7dd59ee7cb5981f172eb44dbb78
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885017"
---
# <span data-ttu-id="a3701-104">0.8.355-インターフェイス IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="a3701-104">0.8.355 - interface IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
  : public IUnknown
```

<span data-ttu-id="a3701-105">呼び出し元は、このインターフェイスを実装して AddScriptToExecuteOnDocumentCreated メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a3701-105">The caller implements this interface to receive the result of the AddScriptToExecuteOnDocumentCreated method.</span></span>

## <span data-ttu-id="a3701-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a3701-106">Summary</span></span>

 <span data-ttu-id="a3701-107">Members</span><span class="sxs-lookup"><span data-stu-id="a3701-107">Members</span></span>                        | <span data-ttu-id="a3701-108">説明</span><span class="sxs-lookup"><span data-stu-id="a3701-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a3701-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="a3701-109">Invoke</span></span>](#invoke) | <span data-ttu-id="a3701-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a3701-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="a3701-111">Members</span><span class="sxs-lookup"><span data-stu-id="a3701-111">Members</span></span>

#### <span data-ttu-id="a3701-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="a3701-112">Invoke</span></span> 

<span data-ttu-id="a3701-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a3701-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="a3701-114">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR id)</span><span class="sxs-lookup"><span data-stu-id="a3701-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR id)</span></span>

