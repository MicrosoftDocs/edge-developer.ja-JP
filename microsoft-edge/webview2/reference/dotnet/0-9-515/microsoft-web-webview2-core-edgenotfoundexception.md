---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (EdgeNotFoundException の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: fc65d857f11a77a1d3629d40266f0453acadaa7b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886312"
---
# <span data-ttu-id="8f2dd-104">0.9.515 クラスの WebView2 クラス (EdgeNotFoundException)</span><span class="sxs-lookup"><span data-stu-id="8f2dd-104">0.9.515 - Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="8f2dd-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="8f2dd-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="8f2dd-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="8f2dd-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="8f2dd-107">エッジのインストールが見つからない場合にスローされる例外。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-107">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="8f2dd-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8f2dd-108">Summary</span></span>

 <span data-ttu-id="8f2dd-109">Members</span><span class="sxs-lookup"><span data-stu-id="8f2dd-109">Members</span></span>                        | <span data-ttu-id="8f2dd-110">説明</span><span class="sxs-lookup"><span data-stu-id="8f2dd-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8f2dd-111">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="8f2dd-111">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="8f2dd-112">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-112">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="8f2dd-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="8f2dd-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="8f2dd-114">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-114">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="8f2dd-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="8f2dd-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="8f2dd-116">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-116">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="8f2dd-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="8f2dd-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="8f2dd-118">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="8f2dd-119">Members</span><span class="sxs-lookup"><span data-stu-id="8f2dd-119">Members</span></span>

#### <span data-ttu-id="8f2dd-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="8f2dd-120">EdgeNotFoundException</span></span> 

<span data-ttu-id="8f2dd-121">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-121">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="8f2dd-122">パブリック[EdgeNotFoundException](#edgenotfoundexception)()</span><span class="sxs-lookup"><span data-stu-id="8f2dd-122">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="8f2dd-123">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="8f2dd-123">EdgeNotFoundException</span></span> 

<span data-ttu-id="8f2dd-124">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-124">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="8f2dd-125">パブリック[EdgeNotFoundException](#edgenotfoundexception)(例外の内部)</span><span class="sxs-lookup"><span data-stu-id="8f2dd-125">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="8f2dd-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f2dd-126">Parameters</span></span>
* `inner` <span data-ttu-id="8f2dd-127">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-127">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="8f2dd-128">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="8f2dd-128">EdgeNotFoundException</span></span> 

<span data-ttu-id="8f2dd-129">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-129">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="8f2dd-130">パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ)</span><span class="sxs-lookup"><span data-stu-id="8f2dd-130">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="8f2dd-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f2dd-131">Parameters</span></span>
* `message` <span data-ttu-id="8f2dd-132">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-132">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="8f2dd-133">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="8f2dd-133">EdgeNotFoundException</span></span> 

<span data-ttu-id="8f2dd-134">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-134">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="8f2dd-135">パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ、例外の内部)</span><span class="sxs-lookup"><span data-stu-id="8f2dd-135">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="8f2dd-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f2dd-136">Parameters</span></span>
* `message` <span data-ttu-id="8f2dd-137">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-137">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="8f2dd-138">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="8f2dd-138">The exception that is the cause of the current exception.</span></span>

