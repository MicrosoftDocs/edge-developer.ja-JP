---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 88f5008dbc9a4ebfccfe96299899a2474ecc6d95
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880410"
---
# <span data-ttu-id="85712-104">0.9.515-インターフェイス ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="85712-104">0.9.515 - interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="85712-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85712-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="85712-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85712-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="85712-107">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="85712-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="85712-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="85712-108">Summary</span></span>

 <span data-ttu-id="85712-109">Members</span><span class="sxs-lookup"><span data-stu-id="85712-109">Members</span></span>                        | <span data-ttu-id="85712-110">説明</span><span class="sxs-lookup"><span data-stu-id="85712-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="85712-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="85712-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="85712-112">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="85712-112">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="85712-113">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="85712-113">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="85712-114">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="85712-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="85712-115">get_State</span><span class="sxs-lookup"><span data-stu-id="85712-115">get_State</span></span>](#get_state) | <span data-ttu-id="85712-116">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="85712-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="85712-117">get_Uri</span><span class="sxs-lookup"><span data-stu-id="85712-117">get_Uri</span></span>](#get_uri) | <span data-ttu-id="85712-118">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="85712-118">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="85712-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="85712-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="85712-120">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="85712-120">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="85712-121">put_State</span><span class="sxs-lookup"><span data-stu-id="85712-121">put_State</span></span>](#put_state) | <span data-ttu-id="85712-122">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="85712-122">Set the State property.</span></span>

## <span data-ttu-id="85712-123">Members</span><span class="sxs-lookup"><span data-stu-id="85712-123">Members</span></span>

#### <span data-ttu-id="85712-124">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="85712-124">get_IsUserInitiated</span></span> 

<span data-ttu-id="85712-125">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="85712-125">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="85712-126">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="85712-126">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="85712-127">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="85712-127">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="85712-128">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="85712-128">get_PermissionKind</span></span> 

<span data-ttu-id="85712-129">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="85712-129">The type of the permission that is requested.</span></span>

> <span data-ttu-id="85712-130">パブリック HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND \* 値)</span><span class="sxs-lookup"><span data-stu-id="85712-130">public HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="85712-131">get_State</span><span class="sxs-lookup"><span data-stu-id="85712-131">get_State</span></span> 

<span data-ttu-id="85712-132">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="85712-132">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="85712-133">パブリック HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE \* 値)</span><span class="sxs-lookup"><span data-stu-id="85712-133">public HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="85712-134">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="85712-134">whether the request is granted.</span></span> <span data-ttu-id="85712-135">既定値は COREWEBVIEW2_PERMISSION_STATE_DEFAULT です。</span><span class="sxs-lookup"><span data-stu-id="85712-135">Default value is COREWEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="85712-136">get_Uri</span><span class="sxs-lookup"><span data-stu-id="85712-136">get_Uri</span></span> 

<span data-ttu-id="85712-137">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="85712-137">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="85712-138">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="85712-138">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="85712-139">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="85712-139">GetDeferral</span></span> 

<span data-ttu-id="85712-140">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="85712-140">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="85712-141">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="85712-141">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="85712-142">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="85712-142">Developer can use the deferral object to make the permission decision at a later time.</span></span>

#### <span data-ttu-id="85712-143">put_State</span><span class="sxs-lookup"><span data-stu-id="85712-143">put_State</span></span> 

<span data-ttu-id="85712-144">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="85712-144">Set the State property.</span></span>

> <span data-ttu-id="85712-145">パブリック HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE 値)</span><span class="sxs-lookup"><span data-stu-id="85712-145">public HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE value)</span></span>

