---
description: CSS Flexbox のデバッグサポート、Web ページのパフォーマンス ヘッドアップ表示、ツールの更新プログラムの発行など
title: DevTools の新機能 (Microsoft Edge 90)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.localizationpriority: high
ms.openlocfilehash: a13c344bb31cdfb7d0402132e3be82e4c330c612
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597164"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-90"></a>DevTools の新機能 (Microsoft Edge 90)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="group-tools-together-in-focus-mode"></a>フォーカス モードでツールをグループ化する  

<!-- Title: Grouping the tools in Focus Mode  -->  
<!-- Subtitle: Organize your favorite tools into groups with the new Focus Mode UI.  -->  

フォーカス モードは、独自のデバッグ シナリオに基づいてさまざまなツールをグループ化できる試験的なインターフェイスです。  左側に表示される新しい**アクティビティ バー**には、**レイアウト**や**デバッグ**などの定義済みのツール グループが含まれています。  各ツール グループをカスタマイズするには、**閉じる**\(`X`\) アイコンでツールを閉じるか、**[その他のツール]** \(`+`\) アイコンを使用して新しいツールを追加します。  

試験を有効にするには、[[試験的機能を有効にする]][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] に移動し、**[フォーカス モード] と[DevTools ツールヒント]** と **[有効にする] + [ボタン] タブ メニューの横にあるチェック ボックスをオンにして、その他のツールを開きます**。  この機能の詳細、または質問やアイデアをコメントするには、[DevTools: フォーカス モード UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer] に移動します。  

:::image type="complex" source="../../media/2021/02/focus-mode.msft.png" alt-text="アクティビティ バーを表示する" lightbox="../../media/2021/02/focus-mode.msft.png":::
   **アクティビティ バー** を表示する  
:::image-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a>有益なツール ヒントを使用した DevTools の詳細  

<!-- Title: DevTools Tooltips  -->  
<!-- Subtitle: Learn more about how to use DevTools with informative DevTools tooltips.  -->  

DevTools ツール ヒント機能を使用すると、さまざまなツールとウィンドウについて学習できます。  DevTools のツールヒントを切り替えるには、**アクティビティ バー**の下部にあるヘルプ \(`?`\)アイコンを選択します。  ツールヒントがオンの場合は、DevTools のアウトライン領域にマウス ポインターを合わせると、ツールの使い方の詳細が確認できます。  試験を有効にするには、[[試験的機能を有効にする]][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] に移動し、**[フォーカス モード] と[DevTools ツールヒント]** と **[有効にする] + [ボタン] タブ メニューの横にあるチェック ボックスをオンにして、その他のツールを開きます**。  この機能の詳細、または質問やアイデアをコメントするには、[DevTools: フォーカス モード UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer] に移動します。  

:::image type="complex" source="../../media/2021/02/focus-mode-and-tooltips-help.msft.png" alt-text="アクティビティ バーの [ヘルプ ] (?) アイコンを選択して、ヒントを表示する" lightbox="../../media/2021/02/focus-mode-and-tooltips-help.msft.png":::
   ヒントを表示するには、**アクティビティ バー**の[ヘルプ \(`?`\) アイコンを選択します。  
:::image-end:::  

## <a name="customize-keyboard-shortcuts-in-settings"></a>[設定] でキーボード ショートカットをカスタマイズする  

<!-- Title: Change keyboard shortcuts in Settings  -->  
<!-- TODO:  Rachel's feedback is about the fact that this experimental feature is turned on by default, may have separate section in What's New for experimental features)  -->  
<!-- Subtitle: Make DevTools work better for you by creating new keyboard shortcuts for any action in the DevTools.  -->  

これで、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。  キーボード ショートカットを編集するには、次の操作を実行します。  

