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
ms.openlocfilehash: 8ea9437530a7f64cc045bfbaa1cc3cc55da77732
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698142"
---
# <span data-ttu-id="a25e3-104">インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="a25e3-104">interface ICoreWebView2SourceChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="a25e3-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a25e3-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="a25e3-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a25e3-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="a25e3-107">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="a25e3-107">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="a25e3-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a25e3-108">Summary</span></span>

 <span data-ttu-id="a25e3-109">Members</span><span class="sxs-lookup"><span data-stu-id="a25e3-109">Members</span></span>                        | <span data-ttu-id="a25e3-110">説明</span><span class="sxs-lookup"><span data-stu-id="a25e3-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a25e3-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="a25e3-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="a25e3-112">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="a25e3-112">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="a25e3-113">Members</span><span class="sxs-lookup"><span data-stu-id="a25e3-113">Members</span></span>

#### <span data-ttu-id="a25e3-114">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="a25e3-114">get_IsNewDocument</span></span> 

<span data-ttu-id="a25e3-115">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="a25e3-115">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="a25e3-116">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="a25e3-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

