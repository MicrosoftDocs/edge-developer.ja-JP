---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 55ada31485ef061bb3649fb5e2a2811358913dd7
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654248"
---
# <span data-ttu-id="df096-104">WebView2 クラス (EdgeNotFoundException クラス)</span><span class="sxs-lookup"><span data-stu-id="df096-104">Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

<span data-ttu-id="df096-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="df096-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="df096-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="df096-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="df096-107">エッジのインストールが見つからない場合にスローされる例外。</span><span class="sxs-lookup"><span data-stu-id="df096-107">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="df096-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="df096-108">Summary</span></span>

 <span data-ttu-id="df096-109">Members</span><span class="sxs-lookup"><span data-stu-id="df096-109">Members</span></span>                        | <span data-ttu-id="df096-110">説明</span><span class="sxs-lookup"><span data-stu-id="df096-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="df096-111">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="df096-111">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="df096-112">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="df096-112">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="df096-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="df096-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="df096-114">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="df096-114">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="df096-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="df096-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="df096-116">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="df096-116">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="df096-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="df096-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="df096-118">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="df096-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="df096-119">Members</span><span class="sxs-lookup"><span data-stu-id="df096-119">Members</span></span>

#### <span data-ttu-id="df096-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="df096-120">EdgeNotFoundException</span></span> 

<span data-ttu-id="df096-121">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="df096-121">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="df096-122">パブリック[EdgeNotFoundException](#edgenotfoundexception)()</span><span class="sxs-lookup"><span data-stu-id="df096-122">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="df096-123">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="df096-123">EdgeNotFoundException</span></span> 

<span data-ttu-id="df096-124">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="df096-124">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="df096-125">パブリック[EdgeNotFoundException](#edgenotfoundexception)(例外の内部)</span><span class="sxs-lookup"><span data-stu-id="df096-125">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="df096-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df096-126">Parameters</span></span>
* `inner` <span data-ttu-id="df096-127">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="df096-127">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="df096-128">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="df096-128">EdgeNotFoundException</span></span> 

<span data-ttu-id="df096-129">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="df096-129">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="df096-130">パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ)</span><span class="sxs-lookup"><span data-stu-id="df096-130">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="df096-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df096-131">Parameters</span></span>
* `message` <span data-ttu-id="df096-132">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="df096-132">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="df096-133">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="df096-133">EdgeNotFoundException</span></span> 

<span data-ttu-id="df096-134">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="df096-134">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="df096-135">パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ、例外の内部)</span><span class="sxs-lookup"><span data-stu-id="df096-135">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="df096-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df096-136">Parameters</span></span>
* `message` <span data-ttu-id="df096-137">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="df096-137">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="df096-138">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="df096-138">The exception that is the cause of the current exception.</span></span>

