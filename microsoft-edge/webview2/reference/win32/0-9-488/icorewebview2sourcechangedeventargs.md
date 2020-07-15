---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9ea8f860d637c5d9e49e68917d167380c0418b87
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877372"
---
# <span data-ttu-id="8b478-104">0.9.515-インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="8b478-104">0.9.515 - interface ICoreWebView2SourceChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="8b478-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b478-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="8b478-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b478-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="8b478-107">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="8b478-107">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="8b478-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8b478-108">Summary</span></span>

 <span data-ttu-id="8b478-109">Members</span><span class="sxs-lookup"><span data-stu-id="8b478-109">Members</span></span>                        | <span data-ttu-id="8b478-110">説明</span><span class="sxs-lookup"><span data-stu-id="8b478-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8b478-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="8b478-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="8b478-112">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8b478-112">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="8b478-113">Members</span><span class="sxs-lookup"><span data-stu-id="8b478-113">Members</span></span>

#### <span data-ttu-id="8b478-114">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="8b478-114">get_IsNewDocument</span></span> 

<span data-ttu-id="8b478-115">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8b478-115">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="8b478-116">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="8b478-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

