---
description: DevTools のアクセシビリティ テスト機能Microsoft Edge一覧です。
title: DevTools のアクセシビリティテスト機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a906d60bb74d927fd86c21af1535a8f62eb93cad
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597035"
---
# <a name="accessibility-testing-features-in-devtools"></a>DevTools のアクセシビリティテスト機能

Web ページでアクセシビリティをテストするには、まずテストするアクセシビリティの側面のチェックリストを作成してから、関連する DevTools 機能を使用して各側面を確認します。

| 確認するアクセシビリティの側面 | DevTools の機能 | 記事または小頭書き |
|---|---|---|
| イメージに代替テキストが含まれています。 | **レポートの** [> **アクセシビリティ]** セクションの [問題] ツール | [イメージに代替テキストが含まれています。](test-issues-tool.md#verify-that-images-have-alt-text) |
| キーボードのサポートを確認する | **オーバーレイ** の [> **アクセシビリティ]** セクションを調す | [[検査] ツールを使用して、Web ページの上にカーソルを移動してアクセシビリティの問題を検出する](test-inspect-tool.md) |
| キーボードのサポートを確認する | `Tab`、 `Shift+Tab` および `Enter` キー | [Tab キーと Enter キーを使用してキーボードのサポートを確認する](test-tab-enter-keys.md) |
| キーボードのサポートを確認する: フォーカスが示されたかどうかを確認する | **ツール**、スタイル**タブ、** およびソース**ツールの検査** | [サイドバー メニューのキーボード フォーカスの表示不足を分析する](test-analyze-no-focus-indicator.md) |
| キーボードのサポートを確認する: フォーム ボタンがキーボードで使用できると確認する | **[要素**] ツール**のツール、DOM** **ツリー、および**[**イベント リスナー] タブの検査** | [フォームでのキーボードサポートの不足を分析する](test-analyze-no-keyboard-support.md) |
| キーボードのサポートを確認する: キー `Tab` の順序を確認する | **[要素** ] > **[アクセシビリティ]** タブ> **ソース オーダー ビューアー** | [ソース オーダー ビューアーを使用したキーボード サポートのテスト](test-tab-key-source-order-viewer.md) |
| テキストのコントラストが十分に高い (ページ全体に対して自動的に) 確認する | **レポートの** [> **アクセシビリティ]** セクションの [問題] ツール | [テキストの色に十分なコントラストが設定されているのを確認する](test-issues-tool.md#verify-that-text-colors-have-enough-contrast) |
| テキストのコントラストが十分に高い | **[要素** ] ツール> **[** スタイル] タブ> **カラー ピッカー** | [カラー ピッカーを使用してテキストと色のコントラストをテストする](color-picker.md) |
| テキストのコントラストが十分に高い | **[コントラスト** ] 行> **オーバーレイの** [アクセシビリティ] セクション> **ツールを検査** する | [[検査] ツールを使用して、Web ページの上にカーソルを移動してアクセシビリティの問題を検出する](test-inspect-tool.md) |
| テキストのコントラストが十分に高い:ホバー状態で確認する | **[要素** ] ツール> **[スタイル** ] タブ> **要素の状態を切り替える** | [要素のすべての状態のアクセシビリティを確認する](test-inspect-states.md) |
| テキストのコントラストが十分に高く、暗いテーマ (濃色モード) と明るいテーマを使用して確認します。 | **レンダリング** ツール > **CSS メディア機能の優先カラー スキームのエミュレート** | [暗いテーマと明るいテーマのコントラストの問題を確認する](test-dark-mode.md) |
| スクリーン リーダーのサポートを確認する: 入力フィールドにラベルが含まれています。 | **レポートの** [> **アクセシビリティ]** セクションの [問題] ツール | [入力フィールドにラベルが含まれています。](test-issues-tool.md#verify-that-input-fields-have-labels) |
| スクリーン リーダーのサポートを確認する | **[名前** と役割] > **オーバーレイ** の [アクセシビリティ] セクション> **ツールを** 検査 **する** | [[検査] ツールを使用して、Web ページの上にカーソルを移動してアクセシビリティの問題を検出する](test-inspect-tool.md) |
| スクリーン リーダーのサポートを確認する | **[アクセシビリティ** ツリー> **アクセシビリティ** ] タブ> **要素ツール** | [[アクセシビリティ ツリー] でキーボードと](test-accessibility-tree.md)スクリーン リーダーのサポートを確認し、[アクセシビリティ] タブを使用してアクセシビリティ [をテストする](accessibility-tab.md) |
| 色覚を持つユーザーが Web ページを使用できると確認する | **レンダリング** ツール > **表示の不足をエミュレートする** ドロップダウン リスト | [色覚を持つユーザーがページを使用できると確認する](test-color-blindness.md) |
| Web ページがぼやけたビジョンで使用できるのを確認する | **レンダリング** ツール > **表示の不足をエミュレートする** ドロップダウン リスト | [ページがぼやけたビジョンで使用できると確認する](test-blurred-vision.md) |
| WEB ページが UI アニメーションをオフにした状態で使用できる (モーションの縮小) を確認する | **レンダリング** ツール > **CSS メディア機能をエミュレートする** | [ページが UI アニメーションをオフにした状態で使用できる状態になっていることを確認する](test-reduced-ui-motion.md) |
| 狭い場合に Web ページ レイアウトが使用可能な場合を確認する | **デバイス エミュレーション** ツール | [Web ページ レイアウトが狭い場合に](accessibility-testing-in-devtools.md#verify-that-the-webpage-layout-is-usable-when-narrow)使用できると確認し[、DevTools でモバイル Microsoft Edgeエミュレートする](../device-mode/index.md) |


## <a name="see-also"></a>関連項目

*   [DevTools を使用したアクセシビリティ テストの概要][DevtoolsAccessibilityAccessibilitytestingindevtools]
*   [支援Microsoft Edge DevTools のナビゲーション][DevtoolsAccessibilityNavigation]
*   [アクセシビリティ テスト][DevtoolsAccessibilityTest]
*   [アクセシビリティの原則とベスト プラクティス][MDNAccessibility]
*   [スクリーン リーダー][MDNScreenReader]


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->  
[DevtoolsAccessibilityTest]: ../../accessibility/test.md "アクセシビリティテスト|Microsoft Docs"
[DevtoolsAccessibilityAccessibilitytestingindevtools]: accessibility-testing-in-devtools.md "DevTools を使用したアクセシビリティ テストの|Microsoft Docs"
[DevtoolsAccessibilityNavigation]: ./navigation.md "支援Microsoft Edgeを使用して DevTools に移動|Microsoft Docs"  
<!-- external -->
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "アクセシビリティ |MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "スクリーン リーダー |MDN"  
