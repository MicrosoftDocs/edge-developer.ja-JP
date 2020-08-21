---
title: EdgeHTML 17 の新機能と API
description: このガイドでは、EdgeHTML 17 に含まれる開発者の機能と標準の概要を示します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 0fc7dda532866e8970003bce2febb7e46fbbc459
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941945"
---
# Microsoft EdgeHTML 17 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

[Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/27) \(04/2018, ビルド 17134\) の一部として[、EdgeHTML 17 Web](https://blogs.windows.com/msedgedev/2018/04/30)プラットフォームで出荷された新機能と更新された機能の一覧を示します。  特定の Windows Insider Preview ビルド [の変更内容](https://insider.windows.com) については [、Microsoft Edge の変更履歴と](https://developer.microsoft.com/microsoft-edge/platform/changelog) [EdgeHTML の新機能を参照してください](../whats-new.md)。  

次の一覧を行うと、この機能が利用できます [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md) 。  

## 新機能と更新された機能  

### ARIA 1.1 の役割、状態、イベント  

Microsoft EdgeHTML 17 では、アクセシビリティに対応したリッチな[インターネット アプリケーション (WAI-ARIA) 1.1 の指定](https://w3.org/TR/wai-aria-1.1)([フ](https://www.w3.org/TR/wai-aria-1.1#feed)ィード、[フォーム](https://www.w3.org/TR/wai-aria-1.1#form)[、aria-haspopup、aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-haspopup)[aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-placeholder)など) からさまざまな役割、状態、プロパティのサポートが追加されました。変更ログ[で ARIA の更新プログラムの完全なリストを検索します](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。  今回の更新プログラムでは、WAI-ARIA 1.1 で定義されたすべてのロールと属性がサポートされるようになりました。  Microsoft Edge [のアクセシビリティ](../../accessibility.md) に関する詳細については、アクセシビリティに関するドキュメントをご覧ください。  

### CSS マスキング  

EdgeHTML 17 では、CSS マスキングのためのサポート [が含まれており、サポートが含まれており、サポートが含まれており、サポートが含まれており、サポートされます](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)。  部分的な実装では、CSS [マスク](https://developer.mozilla.org/docs/Web/CSS/mask-image) イメージとマス [ク サイズのプロパティが](https://developer.mozilla.org/docs/Web/CSS/mask-size) 説明されています。  実用する場合は、「CSS Masking を有効にする」フラグを確認してください。  

### SVG 要素での CSS 変換  

Microsoft EdgeHTML 17 では、SVG 要素とプレゼンテーション属性の CSS 変換がサポートされるようになりました。  これにより、回転、スケーリング、移動、スケース、翻訳を含む、SVG 要素を視覚的に操作できます。  

### 拡張機能  

Microsoft Edge では、 [拡張機能からの通知を表示する通知 API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) がサポートされるようになりました。  拡張機能開発者は、すべてのユーザーが操作をサポートするさまざまな種類の通知 \(基本、リスト、画像など) を作成できるようになりました。  通知は、アクション センターにも自動的にログインされます。  拡張機能で [この](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) API の使用方法についての通知サンプルにアクセスしてください。  

また、Microsoft EdgeHTML 17 では、標準タブ API クラスの一部としてメソ `Tabs.reload()` ッドがサポートされるようになりました。  また、Windows 10 2018 年 4 月の更新プログラムの新機能を使用すると、ユーザーは、InPrivate ブラウジング中に拡張機能を実行できるようになりました。  

このリリースの拡張機能の更新について詳しくは [、Windows 10 April 2018 Update](https://blogs.windows.com/msedgedev/2018/05/24)の拡張機能のための新機能をブログ投稿に移動してください。  

### DevTools  

このリリースでは、DevTools のリリースでは、従用ブラウザー \( \( \) ツールと Microsoft Store からスタンドア `F12` ロン [の Windows 10](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) アプリとしてプレビューする方法の 2 つの方法があります。  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge DevTools アプリ" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   Microsoft Edge DevTools アプリ  
:::image-end:::  

また、ツールは、リモート デバッ [グのサポート](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) \(新 [しい DevTools プロトコ](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)ル \) を使用した [、PWA](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)デバッグ [管理、](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)インデックス作成、垂直ドッキングなど、多くの主要な機能 [で更新されています](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) 。 また、パフォーマンスと確実性に関 [する](./edgehtml-16.md) 進行中の一部として、全体的な再現作業を継続していました。  

詳細については [、最新の Windows 10 更新プログラム (EdgeHTML 17) の DevTools](../../devtools-guide/whats-new/edgehtml-17.md) にアクセスしてください。  

### JavaScript  

Microsoft EdgeHTML 17 では、Chakra JavaScript エンジンでは、次の複数の主要領域でパフォーマンスが向上します。  

:::row:::
   :::column span="1":::
      **Leaner メモリ フットプリント**  
   :::column-end:::
   :::column span="2":::
      *   オブジェクト リテラルの矢印関数およびメソッ[arrow functions](https://github.com/Microsoft/ChakraCore/pull/4105)ドについて \(Re-\)[デファイナル](https://github.com/Microsoft/ChakraCore/pull/4136)  
      *   [RegExp バイト コードのリファクター](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **JavaScript の組み込み関数のパフォーマンスを上下**
   :::column-end:::
   :::column span="2":::
      *   [Object.create の共有の種類](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [Object.assign の Polymorphic インライン キャッシュ](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [JSON.parse/stringify の最適化](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [JavaScript で配列のイターターを書き換え、...が](https://github.com/Microsoft/ChakraCore/pull/4095)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Web アシンボリ**
   :::column-end:::
   :::column span="2":::
      *   [Inling サポート](https://github.com/Microsoft/ChakraCore/pull/3681)  
   :::column-end:::
:::row-end:::  

詳細については [、EdgeHTML 17 での JavaScript と WebAssembly](https://blogs.windows.com/msedgedev/2018/06/19) のパフォーマンスが改善されました。  

### メディア要素

EdgeHTML 17 には、次のような [HTMLMediaElement の更新が含](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) まれています。  

*   要素の `preload` 新しい属性 [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) は、先頭にどのデータが事前に読み込むべきかを示します。
*   メソッドとプロパティ [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) が追加され、デベロッ [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) パーはオーディオ出力デバイスを選択できます。  
    
    > [!NOTE]
    > これは RTC ではまだ利用できません。  
    
### メディア キャプチャ API  

Microsoft Edge では、メディア キャプチャ API を通して RTC で画面キ [ャプチャをサポートできるようになりました](https://w3c.github.io/mediacapture-screen-share)。  この機能を使用すると、Web ページでユーザーの表示デバイスの出力をキャプチャできます。一般的に、プラグインの仮想会議やプレゼンテーション用にデスクトップをブロードキャストするために使用されます。  

### プログレッシブ Web アプリ  

Microsoft EdgeHTML 17 から、サービス ワーカーとプッシュ通知は既定で有効になっています (ブログ投稿サービス ワーカー[のこれらの機能の詳細については、ページをさらに発表するものです)。](https://blogs.windows.com/msedgedev/2017/12/19)  これにより、Windows 10 でプッシュネットワークの \(PWA\) を処理するテクノロジを示すテクノロジ (フェッチ ネットワーク、プッシュ/キャッシュ API を含む) が完了します。  

PWA は、インストール、ホーム画面起動、[progressively enhanced](https://en.wikipedia.org/wiki/Progressive_enhancement)オフライン サポート、プッシュ通知などのプラットフォームやブラウザー エンジンをサポートするネイティブ アプリのような機能で積み的に強化される Web アプリです。  PWA では、Microsoft Edge \(EdgeHTML\) エンジンを使用すると、ブラウザー ウィンドウをユニバーサル [Windows プ](/windows/uwp/get-started/whats-a-uwp) ラットフォーム アプリとしては別に実行する方法が楽になります。  

PWA、サービス ワーカー、キャッシュ API 以外では、ネットワーク要求をインタープライアンスし、キャッシュから応答できる機能をデベロッパーが許可します。  Web サイトは、インターネットや低品質のページ読み込みのパフォーマンスと信頼性を高めて、サービス ワーカー キャッシュを利用できるフル ブロー Web アプリでもかまいません。さらに、インターネットや低品質なしの間にオフライン エクスペリエンスを提供する機能も必要です。  

Windows 10 の Service Workers と PWA の詳細について説明するには [、Windows](../../progressive-web-apps-edgehtml/index.md) ドキュメントのプレイ状況に進みます。  

### Web セキュリティ  

Microsoft EdgeHTML 17 では、Subresource Integrity \(SRI\) のサポートが追加されました。  [サブリソース整合性は](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) 、ブラウザーが予期しない操作を行わずに配信されることを確認できるセキュリティ機能です。  

次の例のように、Web ページで読み込みる予算リソースのキャッシュ表現を含む `integrity` `<script>` `<link>` 属性を、要素に追加します。  その後、Microsoft Edge は要求されたリソースを、属性で定義されたハッシュと `integrity` 比較します。  一致しない場合、Microsoft Edge はリソースを実行しません。ネットワークにエラーが返されます。  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

また [、Upgrade-Insecure-Requests ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) を使用すると、ブラウザーでは、ブラウザーがスキューでの閲覧体験を要求することができます。  このヘッダーは、ブラウザーが不正な要求のアップグレードをサポートしているサーバーに示され、ユーザーは利用可能な場合は、サイトの保護されたバージョンにリダイレクトする必要があることをサーバーに示します。  

### 可変フォント
Variable Fonts \(CSS[フォント バリエーション設定および](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)[フォント-optical-sizing](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) の完全なサポートは、EdgeHTML 17 で入手できます。  さまざまな軸を調整することで、デベロッパーは、さまざまな軸を調整することで、1 つのフォントで異なる書スタイルの外観を実現できます。複数のフォント ファイルが必要なファイルやパフォーマンス向上のためのニーズを下げることができます。  

拡張機能に参加 [して、Web 開](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)発者やデザイナーが提供する可変フォントとサイトでの使い分けについて学習します。  また、ブログ投稿に表示される可変フォントの詳細については、「もちのとも」を参照してください。可用なフォントを使用して Microsoft Edge に対する文字体裁を [実行する](https://blogs.windows.com/msedgedev/2018/03/13)。  

<iframe height='456' scrolling='no' title='可変チェットの例' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> </a> CodePen の MsEdgeDev <a href='https://codepen.io/MSEdgeDev'> (@MSEdgeDev) によるペン変数チ@MSEdgeDev </a> を <a href='https://codepen.io'> 確認できます </a> 。</iframe>  

## EdgeHTML 17 の新しい API  

EdgeHTML 17 の新しい API の完全な一覧を次に示します。  これらは形式で表示されます `[interface name].[api name]` 。  

> [!NOTE] 
> 次の API は DOM で予定されていますが、一部の開発中のエンドツーエンド動作がまだあります。  機能サポート  [のコーサル語については、Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/status) プラットフォームの状態を参照してください。  

<iframe height='580' scrolling='no' title='EdgeHTML 17 の新しい API' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'>CodePen の EdgeHTML 17 の </a> 新しい <a href='https://codepen.io/MSEdgeDev'> API @MSEdgeDev </a> <a href='https://codepen.io'> を参照してください </a> 。</iframe>  

> [!TIP]
> MDN [partnered](https://blogs.windows.com/msedgedev/2017/10/18) Web ドキュメントは、最新の、ブラウザーアジャイル、現在および拡大標準 Web テクノロジのための定義的な場所として[、MDN Web](https://developer.mozilla.org)ドキュメントを開発する場合の定義的な場所としてパートナー化しています。  Microsoft EdgeHTML API のサポートの詳細は、MDN Web リファレンス ライブラリの各 [ページに直接表示できます](https://developer.mozilla.org/docs/Web)。  Microsoft Edge でサポートされている最新機能については [、Microsoft](https://developer.microsoft.com/microsoft-edge/status) Edge のプラットフォームの状態にアクセスしてください。  

## 以前の EdgeHTML リリース  

[Microsoft EdgeHTML 13 / Windows ビルド 10586 (2015/11)](https://aka.ms/devguide_edgehtml_13)  

[EdgeHTML 14 / Windows ビルド 14393 (8/2016)](https://aka.ms/devguide_edgehtml_14)  

[Microsoft EdgeHTML 15 / Windows ビルド 15063 (4/2017)](https://aka.ms/devguide_edgehtml_15)  

[Microsoft EdgeHTML 16 / Windows ビルド 16299 (10/2017)](https://aka.ms/devguide_edgehtml_16)  
