---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 8a9f1b1e44353796c6d3b57d3f4c6f3d4997aad5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880200"
---
# <span data-ttu-id="c7927-104">0.9.430-インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="c7927-104">0.9.430 - interface ICoreWebView2SourceChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="c7927-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7927-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="c7927-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7927-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="c7927-107">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="c7927-107">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="c7927-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="c7927-108">Summary</span></span>

 <span data-ttu-id="c7927-109">Members</span><span class="sxs-lookup"><span data-stu-id="c7927-109">Members</span></span>                        | <span data-ttu-id="c7927-110">説明</span><span class="sxs-lookup"><span data-stu-id="c7927-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c7927-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="c7927-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="c7927-112">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="c7927-112">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="c7927-113">Members</span><span class="sxs-lookup"><span data-stu-id="c7927-113">Members</span></span>

#### <span data-ttu-id="c7927-114">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="c7927-114">get_IsNewDocument</span></span> 

<span data-ttu-id="c7927-115">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="c7927-115">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="c7927-116">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="c7927-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

