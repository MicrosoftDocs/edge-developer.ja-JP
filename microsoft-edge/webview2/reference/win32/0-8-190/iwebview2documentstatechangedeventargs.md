---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2DocumentStateChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 2ef38857b06c14eb9808452a33fa23b24855f055
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878562"
---
# <span data-ttu-id="11fa3-104">0.8.355-インターフェイス IWebView2DocumentStateChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="11fa3-104">0.8.355 - interface IWebView2DocumentStateChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="11fa3-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11fa3-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="11fa3-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11fa3-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2DocumentStateChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="11fa3-107">DocumentStateChanged イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="11fa3-107">Event args for the DocumentStateChanged event.</span></span>

## <span data-ttu-id="11fa3-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="11fa3-108">Summary</span></span>

 <span data-ttu-id="11fa3-109">Members</span><span class="sxs-lookup"><span data-stu-id="11fa3-109">Members</span></span>                        | <span data-ttu-id="11fa3-110">説明</span><span class="sxs-lookup"><span data-stu-id="11fa3-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="11fa3-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="11fa3-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="11fa3-112">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="11fa3-112">True if the page being navigated to is a new document.</span></span>
[<span data-ttu-id="11fa3-113">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="11fa3-113">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="11fa3-114">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="11fa3-114">True if the loaded content is an error page.</span></span>

## <span data-ttu-id="11fa3-115">Members</span><span class="sxs-lookup"><span data-stu-id="11fa3-115">Members</span></span>

#### <span data-ttu-id="11fa3-116">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="11fa3-116">get_IsNewDocument</span></span> 

<span data-ttu-id="11fa3-117">移動先のページが新しい文書の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="11fa3-117">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="11fa3-118">パブリック HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* IsNewDocument)</span><span class="sxs-lookup"><span data-stu-id="11fa3-118">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

#### <span data-ttu-id="11fa3-119">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="11fa3-119">get_IsErrorPage</span></span> 

<span data-ttu-id="11fa3-120">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="11fa3-120">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="11fa3-121">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="11fa3-121">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

