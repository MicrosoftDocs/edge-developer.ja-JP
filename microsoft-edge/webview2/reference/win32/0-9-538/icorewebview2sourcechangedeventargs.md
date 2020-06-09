---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 4ae58375f0158a3876b284e16a579149dc6db9a5
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699074"
---
# <span data-ttu-id="b3e0b-104">インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="b3e0b-104">interface ICoreWebView2SourceChangedEventArgs</span></span> 

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="b3e0b-105">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="b3e0b-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="b3e0b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b3e0b-106">Summary</span></span>

 <span data-ttu-id="b3e0b-107">Members</span><span class="sxs-lookup"><span data-stu-id="b3e0b-107">Members</span></span>                        | <span data-ttu-id="b3e0b-108">説明</span><span class="sxs-lookup"><span data-stu-id="b3e0b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b3e0b-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="b3e0b-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="b3e0b-110">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="b3e0b-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="b3e0b-111">Members</span><span class="sxs-lookup"><span data-stu-id="b3e0b-111">Members</span></span>

#### <span data-ttu-id="b3e0b-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="b3e0b-112">get_IsNewDocument</span></span> 

<span data-ttu-id="b3e0b-113">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="b3e0b-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="b3e0b-114">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="b3e0b-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

