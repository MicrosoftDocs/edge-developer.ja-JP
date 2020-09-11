---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
ms.openlocfilehash: 4cd8f4ab3904bd1a8c2277ba012bb5e6c32cf1d9
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011126"
---
# <span data-ttu-id="f2869-104">0.9.579-インターフェイス ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="f2869-104">0.9.579 - interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="f2869-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Environment 経由で作成された WebView2Environment を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f2869-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="f2869-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f2869-106">Summary</span></span>

 <span data-ttu-id="f2869-107">Members</span><span class="sxs-lookup"><span data-stu-id="f2869-107">Members</span></span>                        | <span data-ttu-id="f2869-108">説明</span><span class="sxs-lookup"><span data-stu-id="f2869-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f2869-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f2869-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f2869-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f2869-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="f2869-111">Members</span><span class="sxs-lookup"><span data-stu-id="f2869-111">Members</span></span>

#### <span data-ttu-id="f2869-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="f2869-112">Invoke</span></span> 

<span data-ttu-id="f2869-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f2869-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="f2869-114">パブリック HRESULT [呼び出し](#invoke)(hresult Result、 [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span><span class="sxs-lookup"><span data-stu-id="f2869-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span></span>

