---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2DocumentStateChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 75741c1ba1d835d1c26c7d1db0845071216e0705
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886123"
---
# <span data-ttu-id="9c6f8-104">0.8.355-インターフェイス IWebView2DocumentStateChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="9c6f8-104">0.8.355 - interface IWebView2DocumentStateChangedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2DocumentStateChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="9c6f8-105">DocumentStateChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="9c6f8-105">Event args for the DocumentStateChanged event.</span></span>

## <span data-ttu-id="9c6f8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="9c6f8-106">Summary</span></span>

 <span data-ttu-id="9c6f8-107">Members</span><span class="sxs-lookup"><span data-stu-id="9c6f8-107">Members</span></span>                        | <span data-ttu-id="9c6f8-108">説明</span><span class="sxs-lookup"><span data-stu-id="9c6f8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9c6f8-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="9c6f8-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="9c6f8-110">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9c6f8-110">True if the page being navigated to is a new document.</span></span>
[<span data-ttu-id="9c6f8-111">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="9c6f8-111">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="9c6f8-112">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9c6f8-112">True if the loaded content is an error page.</span></span>

## <span data-ttu-id="9c6f8-113">Members</span><span class="sxs-lookup"><span data-stu-id="9c6f8-113">Members</span></span>

#### <span data-ttu-id="9c6f8-114">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="9c6f8-114">get_IsNewDocument</span></span> 

<span data-ttu-id="9c6f8-115">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9c6f8-115">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="9c6f8-116">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="9c6f8-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

#### <span data-ttu-id="9c6f8-117">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="9c6f8-117">get_IsErrorPage</span></span> 

<span data-ttu-id="9c6f8-118">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9c6f8-118">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="9c6f8-119">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="9c6f8-119">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

