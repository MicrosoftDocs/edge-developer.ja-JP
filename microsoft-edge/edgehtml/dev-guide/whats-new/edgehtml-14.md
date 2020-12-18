---
description: このページでは、EdgeHTML 14 の新機能の概要について説明します。
title: EdgeHTML 14 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c99dcb4efb253959d55d96a13ca2249eb5164b68
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234697"
---
# EdgeHTML 14 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

[Windows 10 Anniversary Update \(08/2016,](https://blogs.windows.com/windowsexperience/2016/06/29) Build 14393\) の現在、EdgeHTML 14 に同梱されている変更点を次に示します。  Microsoft Edge ブラウザー全体の変更点の概要については [、「Windows 10 Anniversary Update での EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04)の導入」を参照してください。  

次の変更の一覧の permalink を次に示します [https://aka.ms/devguide_edgehtml_14](./edgehtml-14.md) 。  

## 新機能  

### 拡張機能  

拡張機能は、Microsoft Edge に新機能を追加したり、既存の機能を変更したりするために使用できる小規模なプログラムです。  拡張機能は、対象ユーザーにとって重要な最適な機能を提供することで、ユーザーの毎日の閲覧エクスペリエンスを向上することを目的とします。  Microsoft Edge は、新しい HTML、JavaScript、および CSS ベースの拡張機能モデルをサポートしています。  この新しいモデルは Chrome 互換です。つまり、既存の Chrome 拡張機能の開発者は、最小限の変更で拡張機能を Microsoft Edge に移行できます。  詳細については [、Microsoft Edge 拡張機能の開発者向けドキュメントを](../../extensions/index.md) 参照してください。  

### API のフェッチ  
[Fetch API は](https://fetch.spec.whatwg.org#fetch-api)、リソースを `fetch` フェッチするメソッドを利用します。  過去に、これは次の方法で実現されました `XMLHttpRequest` 。  フェッチの方が簡単に使用できるだけでなく、要求と応答への低いレベルのアクセスも提供されます。  Fetch API の詳細については、Microsoft Edge ブログの投稿 [「Fetch (or the undeniable limitations of XHR)」を参照してください](https://blogs.windows.com/msedgedev/2016/05/24)。  

### JavaScript  

EdgeHTML 14 は、Microsoft Edge を機能する JavaScript エンジンである Chakra に、多くの新機能と試験的な機能を提供します。  

#### 新機能  

既定でオン  

*   [既定のパラメーター](https://developer.microsoft.com/microsoft-edge/platform/status/defaultparameteres6) \(ES2015\)
*   [指数演算子](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016) \(ES2016\)
*   [Array.prototype.includes](https://developer.microsoft.com/microsoft-edge/platform/status/arrayprototypeincludeses2016) \(ES2016\)
*   [Object.values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/values) and [object.entries](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) \(ES2017\)  

#### 試験的な JavaScript 機能  

有効 `about:flags`  

*   [Modules](https://blogs.windows.com/msedgedev/2016/05/17) \(ES2015\)  
*   [Async/await](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctionses2016) \(ES2017\)  
*   [Regex 記号](https://developer.microsoft.com/microsoft-edge/platform/status/regexpbuiltinses6) \(ES2015\)  

詳細については [、「ES2015、ES2016](https://blogs.windows.com/msedgedev/2016/05/17) 以降、非同期コードからの ES6 モジュールのプレビュー」を参照してください。Chakra と Microsoft Edge での [ES2016 Async 関数](https://blogs.windows.com/msedgedev/2015/09/30)のサポートにより、非同期コードがより簡単になります。  

### Web 認証 API  

FIDO 2.0 Web API  

Microsoft Edge の Web 認証 \(以前の FIDO 2.0\) API を使用すると、Web アプリケーションはユーザー認証に [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) 生体認証を使用できます。これにより、ユーザーはパスワードの推測、フィッシング、キーlogging攻撃など、パスワード管理のすべての面倒なリスクを回避できます。  現在の Microsoft Edge \( prefixed\) 実装は、Web 認証仕様の以前のドラフトに基づいており、今後変更 `ms-` される可能性があります。  Web 認証の詳細については  [、「Web 認証」と「Windows Hello」を参照してください](../windows-integration/web-authentication.md)。

### Web 通知
Web 通知を使用すると、Web ページとブラウザーのコンテキスト外のユーザーに通知を表示して、新しいメッセージや通知をユーザーに通知し、サイトでユーザーエンゲージメントを向上できます。  Microsoft Edge の Web 通知は、Windows 10 の通知プラットフォームおよびアクション センターと完全に統合され、システム全体で他のアプリと一貫したエクスペリエンスを提供し、アクセス許可と Quiet Hours を簡単に制御できます。  詳細については [、Microsoft Edge の Web 通知](https://blogs.windows.com/msedgedev/2016/05/16) を参照してください。  

### Web 音声認識 API
[Web Speech API は](https://dvcs.w3.org/hg/speech-api/raw-file/tip/speechapi.html)、音声認識と音声合成 \(またはテキストから音声\) の 2 つの部分で構成される JavaScript API です。  現時点では、Microsoft Edge は音声合成のみをサポートしています。  音声合成では、ユーザーが自分のスピーカーから聞く音声にテキストを変換します。  詳細については [、「Web Speech: Speech Synthesis](https://developer.mozilla.org/docs/Web/API/Web_Speech_API) Developer Guide」の記事を参照してください。  

## EdgeHTML 14 の新しい API

EdgeHTML 14 の新しい API の完全な一覧を次に示します。  これらは次の形式で一覧表示されます `[interface name].[api name]` 。  

<iframe height='585' scrolling='no' title='EdgeHTML 14 の新しい API' src='//codepen.io/MSEdgeDev/embed/oWMEPE/?height=585&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>CodePen の <a href='https://codepen.io/MSEdgeDev/pen/oWMEPE/'> EdgeHTML 14 の Pen New API </a> (MSEdgeDev ( <a href='https://codepen.io/MSEdgeDev'> @MSEdgeDev ) </a> を <a href='https://codepen.io'> 参照してください </a> 。</iframe>  
