---
ms.assetid: c4397525-b978-4dc2-89bc-2198b3069742
description: ManifoldJS でのスナップで Microsoft Edge 拡張機能をパッケージ化する方法については、「ソースの Node.js ツール」を参照してください。
title: 拡張機能をパッケージ化するために ManifoldJS を使用する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: 83aa57ae0e4ae302b1360be50e5158782b6fbb76
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986207"
---
# <span data-ttu-id="4631f-104">ManifoldJS を使用して拡張 AppX パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="4631f-104">Using ManifoldJS to create extension AppX packages</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="4631f-105">ManifoldJS はオープンソース Node.js ツールであり、Microsoft ストアへの申請に使用できるパッケージをすばやくおり作成できます。</span><span class="sxs-lookup"><span data-stu-id="4631f-105">ManifoldJS is an open source Node.js tool that allows you to quickly and painlessly create a package that you can then use for submission to the Microsoft Store.</span></span>  

<span data-ttu-id="4631f-106">拡張機能でネイティブメッセージングを使用している場合は、次の記事をスキップして、「 [Microsoft Edge でのネイティブメッセージング](../native-messaging.md#creating-an-extension-with-native-messaging) によるパッケージ化の手順」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4631f-106">If you use native messaging in your extension, you should skip the following article and go to [Native messaging in Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) for packaging instruction.</span></span>  

<span data-ttu-id="4631f-107">作業を始める前に、次の記事を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4631f-107">Before getting started, you will still need to read up on the following articles.</span></span>  

*   [<span data-ttu-id="4631f-108">Windows デベロッパー センターの拡張機能</span><span class="sxs-lookup"><span data-stu-id="4631f-108">Extensions in the Windows Dev Center</span></span>](./extensions-in-the-windows-dev-center.md)  
*   [<span data-ttu-id="4631f-109">拡張機能パッケージのローカライズ</span><span class="sxs-lookup"><span data-stu-id="4631f-109">Localizing extension packages</span></span>](./localizing-extension-packages.md)  

> [!NOTE]
> <span data-ttu-id="4631f-110">Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="4631f-110">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="4631f-111">お客様の内線番号の作成、パッケージ化、テストが完了したら、 [延長申請フォーム](https://developer.microsoft.com/microsoft-edge/extensions/requests)でリクエストを送信してください。</span><span class="sxs-lookup"><span data-stu-id="4631f-111">Once you have created, packaged and tested your extension, please submit a request on our [extension submission form](https://developer.microsoft.com/microsoft-edge/extensions/requests).</span></span>  

## <span data-ttu-id="4631f-112">Node.js と ManifoldJS のインストール</span><span class="sxs-lookup"><span data-stu-id="4631f-112">Installing Node.js and ManifoldJS</span></span>  

<span data-ttu-id="4631f-113">最初に [Node.js LTS](https://nodejs.org/en/download)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4631f-113">The first things you will need to do is install [Node.js LTS](https://nodejs.org/en/download).</span></span>  
<span data-ttu-id="4631f-114">ノードを取得したら、コマンドライン (PowerShell を推奨) から次のコマンドを実行して、ManifoldJS をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4631f-114">Once you have Node, from a command line (preferably PowerShell), run the following command to install ManifoldJS.</span></span>  

```shell
npm install -g manifoldjs
```  

<span data-ttu-id="4631f-115">ManifoldJS が正常にインストールされていることを確認するには、 `manifoldjs` コマンドラインから実行します。</span><span class="sxs-lookup"><span data-stu-id="4631f-115">To verify that you have correctly installed ManifoldJS, run `manifoldjs` from the command line.</span></span> <span data-ttu-id="4631f-116">ManifoldJS が認識されない場合は、 `%APPDATA%\npm` PATH 変数にを追加します。</span><span class="sxs-lookup"><span data-stu-id="4631f-116">If ManifoldJS was not recognized, add `%APPDATA%\npm` to your PATH variables.</span></span>  

## <span data-ttu-id="4631f-117">ManifoldJS でパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="4631f-117">Packaging with ManifoldJS</span></span>  

<span data-ttu-id="4631f-118">パッケージ処理を開始するには、コマンドラインを開き、パッケージ化された拡張のコピー先になるフォルダーにディレクトリを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4631f-118">To start the packaging process, you will need to open a command line and change directories to a folder that will be the destination for your packaged extension.</span></span>  

<span data-ttu-id="4631f-119">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="4631f-119">For example:</span></span>

```shell
cd C:\manifoldJSTest
```  

> [!NOTE]
> <span data-ttu-id="4631f-120">コマンドは、 `manifoldjs` 現在のディレクトリに出力され、コンテンツが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="4631f-120">The `manifoldjs` command outputs in the current directory and overwrites content.</span></span>  

<span data-ttu-id="4631f-121">目的のフォルダーに移動したら、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4631f-121">Now that you are in your destination folder, run the following command.</span></span>  

```shell
manifoldjs -l debug -p edgeextension -f edgeextension -m path\to\manifest.json
```  

<span data-ttu-id="4631f-122">`mainifoldjs`コマンドは次の部分に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="4631f-122">The `mainifoldjs` command can be broken down into the following parts.</span></span>  

:::row:::
   :::column span="1":::
      `-l debug`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4631f-123">ログレベルを変更して完全に印刷されるようにし `debug` ます。</span><span class="sxs-lookup"><span data-stu-id="4631f-123">Changes the log level to `debug` to get a full print out.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-p edgeextension`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4631f-124">への変換を実行する唯一のプラットフォームを設定 `edgeextension` します。</span><span class="sxs-lookup"><span data-stu-id="4631f-124">Sets the only platform to run the conversion on to `edgeextension`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-f edgeextension`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4631f-125">マニフェストの形式が形式であり、 `edgeextension` 検証に失敗した場合は注意しないようにプログラムに指示します。</span><span class="sxs-lookup"><span data-stu-id="4631f-125">Tells the program that the format of the manifest is an `edgeextension` format and not to care if it fails validation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-m \path\to\manifest.json`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4631f-126">変換する拡張機能マニフェストへのパス。</span><span class="sxs-lookup"><span data-stu-id="4631f-126">The path to the extension manifest that you want to convert.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="4631f-127">ManifoldJS の実行が完了すると、次の内容のフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4631f-127">After ManifoldJS has finished running, you will have a folder with the following contents.</span></span>  

```text
┌ My Extension
└┬ edgeextension
 ├- generationInfo.json
 └┬ manifest
  ├- appxmanifest.xml
  ├┬ Assets
  |├- Square150x150Logo.png
  |├- Square44x44Logo.png
  |└- StoreLogo.png    
  └┬ Extension
   ├- manifest.json
   └- popup.html
```  
<!-- 
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
-->  

<span data-ttu-id="4631f-128">ファイルの generationInfo.jsは、ManifoldJS を実行することによって生成されたログであり、拡張機能パッケージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="4631f-128">The generationInfo.json file is a log produced by running ManifoldJS and will not be included in your extension package.</span></span> <span data-ttu-id="4631f-129">フォルダーの内容のみ `manifest` がパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="4631f-129">Only the contents of the `manifest` folder will be packaged.</span></span> <span data-ttu-id="4631f-130">[マニフェスト] フォルダーでは、[アセット] フォルダーには、Windows と Microsoft Store の UI で使用する画像が含まれています。また、拡張機能のフォルダーには、拡張機能の内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4631f-130">Within the manifest folder, the Assets folder contains the images that will be used in the Windows and Microsoft Store UI, while the Extension folder has the contents of your extension within it.</span></span>  

<span data-ttu-id="4631f-131">適切なファイルを作成したので、フォルダー内で生成された Package.appxmanifest ファイルを編集する必要があり `manifest` ます。</span><span class="sxs-lookup"><span data-stu-id="4631f-131">Now that you have the correct files, you will need to edit the generated AppXManifest file within the `manifest` folder.</span></span> <span data-ttu-id="4631f-132">ファイルの拡張子の manifest.jsに "name" フィールドの国際化文字列が含まれている場合、ManifoldJS が実行されると、最上位のレイヤーのフォルダー名にアンダースコアは表示されず、"MSG" が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4631f-132">If the extension’s manifest.json file has an internationalized string for the "name" field, once ManifoldJS is run, the most top layer folder’s name will have no underscores and include "MSG".</span></span>

<span data-ttu-id="4631f-133">たとえば、次のフィールドを含むファイルに manifest.jsし `"name"` ます。</span><span class="sxs-lookup"><span data-stu-id="4631f-133">For example, a manifest.json file with the following `"name"` field.</span></span>  

```shell
"name" : "__MSG_appName__"
```  

<span data-ttu-id="4631f-134">存在するマニフェストフォルダーがあり `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` ます。</span><span class="sxs-lookup"><span data-stu-id="4631f-134">will have a manifest folder that lives in `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest`.</span></span>  

<span data-ttu-id="4631f-135">Package.appxmanifest ファイルでは、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4631f-135">In the AppXManifest file, you will need to:</span></span>  

 *   <span data-ttu-id="4631f-136">[ここで](./creating-and-testing-extension-packages.md#app-identity-template-values)説明するように、必須の id フィールドと PublisherDisplayName フィールドを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4631f-136">Replace the required Identity fields and PublisherDisplayName field as outlined [here](./creating-and-testing-extension-packages.md#app-identity-template-values).</span></span> <span data-ttu-id="4631f-137">テスト目的またはエンタープライズ配布用にのみパッケージ化する場合は、Windows デベロッパーセンターアカウントに登録するのではなく、プレースホルダー値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4631f-137">Note that if you are only packaging for testing purposes or for enterprise distribution, you can use placeholder values instead of registering for a Windows Dev Center account.</span></span>  
 *   <span data-ttu-id="4631f-138">[アセット] フォルダーのプレースホルダーアイコンを、同じサイズ (150x150、50x50、44x44)、名前の拡張機能のアイコンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4631f-138">Replace the placeholder icons in the Assets folder with icons for your extension with the same sizes (150x150, 50x50, 44x44) and names.</span></span> <span data-ttu-id="4631f-139">これらのアイコンが使用されている場所については、 [設計](./../design.md#icons-for-packaging) ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4631f-139">See the [Design](./../design.md#icons-for-packaging) guide for information about where these icons are used.</span></span>  
 *   <span data-ttu-id="4631f-140">拡張機能がローカライズされている場合は、「 [Microsoft Edge のローカライズ](./localizing-extension-packages.md) ガイド」の全機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="4631f-140">If your extension is localized, follow the entire [Localizing Microsoft Edge extensions](./localizing-extension-packages.md) guide.</span></span> <span data-ttu-id="4631f-141">ローカライズされていない場合は、「Microsoft Store」セクションの [ローカライズの名前と説明](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) のみを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4631f-141">If it is not localized, only read the [Localizing name and description in the Microsoft Store](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) section.</span></span>  

<span data-ttu-id="4631f-142">`appxmanifest.xml`ファイルが並べ替えられたら、次のコマンドを実行してパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="4631f-142">Once your `appxmanifest.xml` file is sorted out, run the following command to create your package.</span></span>  

```shell
manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\
```  

<span data-ttu-id="4631f-143">これで、パッケージが edgeextension フォルダー内の **パッケージ** フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4631f-143">Your package will now be in the **package** folder located within the edgeextension folder.</span></span> <span data-ttu-id="4631f-144">新しいパッケージをサイドローディングする方法について詳しくは、「拡張パッケージの作成とテスト」の「 [テスト](./creating-and-testing-extension-packages.md#testing-an-appx-package) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4631f-144">For more information about how to sideload your new package, see [testing](./creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing extension packages.</span></span>  

<span data-ttu-id="4631f-145">パッケージのテストが完了したら、Microsoft ストアへの公開を検討するために、 [内線番号の申請フォーム](https://aka.ms/extension-request) で要求を送信してください。</span><span class="sxs-lookup"><span data-stu-id="4631f-145">Once your package has been tested, feel free to submit a request on our [extension submission form](https://aka.ms/extension-request) in order to be considered for publication to the Microsoft Store.</span></span>  
