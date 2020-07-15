---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について EdgeNotFoundException
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 EdgeNotFoundException。
ms.openlocfilehash: 09a930231fd7f6886108904f25f07bde5c76db73
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879619"
---
# <span data-ttu-id="72ef8-104">WebView2 クラス (EdgeNotFoundException クラス)</span><span class="sxs-lookup"><span data-stu-id="72ef8-104">Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

<span data-ttu-id="72ef8-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="72ef8-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="72ef8-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="72ef8-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="72ef8-107">エッジのインストールが見つからない場合にスローされる例外。</span><span class="sxs-lookup"><span data-stu-id="72ef8-107">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="72ef8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="72ef8-108">Summary</span></span>

 <span data-ttu-id="72ef8-109">Members</span><span class="sxs-lookup"><span data-stu-id="72ef8-109">Members</span></span>                        | <span data-ttu-id="72ef8-110">説明</span><span class="sxs-lookup"><span data-stu-id="72ef8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="72ef8-111">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="72ef8-111">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="72ef8-112">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="72ef8-112">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="72ef8-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="72ef8-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="72ef8-114">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="72ef8-114">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="72ef8-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="72ef8-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="72ef8-116">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="72ef8-116">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="72ef8-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="72ef8-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="72ef8-118">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="72ef8-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="72ef8-119">Members</span><span class="sxs-lookup"><span data-stu-id="72ef8-119">Members</span></span>

#### <span data-ttu-id="72ef8-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="72ef8-120">EdgeNotFoundException</span></span> 

<span data-ttu-id="72ef8-121">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="72ef8-121">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="72ef8-122">パブリック[EdgeNotFoundException](#edgenotfoundexception)()</span><span class="sxs-lookup"><span data-stu-id="72ef8-122">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="72ef8-123">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="72ef8-123">EdgeNotFoundException</span></span> 

<span data-ttu-id="72ef8-124">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="72ef8-124">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="72ef8-125">パブリック[EdgeNotFoundException](#edgenotfoundexception)(例外の内部)</span><span class="sxs-lookup"><span data-stu-id="72ef8-125">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="72ef8-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72ef8-126">Parameters</span></span>
* `inner` <span data-ttu-id="72ef8-127">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="72ef8-127">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="72ef8-128">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="72ef8-128">EdgeNotFoundException</span></span> 

<span data-ttu-id="72ef8-129">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="72ef8-129">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="72ef8-130">パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ)</span><span class="sxs-lookup"><span data-stu-id="72ef8-130">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="72ef8-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72ef8-131">Parameters</span></span>
* `message` <span data-ttu-id="72ef8-132">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="72ef8-132">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="72ef8-133">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="72ef8-133">EdgeNotFoundException</span></span> 

<span data-ttu-id="72ef8-134">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="72ef8-134">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="72ef8-135">パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ、例外の内部)</span><span class="sxs-lookup"><span data-stu-id="72ef8-135">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="72ef8-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72ef8-136">Parameters</span></span>
* `message` <span data-ttu-id="72ef8-137">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="72ef8-137">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="72ef8-138">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="72ef8-138">The exception that is the cause of the current exception.</span></span>

