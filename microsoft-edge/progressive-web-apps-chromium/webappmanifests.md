---
title: Web アプリ マニフェストを使用して、プログレッシブ Web アプリをオペレーティング システムに統合する
description: Web アプリ マニフェストを使用してプログレッシブ Web アプリをオペレーティング システムに統合する方法について説明します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ Web アプリ、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: 0063323b1fde94d84e70df51170726325dd0f2a9
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399100"
---
# <a name="use-the-web-app-manifest-to-integrate-your-progressive-web-app-into-the-operating-system"></a><span data-ttu-id="f9ccd-104">Web アプリ マニフェストを使用して、プログレッシブ Web アプリをオペレーティング システムに統合する</span><span class="sxs-lookup"><span data-stu-id="f9ccd-104">Use the Web App Manifest to integrate your Progressive Web App into the Operating System</span></span>

<span data-ttu-id="f9ccd-105">Web サイトの Web アプリ マニフェストは、デバイスにインストールされた場合のプログレッシブ Web アプリ \(PWA\) の外観と動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-105">A Web App Manifest of a website governs how your Progressive Web App \(PWA\) looks and behaves when installed on a device.</span></span>  <span data-ttu-id="f9ccd-106">最も基本的なレベルでは、マニフェストはアプリの名前、システム メニューでアプリを表すアイコン、およびタイトル バーでオペレーティング システム \(OS\) が使用するテーマの色に関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-106">At the most basic level, the Manifest provides details on the name of your app, icons to use to represent your app in system menus, and the theme colors the operating system \(OS\) uses in the title bar.</span></span>  <span data-ttu-id="f9ccd-107">マニフェストを使用すると、アプリがシステム上の他のネイティブ アプリのように動作する強力な機能のロックを解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-107">The Manifest also enables you to unlock powerful features that allow your app to behave like other native apps on the system.</span></span>  

## <a name="use-shortcuts-to-provide-quick-access-to-features"></a><span data-ttu-id="f9ccd-108">ショートカットを使用して機能にすばやくアクセスする</span><span class="sxs-lookup"><span data-stu-id="f9ccd-108">Use shortcuts to provide quick access to features</span></span>  

<span data-ttu-id="f9ccd-109">ほとんどのオペレーティング システムでは、アプリのアイコンに接続されているコンテキスト メニューのショートカットを使用して、主要なアプリ機能にすばやくアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-109">Most operating systems provide quick access to key app features using shortcuts on the context menu connected to the icon of the app.</span></span>  <span data-ttu-id="f9ccd-110">PWA でショートカットを使用するには、Web `shortcuts` アプリ マニフェストにプロパティを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-110">To use shortcuts in your PWA, include the `shortcuts` property in your Web App Manifest.</span></span>  <span data-ttu-id="f9ccd-111">次のコード スニペットは、Web アプリ マニフェストでショートカットを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-111">The following code snippet displays how to define a shortcut in your web app manifest.</span></span>  

```json
"shortcuts": [
    {
        "name": "Play Later",
        "description": "View the list of podcasts you saved for later",
        "url": "/play-later",
        "icons": [
            {
                "src": "/icons/play-later.svg",
                "type": "image/svg+xml",
                "purpose": "any"
            }
        ]
    },
    {
        "name": "Subscriptions",
        "description": "View the list of podcasts available in your subscription",
        "url": "/subscriptions?sort=desc"
    }
]
```  

<span data-ttu-id="f9ccd-112">完全な Web アプリ マニフェストに追加すると、前のコード スニペットを追加すると、アプリのアイコンのコンテキスト メニューで 2 つのショートカットが有効になります。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-112">When added to a complete Web App Manifest, adding the previous code snippet enables two shortcuts on the context menu on the icon of the app.</span></span>  <span data-ttu-id="f9ccd-113">1 つ目の名前 `Play Later` はカスタム アイコンです。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-113">The first is named `Play Later` and has a custom icon.</span></span>  <span data-ttu-id="f9ccd-114">プロパティは省略可能なので、2 番目の名前は付け `Subscriptions` 、 `icons` アイコンを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-114">The second is named `Subscriptions` and does not have an icon because the `icons` property is optional.</span></span>  <span data-ttu-id="f9ccd-115">この `description` プロパティはオプションで、アクセシビリティの目的で追加情報を提供するために使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-115">The `description` property is also optional and may be used to provide additional information for accessibility purposes.</span></span>  

