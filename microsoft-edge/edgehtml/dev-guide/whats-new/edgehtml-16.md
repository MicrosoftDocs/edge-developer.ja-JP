---
description: このガイドでは、EdgeHTML 16 に含まれる開発者の機能と標準の概要を説明します。
title: EdgeHTML 16 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
keywords: edge, Web 開発, html, css, javascript, developer
ms.openlocfilehash: e6ec2ec4a3152e9dfe73938784968fe3403d99cf
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399198"
---
# <a name="whats-new-in-edgehtml-16"></a>EdgeHTML 16 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

[Windows 10 Fall Creators Update \(10/2017,](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) Build 16299\) の一部として[、EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) Web プラットフォームに同梱されている新機能と更新された機能の一覧を次に示します。  特定の Windows Insider Preview ビルドの変更については [、「Microsoft Edge Changelog」](https://developer.microsoft.com/microsoft-edge/platform/changelog) および [「What's New in EdgeHTML」を参照してください](../whats-new.md)。  

次の変更の一覧の permalink を次に示します  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md) 。  

## <a name="new-and-updated-features"></a>新機能と更新された機能  

### <a name="css-grid-layout"></a>CSS グリッド レイアウト  

Microsoft Edge は、CSS グリッド レイアウトのプレフィックスのない [実装をサポートしています](https://www.w3.org/TR/css-grid-1)。  [グリッド レイアウトは](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) 2 次元のグリッド ベースのレイアウト システムを定義し、フロートまたはスクリプトを使用した配置を使用して、レイアウトの流動性を可能にします。  次の例では、CSS グリッド レイアウトを使用して、基本的な Web ページの構造を作成します。  

<iframe height='303' scrolling='no' title='CSS グリッド レイアウト' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'>CodePen の <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> </a> MSEdgeDev によるペン CSS グリッド レイアウト ( @MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> ) </a> <a href='https://codepen.io'> を参照してください </a> 。</iframe>  

### <a name="css-object-fit-and-object-position"></a>CSS オブジェクトフィットとオブジェクト位置  

EdgeHTML 16 では、CSS プロパティと . [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position)  これらのプロパティは、コンテンツ ボックス内で置き換えられたコンテンツの位置とサイズを制御します。  

### <a name="developer-tools"></a>開発者ツール  

このリリースでは、堅牢性とパフォーマンスを向上するための Microsoft Edge DevTools リファクタリングの主要な取り組みを開始し [、Windows Insider](https://insider.windows.com) ビルドで今日使い始める新機能も追加しました。  変更された情報 [の詳細については、Microsoft Edge DevTools](../whats-new.md) ガイドを参照してください。  

### <a name="javascript"></a>JavaScript  

[EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/31)は、以前のリリースの Javascript パフォーマンスの最適化を基に、Chakra エンジンが関数の延期/再延期、多態インライン キャッシュの使用、ブロックによる関数の最適化を行う機能を拡張します。 `try` / `finally`  

さらに、EdgeHTML 15 で最初にプレビューされた機能は、既定で安定して有効になっています。  

#### <a name="new-features"></a>新機能  

既定でオン  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([demo](https://webassembly.org/demo)\)  
*   [共有メモリとアトミック](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### <a name="payment-request-api"></a>支払い要求 API  

支払い [要求 API](../windows-integration/payment-request-api.md) は、ブラウザーがクラウドに保存したマーチャント、コンシューマー、支払い方法 \(クレジット カード\など) の間の仲介者としてブラウザーが機能するオープンなクロスブラウザー標準です。  EdgeHTML 16 の API は、最新の W3C 支払い要求 API 仕様に合 [わせて更新](https://w3c.github.io/payment-request) されました。  次のようなシナリオが考えられます。  

*   メソッドの `canMakePayment()` サポート  
*   プロパティの `requestId` サポート  
*   プロパティの `id` サポート  
*   メソッドのパラメーターの既定値が " `complete()` `result` " から "unknown" に変更されました  

### <a name="service-workers"></a>サービス ワーカー  

[Service Workers は](https://www.w3.org/TR/service-workers-1) 、Web ページのバックグラウンドで実行されるイベント駆動型スクリプトです。  サービス ワーカーは、ネットワークからの要求の傍受と処理、バックグラウンド同期、ローカル ストレージ、プッシュ通知の管理と処理など、以前はネイティブ アプリでのみ利用できる機能を有効にします。  サービス ワーカーのサポートはまだ開発中ですが、Microsoft Edge でサービス ワーカー機能を有効にすることで、Microsoft Edge で PWA をテストできます `about:flags` 。  

### <a name="webvr"></a>WebVR  

Microsoft Edge の WebVR では、モーション コントローラーの [サポートが追加されました](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)。  これらのコントローラーは空間内の正確な位置を持ち、仮想現実のデジタル オブジェクトとの詳細な対話を可能にします。  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="モーション コントローラー" lightbox="../media/MotionControllers.jpg":::
   モーション コントローラー  
:::image-end:::  

WebVR は、2 つの異なる種類のエクスペリエンスをサポートするために最適化されています。  

**Windows Mixed Reality PC** - 統合グラフィックスを備えたデスクトップとラップトップ。  これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 60 フレームで実行されます。  
**Windows Mixed Reality Ultra PC** - ディスクリート グラフィックスを備えるデスクトップとラップトップ。  これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 90 フレームで実行されます。  

どちらのセットアップも、同じイマーシブ ビデオとゲーム エクスペリエンスをサポートします。  

今後の Windows Mixed Reality 更新プログラムの詳細については [、Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) の休日の更新プログラムのブログ投稿を参照してください。  

ガイドとデモについては、WebVR 開発者ガイド [にアクセスしてください](/microsoft-edge/webvr)。  

 > [!NOTE] 
 > WebVR 仕様はまだ開発中ですから、Microsoft Edge の実装は後で変更される可能性があります。  

## <a name="new-apis-in-edgehtml-16"></a>EdgeHTML 16 の新しい API  

EdgeHTML 16 の新しい API の完全な一覧を次に示します。  これらはの形式で一覧表示されます `[interface name].[api name]` 。

> [!NOTE] 
> 次の API は DOM で公開されているが、一部のエンドツーエンドの動作はまだ開発中である可能性があります。  機能の [サポートに関する公式な単語については、「Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/status) プラットフォームの状態」を参照してください。  

---  

<iframe height='559' scrolling='no' title='EdgeHTML 16 の新しい API' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'>CodePen の <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'> EdgeHTML 16 </a> by MSEdgeDev ( @MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> ) のペンの新しい API </a> を <a href='https://codepen.io'> 参照してください </a> 。</iframe>  

---  

## <a name="previous-edgehtml-releases"></a>以前の EdgeHTML リリース  

[EdgeHTML 12 / Windows ビルド 10240 (2015/7)](./edgehtml-12.md)  

[EdgeHTML 13 / Windows ビルド 10586 (2015/11)](./edgehtml-13.md)  

[EdgeHTML 14 / Windows ビルド 14393 (2016/8)](./edgehtml-14.md)  

[EdgeHTML 15 / Windows ビルド 15063 (2017/4)](./edgehtml-15.md)  
