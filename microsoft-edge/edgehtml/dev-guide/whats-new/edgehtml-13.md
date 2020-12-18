---
description: このページでは、EdgeHTML 13 の新機能の概要について説明します。
title: EdgeHTML 13 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2119e576a637d5f78e073f49a3cb1868a7ce1ca4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235008"
---
# EdgeHTML 13 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

ここでは、EdgeHTML 13 に同梱されている変更点を示します。このエンジンは、Windows [](https://blogs.windows.com/windowsexperience/2015/11/12) 10 用の最初のメジャー更新プログラム (11/2015、ビルド 10586\) で Microsoft Edge ブラウザーを起動します。  Microsoft Edge ブラウザー全体の変更点の概要については、「Microsoft Edge の最初のプラットフォーム更新プログラム [である EdgeHTML 13](https://blogs.windows.com/msedgedev/2015/11/16)の導入」を参照してください。  

次の変更の一覧の permalink を次に示します  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md) 。  

## 機能  

### CSS  

EdgeHTML 13 は、次の新しい CSS 機能をサポートしています。  

*   [CSS の変更可能性擬似クラス](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [CSS 範囲擬似クラス](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   CSS[の初期](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue)[キーワードと未設定](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue)キーワード  

### 暗号化されたメディア拡張機能  

Microsoft Edge では、新しい固定されていない [暗号化メディア拡張機能](https://w3.org/TR/encrypted-media) API がサポートされます。  Encrypted Media Extensions \(EME\) は、プラグインを使用せずにデジタル著作権管理 \(DRM\) で保護されたコンテンツを有効にするようにビデオ要素とオーディオ要素を拡張します。 EME:  [Encrypted Media Extensions について詳しくは、以下を参照してください](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)。  

### グラフィックス  

EdgeHTML 13 では、次のグラフィックス更新プログラムが導入されています。  

*   [キャンバスの楕円](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [キャンバス ブレンド モード](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> 要素](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [SVG 外部コンテンツ](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### JavaScript  

EdgeHTML 13 には、Microsoft Edge を強化する JavaScript エンジン [である Chakra](https://blogs.windows.com/msedgedev/2015/09/30)の主な機能強化と新機能のサポートが含まれています。これには次が含まれます。  

#### 新機能  

既定でオン  

*   [asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) 既定で有効になっている \([ブログ投稿](https://blogs.windows.com/msedgedev/2015/11/10), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)  
*   [Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)  

#### 試験的な JavaScript 機能  

有効 `about:flags`  

*   [非同期関数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)  
*   [指数演算子](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)  
*   [デストラクター](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)  

### ユーザー入力  

EdgeHTML 13 で導入された次の機能により、ユーザー入力が向上します。  

*   [\<meter\> 要素](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [要素ドキュメントとウィンドウの oninvalid イベント ハンドラー](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### ポインター ロック  

Microsoft Edge では、マウスの生の移動にアクセスするためのポインター ロック API \(以前のマウス ロック\ と呼ばれていました) がサポートされ、マウス イベントのターゲットを 1 つの要素にロックし、マウスの移動が 1 方向に移動する範囲の制限を排除し、カーソルをビューから削除します。  

## EdgeHTML 13 の新しい API  

EdgeHTML 13 の新しい API の完全な一覧を次に示します。  これらは次の形式で一覧表示されます `[interface name].[api name]` 。  

<iframe height='584' scrolling='no' title='EdgeHTML 13 の新しい API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'>CodePen の Microsoft Edge Docs ( @MicrosoftEdgeDocumentation ) による <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> EdgeHTML 13 </a> のペンの新しい API <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> をご覧ください </a> 。</iframe>  
