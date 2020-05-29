---
description: このページでは、EdgeHTML 13 の新機能の概要を説明します。
title: EdgeHTML 13 の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 8fb9d6bd78af5d595e217fa2bf210632f4c1a61f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568816"
---
# EdgeHTML 13 の新機能
この変更は、EdgeHTML 13 に同梱されています。エンジンは、Windows 10 の[最初のメジャー更新プログラム](https://blogs.windows.com/windowsexperience/2015/11/12/first-major-update-for-windows-10-available-today/)(11/2015、ビルド 10586) で Microsoft Edge ブラウザーを電源投入します。 Microsoft Edge ブラウザー全体の変更の概要については、「 [Microsoft edge の最初のプラットフォーム更新プログラム EdgeHTML 13」を](https://blogs.windows.com/msedgedev/2015/11/16/introducing-edgehtml-13-our-first-platform-update-for-microsoft-edge/)参照してください。

次の変更の固定リンクを示し [https://aka.ms/devguide_edgehtml_13](https://aka.ms/devguide_edgehtml_13) ます。

## 機能

### CSS
' ' EdgeHTML 13 では、次のような新しい CSS 機能がサポートされています。
* [CSS の可能性のある擬似クラス](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses/)
* [CSS 範囲擬似クラス](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses/)
* CSS の[イニシャル](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue/)と[未](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue/)設定のキーワード

### 暗号化されたメディアの拡張子
Microsoft Edge で、新しいプレフィックスのない[暗号化メディア拡張](https://w3.org/TR/encrypted-media/)api がサポートされるようになりました。 暗号化されたメディア拡張機能 (EME) は、プラグインを使わずに、デジタル著作権管理 (DRM) で保護されたコンテンツを有効にするために、ビデオ要素とオーディオ要素を拡張します。 EME: [Encrypted Media Extensions](https://docs.microsoft.com/microsoft-edge/dev-guide/multimedia/encrypted-media-extensions)の詳細

### グラフィックス

EdgeHTML 13 では、次のグラフィックスの更新が導入されています。
* [キャンバス楕円](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse/)
* [キャンバスブレンドモード](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d/)
* [`<picture>` 要素](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement/)
* [SVG 外部コンテンツ](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent/)

### JavaScript
EdgeHTML 13 には、次のような Microsoft Edge を搭載した、JavaScript エンジンの[Chakra での主な改善と新機能のサポート](https://blogs.windows.com/msedgedev/2015/09/30/asynchronous-code-gets-easier-with-es2016-async-function-support-in-chakra-and-microsoft-edge/)が含まれています。

#### 新機能 (既定でオン)

* 既定で有効になっている[.asm .js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) ([ブログの投稿](https://blogs.windows.com/msedgedev/2015/11/10/supercharging-javascript-performance-with-asm-js/)、[デモ](https://dev.windows.com/microsoft-edge/testdrive/demos/chess/))
* [クラス](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes)(ES2015)

#### 実験的な JavaScript 機能 ( *about: flags*で有効)

* [Async 関数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions)(ES2016)
* [指数演算子](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator)(ES2016)
* [Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) (ES2015)

### ユーザー入力
EdgeHTML 13 で導入された次の機能により、ユーザー入力が向上します。
* [`<meter>` 要素](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement/)
* [`oninvalid` 要素のドキュメントとウィンドウのイベントハンドラー](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler/)

### ポインターのロック
Microsoft Edge では、ポインターロック API (以前のマウスロック) がサポートされるようになりました。マウスの動作のターゲットを単一の要素にロックし、マウスの動きを1方向に移動し、カーソルをビューから削除します。 


## EdgeHTML 13 "" "の新しい Api

EdgeHTML 13 の新しい Api の全一覧を次に示します。 [Interface name] の形式で一覧表示され**ます。 [api 名]**。
<iframe height='584' scrolling='no' title='EdgeHTML 13 の新しい Api' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> </a> CodePen の Microsoft Edge ドキュメント (@MicrosoftEdgeDocumentation) で EdgeHTML 13 の Pen 新しい api を参照してください <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> </a> 。</iframe>""''""''""
