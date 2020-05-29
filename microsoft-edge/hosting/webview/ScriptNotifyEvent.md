---
description: Webview コンテンツからアプリケーションに渡される通知文字列を表します。
title: ScriptNotifyEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 22313f2d96ca2c5d4d3554ca40589b9a583c89cd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568760"
---
# <span data-ttu-id="861d5-104">ScriptNotifyEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="861d5-104">ScriptNotifyEvent object</span></span>

<span data-ttu-id="861d5-105">[Webview](../webview.md)に含まれるコンテンツが JavaScript を使って文字列をアプリケーションに渡すときに発生するイベントを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="861d5-105">An object that represents an event fired when content contained in the [webview](../webview.md) passes a string to the application by using JavaScript.</span></span>

## <span data-ttu-id="861d5-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="861d5-106">Properties</span></span>
    
### <span data-ttu-id="861d5-107">callingUri</span><span class="sxs-lookup"><span data-stu-id="861d5-107">callingUri</span></span>

<span data-ttu-id="861d5-108">**Scriptnotifyevent**を発生させたスクリプトが含まれているページの Uniform resource IDENTIFIER (URI) を取得します。</span><span class="sxs-lookup"><span data-stu-id="861d5-108">Gets the Uniform Resource Identifier (URI) of the page containing the script that raised the **ScriptNotifyEvent**.</span></span>

<span data-ttu-id="861d5-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="861d5-109">This property is read-only.</span></span>

```js
var callingUri = ScriptNotifyEvent.callingUri;
```

#### <span data-ttu-id="861d5-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="861d5-110">Property value</span></span>
<span data-ttu-id="861d5-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="861d5-111">Type: **DOMString**</span></span>

### <span data-ttu-id="861d5-112">value</span><span class="sxs-lookup"><span data-stu-id="861d5-112">value</span></span>

<span data-ttu-id="861d5-113">アプリケーションに渡されるメソッド名。</span><span class="sxs-lookup"><span data-stu-id="861d5-113">The method name as passed to the application.</span></span>

<span data-ttu-id="861d5-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="861d5-114">This property is read-only.</span></span>

```js
var value = ScriptNotifyEvent.value;
```

#### <span data-ttu-id="861d5-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="861d5-115">Property value</span></span>
<span data-ttu-id="861d5-116">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="861d5-116">Type: **DOMString**</span></span>