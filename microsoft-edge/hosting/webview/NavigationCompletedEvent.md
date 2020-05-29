---
description: 完成した webview ナビゲーションに関する情報が含まれています。
title: NavigationCompletedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/26/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 11974f0c66d48569ee63c592bdd3b0153db075b1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569233"
---
# <span data-ttu-id="80554-104">NavigationCompletedEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="80554-104">NavigationCompletedEvent object</span></span>

<span data-ttu-id="80554-105">[Webview](../webview.md)が現在のコンテンツの読み込みを完了したとき、またはナビゲーションに失敗した場合に発生するイベントを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="80554-105">An object that represents an event fired when the [webview](../webview.md) has finished loading the current content or if navigation has failed.</span></span>

## <span data-ttu-id="80554-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="80554-106">Properties</span></span>
    
### <span data-ttu-id="80554-107">uri</span><span class="sxs-lookup"><span data-stu-id="80554-107">uri</span></span>

<span data-ttu-id="80554-108">ナビゲーションの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="80554-108">The Uniform Resource Identifier (URI) of the navigation.</span></span>

<span data-ttu-id="80554-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="80554-109">This property is read-only.</span></span>

```js
var uri = NavigationCompletedEvent.uri;
```

#### <span data-ttu-id="80554-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="80554-110">Property value</span></span>
<span data-ttu-id="80554-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="80554-111">Type: **DOMString**</span></span>

### <span data-ttu-id="80554-112">isSuccess</span><span class="sxs-lookup"><span data-stu-id="80554-112">isSuccess</span></span>

<span data-ttu-id="80554-113">ナビゲーションが正常に完了したかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="80554-113">Gets a value that indicates whether the navigation completed successfully.</span></span>

<span data-ttu-id="80554-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="80554-114">This property is read-only</span></span>

```js
var isSuccess = NavigationCompletedEvent.isSuccess;
```

#### <span data-ttu-id="80554-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="80554-115">Property value</span></span>
<span data-ttu-id="80554-116">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="80554-116">Type: **Boolean**</span></span>

### <span data-ttu-id="80554-117">webErrorStatus</span><span class="sxs-lookup"><span data-stu-id="80554-117">webErrorStatus</span></span>

<span data-ttu-id="80554-118">ナビゲーションに失敗した場合は、理由を示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="80554-118">If the navigation was unsuccessful, gets a value that indicates why.</span></span>

<span data-ttu-id="80554-119">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="80554-119">This property is read-only</span></span>

```js
var webErrorStatus = NavigationCompletedEvent.webErrorStatus;
```

#### <span data-ttu-id="80554-120">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="80554-120">Property value</span></span>
<span data-ttu-id="80554-121">種類:**符号なし長**</span><span class="sxs-lookup"><span data-stu-id="80554-121">Type: **unsigned long**</span></span>
