---
description: このページでは、EdgeHTML 13 の新機能の概要を示します。
title: EdgeHTML 13 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 033b8dacb107492624f3b8c7775a47285c9893dd
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941916"
---
# Microsoft EdgeHTML 13 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

EdgeHTML 13 に出荷される変更は、Microsoft Edge ブラウザーの初回のメジャー更新プログラム[first major update](https://blogs.windows.com/windowsexperience/2015/11/12)(2015/11/2015、ビルド 10586\) でリリースされる変更です。  Microsoft Edge ブラウザー全体の変更の概要については、Microsoft Edge の初回プラット [フォーム更新プログラムの概要をご覧ください](https://blogs.windows.com/msedgedev/2015/11/16)。  

次の一覧を行うと、この機能が利用できます  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md) 。  

## 機能  

### CSS  

EdgeHTML 13 では、次のような新しい CSS 機能がサポートされます。  

*   [CSS ミュート機能 Pseudo クラス](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [CSS 範囲のプッピド クラス](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   CSS [のイニシャル](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) と設定 [を](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) 解除する  

### 暗号化されたメディア拡張機能  

Microsoft Edge では、予期しない暗号化された暗号化メディア拡張 API が [サポートされるようになり](https://w3.org/TR/encrypted-media) ました。  Encrypted Media Extensions \(EME\) は、ビデオ要素およびオーディオ要素を拡張して、プラグインを使用せずに Digital Rights Management \(DRM\) 保護コンテンツを有効にします。 EME: 暗号  [化されたメディア拡張機能の詳細について説明します](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)。  

### グラフィックス  

Microsoft EdgeHTML 13 では、次のグラフィック更新プログラムが追加されました。  

*   [キャンバスの省略語](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [キャンバス ブレンド モード](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> 要素](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [SVG 外部コンテンツ](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### JavaScript  

Microsoft EdgeHTML 13 には、 [次のような Javakra](https://blogs.windows.com/msedgedev/2015/09/30)での主な機能の主な改善と新機能のサポートが含まれており、次のような Microsoft Edge を利用できます。  

#### 新機能  

既定でオン  

*   [asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) 既定で有効にされた \([ブログ投稿](https://blogs.windows.com/msedgedev/2015/11/10), [デモ](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)  
*   [Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)  

#### 実用 JavaScript 機能  

有効 `about:flags`  

*   [Async 関数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)  
*   [Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)  
*   [Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)  

### ユーザー入力  

EdgeHTML 13 で追加された次の機能では、ユーザー入力が改善されます。  

*   [<meter> 要素](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [要素のドキュメントとウィンドウのオンのイベント ハンドラー](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### ポインターのロック  

Microsoft Edge では、放射時のマウスの移動にアクセスできるようにポインター Lock API \(以前はマウス ロック\) がサポートされ、マウス イベントのターゲットを 1 つの要素にロックし、マウスの移動が 1 つの方向でどのように行き入れるかの制限をなくしたり、ビューからカーソルを削除したりできるようになりました。  

## EdgeHTML 13 の新しい API  

EdgeHTML 13 の新しい API の完全な一覧を次に示します。  これらは形式で表示されます `[interface name].[api name]` 。  

<iframe height='584' scrolling='no' title='EdgeHTML 13 の新しい API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> </a> CodePen の Microsoft Edge Docs (新しい <a href='http://codepen.io/MicrosoftEdgeDocumentation'> API) @MicrosoftEdgeDocumentation </a> 参照 <a href='http://codepen.io'> してください </a> 。</iframe>  
