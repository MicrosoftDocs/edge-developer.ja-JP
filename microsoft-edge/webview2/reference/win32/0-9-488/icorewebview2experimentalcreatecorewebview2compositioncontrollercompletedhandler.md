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
ms.openlocfilehash: 91c4e7885526def5de6fd1910a4a6f06c6a6953a
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654258"
---
# <span data-ttu-id="27c69-104">インターフェイス ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="27c69-104">interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="27c69-105">これは、プレリリース SDK バージョン0.9.488 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="27c69-105">This an experimental API that is shipped with our prerelease SDK version 0.9.488.</span></span>

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="27c69-106">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2CompositionController 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="27c69-106">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2CompositionController.</span></span>

## <span data-ttu-id="27c69-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="27c69-107">Summary</span></span>

 <span data-ttu-id="27c69-108">Members</span><span class="sxs-lookup"><span data-stu-id="27c69-108">Members</span></span>                        | <span data-ttu-id="27c69-109">説明</span><span class="sxs-lookup"><span data-stu-id="27c69-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="27c69-110">Invoke</span><span class="sxs-lookup"><span data-stu-id="27c69-110">Invoke</span></span>](#invoke) | <span data-ttu-id="27c69-111">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="27c69-111">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="27c69-112">Members</span><span class="sxs-lookup"><span data-stu-id="27c69-112">Members</span></span>

#### <span data-ttu-id="27c69-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="27c69-113">Invoke</span></span> 

<span data-ttu-id="27c69-114">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="27c69-114">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="27c69-115">パブリック HRESULT[呼び出し](#invoke)(hresult Result、 [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span><span class="sxs-lookup"><span data-stu-id="27c69-115">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span></span>