1.  DevTools を開き、**[設定]** > ** [ショートカット]** を選択します。  
1.  カスタマイズするアクションを選択します。  
1.  [編集] \(![[キーボード ショートカットの編集] アイコン](../../media/2021/02/edit-keyboard-shortcut-icon.msft.png)\) アイコン。  
1.  アクションにバインドするキーを選択します。  
1.  チェックマーク \( を選択します。![チェックマークのキーボード ショートカット アイコン](../../media/2021/02/checkmark-keyboard-shortcut-icon.msft.png)\) アイコン。  
    
ショートカットのカスタマイズと編集の詳細については、「[Microsoft Edge DevToolsでキーボード ショートカットをカスタマイズする][DevtoolsCustomizeShortcuts]」に移動します。  Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、Issue [174309][CR174309] に移動します。  

:::image type="complex" source="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png" alt-text="編集モードのショートカットを使用して、ショートカットの DevTools 設定でキーボード ショートカットをカスタマイズする" lightbox="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png":::
   編集モードのショートカットを使用して、ショートカットの [DevTools 設定][DevtoolsCustomizeIndexSettings] でキーボード ショートカットをカスタマイズする  
:::image-end:::  

## <a name="microsoft-edge-devtools-for-visual-studio-code-extension-update-114"></a>Microsoft Edge DevTools for Visual Studio Code 拡張機能更新プログラム 1.1.4  

<!-- Title: Edge Devtools for Visual Studio code extension update 1.1.4  -->  
<!-- Subtitle: Latest changes including a favicon is displayed next to each of the instances and console messages from the browser are displayed in the console of Visual Studio Code.  -->  

Microsoft Visual Studio Code 拡張バージョン 1.1.4 用 [Microsoft Edge Developer Tools for Microsoft Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] では、各 DevTools インスタンスの横にファビコンが表示されます。  Microsoft Edge からのコンソール メッセージが、**DevTools** コンソールの[Microsoft Visual Studio Code] の **[出力]** の下に表示されるようになりました。  Microsoft Visual Studio Code は拡張機能を自動的に更新します。  バージョン 1.1.4 に手動で更新するには、[[拡張機能を手動で更新する]][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually] に移動します。  [vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools] GitHub リポジトリで問題をファイルし、拡張機能に貢献することができます。  

:::row:::
   :::column span="":::
      次の図は、Microsoft Edge の**コンソール** ツールにログインしている Web ページの例からのメッセージを表示します。  
   :::column-end:::
   :::column span="":::
      次の図は、**DevTools コンソール**の [Microsoft Visual Studio Code の**出力**] に記録されたサンプル Web ページからの同じメッセージを示しています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png" alt-text="Microsoft Edge DevTools のコンソールにメッセージを表示する" lightbox="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png":::
         Microsoft Edge DevTools のコンソールにメッセージを表示する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png" alt-text="DevTools コンソールの [Microsoft Visual Studio Code の出力] の下に同じメッセージを表示します" lightbox="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png":::
         DevTools コンソールの [Microsoft Visual Studio Code の出力] の下に同じメッセージを表示します  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="improved-css-flexbox-editing-with-visual-flexbox-editor-and-multiple-overlays"></a>ビジュアル フレックスボックス エディターと複数のオーバーレイによる CSS flexbox 編集の改善  

<!-- Title: Try different CSS flexbox layouts with the visual flexbox editor  -->  
<!-- Subtitle: In the Styles pane, choose the icon that appears next to display: flex to try different layout properties for flex containers.  -->  

DevTools には、専用の CSS flexbox デバッグ ツールが追加されています。  `display: flex`または`display: inline-flex` CSS スタイルが HTML 要素に適用されている場合、**要素**ツールでその要素の横に`flex`アイコンが表示されます。  Web ページにフレックス オーバーレイを表示\(または非表示\) するには、`flex`アイコンを選択します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issues [1166710][CR1166710] および [1175699][CR1175699]に移動します。  

