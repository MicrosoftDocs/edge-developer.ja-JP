---
description: このページでは、EdgeHTML 14 の新機能の概要を説明します。
title: EdgeHTML 14 の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 5e9e0d5d9a53c5ecbfeb4b93c3b453a3d2904e2b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568855"
---
# EdgeHTML 14 の新機能
[Windows 10 記念日更新プログラム](https://blogs.windows.com/windowsexperience/2016/06/29/windows-10-anniversary-update-available-august-2/)(08/2016、ビルド 14393) の EdgeHTML 14 に同梱されている変更を次に示します。 Microsoft Edge ブラウザー全体の変更の概要については、「 [Windows 10 記念日更新プログラムを使用した EdgeHTML 14 の紹介](https://blogs.windows.com/msedgedev/2016/08/04/introducing-edgehtml-14)」を参照してください。

次の変更の固定リンクを示し [https://aka.ms/devguide_edgehtml_14](https://aka.ms/devguide_edgehtml_14) ます。

## 新機能

### 拡張機能
拡張機能は、Microsoft Edge に新しい機能を追加したり、既存の機能を変更したりするために使用できる小さなプログラムです。 拡張子は、対象ユーザーにとって重要なニッチ機能を提供することによって、ユーザーの日常的なブラウジングエクスペリエンスを向上させることを目的としています。 Microsoft Edge では、新しい HTML、JavaScript、CSS ベースの拡張モデルがサポートされています。 この新しいモデルは Chrome に対応しています。これは、既存の Chrome 拡張開発者が、最小限の変更で Microsoft Edge に拡張機能を移行できることを意味します。 詳細については、 [Microsoft Edge extensions](https://docs.microsoft.com/microsoft-edge/extensions) developer に関するドキュメントをご覧ください。 

### 取得 API
[FETCH API](https://fetch.spec.whatwg.org/#fetch-api)は、 `fetch` リソースを取得するためのメソッドを利用します。 これまでに行っていたのは、によって実現されました `XMLHttpRequest` 。 簡単に使うことができるだけでなく、要求と応答への下位レベルのアクセスも提供されます。 詳細については、Microsoft Edge ブログの投稿、[取得 (または XHR の undeniable の制限)](https://blogs.windows.com/msedgedev/2016/05/24/fetch-and-xhr-limitations/)の fetch API に関する詳細を参照してください。

### JavaScript

EdgeHTML 14 では、Microsoft Edge を搭載した JavaScript エンジンである Chakra に、いくつかの新機能と実験的な機能が搭載されています。

#### 新機能 (既定でオン)

* [既定のパラメーター](https://developer.microsoft.com/microsoft-edge/platform/status/defaultparameteres6) (ES2015)
* [指数演算子](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016)(ES2016)
* ES2016 (を[含む](https://developer.microsoft.com/microsoft-edge/platform/status/arrayprototypeincludeses2016))
* [オブジェクト. 値](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/values)と[オブジェクト. エントリ](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/entries)(ES2017)

#### 実験的な JavaScript 機能 ( *about: flags*で有効)

* [モジュール](https://blogs.windows.com/msedgedev/2016/05/17/es6-modules-and-beyond/)(ES2015)
* [Async/await](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctionses2016) (ES2017)
* [Regex 記号](https://developer.microsoft.com/microsoft-edge/platform/status/regexpbuiltinses6)(ES2015)

詳細については、「 [*ES6 モジュールをプレビューする」および「ES2015、ES2016*](https://blogs.windows.com/msedgedev/2016/05/17/es6-modules-and-beyond/) 、および非同期コードを使用する」を参照してください。 [*Chakra と Microsoft EDGE での ES2016 Async 関数のサポートが簡単に*](https://blogs.windows.com/msedgedev/2015/09/30/asynchronous-code-gets-easier-with-es2016-async-function-support-in-chakra-and-microsoft-edge/)なります。

### Web 認証 API (FIDO 2.0 Web API)
Microsoft Edge の Web Authentication (以前の FIDO 2.0) API では、パスワードの推測、フィッシング詐欺、keylogging などのパスワード管理のすべての問題を回避するために、ユーザーが[Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961)生体認証を使用することができます。 現在の Microsoft Edge (ms プレフィックス) の実装は、以前の Web 認証仕様の草案に基づいており、今後変更される可能性があります。 Web 認証の詳細については[、「web 認証と Windows Hello」を](https://docs.microsoft.com/microsoft-edge/dev-guide/device/web-authentication)参照してください。

### Web 通知
Web 通知を使うと、サイトは、web ページとブラウザーのコンテキスト外のユーザーに通知する通知を表示したり、新しいメッセージや通知をユーザーに通知したり、サイトのユーザーの利用を向上させたりすることができます。 Microsoft Edge の Web 通知は、Windows 10 の通知プラットフォームとアクションセンターに完全に統合されており、システム全体の他のアプリとの一貫性のあるエクスペリエンスを提供し、アクセス許可と非表示時間を簡単に制御できます。 詳細については、 [「Microsoft Edge で Web 通知](https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge/)を確認する」を参照してください。 

### Web Speech API
[Web SPEECH api](https://dvcs.w3.org/hg/speech-api/raw-file/tip/speechapi.html)は、音声認識と音声合成 (またはテキスト読み上げ) の2つの部分で構成された JavaScript api です。 現時点では、Microsoft Edge では音声合成のみがサポートされています。 音声合成では、ユーザーがスピーカーを通して読み上げたテキストを音声に変換することが必要になります。 詳細については、「[音声合成](https://docs.microsoft.com/microsoft-edge/dev-guide/multimedia/web-speech-api)開発者ガイド」をご覧ください。 

## EdgeHTML 14 の新しい Api

EdgeHTML 14 の新しい Api の一覧を次に示します。 [Interface name] の形式で一覧表示され**ます。 [api 名]**。
<iframe height='585' scrolling='no' title='EdgeHTML 14 の新しい Api' src='//codepen.io/MSEdgeDev/embed/oWMEPE/?height=585&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MSEdgeDev/pen/oWMEPE/'> </a> <a href='https://codepen.io/MSEdgeDev'> CodePen の MSEdgeDev (@MSEdgeDev </a> ) で <a href='https://codepen.io'> の Pen New api については、「EdgeHTML 14」を参照してください </a> 。
</iframe>
