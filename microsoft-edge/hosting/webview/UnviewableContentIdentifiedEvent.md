---
description: Webview がサポートされていないファイルをダウンロードしようとしていることを示します。
title: UnviewableContentIdentifiedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/25/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: cec85ca2d5458a05cfd88210907523f25fb4af95
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568759"
---
# <span data-ttu-id="35f4e-104">UnviewableContentIdentifiedEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="35f4e-104">UnviewableContentIdentifiedEvent object</span></span>

<span data-ttu-id="35f4e-105">[Webview](../webview.md)が、サポートされていないコンテンツタイプのファイルに移動しようとしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="35f4e-105">Indicates the [webview](../webview.md) is attempting to navigate to a file of an unsupported content type.</span></span> 

## <span data-ttu-id="35f4e-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="35f4e-106">Properties</span></span>

### <span data-ttu-id="35f4e-107">メディア</span><span class="sxs-lookup"><span data-stu-id="35f4e-107">mediaType</span></span>

<span data-ttu-id="35f4e-108">Unviewable コンテンツのコンテンツタイプを取得します。</span><span class="sxs-lookup"><span data-stu-id="35f4e-108">Gets the content type of the unviewable content.</span></span>

<span data-ttu-id="35f4e-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="35f4e-109">This property is read-only</span></span>

```js
var mediaType = UnviewableContentIdentifiedEvent.mediaType;
```

#### <span data-ttu-id="35f4e-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="35f4e-110">Property value</span></span>
<span data-ttu-id="35f4e-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="35f4e-111">Type: **DOMString**</span></span>

### <span data-ttu-id="35f4e-112">referer</span><span class="sxs-lookup"><span data-stu-id="35f4e-112">referer</span></span>

<span data-ttu-id="35f4e-113">ナビゲーションを要求している[webview](../webview.md)のページの Uniform resource IDENTIFIER (URI) です。</span><span class="sxs-lookup"><span data-stu-id="35f4e-113">The Uniform Resource Identifier (URI) of the page in the [webview](../webview.md) requesting navigation.</span></span>

<span data-ttu-id="35f4e-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="35f4e-114">This property is read-only.</span></span>


```js
var referer = NavigationEventWithReferrer.referer;
```

#### <span data-ttu-id="35f4e-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="35f4e-115">Property value</span></span>
<span data-ttu-id="35f4e-116">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="35f4e-116">Type: **DOMString**</span></span>

### <span data-ttu-id="35f4e-117">uri</span><span class="sxs-lookup"><span data-stu-id="35f4e-117">uri</span></span>

<span data-ttu-id="35f4e-118">ナビゲーションの送信先の Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="35f4e-118">The Uniform Resource Identifier (URI) of the destination of the navigation.</span></span>

<span data-ttu-id="35f4e-119">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="35f4e-119">This property is read-only.</span></span>

```js
var uri = NavigationEventWithReferrer.uri;
```

#### <span data-ttu-id="35f4e-120">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="35f4e-120">Property value</span></span>
<span data-ttu-id="35f4e-121">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="35f4e-121">Type: **DOMString**</span></span>
