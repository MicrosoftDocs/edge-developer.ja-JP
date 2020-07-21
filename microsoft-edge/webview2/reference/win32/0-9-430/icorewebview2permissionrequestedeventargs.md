---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: e29765a4b8a3e620b8c627c7b05b9f0b4ff63f95
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886417"
---
# <span data-ttu-id="e526c-104">0.9.430-インターフェイス ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e526c-104">0.9.430 - interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="e526c-105">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="e526c-105">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="e526c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e526c-106">Summary</span></span>

 <span data-ttu-id="e526c-107">Members</span><span class="sxs-lookup"><span data-stu-id="e526c-107">Members</span></span>                        | <span data-ttu-id="e526c-108">説明</span><span class="sxs-lookup"><span data-stu-id="e526c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e526c-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="e526c-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="e526c-110">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="e526c-110">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="e526c-111">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="e526c-111">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="e526c-112">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="e526c-112">The type of the permission that is requested.</span></span>
[<span data-ttu-id="e526c-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="e526c-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="e526c-114">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e526c-114">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="e526c-115">get_State</span><span class="sxs-lookup"><span data-stu-id="e526c-115">get_State</span></span>](#get_state) | <span data-ttu-id="e526c-116">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="e526c-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="e526c-117">put_State</span><span class="sxs-lookup"><span data-stu-id="e526c-117">put_State</span></span>](#put_state) | <span data-ttu-id="e526c-118">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e526c-118">Set the State property.</span></span>
[<span data-ttu-id="e526c-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="e526c-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="e526c-120">GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="e526c-120">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="e526c-121">Members</span><span class="sxs-lookup"><span data-stu-id="e526c-121">Members</span></span>

#### <span data-ttu-id="e526c-122">get_Uri</span><span class="sxs-lookup"><span data-stu-id="e526c-122">get_Uri</span></span> 

<span data-ttu-id="e526c-123">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="e526c-123">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="e526c-124">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="e526c-124">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="e526c-125">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="e526c-125">get_PermissionKind</span></span> 

<span data-ttu-id="e526c-126">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="e526c-126">The type of the permission that is requested.</span></span>

> <span data-ttu-id="e526c-127">パブリック HRESULT [get_PermissionKind](#get_permissionkind)(CORE_WEBVIEW2_PERMISSION_KIND \* 値)</span><span class="sxs-lookup"><span data-stu-id="e526c-127">public HRESULT [get_PermissionKind](#get_permissionkind)(CORE_WEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="e526c-128">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="e526c-128">get_IsUserInitiated</span></span> 

<span data-ttu-id="e526c-129">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e526c-129">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="e526c-130">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="e526c-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="e526c-131">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e526c-131">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="e526c-132">get_State</span><span class="sxs-lookup"><span data-stu-id="e526c-132">get_State</span></span> 

<span data-ttu-id="e526c-133">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="e526c-133">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="e526c-134">パブリック HRESULT [get_State](#get_state)(CORE_WEBVIEW2_PERMISSION_STATE \* 値)</span><span class="sxs-lookup"><span data-stu-id="e526c-134">public HRESULT [get_State](#get_state)(CORE_WEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="e526c-135">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="e526c-135">whether the request is granted.</span></span> <span data-ttu-id="e526c-136">既定値は CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT です。</span><span class="sxs-lookup"><span data-stu-id="e526c-136">Default value is CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="e526c-137">put_State</span><span class="sxs-lookup"><span data-stu-id="e526c-137">put_State</span></span> 

<span data-ttu-id="e526c-138">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e526c-138">Set the State property.</span></span>

> <span data-ttu-id="e526c-139">パブリック HRESULT [put_State](#put_state)(CORE_WEBVIEW2_PERMISSION_STATE 値)</span><span class="sxs-lookup"><span data-stu-id="e526c-139">public HRESULT [put_State](#put_state)(CORE_WEBVIEW2_PERMISSION_STATE value)</span></span>

#### <span data-ttu-id="e526c-140">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="e526c-140">GetDeferral</span></span> 

<span data-ttu-id="e526c-141">GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="e526c-141">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="e526c-142">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="e526c-142">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="e526c-143">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e526c-143">Developer can use the deferral object to make the permission decision at a later time.</span></span>

