---
description: このページでは、EdgeHTML 14 の新機能の概要を示します。
title: EdgeHTML 14 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 7f3fcbbf84873fbf0851e1652bde48632e6c4378
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941907"
---
# Microsoft EdgeHTML 14 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

[Windows 10 Anniversary Update](https://blogs.windows.com/windowsexperience/2016/06/29) \(08/2016, ビルド 14393\) に加入される変更は次のとおりです。  Microsoft Edge ブラウザー全体の変更の概要については [、Windows 10 Anniversary Update を使用した EdgeHTML 14 の概要を参照してください](https://blogs.windows.com/msedgedev/2016/08/04)。  

次の一覧を行うと、この機能が利用できます [https://aka.ms/devguide_edgehtml_14](./edgehtml-14.md) 。  

## 新機能  

### 拡張機能  

拡張機能は、Microsoft Edge に新機能を追加したり、既存の機能を変更したりするために使用できる小さなプログラムです。  拡張機能は、対象ユーザーにとって重要な機能を提供することで、ユーザーが日常的な閲覧体験を改善するのを対象としています。  Microsoft Edge は、新しい HTML、JavaScript、CSS ベースの拡張モデルをサポートしています。  この新しいモデルは Chrome と互換性があるため、既存の Chrome 拡張機能開発者は、変更を最小に変更して Microsoft Edge に移行できます。  詳細については [、Microsoft Edge 拡張機能の開](../../extensions/index.md) 発者向けドキュメントを参照してください。  

### Fetch API  
[Fetch API は](https://fetch.spec.whatwg.org#fetch-api)リソースをフェッチする `fetch` 方法を利用します。  この問題は、これが実績でした `XMLHttpRequest` 。  使用するのが簡単なだけでなく、要求や返信の低いレベルのアクセスを提供することもできます。  Microsoft Edge ブログの投稿、フェッチ (または XHR の不可定 [な制限) の Fetch](https://blogs.windows.com/msedgedev/2016/05/24)API の詳細をご覧ください。  

### JavaScript  

Microsoft Edge を利用する JavaScript エンジン、JavaScript エンジン、Microsoft Edge の機能を利用できるようになりました。  

#### 新機能  

既定でオン  

*   [既定のパラメーター](https://developer.microsoft.com/microsoft-edge/platform/status/defaultparameteres6) \(ES2015\)
*   [Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016) \(ES2016\)
*   [Array.prototype.includes](https://developer.microsoft.com/microsoft-edge/platform/status/arrayprototypeincludeses2016) \(ES2016\)
*   [Object.values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/values) and [object.entries](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) \(ES2017\)  

#### 実用 JavaScript 機能  

有効 `about:flags`  

*   [モジュール](https://blogs.windows.com/msedgedev/2016/05/17) \(ES2015\)  
*   [Async/await](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctionses2016) \(ES2017\)  
*   [Regex シンボル](https://developer.microsoft.com/microsoft-edge/platform/status/regexpbuiltinses6) \(ES2015\)  

詳細については、Es6 モジュールの [プレビュー版を確認し、ES2015、ES2016](https://blogs.windows.com/msedgedev/2016/05/17) 以降、 [非同期コードを使用すると、Chakra と Microsoft Edge での Es2016 Async 関数のサポートを使用すると、Es2016 Async モ](https://blogs.windows.com/msedgedev/2015/09/30)ジュールや非同期コードを簡単にご確認いたします。  

### Web 認証 API  

FIDO 2.0 Web API  

Microsoft Edge の Web Authentication \(元人 FIDO 2.0\) API では、Web アプリケーションでユーザー認証に [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics を使用できるため、パスワードの成功、フィッシング、キー操作など、パスワード管理のすべてのパスワード管理にパスワード管理の要件とリスクが含まれます。  現在の Microsoft Edge \( プレフィックス付き\) 実装は、Web 認証定義の以前の下書きに基づいており、後で変更される `ms-` 場合がありました。  Web 認証の詳細については  [、Web 認証と Windows Hello を参照してください](../windows-integration/web-authentication.md)。

### Web 通知
Web 通知を使うと、新しいメッセージまたは通知をユーザーに通知し、サイトがユーザーの関性を向上させるための通知をサイトに表示できます。  Microsoft Edge の Web Notification は、Windows 10 の通知プラットフォームとアクション センターに完全に統合され、システム全体で他のアプリと一定のエクスペリエンスを提供し、権限や非通知モードを簡単に制御できます。  詳細については [、Microsoft Edge で Web Notification を](https://blogs.windows.com/msedgedev/2016/05/16) 確認してください。  

### Web 音声 API
[Web 音声認定 API は](https://dvcs.w3.org/hg/speech-api/raw-file/tip/speechapi.html)JavaScript API で構成される JavaScript API であり、音声認定と音声認知 (またはテキストから音声へのテキスト)。  現在、Microsoft Edge は音声合わせのみをサポートしています。  音声合ナさえには、ユーザーがスピーカーを通して聞こえる音声変換が含められます。  詳細については [、Web 音声: 音声合字の](https://developer.mozilla.org/docs/Web/API/Web_Speech_API) 開発者ガイドの記事を参照してください。  

## EdgeHTML 14 の新しい API

EdgeHTML 14 の新しい API の完全な一覧を次に示します。  これらは形式で表示されます `[interface name].[api name]` 。  

<iframe height='585' scrolling='no' title='EdgeHTML 14 の新しい API' src='//codepen.io/MSEdgeDev/embed/oWMEPE/?height=585&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MSEdgeDev/pen/oWMEPE/'>CodePen の Microsoft EdgeHTML 14 の Pen New API </a> <a href='https://codepen.io/MSEdgeDev'> @MSEdgeDev </a> <a href='https://codepen.io'> を参照してください </a> 。</iframe>  
