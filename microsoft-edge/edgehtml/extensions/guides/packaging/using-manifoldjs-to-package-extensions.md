---
ms.assetid: c4397525-b978-4dc2-89bc-2198b3069742
description: Microsoft Edge 拡張機能を、オープン ソース ツールである、Node.jsでパッケージ化する方法について説明します。
title: 拡張機能をパッケージ化するために ManifoldJS を使用する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 151a8b2ababb25e0964a6fbc2696b5fdc059d084
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234921"
---
# <span data-ttu-id="1000a-104">Extension AppX パッケージの作成に、ManifoldJS を使用する</span><span class="sxs-lookup"><span data-stu-id="1000a-104">Using ManifoldJS to create extension AppX packages</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="1000a-105">ManifoldJS はオープン ソース Node.js ツールで、Microsoft Store への申請に使えるパッケージをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="1000a-105">ManifoldJS is an open source Node.js tool that allows you to quickly and painlessly create a package that you can then use for submission to the Microsoft Store.</span></span>  

<span data-ttu-id="1000a-106">拡張機能でネイティブ メッセージングを使用する場合は、次の記事をスキップし、パッケージ化の手順については [Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) のネイティブ メッセージングに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1000a-106">If you use native messaging in your extension, you should skip the following article and go to [Native messaging in Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) for packaging instruction.</span></span>  

<span data-ttu-id="1000a-107">開始する前に、次の記事を読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1000a-107">Before getting started, you will still need to read up on the following articles.</span></span>  

*   [<span data-ttu-id="1000a-108">Windows デベロッパー センターの拡張機能</span><span class="sxs-lookup"><span data-stu-id="1000a-108">Extensions in the Windows Dev Center</span></span>](./extensions-in-the-windows-dev-center.md)  
*   [<span data-ttu-id="1000a-109">拡張機能パッケージのローカライズ</span><span class="sxs-lookup"><span data-stu-id="1000a-109">Localizing extension packages</span></span>](./localizing-extension-packages.md)  

