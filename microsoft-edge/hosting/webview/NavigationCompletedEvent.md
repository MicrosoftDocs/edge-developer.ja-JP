---
description: 完成した webview ナビゲーションに関する情報が含まれています。
title: NavigationCompletedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: eb5727ab59dbaf056f05ab4b19450c70f85d595f
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752140"
---
# <span data-ttu-id="86180-104">NavigationCompletedEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="86180-104">NavigationCompletedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="86180-105">[Webview](../webview.md)が現在のコンテンツの読み込みを完了したとき、またはナビゲーションに失敗した場合に発生するイベントを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="86180-105">An object that represents an event fired when the [webview](../webview.md) has finished loading the current content or if navigation has failed.</span></span>  

## <span data-ttu-id="86180-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="86180-106">Properties</span></span>  

### <span data-ttu-id="86180-107">uri</span><span class="sxs-lookup"><span data-stu-id="86180-107">uri</span></span>  

<span data-ttu-id="86180-108">ナビゲーションの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="86180-108">The Uniform Resource Identifier (URI) of the navigation.</span></span>  

<span data-ttu-id="86180-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="86180-109">This property is read-only.</span></span>  

```javascript
var uri = NavigationCompletedEvent.uri;
```  

#### <span data-ttu-id="86180-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="86180-110">Property value</span></span>  

<span data-ttu-id="86180-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="86180-111">Type: **DOMString**</span></span>  

### <span data-ttu-id="86180-112">isSuccess</span><span class="sxs-lookup"><span data-stu-id="86180-112">isSuccess</span></span>  

<span data-ttu-id="86180-113">ナビゲーションが正常に完了したかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="86180-113">Gets a value that indicates whether the navigation completed successfully.</span></span>  

<span data-ttu-id="86180-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="86180-114">This property is read-only.</span></span>  

```javascript
var isSuccess = NavigationCompletedEvent.isSuccess;
```  

#### <span data-ttu-id="86180-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="86180-115">Property value</span></span>  

<span data-ttu-id="86180-116">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="86180-116">Type: **Boolean**</span></span>  

### <span data-ttu-id="86180-117">webErrorStatus</span><span class="sxs-lookup"><span data-stu-id="86180-117">webErrorStatus</span></span>  

<span data-ttu-id="86180-118">ナビゲーションに失敗した場合は、理由を示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="86180-118">If the navigation was unsuccessful, gets a value that indicates why.</span></span>  

<span data-ttu-id="86180-119">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="86180-119">This property is read-only.</span></span>  

```javascript
var webErrorStatus = NavigationCompletedEvent.webErrorStatus;
```  

#### <span data-ttu-id="86180-120">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="86180-120">Property value</span></span>  

<span data-ttu-id="86180-121">種類:**符号なし長**</span><span class="sxs-lookup"><span data-stu-id="86180-121">Type: **unsigned long**</span></span>  
