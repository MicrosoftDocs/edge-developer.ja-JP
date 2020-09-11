---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
ms.openlocfilehash: 9321f7912cb1217a3b6a28f322469ea12e5820dc
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010629"
---
# <span data-ttu-id="99114-104">0.9.579-インターフェイス ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="99114-104">0.9.579 - interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
  : public IUnknown
```

<span data-ttu-id="99114-105">呼び出し元は、このインターフェイスを実装して AddScriptToExecuteOnDocumentCreated メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="99114-105">The caller implements this interface to receive the result of the AddScriptToExecuteOnDocumentCreated method.</span></span>

## <span data-ttu-id="99114-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="99114-106">Summary</span></span>

 <span data-ttu-id="99114-107">Members</span><span class="sxs-lookup"><span data-stu-id="99114-107">Members</span></span>                        | <span data-ttu-id="99114-108">説明</span><span class="sxs-lookup"><span data-stu-id="99114-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="99114-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="99114-109">Invoke</span></span>](#invoke) | <span data-ttu-id="99114-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="99114-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="99114-111">Members</span><span class="sxs-lookup"><span data-stu-id="99114-111">Members</span></span>

#### <span data-ttu-id="99114-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="99114-112">Invoke</span></span> 

<span data-ttu-id="99114-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="99114-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="99114-114">パブリック HRESULT [呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR id)</span><span class="sxs-lookup"><span data-stu-id="99114-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR id)</span></span>

