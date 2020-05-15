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
ms.openlocfilehash: 5aeeebfc3d8434c096e6946e5161437809f207d3
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654187"
---
# <span data-ttu-id="d1961-104">WebView2 クラス (CoreWebView2PermissionRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="d1961-104">Microsoft.Web.WebView2.Core.CoreWebView2PermissionRequestedEventArgs class</span></span> 

<span data-ttu-id="d1961-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="d1961-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d1961-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1961-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d1961-107">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="d1961-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="d1961-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d1961-108">Summary</span></span>

 <span data-ttu-id="d1961-109">Members</span><span class="sxs-lookup"><span data-stu-id="d1961-109">Members</span></span>                        | <span data-ttu-id="d1961-110">説明</span><span class="sxs-lookup"><span data-stu-id="d1961-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d1961-111">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="d1961-111">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="d1961-112">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d1961-112">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="d1961-113">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="d1961-113">PermissionKind</span></span>](#permissionkind) | <span data-ttu-id="d1961-114">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="d1961-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="d1961-115">状態</span><span class="sxs-lookup"><span data-stu-id="d1961-115">State</span></span>](#state) | <span data-ttu-id="d1961-116">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="d1961-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="d1961-117">URI</span><span class="sxs-lookup"><span data-stu-id="d1961-117">Uri</span></span>](#uri) | <span data-ttu-id="d1961-118">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="d1961-118">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="d1961-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d1961-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="d1961-120">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="d1961-120">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="d1961-121">Members</span><span class="sxs-lookup"><span data-stu-id="d1961-121">Members</span></span>

#### <span data-ttu-id="d1961-122">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="d1961-122">IsUserInitiated</span></span> 

<span data-ttu-id="d1961-123">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d1961-123">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="d1961-124">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="d1961-124">public bool [IsUserInitiated](#isuserinitiated)</span></span>

<span data-ttu-id="d1961-125">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1961-125">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="d1961-126">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="d1961-126">PermissionKind</span></span> 

<span data-ttu-id="d1961-127">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="d1961-127">The type of the permission that is requested.</span></span>

> <span data-ttu-id="d1961-128">パブリック CoreWebView2PermissionKind [Permissionkind](#permissionkind)</span><span class="sxs-lookup"><span data-stu-id="d1961-128">public CoreWebView2PermissionKind [PermissionKind](#permissionkind)</span></span>

#### <span data-ttu-id="d1961-129">状態</span><span class="sxs-lookup"><span data-stu-id="d1961-129">State</span></span> 

<span data-ttu-id="d1961-130">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="d1961-130">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="d1961-131">パブリック CoreWebView2PermissionState の[状態](#state)</span><span class="sxs-lookup"><span data-stu-id="d1961-131">public CoreWebView2PermissionState [State](#state)</span></span>

<span data-ttu-id="d1961-132">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d1961-132">whether the request is granted.</span></span>

<span data-ttu-id="d1961-133">既定値は CoreWebView2PermissionState です。</span><span class="sxs-lookup"><span data-stu-id="d1961-133">Default value is CoreWebView2PermissionState.Default.</span></span>

#### <span data-ttu-id="d1961-134">URI</span><span class="sxs-lookup"><span data-stu-id="d1961-134">Uri</span></span> 

<span data-ttu-id="d1961-135">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="d1961-135">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="d1961-136">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="d1961-136">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="d1961-137">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d1961-137">GetDeferral</span></span> 

<span data-ttu-id="d1961-138">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="d1961-138">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="d1961-139">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="d1961-139">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="d1961-140">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d1961-140">Developer can use the deferral object to make the permission decision at a later time.</span></span>