:::row:::
   :::column span="":::
      **Flexbox** エディターを開く場合は、**[スタイル]** ウィンドウに移動し、`display: flex` または `display: inline-flex` スタイルの横にある新しいアイコンを選択します。  **Flexbox** エディターでは、flexbox プロパティを簡単に編集できます。  
   :::column-end:::
   :::column span="":::
      さらに、**[レイアウト]** ウィンドウの **[Flexbox]** セクションには、Web ページ上のすべての flexbox 要素が表示されます。  各要素のオーバーレイを切り替えできます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-styles-display-flex-window.msft.png" alt-text="CSS flexbox デバッグ ツール" lightbox="../../media/2021/02/elements-styles-display-flex-window.msft.png":::
         CSS flexbox デバッグ ツール  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-layout-flexbox-flexbox-overlays.msft.png" alt-text="[レイアウト] ウィンドウの [Flexbox] セクション" lightbox="../../media/2021/02/elements-layout-flexbox-flexbox-overlays.msft.png":::
         **[レイアウト]** ウィンドウの **[Flexbox]** セクション  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="keyboard-navigation-improvements-for-network-requests"></a>ネットワーク要求のキーボード ナビゲーションの機能強化  

<!-- Title: Navigate the request initiator chain in the Network tool with the keyboard  -->  
<!-- Subtitle: The Initiator pane may now be expanded or collapsed with the arrow keys.  -->  

以前は、**要素**ツールの DOM とは異なり、**イニシエーター** ウィンドウのキーボードの矢印キーを使用して、要求のチェーンを展開または折りたたむ機能が使えなくなっていました。  **ネットワーク** ツールでネットワーク要求を選択すると、**[イニシエーター]** ウィンドウに、現在選択されている要求を開始した要求のチェーンが表示されます。  

Microsoft Edge バージョン 90 では、**イニシエーター** ウィンドウのキーボードの矢印キーを使用して、要求のチェーンを展開または折りたたみできます。  チェーン内のフォーカスされたネットワーク要求も強調表示されます。  **ネットワーク** ツールのイニシエーターの詳細については、「[イニシエーターと依存関係の表示][DevtoolsNetworkReferenceDisplayInitiatorsDependencies]」に移動します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issues [1158276][CR1158276] および [1160637][CR1160637]に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-request-initiator-chain.msft.png" alt-text="ネットワーク要求を選択し、[イニシエーター] ウィンドウを選択します。" lightbox="../../media/2021/02/network-request-initiator-chain.msft.png":::
         ネットワーク要求を選択し、**[イニシエーター]** ウィンドウを選択します。  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-request-initiator-chain-right-arrow-down-twice-down-arrow-thrice.msft.png" alt-text="要求開始チェーンを展開または折りたたみ、強調表示された行に従う" lightbox="../../media/2021/02/network-request-initiator-chain-right-arrow-down-twice-down-arrow-thrice.msft.png":::
         要求開始チェーンを展開または折りたたみ、強調表示された行に従う  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="filtering-in-the-console-is-more-consistent"></a>コンソールでのフィルター処理の整合性が高い  

<!-- Title: Console improvements make filtering more consistent  -->  
<!-- Subtitle: The Log Levels dropdown is more clearly disabled when using filters in the Console sidebar.  -->  

