---
description: CSS Flexbox のデバッグサポート、Web ページのパフォーマンス ヘッドアップ表示、ツールの更新プログラムの発行など
title: DevTools の新機能 (Microsoft Edge 90)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4222bcf7284b69269691ec9fb78094e5efb95793
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408535"
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

フォーカス モードは、独自のデバッグ シナリオに基づいてさまざまなツールをグループ化できる実験的なインターフェイスです。  左側に**表示される新**しいアクティビティ バーには、レイアウトやデバッグなどの定義済みのツール**グループ****が含まれています**。  各ツール グループをカスタマイズするには、閉じる**\(** \) アイコンでツールを閉じるか、[その他のツール] \( \) アイコンを使用して新しいツール `X` を**** `+` 追加します。  

実験を有効にするには、[実験機能を[][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]有効にする] に移動し、[フォーカス モード] と **[DevTools ツール**ヒント] と [有効にする] + [ボタン] タブ メニューの横にあるチェック ボックスをオンにして、その他のツールを開**きます**。  この機能の詳細、または質問やアイデアをコメントするには [、DevTools: フォーカス モード UI に移動します][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]。  

:::image type="complex" source="../../media/2021/02/focus-mode.msft.png" alt-text="アクティビティ バーを表示する" lightbox="../../media/2021/02/focus-mode.msft.png":::
   アクティビティ バー **を表示する**  
:::image-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a>有益なツールヒントを使用した DevTools の詳細  

<!-- Title: DevTools Tooltips  -->  
<!-- Subtitle: Learn more about how to use DevTools with informative DevTools tooltips.  -->  

DevTools ツールヒント機能を使用すると、さまざまなツールとウィンドウについて学習できます。  DevTools のツールヒントを切り替えるには、アクティビティ バーの下部にあるヘルプ `?` \( \)**** アイコンを選択します。  ツールヒントがオンの場合は、DevTools のアウトライン領域にマウス ポインターを合わせると、ツールの使い方の詳細が確認できます。  実験を有効にするには、[実験機能を[][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]有効にする] に移動し、[フォーカス モード] と **[DevTools ツール**ヒント] と [有効にする] + [ボタン] タブ メニューの横にあるチェック ボックスをオンにして、その他のツールを開**きます**。  この機能の詳細、または質問やアイデアをコメントするには [、DevTools: フォーカス モード UI に移動します][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]。  

:::image type="complex" source="../../media/2021/02/focus-mode-and-tooltips-help.msft.png" alt-text="アクティビティ バーの [ヘルプ ] (?) アイコンを選択して、ヒントを表示する" lightbox="../../media/2021/02/focus-mode-and-tooltips-help.msft.png":::
   ヒントを表示するには、 `?` アクティビティ バーの****[ヘルプ \( \) アイコンを選択します。  
:::image-end:::  

## <a name="customize-keyboard-shortcuts-in-settings"></a>[設定] でキーボード ショートカットをカスタマイズする  

<!-- Title: Change keyboard shortcuts in Settings  -->  
<!-- TODO:  Rachel's feedback is about the fact that this experimental feature is turned on by default, may have separate section in What's New for experimental features)  -->  
<!-- Subtitle: Make DevTools work better for you by creating new keyboard shortcuts for any action in the DevTools.  -->  

これで、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。  キーボード ショートカットを編集するには、次の操作を実行します。  

1.  DevTools を開き、[設定のショートカット **]**  >  **を選択します**。  
1.  カスタマイズするアクションを選択します。  
1.  [編集] \(![[キーボード ショートカットの編集] アイコン](../../media/2021/02/edit-keyboard-shortcut-icon.msft.png)\) アイコン。  
1.  アクションにバインドするキーを選択します。  
1.  チェックマーク \( を選択します。![チェックマークのキーボード ショートカット アイコン](../../media/2021/02/checkmark-keyboard-shortcut-icon.msft.png)\) アイコン。  
    
ショートカットのカスタマイズと編集の詳細については [、「Microsoft Edge DevTools][DevtoolsCustomizeShortcuts]でキーボード ショートカットをカスタマイズする」に移動します。  Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新プログラムを確認するには、Issue [174309 に移動します][CR174309]。  

