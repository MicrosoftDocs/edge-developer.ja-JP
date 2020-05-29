---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: このガイドでは、Microsoft Edge に含まれている開発者向けの機能と標準の概要について説明します。
title: 開発ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 36c5e6530ff584a97e4b42910757495362a1960d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568849"
---
# EdgeHTML 16 の新機能

次に、 [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17/edgehtml-16-fall-creators-update/) web platform で出荷される新機能と更新された機能の一覧を示し[ます (10/2017](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update/) 、ビルド 16299)。 特定の Windows Insider Preview ビルドでの変更については、 [Microsoft Edge の Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/)と[EdgeHTML の新機能](../whats-new.md)をご覧ください。

次の変更の固定リンクを示し [https://aka.ms/devguide_edgehtml_16](https://aka.ms/devguide_edgehtml_16) ます。

## 新機能と更新された機能

### CSS グリッドのレイアウト

Microsoft Edge で、 [CSS グリッドレイアウト](https://www.w3.org/TR/css-grid-1/)のプレフィックスのない実装がサポートされるようになりました。 [Grid レイアウト](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout)では、2次元グリッドベースのレイアウトシステムが定義されています。これにより、フロートまたはスクリプトを使用した配置で、より多くのレイアウト適切な決まりが可能になります。 次の例では、CSS Grid レイアウトを使って、基本的な web ページの構造を作成しています。


<iframe height='303' scrolling='no' title='CSS グリッドのレイアウト' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> </a> CodePen の MSEdgeDev (@MSEdgeDev) でペン CSS グリッドレイアウトを参照してください <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> </a> 。
</iframe>


### CSS `object-fit` と `object-position`

EdgeHTML 16 では、CSS プロパティとのサポートが導入さ [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position) れています。  これらのプロパティは、コンテンツボックス内の置換されたコンテンツの位置とサイズを制御します。  

### 開発者ツール

このリリースでは、優れた信頼性とパフォーマンスを向上させるための主要な Microsoft Edge DevTools リファクタリングの取り組みを開始しました。また、 [Windows Insider](https://insider.windows.com/)ビルドで今日使用できる新機能の多数を追加しました。  変更点については、 [Microsoft Edge DevTools のガイド](../../devtools-guide/whats-new.md)をご覧ください。

### JavaScript

[EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/31/optimizations-webassembly-sharedarraybuffer-atomics-edgehtml-16/#FodxEPHxR4WkbtyA.97)は、以前のリリースの Javascript パフォーマンスの最適化について、Chakra エンジンの機能を拡張して、関数の遅延/再遅延、ポリモーフィックなインラインキャッシュの使用、 *try/finally*ブロックでの関数の最適化を実現しています。

さらに、EdgeHTML 15 で最初にプレビューされた機能は、既定で安定して有効になりました。

#### 新機能 (既定でオン)

* [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly)おMVP ([デモ](https://webassembly.org/demo/))
* [共有メモリと Atomics](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)

### 支払い要求 API

[支払い要求 API](../windows-integration/payment-request-api.md)は、ユーザーがクラウドに保存されている商人、消費者、支払方法 (クレジットカードなど) との仲介としてブラウザーが機能するようにする、オープンなクロスブラウザー標準です。  EdgeHTML 16 の API は、W3C の最新の[支払い要求 api](https://w3c.github.io/payment-request/)仕様と一致するように更新されました。 次のようなシナリオが考えられます。
* メソッドのサポート `canMakePayment()`
* プロパティのサポート `requestId`
* プロパティのサポート `id`
* `complete()`メソッドのパラメーターの既定値が `result` "" から "不明" に変更されました。

### サービス員

[サービスワーカー](https://www.w3.org/TR/service-workers-1/)は、web ページのバックグラウンドで実行されるイベント駆動型のスクリプトです。 サービスワーカーは、以前は、ネットワークからの要求の傍受と処理、バックグラウンド同期の管理と処理、ローカルストレージ、プッシュ通知などのネイティブアプリでのみ利用できる機能を有効にします。 サービスワーカーのサポートはまだ開発段階ですが、Microsoft Edge で、サービスワーカー機能を [ **about: flags**] で有効にすることによって、実験的なサービスワーカーサポートで PWA をテストできます。

### WebVR
Microsoft Edge 用 WebVR では、[モーションコントローラー](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)のサポートが追加されました。 これらのコントローラーは、空間内の正確な位置を持ち、仮想現実のデジタルオブジェクトのきめ細かな操作を実現します。

![モーションコントローラー](../media/MotionControllers.jpg)

また、WebVR は、2種類のエクスペリエンスをサポートするように最適化されています。

**Windows Mixed Reality pc** -内蔵グラフィックス付きのデスクトップとノート pc。  これらのデバイスに接続すると、イマーシブヘッドセットは1秒あたり60フレームで動作します。  
**Windows Mixed Reality ウルトラ pc** -個別のグラフィックスを備えたデスクトップとノート pc。 これらのデバイスに接続すると、イマーシブヘッドセットは1秒あたり90フレームで動作します。   

どちらのセットアップでも、同じイマーシブビデオとゲームエクスペリエンスがサポートされます。 

今後の Windows Mixed Reality の更新について詳しくは、「 [Windows Mixed reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update/)の更新」のブログ投稿をご覧ください。 

ガイドとデモについては、「 [Webvr 開発者向けガイド」](https://docs.microsoft.com/microsoft-edge/webvr/)を参照してください。

 > [!NOTE] 
 > WebVR の仕様はまだ開発段階のため、Microsoft Edge の実装は後で変更される可能性があります。

## EdgeHTML 16 の新しい Api

EdgeHTML 16 の新しい Api の一覧を次に示します。 [Interface name] の形式で一覧表示され**ます。 [api 名]**。

> [!NOTE] 
> 次の Api は DOM に公開されますが、一部のエンドツーエンドの動作はまだ開発中の可能性があります。 機能のサポートに関するオフィシャル単語については、 [Microsoft Edge プラットフォームの状態](https://developer.microsoft.com/microsoft-edge/platform/status/)を参照してください。

<iframe height='559' scrolling='no' title='EdgeHTML 16 の新しい Api' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>EdgeHTML 16 </a> x MSEdgeDev (@MSEdgeDev) の Pen 新しい api <a href='https://codepen.io/MSEdgeDev'> を </a> CodePen で <a href='https://codepen.io'> </a> 参照してください。</iframe></p>

<h2 id="previous-edgehtml-releases">以前の EdgeHTML リリース</h2>
<p><a href="https://aka.ms/devguide_edgehtml_12" data-raw-source="[EdgeHTML 12 / Windows build 10240 (7/2015)](https://aka.ms/devguide_edgehtml_12)">EdgeHTML 12/Windows ビルド 10240 (7/2015)</a>

[EdgeHTML 13/Windows ビルド 10586 (11/2015)](https://aka.ms/devguide_edgehtml_13)

[EdgeHTML 14/Windows ビルド 14393 (8/2016)](https://aka.ms/devguide_edgehtml_14)

[EdgeHTML 15/Windows ビルド 15063 (4/2017)](https://aka.ms/devguide_edgehtml_15)