[コンソール サイドバー][DevtoolsConsoleReferenceOpenConsoleSidebar]でフィルター 処理を行う場合、[[ログ レベル]][DevtoolsConsoleReferenceFilterByLogLevel] ドロップダウン のフィルターは 使用できません。  以前は、**[コンソール サイドバー]** の フィルターが選択されている間でも、その上にマウス ポインターを置くと、**[ログ レベル]** ドロップダウン が 強調表示されました。  Microsoft Edge バージョン 90では、**[コンソール サイドバー]** のフィルターが選択されている間に、その上にマウス ポインターを置くと、**[ログ レベル]** ドロップダウンが強調表示されなくなりました。  [コンソール][DevtoolsConsoleReferenceFilterMessages]でのフィルター処理の詳細については、「**メッセージのフィルター**」に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-old.msft.png" alt-text="以前は、[コンソール] サイドバーを開き、[既定のレベル] にカーソルを合わせると、強調表示されました" lightbox="../../media/2021/02/console-sidebar-default-levels-old.msft.png":::
         以前は、**[コンソール] サイドバー**を開き、**[既定のレベル]** にカーソルを合わせると強調表示されました  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-new.msft.png" alt-text="Microsoft Edge 90 から、コンソール サイドバーを選択し、既定のレベルにカーソルを合わせると、強調表示されません" lightbox="../../media/2021/02/console-sidebar-default-levels-new.msft.png":::
         Microsoft Edge 90 から、**コンソール サイドバー**を選択し、**既定のレベル**にカーソルを合わせると、強調表示されません  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="the-console-now-escapes-double-quote-characters"></a>コンソールで二重引用符をエスケープする  

以前は、**コンソール**は JavaScript 文字列で有効な二重引用符 \(`"`\) 文字を出力しませんでした。  Microsoft Edge バージョン 90 から、**コンソール**はエスケープされた二重引用符 \(`"`\) 文字を使用して JavaScript 文字列を出力します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1178530][CR1178530] に移動します。  

:::image type="complex" source="../../media/2021/02/console-string-formatted-double-quotes.msft.png" alt-text="コンソールは、エスケープされた二重引用符 (&#0022;) を使用して JavaScript 文字列を出力します。" lightbox="../../media/2021/02/console-string-formatted-double-quotes.msft.png":::
   **コンソール**は、 エスケープされた二重引用符 \(`"`\) 文字を使用して JavaScript 文字列を出力します。  
:::image-end:::  

### <a name="emulate-the-css-color-gamut-media-feature"></a>CSS 色域メディア機能をエミュレートする  

[色域][ChromestatusFeature5354410980933632] メディア クエリは、ブラウザーとテスト中のデバイスでサポートされる色の概算範囲をエミュレートします。  **[CSS メディア 機能の色域をエミュレートする]** のドロップダウンには、DevTools がエミュレートできる色空間が含まれます。  たとえば、`color-gamut: p3`メディア クエリをトリガーするには、ドロップダウンから **[色域: p3]** を選択します。  

CSS 色域メディア機能をエミュレートするには、次のアクションを実行します。  

1.  [コマンド メニュー][DevtoolsCommandMenuIndex] を開きます。  
1.  「`Rendering`」と入力します。  
1.  **[レンダリングの 表示]** コマンドを実行 します。  
1.  **[CSS メディア 機能の色域をエミュレートする ]** に移動し、オプションを選択します。  

`color-gamut`この機能の詳細については、「[色の表示品質 : "色域" 機能][CsswgDraftsMediaqueries4ColorGamut]」に移動します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issue [1073887][CR1073887] に移動します。  

:::image type="complex" source="../../media/2021/02/rendering-css-color-gamut.msft.png" alt-text="CSS 色域メディア機能をエミュレートする" lightbox="../../media/2021/02/rendering-css-color-gamut.msft.png":::
   CSS 色域メディア機能をエミュレートする  
:::image-end:::  

### <a name="improved-progressive-web-apps-tooling"></a>プログレッシブ Web アプリのツールの改善  

#### <a name="pwa-installability-warning-in-the-console"></a>コンソールの PWA インストール可能性に関する警告  

**コンソール** には、 [プログレッシブ Web アプリのオフライン サポート検出の改善][ChromeDeveloperBlogImprovedPwaOfflineDetection]へのリンクを含む、より詳細な[プログレッシブ Web アプリ (PWA)][ProgressiveWebAppsIndex] インストール可能性の警告メッセージ が表示されます。  

:::image type="complex" source="../../media/2021/02/console-pwa-installability.msft.png" alt-text="コンソール ツールでの PWA インストール可能性の警告" lightbox="../../media/2021/02/console-pwa-installability.msft.png":::
   **コンソール** ツールでの PWA インストール可能性の警告  
