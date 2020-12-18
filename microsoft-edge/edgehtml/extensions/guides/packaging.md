---
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
description: 拡張機能をパッケージ化する方法について学習します。
title: 拡張機能 - パッケージ化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0ea4d6a4450d47d116164fd8481fdfb0f79bd30b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234944"
---
# <span data-ttu-id="49377-104">Microsoft Edge 拡張機能のパッケージ化</span><span class="sxs-lookup"><span data-stu-id="49377-104">Packaging Microsoft Edge extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="49377-105">最後に拡張機能が完成し、パッケージ化する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="49377-105">So you've finally completed your extension and are ready to package it up.</span></span> <span data-ttu-id="49377-106">潜在的なユーザーの手でこれを実現するための次の手順は何か疑問に思うでしょう。</span><span class="sxs-lookup"><span data-stu-id="49377-106">You might be wondering what the next steps are toward getting this in the hands of potential users.</span></span> <span data-ttu-id="49377-107">このガイドは、その方法を教えることを目的にしています。</span><span class="sxs-lookup"><span data-stu-id="49377-107">This guide is intended to teach you how to do just that.</span></span>

<span data-ttu-id="49377-108">拡張機能のパッケージ 化ガイドは、パッケージ化に関して知りたいすべての情報を含む包括的なガイドです。さらに細かく、細かい詳細な詳細も含まれています。</span><span class="sxs-lookup"><span data-stu-id="49377-108">The extension packaging guide is comprehensive in that it covers everything you'd want to know about packaging, even the finer, nitty gritty details.</span></span> <span data-ttu-id="49377-109">拡張機能のパッケージ化について知る必要があるすべての情報を知りたくない場合は、幸いです。</span><span class="sxs-lookup"><span data-stu-id="49377-109">If you don't want to learn everything there is to know about packaging your extension, you're in luck.</span></span> <span data-ttu-id="49377-110">パッケージ化の問題の大部分を取り上Node.jsオープン ソース ソース ツールである、MajorityJS の拡張機能のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="49377-110">We've added support for extensions to ManifoldJS, an open source Node.js tool that takes the majority of your packaging woes away.</span></span>

