---
description: Webview 機能を有効または無効にするプロパティを定義します。
title: MSWebViewSettings オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 147f852f8fbcb2a748c00b472814e9cc45b9c9da
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752179"
---
# <span data-ttu-id="1b6c4-104">MSWebViewSettings オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1b6c4-104">MSWebViewSettings object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="1b6c4-105">[Webview](../webview.md)機能を有効または無効にするプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b6c4-105">Defines properties that enable or disable [webview](../webview.md) features.</span></span>  

## <span data-ttu-id="1b6c4-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1b6c4-106">Properties</span></span>  

### <span data-ttu-id="1b6c4-107">isIndexedDBEnabled</span><span class="sxs-lookup"><span data-stu-id="1b6c4-107">isIndexedDBEnabled</span></span>  

<span data-ttu-id="1b6c4-108">[Webview](../webview.md)での IndexedDB の使用が許可されているかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="1b6c4-108">Gets or sets a value that indicates whether the use of IndexedDB is allowed in the [webview](../webview.md).</span></span>  

```javascript
var isIndexedDBEnabled = MSWebViewSettings.isIndexedDBEnabled;
MSWebViewSettings.isIndexedDBEnabled = isIndexedDBEnabled;
```  

#### <span data-ttu-id="1b6c4-109">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="1b6c4-109">Property value</span></span>  

<span data-ttu-id="1b6c4-110">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="1b6c4-110">Type: **boolean**</span></span>  

<span data-ttu-id="1b6c4-111">**Webview**で IndexedDB が許可されている場合は**True** 。それ以外の場合は**false**です。</span><span class="sxs-lookup"><span data-stu-id="1b6c4-111">**True** if IndexedDB is allowed in the **webview**; otherwise, **false**.</span></span>  

### <span data-ttu-id="1b6c4-112">isJavaScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="1b6c4-112">isJavaScriptEnabled</span></span>  

<span data-ttu-id="1b6c4-113">[Webview](../webview.md)で JavaScript の使用が許可されているかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="1b6c4-113">Gets or sets a value that indicates whether the use of JavaScript is allowed in the [webview](../webview.md).</span></span>  

```javascript
var isJavaScriptEnabled = MSWebViewSettings.isJavaScriptEnabled;
MSWebViewSettings.isJavaScriptEnabled = isJavaScriptEnabled;
```  

#### <span data-ttu-id="1b6c4-114">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="1b6c4-114">Property value</span></span>  

<span data-ttu-id="1b6c4-115">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="1b6c4-115">Type: **boolean**</span></span>  

<span data-ttu-id="1b6c4-116">**True**[Webview](../webview.md)では JavaScript が許可されています。それ以外の場合は**false**です。</span><span class="sxs-lookup"><span data-stu-id="1b6c4-116">**True** JavaScript is allowed in the [webview](../webview.md); otherwise, **false**.</span></span>  

### <span data-ttu-id="1b6c4-117">isScriptNotifyAllowed</span><span class="sxs-lookup"><span data-stu-id="1b6c4-117">isScriptNotifyAllowed</span></span>  

<span data-ttu-id="1b6c4-118">[Webview](../webview.md)で[scriptnotifyevent](ScriptNotifyEvent.md)の使用が許可されているかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="1b6c4-118">Gets or sets a value that indicates whether the use of [ScriptNotifyEvent](ScriptNotifyEvent.md) is allowed in the [webview](../webview.md).</span></span>  

```javascript
var isScriptNotifyAllowed = MSWebViewSettings.isScriptNotifyAllowed;
MSWebViewSettings.isScriptNotifyAllowed = isScriptNotifyAllowed;
```  

#### <span data-ttu-id="1b6c4-119">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="1b6c4-119">Property value</span></span>  

<span data-ttu-id="1b6c4-120">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="1b6c4-120">Type: **boolean**</span></span>  

<span data-ttu-id="1b6c4-121">[Webview](../webview.md)では、 **True** [scriptnotifyevent](ScriptNotifyEvent.md)が許可されています。それ以外の場合は**false**です。</span><span class="sxs-lookup"><span data-stu-id="1b6c4-121">**True** [ScriptNotifyEvent](ScriptNotifyEvent.md) is allowed in the [webview](../webview.md); otherwise, **false**.</span></span>  
