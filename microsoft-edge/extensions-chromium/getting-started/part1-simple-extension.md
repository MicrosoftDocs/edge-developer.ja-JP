---
description: その日の NASA の画像をポップアップする拡張機能を作成する
title: 拡張機能のチュートリアルを作成する - パート 1
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, Web 開発, html, css, javascript, developer, extensions
ms.openlocfilehash: dfbe7893ce576c223d2b1d39ec21b6c5f46d8356
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397511"
---
# <a name="create-an-extension-tutorial---part-1"></a>拡張機能のチュートリアルを作成する - パート 1  

## <a name="overview"></a>概要  

このチュートリアルの目的は、空のディレクトリから始まる Microsoft Edge (Chromium) 拡張機能を作成します。  その日の NASA の画像をポップアップする拡張機能を作成しています。 このチュートリアルでは、次のアクションを実行して拡張機能を作成する方法について説明します。  

*   ファイルの `manifest.json` 作成。  
*   アイコンの追加。  
*   既定のポップアップ ダイアログを開きます。  

## <a name="before-you-begin"></a>開始する前に

このチュートリアルで構築する完成した拡張機能をテストするには、ソース コードを [ダウンロードします][ArchiveExtensionGettingStartedPart1]。  

## <a name="step-1-create-a-manifestjson-file"></a>手順 1: ファイルにmanifest.js作成する

すべての拡張パッケージには、ルート `manifest.json` にファイルが必要です。  マニフェストには、拡張機能の詳細、拡張機能パッケージのバージョン、拡張機能の名前と説明が表示されます。  

次のコード スニペットは、ファイルに必要な基本情報の概要を示 `manifest.json` しています。  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to display the NASA picture of the day."
}
```  

## <a name="step-2-add-icons"></a>手順 2: アイコンを追加する  

まず、プロジェクトに `icons` ディレクトリを作成し、アイコン イメージ ファイルを保存します。  アイコンは、ユーザーが拡張機能を起動するために選択したボタンの背景画像に使用されます。  

:::image type="complex" source="./media/part1-badge1.png" alt-text="拡張機能を開くツールバーのアイコン":::
   拡張機能を開くツールバーのアイコン  
:::image-end:::  

アイコンの場合は、次の使用をお勧めします。 
*   `PNG` アイコンの形式を指定しますが、形式 `BMP` を `GIF` 使用 `ICO` `JPEG` できます。  
*   128 x 128 px の画像で、必要に応じてブラウザーによってサイズが変更されます。  

プロジェクトのディレクトリは、次の構造に似ている必要があります。   

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

次に、アイコンをファイルに追加 `manifest.json` します。 アイコン情報 `manifest.json` を使用してファイルを更新し、次のコード スニペットと一致します。 次 `png` のコードに記載されているファイルは、この記事で前述したダウンロード ファイルで使用できます。  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium extension to show the NASA picture of the day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    }
}
```  

## <a name="step-3-open-a-default-pop-up-dialog"></a>手順 3: 既定のポップアップ ダイアログを開く  

次に、ユーザーが `HTML` 拡張機能を起動するときに実行するファイルを作成します。  という名前のディレクトリに HTML `popup.html` ファイルを作成します `popup` 。  ユーザーが拡張機能を起動するアイコンを選択すると `popup/popup.html` 、モーダル ダイアログとして表示されます。  

星の画像を表示するには、次のコード スニペット `popup.html` のコードを追加します。  

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

イメージ ファイルを images フォルダー `images/stars.jpeg` に追加してください。  プロジェクトのディレクトリは、次の構造に似ている必要があります。   

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

最後に、次のコード スニペットに示すように、ポップアップを `manifest.json` `browser_action` [下] に登録してください。  

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

## <a name="next-steps"></a>次の手順
これは、作業拡張機能を開発するために必要なすべてです。  次に、引き続きサイドロードを行い、拡張機能をテストします。 詳細については、「拡張機能を [サイドロードする」に移動します][TestExtensionSideload]。  

<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part1/part1 "完成した拡張パッケージ ソース |Microsoft Docs"

[TestExtensionSideload]: ./extension-sideloading.md "拡張機能 (サイドローディング) のテスト|Microsoft Docs"
