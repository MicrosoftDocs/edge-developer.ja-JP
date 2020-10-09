---
description: その日の NASA の画像をポップアップする拡張機能を作成する
title: 拡張チュートリアルを作成する-パート1
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: 3809bfac714621cf97184127132487ed93958a2f
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104708"
---
# 拡張チュートリアルを作成する-パート1  

## 概要  

このチュートリアルの目標は、空のディレクトリから開始する Microsoft Edge (Chromium) の拡張機能を構築することです。 この日の NASA の画像をポップアップする拡張機能を作成します。 このチュートリアルでは、次の方法で拡張機能を作成する方法について説明します。

*   ファイルを作成する `manifest.json` 。  
*   アイコンを追加します。  
*   既定のポップアップダイアログを開く。  

## 始める前に

このチュートリアルで構築する完成した拡張機能をテストするには、 [ソースコード][ArchiveExtensionGettingStartedPart1]をダウンロードしてください。  

## 手順 1: ファイルを作成する `manifest.json`

すべての拡張パッケージには `manifest.json` 、ルートにファイルが必要です。  マニフェストには、拡張機能の詳細、拡張機能パッケージのバージョン、拡張機能の名前と説明などが用意されています。  

次のコードスニペットでは、ファイルに必要な基本的な情報を示して `manifest.json` います。  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to display the NASA picture of the day."
}
```  

## 手順 2: アイコンを追加する  

まず `icons` 、アイコンイメージファイルを格納するディレクトリをプロジェクトに作成します。  アイコンは、ユーザーが拡張機能を起動するために選択したボタンの背景画像に使用されます。  

:::image type="complex" source="./media/part1-badge1.png" alt-text="拡張機能を開くためのツールバーのアイコン&quot;:::
   拡張機能を開くためのツールバーのアイコン
:::image-end:::

アイコンの場合は、次のことをお勧めします。 
*   `PNG` アイコンの書式を設定しますが、、、 `BMP` `GIF` `ICO` または形式を使用することもでき `JPEG` ます。  
*   128 x 128 ピクセルの画像。必要に応じてブラウザーでサイズが変更されます。  

プロジェクトのディレクトリは、次のような構造になっている必要があります。   

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

次に、ファイルにアイコンを追加 `manifest.json` します。 `manifest.json`次のコードスニペットと一致するように、アイコンの情報でファイルを更新します。 `png`次のコードに記載されているファイルは、この記事の前半で説明したダウンロードファイルで入手できます。  

```json
{
    &quot;name&quot;: &quot;NASA picture of the day viewer&quot;,
    &quot;version&quot;: &quot;0.0.0.1&quot;,
    &quot;manifest_version&quot;: 2,
    &quot;description&quot;: &quot;A chromium extension to show the NASA picture of the day.&quot;,
    &quot;icons&quot;: {
        &quot;16&quot;: &quot;icons/nasapod16x16.png&quot;,
        &quot;32&quot;: &quot;icons/nasapod32x32.png&quot;,
        &quot;48&quot;: &quot;icons/nasapod48x48.png&quot;,
        &quot;128&quot;: &quot;icons/nasapod128x128.png"
    }
}
```  

## 手順 3: 既定のポップアップダイアログを開く  

次に、 `HTML` ユーザーが拡張機能を起動したときに実行されるファイルを作成します。  `popup.html`という名前のディレクトリにある HTML ファイルを作成 `popup` します。  ユーザーが拡張機能を起動するためにアイコンを選択すると、 `popup/popup.html` モーダルダイアログとして表示されます。  

次のコードスニペットから、星の画像を表示するコードを追加し `popup.html` ます。  

```html
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>NASA picture of the day</title>
    </head>
    <body>
        <div>
            <img src="/images/stars.jpeg" alt="Display the stars image" />
        </div>
    </body>
</html>
```  

画像ファイルを `images/stars.jpeg` images フォルダーに追加します。  プロジェクトのディレクトリは、次のような構造になっている必要があります。   

```shell
└── part1
    ├── _manifest.json
    ├── icons
    │   ├── nasapod16x16.png
    │   ├── nasapod32x32.png
    │   ├── nasapod48x48.png
    │   └── nasapod128x128.png
    ├── images
    │   └── stars.jpeg
    └── popup
        └── popup.html
```  

最後に、 `manifest.json` `browser_action` 次のコードスニペットに示すように、でポップアップを登録していることを確認します。  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium extension to display the NASA picture of the day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    },
    "browser_action": {
        "default_popup": "popup/popup.html"
    }
}
```  

## 次のステップ
これは、作業拡張機能を開発するために必要なものです。 次に、サイドローディングに進み、拡張機能をテストします。 詳細については、「 [サイドローディングの拡張機能][TestExtensionSideload]」を参照してください。  


<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part1/part1 "完成した拡張パッケージソース |Microsoft ドキュメント"

[TestExtensionSideload]: ./extension-sideloading.md "拡張機能をテストする (サイドローディング) |Microsoft ドキュメント"