> [!NOTE]
> <span data-ttu-id="1000a-110">Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="1000a-110">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="1000a-111">拡張機能を作成、パッケージ化、テストしたら、拡張機能の提出フォームで要求 [を送信してください](https://developer.microsoft.com/microsoft-edge/extensions/requests)。</span><span class="sxs-lookup"><span data-stu-id="1000a-111">Once you have created, packaged and tested your extension, please submit a request on our [extension submission form](https://developer.microsoft.com/microsoft-edge/extensions/requests).</span></span>  

## <span data-ttu-id="1000a-112">システムとNode.js JS のインストール</span><span class="sxs-lookup"><span data-stu-id="1000a-112">Installing Node.js and ManifoldJS</span></span>  

<span data-ttu-id="1000a-113">最初に行う必要があるのは [ 、LTSNode.jsです](https://nodejs.org/en/download)。</span><span class="sxs-lookup"><span data-stu-id="1000a-113">The first things you will need to do is install [Node.js LTS](https://nodejs.org/en/download).</span></span>  
<span data-ttu-id="1000a-114">Node を取得したら、コマンド ライン (PowerShell が望ましい) から次のコマンドを実行して、ManifoldJS をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1000a-114">Once you have Node, from a command line (preferably PowerShell), run the following command to install ManifoldJS.</span></span>  

```shell
npm install -g manifoldjs
```  

<span data-ttu-id="1000a-115">CorrectlyJS が正しくインストールされていることを確認するには、コマンド `manifoldjs` ラインから実行します。</span><span class="sxs-lookup"><span data-stu-id="1000a-115">To verify that you have correctly installed ManifoldJS, run `manifoldjs` from the command line.</span></span> <span data-ttu-id="1000a-116">1 つも認識されない場合は `%APPDATA%\npm` 、PATH 変数に追加します。</span><span class="sxs-lookup"><span data-stu-id="1000a-116">If ManifoldJS was not recognized, add `%APPDATA%\npm` to your PATH variables.</span></span>  

## <span data-ttu-id="1000a-117">ManifoldJS を使用したパッケージ化</span><span class="sxs-lookup"><span data-stu-id="1000a-117">Packaging with ManifoldJS</span></span>  

<span data-ttu-id="1000a-118">パッケージ化プロセスを開始するには、コマンド ラインを開き、パッケージ化された拡張機能の宛先になるフォルダーにディレクトリを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1000a-118">To start the packaging process, you will need to open a command line and change directories to a folder that will be the destination for your packaged extension.</span></span>  

<span data-ttu-id="1000a-119">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="1000a-119">For example:</span></span>

```shell
cd C:\manifoldJSTest
```  

> [!NOTE]
> <span data-ttu-id="1000a-120">コマンド `manifoldjs` は現在のディレクトリに出力し、コンテンツを上書きします。</span><span class="sxs-lookup"><span data-stu-id="1000a-120">The `manifoldjs` command outputs in the current directory and overwrites content.</span></span>  

<span data-ttu-id="1000a-121">移動先フォルダーに移動した後、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1000a-121">Now that you are in your destination folder, run the following command.</span></span>  

```shell
manifoldjs -l debug -p edgeextension -f edgeextension -m path\to\manifest.json
```  

<span data-ttu-id="1000a-122">この `mainifoldjs` コマンドは、次の部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="1000a-122">The `mainifoldjs` command can be broken down into the following parts.</span></span>  

:::row:::
   :::column span="1":::
      `-l debug`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1000a-123">ログ レベルを変更して `debug` 、完全な印刷を取得します。</span><span class="sxs-lookup"><span data-stu-id="1000a-123">Changes the log level to `debug` to get a full print out.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-p edgeextension`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1000a-124">変換を実行する唯一のプラットフォームを設定します `edgeextension` 。</span><span class="sxs-lookup"><span data-stu-id="1000a-124">Sets the only platform to run the conversion on to `edgeextension`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-f edgeextension`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1000a-125">マニフェストの形式が形式であり、検証に失敗した場合 `edgeextension` は注意が必要で、プログラムに指示します。</span><span class="sxs-lookup"><span data-stu-id="1000a-125">Tells the program that the format of the manifest is an `edgeextension` format and not to care if it fails validation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-m \path\to\manifest.json`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1000a-126">変換する拡張機能マニフェストへのパス。</span><span class="sxs-lookup"><span data-stu-id="1000a-126">The path to the extension manifest that you want to convert.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="1000a-127">読み込み完了したら、次の内容のフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1000a-127">After ManifoldJS has finished running, you will have a folder with the following contents.</span></span>  

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

<span data-ttu-id="1000a-128">The generationInfo.json file is a log produced by running ManifoldJS and will not be included in your extension package.</span><span class="sxs-lookup"><span data-stu-id="1000a-128">The generationInfo.json file is a log produced by running ManifoldJS and will not be included in your extension package.</span></span> <span data-ttu-id="1000a-129">フォルダーの内容 `manifest` だけがパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="1000a-129">Only the contents of the `manifest` folder will be packaged.</span></span> <span data-ttu-id="1000a-130">マニフェスト フォルダー内の Assets フォルダーには、Windows と Microsoft Store の UI で使用されるイメージが含まれますが、Extension フォルダーには拡張機能の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1000a-130">Within the manifest folder, the Assets folder contains the images that will be used in the Windows and Microsoft Store UI, while the Extension folder has the contents of your extension within it.</span></span>  

<span data-ttu-id="1000a-131">これで適切なファイルが作成されたので、生成された AppXManifest ファイルをフォルダー内で編集する必要 `manifest` があります。</span><span class="sxs-lookup"><span data-stu-id="1000a-131">Now that you have the correct files, you will need to edit the generated AppXManifest file within the `manifest` folder.</span></span> <span data-ttu-id="1000a-132">拡張子の manifest.json ファイルに "name" フィールドの国際化文字列が含まれている場合、一度、UnderscoreJS を実行すると、最も上位のレイヤー フォルダーの名前にはアンダースコアが付けらなく、"MSG" が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1000a-132">If the extension’s manifest.json file has an internationalized string for the "name" field, once ManifoldJS is run, the most top layer folder’s name will have no underscores and include "MSG".</span></span>

<span data-ttu-id="1000a-133">たとえば、次のフィールドmanifest.jsを含むファイルに対してファイルを作成 `"name"` できます。</span><span class="sxs-lookup"><span data-stu-id="1000a-133">For example, a manifest.json file with the following `"name"` field.</span></span>  

```shell
"name" : "__MSG_appName__"
```  

<span data-ttu-id="1000a-134">マニフェスト フォルダーが含まれます `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` 。</span><span class="sxs-lookup"><span data-stu-id="1000a-134">will have a manifest folder that lives in `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest`.</span></span>  

<span data-ttu-id="1000a-135">AppXManifest ファイルでは、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="1000a-135">In the AppXManifest file, you will need to:</span></span>  

 *   <span data-ttu-id="1000a-136">ここで説明する必要な Identity フィールドと PublisherDisplayName フィールドを置き換 [える](./creating-and-testing-extension-packages.md#app-identity-template-values)。</span><span class="sxs-lookup"><span data-stu-id="1000a-136">Replace the required Identity fields and PublisherDisplayName field as outlined [here](./creating-and-testing-extension-packages.md#app-identity-template-values).</span></span> <span data-ttu-id="1000a-137">テスト目的またはエンタープライズ配布のみを目的としてパッケージ化する場合は、Windows デベロッパー センター アカウントに登録する代わりにプレースホルダー値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1000a-137">Note that if you are only packaging for testing purposes or for enterprise distribution, you can use placeholder values instead of registering for a Windows Dev Center account.</span></span>  
 *   <span data-ttu-id="1000a-138">Assets フォルダー内のプレースホルダー アイコンを、同じサイズ (150x150、50x50、44x44) と名前を持つ拡張機能のアイコンに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="1000a-138">Replace the placeholder icons in the Assets folder with icons for your extension with the same sizes (150x150, 50x50, 44x44) and names.</span></span> <span data-ttu-id="1000a-139">これらのアイコン [が使用](./../design.md#icons-for-packaging) される場所については、デザイン ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1000a-139">See the [Design](./../design.md#icons-for-packaging) guide for information about where these icons are used.</span></span>  
 *   <span data-ttu-id="1000a-140">拡張機能がローカライズされている場合は、Localizing Microsoft Edge 拡張機能ガイド [全体に従](./localizing-extension-packages.md) ってください。</span><span class="sxs-lookup"><span data-stu-id="1000a-140">If your extension is localized, follow the entire [Localizing Microsoft Edge extensions](./localizing-extension-packages.md) guide.</span></span> <span data-ttu-id="1000a-141">ローカライズされていない場合は、Microsoft Store セクションの 「 [ローカライズ」の名前と説明のみを読み取](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) る必要があります。</span><span class="sxs-lookup"><span data-stu-id="1000a-141">If it is not localized, only read the [Localizing name and description in the Microsoft Store](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) section.</span></span>  

<span data-ttu-id="1000a-142">ファイルを `appxmanifest.xml` 並べ替えた後、次のコマンドを実行してパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1000a-142">Once your `appxmanifest.xml` file is sorted out, run the following command to create your package.</span></span>  

```shell
manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\
```  

<span data-ttu-id="1000a-143">これで、パッケージは edgeextension フォルダー内にあるパッケージ フォルダーに格納されます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1000a-143">Your package will now be in the **package** folder located within the edgeextension folder.</span></span> <span data-ttu-id="1000a-144">新しいパッケージをサイドロードする方法の詳細については、「拡張機能[](./creating-and-testing-extension-packages.md#testing-an-appx-package)パッケージの作成とテスト」の「テスト」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1000a-144">For more information about how to sideload your new package, see [testing](./creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing extension packages.</span></span>  

<span data-ttu-id="1000a-145">パッケージのテストが完了したら、Microsoft Store への公開を検討するために[](https://aka.ms/extension-request)、拡張機能提出フォームで要求を自由に送信してください。</span><span class="sxs-lookup"><span data-stu-id="1000a-145">Once your package has been tested, feel free to submit a request on our [extension submission form](https://aka.ms/extension-request) in order to be considered for publication to the Microsoft Store.</span></span>  
