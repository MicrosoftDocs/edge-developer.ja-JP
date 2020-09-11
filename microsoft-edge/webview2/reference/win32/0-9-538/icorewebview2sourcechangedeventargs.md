---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2SourceChangedEventArgs
ms.openlocfilehash: b9350db7d59c0369bfb16d10e30a23ef3f6bffa5
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010461"
---
# <span data-ttu-id="1d3d0-104">0.9.579-インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="1d3d0-104">0.9.579 - interface ICoreWebView2SourceChangedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="1d3d0-105">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="1d3d0-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="1d3d0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="1d3d0-106">Summary</span></span>

 <span data-ttu-id="1d3d0-107">Members</span><span class="sxs-lookup"><span data-stu-id="1d3d0-107">Members</span></span>                        | <span data-ttu-id="1d3d0-108">説明</span><span class="sxs-lookup"><span data-stu-id="1d3d0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1d3d0-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="1d3d0-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="1d3d0-110">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="1d3d0-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="1d3d0-111">Members</span><span class="sxs-lookup"><span data-stu-id="1d3d0-111">Members</span></span>

#### <span data-ttu-id="1d3d0-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="1d3d0-112">get_IsNewDocument</span></span> 

<span data-ttu-id="1d3d0-113">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="1d3d0-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="1d3d0-114">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="1d3d0-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

