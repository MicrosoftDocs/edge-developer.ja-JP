---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2PermissionRequestedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 2bfa4559824c9bb397648249ead8fa8cb60c281c
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884632"
---
# <span data-ttu-id="8ebaf-104">0.9.515 クラスの WebView2 クラス (CoreWebView2PermissionRequestedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="8ebaf-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2PermissionRequestedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="8ebaf-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="8ebaf-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="8ebaf-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="8ebaf-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="8ebaf-107">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="8ebaf-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8ebaf-108">Summary</span></span>

 <span data-ttu-id="8ebaf-109">Members</span><span class="sxs-lookup"><span data-stu-id="8ebaf-109">Members</span></span>                        | <span data-ttu-id="8ebaf-110">説明</span><span class="sxs-lookup"><span data-stu-id="8ebaf-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8ebaf-111">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="8ebaf-111">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="8ebaf-112">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-112">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="8ebaf-113">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="8ebaf-113">PermissionKind</span></span>](#permissionkind) | <span data-ttu-id="8ebaf-114">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="8ebaf-115">状態</span><span class="sxs-lookup"><span data-stu-id="8ebaf-115">State</span></span>](#state) | <span data-ttu-id="8ebaf-116">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="8ebaf-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="8ebaf-117">URI</span><span class="sxs-lookup"><span data-stu-id="8ebaf-117">Uri</span></span>](#uri) | <span data-ttu-id="8ebaf-118">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-118">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="8ebaf-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8ebaf-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="8ebaf-120">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-120">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="8ebaf-121">Members</span><span class="sxs-lookup"><span data-stu-id="8ebaf-121">Members</span></span>

#### <span data-ttu-id="8ebaf-122">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="8ebaf-122">IsUserInitiated</span></span> 

<span data-ttu-id="8ebaf-123">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-123">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="8ebaf-124">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="8ebaf-124">public bool [IsUserInitiated](#isuserinitiated)</span></span>

<span data-ttu-id="8ebaf-125">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-125">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="8ebaf-126">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="8ebaf-126">PermissionKind</span></span> 

<span data-ttu-id="8ebaf-127">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-127">The type of the permission that is requested.</span></span>

> <span data-ttu-id="8ebaf-128">パブリック CoreWebView2PermissionKind [Permissionkind](#permissionkind)</span><span class="sxs-lookup"><span data-stu-id="8ebaf-128">public CoreWebView2PermissionKind [PermissionKind](#permissionkind)</span></span>

#### <span data-ttu-id="8ebaf-129">状態</span><span class="sxs-lookup"><span data-stu-id="8ebaf-129">State</span></span> 

<span data-ttu-id="8ebaf-130">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="8ebaf-130">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="8ebaf-131">パブリック CoreWebView2PermissionState の[状態](#state)</span><span class="sxs-lookup"><span data-stu-id="8ebaf-131">public CoreWebView2PermissionState [State](#state)</span></span>

<span data-ttu-id="8ebaf-132">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-132">whether the request is granted.</span></span>

<span data-ttu-id="8ebaf-133">既定値は CoreWebView2PermissionState です。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-133">Default value is CoreWebView2PermissionState.Default.</span></span>

#### <span data-ttu-id="8ebaf-134">URI</span><span class="sxs-lookup"><span data-stu-id="8ebaf-134">Uri</span></span> 

<span data-ttu-id="8ebaf-135">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-135">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="8ebaf-136">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="8ebaf-136">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="8ebaf-137">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8ebaf-137">GetDeferral</span></span> 

<span data-ttu-id="8ebaf-138">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-138">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="8ebaf-139">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="8ebaf-139">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="8ebaf-140">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8ebaf-140">Developer can use the deferral object to make the permission decision at a later time.</span></span>

