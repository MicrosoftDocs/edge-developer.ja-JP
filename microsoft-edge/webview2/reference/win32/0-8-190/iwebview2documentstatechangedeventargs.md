---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 342716da2cded9c903f1edd13fb3400c779a9b39
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654408"
---
# <span data-ttu-id="f9b32-104">インターフェイス IWebView2DocumentStateChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="f9b32-104">interface IWebView2DocumentStateChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="f9b32-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f9b32-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="f9b32-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9b32-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2DocumentStateChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="f9b32-107">DocumentStateChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="f9b32-107">Event args for the DocumentStateChanged event.</span></span>

## <span data-ttu-id="f9b32-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="f9b32-108">Summary</span></span>

 <span data-ttu-id="f9b32-109">Members</span><span class="sxs-lookup"><span data-stu-id="f9b32-109">Members</span></span>                        | <span data-ttu-id="f9b32-110">説明</span><span class="sxs-lookup"><span data-stu-id="f9b32-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f9b32-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="f9b32-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="f9b32-112">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="f9b32-112">True if the page being navigated to is a new document.</span></span>
[<span data-ttu-id="f9b32-113">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f9b32-113">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="f9b32-114">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="f9b32-114">True if the loaded content is an error page.</span></span>

## <span data-ttu-id="f9b32-115">Members</span><span class="sxs-lookup"><span data-stu-id="f9b32-115">Members</span></span>

#### <span data-ttu-id="f9b32-116">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="f9b32-116">get_IsNewDocument</span></span> 

<span data-ttu-id="f9b32-117">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="f9b32-117">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="f9b32-118">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="f9b32-118">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

#### <span data-ttu-id="f9b32-119">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f9b32-119">get_IsErrorPage</span></span> 

<span data-ttu-id="f9b32-120">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="f9b32-120">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="f9b32-121">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="f9b32-121">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

