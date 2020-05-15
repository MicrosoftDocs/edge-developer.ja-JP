---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 69c569be7e712d0f5cfddbaa180419be8d475ad0
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654551"
---
# <span data-ttu-id="c984e-104">インターフェイス ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="c984e-104">interface ICoreWebView2SourceChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="c984e-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c984e-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="c984e-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c984e-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="c984e-107">SourceChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="c984e-107">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="c984e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="c984e-108">Summary</span></span>

 <span data-ttu-id="c984e-109">Members</span><span class="sxs-lookup"><span data-stu-id="c984e-109">Members</span></span>                        | <span data-ttu-id="c984e-110">説明</span><span class="sxs-lookup"><span data-stu-id="c984e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c984e-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="c984e-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="c984e-112">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="c984e-112">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="c984e-113">Members</span><span class="sxs-lookup"><span data-stu-id="c984e-113">Members</span></span>

#### <span data-ttu-id="c984e-114">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="c984e-114">get_IsNewDocument</span></span> 

<span data-ttu-id="c984e-115">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="c984e-115">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="c984e-116">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="c984e-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

