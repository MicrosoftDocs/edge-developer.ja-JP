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
ms.openlocfilehash: abe167548b7e604bd60c792660ea5b52dec9b848
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697302"
---
# <span data-ttu-id="67019-104">WebView2 クラス (CoreWebView2ContentLoadingEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="67019-104">Microsoft.Web.WebView2.Core.CoreWebView2ContentLoadingEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="67019-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67019-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="67019-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67019-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="67019-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="67019-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="67019-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="67019-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="67019-109">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="67019-109">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="67019-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="67019-110">Summary</span></span>

 <span data-ttu-id="67019-111">Members</span><span class="sxs-lookup"><span data-stu-id="67019-111">Members</span></span>                        | <span data-ttu-id="67019-112">説明</span><span class="sxs-lookup"><span data-stu-id="67019-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="67019-113">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="67019-113">IsErrorPage</span></span>](#iserrorpage) | <span data-ttu-id="67019-114">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="67019-114">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="67019-115">NavigationId</span><span class="sxs-lookup"><span data-stu-id="67019-115">NavigationId</span></span>](#navigationid) | <span data-ttu-id="67019-116">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="67019-116">The ID of the navigation.</span></span>

## <span data-ttu-id="67019-117">Members</span><span class="sxs-lookup"><span data-stu-id="67019-117">Members</span></span>

#### <span data-ttu-id="67019-118">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="67019-118">IsErrorPage</span></span> 

<span data-ttu-id="67019-119">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="67019-119">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="67019-120">public bool [IsErrorPage](#iserrorpage)</span><span class="sxs-lookup"><span data-stu-id="67019-120">public bool [IsErrorPage](#iserrorpage)</span></span>

#### <span data-ttu-id="67019-121">NavigationId</span><span class="sxs-lookup"><span data-stu-id="67019-121">NavigationId</span></span> 

<span data-ttu-id="67019-122">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="67019-122">The ID of the navigation.</span></span>

> <span data-ttu-id="67019-123">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="67019-123">public ulong [NavigationId](#navigationid)</span></span>

