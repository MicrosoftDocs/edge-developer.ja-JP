---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 3c34c75e62fd73530d338e618469e071648f2fcb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884345"
---
# <span data-ttu-id="ba2e6-104">0.9.430-インターフェイス ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="ba2e6-104">0.9.430 - interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
  : public IUnknown
```

<span data-ttu-id="ba2e6-105">呼び出し元は、このインターフェイスを実装して AddScriptToExecuteOnDocumentCreated メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ba2e6-105">The caller implements this interface to receive the result of the AddScriptToExecuteOnDocumentCreated method.</span></span>

## <span data-ttu-id="ba2e6-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="ba2e6-106">Summary</span></span>

 <span data-ttu-id="ba2e6-107">Members</span><span class="sxs-lookup"><span data-stu-id="ba2e6-107">Members</span></span>                        | <span data-ttu-id="ba2e6-108">説明</span><span class="sxs-lookup"><span data-stu-id="ba2e6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ba2e6-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="ba2e6-109">Invoke</span></span>](#invoke) | <span data-ttu-id="ba2e6-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ba2e6-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="ba2e6-111">Members</span><span class="sxs-lookup"><span data-stu-id="ba2e6-111">Members</span></span>

#### <span data-ttu-id="ba2e6-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="ba2e6-112">Invoke</span></span> 

<span data-ttu-id="ba2e6-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ba2e6-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="ba2e6-114">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR id)</span><span class="sxs-lookup"><span data-stu-id="ba2e6-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR id)</span></span>

