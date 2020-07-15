---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 92c08d199aa607dae9cc575955a1eb0bf016a9c0
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878331"
---
# <span data-ttu-id="d2297-104">0.8.355-インターフェイス IWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d2297-104">0.8.355 - interface IWebView2PermissionRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="d2297-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d2297-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="d2297-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2297-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="d2297-107">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="d2297-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="d2297-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d2297-108">Summary</span></span>

 <span data-ttu-id="d2297-109">Members</span><span class="sxs-lookup"><span data-stu-id="d2297-109">Members</span></span>                        | <span data-ttu-id="d2297-110">説明</span><span class="sxs-lookup"><span data-stu-id="d2297-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d2297-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="d2297-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="d2297-112">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="d2297-112">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="d2297-113">get_PermissionType</span><span class="sxs-lookup"><span data-stu-id="d2297-113">get_PermissionType</span></span>](#get_permissiontype) | <span data-ttu-id="d2297-114">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="d2297-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="d2297-115">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="d2297-115">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="d2297-116">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d2297-116">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="d2297-117">get_State</span><span class="sxs-lookup"><span data-stu-id="d2297-117">get_State</span></span>](#get_state) | <span data-ttu-id="d2297-118">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="d2297-118">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="d2297-119">put_State</span><span class="sxs-lookup"><span data-stu-id="d2297-119">put_State</span></span>](#put_state) | <span data-ttu-id="d2297-120">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d2297-120">Set the State property.</span></span>
[<span data-ttu-id="d2297-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d2297-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="d2297-122">GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="d2297-122">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="d2297-123">Members</span><span class="sxs-lookup"><span data-stu-id="d2297-123">Members</span></span>

#### <span data-ttu-id="d2297-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="d2297-124">get_Uri</span></span> 

<span data-ttu-id="d2297-125">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="d2297-125">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="d2297-126">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="d2297-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="d2297-127">get_PermissionType</span><span class="sxs-lookup"><span data-stu-id="d2297-127">get_PermissionType</span></span> 

<span data-ttu-id="d2297-128">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="d2297-128">The type of the permission that is requested.</span></span>

> <span data-ttu-id="d2297-129">パブリック HRESULT [get_PermissionType](#get_permissiontype)(WEBVIEW2_PERMISSION_TYPE \* 値)</span><span class="sxs-lookup"><span data-stu-id="d2297-129">public HRESULT [get_PermissionType](#get_permissiontype)(WEBVIEW2_PERMISSION_TYPE \* value)</span></span>

#### <span data-ttu-id="d2297-130">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="d2297-130">get_IsUserInitiated</span></span> 

<span data-ttu-id="d2297-131">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d2297-131">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="d2297-132">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="d2297-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="d2297-133">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d2297-133">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="d2297-134">get_State</span><span class="sxs-lookup"><span data-stu-id="d2297-134">get_State</span></span> 

<span data-ttu-id="d2297-135">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="d2297-135">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="d2297-136">パブリック HRESULT [get_State](#get_state)(WEBVIEW2_PERMISSION_STATE \* 値)</span><span class="sxs-lookup"><span data-stu-id="d2297-136">public HRESULT [get_State](#get_state)(WEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="d2297-137">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d2297-137">whether the request is granted.</span></span> <span data-ttu-id="d2297-138">既定値は WEBVIEW2_PERMISSION_STATE_DEFAULT です。</span><span class="sxs-lookup"><span data-stu-id="d2297-138">Default value is WEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="d2297-139">put_State</span><span class="sxs-lookup"><span data-stu-id="d2297-139">put_State</span></span> 

<span data-ttu-id="d2297-140">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d2297-140">Set the State property.</span></span>

> <span data-ttu-id="d2297-141">パブリック HRESULT [put_State](#put_state)(WEBVIEW2_PERMISSION_STATE 値)</span><span class="sxs-lookup"><span data-stu-id="d2297-141">public HRESULT [put_State](#put_state)(WEBVIEW2_PERMISSION_STATE value)</span></span>

#### <span data-ttu-id="d2297-142">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d2297-142">GetDeferral</span></span> 

<span data-ttu-id="d2297-143">GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="d2297-143">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="d2297-144">パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="d2297-144">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="d2297-145">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d2297-145">Developer can use the deferral object to make the permission decision at a later time.</span></span>

