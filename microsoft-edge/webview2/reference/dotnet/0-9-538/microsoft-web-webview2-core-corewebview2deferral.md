---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2Deferral の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2Deferral。
ms.openlocfilehash: 62cd86772d45e1bf9eee7d1821a90b723e1af7db
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011049"
---
# <span data-ttu-id="75688-104">0.9.579 クラスの WebView2 クラス (CoreWebView2Deferral)</span><span class="sxs-lookup"><span data-stu-id="75688-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="75688-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="75688-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="75688-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="75688-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="75688-107">このクラスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="75688-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="75688-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="75688-108">Summary</span></span>

 <span data-ttu-id="75688-109">Members</span><span class="sxs-lookup"><span data-stu-id="75688-109">Members</span></span>                        | <span data-ttu-id="75688-110">説明</span><span class="sxs-lookup"><span data-stu-id="75688-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="75688-111">Complete</span><span class="sxs-lookup"><span data-stu-id="75688-111">Complete</span></span>](#complete) | <span data-ttu-id="75688-112">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="75688-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="75688-113">Members</span><span class="sxs-lookup"><span data-stu-id="75688-113">Members</span></span>

#### <span data-ttu-id="75688-114">Complete</span><span class="sxs-lookup"><span data-stu-id="75688-114">Complete</span></span> 

<span data-ttu-id="75688-115">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="75688-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="75688-116">パブリックの void [完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="75688-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="75688-117">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="75688-117">Complete should only be called once for each deferral taken.</span></span>

