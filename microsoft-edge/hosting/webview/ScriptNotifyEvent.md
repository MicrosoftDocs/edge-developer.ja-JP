---
description: Webview コンテンツからアプリケーションに渡される通知文字列を表します。
title: ScriptNotifyEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 164bfa7228b1f4ccf9817e4b7231361d090f1394
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752025"
---
# <span data-ttu-id="44ce8-104">ScriptNotifyEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="44ce8-104">ScriptNotifyEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="44ce8-105">[Webview](../webview.md)に含まれるコンテンツが JavaScript を使って文字列をアプリケーションに渡すときに発生するイベントを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="44ce8-105">An object that represents an event fired when content contained in the [webview](../webview.md) passes a string to the application by using JavaScript.</span></span>  

## <span data-ttu-id="44ce8-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="44ce8-106">Properties</span></span>  

### <span data-ttu-id="44ce8-107">callingUri</span><span class="sxs-lookup"><span data-stu-id="44ce8-107">callingUri</span></span>  

<span data-ttu-id="44ce8-108">**Scriptnotifyevent**を発生させたスクリプトが含まれているページの Uniform resource IDENTIFIER (URI) を取得します。</span><span class="sxs-lookup"><span data-stu-id="44ce8-108">Gets the Uniform Resource Identifier (URI) of the page containing the script that raised the **ScriptNotifyEvent**.</span></span>  

<span data-ttu-id="44ce8-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="44ce8-109">This property is read-only.</span></span>  

```javascript
var callingUri = ScriptNotifyEvent.callingUri;
```  

#### <span data-ttu-id="44ce8-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="44ce8-110">Property value</span></span>  

<span data-ttu-id="44ce8-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="44ce8-111">Type: **DOMString**</span></span>  

### <span data-ttu-id="44ce8-112">value</span><span class="sxs-lookup"><span data-stu-id="44ce8-112">value</span></span>  

<span data-ttu-id="44ce8-113">アプリケーションに渡されるメソッド名。</span><span class="sxs-lookup"><span data-stu-id="44ce8-113">The method name as passed to the application.</span></span>  

<span data-ttu-id="44ce8-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="44ce8-114">This property is read-only.</span></span>  

```javascript
var value = ScriptNotifyEvent.value;
```  

#### <span data-ttu-id="44ce8-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="44ce8-115">Property value</span></span>  

<span data-ttu-id="44ce8-116">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="44ce8-116">Type: **DOMString**</span></span>  
