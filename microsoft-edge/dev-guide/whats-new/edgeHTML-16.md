---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: このガイドでは、Microsoft Edge に含まれる開発者の機能と標準の概要を説明します。
title: EdgeHTML 16 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: a15888bc8c1314d61d436759e5d63be942174ea4
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941937"
---
# Microsoft EdgeHTML 16 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

[Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \(10/2017, ビルド 16299\)[の一部として、EdgeHTML 16 Web](https://blogs.windows.com/msedgedev/2017/10/17)プラットフォームで出荷された新機能と更新された機能の一覧を示します。  特定の Windows Insider Preview ビルドの変更内容については [、Microsoft Edge の変更履歴と](https://developer.microsoft.com/microsoft-edge/platform/changelog) [EdgeHTML の新機能を参照してください](../whats-new.md)。  

次の一覧を行うと、この機能が利用できます  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md) 。  

## 新機能と更新された機能  

### CSS グリッド レイアウト  

Microsoft Edge では、CSS グリッド レイアウトの先頭フィックスなし [の実装がサポートされるようになりました](https://www.w3.org/TR/css-grid-1)。  [グリッ](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) ド レイアウトは 2 次次のグリッドベース レイアウト システムを定義し、フロートやスクリプトを使用した位置よりもレイアウトのフラデリングが可能になります。  次の例では、CSS グリッド レイアウトを使用して、基本的な Web ページ用の構造を作成します。  

<iframe height='303' scrolling='no' title='CSS グリッド レイアウト' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'>CodePen の Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> CSS </a> <a href='https://codepen.io/MSEdgeDev'> グリッド レイアウト </a> @MSEdgeDev) <a href='https://codepen.io'> を参照してください </a> 。</iframe>  

### CSS オブジェクトに合うオブジェクト位置とオブジェクト位置  

Microsoft EdgeHTML 16 では、CSS のプロパティとサポートが追加 [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) されました [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position) 。  これらのプロパティは、置換されたコンテンツ ボックス内のコンテンツの位置とサイズを制御します。  

### 開発者ツール  

このリリースでは、強化された強力な機能とパフォーマンス向上のための主な Microsoft Edge DevTools の取り戻り機能を開始しました。 [また、Windows Insider ビルド](https://insider.windows.com) で今日の使用を開始できる新機能が数多く加えられました。  [変更内容の詳細については、Microsoft Edge DevTools](../whats-new.md)ガイドをご覧ください。  

### JavaScript  

[EdgeHTML 16 は、以前のリリースの Javascript パ](https://blogs.windows.com/msedgedev/2017/10/31)フォーマンス最適化に基するビルドで、キャクラエンド関数を Defer/re dedefer 関数の使用し、ブロック付きの関数を最適化 `try` / `finally` します。  

さらに、Microsoft EdgeHTML 15 で最初にプレビューした機能が、既定で有効になり、既定で有効になりました。  

#### 新機能  

既定でオン  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([デモ](https://webassembly.org/demo)\)  
*   [共有メモリとアトミックス](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### 支払い要求 API  

[支払要求 API は開発者](../windows-integration/payment-request-api.md)がクラウドに保存されているメッカー、コンシューマー、支払方法 \(クレジット カード\) 間の中間として機能する開いています。  Microsoft EdgeHTML 16 の API が最新の W3C [Payment Request API の指定と一致するように更新](https://w3c.github.io/payment-request) されました。  次のようなシナリオが考えられます。  

*   方法の `canMakePayment()` サポート  
*   プロパティの `requestId` サポート  
*   プロパティの `id` サポート  
*   メソッドのパラ `complete()` メーターの既定値 `result` は、"" から "不明" に変更されます。  

### サービス ワーカー  

[サービス ワーカーは](https://www.w3.org/TR/service-workers-1) 、Web ページのバックグラウンドで実行されるイベント ベースのスクリプトです。  サービスワーカーは、以前はネットワークから要求を取り消す、バックグラウンド同期の管理と取り付け、ローカル ストレージ、プッシュ通知など、以前はネイティブ アプリでのみ利用できます。  サービス ワーカーのサポートは現在開発中ですが、サービス ワーカー機能を有効にすることで、Microsoft Edge の実用サービス ワーカー サポートをテストすることができます `about:flags` 。  

### WebVR  

WebVR for Microsoft Edge では、モーション コントロー [ラーのサポートが追加されました](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)。  これらのコントローラーはスペースで正確な位置であり、仮想リアルティでデジタル オブジェクトとのやり取りをきれいにすることができます。  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="モーション コントローラー" lightbox="../media/MotionControllers.jpg":::
   モーション コントローラー  
:::image-end:::  

また、WebVR は、2 種類の異なるエクスペリエンスをサポートする最適化されています。  

**Windows Mixed Reality PC** - 統合グラフィック付きのデスクトップとノート PC。  これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 60 フレームで実行されます。  
**Windows Mixed Reality Ultra PC** - グラフィックとノート PC に、グラフィックが分けされたデスクトップやノート PC。  これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 90 フレームで実行されます。  

どちらのセットアップも、同じイマーシブ ビデオとゲーム エクスペリエンスをサポートします。  

以降の Windows Mixed Reality の更新プログラムの詳細については [、Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) の祝日の更新プログラムのブログを参照してください。  

ガイドやデモについては [、WebVR](/microsoft-edge/webvr)開発者ガイドを参照してください。  

 > [!NOTE] 
 > WebVR の速度は開発中であるため、Microsoft Edge の実装は後で行直す場合があります。  

## EdgeHTML 16 の新しい API  

EdgeHTML 16 の新しい API の完全な一覧を次に示します。  これらは形式で表示されます `[interface name].[api name]` 。

> [!NOTE] 
> 次の API は DOM で予定されていますが、一部の開発中のエンドツーエンド動作がまだあります。  機能サポート  [のコーサル語については、Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/status) プラットフォームの状態を参照してください。  

---  

<iframe height='559' scrolling='no' title='EdgeHTML 16 の新しい API' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>CodePen の EdgeHTML 16 の Pen New API </a> <a href='https://codepen.io/MSEdgeDev'> @MSEdgeDev </a> <a href='https://codepen.io'> 参照してください </a> 。</iframe>  

---  

## 以前の EdgeHTML リリース  

[Microsoft EdgeHTML 12 / Windows ビルド 10240 (7/2015)](./edgehtml-12.md)  

[Microsoft EdgeHTML 13 / Windows ビルド 10586 (2015/11)](./edgehtml-13.md)  

[EdgeHTML 14 / Windows ビルド 14393 (8/2016)](./edgehtml-14.md)  

[Microsoft EdgeHTML 15 / Windows ビルド 15063 (4/2017)](./edgehtml-15.md)  
