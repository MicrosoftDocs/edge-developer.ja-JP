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
ms.openlocfilehash: fec7fd7399222d8223d1022cd1e528bc9ed0d161
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654480"
---
# <span data-ttu-id="db467-104">WebView2 クラス (CoreWebView2Deferral クラス)</span><span class="sxs-lookup"><span data-stu-id="db467-104">Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

<span data-ttu-id="db467-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="db467-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="db467-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="db467-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="db467-107">このクラスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="db467-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="db467-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="db467-108">Summary</span></span>

 <span data-ttu-id="db467-109">Members</span><span class="sxs-lookup"><span data-stu-id="db467-109">Members</span></span>                        | <span data-ttu-id="db467-110">説明</span><span class="sxs-lookup"><span data-stu-id="db467-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="db467-111">Complete</span><span class="sxs-lookup"><span data-stu-id="db467-111">Complete</span></span>](#complete) | <span data-ttu-id="db467-112">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="db467-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="db467-113">Members</span><span class="sxs-lookup"><span data-stu-id="db467-113">Members</span></span>

#### <span data-ttu-id="db467-114">Complete</span><span class="sxs-lookup"><span data-stu-id="db467-114">Complete</span></span> 

<span data-ttu-id="db467-115">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="db467-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="db467-116">パブリックの void[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="db467-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="db467-117">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="db467-117">Complete should only be called once for each deferral taken.</span></span>