:::image type="complex" source="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png" alt-text="編集モードのショートカットを使用して、ショートカットの DevTools 設定でキーボード ショートカットをカスタマイズする" lightbox="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png":::
   編集モードのショートカットを使用して [、ショートカットの DevTools 設定][DevtoolsCustomizeIndexSettings] でキーボード ショートカットをカスタマイズする  
:::image-end:::  

## <a name="microsoft-edge-devtools-for-visual-studio-code-extension-update-114"></a>Microsoft Edge DevTools for Visual Studio コード拡張機能更新プログラム 1.1.4  

<!-- Title: Edge Devtools for Visual Studio code extension update 1.1.4  -->  
<!-- Subtitle: Latest changes including a favicon is displayed next to each of the instances and console messages from the browser are displayed in the console of Visual Studio Code.  -->  

Microsoft Visual Studio Code 拡張バージョン 1.1.4 用 Microsoft Edge Developer [Tools][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] for Microsoft Visual Studio Code では、各 DevTools インスタンスの横にファビコンが表示されます。  Microsoft Edge からのコンソール メッセージが、Microsoft の****[コードの出力] の下の**DevTools**コンソールにVisual Studioされます。  Microsoft Visual Studioコードは拡張機能を自動的に更新します。  バージョン 1.1.4 に手動で更新するには、[拡張機能を手動で更新 [する] に移動します][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。  [vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools] GitHub リポジトリで問題をファイルし、拡張機能に貢献することができます。  

:::row:::
   :::column span="":::
      次の図は、Microsoft Edge のコンソール ツールにログインしている Web **ページの例** からのメッセージを表示します。  
   :::column-end:::
   :::column span="":::
      次の図は **、DevTools**コンソールの [Microsoft コードの出力]**** でログに記録された web ページの例と同Visual Studioします。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png" alt-text="Microsoft Edge DevTools のコンソールにメッセージを表示する" lightbox="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png":::
         Microsoft Edge DevTools のコンソールにメッセージを表示する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png" alt-text="[Microsoft コードの出力] の下の DevTools コンソールに同じメッセージVisual Studioします。" lightbox="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png":::
         [Microsoft コードの出力] の下の DevTools コンソールに同じメッセージVisual Studioします。  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="improved-css-flexbox-editing-with-visual-flexbox-editor-and-multiple-overlays"></a>ビジュアル フレックスボックス エディターと複数のオーバーレイによる CSS flexbox 編集の改善  

<!-- Title: Try different CSS flexbox layouts with the visual flexbox editor  -->  
<!-- Subtitle: In the Styles pane, choose the icon that appears next to display: flex to try different layout properties for flex containers.  -->  

DevTools には、専用の CSS flexbox デバッグ ツールが追加されています。  HTML 要素に CSS スタイルを適用すると、要素ツールのその要素の横 `display: flex` `display: inline-flex` にアイコン `flex` が **表示** されます。  Web ページにフレックス オーバーレイを表示するには、アイコンを選択 `flex` します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issues [1166710][CR1166710] および [1175699][CR1175699]に移動します。  

:::row:::
   :::column span="":::
      **Flexbox エディターを開く**場合は、[**** スタイル] ウィンドウに移動し、スタイルの横にある新しいアイコン `display: flex` を選択 `display: inline-flex` します。  **Flexbox エディターでは、flexbox**プロパティを簡単に編集できます。  
   :::column-end:::
   :::column span="":::
      さらに、[レイアウト] **ウィンドウの [Flexbox]** **セクションには** 、Web ページ上のすべての flexbox 要素が表示されます。  各要素のオーバーレイを切り替えできます。  
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

以前は、要素ツールの DOM とは異なり、 **イニシエータ** ー ウィンドウのキーボードの矢印キーを使用して、要求のチェーンを展開または折 **りたたむ機能が使** えなくなっていました。  ネットワーク ツールでネットワーク要求を選択すると****、[**イニシエータ**ー] ウィンドウに、現在選択されている要求を開始した要求のチェーンが表示されます。  

Microsoft Edge バージョン 90 では、イニシエーター ウィンドウのキーボードの矢印キーを使用して、要求のチェーンを展開または **折りたたみ** できます。  チェーン内のフォーカスされたネットワーク要求も強調表示されます。  ネットワーク ツールのイニシエーターの詳細**** については、「イニシエーターと依存関係の[表示」に移動します][DevtoolsNetworkReferenceDisplayInitiatorsDependencies]。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issues [1158276][CR1158276] および [1160637][CR1160637]に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-request-initiator-chain.msft.png" alt-text="ネットワーク要求を選択し、[イニシエーター] ウィンドウを選択します。" lightbox="../../media/2021/02/network-request-initiator-chain.msft.png":::
         ネットワーク要求を選択し、[イニシエーター] ウィンドウ **を選択** します。  
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

コンソール サイドバーでフィルター [処理を行う場合][DevtoolsConsoleReferenceOpenConsoleSidebar]、[ログ レベル] ドロップダウン [のフィルターは][DevtoolsConsoleReferenceFilterByLogLevel] 使用できません。  以前は、[ **コンソール サイドバー] の** フィルターが選択されている間でも、その上にマウス ポインターを置くと、[ログ レベル] ドロップダウン **が** 強調表示されました。  Microsoft Edge バージョン 90**** では、[コンソール サイドバー] のフィルターが選択されている間に、その上にマウス ポインターを置くと、[ログ レベル] ドロップダウン**が強調表示され**なくなりました。  コンソールでのフィルター処理の詳細については、「 **メッセージ**のフィルター」 [に移動します][DevtoolsConsoleReferenceFilterMessages]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-old.msft.png" alt-text="以前は、[コンソール] サイドバーを開き、[既定のレベル] にカーソルを合わせると、強調表示されました" lightbox="../../media/2021/02/console-sidebar-default-levels-old.msft.png":::
         以前は、[コンソール] サイドバー **を開き** 、[既定のレベル] にカーソルを合 **わせると、** 強調表示されました  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-new.msft.png" alt-text="Microsoft Edge 90 から、コンソール サイドバーを選択し、既定のレベルにカーソルを合わせると、強調表示されません" lightbox="../../media/2021/02/console-sidebar-default-levels-new.msft.png":::
         Microsoft Edge 90 から、コンソール サイドバー**** を選択し、既定**** のレベルにカーソルを合わせると、強調表示されません  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="the-console-now-escapes-double-quote-characters"></a>コンソールで二重引用符をエスケープする  

以前は、コンソール **は JavaScript** 文字列の有効な二重引用符 \( `"` \) 文字を出力していなかった。  Microsoft Edge バージョン 90 から****、コンソールはエスケープされた二重引用符 \( \) 文字を使用して JavaScript 文字列 `"` を出力します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1178530 に移動します][CR1178530]。  

