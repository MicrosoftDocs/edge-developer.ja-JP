---
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
description: ネイティブメッセージングを使って、拡張機能とコンパニオン UWP アプリとの通信を行う方法について説明します。
title: 拡張機能-パッケージ化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 23c97f366db527cae2672d6ad46fa666583f6398
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569459"
---
# <span data-ttu-id="2d3fd-104">Microsoft Edge extensions のパッケージ化</span><span class="sxs-lookup"><span data-stu-id="2d3fd-104">Packaging Microsoft Edge extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="2d3fd-105">最後に拡張機能を完成させ、パッケージ化する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-105">So you've finally completed your extension and are ready to package it up.</span></span> <span data-ttu-id="2d3fd-106">次の手順は、潜在的なユーザーに対してこの作業を行うためのものです。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-106">You might be wondering what the next steps are toward getting this in the hands of potential users.</span></span> <span data-ttu-id="2d3fd-107">このガイドは、そのための方法を説明することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-107">This guide is intended to teach you how to do just that.</span></span>

<span data-ttu-id="2d3fd-108">拡張機能パッケージガイドは、パッケージ化について知っておく必要があるものをすべて網羅しており、細かい部分もあります。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-108">The extension packaging guide is comprehensive in that it covers everything you'd want to know about packaging, even the finer, nitty gritty details.</span></span> <span data-ttu-id="2d3fd-109">拡張機能のパッケージ化について知っておくべきことをすべて学習したくない場合は、運を気にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-109">If you don't want to learn everything there is to know about packaging your extension, you're in luck.</span></span> <span data-ttu-id="2d3fd-110">ManifoldJS の拡張機能のサポートを追加しました。このツールでは、パッケージ woes の大半を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-110">We've added support for extensions to ManifoldJS, an open source Node.js tool that takes the majority of your packaging woes away.</span></span>

> [!NOTE]
> <span data-ttu-id="2d3fd-111">Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-111">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="2d3fd-112">Microsoft Store の一部として要求が送信された場合は、skype[に](https://aka.ms/extension-request)連絡して、将来の更新についてご検討ください。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-112">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we’ll consider you for a future update.</span></span>


<span data-ttu-id="2d3fd-113">以下のプロセスの概要を使用して、パッケージの冒険をマッピングしてください。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-113">Use the process outline below to map out your packaging adventure!</span></span>


## [<span data-ttu-id="2d3fd-114">Windows デベロッパーセンターの拡張機能</span><span class="sxs-lookup"><span data-stu-id="2d3fd-114">Extensions in the Windows Dev Center</span></span>](./packaging/extensions-in-the-windows-dev-center.md)

