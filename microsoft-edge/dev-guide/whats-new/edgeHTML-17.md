---
title: EdgeHTML 17 の新機能と Api
description: このガイドでは、EdgeHTML 17 に含まれている開発者向けの機能と標準の概要について説明します。
author: mattwojo
ms.author: mattwoj
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 1359464bfb9ec6f2b84536a11b0fb4bfcce2fb1c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568845"
---
# EdgeHTML 17 の新機能

[2018 年4月の更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/27/make-the-most-of-your-time-with-the-new-windows-10-update/)(04/2018、ビルド 17134) の一部として、 [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30/edgehtml-17-april-2018-update/) web プラットフォームで出荷される新機能と更新された機能の一覧を示します。 特定の[Windows Insider](https://insider.windows.com/) Preview ビルドでの変更については、 [Microsoft Edge の Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/)と[EdgeHTML の新機能](../whats-new.md)をご覧ください。

次の変更の固定リンクを示し [https://aka.ms/devguide_edgehtml_17](https://aka.ms/devguide_edgehtml_17) ます。

## 新機能と更新された機能 

### ARIA 1.1 の役割、状態、イベント

EdgeHTML 17 では、[フィード](https://www.w3.org/TR/wai-aria-1.1/#feed)、[フォーム](https://www.w3.org/TR/wai-aria-1.1/#form)、 [aria-haspopup](https://w3.org/TR/wai-aria-1.1/#aria-haspopup)、 [aria、Placeholder](https://w3.org/TR/wai-aria-1.1/#aria-placeholder)など、アクセシビリティ性の高い[リッチインターネットアプリケーション (wai-aria 使った-ARIA) 1.1 仕様](https://w3.org/TR/wai-aria-1.1/)のさまざまな役割、状態、プロパティのサポートが追加されています。[changelog での ARIA の更新プログラムの完全な一覧](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)を確認します。 この更新プログラムでは、EdgeHTML 17 は WAI-ARIA 使った-ARIA 1.1 で定義されたすべての役割と属性をサポートするようになりました。 Microsoft Edge でのアクセシビリティについて詳しくは、[アクセシビリティ](https://docs.microsoft.com/microsoft-edge/accessibility)に関するドキュメントをご覧ください。

### CSS マスク

EdgeHTML 17 には、 [CSS マスク](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)の実験的なサポートが含まれています。 部分的な実装では、CSS[マスクと画像](https://developer.mozilla.org/docs/Web/CSS/mask-image)および[マスクサイズ](https://developer.mozilla.org/docs/Web/CSS/mask-size)のプロパティが導入されています。  「[CSS のマスキングを有効にする]」フラグを確認します。

### SVG 要素での CSS の変換

EdgeHTML 17 では、SVG 要素とプレゼンテーション属性での CSS 変換がサポートされるようになりました。 これにより、回転、拡大縮小、移動、傾斜、翻訳などの SVG 要素を視覚的に操作できます。 

### 拡張機能 

Microsoft Edge で、拡張機能からの通知を表示する[通知 API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications)がサポートされるようになりました。 拡張機能の開発者は、完全なユーザー操作をサポートする、さまざまな種類の通知 (基本的、リスト、画像など) を作成できるようになりました。 通知は、アクションセンターにも自動的にログインされます。 この API を拡張機能で使用する方法については、[通知のサンプル](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications)を参照してください。

EdgeHTML 17 `Tabs.reload()` は、標準タブ API クラスの一部としてもメソッドをサポートするようになりました。 さらに、2018年4月の更新プログラムの新機能により、ユーザーは inPrivate ブラウズ中に拡張機能を実行できるようにすることを選択できるようになりました。

このリリースでの拡張機能の更新について詳しくは、 [Windows 10 年 4 2018 月の更新プログラムで](https://blogs.windows.com/msedgedev/2018/05/24/new-extension-features-april-2018-update-notifications-inprivate/)、「拡張機能のブログの新機能」をご覧ください。

### DevTools
DevTools のこのリリースは、microsoft Edge 用の従来のブラウザー () ツールとして、 `F12` Microsoft Store からスタンドアロンの[Windows 10 アプリ](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview)としてプレビューする、2つの方法で提供されています。

![Microsoft Edge DevTools アプリ](../../devtools-protocol/media/microsoft-edge-devtools.png) 

また、このツールは、[リモートデバッグ](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)の基本的なサポート (新しい[devtools プロトコル](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)を使用)、 [PWA のデバッグ機能](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)、 [indexeddb キャッシュ管理](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)、[縦型のドッキング](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge)など、さまざまな主要機能によって更新されています。 また、パフォーマンスと信頼性への継続的な投資の一環として、最後のリリースで行われた全体的な[リファクタリングの取り組み](./edgehtml-16.md)を継続しました。

詳細について[は、「Windows 10 の最新の更新プログラム (EdgeHTML 17) の Devtools」](../../devtools-guide/whats-new/edgehtml-17.md)を参照してください。

### JavaScript

EdgeHTML 17 では、次のようないくつかの主要領域で、Chakra JavaScript エンジンによってパフォーマンスが向上しています。

**スリムなメモリ使用量**

 - (再)[オブジェクトリテラル上](https://github.com/Microsoft/ChakraCore/pull/4136)の[矢印関数](https://github.com/Microsoft/ChakraCore/pull/4105)とメソッドの解析を延期します。
 - [RegExp バイトコードのリファクタリング](https://github.com/Microsoft/ChakraCore/pull/3915)

**より高速な JavaScript の組み込み**

 - [オブジェクトの共有を入力します。作成](https://github.com/Microsoft/ChakraCore/pull/3901)
 - [Object のポリモーフィックなインラインキャッシュ。](https://github.com/Microsoft/ChakraCore/pull/3792)
 - [JSON. parse/stringify の最適化](https://github.com/Microsoft/ChakraCore/pull/4077)
 - [JavaScript での配列反復子の再書き込みと高速化数](https://github.com/Microsoft/ChakraCore/pull/4095)

**Web アセンブリ**

 - [サポート](https://github.com/Microsoft/ChakraCore/pull/3681) 

詳細については、「 [*JavaScript と EdgeHTML 17 のパフォーマンスが改善*](https://blogs.windows.com/msedgedev/2018/06/19/improved-javascript-webassembly-performance-edgehtml-17/#I4vzUJK2va54kSWl.97)されました」をご覧ください。

### メディア要素

EdgeHTML 17 には、次のような[Htmlmediaelement](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement)の更新が含まれています。
* 要素の新しい属性は、 `preload` [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 読み込むデータを示します。
* [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId)メソッドとプロパティを追加すると、 [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) 開発者はオーディオ出力デバイスを選ぶことができます。 (**注**: これはまだ RTC で avaiable していません)

### メディアキャプチャ API 
Microsoft Edge では、[メディアキャプチャ API](https://w3c.github.io/mediacapture-screen-share/)を使用した RTC の画面キャプチャがサポートされるようになりました。 この機能により、web ページでユーザーの表示デバイスの出力をキャプチャできるようになります。通常は、プラグインなしの仮想会議やプレゼンテーション用のデスクトップをブロードキャストするために使用されます。

### プログレッシブ Web アプリ
EdgeHTML 17 以降では、サービスワーカーとプッシュ通知は既定で有効になっています (この機能の詳細については、この[ページを](https://blogs.windows.com/msedgedev/2017/12/19/service-workers-going-beyond-page/)参照してください。 これにより、Windows 10 のプログレッシブ Web アプリ (PWAs) の技術基盤となる一連のテクノロジ (取得ネットワーク、プッシュとキャッシュ Api など) が完成します。

PWAs は、単なる web アプリであり、インストール/ホーム画面の起動、オフラインサポート、プッシュ通知などのプラットフォームとブラウザーエンジンのサポートについて、アプリのようなネイティブ機能によって[段階的に強化](https://en.wikipedia.org/wiki/Progressive_enhancement)されています。 Microsoft Edge (EdgeHTML) エンジンを備えた Windows 10 では、ブラウザーウィンドウと[ユニバーサル Windows プラットフォーム](https://docs.microsoft.com/windows/uwp/get-started/whats-a-uwp)アプリとで独立して実行できる機能が追加されました。

PWAs 以外のサービスワーカーとキャッシュ API により、開発者は、ネットワーク要求を傍受してキャッシュから応答することができます。 Web サイトは、短時間でのページ読み込みのパフォーマンスと信頼性を実現するために、サービスワーカーキャッシュを利用したり、インターネットや音質の低い接続中にオフライン環境を提供したりするための完全な機能を備えた web アプリではありません。  

[Windows ドキュメントのプログレッシブ Web アプリ](../../progressive-web-apps-edgehtml/index.md)にアクセスして、サービスの担当者と pwas の詳細情報については、windows 10 を参照してください。

### Web セキュリティ
EdgeHTML 17 には、サブリソースの完全性 (スリランカ) のサポートが導入されています。 [サブリソースの整合性](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity)は、取得したリソース (画像、スクリプト、フォントなど) が、予期しない操作なしで配信されることをブラウザーが確認できるようにするセキュリティの機能です。 

`integrity` `<script>` 次の例のように、web ページに読み込まれる予定のリソースの暗号化ハッシュ表現を含む属性を追加し `<link>` ます。 次に、Microsoft Edge は、要求されたリソースと属性で定義されているハッシュを比較し `integrity` ます。 一致しない場合、Microsoft Edge はリソースを実行せず、ネットワークにエラーを返します。

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```

さらに、EdgeHTML 17 の新機能として、セキュリティで保護されていない[要求](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests)のヘッダーを使用すると、ブラウザーで安全な参照エクスペリエンスを要求することができます。 このヘッダーは、ブラウザーがセキュリティで保護されていない要求のアップグレードをサポートしており、可能であれば、ユーザーがセキュリティで保護されたバージョンのサイトにリダイレクトされることをサーバーに通知します。

### 可変フォント
EdgeHTML 17 では、可変フォント (CSS[フォントバリエーションの設定](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)や[フォント光のサイズ変更](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)など) を完全にサポートしています。 さまざまな軸を調整することで、開発者は可変書体の外観を1つのフォントで見られるようになり、複数のフォントファイルや bettering のパフォーマンスを向上させることができます。

Expedition に参加して、 [web 開発者とデザイナーが提供する可変フォント](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts/)と、それらをサイトで使用する方法について説明します。 また、さまざまなフォントを使用して、 [Microsoft Edge に、豊かでパフォーマンスの高いタイポグラフィをもたらす](https://blogs.windows.com/msedgedev/2018/03/13/bringing-expressive-performant-typography-to-microsoft-edge-with-variable-fonts/)ブログ投稿の可変フォントについて説明します。

<iframe height='456' scrolling='no' title='変数の Tides チケットの例' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> </a> CodePen の MSEdgeDev (@MSEdgeDev) で、Pen 変数の tides チケットの例を参照してください <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> </a> 。</iframe>

## EdgeHTML 17 の新しい Api

EdgeHTML 17 の新しい Api の一覧を次に示します。 [Interface name] の形式で一覧表示されます。[api name]。

> [!NOTE] 
> 次の Api は DOM に公開されますが、一部のエンドツーエンドの動作はまだ開発中の可能性があります。 機能のサポートに関するオフィシャル単語については、 [Microsoft Edge プラットフォームの状態](https://developer.microsoft.com/microsoft-edge/platform/status/)を参照してください。

<iframe height='580' scrolling='no' title='EdgeHTML 17 の新しい Api' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'> </a> CodePen の EdgeHTML 17 by MSEdgeDev (@MSEdgeDev) の Pen 新しい api を参照してください <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> </a> 。</iframe>

> [!TIP]
> Microsoft は、現在および最新の標準ベースの web テクノロジについて、理解されていないブラウザーを使用したドキュメントの明確な場所として、 [MDN Web ドキュメント](https://developer.mozilla.org/)を採用して、他のブラウザーや web コミュニティと[提携](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/)しています。 EdgeHTML API のサポートについて詳しくは、 [MDN web リファレンスライブラリ](https://developer.mozilla.org/docs/Web)の各ページで直接参照できます。 Microsoft Edge でサポートされている最新機能については、Microsoft Edge の[プラットフォームの状態](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release)を参照してください。 

## 以前の EdgeHTML リリース

[EdgeHTML 13/Windows ビルド 10586 (11/2015)](https://aka.ms/devguide_edgehtml_13)

[EdgeHTML 14/Windows ビルド 14393 (8/2016)](https://aka.ms/devguide_edgehtml_14)

[EdgeHTML 15/Windows ビルド 15063 (4/2017)](https://aka.ms/devguide_edgehtml_15)

[EdgeHTML 16/Windows ビルド 16299 (10/2017)](https://aka.ms/devguide_edgehtml_16)