:::image-end:::  

#### <a name="pwa-description-length-warning-in-the-manifest-pane"></a>マニフェスト ウィンドウの PWA の説明の長さの警告

**マニフェスト** の説明が 324 文字を超えると、マニフェスト ウィンドウに警告メッセージが表示されます。  

:::image type="complex" source="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png" alt-text="PWA の説明の切り捨て警告" lightbox="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png":::
   PWA の説明の切り捨て警告  
:::image-end:::  

Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [965802][CR965802]、[1146450][CR1146450]、および [1169689][CR1169689] に移動します。  

### <a name="new-remote-address-space-column-in-the-network-tool"></a>[ネットワーク] ツールの [新しいリモート アドレス空間] 列  

<!-- does not work in canary 90.0.813.0 -->  
新しい **[リモート アドレス空間]** 列には、各ネットワーク リソースのネットワーク IP アドレス空間が表示されます。  新しい [リモート アドレス空間] 列を表示するには、次の操作を実行します。  

1.  **[ネットワーク]** ツールに移動します。  
1.  [要求] テーブルで、ヘッダー行にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開きます。  [要求] テーブルから列を追加または削除する方法については、「[列の追加または削除][DevtoolsNetworkReferenceAddRemoveColumns]」に移動します。  
1.  **[リモート アドレス空間]** を選択します。  
    
Requests テーブルに、**[リモート アドレス空間]** という名前のヘッダーを含む新しい列が表示されます。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1128885][CR1128885] に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png" alt-text="コンテキスト メニューで、[リモート アドレス空間] を選択します。" lightbox="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png":::
         コンテキスト メニューで、**[リモート アドレス空間]** を選択します。  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-remote-address-space.msft.png" alt-text="[要求] テーブルに [リモート アドレス空間] 列が表示される" lightbox="../../media/2021/02/network-requests-remote-address-space.msft.png":::
         [要求] テーブルに **[リモート アドレス空間]** 列が表示される :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-allowed-and-disallowed-features-in-the-frame-details-view"></a>[フレームの詳細] ビューに許可および禁止された機能を表示する  

[[フレームの詳細]][GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer] ビューに、アクセス許可ポリシーによって制御される許可および禁止されたブラウザー機能の一覧が表示されます。  アクセス許可ポリシーは Web プラットフォーム API で、Web ページ内のブラウザー機能を個々のフレームまたは埋め込み iframe 内で使用できます。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1158827][CR1158827] に移動します。  

:::image type="complex" source="../../media/2021/02/application-frames-permissions-policy.msft.png" alt-text="アクセス許可ポリシーに基づく許可機能と禁止機能" lightbox="../../media/2021/02/application-frames-permissions-policy.msft.png":::
   アクセス許可ポリシーに基づく許可機能と禁止機能  
:::image-end:::  

### <a name="new-sameparty-column-in-the-cookies-pane"></a>Cookie ウィンドウの新しい SameParty 列  

**アプリケーション** ツールの **[Cookie]** ウィンドウ に、各 Cookie の `SameParty` 属性が表示されます。  この `SameParty` 属性は、Cookie が同じ[ファースト パーティ セット][GithubPrivacycgFirstPartySets]の起点への要求に含まれているかどうかを示す新しいブール属性 です。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1161427][CR1161427] に移動します。  

:::image type="complex" source="../../media/2021/02/application-storage-cookies-sameparty.msft.png" alt-text="Cookie ウィンドウの SameParty 列" lightbox="../../media/2021/02/application-storage-cookies-sameparty.msft.png":::
   **Cookie** ウィンドウの **SameParty** 列  
:::image-end:::  

### <a name="fndisplayname-property-in-the-console-tool-is-now-deprecated"></a>コンソール ツールの fn.displayName プロパティが廃止されました  