:::image type="complex" source="../../media/2021/02/console-string-formatted-double-quotes.msft.png" alt-text="コンソールは、エスケープされた二重引用符 (&#0022;) を使用して JavaScript 文字列を出力します。" lightbox="../../media/2021/02/console-string-formatted-double-quotes.msft.png":::
   コンソール **は、** エスケープされた二重引用符 \( \) 文字を使用して `"` JavaScript 文字列を出力します。  
:::image-end:::  

### <a name="emulate-the-css-color-gamut-media-feature"></a>CSS 色域メディア機能をエミュレートする  

色 [域メディア クエリは][ChromestatusFeature5354410980933632] 、ブラウザーとテスト中のデバイスでサポートされる色の概算範囲をエミュレートします。  [CSS メディア **機能の色域を** エミュレートする] のドロップダウンには、DevTools がエミュレートできる色空間が含まれます。  たとえば、メディア クエリをトリガー `color-gamut: p3` するには、ドロップダウンから **[色域: p3]** を選択します。  

CSS 色域メディア機能をエミュレートするには、次のアクションを実行します。  

1.  コマンド メニュー [を開きます][DevtoolsCommandMenuIndex]。  
1.  「`Rendering`」と入力します。  
1.  [レンダリングの **表示] コマンドを実行** します。  
1.  [CSS メディア **機能の色域をエミュレートする** ] に移動し、オプションを選択します。  

この機能の詳細については `color-gamut` 、「色の表示品質 [: "色域" 機能」 に移動します][CsswgDraftsMediaqueries4ColorGamut]。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issue [1073887 に移動します][CR1073887]。  

