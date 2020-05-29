---
description: DOM ブレークポイントを使用して、ページのレイアウトに関するエラーを視覚的にデバッグする
title: DevTools-Elements-DOM ブレークポイント
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、elements、dom ブレークポイント、dom 変異
ms.custom: seodec18
ms.openlocfilehash: 4e9eab4727cf1c3ef74b69495dd972838985e589
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570481"
---
# DOM ブレークポイント

このウィンドウから DOM 変異のブレークポイントを管理します。これには、無効化、削除、再バインドなどが含まれます。

DOM 変異ブレークポイントを使用して、選択した要素ノードが変更されるたびにデバッガーを中断することができます。 これは、 *EdgeHTML*の各 450 + DOM api に個別のブレークポイントを設定しなくても、このような変更をトリガーできるコードを追跡するのに役立ちます。 

DOM ブレークポイントを設定するには、**要素**パネルの*HTML ツリービュー*で任意の要素を右クリックしてコンテキストメニューを開きます。

![DOM ブレークポイントコンテキストメニュー](../media/elements_dom_breakpoints_contextmenu.png)

次のいずれかのブレークポイントを設定することができます。

 - **ノードが削除されたときの中断**: 選択した要素がドキュメント (DOM ツリー) から削除されたときにデバッガーを中断します。

 - **サブツリーの中断**: 選択した要素の子孫 (追加、削除、またはサブツリーの変更) が変更されたときにデバッガーを中断します。 属性が変更された場合、この操作は中断されません (次のオプションを参照してください)。

 - **属性でのブレークの変更**: 選択した要素の属性が追加、削除、または値で変更されたときにデバッガーに中断します。

次に、[ **dom ブレークポイント**] ウィンドウに、選択した要素 (dom での場所を説明するセレクターを生成) と、設定したブレークポイントの種類 (*ノードの削除、サブツリー、変更*された属性) を一覧表示します。 ここでは、ブレークポイントを個別に再*バインド*、*無効化*、または削除することもできます ([rt] のコンテキストメニューから)。または、ボタンを使ってすべて一度に*削除*することもできます。

![DOM のブレークポイントウィンドウ](../media/elements_dom_breakpoints.png)

## ブレークポイントの永続性

ブレークポイントは、DevTools の設定の一部として格納されます (範囲内に設定されているページの URL が対象となります)。 ページを再読み込みしたとき、またはツールを閉じて再び開いたときに、DevTools はブレークポイントを関連付けられた要素にバインドします。

自動的に rebinded できないブレークポイントは、ブレークポイントの円に警告アイコンが表示されます。 そのためには、対応する要素が DOM に表示されるまで ([ブレークポイントの再**バインド**] ボタンとコンテキストメニューオプションを使用して)、要素を手動で再バインドするか、ブレークポイントを**削除**します。

![非連結ブレークポイントインジケーター](../media/elements_dom_breakpoint_unbound.png)

この*dom ブレークポイント*ウィンドウに加えて、**デバッガー**内から[dom ブレークポイント](../debugger.md#dom-breakpoints)を管理することもできます。

## 現在の制限事項

Edge の DevTools での DOM ブレークポイントのデバッグに関する次の制限事項に注意してください。

- エッジ DevTools では、現在、 [ `<iframe>` s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)内の再バインドブレークポイントがサポートされていません。 Iframe にブレークポイントを設定し、その後 Edge ツールを終了するか、ページを更新すると、ブレークポイントは失われます。

- DOM が完了する前に、スクリプトが同期的に実行されたブレークポイントを検出した場合 [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) 、デバッガーが一時停止されている間は dom ブレークポイントを設定することはできません。 通常 [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) は、またはスクリプト属性を設定することで、このような状況を解決でき [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) ます。

- 同期スクリプトの場合、イベントが呼び出されたときにブレークポイントの自動再バインドをトリガーし [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) ます。 この場合、DOM の最初のスクリプト駆動のビルド時にトリガーされるバインドブレークポイントを見逃してしまう可能性があります。 非同期スクリプトの場合、最初のスクリプトが実行される前に再バインドが行われ、必要に応じてブレークポイントが再バインドされ、トリガーされることがあります。
