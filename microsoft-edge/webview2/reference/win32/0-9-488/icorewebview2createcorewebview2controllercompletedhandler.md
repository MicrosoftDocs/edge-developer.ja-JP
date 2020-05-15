---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 49b2baf825d65b97b4b1fa62d06b2f6d6b7bd26d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654443"
---
# <span data-ttu-id="957b8-104">インターフェイス ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="957b8-104">interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="957b8-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Controller 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="957b8-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="957b8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="957b8-106">Summary</span></span>

 <span data-ttu-id="957b8-107">Members</span><span class="sxs-lookup"><span data-stu-id="957b8-107">Members</span></span>                        | <span data-ttu-id="957b8-108">説明</span><span class="sxs-lookup"><span data-stu-id="957b8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="957b8-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="957b8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="957b8-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="957b8-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="957b8-111">Members</span><span class="sxs-lookup"><span data-stu-id="957b8-111">Members</span></span>

#### <span data-ttu-id="957b8-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="957b8-112">Invoke</span></span> 

<span data-ttu-id="957b8-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="957b8-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="957b8-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result, [ICoreWebView2Controller](icorewebview2controller.md) \* の生成コントローラー)</span><span class="sxs-lookup"><span data-stu-id="957b8-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

