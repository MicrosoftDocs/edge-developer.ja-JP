---
description: Webview ナビゲーションに関する情報が含まれています。
title: NavigationEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 785e9646ff400e7ad229046c7030b51420b1d9ad
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752172"
---
# <span data-ttu-id="ed8ef-104">NavigationEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ed8ef-104">NavigationEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="ed8ef-105">ナビゲーションが開始されたときに発生するイベントを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-105">An object that represents an event fired when navigation is initiated.</span></span>  

## <span data-ttu-id="ed8ef-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ed8ef-106">Properties</span></span>  

### <span data-ttu-id="ed8ef-107">uri</span><span class="sxs-lookup"><span data-stu-id="ed8ef-107">uri</span></span>  

<span data-ttu-id="ed8ef-108">ターゲットの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-108">The Uniform Resource Identifier (URI) of the target.</span></span>  

<span data-ttu-id="ed8ef-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-109">This property is read-only.</span></span>  

```javascript
var uri = NavigationEvent.uri;
```  

#### <span data-ttu-id="ed8ef-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="ed8ef-110">Property value</span></span>  

<span data-ttu-id="ed8ef-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="ed8ef-111">Type: **DOMString**</span></span>  
