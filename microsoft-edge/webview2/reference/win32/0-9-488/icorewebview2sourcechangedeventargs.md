---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9a98e2afa5b15452d7521183abebc019d51e3a3c
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885458"
---
# <span data-ttu-id="a0014-104">0.9.515-インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="a0014-104">0.9.515 - interface ICoreWebView2SourceChangedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="a0014-105">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="a0014-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="a0014-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a0014-106">Summary</span></span>

 <span data-ttu-id="a0014-107">Members</span><span class="sxs-lookup"><span data-stu-id="a0014-107">Members</span></span>                        | <span data-ttu-id="a0014-108">説明</span><span class="sxs-lookup"><span data-stu-id="a0014-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a0014-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="a0014-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="a0014-110">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="a0014-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="a0014-111">Members</span><span class="sxs-lookup"><span data-stu-id="a0014-111">Members</span></span>

#### <span data-ttu-id="a0014-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="a0014-112">get_IsNewDocument</span></span> 

<span data-ttu-id="a0014-113">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="a0014-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="a0014-114">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="a0014-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