<span data-ttu-id="2d3fd-115">どのパッケージ作成ルート (manual または ManifoldJS のいずれを選んでも、最初の手順では、Windows 開発者アカウントに登録し、内線番号の名前を予約しています。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-115">No matter which package creation route you choose, manual or ManifoldJS, the first step is registering for a Windows Developer account and reserving the name(s) of your extension.</span></span>

<span data-ttu-id="2d3fd-116">この操作を完了すると、[拡張パッケージの作成とテスト](./packaging/creating-and-testing-extension-packages.md)を行って、appxs の作成方法と拡張機能を手動でパッケージ化する方法、またはより簡単なルートに移動し[て、ManifoldJS を使ってパッケージの拡張子に](./packaging/using-ManifoldJS-to-package-extensions.md)移動することができます。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-116">Once you've done this, you can either move on to [Creating and testing extension packages](./packaging/creating-and-testing-extension-packages.md) to learn how AppXs are created and manually package your extension, or go the easier route and jump to [Using ManifoldJS to package extensions](./packaging/using-ManifoldJS-to-package-extensions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2d3fd-117">Microsoft Store の内線番号に登録されていることを確認したら、[[アプリの申請] チェックリスト](https://docs.microsoft.com/windows/uwp/publish/app-submissions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-117">Once you've reached out to us and have been approved to have your extension in the Microsoft Store, check out the [app submission checklist](https://docs.microsoft.com/windows/uwp/publish/app-submissions).</span></span>


## [<span data-ttu-id="2d3fd-118">拡張パッケージの作成とテスト</span><span class="sxs-lookup"><span data-stu-id="2d3fd-118">Creating and testing extension packages</span></span>](./packaging/creating-and-testing-extension-packages.md)

<span data-ttu-id="2d3fd-119">このセクションでは、 [Windows 開発者アカウントを設定し、内線番号を予約](./packaging/extensions-in-the-windows-Dev-Center.md)した後の手動による拡張パッケージの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-119">This section of the guide walks through manual extension package creation once [you've set up your Windows Developer account and reserved your extension name(s)](./packaging/extensions-in-the-windows-Dev-Center.md).</span></span> <span data-ttu-id="2d3fd-120">拡張機能のパッケージ化について詳しく知りたい場合は、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-120">If you're curious about the finer details of packaging an extension, give this a read.</span></span>

<span data-ttu-id="2d3fd-121">[パッケージ化された拡張機能のテストと展開](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)の方法に関する情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-121">Also included is info on how to [test and unpack a packaged extension](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package).</span></span> <span data-ttu-id="2d3fd-122">この情報は、ManifoldJS のパッケージルートを使用していない場合でも関連します。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-122">This info is relevant even if you've gone the ManifoldJS packaging route.</span></span>

## [<span data-ttu-id="2d3fd-123">拡張パッケージのローカライズ</span><span class="sxs-lookup"><span data-stu-id="2d3fd-123">Localizing extension packages</span></span>](./packaging/localizing-extension-packages.md)
<span data-ttu-id="2d3fd-124">パッケージのローカライズ手順では、package.appxmanifest ファイルを作成し、最後のコマンドを実行して拡張機能をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-124">The package localization step falls between creating your appxmanifest.xml file and running the final command to package your extension.</span></span>
<span data-ttu-id="2d3fd-125">これにより、Microsoft ストアの登録情報で、拡張機能でサポートされている言語と、Windows に拡張機能の名前が表示される言語を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-125">This allows you to indicate which languages your extensions supports in your Microsoft Store listing, and what language your extension's name appears in Windows.</span></span>

<span data-ttu-id="2d3fd-126">拡張機能で複数の言語がサポートされていない場合は、ガイドのこのセクションで[、Microsoft ストアの名前と説明のローカライズ](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store)に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-126">You can jump to [Localizing name and description for the Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) in this section of the guide if your extension doesn't support multiple languages.</span></span>

## [<span data-ttu-id="2d3fd-127">ManifoldJS を使って拡張子をパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="2d3fd-127">Using ManifoldJS to package extensions</span></span>](./packaging/using-ManifoldJS-to-package-extensions.md)

<span data-ttu-id="2d3fd-128">ManifoldJS は、拡張機能をパッケージ化するためのツールルートであり、お客様の最終的な作業を最小限に抑えて、スナップで拡張機能をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-128">The tool route for packaging your extension, ManifoldJS will package up your extension in a snap with minimal effort on your end.</span></span> <span data-ttu-id="2d3fd-129">いくつかの Package.appxmanifest プロパティに入力した後で、いくつかの Windows/Microsoft ストアアセットを提供します。拡張機能は、いつでもパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-129">Provide a few Windows/Microsoft Store assets after filling out some AppXManifest properties and your extension will be packaged in no time.</span></span>

<span data-ttu-id="2d3fd-130">拡張機能をパッケージ化したら、Microsoft Edge 拡張機能のサイドローディングまたは展開に関する[テスト](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-130">Once your extension is packaged, see the [testing](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing your Microsoft Edge extension to learn how to sideload or unpack it.</span></span>


## [<span data-ttu-id="2d3fd-131">Windows アプリ認定キットを実行する</span><span class="sxs-lookup"><span data-stu-id="2d3fd-131">Running the Windows App Certification Kit</span></span>](./packaging/running-the-windows-app-certification-kit.md)

<span data-ttu-id="2d3fd-132">パッケージ化された拡張子を取得したら、Windows アプリ認定キットを使ってその拡張機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-132">Once you have a packaged extension, you can then run it through the Windows App Certification Kit.</span></span> <span data-ttu-id="2d3fd-133">こうすることで、Microsoft ストアの準備ができていることを確認するため、拡張パッケージで多数のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d3fd-133">Doing so will run a number of tests on your extension package to ensure that it's ready for the Microsoft Store.</span></span>