:::image type="complex" source="../../media/2021/02/rendering-css-color-gamut.msft.png" alt-text="CSS 色域メディア機能をエミュレートする" lightbox="../../media/2021/02/rendering-css-color-gamut.msft.png":::
   CSS 色域メディア機能をエミュレートする  
:::image-end:::  

### <a name="improved-progressive-web-apps-tooling"></a>プログレッシブ Web アプリのツールの改善  

#### <a name="pwa-installability-warning-in-the-console"></a>コンソールの PWA インストール可能性に関する警告  

コンソール **には、** プログレッシブ Web アプリのオフライン サポート検出の改善へのリンクを含む、より詳細なプログレッシブ Web アプリ [(PWA)][ProgressiveWebAppsIndex] インストール可能性の警告メッセージ [が表示されます][ChromeDeveloperBlogImprovedPwaOfflineDetection]。  

:::image type="complex" source="../../media/2021/02/console-pwa-installability.msft.png" alt-text="コンソール ツールでの PWA インストール可能性の警告" lightbox="../../media/2021/02/console-pwa-installability.msft.png":::
   コンソール ツールでの PWA インストール可能性 **の** 警告  
:::image-end:::  

#### <a name="pwa-description-length-warning-in-the-manifest-pane"></a>マニフェスト ウィンドウの PWA の説明の長さの警告

マニフェスト **の説明** が 324 文字を超えると、マニフェスト ウィンドウに警告メッセージが表示されます。  

:::image type="complex" source="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png" alt-text="PWA の説明の切り捨て警告" lightbox="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png":::
   PWA の説明の切り捨て警告  
:::image-end:::  

Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issues [965802][CR965802] [、1146450、および][CR1146450] [1169689][CR1169689]に移動します。  

### <a name="new-remote-address-space-column-in-the-network-tool"></a>[ネットワーク] ツールの [新しいリモート アドレス空間] 列  

<!-- does not work in canary 90.0.813.0 -->  
新しい **[リモート アドレス空間]** 列には、各ネットワーク リソースのネットワーク IP アドレス空間が表示されます。  新しい [リモート アドレス空間] 列を表示するには、次の操作を実行します。  

1.  [ネットワーク] ツール **に移動** します。  
1.  [要求] テーブルで、ヘッダー行にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開きます。  [要求] テーブルから列を追加または削除する方法については、「列の追加または削除 [」に移動します][DevtoolsNetworkReferenceAddRemoveColumns]。  
1.  [リモート **アドレス空間] を選択します**。  
    
Requests テーブルに、リモート アドレス空間という名前のヘッダーを含む新 **しい列が表示されます**。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1128885 に移動します][CR1128885]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png" alt-text="コンテキスト メニューで、[リモート アドレス空間] を選択します。" lightbox="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png":::
         コンテキスト メニューで、[リモート アドレス空間 **] を選択します。**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-remote-address-space.msft.png" alt-text="[要求] テーブルに [リモート アドレス空間] 列が表示される" lightbox="../../media/2021/02/network-requests-remote-address-space.msft.png":::
         [要求] テーブルに [リモート アドレス **空間] 列が表示** される :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-allowed-and-disallowed-features-in-the-frame-details-view"></a>[フレームの詳細] ビューに許可および禁止された機能を表示する  

[フレームの詳細] ビューに、アクセス許可ポリシーによって制御される許可および禁止されたブラウザー機能の一覧 [が表示されます][GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer]。  Permissions Policy は Web プラットフォーム API で、Web ページ内のブラウザー機能を個々のフレームまたは埋め込み iframe 内で使用できます。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1158827 に移動します][CR1158827]。  

:::image type="complex" source="../../media/2021/02/application-frames-permissions-policy.msft.png" alt-text="アクセス許可ポリシーに基づく許可機能と禁止機能" lightbox="../../media/2021/02/application-frames-permissions-policy.msft.png":::
   アクセス許可ポリシーに基づく許可機能と禁止機能  
:::image-end:::  

### <a name="new-sameparty-column-in-the-cookies-pane"></a>Cookie ウィンドウの新しい SameParty 列  

アプリケーション **ツールの** [Cookie] **ウィンドウ** に、各 `SameParty` Cookie の属性が表示されます。  この `SameParty` 属性は、Cookie が同じファースト パーティ セットの起点への要求に含まれているかどうかを示す新しいブール属性 [です][GithubPrivacycgFirstPartySets]。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1161427 に移動します][CR1161427]。  

