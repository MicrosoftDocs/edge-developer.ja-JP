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
# ManifoldJS を使用して拡張 AppX パッケージを作成する  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

ManifoldJS はオープンソース Node.js ツールであり、Microsoft ストアへの申請に使用できるパッケージをすばやくおり作成できます。  

拡張機能でネイティブメッセージングを使用している場合は、次の記事をスキップして、「 [Microsoft Edge でのネイティブメッセージング](../native-messaging.md#creating-an-extension-with-native-messaging) によるパッケージ化の手順」を参照してください。  

作業を始める前に、次の記事を参照する必要があります。  

*   [Windows デベロッパー センターの拡張機能](./extensions-in-the-windows-dev-center.md)  
*   [拡張機能パッケージのローカライズ](./localizing-extension-packages.md)  

> [!NOTE]
> Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。  お客様の内線番号の作成、パッケージ化、テストが完了したら、 [延長申請フォーム](https://developer.microsoft.com/microsoft-edge/extensions/requests)でリクエストを送信してください。  

## Node.js と ManifoldJS のインストール  

最初に [Node.js LTS](https://nodejs.org/en/download)をインストールする必要があります。  
ノードを取得したら、コマンドライン (PowerShell を推奨) から次のコマンドを実行して、ManifoldJS をインストールします。  

```shell
npm install -g manifoldjs
```  

ManifoldJS が正常にインストールされていることを確認するには、 `manifoldjs` コマンドラインから実行します。 ManifoldJS が認識されない場合は、 `%APPDATA%\npm` PATH 変数にを追加します。  

## ManifoldJS でパッケージ化する  

パッケージ処理を開始するには、コマンドラインを開き、パッケージ化された拡張のコピー先になるフォルダーにディレクトリを変更する必要があります。  

次に、例を示します。

```shell
cd C:\manifoldJSTest
```  

> [!NOTE]
> コマンドは、 `manifoldjs` 現在のディレクトリに出力され、コンテンツが上書きされます。  

目的のフォルダーに移動したら、次のコマンドを実行します。  

```shell
manifoldjs -l debug -p edgeextension -f edgeextension -m path\to\manifest.json
```  

`mainifoldjs`コマンドは次の部分に分けることができます。  

:::row:::
   :::column span="1":::
      `-l debug`  
   :::column-end:::
   :::column span="2":::
      ログレベルを変更して完全に印刷されるようにし `debug` ます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-p edgeextension`  
   :::column-end:::
   :::column span="2":::
      への変換を実行する唯一のプラットフォームを設定 `edgeextension` します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-f edgeextension`  
   :::column-end:::
   :::column span="2":::
      マニフェストの形式が形式であり、 `edgeextension` 検証に失敗した場合は注意しないようにプログラムに指示します。  
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

ManifoldJS の実行が完了すると、次の内容のフォルダーが作成されます。  

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

ファイルの generationInfo.jsは、ManifoldJS を実行することによって生成されたログであり、拡張機能パッケージには含まれません。 フォルダーの内容のみ `manifest` がパッケージ化されます。 [マニフェスト] フォルダーでは、[アセット] フォルダーには、Windows と Microsoft Store の UI で使用する画像が含まれています。また、拡張機能のフォルダーには、拡張機能の内容が含まれています。  

適切なファイルを作成したので、フォルダー内で生成された Package.appxmanifest ファイルを編集する必要があり `manifest` ます。 ファイルの拡張子の manifest.jsに "name" フィールドの国際化文字列が含まれている場合、ManifoldJS が実行されると、最上位のレイヤーのフォルダー名にアンダースコアは表示されず、"MSG" が含まれます。

たとえば、次のフィールドを含むファイルに manifest.jsし `"name"` ます。  

```shell
"name" : "__MSG_appName__"
```  

存在するマニフェストフォルダーがあり `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` ます。  

Package.appxmanifest ファイルでは、次のことを行う必要があります。  

 *   [ここで](./creating-and-testing-extension-packages.md#app-identity-template-values)説明するように、必須の id フィールドと PublisherDisplayName フィールドを置き換えます。 テスト目的またはエンタープライズ配布用にのみパッケージ化する場合は、Windows デベロッパーセンターアカウントに登録するのではなく、プレースホルダー値を使用できます。  
 *   [アセット] フォルダーのプレースホルダーアイコンを、同じサイズ (150x150、50x50、44x44)、名前の拡張機能のアイコンに置き換えます。 これらのアイコンが使用されている場所については、 [設計](./../design.md#icons-for-packaging) ガイドを参照してください。  
 *   拡張機能がローカライズされている場合は、「 [Microsoft Edge のローカライズ](./localizing-extension-packages.md) ガイド」の全機能について説明します。 ローカライズされていない場合は、「Microsoft Store」セクションの [ローカライズの名前と説明](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) のみを参照してください。  

`appxmanifest.xml`ファイルが並べ替えられたら、次のコマンドを実行してパッケージを作成します。  

```shell
manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\
```  

これで、パッケージが edgeextension フォルダー内の **パッケージ** フォルダーに保存されます。 新しいパッケージをサイドローディングする方法について詳しくは、「拡張パッケージの作成とテスト」の「 [テスト](./creating-and-testing-extension-packages.md#testing-an-appx-package) 」をご覧ください。  

パッケージのテストが完了したら、Microsoft ストアへの公開を検討するために、 [内線番号の申請フォーム](https://aka.ms/extension-request) で要求を送信してください。  
