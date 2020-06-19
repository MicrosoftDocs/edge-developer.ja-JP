---
description: ナビゲーションに関する参照情報が含まれています
title: NavigationEventWithReferrer 元オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 72c8a213f632e9e74145de9c34b949adf074cd22
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752129"
---
# <span data-ttu-id="b107b-104">NavigationEventWithReferrer 元オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b107b-104">NavigationEventWithReferrer object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="b107b-105">ナビゲーションが開始され、ナビゲーションに referer が含まれているときに発生するイベントを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b107b-105">An object that represents an event fired when navigation is initiated and the navigation contains a referer.</span></span>  

## <span data-ttu-id="b107b-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b107b-106">Properties</span></span>  

### <span data-ttu-id="b107b-107">referer</span><span class="sxs-lookup"><span data-stu-id="b107b-107">referer</span></span>

<span data-ttu-id="b107b-108">ナビゲーションを要求している[webview](../webview.md)のページの Uniform resource IDENTIFIER (URI) です。</span><span class="sxs-lookup"><span data-stu-id="b107b-108">The Uniform Resource Identifier (URI) of the page in the [webview](../webview.md) requesting navigation.</span></span>  

<span data-ttu-id="b107b-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b107b-109">This property is read-only.</span></span>  

#### <span data-ttu-id="b107b-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="b107b-110">Property value</span></span>  

<span data-ttu-id="b107b-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="b107b-111">Type: **DOMString**</span></span>  

```javascript
var referer = NavigationEventWithReferrer.referer;
```  

### <span data-ttu-id="b107b-112">uri</span><span class="sxs-lookup"><span data-stu-id="b107b-112">uri</span></span>  

<span data-ttu-id="b107b-113">ナビゲーションの送信先の Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="b107b-113">The Uniform Resource Identifier (URI) of the destination of the navigation.</span></span>  

<span data-ttu-id="b107b-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b107b-114">This property is read-only.</span></span>  

```javascript
var uri = NavigationEventWithReferrer.uri;
```  

#### <span data-ttu-id="b107b-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="b107b-115">Property value</span></span>  

<span data-ttu-id="b107b-116">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="b107b-116">Type: **DOMString**</span></span>  