以前は、`fn.displayName` プロパティを使用して、`error.stack` および DevTools スタック トレースに表示する関数のデバッグ名を制御できました。  Microsoft Edge バージョン90以降、`fn.displayName` プロパティは非推奨になり、`fn.name` プロパティに置き換えられました。  標準の`Object.defineProperty`メソッドを使用して`fn.name`プロパティを定義します。  `fn.name` の詳細については、[Function.name][MdnJavascriptReferenceGlobalObjectsFunctionName] に移動してください。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1177685][CR1177685] に移動します。  

:::image type="complex" source="../../media/2021/02/console-display-name-name.msft.png" alt-text="関数のデバッグ名を制御するための fn.name プロパティの例" lightbox="../../media/2021/02/console-display-name-name.msft.png":::
   関数のデバッグ名を制御するための `fn.name` プロパティの例  
:::image-end:::  

### <a name="full-accessibility-tree-view-in-the-elements-tool"></a>要素ツールの完全なアクセシビリティ ツリー ビュー  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

この実験では、**要素** ツールで**アクセシビリティ ツリー ビュー全体**を提供します。  [[アクセシビリティ]][DevtoolsAccessibilityTab] ウィンドウ には部分的なアクセシビリティ ツリー ビューが表示され、ルート ノードから検査されたノードへの直接の祖先チェーンが表示されます。  
この実験を有効にし、DevTools を再読み込みした後、次のいずれかのボタンを選択して、Web ページ上のすべての要素の [要素] ツールの表示を切り替えます。  

*   完全なアクセシビリティ ツリー ビューを表示するには、**[アクセシビリティ ツリーに切り替える]** ビューを選択します。  
*   DOM ツリー ビューを表示するには、**[DOM ツリー ビューに切り替える]** ビューを選択します。  
    
試験を有効にするには、[[試験的機能を有効にする]][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] に移動し、[要素] ウィンドウの **[完全なアクセシビリティ ツリー ビューを有効にする]** の横にあるチェックボックスをオンにします。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [887173][CR887173] に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png" alt-text="DOM ツリー ビューを表示する" lightbox="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png":::
         **DOM ツリー ビュー**を表示する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png" alt-text="アクセシビリティ ツリービュー全体を表示する" lightbox="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png":::
         **[完全なアクセシビリティ ツリー]** ビューを表示する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows、Linux、または macOS を使用している場合は、 既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]の使用を検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsAccessibilityTab]: ../../../accessibility/accessibility-tab.md "[アクセシビリティ] タブを使用してアクセシビリティをテスト | Microsoft Docs"  
[DevtoolsCommandMenuIndex]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行する | Microsoft Docs"  
[DevtoolsConsoleReferenceFilterByLogLevel]: ../../../console/reference.md#filter-by-log-level "ログ レベルによるフィルター - コンソール リファレンス | Microsoft Docs"  
[DevtoolsConsoleReferenceFilterMessages]: ../../../console/reference.md#filter-messages "フィルター メッセージ - コンソール リファレンス | Microsoft Docs"  
[DevtoolsConsoleReferenceOpenConsoleSidebar]: ../../../console/reference.md#open-the-console-sidebar "コンソール サイドバーを開く - コンソール リファレンス | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: ../../../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: ../../../customize/shortcuts.md "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexEnablePlusButtonTabMenusToOpenMoreTools]: ../../../experimental-features/index.md#enable--button-tab-menus-to-open-more-tools "[+] ボタン タブ メニューを有効にして、その他のツールを開く - 試験的な| Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: ../../../experimental-features/index.md#turn-on-experimental-features "試験的機能を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsNetworkReferenceAddRemoveColumns]: ../../../network/reference.md#add-or-remove-columns "列の追加または削除 - ネットワーク分析リファレンス | Microsoft Docs"  
[DevtoolsNetworkReferenceDisplayInitiatorsDependencies]: ../../../network/reference.md#display-initiators-and-dependencies "イニシエーターと依存関係の表示 - ネットワーク分析リファレンス | Microsoft Docs"  

