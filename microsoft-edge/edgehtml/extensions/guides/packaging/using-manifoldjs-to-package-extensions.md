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
# Extension AppX パッケージの作成に、ManifoldJS を使用する  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

ManifoldJS はオープン ソース Node.js ツールで、Microsoft Store への申請に使えるパッケージをすばやく簡単に作成できます。  

拡張機能でネイティブ メッセージングを使用する場合は、次の記事をスキップし、パッケージ化の手順については [Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) のネイティブ メッセージングに移動する必要があります。  

開始する前に、次の記事を読む必要があります。  

*   [Windows デベロッパー センターの拡張機能](./extensions-in-the-windows-dev-center.md)  
*   [拡張機能パッケージのローカライズ](./localizing-extension-packages.md)  

> [!NOTE]
> Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。  拡張機能を作成、パッケージ化、テストしたら、拡張機能の提出フォームで要求 [を送信してください](https://developer.microsoft.com/microsoft-edge/extensions/requests)。  

## システムとNode.js JS のインストール  

最初に行う必要があるのは [ 、LTSNode.jsです](https://nodejs.org/en/download)。  
Node を取得したら、コマンド ライン (PowerShell が望ましい) から次のコマンドを実行して、ManifoldJS をインストールします。  

```shell
npm install -g manifoldjs
```  

CorrectlyJS が正しくインストールされていることを確認するには、コマンド `manifoldjs` ラインから実行します。 1 つも認識されない場合は `%APPDATA%\npm` 、PATH 変数に追加します。  

## ManifoldJS を使用したパッケージ化  

パッケージ化プロセスを開始するには、コマンド ラインを開き、パッケージ化された拡張機能の宛先になるフォルダーにディレクトリを変更する必要があります。  

次に、例を示します。

```shell
cd C:\manifoldJSTest
```  

> [!NOTE]
> コマンド `manifoldjs` は現在のディレクトリに出力し、コンテンツを上書きします。  

移動先フォルダーに移動した後、次のコマンドを実行します。  

```shell
manifoldjs -l debug -p edgeextension -f edgeextension -m path\to\manifest.json
```  

この `mainifoldjs` コマンドは、次の部分に分かれています。  

:::row:::
   :::column span="1":::
      `-l debug`  
   :::column-end:::
   :::column span="2":::
      ログ レベルを変更して `debug` 、完全な印刷を取得します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-p edgeextension`  
   :::column-end:::
   :::column span="2":::
      変換を実行する唯一のプラットフォームを設定します `edgeextension` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-f edgeextension`  
   :::column-end:::
   :::column span="2":::
      マニフェストの形式が形式であり、検証に失敗した場合 `edgeextension` は注意が必要で、プログラムに指示します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-m \path\to\manifest.json`  
   :::column-end:::
   :::column span="2":::
      変換する拡張機能マニフェストへのパス。  
   :::column-end:::
:::row-end:::  

読み込み完了したら、次の内容のフォルダーが作成されます。  

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

The generationInfo.json file is a log produced by running ManifoldJS and will not be included in your extension package. フォルダーの内容 `manifest` だけがパッケージ化されます。 マニフェスト フォルダー内の Assets フォルダーには、Windows と Microsoft Store の UI で使用されるイメージが含まれますが、Extension フォルダーには拡張機能の内容が含まれます。  

これで適切なファイルが作成されたので、生成された AppXManifest ファイルをフォルダー内で編集する必要 `manifest` があります。 拡張子の manifest.json ファイルに "name" フィールドの国際化文字列が含まれている場合、一度、UnderscoreJS を実行すると、最も上位のレイヤー フォルダーの名前にはアンダースコアが付けらなく、"MSG" が含まれます。

たとえば、次のフィールドmanifest.jsを含むファイルに対してファイルを作成 `"name"` できます。  

```shell
"name" : "__MSG_appName__"
```  

マニフェスト フォルダーが含まれます `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` 。  

AppXManifest ファイルでは、次の必要があります。  

 *   ここで説明する必要な Identity フィールドと PublisherDisplayName フィールドを置き換 [える](./creating-and-testing-extension-packages.md#app-identity-template-values)。 テスト目的またはエンタープライズ配布のみを目的としてパッケージ化する場合は、Windows デベロッパー センター アカウントに登録する代わりにプレースホルダー値を使用できます。  
 *   Assets フォルダー内のプレースホルダー アイコンを、同じサイズ (150x150、50x50、44x44) と名前を持つ拡張機能のアイコンに置き換えてください。 これらのアイコン [が使用](./../design.md#icons-for-packaging) される場所については、デザイン ガイドを参照してください。  
 *   拡張機能がローカライズされている場合は、Localizing Microsoft Edge 拡張機能ガイド [全体に従](./localizing-extension-packages.md) ってください。 ローカライズされていない場合は、Microsoft Store セクションの 「 [ローカライズ」の名前と説明のみを読み取](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) る必要があります。  

ファイルを `appxmanifest.xml` 並べ替えた後、次のコマンドを実行してパッケージを作成します。  

```shell
manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\
```  

これで、パッケージは edgeextension フォルダー内にあるパッケージ フォルダーに格納されます。 **** 新しいパッケージをサイドロードする方法の詳細については、「拡張機能[](./creating-and-testing-extension-packages.md#testing-an-appx-package)パッケージの作成とテスト」の「テスト」セクションを参照してください。  

パッケージのテストが完了したら、Microsoft Store への公開を検討するために[](https://aka.ms/extension-request)、拡張機能提出フォームで要求を自由に送信してください。  