:::image type="complex" source="../../media/2021/02/application-storage-cookies-sameparty.msft.png" alt-text="Cookie ウィンドウの SameParty 列" lightbox="../../media/2021/02/application-storage-cookies-sameparty.msft.png":::
   **Cookie ウィンドウの SameParty****列**  
:::image-end:::  

### <a name="fndisplayname-property-in-the-console-tool-is-now-deprecated"></a>コンソール ツールの fn.displayName プロパティが廃止されました  

以前は、 `fn.displayName` このプロパティを使用すると、DevTools スタック トレース内および DevTools スタック トレースに表示する関数のデバッグ名 `error.stack` を制御できます。  Microsoft Edge バージョン 90 から、このプロパティは廃止され、プロパティ `fn.displayName` に置き換 `fn.name` えられる予定です。  プロパティを定義 `Object.defineProperty` するには、標準のメソッドを使用 `fn.name` します。  詳細については、次 `fn.name` のページに[移動Function.name。][MdnJavascriptReferenceGlobalObjectsFunctionName]  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1177685 に移動します][CR1177685]。  

:::image type="complex" source="../../media/2021/02/console-display-name-name.msft.png" alt-text="関数のデバッグ名をfn.nameするプロパティの例" lightbox="../../media/2021/02/console-display-name-name.msft.png":::
   関数のデバッグ `fn.name` 名を制御するプロパティの例  
:::image-end:::  

### <a name="full-accessibility-tree-view-in-the-elements-tool"></a>要素ツールの完全なアクセシビリティ ツリー ビュー  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

この実験では、要素 **ツールでアクセシビリティ ツリー** ビュー全体を **提供** します。  [ [アクセシビリティ] ウィンドウ][DevtoolsAccessibilityReferenceTheAccessibilityPane] には部分的なアクセシビリティ ツリー ビューが表示され、ルート ノードから検査されたノードへの直接の先祖チェーンが表示されます。  
この実験を有効にし、DevTools を再読み込みした後、次のいずれかのボタンを選択して、Web ページ上のすべての要素の [要素] ツールの表示を切り替えます。  

*   完全なアクセシビリティ ツリー ビューを表示するには、[アクセシビリティ ツリーに切り替える **] ビューを選択します**。  
*   DOM ツリー ビューを表示するには、[DOM ツリーに切り替 **える] ビューを選択します**。  
    
実験を有効にするには、[実験機能を[][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]有効にする] に移動し、[要素] ウィンドウの [完全なアクセシビリティ ツリー ビューを有効にする] の横にあるチェック**ボックスをオンにします**。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [887173 に移動します][CR887173]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png" alt-text="DOM ツリー ビューを表示する" lightbox="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png":::
         DOM ビュー **を表示する**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png" alt-text="アクセシビリティ ツリービュー全体を表示する" lightbox="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png":::
         [完全 **なアクセシビリティ ツリー] ビューを表示する**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows、Linux、または macOS を使用している場合は、 [既定][MicrosoftEdgePreviewChannels] の開発ブラウザーとして Microsoft Edge プレビュー チャネルの使用を検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsAccessibilityReferenceTheAccessibilityPane]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#the-accessibility-pane "[アクセシビリティ] ウィンドウ - [アクセシビリティ] |Microsoft Docs"  
[DevtoolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行|Microsoft Docs"  
[DevtoolsConsoleReferenceFilterByLogLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "ログ レベルによるフィルター - コンソール参照|Microsoft Docs"  
[DevtoolsConsoleReferenceFilterMessages]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-messages "フィルター メッセージ - コンソール リファレンス |Microsoft Docs"  
[DevtoolsConsoleReferenceOpenConsoleSidebar]: /microsoft-edge/devtools-guide-chromium/console/reference#open-the-console-sidebar "コンソール サイドバー - コンソール リファレンス を開|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexEnablePlusButtonTabMenusToOpenMoreTools]: /microsoft-edge/devtools-guide-chromium/experimental-features/index#enable--button-tab-menus-to-open-more-tools "[+ ボタン] タブ メニューを有効にして、その他のツールを開く - 実験的な|Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features/index#turn-on-experimental-features "試験的機能を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsNetworkReferenceAddRemoveColumns]: /microsoft-edge/devtools-guide-chromium/network/reference#add-or-remove-columns "列の追加または削除 - ネットワーク分析の参照|Microsoft Docs"  
[DevtoolsNetworkReferenceDisplayInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/network/reference#display-initiators-and-dependencies "イニシエーターと依存関係の表示 - ネットワーク分析リファレンス |Microsoft Docs"  

[ProgressiveWebAppsIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上のプログレッシブ Web アプリの概要|Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 Marketplace |Visual Studioコード"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio コード |Visual Studio Marketplace"  

[ChromeDeveloperBlogImprovedPwaOfflineDetection]: https://developer.chrome.com/blog/improved-pwa-offline-detection "プログレッシブ Web アプリのオフライン サポート検出機能の|Chrome 開発者"  

[ChromestatusFeature5354410980933632]: https://www.chromestatus.com/feature/5354410980933632 "色域メディア クエリ |Chrome プラットフォームの状態"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "クロムのバグ"  
[CR174309]: https://crbug.com/174309 "問題 174309: DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium のバグ"  
[CR887173]: https://crbug.com/887173 "問題 887173: DevTools: 完全なアクセシビリティ ツリー検査|クロムのバグ"  
[CR965802]: https://crbug.com/965802 "Issue 965802: より正確なサービス ワーカーのオフライン機能検出機能を実装|クロムのバグ"  
[CR1073887]: https://crbug.com/1073887 "問題 1073887: DevTools: @media (色域: ...) カラースペース エミュレーション |クロムのバグ"  
[CR1128885]: https://crbug.com/1128885 "問題 1128885: DEVTools サポート for CORS-RFC1918 |クロムのバグ"  
[CR1146450]: https://crbug.com/1146450 "問題 1146450: [Android] 下部シートのインストールを実装|クロムのバグ"  
[CR1158276]: https://crbug.com/1158276 "問題 1158276: DevTools | の [ネットワーク] セクションの矢印キーを使用して [イニシエーター チェーンの要求] ウィンドウを展開/契約|クロムのバグ"  
[CR1158827]: https://crbug.com/1158827 "問題 1158827: [アクセス許可ポリシー] アクセス許可ポリシーの devtool サポートを実装|クロムのバグ"  
[CR1160637]: https://crbug.com/1160637 "問題 1160637: 'Request イニシエーター チェーン' にフォーカスが'Dev Tools' ウィンドウ の 'Network' セクションで不完全|クロム バグ"  
[CR1161427]: https://crbug.com/1161427 "問題 1161427: DevTools &#9730;で SameParty Cookie 属性のデバッグをサポート|クロムのバグ"  
[CR1166710]: https://crbug.com/1166710 "問題 1166710: 既定で flexbox ツールの実験を有効|クロムのバグ"  
[CR1169689]: https://crbug.com/1169689 "問題 1169689: PWA install bottom sheet should not feature categories |クロムのバグ"  
[CR1175699]: https://crbug.com/1175699 "問題 1175699: Flexbox エディター |クロムのバグ"  
[CR1177685]: https://crbug.com/1177685 "問題 1177685: 標準以外の fn.displayName サポート を削除|クロムのバグ"  
[CR1178530]: https://crbug.com/1178530 "問題 1178530: 文字列を印刷するときに、コンソールで二重引用符をエスケープ|クロムのバグ"  

[CsswgDraftsMediaqueries4ColorGamut]: https://drafts.csswg.org/mediaqueries-4#color-gamut "カラー表示の品質: "色域" 機能の|CSS ワーキング グループ エディターの下書き"  

[GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/main/DevTools/FocusMode/explainer.md "DevTools: フォーカス モード UI - MicrosoftEdge/MSEdgeExplainers |GitHub"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubPrivacycgFirstPartySets]: https://github.com/privacycg/first-party-sets "ファースト パーティ セット |GitHub"  

[GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer]: https://github.com/w3c/webappsec-permissions-policy/blob/main/permissions-policy-explainer.md "アクセス許可ポリシーの説明|GitHub"  

[MdnJavascriptReferenceGlobalObjectsFunctionName]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Function/name "Function.name |MDN"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2021/02/devtools/index)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
