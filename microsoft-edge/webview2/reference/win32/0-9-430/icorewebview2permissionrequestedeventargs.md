---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 529f4a444b3ad6d0d5831da6015831b077102354
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654198"
---
# <span data-ttu-id="4607a-104">インターフェイス ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="4607a-104">interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="4607a-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4607a-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="4607a-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4607a-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="4607a-107">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="4607a-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="4607a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="4607a-108">Summary</span></span>

 <span data-ttu-id="4607a-109">Members</span><span class="sxs-lookup"><span data-stu-id="4607a-109">Members</span></span>                        | <span data-ttu-id="4607a-110">説明</span><span class="sxs-lookup"><span data-stu-id="4607a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4607a-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4607a-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="4607a-112">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="4607a-112">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="4607a-113">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="4607a-113">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="4607a-114">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="4607a-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="4607a-115">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4607a-115">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="4607a-116">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4607a-116">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="4607a-117">get_State</span><span class="sxs-lookup"><span data-stu-id="4607a-117">get_State</span></span>](#get_state) | <span data-ttu-id="4607a-118">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="4607a-118">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="4607a-119">put_State</span><span class="sxs-lookup"><span data-stu-id="4607a-119">put_State</span></span>](#put_state) | <span data-ttu-id="4607a-120">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4607a-120">Set the State property.</span></span>
[<span data-ttu-id="4607a-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4607a-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="4607a-122">GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="4607a-122">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="4607a-123">Members</span><span class="sxs-lookup"><span data-stu-id="4607a-123">Members</span></span>

#### <span data-ttu-id="4607a-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4607a-124">get_Uri</span></span> 

<span data-ttu-id="4607a-125">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="4607a-125">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="4607a-126">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="4607a-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="4607a-127">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="4607a-127">get_PermissionKind</span></span> 

<span data-ttu-id="4607a-128">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="4607a-128">The type of the permission that is requested.</span></span>

> <span data-ttu-id="4607a-129">パブリック HRESULT [get_PermissionKind](#get_permissionkind)(CORE_WEBVIEW2_PERMISSION_KIND \* 値)</span><span class="sxs-lookup"><span data-stu-id="4607a-129">public HRESULT [get_PermissionKind](#get_permissionkind)(CORE_WEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="4607a-130">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4607a-130">get_IsUserInitiated</span></span> 

<span data-ttu-id="4607a-131">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4607a-131">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="4607a-132">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="4607a-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="4607a-133">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4607a-133">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="4607a-134">get_State</span><span class="sxs-lookup"><span data-stu-id="4607a-134">get_State</span></span> 

<span data-ttu-id="4607a-135">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="4607a-135">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="4607a-136">パブリック HRESULT [get_State](#get_state)(CORE_WEBVIEW2_PERMISSION_STATE \* 値)</span><span class="sxs-lookup"><span data-stu-id="4607a-136">public HRESULT [get_State](#get_state)(CORE_WEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="4607a-137">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="4607a-137">whether the request is granted.</span></span> <span data-ttu-id="4607a-138">既定値は CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT です。</span><span class="sxs-lookup"><span data-stu-id="4607a-138">Default value is CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="4607a-139">put_State</span><span class="sxs-lookup"><span data-stu-id="4607a-139">put_State</span></span> 

<span data-ttu-id="4607a-140">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4607a-140">Set the State property.</span></span>

> <span data-ttu-id="4607a-141">パブリック HRESULT [put_State](#put_state)(CORE_WEBVIEW2_PERMISSION_STATE 値)</span><span class="sxs-lookup"><span data-stu-id="4607a-141">public HRESULT [put_State](#put_state)(CORE_WEBVIEW2_PERMISSION_STATE value)</span></span>

#### <span data-ttu-id="4607a-142">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4607a-142">GetDeferral</span></span> 

<span data-ttu-id="4607a-143">GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="4607a-143">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="4607a-144">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="4607a-144">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="4607a-145">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4607a-145">Developer can use the deferral object to make the permission decision at a later time.</span></span>

