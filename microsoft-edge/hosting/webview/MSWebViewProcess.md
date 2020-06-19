---
description: Webview プロセスを表します。
title: MSWebViewProcess オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: bb70b0e8eb12c7a7c23d71f01ea24e9084caa156
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752157"
---
# <span data-ttu-id="d27c1-104">MSWebViewProcess オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d27c1-104">MSWebViewProcess object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="d27c1-105">[Webview](../webview.md)プロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="d27c1-105">Represents a [webview](../webview.md) process.</span></span>  

```javascript
var wvprocess = new MSWebViewProcess();
```  

## <span data-ttu-id="d27c1-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d27c1-106">Properties</span></span>  

### <span data-ttu-id="d27c1-107">enterpriseId</span><span class="sxs-lookup"><span data-stu-id="d27c1-107">enterpriseId</span></span>  

<span data-ttu-id="d27c1-108">プロセスのエンタープライズ ID です。</span><span class="sxs-lookup"><span data-stu-id="d27c1-108">The enterprise ID of the process.</span></span>  

```js
var enterpriseId = wvprocess.enterpriseId;
```  

<span data-ttu-id="d27c1-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="d27c1-109">This property is read-only.</span></span>  

#### <span data-ttu-id="d27c1-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="d27c1-110">Property value</span></span>  

<span data-ttu-id="d27c1-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="d27c1-111">Type: **DOMString**</span></span>  

### <span data-ttu-id="d27c1-112">isPrivateNetworkClientServerCapabilityEnabled</span><span class="sxs-lookup"><span data-stu-id="d27c1-112">isPrivateNetworkClientServerCapabilityEnabled</span></span>  

<span data-ttu-id="d27c1-113">[Webview](../webview.md)プロセスの*プライベートネットワーク (クライアント & Server)* ユニバーサル Windows[アプリ機能の宣言](/windows/uwp/packaging/app-capability-declarations)がアプリマニフェストで有効になっているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d27c1-113">Gets a value indicating whether the [webview](../webview.md) process has the *Private Networks (Client & Server)* Universal Windows [App capability declaration](/windows/uwp/packaging/app-capability-declarations) enabled in the app manifest.</span></span>  

```javascript
var privateNetwork = wvprocess.isPrivateNetworkClientServerCapabilityEnabled;
```  

<span data-ttu-id="d27c1-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="d27c1-114">This property is read-only.</span></span>  

#### <span data-ttu-id="d27c1-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="d27c1-115">Property value</span></span>  

<span data-ttu-id="d27c1-116">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="d27c1-116">Type: **Boolean**</span></span>  

## <span data-ttu-id="d27c1-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="d27c1-117">Methods</span></span>  

### <span data-ttu-id="d27c1-118">CreateWebViewAsync</span><span class="sxs-lookup"><span data-stu-id="d27c1-118">CreateWebViewAsync</span></span>  

<span data-ttu-id="d27c1-119">特定のプロセスで[webview](../webview.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="d27c1-119">Creates a [webview](../webview.md) in a specific process.</span></span>  

```javascript
wvprocess.createWebviewAsync();
```  

#### <span data-ttu-id="d27c1-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="d27c1-120">Return value</span></span>  

<span data-ttu-id="d27c1-121">種類**`Promise<MSHTMLWebViewElement>`**</span><span class="sxs-lookup"><span data-stu-id="d27c1-121">Type: **`Promise<MSHTMLWebViewElement>`**</span></span>  

### <span data-ttu-id="d27c1-122">GetWebViews</span><span class="sxs-lookup"><span data-stu-id="d27c1-122">GetWebViews</span></span>  

<span data-ttu-id="d27c1-123">プロセス内でホストされている**Mswebviewprocess**オブジェクトのシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="d27c1-123">Returns a sequence of **MSWebViewProcess** objects hosted within the process.</span></span>  

#### <span data-ttu-id="d27c1-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="d27c1-124">Return value</span></span>  

<span data-ttu-id="d27c1-125">種類**`sequence<MSHTMLWebViewElement>`**</span><span class="sxs-lookup"><span data-stu-id="d27c1-125">Type: **`sequence<MSHTMLWebViewElement>`**</span></span>  

### <span data-ttu-id="d27c1-126">Terminate</span><span class="sxs-lookup"><span data-stu-id="d27c1-126">Terminate</span></span>  

<span data-ttu-id="d27c1-127">プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="d27c1-127">Terminates the process.</span></span>  

```javascript
wvprocess.terminate();
```  

#### <span data-ttu-id="d27c1-128">戻り値</span><span class="sxs-lookup"><span data-stu-id="d27c1-128">Return value</span></span>  

<span data-ttu-id="d27c1-129">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="d27c1-129">This method does not return a value.</span></span>  
