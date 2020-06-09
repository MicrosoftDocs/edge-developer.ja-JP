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
ms.openlocfilehash: bf198781d67761e9d6c29ee9c6a274462e92a61d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697673"
---
# <span data-ttu-id="22071-104">WebView2 クラス (CoreWebView2Deferral クラス)</span><span class="sxs-lookup"><span data-stu-id="22071-104">Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

> [!NOTE]
> <span data-ttu-id="22071-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22071-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="22071-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22071-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="22071-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="22071-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="22071-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="22071-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="22071-109">このクラスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="22071-109">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="22071-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="22071-110">Summary</span></span>

 <span data-ttu-id="22071-111">Members</span><span class="sxs-lookup"><span data-stu-id="22071-111">Members</span></span>                        | <span data-ttu-id="22071-112">説明</span><span class="sxs-lookup"><span data-stu-id="22071-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="22071-113">Complete</span><span class="sxs-lookup"><span data-stu-id="22071-113">Complete</span></span>](#complete) | <span data-ttu-id="22071-114">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="22071-114">Completes the associated deferred event.</span></span>

## <span data-ttu-id="22071-115">Members</span><span class="sxs-lookup"><span data-stu-id="22071-115">Members</span></span>

#### <span data-ttu-id="22071-116">Complete</span><span class="sxs-lookup"><span data-stu-id="22071-116">Complete</span></span> 

<span data-ttu-id="22071-117">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="22071-117">Completes the associated deferred event.</span></span>

> <span data-ttu-id="22071-118">パブリックの void[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="22071-118">public void [Complete](#complete)()</span></span>

<span data-ttu-id="22071-119">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="22071-119">Complete should only be called once for each deferral taken.</span></span>

