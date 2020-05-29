---
ms.assetid: c4397525-b978-4dc2-89bc-2198b3069742
description: ManifoldJS でのスナップで Microsoft Edge 拡張機能をパッケージ化する方法については、「.js open source ツール」を参照してください。
title: ManifoldJS を使って拡張子をパッケージ化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: cca83a26c9f80eca6454e3b5b329f72a7491b6e2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569441"
---
# <span data-ttu-id="63e11-104">ManifoldJS を使用して拡張 AppX パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="63e11-104">Using ManifoldJS to create extension AppX packages</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="63e11-105">ManifoldJS は、オープンなソースノード .js ツールであり、Microsoft ストアへの申請に使用できるパッケージをすばやくおり作成することができます。</span><span class="sxs-lookup"><span data-stu-id="63e11-105">ManifoldJS is an open source Node.js tool that allows you to quickly and painlessly create a package that you can then use for submission to the Microsoft Store.</span></span>

<span data-ttu-id="63e11-106">拡張機能でネイティブメッセージングを使用している場合は、この手順をスキップして、 [Microsoft Edge の [ネイティブメッセージング](../native-messaging.md#creating-an-extension-with-native-messaging)] に移動して、パッケージ化の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e11-106">If you use native messaging in your extension, you should skip this and go to [Native messaging in Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) for packaging instruction.</span></span> 

<span data-ttu-id="63e11-107">作業を始める前に、次の記事を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e11-107">Before getting started, you will still need to read up on the following articles:</span></span>

- [<span data-ttu-id="63e11-108">Windows デベロッパーセンターの拡張機能</span><span class="sxs-lookup"><span data-stu-id="63e11-108">Extensions in the Windows Dev Center</span></span>](./extensions-in-the-windows-dev-center.md)
- [<span data-ttu-id="63e11-109">拡張パッケージのローカライズ</span><span class="sxs-lookup"><span data-stu-id="63e11-109">Localizing extension packages</span></span>](./localizing-extension-packages.md)

> [!NOTE]
> <span data-ttu-id="63e11-110">Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="63e11-110">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="63e11-111">お客様の内線番号の作成、パッケージ化、テストが完了したら、[延長申請フォーム](https://aka.ms/extension-request)でリクエストを送信してください。</span><span class="sxs-lookup"><span data-stu-id="63e11-111">Once you've created, packaged and tested your extension, please submit a request on our [extension submission form](https://aka.ms/extension-request).</span></span>


## <span data-ttu-id="63e11-112">ノード .js と ManifoldJS のインストール</span><span class="sxs-lookup"><span data-stu-id="63e11-112">Installing Node.js and ManifoldJS</span></span>

<span data-ttu-id="63e11-113">まず、 [LTS](https://nodejs.org/en/download/)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e11-113">The first things you'll need to do is install [Node.js LTS](https://nodejs.org/en/download/).</span></span>
<span data-ttu-id="63e11-114">ノードを取得したら、コマンドライン (PowerShell を推奨) から次のコマンドを実行して、ManifoldJS をインストールします。</span><span class="sxs-lookup"><span data-stu-id="63e11-114">Once you have Node, from a command line (preferably PowerShell), run the following command to install ManifoldJS:</span></span>

`npm install -g manifoldjs`

<span data-ttu-id="63e11-115">ManifoldJS が正常にインストールされていることを確認するには、 `manifoldjs` コマンドラインから実行します。</span><span class="sxs-lookup"><span data-stu-id="63e11-115">To verify that you've correctly installed ManifoldJS, run `manifoldjs` from the command line.</span></span> <span data-ttu-id="63e11-116">ManifoldJS が認識されない場合は、 `%APPDATA%\npm` PATH 変数にを追加します。</span><span class="sxs-lookup"><span data-stu-id="63e11-116">If ManifoldJS wasn't recognized, add `%APPDATA%\npm` to your PATH variables.</span></span>

## <span data-ttu-id="63e11-117">ManifoldJS でパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="63e11-117">Packaging with ManifoldJS</span></span>

<span data-ttu-id="63e11-118">パッケージ処理を開始するには、コマンドラインを開き、パッケージ化された拡張のコピー先になるフォルダーにディレクトリを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e11-118">To start the packaging process, you'll need to open a command line and change directories to a folder that will be the destination for your packaged extension.</span></span>

<span data-ttu-id="63e11-119">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="63e11-119">For example:</span></span>

`cd C:\manifoldJSTest`

> [!NOTE]
> <span data-ttu-id="63e11-120">ManifoldJS は、現在のディレクトリに出力され、コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="63e11-120">ManifoldJS will output in the current directory and can overwrite content.</span></span>



<span data-ttu-id="63e11-121">目的のフォルダーに移動したら、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="63e11-121">Now that you're in your destination folder, run the following command:</span></span>

`manifoldjs -l debug -p edgeextension -f edgeextension -m <EXTENSION LOCATION>\manifest.json`


<span data-ttu-id="63e11-122">このコマンドは、次の部分に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="63e11-122">This command can be broken down into the following parts:</span></span>
 -    <span data-ttu-id="63e11-123">**-l debug**: ログレベルを [デバッグ] に変更し、完全に印刷されるようにします。</span><span class="sxs-lookup"><span data-stu-id="63e11-123">**-l debug**: Changes the log level to "debug" to get a full print out.</span></span>
 -    <span data-ttu-id="63e11-124">**-p edgeextension**: edgeextension への変換を実行する唯一のプラットフォームを設定します。</span><span class="sxs-lookup"><span data-stu-id="63e11-124">**-p edgeextension**: Sets the only platform to run the conversion on to edgeextension.</span></span>
 -    <span data-ttu-id="63e11-125">**-f edgeextension**: マニフェストの形式が edgeextension 形式であり、検証に失敗した場合は注意しないようプログラムに指示します。</span><span class="sxs-lookup"><span data-stu-id="63e11-125">**-f edgeextension**: Tells the program that the format of the manifest is an edgeextension format and not to care if it fails validation.</span></span>
 -    <span data-ttu-id="63e11-126">**-m \ < 拡張機能の場所 > \ manifest¥ json**: 変換する拡張機能マニフェストへのパス。</span><span class="sxs-lookup"><span data-stu-id="63e11-126">**-m \<EXTENSION LOCATION>\manifest.json**: The path to the extension manifest that you want to convert.</span></span>


<span data-ttu-id="63e11-127">ManifoldJS の実行が完了すると、次の内容のフォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63e11-127">After ManifoldJS has finished running, you'll have a folder with the following contents:</span></span>

    My Extension
        edgeextension
            generationInfo.json
            manifest
                   appxmanifest.xml
                Assets
                    Square150x150Logo.png
                    Square44x44Logo.png
                    StoreLogo.png    
                Extension
                    manifest.json
                    popup.html
                    ...
                ...

<span data-ttu-id="63e11-128">GenerationInfo ファイルは、ManifoldJS を実行して生成されたログであり、拡張機能パッケージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="63e11-128">The generationInfo.json file is a log produced by running ManifoldJS and won't be included in your extension package.</span></span> <span data-ttu-id="63e11-129">**マニフェスト**フォルダーのコンテンツのみがパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="63e11-129">Only the contents of the **manifest** folder will be packaged.</span></span> <span data-ttu-id="63e11-130">[マニフェスト] フォルダーでは、[アセット] フォルダーには、Windows と Microsoft Store の UI で使用する画像が含まれています。また、拡張機能のフォルダーには、拡張機能の内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63e11-130">Within the manifest folder, the Assets folder contains the images that will be used in the Windows and Microsoft Store UI, while the Extension folder has the contents of your extension within it.</span></span>


<span data-ttu-id="63e11-131">適切なファイルを作成したので、**マニフェスト**フォルダー内で、生成された package.appxmanifest ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e11-131">Now that you have the correct files, you'll need to edit the generated AppXManifest file within the **manifest** folder.</span></span> <span data-ttu-id="63e11-132">拡張機能の manifest.xml ファイルに "name" フィールドの国際化文字列が含まれている場合、ManifoldJS を実行すると、最上位のレイヤーフォルダー名にはアンダースコアがなく、"MSG" が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63e11-132">If the extension’s manifest.json file has an internationalized string for the "name" field, once ManifoldJS is run, the most top layer folder’s name will have no underscores and include "MSG".</span></span>

<span data-ttu-id="63e11-133">たとえば、次のフィールドを含む manifest.xml ファイル `"name"` 。</span><span class="sxs-lookup"><span data-stu-id="63e11-133">For example, a manifest.json file with the following `"name"` field:</span></span>

`"name" : "__MSG_appName__"`

<span data-ttu-id="63e11-134">存在するマニフェストフォルダーがあり `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` ます。</span><span class="sxs-lookup"><span data-stu-id="63e11-134">will have a manifest folder that lives in `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest`.</span></span>

<span data-ttu-id="63e11-135">Package.appxmanifest ファイルでは、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e11-135">In the AppXManifest file, you'll need to:</span></span>
 -    <span data-ttu-id="63e11-136">[ここで](./creating-and-testing-extension-packages.md#app-identity-template-values)説明するように、必須の id フィールドと PublisherDisplayName フィールドを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="63e11-136">Replace the required Identity fields and PublisherDisplayName field as outlined [here](./creating-and-testing-extension-packages.md#app-identity-template-values).</span></span> <span data-ttu-id="63e11-137">テスト目的またはエンタープライズ配布用にのみパッケージ化する場合は、Windows デベロッパーセンターアカウントに登録するのではなく、プレースホルダー値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63e11-137">Note that if you're only packaging for testing purposes or for enterprise distribution, you can use placeholder values instead of registering for a Windows Dev Center account.</span></span>
 -    <span data-ttu-id="63e11-138">[アセット] フォルダーのプレースホルダーアイコンを、同じサイズ (150x150、50x50、44x44)、名前の拡張機能のアイコンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="63e11-138">Replace the placeholder icons in the Assets folder with icons for your extension with the same sizes (150x150, 50x50, 44x44) and names.</span></span> <span data-ttu-id="63e11-139">これらのアイコンが使用されている場所については、[設計](./../design.md#icons-for-packaging)ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63e11-139">See the [Design](./../design.md#icons-for-packaging) guide for information about where these icons are used.</span></span>
 - <span data-ttu-id="63e11-140">拡張機能がローカライズされている場合は、「 [Microsoft Edge のローカライズ](./localizing-extension-packages.md)ガイド」の全機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="63e11-140">If your extension is localized, follow the entire [Localizing Microsoft Edge extensions](./localizing-extension-packages.md) guide.</span></span> <span data-ttu-id="63e11-141">ローカライズされていない場合は、「 [Microsoft Store」セクションでローカライズする名前と説明](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store)のみを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63e11-141">If it isn't localized, only read the [Localizing name and description in the Microsoft Store](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) section.</span></span>

<span data-ttu-id="63e11-142">Package.appxmanifest ファイルが並べ替えられたら、次のコマンドを実行してパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="63e11-142">Once your appxmanifest.xml file is sorted out, run the following command to create your package:</span></span>

`manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\`

<span data-ttu-id="63e11-143">これで、パッケージが edgeextension フォルダー内の**パッケージ**フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="63e11-143">Your package will now be in the **package** folder located within the edgeextension folder.</span></span> <span data-ttu-id="63e11-144">新しいパッケージをサイドローディングする方法について詳しくは、「拡張パッケージの[テスト](./creating-and-testing-extension-packages.md#testing-an-appx-package)とテスト」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63e11-144">See Creating and testing extension packages' [testing](./creating-and-testing-extension-packages.md#testing-an-appx-package) section for info on how to sideload your new package.</span></span>

<span data-ttu-id="63e11-145">パッケージのテストが完了したら、Microsoft ストアへの公開を検討するために、[内線番号の申請フォーム](https://aka.ms/extension-request)で要求を送信してください。</span><span class="sxs-lookup"><span data-stu-id="63e11-145">Once your package has been tested, feel free to submit a request on our [extension submission form](https://aka.ms/extension-request) in order to be considered for publication to the Microsoft Store.</span></span>
