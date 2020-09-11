---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (EdgeNotFoundException の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 EdgeNotFoundException。
ms.openlocfilehash: b4dc30ff741702d03796cb40e6ea6367ffdd0fc0
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010104"
---
# <span data-ttu-id="b529e-104">0.9.579 クラスの WebView2 クラス (EdgeNotFoundException)</span><span class="sxs-lookup"><span data-stu-id="b529e-104">0.9.579 - Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="b529e-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="b529e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="b529e-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="b529e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="b529e-107">エッジのインストールが見つからない場合にスローされる例外。</span><span class="sxs-lookup"><span data-stu-id="b529e-107">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="b529e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="b529e-108">Summary</span></span>

 <span data-ttu-id="b529e-109">Members</span><span class="sxs-lookup"><span data-stu-id="b529e-109">Members</span></span>                        | <span data-ttu-id="b529e-110">説明</span><span class="sxs-lookup"><span data-stu-id="b529e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b529e-111">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="b529e-111">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="b529e-112">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b529e-112">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="b529e-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="b529e-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="b529e-114">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b529e-114">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="b529e-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="b529e-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="b529e-116">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b529e-116">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="b529e-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="b529e-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="b529e-118">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b529e-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="b529e-119">Members</span><span class="sxs-lookup"><span data-stu-id="b529e-119">Members</span></span>

#### <span data-ttu-id="b529e-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="b529e-120">EdgeNotFoundException</span></span> 

<span data-ttu-id="b529e-121">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b529e-121">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="b529e-122">パブリック [EdgeNotFoundException](#edgenotfoundexception)()</span><span class="sxs-lookup"><span data-stu-id="b529e-122">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="b529e-123">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="b529e-123">EdgeNotFoundException</span></span> 

<span data-ttu-id="b529e-124">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b529e-124">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="b529e-125">パブリック [EdgeNotFoundException](#edgenotfoundexception)(例外の内部)</span><span class="sxs-lookup"><span data-stu-id="b529e-125">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="b529e-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b529e-126">Parameters</span></span>
* `inner` <span data-ttu-id="b529e-127">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="b529e-127">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="b529e-128">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="b529e-128">EdgeNotFoundException</span></span> 

<span data-ttu-id="b529e-129">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b529e-129">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="b529e-130">パブリック [EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ)</span><span class="sxs-lookup"><span data-stu-id="b529e-130">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="b529e-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b529e-131">Parameters</span></span>
* `message` <span data-ttu-id="b529e-132">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="b529e-132">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="b529e-133">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="b529e-133">EdgeNotFoundException</span></span> 

<span data-ttu-id="b529e-134">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b529e-134">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="b529e-135">パブリック [EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ、例外の内部)</span><span class="sxs-lookup"><span data-stu-id="b529e-135">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="b529e-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b529e-136">Parameters</span></span>
* `message` <span data-ttu-id="b529e-137">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="b529e-137">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="b529e-138">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="b529e-138">The exception that is the cause of the current exception.</span></span>

