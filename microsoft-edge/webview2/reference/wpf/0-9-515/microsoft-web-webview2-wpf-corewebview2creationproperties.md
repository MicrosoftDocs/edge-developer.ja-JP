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
ms.openlocfilehash: d2c3b3ee179dec217418241031142549d170e440
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654157"
---
# <span data-ttu-id="81b2b-104">WebView2 クラスを CoreWebView2CreationProperties します。</span><span class="sxs-lookup"><span data-stu-id="81b2b-104">Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties class</span></span> 

<span data-ttu-id="81b2b-105">名前空間: Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="81b2b-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="81b2b-106">"WebView2" というアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="81b2b-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties
  : public DependencyObject
```

<span data-ttu-id="81b2b-107">このクラスは、CoreWebView2Environment を作成するために使用される最も一般的なパラメーターのバンドルです。</span><span class="sxs-lookup"><span data-stu-id="81b2b-107">This class is a bundle of the most common parameters used to create a CoreWebView2Environment.</span></span>

## <span data-ttu-id="81b2b-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="81b2b-108">Summary</span></span>

 <span data-ttu-id="81b2b-109">Members</span><span class="sxs-lookup"><span data-stu-id="81b2b-109">Members</span></span>                        | <span data-ttu-id="81b2b-110">説明</span><span class="sxs-lookup"><span data-stu-id="81b2b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="81b2b-111">BrowserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="81b2b-111">BrowserExecutableFolder</span></span>](#browserexecutablefolder) | <span data-ttu-id="81b2b-112">このインスタンスで環境を作成するときに、CoreWebView2Environment の browserExecutableFolder パラメーターとして渡す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="81b2b-112">Gets or sets the value to pass as the browserExecutableFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="81b2b-113">言語</span><span class="sxs-lookup"><span data-stu-id="81b2b-113">Language</span></span>](#language) | <span data-ttu-id="81b2b-114">このインスタンスで環境を作成するときに、CoreWebView2Environment に渡される CoreWebView2EnvironmentOptions パラメーターの Language プロパティに使用する値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="81b2b-114">Gets or sets the value to use for the Language property of the CoreWebView2EnvironmentOptions parameter passed to CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="81b2b-115">UserDataFolder</span><span class="sxs-lookup"><span data-stu-id="81b2b-115">UserDataFolder</span></span>](#userdatafolder) | <span data-ttu-id="81b2b-116">このインスタンスで環境を作成するときに、CoreWebView2Environment の userDataFolder パラメーターとして渡す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="81b2b-116">Gets or sets the value to pass as the userDataFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="81b2b-117">CoreWebView2CreationProperties</span><span class="sxs-lookup"><span data-stu-id="81b2b-117">CoreWebView2CreationProperties</span></span>](#corewebview2creationproperties) | <span data-ttu-id="81b2b-118">すべてのプロパティの既定のデータを使用して、CoreWebView2CreationProperties の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="81b2b-118">Creates a new instance of CoreWebView2CreationProperties with default data for all properties.</span></span>

<span data-ttu-id="81b2b-119">この主な目的は、 [WebView2](microsoft-web-webview2-wpf-webview2.md)で暗黙的な初期化中に使用される環境をカスタマイズするために、 [WebView2 プロパティ](microsoft-web-webview2-wpf-webview2.md)に設定することです。</span><span class="sxs-lookup"><span data-stu-id="81b2b-119">Its main purpose is to be set to [WebView2.CreationProperties](microsoft-web-webview2-wpf-webview2.md) in order to customize the environment used by a [WebView2](microsoft-web-webview2-wpf-webview2.md) during implicit initialization.</span></span> <span data-ttu-id="81b2b-120">また、一般的に使用される環境パラメーターを依存関係プロパティとして作成し、マークアップで使うことができる優れた WPF 統合ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="81b2b-120">It is also a nice WPF integration utility which allows commonly used environment parameters to be dependency properties and be created and used in markup.</span></span>

<span data-ttu-id="81b2b-121">このクラスは、可能なすべての環境のカスタマイズオプションを含めることを意図していません。</span><span class="sxs-lookup"><span data-stu-id="81b2b-121">This class isn't intended to contain all possible environment customization options.</span></span> <span data-ttu-id="81b2b-122">WebView2 コントロールによって使用されている環境を完全に制御する必要がある場合[は、CoreWebView2Environment](microsoft-web-webview2-wpf-webview2.md)を使用して独自の環境を作成してから[WebView2](microsoft-web-webview2-wpf-webview2.md)に渡す*ことによっ*て、そのコントロールを明示的に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81b2b-122">If you need complete control over the environment used by a WebView2 control then you'll need to initialize the control explicitly by creating your own environment with CoreWebView2Environment.CreateAsync and passing it to [WebView2.EnsureCoreWebView2Async](microsoft-web-webview2-wpf-webview2.md)*before* you set the [WebView2.Source](microsoft-web-webview2-wpf-webview2.md) property to anything.</span></span> <span data-ttu-id="81b2b-123">初期化の概要については、 [WebView2](microsoft-web-webview2-wpf-webview2.md)クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81b2b-123">See the [WebView2](microsoft-web-webview2-wpf-webview2.md) class documentation for an initialization overview.</span></span>

## <span data-ttu-id="81b2b-124">Members</span><span class="sxs-lookup"><span data-stu-id="81b2b-124">Members</span></span>

#### <span data-ttu-id="81b2b-125">BrowserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="81b2b-125">BrowserExecutableFolder</span></span> 

<span data-ttu-id="81b2b-126">このインスタンスで環境を作成するときに、CoreWebView2Environment の browserExecutableFolder パラメーターとして渡す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="81b2b-126">Gets or sets the value to pass as the browserExecutableFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="81b2b-127">パブリック文字列[ブラウザーの Executablefolder](#browserexecutablefolder)</span><span class="sxs-lookup"><span data-stu-id="81b2b-127">public string [BrowserExecutableFolder](#browserexecutablefolder)</span></span>

#### <span data-ttu-id="81b2b-128">言語</span><span class="sxs-lookup"><span data-stu-id="81b2b-128">Language</span></span> 

<span data-ttu-id="81b2b-129">このインスタンスで環境を作成するときに、CoreWebView2Environment に渡される CoreWebView2EnvironmentOptions パラメーターの Language プロパティに使用する値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="81b2b-129">Gets or sets the value to use for the Language property of the CoreWebView2EnvironmentOptions parameter passed to CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="81b2b-130">公開文字列の[言語](#language)</span><span class="sxs-lookup"><span data-stu-id="81b2b-130">public string [Language](#language)</span></span>

#### <span data-ttu-id="81b2b-131">UserDataFolder</span><span class="sxs-lookup"><span data-stu-id="81b2b-131">UserDataFolder</span></span> 

<span data-ttu-id="81b2b-132">このインスタンスで環境を作成するときに、CoreWebView2Environment の userDataFolder パラメーターとして渡す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="81b2b-132">Gets or sets the value to pass as the userDataFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="81b2b-133">パブリック文字列[Userdatafolder](#userdatafolder)</span><span class="sxs-lookup"><span data-stu-id="81b2b-133">public string [UserDataFolder](#userdatafolder)</span></span>

#### <span data-ttu-id="81b2b-134">CoreWebView2CreationProperties</span><span class="sxs-lookup"><span data-stu-id="81b2b-134">CoreWebView2CreationProperties</span></span> 

<span data-ttu-id="81b2b-135">すべてのプロパティの既定のデータを使用して、CoreWebView2CreationProperties の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="81b2b-135">Creates a new instance of CoreWebView2CreationProperties with default data for all properties.</span></span>

> <span data-ttu-id="81b2b-136">パブリック[CoreWebView2CreationProperties](#corewebview2creationproperties)()</span><span class="sxs-lookup"><span data-stu-id="81b2b-136">public  [CoreWebView2CreationProperties](#corewebview2creationproperties)()</span></span>

