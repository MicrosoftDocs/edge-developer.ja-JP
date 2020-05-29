---
description: ナビゲーションに関する参照情報が含まれています
title: NavigationEventWithReferrer 元オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/22/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: b11f60724387d996d0a730965602b5ead6a84145
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569227"
---
# <span data-ttu-id="6e8ec-104">NavigationEventWithReferrer 元オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6e8ec-104">NavigationEventWithReferrer object</span></span>

<span data-ttu-id="6e8ec-105">ナビゲーションが開始され、ナビゲーションに referer が含まれているときに発生するイベントを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6e8ec-105">An object that represents an event fired when navigation is initiated and the navigation contains a referer.</span></span>

## <span data-ttu-id="6e8ec-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6e8ec-106">Properties</span></span>

### <span data-ttu-id="6e8ec-107">referer</span><span class="sxs-lookup"><span data-stu-id="6e8ec-107">referer</span></span>

<span data-ttu-id="6e8ec-108">ナビゲーションを要求している[webview](../webview.md)のページの Uniform resource IDENTIFIER (URI) です。</span><span class="sxs-lookup"><span data-stu-id="6e8ec-108">The Uniform Resource Identifier (URI) of the page in the [webview](../webview.md) requesting navigation.</span></span>

<span data-ttu-id="6e8ec-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="6e8ec-109">This property is read-only.</span></span>

#### <span data-ttu-id="6e8ec-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="6e8ec-110">Property value</span></span>
<span data-ttu-id="6e8ec-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="6e8ec-111">Type: **DOMString**</span></span>


```js
var referer = NavigationEventWithReferrer.referer;
```

### <span data-ttu-id="6e8ec-112">uri</span><span class="sxs-lookup"><span data-stu-id="6e8ec-112">uri</span></span>

<span data-ttu-id="6e8ec-113">ナビゲーションの送信先の Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="6e8ec-113">The Uniform Resource Identifier (URI) of the destination of the navigation.</span></span>

<span data-ttu-id="6e8ec-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="6e8ec-114">This property is read-only.</span></span>

```js
var uri = NavigationEventWithReferrer.uri;
```

#### <span data-ttu-id="6e8ec-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="6e8ec-115">Property value</span></span>
<span data-ttu-id="6e8ec-116">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="6e8ec-116">Type: **DOMString**</span></span>
