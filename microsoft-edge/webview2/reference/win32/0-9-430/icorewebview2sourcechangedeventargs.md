---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 2eb2749b71cd9be9dfd25bb686b4ea57e728f179
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883982"
---
# <span data-ttu-id="7847d-104">0.9.430-インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7847d-104">0.9.430 - interface ICoreWebView2SourceChangedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="7847d-105">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="7847d-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="7847d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="7847d-106">Summary</span></span>

 <span data-ttu-id="7847d-107">Members</span><span class="sxs-lookup"><span data-stu-id="7847d-107">Members</span></span>                        | <span data-ttu-id="7847d-108">説明</span><span class="sxs-lookup"><span data-stu-id="7847d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7847d-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="7847d-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="7847d-110">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="7847d-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="7847d-111">Members</span><span class="sxs-lookup"><span data-stu-id="7847d-111">Members</span></span>

#### <span data-ttu-id="7847d-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="7847d-112">get_IsNewDocument</span></span> 

<span data-ttu-id="7847d-113">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="7847d-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="7847d-114">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="7847d-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

