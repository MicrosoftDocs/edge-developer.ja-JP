---
description: Webview プロセスを表します。
title: MSWebViewProcess オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 7581f6da3a23295180c50f6d41cc282ce998b64e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569236"
---
# <span data-ttu-id="3076b-104">MSWebViewProcess オブジェクト</span><span class="sxs-lookup"><span data-stu-id="3076b-104">MSWebViewProcess object</span></span>

<span data-ttu-id="3076b-105">[Webview](../webview.md)プロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="3076b-105">Represents a [webview](../webview.md) process.</span></span>

```js
var wvprocess = new MSWebViewProcess();
```

## <span data-ttu-id="3076b-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3076b-106">Properties</span></span>

### <span data-ttu-id="3076b-107">enterpriseId</span><span class="sxs-lookup"><span data-stu-id="3076b-107">enterpriseId</span></span>

<span data-ttu-id="3076b-108">プロセスのエンタープライズ ID です。</span><span class="sxs-lookup"><span data-stu-id="3076b-108">The enterprise ID of the process.</span></span>

```js
var enterpriseId = wvprocess.enterpriseId;
```

<span data-ttu-id="3076b-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3076b-109">This property is read-only.</span></span>

#### <span data-ttu-id="3076b-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="3076b-110">Property value</span></span>
<span data-ttu-id="3076b-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="3076b-111">Type: **DOMString**</span></span>

### <span data-ttu-id="3076b-112">isPrivateNetworkClientServerCapabilityEnabled</span><span class="sxs-lookup"><span data-stu-id="3076b-112">isPrivateNetworkClientServerCapabilityEnabled</span></span>

<span data-ttu-id="3076b-113">[Webview](../webview.md)プロセスの*プライベートネットワーク (クライアント & Server)* ユニバーサル Windows[アプリ機能の宣言](/windows/uwp/packaging/app-capability-declarations)がアプリマニフェストで有効になっているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3076b-113">Gets a value indicating whether the [webview](../webview.md) process has the *Private Networks (Client & Server)* Universal Windows [App capability declaration](/windows/uwp/packaging/app-capability-declarations) enabled in the app manifest.</span></span>

```js
var privateNetwork = wvprocess.isPrivateNetworkClientServerCapabilityEnabled;
```

<span data-ttu-id="3076b-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3076b-114">This property is read-only.</span></span>

#### <span data-ttu-id="3076b-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="3076b-115">Property value</span></span>
<span data-ttu-id="3076b-116">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="3076b-116">Type: **Boolean**</span></span>

## <span data-ttu-id="3076b-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="3076b-117">Methods</span></span>

### <span data-ttu-id="3076b-118">CreateWebViewAsync</span><span class="sxs-lookup"><span data-stu-id="3076b-118">CreateWebViewAsync</span></span>

<span data-ttu-id="3076b-119">特定のプロセスで[webview](../webview.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="3076b-119">Creates a [webview](../webview.md) in a specific process.</span></span>

```js
wvprocess.createWebviewAsync();
```

#### <span data-ttu-id="3076b-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="3076b-120">Return value</span></span>

<span data-ttu-id="3076b-121">種類**`Promise<MSHTMLWebViewElement>`**</span><span class="sxs-lookup"><span data-stu-id="3076b-121">Type: **`Promise<MSHTMLWebViewElement>`**</span></span>

### <span data-ttu-id="3076b-122">GetWebViews</span><span class="sxs-lookup"><span data-stu-id="3076b-122">GetWebViews</span></span>

<span data-ttu-id="3076b-123">プロセス内でホストされている**Mswebviewprocess**オブジェクトのシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="3076b-123">Returns a sequence of **MSWebViewProcess** objects hosted within the process.</span></span>

#### <span data-ttu-id="3076b-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="3076b-124">Return value</span></span>

<span data-ttu-id="3076b-125">種類**`sequence<MSHTMLWebViewElement>`**</span><span class="sxs-lookup"><span data-stu-id="3076b-125">Type: **`sequence<MSHTMLWebViewElement>`**</span></span>

### <span data-ttu-id="3076b-126">Terminate</span><span class="sxs-lookup"><span data-stu-id="3076b-126">Terminate</span></span>

<span data-ttu-id="3076b-127">プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="3076b-127">Terminates the process.</span></span>

```js
wvprocess.terminate();
```

#### <span data-ttu-id="3076b-128">戻り値</span><span class="sxs-lookup"><span data-stu-id="3076b-128">Return value</span></span>

<span data-ttu-id="3076b-129">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="3076b-129">This method does not return a value.</span></span>
