---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: このガイドでは、EdgeHTML 16 の新機能と API の概要について説明します。
title: EdgeHTML 16 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7697114546153555d947903eda6bf8477cca3516
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234691"
---
# EdgeHTML 16 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

[Windows 10 Fall Creators Update \(10/2017,](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) Build 16299\) の一部として[、EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) Web プラットフォームに同梱されている新機能と更新された機能の一覧を次に示します。  特定の Windows Insider Preview ビルドの変更については [、Microsoft Edge の変更ログ](https://developer.microsoft.com/microsoft-edge/platform/changelog) と EdgeHTML の新機能に関するページ [をご覧ください](../whats-new.md)。  

次の変更の一覧の permalink を次に示します  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md) 。  

## 新機能と更新された機能  

### CSS グリッド レイアウト  

Microsoft Edge では、プレフィックスのない CSS グリッド レイアウトの [実装がサポートされます](https://www.w3.org/TR/css-grid-1)。  [グリッド レイアウトは](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) 、2 次元のグリッド ベースのレイアウト システムを定義します。これにより、浮動小数点またはスクリプトを使用した配置により、より多くのレイアウトの流動的性が実現されます。  次の例では、CSS グリッド レイアウトを使用して、基本的な Web ページの構造を作成します。  

<iframe height='303' scrolling='no' title='CSS グリッド レイアウト' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'>CodePen で MSEdgeDev ( @MSEdgeDev ) によるペン CSS グリッド レイアウト <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> </a> <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> を参照してください </a> 。</iframe>  

### CSS オブジェクトに適合する位置とオブジェクトの位置  

EdgeHTML 16 では、CSS プロパティと . [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position)  これらのプロパティは、コンテンツ ボックス内で置き換えられたコンテンツの位置とサイズを制御します。  

### 開発者ツール  

このリリースでは、堅牢性とパフォーマンスの向上に向けた Microsoft Edge DevTools リファクタリングの主要な取り組みを開始し [、Windows Insider](https://insider.windows.com) ビルドで現在使用を開始できる一連の新機能も追加しました。  変更された情報 [について詳しくは、Microsoft Edge DevTools](../whats-new.md) ガイドをご覧ください。  

### JavaScript  

[EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/31)は、関数の延期/再延期、ポリモーフィック インライン キャッシュの使用、ブロックを使用した関数の最適化を行う Chakra エンジンの機能を拡張することで、以前のリリースの Javascript パフォーマンス最適化を基に構築されています。 `try` / `finally`  

さらに、EdgeHTML 15 で最初にプレビューされた機能は安定しており、既定で有効になっています。  

#### 新機能  

既定でオン  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([demo](https://webassembly.org/demo)\)  
*   [共有メモリとアトミック](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### 支払い要求 API  

支払い要求 [API](../windows-integration/payment-request-api.md) はオープンなクロスブラウザー標準であり、ブラウザーは、消費者がクラウドに保存した業者、消費者、支払い方法 \(クレジット カード\など) の仲介者として動作できます。  EdgeHTML 16 の API は、最新の W3C 支払い要求 API 仕様に合 [わせて更新](https://w3c.github.io/payment-request) されました。  次のようなシナリオが考えられます。  

*   メソッドの `canMakePayment()` サポート  
*   プロパティの `requestId` サポート  
*   プロパティの `id` サポート  
*   メソッドのパラメーターの `complete()` 既定値が `result` " " から "unknown" に変更されました  

### サービス ワーカー  

[サービス ワーカーは](https://www.w3.org/TR/service-workers-1) 、Web ページのバックグラウンドで実行されるイベント駆動型スクリプトです。  サービス ワーカーは、ネットワークからの要求の傍受と処理、バックグラウンド同期の管理と処理、ローカル ストレージ、プッシュ通知など、ネイティブ アプリでのみ利用できる機能を有効にします。  サービス ワーカーのサポートはまだ開発中ですが、Microsoft Edge でサービス ワーカー機能を有効にすることで、試験的なサービス ワーカー サポートを使用して PWA をテストできます `about:flags` 。  

### WebVR  

Microsoft Edge の WebVR では、モーション コントローラーの [サポートが追加されました](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)。  これらのコントローラーは空間内の正確な位置を持ち、仮想現実のデジタル オブジェクトとの詳細な対話を可能にします。  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="モーション コントローラー" lightbox="../media/MotionControllers.jpg":::
   モーション コントローラー  
:::image-end:::  

WebVR は、2 種類のエクスペリエンスをサポートするために最適化されています。  

**Windows Mixed Reality PC** - 統合グラフィックスを備えたデスクトップとノート PC。  これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 60 フレームで実行されます。  
**Windows Mixed Reality 超小型 PC** - 個別のグラフィックスを搭載したデスクトップとノート PC。  これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 90 フレームで実行されます。  

どちらのセットアップでも、同じイマーシブビデオとゲーム エクスペリエンスがサポートされます。  

Windows Mixed Reality の今後の更新プログラムについて詳しくは [、Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) 休日の更新に関するブログ投稿をご覧ください。  

ガイドとデモについては [、WebVR 開発者ガイドにアクセスしてください](/microsoft-edge/webvr)。  

 > [!NOTE] 
 > WebVR 仕様はまだ開発中です。Microsoft Edge の実装は後で変更される可能性があります。  

## EdgeHTML 16 の新しい API  

EdgeHTML 16 の新しい API の完全な一覧を次に示します。  これらは次の形式で一覧表示されます `[interface name].[api name]` 。

> [!NOTE] 
> 以下の API は DOM で公開されていますが、一部の API のエンド エンドの動作はまだ開発中である可能性があります。  機能の  [サポートに関する公式](https://developer.microsoft.com/microsoft-edge/platform/status) の単語については、Microsoft Edge プラットフォームの状態を参照してください。  

---  

<iframe height='559' scrolling='no' title='EdgeHTML 16 の新しい API' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'>CodePen の <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'> EdgeHTML 16 by MSEdgeDev ( @MSEdgeDev ) の Pen New API </a> <a href='https://codepen.io/MSEdgeDev'> </a> を <a href='https://codepen.io'> 参照してください </a> 。</iframe>  

---  

## 以前の EdgeHTML リリース  

[EdgeHTML 12 / Windows ビルド 10240 (7/2015)](./edgehtml-12.md)  

[EdgeHTML 13 / Windows ビルド 10586 (11/2015)](./edgehtml-13.md)  

[EdgeHTML 14 / Windows ビルド 14393 (8/2016)](./edgehtml-14.md)  

[EdgeHTML 15 / Windows ビルド 15063 (4/2017)](./edgehtml-15.md)  
