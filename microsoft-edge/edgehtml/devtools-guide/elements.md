---
description: '[要素] パネルを使用して、ページの HTML、CSS、DOM、およびアクセシビリティを検査します。'
title: DevTools - 要素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 要素, html, css, dom ブレークポイント, イベント, アクセシビリティ
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 14052bc40b9f94e628f0b575ede6c1ca8ccf179a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234461"
---
# 要素

要素 **パネルは** 、次の操作を行うのに役立ちます。

* [現在のページの HTML ツリー内の要素を](#html-tree-view) 識別および編集する
* [ページ上の CSS (擬似](./elements/styles.md) 状態と擬似要素を含む) を検査および変更する
* [ページ上で発生する CSS レイアウトとスタイルカスケード](./elements/computed.md) について理解する
* [悪意のあるイベント ハンドラーを追跡して](./elements/events.md) デバッグできる
* [予期しない視覚的な変更が原因のコードに](./elements/dom-breakpoints.md) ジャンプするためにデバッグブレークポイントを設定する
* [ページで使用されるフォントと、](./elements/fonts.md) そのフォントの読み込み場所に関する詳細情報を取得する
* [スクリーン リーダーの視点から](./elements/accessibility.md) ページを表示し、アクセシビリティを確認してテストする 
* [ページの UI をデバッグする場合に加](./elements/changes.md) える CSS の変更の実行中の違いを確認する

## HTML ツリー ビュー

![Microsoft Edge DevTools 要素パネル](./media/elements.png)

1. Select**要素**( ) ツールを使用して、ページ内で要素をクリックして HTML ツリー ビュー `Ctrl+B` で要素を見つける。 ****

2. 要素の **強調表示** ( ) ツールを使用して、HTML ツリー ビューで要素をポイントして、ページ `Ctrl+Shift+L` **上の要素を検索します**。

3. 色の **選択 ()** ツールを開き、現在のページで使用されている色 `Ctrl+K` の一覧を表示します。 一覧の色をクリックすると、詳細 (色相、彩度、明度、アルファ) が表示されます。 [*スタイル*] ウィンドウで色の値の横にある色付き正方形をクリックすると、色**** の選択も開き、ページ要素の色を編集してすぐに結果を表示できます。

4. アクセシビリティ**ツリー** ( ) ボタンをクリックすると、[アクセシビリティ ツリー] ウィンドウが開き `Ctrl+Shift+A` [、Windows](https://support.microsoft.com/help/22798/windows-10-narrator-get-started)ナレーター スクリーンリーダーなどの支援技術に表示されるページの構造が表示されます。 [](./elements/accessibility.md)

5. また、HTML **ツリー** ビューで要素のタグ名、属性、またはテキスト コンテンツを検索して、要素 `Ctrl+F` を検索することもできます。

### 要素の編集

HTML ツリー ビュー内で要素を右クリックし、コンテキスト メニューから **[HTML** として編集] を選択すると、要素を編集できます。 コンテキスト メニューには、削除、切り取り、コピー、貼り付け、CSS 擬似クラス *(:active* *、:focus 、:hover* *、:visited)* の設定、属性の追加を行うオプションも用意されています。 ** 属性や値を編集するもう 1 つの方法は、HTML ツリー ビューからダブルクリックする方法です。

![HTML ツリー ビューのコンテキスト メニュー](./media/elements_html_tree_context.png)

> [!NOTE]
> HTML ツリーを編集しても、基になるソース マークアップには影響を与え得ない。 ページを更新すると、変更が元に戻り、ページ ソースによって決定されたレイアウトだけがレンダリングされます。 変更した**** HTML をクリップボードにコピーするには、目的の要素 (またはページ全体が必要な場合はグローバル要素) を右クリックして、コンテキスト メニューを `html` 開きます。 (**切り取** り **および貼り付** けオプションも使用できます)。

[スタイル [] ウィンドウから](./elements/styles.md) 、CSS 擬似状態と擬似要素を追加/削除/編集することもできます。

## ツール ウィンドウ

目的のページ要素を選択したら、ツール ウィンドウを使用して、さまざまなスタイルとアクセシビリティ プロパティをさらに調査し、そのイベント リスナーを表示し、DOM のブレークポイントを設定できます。

![[要素] パネルの [ツール] ウィンドウ](./media/elements_toolpanes.png)

1. [**スタイル**](./elements/styles.md): 現在適用されているスタイルをスタイルシート別に整理

2. [**計算:**](./elements/computed.md)現在適用されているスタイルを CSS 属性別に整理

3. [**イベント**](./elements/events.md): 現在の要素と先祖要素に登録されているイベント リスナー

4. [**DOM ブレークポイント**](./elements/dom-breakpoints.md): DOM のブレークポイント 

5. [**フォント**](./elements/fonts.md): 選択した要素に現在適用されているフォント

6. [**アクセシビリティ**](./elements/accessibility.md): アクセシビリティ プロパティ

7. [**変更**](./elements/changes.md): 診断セッション中に行われた CSS の変更  

## ショートカット

| 操作               | ショートカット               |
|:---------------------|:-----------------------|
| 要素パネル       | `Ctrl` + `1`           |
| 要素の強調表示 | `Ctrl` + `Shift` + `L` |
| Select 要素       | `Ctrl` + `B`           |
| カラー ピッカー         | `Ctrl` + `K`           |
| アクセシビリティ ツリー   | `Ctrl` + `Shift` + `A` |
