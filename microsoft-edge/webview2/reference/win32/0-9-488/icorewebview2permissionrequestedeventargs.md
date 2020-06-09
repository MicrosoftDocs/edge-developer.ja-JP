---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 3d88d4ee0a89b4690b47f67ee90756ebecdd1c78
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698191"
---
# <span data-ttu-id="83ba3-104">インターフェイス ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="83ba3-104">interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="83ba3-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83ba3-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="83ba3-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83ba3-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="83ba3-107">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="83ba3-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="83ba3-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="83ba3-108">Summary</span></span>

 <span data-ttu-id="83ba3-109">Members</span><span class="sxs-lookup"><span data-stu-id="83ba3-109">Members</span></span>                        | <span data-ttu-id="83ba3-110">説明</span><span class="sxs-lookup"><span data-stu-id="83ba3-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="83ba3-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="83ba3-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="83ba3-112">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="83ba3-112">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="83ba3-113">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="83ba3-113">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="83ba3-114">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="83ba3-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="83ba3-115">get_State</span><span class="sxs-lookup"><span data-stu-id="83ba3-115">get_State</span></span>](#get_state) | <span data-ttu-id="83ba3-116">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="83ba3-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="83ba3-117">get_Uri</span><span class="sxs-lookup"><span data-stu-id="83ba3-117">get_Uri</span></span>](#get_uri) | <span data-ttu-id="83ba3-118">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="83ba3-118">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="83ba3-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="83ba3-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="83ba3-120">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="83ba3-120">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="83ba3-121">put_State</span><span class="sxs-lookup"><span data-stu-id="83ba3-121">put_State</span></span>](#put_state) | <span data-ttu-id="83ba3-122">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="83ba3-122">Set the State property.</span></span>

## <span data-ttu-id="83ba3-123">Members</span><span class="sxs-lookup"><span data-stu-id="83ba3-123">Members</span></span>

#### <span data-ttu-id="83ba3-124">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="83ba3-124">get_IsUserInitiated</span></span> 

<span data-ttu-id="83ba3-125">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="83ba3-125">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="83ba3-126">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="83ba3-126">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="83ba3-127">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="83ba3-127">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="83ba3-128">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="83ba3-128">get_PermissionKind</span></span> 

<span data-ttu-id="83ba3-129">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="83ba3-129">The type of the permission that is requested.</span></span>

> <span data-ttu-id="83ba3-130">パブリック HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND \* 値)</span><span class="sxs-lookup"><span data-stu-id="83ba3-130">public HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="83ba3-131">get_State</span><span class="sxs-lookup"><span data-stu-id="83ba3-131">get_State</span></span> 

<span data-ttu-id="83ba3-132">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="83ba3-132">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="83ba3-133">パブリック HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE \* 値)</span><span class="sxs-lookup"><span data-stu-id="83ba3-133">public HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="83ba3-134">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="83ba3-134">whether the request is granted.</span></span> <span data-ttu-id="83ba3-135">既定値は COREWEBVIEW2_PERMISSION_STATE_DEFAULT です。</span><span class="sxs-lookup"><span data-stu-id="83ba3-135">Default value is COREWEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="83ba3-136">get_Uri</span><span class="sxs-lookup"><span data-stu-id="83ba3-136">get_Uri</span></span> 

<span data-ttu-id="83ba3-137">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="83ba3-137">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="83ba3-138">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="83ba3-138">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="83ba3-139">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="83ba3-139">GetDeferral</span></span> 

<span data-ttu-id="83ba3-140">GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="83ba3-140">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="83ba3-141">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="83ba3-141">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="83ba3-142">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="83ba3-142">Developer can use the deferral object to make the permission decision at a later time.</span></span>

#### <span data-ttu-id="83ba3-143">put_State</span><span class="sxs-lookup"><span data-stu-id="83ba3-143">put_State</span></span> 

<span data-ttu-id="83ba3-144">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="83ba3-144">Set the State property.</span></span>

> <span data-ttu-id="83ba3-145">パブリック HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE 値)</span><span class="sxs-lookup"><span data-stu-id="83ba3-145">public HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE value)</span></span>