> [!NOTE]
> <span data-ttu-id="49377-111">Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="49377-111">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="49377-112">Microsoft Store[の一](https://aka.ms/extension-request)部としてお客様からのリクエストをお問い合わせください。今後の更新について検討します。</span><span class="sxs-lookup"><span data-stu-id="49377-112">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we’ll consider you for a future update.</span></span>


<span data-ttu-id="49377-113">以下のプロセス アウトラインを使用して、パッケージ化の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="49377-113">Use the process outline below to map out your packaging adventure!</span></span>


## [<span data-ttu-id="49377-114">Windows デベロッパー センターの拡張機能</span><span class="sxs-lookup"><span data-stu-id="49377-114">Extensions in the Windows Dev Center</span></span>](./packaging/extensions-in-the-windows-dev-center.md)

<span data-ttu-id="49377-115">選ぶパッケージの作成ルート (手動または分作JS) に関係なく、最初の手順は Windows 開発者アカウントに登録し、拡張機能の名前を予約することです。</span><span class="sxs-lookup"><span data-stu-id="49377-115">No matter which package creation route you choose, manual or ManifoldJS, the first step is registering for a Windows Developer account and reserving the name(s) of your extension.</span></span>

<span data-ttu-id="49377-116">これを行った後は、拡張機能パッケージの作成とテストに[](./packaging/creating-and-testing-extension-packages.md)進み、AppX の作成方法と拡張機能の手動パッケージ化方法を確認するか、簡単なルートに移動して[、ExtensionJS](./packaging/using-ManifoldJS-to-package-extensions.md)を使用して拡張機能をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="49377-116">Once you've done this, you can either move on to [Creating and testing extension packages](./packaging/creating-and-testing-extension-packages.md) to learn how AppXs are created and manually package your extension, or go the easier route and jump to [Using ManifoldJS to package extensions](./packaging/using-ManifoldJS-to-package-extensions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="49377-117">Microsoft Store にアクセスして拡張機能の提供が承認された後は、アプリの申請のチェックリスト [を確認してください](https://docs.microsoft.com/windows/uwp/publish/app-submissions)。</span><span class="sxs-lookup"><span data-stu-id="49377-117">Once you've reached out to us and have been approved to have your extension in the Microsoft Store, check out the [app submission checklist](https://docs.microsoft.com/windows/uwp/publish/app-submissions).</span></span>


## [<span data-ttu-id="49377-118">拡張機能パッケージの作成とテスト</span><span class="sxs-lookup"><span data-stu-id="49377-118">Creating and testing extension packages</span></span>](./packaging/creating-and-testing-extension-packages.md)

<span data-ttu-id="49377-119">このガイドのこのセクションでは、Windows 開発者アカウントを設定し、拡張機能名を予約した後に、拡張機能パッケージを手動で作成する方法 [について説明します](./packaging/extensions-in-the-windows-Dev-Center.md)。</span><span class="sxs-lookup"><span data-stu-id="49377-119">This section of the guide walks through manual extension package creation once [you've set up your Windows Developer account and reserved your extension name(s)](./packaging/extensions-in-the-windows-Dev-Center.md).</span></span> <span data-ttu-id="49377-120">拡張機能のパッケージ化の詳細について知りたがっている場合は、この記事を読んでおきます。</span><span class="sxs-lookup"><span data-stu-id="49377-120">If you're curious about the finer details of packaging an extension, give this a read.</span></span>

<span data-ttu-id="49377-121">パッケージ化された拡張機能をテストして展開 [する方法に関する情報も含まれています](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)。</span><span class="sxs-lookup"><span data-stu-id="49377-121">Also included is info on how to [test and unpack a packaged extension](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package).</span></span> <span data-ttu-id="49377-122">この情報は、分かっている場合でも関連します。</span><span class="sxs-lookup"><span data-stu-id="49377-122">This info is relevant even if you've gone the ManifoldJS packaging route.</span></span>

## [<span data-ttu-id="49377-123">拡張機能パッケージのローカライズ</span><span class="sxs-lookup"><span data-stu-id="49377-123">Localizing extension packages</span></span>](./packaging/localizing-extension-packages.md)
<span data-ttu-id="49377-124">パッケージのローカライズ手順は、appxmanifest.xml ファイルを作成し、拡張機能をパッケージ化する最後のコマンドを実行する手順の間に含まれます。</span><span class="sxs-lookup"><span data-stu-id="49377-124">The package localization step falls between creating your appxmanifest.xml file and running the final command to package your extension.</span></span>
<span data-ttu-id="49377-125">これにより、Microsoft Store 登録情報で拡張機能がサポートする言語と、拡張機能の名前が Windows に表示される言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="49377-125">This allows you to indicate which languages your extensions supports in your Microsoft Store listing, and what language your extension's name appears in Windows.</span></span>

<span data-ttu-id="49377-126">拡張機能が複数の言語をサポートしない場合は、ガイドのこのセクションで [Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) のローカライズ名と説明に移動できます。</span><span class="sxs-lookup"><span data-stu-id="49377-126">You can jump to [Localizing name and description for the Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) in this section of the guide if your extension doesn't support multiple languages.</span></span>

## [<span data-ttu-id="49377-127">拡張機能をパッケージ化するために ManifoldJS を使用する</span><span class="sxs-lookup"><span data-stu-id="49377-127">Using ManifoldJS to package extensions</span></span>](./packaging/using-ManifoldJS-to-package-extensions.md)

<span data-ttu-id="49377-128">Extension をパッケージ化するためのツール ルート、MinimalJS は最小限の労力で拡張機能をスナップでパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="49377-128">The tool route for packaging your extension, ManifoldJS will package up your extension in a snap with minimal effort on your end.</span></span> <span data-ttu-id="49377-129">AppXManifest プロパティを入力した後、いくつかの Windows/Microsoft Store アセットを提供すると、拡張機能はあっという間にパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="49377-129">Provide a few Windows/Microsoft Store assets after filling out some AppXManifest properties and your extension will be packaged in no time.</span></span>

<span data-ttu-id="49377-130">拡張機能をパッケージ化したら、「Microsoft Edge[](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)拡張機能の作成とテスト」のテスト セクションを参照して、サイドロードまたはアンパックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49377-130">Once your extension is packaged, see the [testing](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing your Microsoft Edge extension to learn how to sideload or unpack it.</span></span>


## [<span data-ttu-id="49377-131">Windows アプリ認定キットの実行</span><span class="sxs-lookup"><span data-stu-id="49377-131">Running the Windows App Certification Kit</span></span>](./packaging/running-the-windows-app-certification-kit.md)

<span data-ttu-id="49377-132">パッケージ化された拡張機能を取得したら、Windows アプリ認定キットから実行できます。</span><span class="sxs-lookup"><span data-stu-id="49377-132">Once you have a packaged extension, you can then run it through the Windows App Certification Kit.</span></span> <span data-ttu-id="49377-133">そうすると、拡張機能パッケージに対して多数のテストが実行されます。これにより、Microsoft Store の準備ができていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="49377-133">Doing so will run a number of tests on your extension package to ensure that it's ready for the Microsoft Store.</span></span>
