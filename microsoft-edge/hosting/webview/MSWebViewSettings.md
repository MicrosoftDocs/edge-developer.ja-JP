---
description: Webview 機能を有効または無効にするプロパティを定義します。
title: MSWebViewSettings オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/10/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 0e164e7eb44edc636201f283ec4bbe866a122b8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569234"
---
# <span data-ttu-id="b7df0-104">MSWebViewSettings オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b7df0-104">MSWebViewSettings object</span></span>

<span data-ttu-id="b7df0-105">[Webview](../webview.md)機能を有効または無効にするプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="b7df0-105">Defines properties that enable or disable [webview](../webview.md) features.</span></span>

## <span data-ttu-id="b7df0-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b7df0-106">Properties</span></span>

### <span data-ttu-id="b7df0-107">isIndexedDBEnabled</span><span class="sxs-lookup"><span data-stu-id="b7df0-107">isIndexedDBEnabled</span></span>

<span data-ttu-id="b7df0-108">[Webview](../webview.md)での IndexedDB の使用が許可されているかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b7df0-108">Gets or sets a value that indicates whether the use of IndexedDB is allowed in the [webview](../webview.md).</span></span>

```js
var isIndexedDBEnabled = MSWebViewSettings.isIndexedDBEnabled;
MSWebViewSettings.isIndexedDBEnabled = isIndexedDBEnabled;
```

#### <span data-ttu-id="b7df0-109">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="b7df0-109">Property value</span></span>
<span data-ttu-id="b7df0-110">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="b7df0-110">Type: **boolean**</span></span>

<span data-ttu-id="b7df0-111">**Webview**で IndexedDB が許可されている場合は**True** 。それ以外の場合は**false**です。</span><span class="sxs-lookup"><span data-stu-id="b7df0-111">**True** if IndexedDB is allowed in the **webview**; otherwise, **false**.</span></span> 

### <span data-ttu-id="b7df0-112">isJavaScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="b7df0-112">isJavaScriptEnabled</span></span>

<span data-ttu-id="b7df0-113">[Webview](../webview.md)で JavaScript の使用が許可されているかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b7df0-113">Gets or sets a value that indicates whether the use of JavaScript is allowed in the [webview](../webview.md).</span></span>

```js
var isJavaScriptEnabled = MSWebViewSettings.isJavaScriptEnabled;
MSWebViewSettings.isJavaScriptEnabled = isJavaScriptEnabled;
```

#### <span data-ttu-id="b7df0-114">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="b7df0-114">Property value</span></span>
<span data-ttu-id="b7df0-115">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="b7df0-115">Type: **boolean**</span></span>

<span data-ttu-id="b7df0-116">**True**[Webview](../webview.md)では JavaScript が許可されています。それ以外の場合は**false**です。</span><span class="sxs-lookup"><span data-stu-id="b7df0-116">**True** JavaScript is allowed in the [webview](../webview.md); otherwise, **false**.</span></span> 

### <span data-ttu-id="b7df0-117">isScriptNotifyAllowed</span><span class="sxs-lookup"><span data-stu-id="b7df0-117">isScriptNotifyAllowed</span></span>

<span data-ttu-id="b7df0-118">[Webview](../webview.md)で[scriptnotifyevent](ScriptNotifyEvent.md)の使用が許可されているかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b7df0-118">Gets or sets a value that indicates whether the use of [ScriptNotifyEvent](ScriptNotifyEvent.md) is allowed in the [webview](../webview.md).</span></span>

```js
var isScriptNotifyAllowed = MSWebViewSettings.isScriptNotifyAllowed;
MSWebViewSettings.isScriptNotifyAllowed = isScriptNotifyAllowed;
```

#### <span data-ttu-id="b7df0-119">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="b7df0-119">Property value</span></span>
<span data-ttu-id="b7df0-120">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="b7df0-120">Type: **boolean**</span></span>

<span data-ttu-id="b7df0-121">[Webview](../webview.md)では、 **True** [scriptnotifyevent](ScriptNotifyEvent.md)が許可されています。それ以外の場合は**false**です。</span><span class="sxs-lookup"><span data-stu-id="b7df0-121">**True** [ScriptNotifyEvent](ScriptNotifyEvent.md) is allowed in the [webview](../webview.md); otherwise, **false**.</span></span> 
