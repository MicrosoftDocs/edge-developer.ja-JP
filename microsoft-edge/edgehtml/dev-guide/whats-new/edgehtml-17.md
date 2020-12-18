---
title: EdgeHTML 17 の新機能と API
description: このガイドでは、EdgeHTML 17 に含まれる開発者向けの機能と標準の概要について説明します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 75429528fd814963a8c78e27f85564223fb2d3c8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234497"
---
# EdgeHTML 17 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

[Windows 10 April 2018 Update \(04/2018,](https://blogs.windows.com/windowsexperience/2018/04/27) Build 17134\) の一部として[、EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) Web プラットフォームで提供される新機能と更新された機能の一覧を次に示します。  特定の [Windows Insider](https://insider.windows.com) Preview ビルドの変更については [、Microsoft Edge の変更ログ](https://developer.microsoft.com/microsoft-edge/platform/changelog) と EdgeHTML の新機能に関するページ [をご覧ください](../whats-new.md)。  

次の変更の一覧の permalink を次に示します [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md) 。  

## 新機能と更新された機能  

### ARIA 1.1 の役割、状態、およびイベント  

EdgeHTML 17 では、Accessible [Rich Internet Applications (RIA-ARIA) 1.1](https://w3.org/TR/wai-aria-1.1)仕様から、フィード、[](https://www.w3.org/TR/wai-aria-1.1#feed)[フォーム](https://www.w3.org/TR/wai-aria-1.1#form)[、aria-haspopup、aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-haspopup)など、さまざまなロール、状態、およびプロパティのサポートが追加されています。 [](https://w3.org/TR/wai-aria-1.1#aria-placeholder)変更ログ[で ARIA 更新プログラムの完全な一覧を見つける](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。  この更新プログラムを使用して、EdgeHTML 17 は、RIA-ARIA 1.1 で定義されているロールと属性をサポートします。  <!--  Check out the [Accessibility](../../accessibility.md) docs for more information about accessibility in Microsoft Edge.  -->  

### CSS マスク  

EdgeHTML 17 には、CSS マスクの試験 [的なサポートが含まれています](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)。  部分的な実装では、CSS マスク イメージ[とマスク サイズの](https://developer.mozilla.org/docs/Web/CSS/mask-image)[プロパティが導入](https://developer.mozilla.org/docs/Web/CSS/mask-size)されています。  about:flags の [CSS マスクを有効にする] フラグを確認して、試用してください。  

### SVG 要素での CSS 変換  

EdgeHTML 17 では、SVG 要素とプレゼンテーション属性で CSS 変換がサポートされます。  これにより、回転、スケーリング、移動、ゆがみ、翻訳など、SVG 要素を視覚的に操作できます。  

### 拡張機能  

Microsoft Edge では、拡張機能からの [通知を表示](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) する通知 API がサポートされます。  拡張機能の開発者は、ユーザーの完全な操作をサポートするさまざまな種類の通知 \(基本、リスト、画像など)を作成できます。  通知は、アクション センターにも自動的にログインされます。  拡張機能で [この API を](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) 使用する方法に関する通知サンプルにアクセスしてください。  

EdgeHTML 17 では、標準のタブ API クラスの一部としてメソッド `Tabs.reload()` もサポートされています。  また、Windows 10 April 2018 Update の新機能として、ユーザーは InPrivate ブラウズ中に拡張機能の実行を許可するように選択できます。  

このリリースの拡張機能の更新プログラムについて詳しくは [、Windows 10 April 2018 Update](https://blogs.windows.com/msedgedev/2018/05/24)の拡張機能の新機能に関するブログ投稿をご覧ください。  

### DevTools  

DevTools のこのリリースには、従来の Microsoft Edge 用のブラウザー内 \( \) ツールとして、および Microsoft Store からスタンドアロン `F12` [の Windows 10](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) アプリとしてプレビューする 2 つの方法が含まれています。  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge DevTools アプリ" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   Microsoft Edge DevTools アプリ  
:::image-end:::  

このツールは、リモート デバッグの基本的なサポート (新しい[](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge)[DevTools Protocol](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\ 経由)、PWA デバッグ機能[](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)[、IndexedDB](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)キャッシュ管理、垂直ドッキングなど、多くの主要な機能で更新されました。 [](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) また、パフォーマンスと信頼性 [に対](./edgehtml-16.md) する継続的な投資の一環として、最後のリリースで開始された全体的なリファクタリング作業も継続しました。  

詳 [しくは、最新の Windows 10 更新プログラム (EdgeHTML 17) の DevTools](../../devtools-guide/whats-new/edgehtml-17.md) をご覧ください。  

### JavaScript  

EdgeHTML 17 では、Chakra JavaScript エンジンを使用すると、多くの主要な領域でパフォーマンスが向上しています。  

:::row:::
   :::column span="1":::
      **より細いメモリ使用量**  
   :::column-end:::
   :::column span="2":::
      *   \(Re-\)オブジェクト リテラルの [方向キー関数](https://github.com/Microsoft/ChakraCore/pull/4105) とメソッド [の解析を延期する](https://github.com/Microsoft/ChakraCore/pull/4136)  
      *   [RegExp バイトコードリファクタリング](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **JavaScript の組み込み時間を短縮する**
   :::column-end:::
   :::column span="2":::
      *   [Object.create の型共有](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [Object.assign のポリモーフィック インライン キャッシュ](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [JSON.parse/stringify の最適化](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [JavaScript での配列反復子の書き換えと高速化.of](https://github.com/Microsoft/ChakraCore/pull/4095)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Web アセンブリ**
   :::column-end:::
   :::column span="2":::
      *   [インリングのサポート](https://github.com/Microsoft/ChakraCore/pull/3681)  
   :::column-end:::
:::row-end:::  

すべての詳細 [については、EdgeHTML 17 の JavaScript と WebAssembly の](https://blogs.windows.com/msedgedev/2018/06/19) パフォーマンスの向上を確認してください。  

### メディア要素

EdgeHTML 17 には、次の [HTMLMediaElement の更新が含](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) まれています。  

*   要素の `preload` 新しい [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 属性は、プリロードするデータを示します。
*   メソッドとプロパティ [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) を追加 [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) すると、開発者はオーディオ出力デバイスを選択できます。  
    
    > [!NOTE]
    > これは、RTC ではまだ使用できません。  
    
### メディア キャプチャ API  

Microsoft Edge では、メディア キャプチャ API を介した RTC での画面キャプチャ [がサポートされます](https://w3c.github.io/mediacapture-screen-share)。  この機能を使用すると、Web ページはユーザーのディスプレイ デバイスの出力をキャプチャできます。通常は、プラグインを使用する仮想会議やプレゼンテーション用にデスクトップをブロードキャストするために使用されます。  

### プログレッシブ Web アプリ  

EdgeHTML 17 以降、サービス ワーカーとプッシュ通知は既定で有効になっています (これらの機能の詳細については、「サービス ワーカー: ページを越えて」を参照[してください)。](https://blogs.windows.com/msedgedev/2017/12/19)  これで、Windows 10 上の段階的な Web Apps \(PWAs\) の技術的基盤を構築するテクノロジ \(Fetch ネットワークと Push and Cache API を含む)が完成します。  

PAS は、インストール/ホーム[](https://en.wikipedia.org/wiki/Progressive_enhancement)画面の起動、オフライン サポート、プッシュ通知など、サポート プラットフォームとブラウザー エンジン上のネイティブ アプリのような機能によって段階的に拡張される単純な Web アプリです。  Microsoft Edge \(EdgeHTML\) エンジンを搭載した Windows 10 では、PAS は、ユニバーサル [Windows](/windows/uwp/get-started/whats-a-uwp) プラットフォーム アプリとしてブラウザー ウィンドウとは別に実行できるという利点があります。  

PAS 以外にも、サービス ワーカーとキャッシュ API を使用すると、開発者はネットワーク要求を傍受してキャッシュから応答できます。  Web サイトは、ページ読み込みパフォーマンスと信頼性を細かく設定するためにサービス ワーカー キャッシュを活用したり、インターネットや低品質接続の期間中にオフライン エクスペリエンスを提供したりするために、本格的な Web アプリである必要さえありません。  

Windows 10 のサービス ワーカー [と PAS](../../progressive-web-apps/index.md) の詳細については、Windows ドキュメントの段階的な Web アプリをご覧ください。  

### Web セキュリティ  

EdgeHTML 17 では、Subresource Integrity \(SRI\) のサポートが導入されています。  [サブリソースの整合性](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) は、ブラウザーがフェッチされたリソース \(画像、スクリプト、フォントなど)が予期しない操作なしに配信されるのを検証できるセキュリティ機能です。  

以下の例のように、Web ページに読み込むリソースの暗号化ハッシュ表現を含む属性を、1 つ以上の要素 `integrity` `<script>` `<link>` に追加します。  次に、Microsoft Edge は要求されたリソースと属性で定義されているハッシュを比較 `integrity` します。  一致しない場合、Microsoft Edge はリソースを実行し、ネットワークにエラーを返します。  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

また、EdgeHTML 17 の新機能である [Upgrade-Insecure-Requests 要求](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) ヘッダーを使用すると、ブラウザーは安全な閲覧エクスペリエンスを要求できます。  このヘッダーは、ブラウザーが安全でない要求のアップグレードをサポートし、利用可能な場合はユーザーを安全なバージョンのサイトにリダイレクトする必要があるというサーバーに指示します。  

### 可変フォント
可変フォント \(CSS [フォント](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) バリエーション設定や [フォント](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)光学式サイズ変更 \を含む) の完全なサポートは、EdgeHTML 17 で利用できます。  可変フォントを使用すると、開発者はさまざまな軸を調整することで、1 つのフォントで一見異なる書体の外観を実現できます。複数のフォント ファイルの必要性が減り、パフォーマンスが向上します。  

Web 開発者やデザイナー [に](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)提供される可変フォントや、サイトで使用する方法について学ぶには、ご参加ください。  また、ブログ投稿の変数フォントの詳細については、「可変フォントを使用して表現力のあるパフォーマンスの高い文字体裁を [Microsoft Edge に取り込む」を参照してください](https://blogs.windows.com/msedgedev/2018/03/13)。  

<iframe height='456' scrolling='no' title='Variable VariableS ticket examples' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>CodePen の MSEdgeDev ( @MSEdgeDev ) による Pen <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> Variable Variable のチケットの例 </a> <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> を参照してください </a> 。</iframe>  

## EdgeHTML 17 の新しい API  

EdgeHTML 17 の新しい API の完全な一覧を次に示します。  これらは次の形式で一覧表示されます `[interface name].[api name]` 。  

> [!NOTE] 
> 以下の API は DOM で公開されていますが、一部の API のエンド エンドの動作はまだ開発中である可能性があります。  機能の  [サポートに関する公式](https://developer.microsoft.com/microsoft-edge/platform/status) の単語については、Microsoft Edge プラットフォームの状態を参照してください。  

<iframe height='580' scrolling='no' title='EdgeHTML 17 の新しい API' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>CodePen の <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'> EdgeHTML 17 by MSEdgeDev ( @MSEdgeDev ) の Pen New API を </a> <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> 参照してください </a> 。</iframe>  

> [!TIP]
> 他のブラウザー[](https://blogs.windows.com/msedgedev/2017/10/18)や Web コミュニティと提携し[、MDN Web Docs](https://developer.mozilla.org)を、現在および新たな標準ベースの Web テクノロジに関する有用で、未確定のブラウザーに依存しないドキュメントの決定的な場所として採用しています。  EdgeHTML API のサポートに関する詳細は、MDN Web リファレンス ライブラリの各ページ [で直接確認できます](https://developer.mozilla.org/docs/Web)。  Microsoft Edge でサポートされている最新 [の](https://developer.microsoft.com/microsoft-edge/status) 機能については、Microsoft Edge のプラットフォームの状態にアクセスしてください。  

## 以前の EdgeHTML リリース  

[EdgeHTML 13 / Windows ビルド 10586 (11/2015)](https://aka.ms/devguide_edgehtml_13)  

[EdgeHTML 14 / Windows ビルド 14393 (8/2016)](https://aka.ms/devguide_edgehtml_14)  

[EdgeHTML 15 / Windows ビルド 15063 (4/2017)](https://aka.ms/devguide_edgehtml_15)  

[EdgeHTML 16 / Windows ビルド 16299 (10/2017)](https://aka.ms/devguide_edgehtml_16)  
