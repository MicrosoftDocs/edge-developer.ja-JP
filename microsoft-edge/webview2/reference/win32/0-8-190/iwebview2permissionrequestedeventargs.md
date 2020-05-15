---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 9d16f1c72a3921b220bd0046e78ed0c6b32a718a
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654387"
---
# <span data-ttu-id="cbaaf-104">インターフェイス IWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="cbaaf-104">interface IWebView2PermissionRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="cbaaf-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="cbaaf-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="cbaaf-107">PermissionRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="cbaaf-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="cbaaf-108">Summary</span></span>

 <span data-ttu-id="cbaaf-109">Members</span><span class="sxs-lookup"><span data-stu-id="cbaaf-109">Members</span></span>                        | <span data-ttu-id="cbaaf-110">説明</span><span class="sxs-lookup"><span data-stu-id="cbaaf-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cbaaf-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="cbaaf-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="cbaaf-112">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-112">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="cbaaf-113">get_PermissionType</span><span class="sxs-lookup"><span data-stu-id="cbaaf-113">get_PermissionType</span></span>](#get_permissiontype) | <span data-ttu-id="cbaaf-114">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="cbaaf-115">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="cbaaf-115">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="cbaaf-116">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-116">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="cbaaf-117">get_State</span><span class="sxs-lookup"><span data-stu-id="cbaaf-117">get_State</span></span>](#get_state) | <span data-ttu-id="cbaaf-118">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="cbaaf-118">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="cbaaf-119">put_State</span><span class="sxs-lookup"><span data-stu-id="cbaaf-119">put_State</span></span>](#put_state) | <span data-ttu-id="cbaaf-120">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-120">Set the State property.</span></span>
[<span data-ttu-id="cbaaf-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="cbaaf-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="cbaaf-122">GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-122">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="cbaaf-123">Members</span><span class="sxs-lookup"><span data-stu-id="cbaaf-123">Members</span></span>

#### <span data-ttu-id="cbaaf-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="cbaaf-124">get_Uri</span></span> 

<span data-ttu-id="cbaaf-125">アクセス許可を要求する web コンテンツの起点。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-125">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="cbaaf-126">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="cbaaf-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="cbaaf-127">get_PermissionType</span><span class="sxs-lookup"><span data-stu-id="cbaaf-127">get_PermissionType</span></span> 

<span data-ttu-id="cbaaf-128">要求されるアクセス許可の型。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-128">The type of the permission that is requested.</span></span>

> <span data-ttu-id="cbaaf-129">パブリック HRESULT [get_PermissionType](#get_permissiontype)(WEBVIEW2_PERMISSION_TYPE \* 値)</span><span class="sxs-lookup"><span data-stu-id="cbaaf-129">public HRESULT [get_PermissionType](#get_permissiontype)(WEBVIEW2_PERMISSION_TYPE \* value)</span></span>

#### <span data-ttu-id="cbaaf-130">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="cbaaf-130">get_IsUserInitiated</span></span> 

<span data-ttu-id="cbaaf-131">アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-131">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="cbaaf-132">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="cbaaf-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="cbaaf-133">ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-133">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="cbaaf-134">get_State</span><span class="sxs-lookup"><span data-stu-id="cbaaf-134">get_State</span></span> 

<span data-ttu-id="cbaaf-135">権限要求の状態。つまり、</span><span class="sxs-lookup"><span data-stu-id="cbaaf-135">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="cbaaf-136">パブリック HRESULT [get_State](#get_state)(WEBVIEW2_PERMISSION_STATE \* 値)</span><span class="sxs-lookup"><span data-stu-id="cbaaf-136">public HRESULT [get_State](#get_state)(WEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="cbaaf-137">要求を許可するかどうか。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-137">whether the request is granted.</span></span> <span data-ttu-id="cbaaf-138">既定値は WEBVIEW2_PERMISSION_STATE_DEFAULT です。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-138">Default value is WEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="cbaaf-139">put_State</span><span class="sxs-lookup"><span data-stu-id="cbaaf-139">put_State</span></span> 

<span data-ttu-id="cbaaf-140">State プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-140">Set the State property.</span></span>

> <span data-ttu-id="cbaaf-141">パブリック HRESULT [put_State](#put_state)(WEBVIEW2_PERMISSION_STATE 値)</span><span class="sxs-lookup"><span data-stu-id="cbaaf-141">public HRESULT [put_State](#put_state)(WEBVIEW2_PERMISSION_STATE value)</span></span>

#### <span data-ttu-id="cbaaf-142">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="cbaaf-142">GetDeferral</span></span> 

<span data-ttu-id="cbaaf-143">GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-143">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="cbaaf-144">パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="cbaaf-144">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="cbaaf-145">開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cbaaf-145">Developer can use the deferral object to make the permission decision at a later time.</span></span>

