---
description: Webview ナビゲーションに関する情報が含まれています。
title: NavigationEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 1b3c9bd8f10c1f35a5ac518a54dd78ce96e201b5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569228"
---
# <span data-ttu-id="a16a1-104">NavigationEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a16a1-104">NavigationEvent object</span></span>

<span data-ttu-id="a16a1-105">ナビゲーションが開始されたときに発生するイベントを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a16a1-105">An object that represents an event fired when navigation is initiated.</span></span>

## <span data-ttu-id="a16a1-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a16a1-106">Properties</span></span>
    
### <span data-ttu-id="a16a1-107">uri</span><span class="sxs-lookup"><span data-stu-id="a16a1-107">uri</span></span>

<span data-ttu-id="a16a1-108">ターゲットの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="a16a1-108">The Uniform Resource Identifier (URI) of the target.</span></span>

<span data-ttu-id="a16a1-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a16a1-109">This property is read-only.</span></span>

```js
var uri = NavigationEvent.uri;
```

#### <span data-ttu-id="a16a1-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a16a1-110">Property value</span></span>
<span data-ttu-id="a16a1-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="a16a1-111">Type: **DOMString**</span></span>
