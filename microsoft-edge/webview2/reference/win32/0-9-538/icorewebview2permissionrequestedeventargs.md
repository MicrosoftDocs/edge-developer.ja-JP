---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2PermissionRequestedEventArgs
ms.openlocfilehash: b3178f3c012bc19b9221fbf6961ce0665245d551
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879339"
---
# <span data-ttu-id="e221d-104">インターフェイス ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e221d-104">interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="e221d-105">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="e221d-105">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="e221d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e221d-106">Summary</span></span>

 <span data-ttu-id="e221d-107">Members</span><span class="sxs-lookup"><span data-stu-id="e221d-107">Members</span></span>                        | <span data-ttu-id="e221d-108">説明</span><span class="sxs-lookup"><span data-stu-id="e221d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e221d-109">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="e221d-109">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="e221d-110">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e221d-110">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="e221d-111">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="e221d-111">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="e221d-112">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="e221d-112">The type of the permission that is requested.</span></span>
[<span data-ttu-id="e221d-113">get_State</span><span class="sxs-lookup"><span data-stu-id="e221d-113">get_State</span></span>](#get_state) | <span data-ttu-id="e221d-114">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="e221d-114">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="e221d-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="e221d-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="e221d-116">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="e221d-116">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="e221d-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="e221d-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="e221d-118">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="e221d-118">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="e221d-119">put_State</span><span class="sxs-lookup"><span data-stu-id="e221d-119">put_State</span></span>](#put_state) | <span data-ttu-id="e221d-120">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e221d-120">Set the State property.</span></span>

## <span data-ttu-id="e221d-121">Members</span><span class="sxs-lookup"><span data-stu-id="e221d-121">Members</span></span>

#### <span data-ttu-id="e221d-122">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="e221d-122">get_IsUserInitiated</span></span> 

<span data-ttu-id="e221d-123">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e221d-123">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="e221d-124">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="e221d-124">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="e221d-125">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e221d-125">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="e221d-126">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="e221d-126">get_PermissionKind</span></span> 

<span data-ttu-id="e221d-127">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="e221d-127">The type of the permission that is requested.</span></span>

> <span data-ttu-id="e221d-128">パブリック HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND \* 値)</span><span class="sxs-lookup"><span data-stu-id="e221d-128">public HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="e221d-129">get_State</span><span class="sxs-lookup"><span data-stu-id="e221d-129">get_State</span></span> 

<span data-ttu-id="e221d-130">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="e221d-130">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="e221d-131">パブリック HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE \* 値)</span><span class="sxs-lookup"><span data-stu-id="e221d-131">public HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="e221d-132">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="e221d-132">whether the request is granted.</span></span> <span data-ttu-id="e221d-133">既定値は COREWEBVIEW2_PERMISSION_STATE_DEFAULT です。</span><span class="sxs-lookup"><span data-stu-id="e221d-133">Default value is COREWEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="e221d-134">get_Uri</span><span class="sxs-lookup"><span data-stu-id="e221d-134">get_Uri</span></span> 

<span data-ttu-id="e221d-135">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="e221d-135">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="e221d-136">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="e221d-136">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="e221d-137">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="e221d-137">GetDeferral</span></span> 

<span data-ttu-id="e221d-138">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="e221d-138">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="e221d-139">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="e221d-139">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="e221d-140">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e221d-140">Developer can use the deferral object to make the permission decision at a later time.</span></span>

#### <span data-ttu-id="e221d-141">put_State</span><span class="sxs-lookup"><span data-stu-id="e221d-141">put_State</span></span> 

<span data-ttu-id="e221d-142">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e221d-142">Set the State property.</span></span>

> <span data-ttu-id="e221d-143">パブリック HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE 値)</span><span class="sxs-lookup"><span data-stu-id="e221d-143">public HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE value)</span></span>

