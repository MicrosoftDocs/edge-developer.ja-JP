---
title: Web アプリマニフェストを使ってプログレッシブ Web アプリをオペレーティングシステムに統合する
description: Web アプリマニフェストを使って、プログレッシブ Web アプリをオペレーティングシステムに統合する方法について説明します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ web アプリ、PWA、エッジ、JavaScript、Windows、UWP、Microsoft ストア
ms.openlocfilehash: f493ae0c3cef3a1950b2207d66fef65055b2d959
ms.sourcegitcommit: d9cc829deb709b0866f6b43a5f4733682ddae5ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "10659294"
---
# <span data-ttu-id="2ab2e-104">Web アプリマニフェストを使ってプログレッシブ Web アプリをオペレーティングシステムに統合する</span><span class="sxs-lookup"><span data-stu-id="2ab2e-104">Use the Web App Manifest to integrate your Progressive Web App into the Operating System</span></span>

<span data-ttu-id="2ab2e-105">Web サイトの Web アプリマニフェストは、プログレッシブ Web アプリ \ (PWA) がデバイスにインストールされたときの外観と動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-105">A Web App Manifest of a website governs how your Progressive Web App \(PWA\) looks and behaves when installed on a device.</span></span>  <span data-ttu-id="2ab2e-106">最も基本的なレベルでは、マニフェストは、アプリの名前、システムメニューでアプリを表すために使用するアイコン、オペレーティングシステム \ (OS \) がタイトルバーに使用するテーマの色について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-106">At the most basic level, the Manifest provides details on the name of your app, icons to use to represent your app in system menus, and the theme colors the operating system \(OS\) uses in the title bar.</span></span>  <span data-ttu-id="2ab2e-107">マニフェストでは、システム上の他のネイティブアプリと同じようにアプリを動作させることができる強力な機能のロックを解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-107">The Manifest also enables you to unlock powerful features that allow your app to behave like other native apps on the system.</span></span>  

## <span data-ttu-id="2ab2e-108">ショートカットを使用して機能にすばやくアクセスする</span><span class="sxs-lookup"><span data-stu-id="2ab2e-108">Use shortcuts to provide quick access to features</span></span>  

<span data-ttu-id="2ab2e-109">ほとんどのオペレーティングシステムでは、アプリのアイコンに接続されたコンテキストメニューのショートカットを使用して、主要なアプリの機能にすばやくアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-109">Most operating systems provide quick access to key app features using shortcuts on the context menu connected to the icon of the app.</span></span>  <span data-ttu-id="2ab2e-110">PWA のショートカットを使用するには、 `shortcuts` Web アプリマニフェストにプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-110">To use shortcuts in your PWA, include the `shortcuts` property in your Web App Manifest.</span></span>  <span data-ttu-id="2ab2e-111">次のコードスニペットは、web アプリマニフェストでショートカットを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-111">The following code snippet shows how to define a shortcut in your web app manifest.</span></span>  

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

<span data-ttu-id="2ab2e-112">完全な Web アプリマニフェストに追加された場合、前のコードスニペットを追加すると、アプリのアイコンのコンテキストメニューで2つのショートカットが有効になります。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-112">When added to a complete Web App Manifest, adding the previous code snippet enables two shortcuts on the context menu on the icon of the app.</span></span>  <span data-ttu-id="2ab2e-113">最初の名前には、 `Play Later` カスタムアイコンが付いています。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-113">The first is named `Play Later` and has a custom icon.</span></span>  <span data-ttu-id="2ab2e-114">2番目の引数には、 `Subscriptions` `icons` プロパティが省略可能であるため、という名前が付けられ、アイコンはありません。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-114">The second is named `Subscriptions` and does not have an icon because the `icons` property is optional.</span></span>  <span data-ttu-id="2ab2e-115">この `description` プロパティはオプションでもあり、アクセシビリティのために追加情報を提供するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-115">The `description` property is also optional and may be used to provide additional information for accessibility purposes.</span></span>  

## <span data-ttu-id="2ab2e-116">アプリを共有ターゲットとして識別する</span><span class="sxs-lookup"><span data-stu-id="2ab2e-116">Identify your app as a Share Target</span></span>

<span data-ttu-id="2ab2e-117">多くのオペレーティングシステムでは、ネイティブアプリケーションでリンクやファイルを簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-117">Many operating systems enable users to quickly share links and files with native applications.</span></span> <span data-ttu-id="2ab2e-118">プログレッシブ Web アプリは、 `share_target` Web アプリマニフェストのメンバーを通じて、この機能にも参加できます。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-118">Progressive Web Apps can participate in this feature as well, via the `share_target` member of the Web App Manifest.</span></span> <span data-ttu-id="2ab2e-119">Share_target を使って、"アクション" ページ (フォームと同様) と、それに渡す必要があるパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-119">Using share_target, you define the "action" page (similar to a form) and the parameters you expect to be passed into it.</span></span> <span data-ttu-id="2ab2e-120">次のコードスニペットは、の使い方の例を示して `share_target` います。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-120">The following code snippet shows an example of how to use `share_target`.</span></span>

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

<span data-ttu-id="2ab2e-121">Web アプリマニフェストに追加されると、共有の操作ページとして "/¥ .html" が確立されます。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-121">When added to the Web App Manifest, this establishes "/share.html" as the action page for a share.</span></span> <span data-ttu-id="2ab2e-122">さらに、アクションページに渡される3つのパラメーターを定義します。これには、"title"、"text"、"url" があります。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-122">Additionally, it defines three parameters that would be passed to that action page: "title", "text", and "url".</span></span> <span data-ttu-id="2ab2e-123">これらのパラメーターは、"name"、"description"、"link [" の各](https://wicg.github.io/web-share#dom-sharedata)プロパティに保存されます。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-123">These parameters will be stored in the [ShareData](https://wicg.github.io/web-share#dom-sharedata) object’s "name", "description", and "link" properties.</span></span> <span data-ttu-id="2ab2e-124">既定では、アクションページは GET 要求の一部としてこれらのパラメーターを受け取りますが、web フォームの場合と同様に、要求 `method` とエンコードは \ (as) を指定でき `enctype` ます。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-124">By default, the action page receives these parameters as part of a GET request, but you can specify the request `method` and encoding \(as `enctype`\), just like you would on a web form.</span></span>

## <span data-ttu-id="2ab2e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ab2e-125">See also</span></span>  

<span data-ttu-id="2ab2e-126">Web アプリマニフェストの詳細については、次の関連するトピックの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ab2e-126">To learn more about Web App Manifests, see the following list of related topics.</span></span>  

* [<span data-ttu-id="2ab2e-127">Web App マニフェスト</span><span class="sxs-lookup"><span data-stu-id="2ab2e-127">Web App Manifests</span></span>][MDNWebAppManifests]  
* [<span data-ttu-id="2ab2e-128">Web 共有ターゲット</span><span class="sxs-lookup"><span data-stu-id="2ab2e-128">Web Share Target</span></span>][WICGShareTarget]
* [<span data-ttu-id="2ab2e-129">Web 共有</span><span class="sxs-lookup"><span data-stu-id="2ab2e-129">Web Share</span></span>][WICGShare]

<!-- links -->  

[MDNWebAppManifests]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  
[WICGShareTarget]: https://wicg.github.io/web-share-target/ "Web 共有ターゲット API |WICG"
[WICGShare]: https://w3c.github.io/web-share/ "Web Share API |WICG"