[ProgressiveWebAppsIndex]: ../../../../progressive-web-apps-chromium/index.md "Windows 上のプログレッシブ Web アプリの概要 | Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 マーケットプレース | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  

[ChromeDeveloperBlogImprovedPwaOfflineDetection]: https://developer.chrome.com/blog/improved-pwa-offline-detection "プログレッシブ Web アプリのオフライン サポート検出の改善 | Chrome 開発者"  

[ChromestatusFeature5354410980933632]: https://www.chromestatus.com/feature/5354410980933632 "色域メディア クエリ | Chrome プラットフォーム ステータス"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  
[CR174309]: https://crbug.com/174309 "問題 174309: DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium のバグ"  
[CR887173]: https://crbug.com/887173 "問題 887173: DevTools: 完全なアクセシビリティ ツリーの検査 | Chromium のバグ"  
[CR965802]: https://crbug.com/965802 "問題 965802: より正確な Service Worker のオフライン機能検出を実装する | Chromium のバグ"  
[CR1073887]: https://crbug.com/1073887 "問題 1073887: DevTools: @media (color-gamut: ...) 色空間エミュレーション | Chromium のバグ"  
[CR1128885]: https://crbug.com/1128885 "問題 1128885: CORS の DevTools サポート - RFC1918 | Chromium のバグ"  
[CR1146450]: https://crbug.com/1146450 "問題 1146450: [Android] ボトムシートのインストールを実装する | Chromium のバグ"  
[CR1158276]: https://crbug.com/1158276 "問題 1158276: DevTools | の [ネットワーク] セクションの矢印キーを使用して [イニシエーター チェーンの要求] ウィンドウを展開/契約する | クロムのバグ"  
[CR1158827]: https://crbug.com/1158827 "問題 1158827: [アクセス許可ポリシー] アクセス許可ポリシーの devtool サポートを実装する | Chromium のバグ"  
[CR1160637]: https://crbug.com/1160637 "問題 1160637: 「開発ツール」ウィンドウの「ネットワーク」セクションで「リクエスト イニシエーター チェーン」へのフォーカスが不完全であることがわかる | Chromium のバグ"  
[CR1161427]: https://crbug.com/1161427 "問題1161427: &#9730; DevTools でSame Party Cookie 属性のデバッグをサポートする | Chromium のバグ"  
[CR1166710]: https://crbug.com/1166710 "問題 1166710: デフォルトで flexbox ツールの実験を有効にする | Chromium のバグ"  
[CR1169689]: https://crbug.com/1169689 "問題 1169689: PWA インストールのボトム シートにカテゴリを含めるべきではない | Chromium のバグ"  
[CR1175699]: https://crbug.com/1175699 "問題 1175699: Flexbox エディター | Chromium のバグ"  
[CR1177685]: https://crbug.com/1177685 "問題 1177685: 標準以外の fn.displayName サポート を削除する | Chromium のバグ"  
[CR1178530]: https://crbug.com/1178530 "問題 1178530: 文字列を印刷するときにコンソールが二重引用符をエスケープしない | Chromium のバグ"  

[CsswgDraftsMediaqueries4ColorGamut]: https://drafts.csswg.org/mediaqueries-4#color-gamut "カラー表示品質：「色域」機能 | CSS ワーキング グループ エディター ドラフト"  

[GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/main/DevTools/FocusMode/explainer.md "DevTools: フォーカス モード UI - MicrosoftEdge/MSEdgeExplainers | GitHub"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubPrivacycgFirstPartySets]: https://github.com/privacycg/first-party-sets "ファーストパーティ セット | GitHub"  

[GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer]: https://github.com/w3c/webappsec-permissions-policy/blob/main/permissions-policy-explainer.md "アクセス許可ポリシーの説明| GitHub"  

[MdnJavascriptReferenceGlobalObjectsFunctionName]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Function/name "Function.name | MDN"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developer.chrome.com/blog/new-in-devtools-90)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
