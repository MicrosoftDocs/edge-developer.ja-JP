---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
ms.openlocfilehash: 3ecafb8181b04032bf121a93af3771cfcad8fa91
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011168"
---
# <span data-ttu-id="f9654-104">0.9.579-インターフェイス ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="f9654-104">0.9.579 - interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="f9654-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Controller 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f9654-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="f9654-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f9654-106">Summary</span></span>

 <span data-ttu-id="f9654-107">Members</span><span class="sxs-lookup"><span data-stu-id="f9654-107">Members</span></span>                        | <span data-ttu-id="f9654-108">説明</span><span class="sxs-lookup"><span data-stu-id="f9654-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f9654-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f9654-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f9654-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f9654-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="f9654-111">Members</span><span class="sxs-lookup"><span data-stu-id="f9654-111">Members</span></span>

#### <span data-ttu-id="f9654-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="f9654-112">Invoke</span></span> 

<span data-ttu-id="f9654-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f9654-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="f9654-114">パブリック HRESULT [呼び出し](#invoke)(hresult Result, [ICoreWebView2Controller](icorewebview2controller.md) \* の生成コントローラー)</span><span class="sxs-lookup"><span data-stu-id="f9654-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

