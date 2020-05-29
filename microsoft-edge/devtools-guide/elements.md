---
description: '[要素] パネルを使用して、ページの HTML、CSS、DOM、アクセシビリティを検査します。'
title: DevTools-要素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、elements、html、css、dom ブレークポイント、イベント、アクセシビリティ
ms.custom: seodec18
ms.openlocfilehash: 8948ddb3291bd122521e0b0800c0113a576d49e4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570494"
---
# 要素

[**要素**] パネルでは、次の操作を行うことができます。

* 現在のページの[HTML ツリーの要素を識別および編集](#html-tree-view)する
* 擬似状態と擬似要素を含むページの[CSS を検査して変更](./elements/styles.md)する
* ページ上での[CSS レイアウトとスタイルのカスケードについて理解する](./elements/computed.md)
* デバッグできるように、[不正なイベントハンドラーを追跡](./elements/events.md)する
* [予期しない視覚的な変更に対してデバッグのブレークポイントを設定して](./elements/dom-breakpoints.md)、それを引き起こしているコードにジャンプします。
* [ページで使用され](./elements/fonts.md)ているフォントおよびその読み込み元の場所に関する詳細情報を取得する
* [スクリーンリーダーの視点からページを表示](./elements/accessibility.md)して、アクセシビリティを確認およびテストする 
* ページの UI をデバッグするときに加えた[CSS の変更の実行結果を確認](./elements/changes.md)する

## HTML ツリービュー

![Microsoft Edge DevTools 要素パネル](./media/elements.png)

1. **Select element** () ツールを使用し `Ctrl+B` て、ページ内の要素をクリックし、 **HTML ツリービュー**で要素を見つけます。

2. 要素の**強調**表示 ( `Ctrl+Shift+L` ) ツールを使って、 **HTML ツリービュー**の要素の上にマウスポインターを置くと、ページ上の要素を見つけることができます。

3. [**カラーピッカー** ] ( `Ctrl+K` ) ツールを開いて、現在のページで使用されている色の一覧を表示します。 リストの色をクリックすると、さらに詳細 (色相、鮮やかさ、明度、アルファ) が提供されます。 また、[**スタイル**] ウィンドウで色の値の横にある色付きの正方形をクリックすると、*カラーピッカー*が開き、ページ要素の色を編集してすぐに結果を表示できます。

4. [ **Accessibility tree** ( `Ctrl+Shift+A` )] ボタンをクリックすると、 [Windows ナレーター](https://support.microsoft.com/help/22798/windows-10-narrator-get-started)スクリーンリーダーなどの支援技術に表示されるページの構造が表示された [[アクセシビリティツリー](./elements/accessibility.md) ] ウィンドウが開きます。

5. **Find** `Ctrl+F` タグ名、属性、またはテキストの内容を検索することによって、HTML ツリービューで要素を検索することもできます。

### 要素の編集

HTML ツリービュー内で要素を右クリックし、コンテキストメニューから [ **html として編集**] を選択して要素を編集できます。 コンテキストメニューには、削除、切り取り、コピー、貼り付け、CSS 擬似クラス (*: active*、 *: focus*、 *: hover*、 *: アクセス*)、属性の追加のオプションも用意されています。 属性やその値を編集するもう1つの方法は、HTML ツリービューから属性をダブルクリックすることです。

![HTML ツリービューコンテキストメニュー](./media/elements_html_tree_context.png)

> [!NOTE]
> HTML ツリーを編集しても、基になるソースマークアップには影響しません。 ページを更新すると、変更が元に戻り、ページソースによって決定されたレイアウトのみが表示されます。 変更した HTML をクリップボードに**コピー**するには、目的の要素 (またはページ全体を表示する場合はグローバル要素) を右クリックして `html` コンテキストメニューを開きます。 ([**切り取り**] と [**貼り付け**] のオプションも使用できます)。

[[スタイル](./elements/styles.md)] ウィンドウでは、CSS の擬似状態と擬似要素の追加、削除、編集を行うこともできます。

## ツールウィンドウ

目的のページ要素を選択した後は、ツールウィンドウを使用して、その他のスタイルとアクセシビリティプロパティの検査、イベントリスナーの表示、DOM 変異ブレークポイントの設定を行うことができます。

![[要素] パネルの [ツール] ウィンドウ](./media/elements_toolpanes.png)

1. [**スタイル**](./elements/styles.md): 現在、スタイルシートによって整理されたスタイル

2. [**計算**](./elements/computed.md)済み: 現在、CSS 属性によって整理されたスタイル

3. [**イベント**](./elements/events.md): 現在の要素と先祖要素に登録されているイベントリスナー

4. [**Dom ブレークポイント**](./elements/dom-breakpoints.md): Dom 変異ブレークポイント 

5. [**フォント**](./elements/fonts.md): 選択した要素に対して現在適用されているフォント

6. [**アクセシビリティ**](./elements/accessibility.md): アクセシビリティプロパティ

7. [**変更**](./elements/changes.md): 診断セッション中に行われた CSS の変更  

## ショートカット

| 操作               | キー               |
|:---------------------|:-----------------------|
| 要素パネル       | `Ctrl` + `1`           |
| 要素の強調表示 | `Ctrl` + `Shift` + `L` |
| 要素を選ぶ       | `Ctrl` + `B`           |
| カラー ピッカー         | `Ctrl` + `K`           |
| アクセシビリティツリー   | `Ctrl` + `Shift` + `A` |
