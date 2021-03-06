---
description: 拡張機能をパッケージ化する方法について学習します。
title: 拡張機能 - パッケージ化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
keywords: edge, Web 開発, html, css, javascript, developer
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 62c7858c38cf0c06e24c25938a885b10b391fd8f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398498"
---
# <a name="packaging-microsoft-edge-extensions"></a><span data-ttu-id="71cf8-104">Microsoft Edge 拡張機能のパッケージ化</span><span class="sxs-lookup"><span data-stu-id="71cf8-104">Packaging Microsoft Edge extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="71cf8-105">最後に拡張機能を完成し、パッケージ化する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="71cf8-105">So you've finally completed your extension and are ready to package it up.</span></span> <span data-ttu-id="71cf8-106">潜在的なユーザーの手でこれを取得するための次の手順は何か疑問に思う場合があります。</span><span class="sxs-lookup"><span data-stu-id="71cf8-106">You might be wondering what the next steps are toward getting this in the hands of potential users.</span></span> <span data-ttu-id="71cf8-107">このガイドは、それを行う方法を教えることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="71cf8-107">This guide is intended to teach you how to do just that.</span></span>  

<span data-ttu-id="71cf8-108">拡張パッケージ ガイドは、パッケージ化について知りたいもの、さらに細かく、細かく詳細な詳細をカバーする包括的なガイドです。</span><span class="sxs-lookup"><span data-stu-id="71cf8-108">The extension packaging guide is comprehensive in that it covers everything you'd want to know about packaging, even the finer, nitty gritty details.</span></span> <span data-ttu-id="71cf8-109">拡張機能のパッケージ化について知っている必要があるすべてを学びたくない場合は、運が良いです。</span><span class="sxs-lookup"><span data-stu-id="71cf8-109">If you don't want to learn everything there is to know about packaging your extension, you're in luck.</span></span> <span data-ttu-id="71cf8-110">パッケージ化の苦境の大部分を取り去るオープンソースNode.js、マニホールドJS に拡張機能のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="71cf8-110">We've added support for extensions to ManifoldJS, an open source Node.js tool that takes the majority of your packaging woes away.</span></span>  

