---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 6d4c5e7893f9be78baca25e8976ca889ef9826c0
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654511"
---
# <span data-ttu-id="18ae5-104">インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="18ae5-104">interface ICoreWebView2SourceChangedEventArgs</span></span> 

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="18ae5-105">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="18ae5-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="18ae5-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="18ae5-106">Summary</span></span>

 <span data-ttu-id="18ae5-107">Members</span><span class="sxs-lookup"><span data-stu-id="18ae5-107">Members</span></span>                        | <span data-ttu-id="18ae5-108">説明</span><span class="sxs-lookup"><span data-stu-id="18ae5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="18ae5-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="18ae5-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="18ae5-110">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="18ae5-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="18ae5-111">Members</span><span class="sxs-lookup"><span data-stu-id="18ae5-111">Members</span></span>

#### <span data-ttu-id="18ae5-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="18ae5-112">get_IsNewDocument</span></span> 

<span data-ttu-id="18ae5-113">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="18ae5-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="18ae5-114">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="18ae5-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

