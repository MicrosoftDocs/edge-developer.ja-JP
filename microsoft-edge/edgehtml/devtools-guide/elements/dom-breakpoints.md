---
description: DOM ブレークポイントを使用してページ上のレイアウトの不具合を視覚的にデバッグする
title: DevTools - 要素 - DOM のブレークポイント
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 要素, dom ブレークポイント, dom の変更
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb60fa0497c98c152ca2c5adf28e9dee5d7c9f98
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234626"
---
# DOM ブレークポイント

DOM のブレークポイントを無効、削除、再バインドなど、このウィンドウから管理します。

DOM のブレークポイントを使用すると、選択した要素ノードが変更されるたびにデバッガーにブレークポイントを割り込みます。 これは、このような変更をトリガーできる *EdgeHTML* の 450+ DOM API それぞれに個別のブレークポイントを設定することなく、UI で視覚的な不具合を引き起こす原因となるコードを追跡する場合に役立ちます。 

DOM のブレークポイントを設定するには、[要素] パネルの*****HTML*ツリー ビューで任意の要素を右クリックしてコンテキスト メニューを開きます。

![DOM ブレークポイントのコンテキスト メニュー](../media/elements_dom_breakpoints_contextmenu.png)

次のブレークポイントを設定できます。

 - **削除されたノードで**ブレーク : 選択した要素がドキュメント (DOM ツリー) から削除されると、デバッガーに割り込みます。

 - **変更されたサブツリー**でのブレーク : 選択した要素の子孫が変更された場合 (追加、削除、またはサブツリーが変更された場合) にデバッガーに割り込みます。 これは、属性が変更された場合に壊れる可能性はありません (その次のオプションを参照してください)。

 - **Break on Attribute modified:** Break into the debugger when an attribute of the selected element is added, removed or changed in value.

**DOM**のブレークポイント ウィンドウには、選択した要素 (DOM 内での位置を示すセレクターを生成) と、設定したブレークポイントの種類 (ノードの削除、サブツリーの変更、*属性*の変更) が一覧表示されます。 ここから、ブレークポイントを個別に**(rt-click コンテキスト** メニューから) 再バインド、無効化、または削除したり、または一度にすべて (ボタンを使用) することもできます。 **

![[DOM ブレークポイント] ウィンドウ](../media/elements_dom_breakpoints.png)

## ブレークポイントの永続性

ブレークポイントは、DevTools の設定の一部として格納されます (また、ブレークポイントが設定されているページの URL にスコープが設定されます)。 ページを再読み込みするか、ツールを閉じてから再度開くと、DevTools はブレークポイントを関連する要素に再バインドします。

自動的に再バインドできなかったブレークポイントは、ブレークポイント の円に警告アイコンで示されます。 このため、DOM に対応する要素が表示されたら ([再バインド**** されたブレークポイント] ボタンやコンテキスト メニュー オプションを使用して) 要素を手動で再バインドするのを待つ (ブレークポイント アイコンに警告インジケーターが**** 表示されなくなった) か、ブレークポイントを完全に削除することができます。

![非受信ブレークポイント インジケーター](../media/elements_dom_breakpoint_unbound.png)

この DOM のブレークポイント ウィンドウに *加* えて、デバッガー内から [DOM](../debugger.md#dom-breakpoints) のブレークポイントを管理 **することもできます**。

## 現在の制限事項

Edge DevTools での DOM ブレークポイント デバッグの次の制限事項に注意してください。

- Edge DevTools では、現在、ブレークポイント内のブレークポイントの再バインドはサポート[ `<iframe>` されていません](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)。 iframe にブレークポイントを設定して Edge DevTools を閉じるか、ページを更新すると、ブレークポイントは失われます。

- DOM が完了する前に同期的に実行されたブレークポイントがスクリプトで検出された場合、デバッガーが一時停止している間は DOM のブレークポイントを [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) 設定できません。 通常、この状況を解決するには、スクリプト属性 [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) またはスクリプト属性 [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) を設定します。

- 同期スクリプトの場合、イベントが呼び出されるとブレークポイントの自動再バインド [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) がトリガーされます。 この場合、DOM のスクリプト駆動型の初期ビルド時にトリガーされるバインド ブレークポイントが見つからない可能性があります。 非同期スクリプトの場合、最初のスクリプトが実行される前に再バインドの試行がトリガーされます。そのため、ブレークポイントが再バインドされ、必要に応じてトリガーされる可能性があります。
