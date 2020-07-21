---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 を CoreWebView2CreationProperties します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/17/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft のように指定します。
ms.openlocfilehash: 04c80d3319c74d3461666b6f35fadd0481b45207
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885535"
---
# <span data-ttu-id="bd3f5-104">WebView2 クラスを CoreWebView2CreationProperties します。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-104">Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties class</span></span> 

<span data-ttu-id="bd3f5-105">名前空間: Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="bd3f5-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="bd3f5-106">アセンブリ: Microsoft.Web.WebView2.Wpf.dll</span><span class="sxs-lookup"><span data-stu-id="bd3f5-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties
  : public DependencyObject
```

<span data-ttu-id="bd3f5-107">このクラスは、CoreWebView2Environment を作成するために使用される最も一般的なパラメーターのバンドルです。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-107">This class is a bundle of the most common parameters used to create a CoreWebView2Environment.</span></span>

## <span data-ttu-id="bd3f5-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="bd3f5-108">Summary</span></span>

 <span data-ttu-id="bd3f5-109">Members</span><span class="sxs-lookup"><span data-stu-id="bd3f5-109">Members</span></span>                        | <span data-ttu-id="bd3f5-110">説明</span><span class="sxs-lookup"><span data-stu-id="bd3f5-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bd3f5-111">BrowserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="bd3f5-111">BrowserExecutableFolder</span></span>](#browserexecutablefolder) | <span data-ttu-id="bd3f5-112">このインスタンスで環境を作成するときに、CoreWebView2Environment の browserExecutableFolder パラメーターとして渡す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-112">Gets or sets the value to pass as the browserExecutableFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="bd3f5-113">言語</span><span class="sxs-lookup"><span data-stu-id="bd3f5-113">Language</span></span>](#language) | <span data-ttu-id="bd3f5-114">このインスタンスで環境を作成するときに、CoreWebView2Environment に渡される CoreWebView2EnvironmentOptions パラメーターの Language プロパティに使用する値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-114">Gets or sets the value to use for the Language property of the CoreWebView2EnvironmentOptions parameter passed to CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="bd3f5-115">UserDataFolder</span><span class="sxs-lookup"><span data-stu-id="bd3f5-115">UserDataFolder</span></span>](#userdatafolder) | <span data-ttu-id="bd3f5-116">このインスタンスで環境を作成するときに、CoreWebView2Environment の userDataFolder パラメーターとして渡す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-116">Gets or sets the value to pass as the userDataFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="bd3f5-117">CoreWebView2CreationProperties</span><span class="sxs-lookup"><span data-stu-id="bd3f5-117">CoreWebView2CreationProperties</span></span>](#corewebview2creationproperties) | <span data-ttu-id="bd3f5-118">すべてのプロパティの既定のデータを使用して、CoreWebView2CreationProperties の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-118">Creates a new instance of CoreWebView2CreationProperties with default data for all properties.</span></span>

<span data-ttu-id="bd3f5-119">この主な目的は、 [WebView2](microsoft-web-webview2-wpf-webview2.md)で暗黙的な初期化中に使用される環境をカスタマイズするために、 [WebView2 プロパティ](microsoft-web-webview2-wpf-webview2.md)に設定することです。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-119">Its main purpose is to be set to [WebView2.CreationProperties](microsoft-web-webview2-wpf-webview2.md) in order to customize the environment used by a [WebView2](microsoft-web-webview2-wpf-webview2.md) during implicit initialization.</span></span> <span data-ttu-id="bd3f5-120">また、一般的に使用される環境パラメーターを依存関係プロパティとして作成し、マークアップで使うことができる優れた WPF 統合ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-120">It is also a nice WPF integration utility which allows commonly used environment parameters to be dependency properties and be created and used in markup.</span></span>

<span data-ttu-id="bd3f5-121">このクラスは、可能なすべての環境のカスタマイズオプションを含めることを意図していません。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-121">This class isn't intended to contain all possible environment customization options.</span></span> <span data-ttu-id="bd3f5-122">WebView2 コントロールによって使用されている環境を完全に制御する必要がある場合[は、CoreWebView2Environment](microsoft-web-webview2-wpf-webview2.md)を使用して独自の環境を作成してから[WebView2](microsoft-web-webview2-wpf-webview2.md)に渡す*ことによっ*て、そのコントロールを明示的に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-122">If you need complete control over the environment used by a WebView2 control then you'll need to initialize the control explicitly by creating your own environment with CoreWebView2Environment.CreateAsync and passing it to [WebView2.EnsureCoreWebView2Async](microsoft-web-webview2-wpf-webview2.md)*before* you set the [WebView2.Source](microsoft-web-webview2-wpf-webview2.md) property to anything.</span></span> <span data-ttu-id="bd3f5-123">初期化の概要については、 [WebView2](microsoft-web-webview2-wpf-webview2.md)クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-123">See the [WebView2](microsoft-web-webview2-wpf-webview2.md) class documentation for an initialization overview.</span></span>

## <span data-ttu-id="bd3f5-124">Members</span><span class="sxs-lookup"><span data-stu-id="bd3f5-124">Members</span></span>

#### <span data-ttu-id="bd3f5-125">BrowserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="bd3f5-125">BrowserExecutableFolder</span></span> 

<span data-ttu-id="bd3f5-126">このインスタンスで環境を作成するときに、CoreWebView2Environment の browserExecutableFolder パラメーターとして渡す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-126">Gets or sets the value to pass as the browserExecutableFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="bd3f5-127">パブリック文字列[ブラウザーの Executablefolder](#browserexecutablefolder)</span><span class="sxs-lookup"><span data-stu-id="bd3f5-127">public string [BrowserExecutableFolder](#browserexecutablefolder)</span></span>

#### <span data-ttu-id="bd3f5-128">言語</span><span class="sxs-lookup"><span data-stu-id="bd3f5-128">Language</span></span> 

<span data-ttu-id="bd3f5-129">このインスタンスで環境を作成するときに、CoreWebView2Environment に渡される CoreWebView2EnvironmentOptions パラメーターの Language プロパティに使用する値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-129">Gets or sets the value to use for the Language property of the CoreWebView2EnvironmentOptions parameter passed to CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="bd3f5-130">公開文字列の[言語](#language)</span><span class="sxs-lookup"><span data-stu-id="bd3f5-130">public string [Language](#language)</span></span>

#### <span data-ttu-id="bd3f5-131">UserDataFolder</span><span class="sxs-lookup"><span data-stu-id="bd3f5-131">UserDataFolder</span></span> 

<span data-ttu-id="bd3f5-132">このインスタンスで環境を作成するときに、CoreWebView2Environment の userDataFolder パラメーターとして渡す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-132">Gets or sets the value to pass as the userDataFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="bd3f5-133">パブリック文字列[Userdatafolder](#userdatafolder)</span><span class="sxs-lookup"><span data-stu-id="bd3f5-133">public string [UserDataFolder](#userdatafolder)</span></span>

#### <span data-ttu-id="bd3f5-134">CoreWebView2CreationProperties</span><span class="sxs-lookup"><span data-stu-id="bd3f5-134">CoreWebView2CreationProperties</span></span> 

<span data-ttu-id="bd3f5-135">すべてのプロパティの既定のデータを使用して、CoreWebView2CreationProperties の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd3f5-135">Creates a new instance of CoreWebView2CreationProperties with default data for all properties.</span></span>

> <span data-ttu-id="bd3f5-136">パブリック[CoreWebView2CreationProperties](#corewebview2creationproperties)()</span><span class="sxs-lookup"><span data-stu-id="bd3f5-136">public [CoreWebView2CreationProperties](#corewebview2creationproperties)()</span></span>

