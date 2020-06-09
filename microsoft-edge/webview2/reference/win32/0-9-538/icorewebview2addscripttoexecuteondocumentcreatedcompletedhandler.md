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
ms.openlocfilehash: 9777a27c1b9252d0d1a5f91a4692b9043fffc569
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699027"
---
# <span data-ttu-id="a8b21-104">インターフェイス ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="a8b21-104">interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span></span> 

```
interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
  : public IUnknown
```

<span data-ttu-id="a8b21-105">呼び出し元は、このインターフェイスを実装して AddScriptToExecuteOnDocumentCreated メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a8b21-105">The caller implements this interface to receive the result of the AddScriptToExecuteOnDocumentCreated method.</span></span>

## <span data-ttu-id="a8b21-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a8b21-106">Summary</span></span>

 <span data-ttu-id="a8b21-107">Members</span><span class="sxs-lookup"><span data-stu-id="a8b21-107">Members</span></span>                        | <span data-ttu-id="a8b21-108">説明</span><span class="sxs-lookup"><span data-stu-id="a8b21-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a8b21-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="a8b21-109">Invoke</span></span>](#invoke) | <span data-ttu-id="a8b21-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a8b21-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="a8b21-111">Members</span><span class="sxs-lookup"><span data-stu-id="a8b21-111">Members</span></span>

#### <span data-ttu-id="a8b21-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="a8b21-112">Invoke</span></span> 

<span data-ttu-id="a8b21-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a8b21-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="a8b21-114">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR id)</span><span class="sxs-lookup"><span data-stu-id="a8b21-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR id)</span></span>

