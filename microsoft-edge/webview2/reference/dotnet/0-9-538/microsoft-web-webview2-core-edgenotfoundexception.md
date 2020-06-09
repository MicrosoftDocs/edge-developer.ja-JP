---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b7d738628d6627232780e003f126b45c0421d6f0
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698948"
---
# <span data-ttu-id="0fb70-104">WebView2 クラス (EdgeNotFoundException クラス)</span><span class="sxs-lookup"><span data-stu-id="0fb70-104">Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

<span data-ttu-id="0fb70-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="0fb70-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="0fb70-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="0fb70-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="0fb70-107">エッジのインストールが見つからない場合にスローされる例外。</span><span class="sxs-lookup"><span data-stu-id="0fb70-107">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="0fb70-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="0fb70-108">Summary</span></span>

 <span data-ttu-id="0fb70-109">Members</span><span class="sxs-lookup"><span data-stu-id="0fb70-109">Members</span></span>                        | <span data-ttu-id="0fb70-110">説明</span><span class="sxs-lookup"><span data-stu-id="0fb70-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0fb70-111">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="0fb70-111">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="0fb70-112">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="0fb70-112">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="0fb70-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="0fb70-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="0fb70-114">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="0fb70-114">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="0fb70-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="0fb70-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="0fb70-116">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="0fb70-116">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="0fb70-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="0fb70-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="0fb70-118">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="0fb70-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="0fb70-119">Members</span><span class="sxs-lookup"><span data-stu-id="0fb70-119">Members</span></span>

#### <span data-ttu-id="0fb70-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="0fb70-120">EdgeNotFoundException</span></span> 

<span data-ttu-id="0fb70-121">EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="0fb70-121">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="0fb70-122">パブリック[EdgeNotFoundException](#edgenotfoundexception)()</span><span class="sxs-lookup"><span data-stu-id="0fb70-122">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="0fb70-123">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="0fb70-123">EdgeNotFoundException</span></span> 

<span data-ttu-id="0fb70-124">この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="0fb70-124">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="0fb70-125">パブリック[EdgeNotFoundException](#edgenotfoundexception)(例外の内部)</span><span class="sxs-lookup"><span data-stu-id="0fb70-125">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="0fb70-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0fb70-126">Parameters</span></span>
* `inner` <span data-ttu-id="0fb70-127">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="0fb70-127">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="0fb70-128">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="0fb70-128">EdgeNotFoundException</span></span> 

<span data-ttu-id="0fb70-129">指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="0fb70-129">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="0fb70-130">パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ)</span><span class="sxs-lookup"><span data-stu-id="0fb70-130">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="0fb70-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0fb70-131">Parameters</span></span>
* `message` <span data-ttu-id="0fb70-132">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0fb70-132">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="0fb70-133">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="0fb70-133">EdgeNotFoundException</span></span> 

<span data-ttu-id="0fb70-134">指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="0fb70-134">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="0fb70-135">パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ、例外の内部)</span><span class="sxs-lookup"><span data-stu-id="0fb70-135">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="0fb70-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0fb70-136">Parameters</span></span>
* `message` <span data-ttu-id="0fb70-137">例外の理由を説明するエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0fb70-137">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="0fb70-138">現在の例外の原因である例外。</span><span class="sxs-lookup"><span data-stu-id="0fb70-138">The exception that is the cause of the current exception.</span></span>

