---
description: 拡張機能の概要パート1
title: その日の NASA の絵を飛び出すシンプルな拡張機能を構築する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: 826401869b98d339e9b156a3727d94bd1182063d
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015766"
---
# その日の NASA の絵を飛び出すシンプルな拡張機能を構築する 
 
<!--  
[Completed Extension Package Source for This Part][ArchiveExtensionGettingStartedPart1]  
-->  

## 概要  

パート1では、空のディレクトリから開始する非常にシンプルな Edge Chromium 拡張機能を作成することを目標としています。  この拡張機能の目標は、次のタスクを実行することです。  

*   複数の場所で使用される可能性がある、さまざまなサイズの拡張のアイコンを作成する  
*   簡単なファイルを作成する `manifest.json`  
*   選択されたときに、その日の NASA の画像が含まれたポップアップウィンドウを表示する起動アイコンを表示する  

## マニフェストファイルの基本  

すべての拡張パッケージには `manifest.json` 、ルートにファイルが必要です。  これは、拡張機能の青写真と考える必要があります。  この機能は、ブラウザーエンジンに、Extension が想定している拡張 API のバージョン、拡張機能の名前と説明、その他多くの詳細情報を示します。これについては、このマルチパート拡張機能の概要について説明します。  

以下は簡単  `manifest.json`  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium Extension to show the NASA Picture of the Day."
}
```  

## 拡張機能のアイコンのセットアップ  

次に、ファイルにいくつかのアイコンを追加 `manifest.json` し `/icons` ます (アイコンファイルを使って新しいディレクトリを作成します)。  アイコンは、拡張機能 \ (存在する場合) を起動するためにユーザーが選択したボタンの背景画像や、適切なその他の場所に使用されます。  

`PNG` は推奨される形式ですが、、、、を使用することもでき `BMP` `GIF` `ICO` `JPEG` ます。  常に少なくとも 128 x 128 ピクセルのサイズアイコンを設定することをお勧めします。ブラウザーは必要に応じて、自動的にサイズを変更することをお勧めします。  

ディレクトリ構造は、次の図のようになります。  

<!--  
:::image type="complex" source="./media/part1-heirarchy.png" alt-text="Directory Structure":::
   Directory Structure
:::image-end:::
-->  

<!--![Directory Structure][ImagePart1Heirarchy]  -->  

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

更新された `manifest.json` ファイルは、次のように表示されます。  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium extension to show the NASA Picture of the Day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    }
}
```  

> [!NOTE]
> `png`このページの一番上に記載されている zip ダウンロードで、前のコードに記載されているアイコンファイルを利用できます。  

## 既定のポップアップダイアログを追加する  

次に、 `HTML` ユーザーが拡張機能アイコンを選択したときに自動的に実行されるファイルを作成します。  

:::image type="complex" source="./media/part1-badge1.png" alt-text="ツールバーバッジのアイコン":::
   ツールバーバッジのアイコン
:::image-end:::

<!--![Toolbar Badge Icon][ImagePart1Badge1]  -->  

HTML ファイルには、という名前が付いてい `popup/popup.html` ます。  [拡張機能] アイコンを選択 `popup/popup.html` すると、ダイアログの外側にある [モーダル] ダイアログが開きます。  

そのためには、次のコードの下のにある [既定のポップアップとしてファイルを登録します] を選び `manifest.json` `browser_action` ます。  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium Extension to show the NASA Picture of the Day.",
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

ディレクトリで、 `popup` ファイルを追加して、 `popup.html` 星の画像を表示します。  ファイルを次に示し `popup.html` ます。  

```html
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>NASA Picture of the Day</title>
    </head>
    <body>
        <div>
            <img src="/images/stars.jpeg" alt="stars" />
        </div>
    </body>
</html>
```  

 また、 `images/stars.jpeg` ファイルで参照されている画像ファイルを追加し `popup.html` ます。  

次の図は、この例の拡張機能のディレクトリ構造を示しています。  

<!--  
:::image type="complex" source="./media/part1-heirarchy1.png" alt-text="Directory Structure for Extension":::
   Directory Structure for Extension
:::image-end:::
-->  

<!--![Directory Structure for Extension][ImagePart1Heirarchy1]  -->  

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

<!--  
> [!NOTE]
> The `images/stars.jpeg` file listed in the previous image is available in the [zip download][ArchiveExtensionGettingStartedPart1].  
-->  

これは、機能拡張を構築するために必要なものです。  これだけで、テストを行うことができます。  

次のセクションでは、Microsoft Edge \ (Chromium) ブラウザーに拡張機能 \ (サイドローディング \ とも呼ばれます) をロードして、それをテストする方法について説明します。  

## ブラウザーで拡張機能をローカルで実行する (サイドロード \)  

Microsoft Edge \ (Chromium) ブラウザーには、開発中に拡張機能をデバッグできる安全で簡単な方法が用意されています。  

このプロセスは非常に簡単です。  まず、ブラウザーの上部にある3つの点を選択する必要があります。  次に、 `Extensions` 次の図に示すように、コンテキストメニューから選びます。  

:::image type="complex" source="./media/part1-threedots.png" alt-text="拡張機能の選択":::
   拡張機能の選択
:::image-end:::

<!--![Choose Extensions][ImagePart1Threedots]  -->  

次の図に示すように、[ **拡張機能** ] ページを表示している場合は、次の図に示すように、ページの左下のトグルを有効にして、 **開発者モード** を有効にします。  

:::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="開発者モードを有効にする":::
   開発者モードを有効にする
:::image-end:::

<!--![Enable Developer Mode][ImagePart1DevelopermodeToggle]  -->  

## サイドロードされた拡張機能のインストールと更新  

初めて拡張機能をインストールする場合は、次の画像のようなオプションを選択し `Load Unpacked` ます。  これにより、ファイルによって拡張アセットファイルが保存されているディレクトリを入力するように求められます。  これにより、ストアからダウンロードした場合と同じように拡張機能がインストールされます。  

:::image type="complex" source="./media/part1-installed-extension.png" alt-text="インストールされている拡張機能":::
   インストールされている拡張機能
:::image-end:::

<!--![Installed Extensions][ImagePart1InstalledExtension]  -->  

拡張機能をインストールしたら、拡張機能の一覧の下にあるボタンを選択して更新することができ `Reload` ます。  

ブラウザーから拡張機能を削除するには、 `Remove` 拡張機能一覧の下部にあるボタンをクリックします。  

## デバッグ用の拡張機能  

拡張機能のデバッグは非常に簡単で、Edge Chromium DevTools のすべての機能をサポートしています。  ただし、これらの詳細は、この「はじめに」のガイドでは説明していませんが、拡張機能を正常に構築するには非常に重要です。  

<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: ./extension-source/extension-getting-started-part1.zip "このパーツの完成した拡張パッケージソース |Microsoft ドキュメント"  