## <a name="identify-your-app-as-a-share-target"></a><span data-ttu-id="f9ccd-116">アプリを共有ターゲットとして識別する</span><span class="sxs-lookup"><span data-stu-id="f9ccd-116">Identify your app as a Share Target</span></span>

<span data-ttu-id="f9ccd-117">多くのオペレーティング システムを使用すると、ユーザーはリンクやファイルをネイティブ アプリケーションとすばやく共有できます。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-117">Many operating systems enable users to quickly share links and files with native applications.</span></span> <span data-ttu-id="f9ccd-118">プログレッシブ Web アプリは、Web アプリ マニフェストのメンバーを使用して、この `share_target` 機能にも参加できます。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-118">Progressive Web Apps can participate in this feature as well, using the `share_target` member of the Web App Manifest.</span></span>  <span data-ttu-id="f9ccd-119">を `share_target` 使用して、ページ \(form\に似た) と、ページに渡す必要がある `"action"` パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-119">Using `share_target`, you define the `"action"` page \(similar to a form\) and the parameters you expect to be passed into it.</span></span>  <span data-ttu-id="f9ccd-120">次のコード スニペットは、使用方法の例を表示します `share_target` 。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-120">The following code snippet displays an example of how to use `share_target`.</span></span>

```json
"share_target": {
    "action": "/share.html",
    "params": {
        "title": "name",
        "text": "description",
        "url": "link"
    }
}
```

<span data-ttu-id="f9ccd-121">Web アプリ マニフェストに追加すると、共有 `"/share.html"` のアクション ページとして確立されます。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-121">When added to the Web App Manifest, this establishes `"/share.html"` as the action page for a share.</span></span> <span data-ttu-id="f9ccd-122">さらに、そのアクション ページに渡される 3 つのパラメーターを定義 `"title"` します。 `"text"` `"url"`</span><span class="sxs-lookup"><span data-stu-id="f9ccd-122">Additionally, it defines three parameters that would be passed to that action page:`"title"`, `"text"`, and `"url"`.</span></span>  <span data-ttu-id="f9ccd-123">これらのパラメーターは `"name"` 、ShareData オブジェクトの `"description"` 、、 `"link"` およびプロパティに [格納][GitHubWicgWebShareDomSharedata] されます。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-123">These parameters will be stored in the `"name"`, `"description"`, and `"link"` properties of the [ShareData][GitHubWicgWebShareDomSharedata] object.</span></span>  <span data-ttu-id="f9ccd-124">既定では、アクション ページは GET 要求の一部としてパラメーターを受け取りますが、Web フォームと同様に、要求とエンコード `method` \(\) を `enctype` 指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-124">By default, the action page receives the parameters as part of a GET request, but you can specify the request `method` and encoding \(as `enctype`\), just like you would on a web form.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9ccd-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9ccd-125">See also</span></span>  

<span data-ttu-id="f9ccd-126">Web アプリ マニフェストの詳細については、次の関連トピックの一覧に移動します。</span><span class="sxs-lookup"><span data-stu-id="f9ccd-126">To learn more about Web App Manifests, navigate to the following list of related topics.</span></span>  

*   [<span data-ttu-id="f9ccd-127">Web アプリ マニフェスト</span><span class="sxs-lookup"><span data-stu-id="f9ccd-127">Web App Manifests</span></span>][MDNWebAppManifests]  
*   [<span data-ttu-id="f9ccd-128">Web 共有ターゲット</span><span class="sxs-lookup"><span data-stu-id="f9ccd-128">Web Share Target</span></span>][GitHubWicgWebShareTarget]
*   [<span data-ttu-id="f9ccd-129">Web 共有</span><span class="sxs-lookup"><span data-stu-id="f9ccd-129">Web Share</span></span>][GithubW3cWebShare]
    
<!-- links -->  

[MDNWebAppManifests]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ のマニフェスト|MDN"  

[GitHubWicgWebShareTarget]: https://wicg.github.io/web-share-target "Web 共有ターゲット API |WICG"
[GitHubWicgWebShareDomSharedata]: https://wicg.github.io/web-share#dom-sharedata "ShareData ディクショナリ - Web Share API |WICG"  

[GithubW3cWebShare]: https://w3c.github.io/web-share/ "Web 共有 API |WICG"