> [!NOTE]
> <span data-ttu-id="71cf8-111">Microsoft Edge 拡張機能を Microsoft Store に提出する機能は、現在制限付き機能です。</span><span class="sxs-lookup"><span data-stu-id="71cf8-111">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="71cf8-112">[Microsoft Store の一](https://developer.microsoft.com/en-us/microsoft-edge/extensions/requests) 部として要求を受け取り、今後の更新について検討します。</span><span class="sxs-lookup"><span data-stu-id="71cf8-112">[Reach out to us](https://developer.microsoft.com/en-us/microsoft-edge/extensions/requests) with your requests to be a part of the Microsoft Store, and we’ll consider you for a future update.</span></span>  

<span data-ttu-id="71cf8-113">以下のプロセスの概要を使用して、パッケージ化の冒険をマップします。</span><span class="sxs-lookup"><span data-stu-id="71cf8-113">Use the process outline below to map out your packaging adventure!</span></span>  

## [<a name="extensions-in-the-windows-dev-center"></a><span data-ttu-id="71cf8-114">Windows デベロッパー センターの拡張機能</span><span class="sxs-lookup"><span data-stu-id="71cf8-114">Extensions in the Windows Dev Center</span></span>](./packaging/extensions-in-the-windows-dev-center.md)  

<span data-ttu-id="71cf8-115">手動またはマニホールドJS を選択したパッケージ作成ルートに関係なく、最初の手順は Windows Developer アカウントに登録し、拡張機能の名前を予約することです。</span><span class="sxs-lookup"><span data-stu-id="71cf8-115">No matter which package creation route you choose, manual or ManifoldJS, the first step is registering for a Windows Developer account and reserving the name(s) of your extension.</span></span>  

<span data-ttu-id="71cf8-116">これを行った後は、[拡張機能パッケージの作成とテスト][](./packaging/creating-and-testing-extension-packages.md)に進んで、AppXs の作成方法と拡張機能の手動パッケージ化方法を確認するか、簡単なルートに移動して「[マニホールドJS](./packaging/using-ManifoldJS-to-package-extensions.md)を使用して拡張機能をパッケージ化する」に移動します。</span><span class="sxs-lookup"><span data-stu-id="71cf8-116">Once you've done this, you can either move on to [Creating and testing extension packages](./packaging/creating-and-testing-extension-packages.md) to learn how AppXs are created and manually package your extension, or go the easier route and jump to [Using ManifoldJS to package extensions](./packaging/using-ManifoldJS-to-package-extensions.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="71cf8-117">Microsoft Store で拡張機能を利用できると承認された場合は、アプリ提出チェックリスト [を確認してください](https://docs.microsoft.com/windows/uwp/publish/app-submissions)。</span><span class="sxs-lookup"><span data-stu-id="71cf8-117">Once you've reached out to us and have been approved to have your extension in the Microsoft Store, check out the [app submission checklist](https://docs.microsoft.com/windows/uwp/publish/app-submissions).</span></span>  


## [<a name="creating-and-testing-extension-packages"></a><span data-ttu-id="71cf8-118">拡張機能パッケージの作成とテスト</span><span class="sxs-lookup"><span data-stu-id="71cf8-118">Creating and testing extension packages</span></span>](./packaging/creating-and-testing-extension-packages.md)  

<span data-ttu-id="71cf8-119">このガイドのセクションでは、Windows Developer アカウントを設定し、拡張機能名を予約した後に、手動で拡張パッケージを作成する [方法について説明します](./packaging/extensions-in-the-windows-Dev-Center.md)。</span><span class="sxs-lookup"><span data-stu-id="71cf8-119">This section of the guide walks through manual extension package creation once [you've set up your Windows Developer account and reserved your extension name(s)](./packaging/extensions-in-the-windows-Dev-Center.md).</span></span> <span data-ttu-id="71cf8-120">拡張機能のパッケージ化の詳細が気になる場合は、これを読み取って下さい。</span><span class="sxs-lookup"><span data-stu-id="71cf8-120">If you're curious about the finer details of packaging an extension, give this a read.</span></span>  

<span data-ttu-id="71cf8-121">パッケージ化された拡張機能をテストして解凍する方法 [に関する情報も含まれています](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)。</span><span class="sxs-lookup"><span data-stu-id="71cf8-121">Also included is info on how to [test and unpack a packaged extension](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package).</span></span> <span data-ttu-id="71cf8-122">この情報は、マニホールドJS のパッケージ化ルートを行った場合でも関連します。</span><span class="sxs-lookup"><span data-stu-id="71cf8-122">This info is relevant even if you've gone the ManifoldJS packaging route.</span></span>  

## [<a name="localizing-extension-packages"></a><span data-ttu-id="71cf8-123">拡張機能パッケージのローカライズ</span><span class="sxs-lookup"><span data-stu-id="71cf8-123">Localizing extension packages</span></span>](./packaging/localizing-extension-packages.md)  

<span data-ttu-id="71cf8-124">パッケージのローカライズ手順は、appxmanifest.xmlファイルを作成し、最終コマンドを実行して拡張機能をパッケージ化する場合の間に行います。</span><span class="sxs-lookup"><span data-stu-id="71cf8-124">The package localization step falls between creating your appxmanifest.xml file and running the final command to package your extension.</span></span>  
<span data-ttu-id="71cf8-125">これにより、Microsoft Store の登録情報で拡張機能がサポートする言語と、Windows で拡張機能の名前が表示される言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="71cf8-125">This allows you to indicate which languages your extensions supports in your Microsoft Store listing, and what language your extension's name appears in Windows.</span></span>  

<span data-ttu-id="71cf8-126">拡張機能が複数の言語をサポートしない場合は、ガイドのこのセクションで [Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) の名前と説明のローカライズにジャンプできます。</span><span class="sxs-lookup"><span data-stu-id="71cf8-126">You can jump to [Localizing name and description for the Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) in this section of the guide if your extension doesn't support multiple languages.</span></span>  

## [<a name="using-manifoldjs-to-package-extensions"></a><span data-ttu-id="71cf8-127">拡張機能をパッケージ化するために ManifoldJS を使用する</span><span class="sxs-lookup"><span data-stu-id="71cf8-127">Using ManifoldJS to package extensions</span></span>](./packaging/using-ManifoldJS-to-package-extensions.md)  

<span data-ttu-id="71cf8-128">拡張機能をパッケージ化するためのツール ルート、ManifoldJS は、最小限の労力で拡張機能を簡単にパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="71cf8-128">The tool route for packaging your extension, ManifoldJS will package up your extension in a snap with minimal effort on your end.</span></span> <span data-ttu-id="71cf8-129">AppXManifest プロパティを入力した後、いくつかの Windows/Microsoft Store アセットを提供すると、拡張機能はあっという間にパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="71cf8-129">Provide a few Windows/Microsoft Store assets after filling out some AppXManifest properties and your extension will be packaged in no time.</span></span>  

<span data-ttu-id="71cf8-130">拡張機能をパッケージ化したら、「Microsoft Edge[](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)拡張機能の作成とテスト」の「テスト」セクションを参照して、サイドロードまたはアンパックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71cf8-130">Once your extension is packaged, see the [testing](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing your Microsoft Edge extension to learn how to sideload or unpack it.</span></span>  

## [<a name="running-the-windows-app-certification-kit"></a><span data-ttu-id="71cf8-131">Windows アプリ認定キットの実行</span><span class="sxs-lookup"><span data-stu-id="71cf8-131">Running the Windows App Certification Kit</span></span>](./packaging/running-the-windows-app-certification-kit.md)  

<span data-ttu-id="71cf8-132">パッケージ化された拡張機能を取得したら、Windows アプリ認定キットを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="71cf8-132">Once you have a packaged extension, you can then run it through the Windows App Certification Kit.</span></span> <span data-ttu-id="71cf8-133">これにより、Microsoft Store の準備ができていることを確認するために、拡張機能パッケージで多数のテストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="71cf8-133">Doing so will run a number of tests on your extension package to ensure that it's ready for the Microsoft Store.</span></span>  
