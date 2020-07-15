---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
ms.openlocfilehash: e26d711c24758f82d42067fa28e71bc6ac1177ad
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877414"
---
# <span data-ttu-id="1db16-104">インターフェイス ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="1db16-104">interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="1db16-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Controller 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1db16-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="1db16-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="1db16-106">Summary</span></span>

 <span data-ttu-id="1db16-107">Members</span><span class="sxs-lookup"><span data-stu-id="1db16-107">Members</span></span>                        | <span data-ttu-id="1db16-108">説明</span><span class="sxs-lookup"><span data-stu-id="1db16-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1db16-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="1db16-109">Invoke</span></span>](#invoke) | <span data-ttu-id="1db16-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1db16-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="1db16-111">Members</span><span class="sxs-lookup"><span data-stu-id="1db16-111">Members</span></span>

#### <span data-ttu-id="1db16-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="1db16-112">Invoke</span></span> 

<span data-ttu-id="1db16-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1db16-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="1db16-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result, [ICoreWebView2Controller](icorewebview2controller.md) \* の生成コントローラー)</span><span class="sxs-lookup"><span data-stu-id="1db16-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

