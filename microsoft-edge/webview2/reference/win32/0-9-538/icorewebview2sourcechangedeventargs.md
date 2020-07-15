---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2SourceChangedEventArgs
ms.openlocfilehash: 3e622a8fb5b8ed43e5a23eaab8bd0aa61ed7d193
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879402"
---
# <span data-ttu-id="4d878-104">インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="4d878-104">interface ICoreWebView2SourceChangedEventArgs</span></span> 

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="4d878-105">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="4d878-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="4d878-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4d878-106">Summary</span></span>

 <span data-ttu-id="4d878-107">Members</span><span class="sxs-lookup"><span data-stu-id="4d878-107">Members</span></span>                        | <span data-ttu-id="4d878-108">説明</span><span class="sxs-lookup"><span data-stu-id="4d878-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4d878-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="4d878-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="4d878-110">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4d878-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="4d878-111">Members</span><span class="sxs-lookup"><span data-stu-id="4d878-111">Members</span></span>

#### <span data-ttu-id="4d878-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="4d878-112">get_IsNewDocument</span></span> 

<span data-ttu-id="4d878-113">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4d878-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="4d878-114">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="4d878-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

