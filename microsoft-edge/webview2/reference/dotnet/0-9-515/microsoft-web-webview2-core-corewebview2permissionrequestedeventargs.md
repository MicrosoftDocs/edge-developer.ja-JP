---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2PermissionRequestedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 22fc8ec74c8da0a0ff072cacf91a792b9246900f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879801"
---
# <span data-ttu-id="2cbdb-104">0.9.515 クラスの WebView2 クラス (CoreWebView2PermissionRequestedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="2cbdb-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2PermissionRequestedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="2cbdb-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="2cbdb-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="2cbdb-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="2cbdb-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="2cbdb-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="2cbdb-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="2cbdb-109">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-109">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="2cbdb-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="2cbdb-110">Summary</span></span>

 <span data-ttu-id="2cbdb-111">Members</span><span class="sxs-lookup"><span data-stu-id="2cbdb-111">Members</span></span>                        | <span data-ttu-id="2cbdb-112">説明</span><span class="sxs-lookup"><span data-stu-id="2cbdb-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2cbdb-113">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="2cbdb-113">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="2cbdb-114">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-114">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="2cbdb-115">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="2cbdb-115">PermissionKind</span></span>](#permissionkind) | <span data-ttu-id="2cbdb-116">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-116">The type of the permission that is requested.</span></span>
[<span data-ttu-id="2cbdb-117">状態</span><span class="sxs-lookup"><span data-stu-id="2cbdb-117">State</span></span>](#state) | <span data-ttu-id="2cbdb-118">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="2cbdb-118">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="2cbdb-119">URI</span><span class="sxs-lookup"><span data-stu-id="2cbdb-119">Uri</span></span>](#uri) | <span data-ttu-id="2cbdb-120">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-120">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="2cbdb-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="2cbdb-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="2cbdb-122">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-122">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="2cbdb-123">Members</span><span class="sxs-lookup"><span data-stu-id="2cbdb-123">Members</span></span>

#### <span data-ttu-id="2cbdb-124">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="2cbdb-124">IsUserInitiated</span></span> 

<span data-ttu-id="2cbdb-125">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-125">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="2cbdb-126">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="2cbdb-126">public bool [IsUserInitiated](#isuserinitiated)</span></span>

<span data-ttu-id="2cbdb-127">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-127">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="2cbdb-128">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="2cbdb-128">PermissionKind</span></span> 

<span data-ttu-id="2cbdb-129">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-129">The type of the permission that is requested.</span></span>

> <span data-ttu-id="2cbdb-130">パブリック CoreWebView2PermissionKind [Permissionkind](#permissionkind)</span><span class="sxs-lookup"><span data-stu-id="2cbdb-130">public CoreWebView2PermissionKind [PermissionKind](#permissionkind)</span></span>

#### <span data-ttu-id="2cbdb-131">状態</span><span class="sxs-lookup"><span data-stu-id="2cbdb-131">State</span></span> 

<span data-ttu-id="2cbdb-132">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="2cbdb-132">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="2cbdb-133">パブリック CoreWebView2PermissionState の[状態](#state)</span><span class="sxs-lookup"><span data-stu-id="2cbdb-133">public CoreWebView2PermissionState [State](#state)</span></span>

<span data-ttu-id="2cbdb-134">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-134">whether the request is granted.</span></span>

<span data-ttu-id="2cbdb-135">既定値は CoreWebView2PermissionState です。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-135">Default value is CoreWebView2PermissionState.Default.</span></span>

#### <span data-ttu-id="2cbdb-136">URI</span><span class="sxs-lookup"><span data-stu-id="2cbdb-136">Uri</span></span> 

<span data-ttu-id="2cbdb-137">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-137">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="2cbdb-138">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="2cbdb-138">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="2cbdb-139">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="2cbdb-139">GetDeferral</span></span> 

<span data-ttu-id="2cbdb-140">GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-140">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="2cbdb-141">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="2cbdb-141">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="2cbdb-142">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2cbdb-142">Developer can use the deferral object to make the permission decision at a later time.</span></span>

