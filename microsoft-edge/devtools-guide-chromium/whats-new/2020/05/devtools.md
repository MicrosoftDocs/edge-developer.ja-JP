---
description: ハイ コントラスト モードで DevTools をWindows、DevTools のキーボード ショートカットを一致Visual Studio Codeなどです。
title: DevTools の新機能 (Microsoft Edge 84)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2537495ad14462aac70bfb1b5873aaa0b6e21cdf
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564673"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-84"></a>DevTools の新機能 (Microsoft Edge 84)  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームからのお知らせ  

以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。  DevTools、コード拡張機能、その他の新機能を試Microsoft Visual Studioお知らせをご覧ください。  開発者ツールのすべての最新および最大の機能を最新の情報に更新するには、プレビュー チャネルMicrosoft Edge[][MicrosoftEdgePreviewChannels]ダウンロードし[、Twitter][EdgeDevToolsTwitterAccount]でフォローしてください。  

### <a name="use-the-devtools-in-windows-high-contrast-mode"></a>ハイ コントラスト モードで DevTools をWindowsする

このMicrosoft Edge DevTools がハイ コントラスト モードの場合、Windowsハイ コントラスト モードで表示されます。  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="ハイ コントラスト Microsoft Edge DevTools の機能" lightbox="../../media/2020/05/high-contrast.msft.png":::
   ハイ コントラスト Microsoft Edge DevTools の機能  
:::image-end:::  

[手順に従って、ハイ コントラスト][MicrosoftSupportWindows10HighContrastMode]モードをオンWindows。  アプリケーションで DevTools を開Microsoft Edgeまたはを `F12` 選択します `Ctrl` + `Shift` + `I` 。  DevTools はハイ コントラスト モードで表示されます。  

> [!NOTE]
> DevTools Microsoft Edgeは現在、macOS 上ではなく、Windowsハイ コントラスト モードをサポートしています。  

Chromium[問題#1048378][CR1048378]  

### <a name="match-keyboard-shortcuts-in-the-devtools-to-visual-studio-code"></a>DevTools のキーボード ショートカットを Visual Studio Code と一致させる  

フィードバックと[パブリック](#getting-in-touch-with-microsoft-edge-devtools-team)Chromiumトラッカー[][CRIssuesList]から、Microsoft Edge DevTools チームは、DevTools でキーボード ショートカットをカスタマイズする機能が必要なことを学習しました。  このMicrosoft Edge 84 では[、DevTools][VisualStudioCodeMain]のキーボード ショートカットを Visual Studio Code に一致できます。これは、チームがショートカットのカスタマイズに取り組む機能の 1 つにすすむ機能の 1 つです。  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="DevTools のキーボード ショートカットを Visual Studio Code と一致させる" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   ハイ コントラスト Microsoft Edge DevTools の機能  
:::image-end:::  

実験を試す場合は、DevTools 設定 の右上隅にある Devtools 設定 アイコンアイコンを選択または選択して `?` ![ 、DevTools 設定 を開 ](../../../media/settings-icon.msft.png) きます。  [実験] セクション **に移動し、[** カスタム キーボード ショートカット設定を有効にする] タブ (再読み込 **みが必要) をオンにします**。  DevTools を再読み込みし、設定開き、[ショートカット]**セクションに移動**します。  

[**プリセットからショートカットを一致する] ドロップダウンで [DevTools( Default)** ] を選択し、[既定] Visual Studio Code を**選択します**。 ****  DevTools のキーボード ショートカットが、同じ操作のショートカットと一致Visual Studio Code。  

たとえば、[Visual Studio Code][VisualStudioCodeShortcuts] でスクリプトを一時停止または実行し続けるためのキーボード ショートカットは `F5` です。  **DevTools (Default)** プリセットを使用すると、DevTools の同じショートカットが、Visual Studio Codeプリセットと同じショートカットになります。 `F8` **** `F5`  

この機能は現在、Microsoft Edge 84 で使用できますので、チームとフィードバック[を](#getting-in-touch-with-microsoft-edge-devtools-team)共有してください。  

Chromium の問題 [#174309][CR174309]  

### <a name="remote-debug-surface-duo-emulators"></a>リモート デバッグ Surface Duo エミュレーター  

これで、Surface Duo エミュレーターで実行されている Web コンテンツを[、DevTools][DualScreensAndroidEmulator]のフル パワーを使用してリモート[でデバッグMicrosoft Edgeできます][DevtoolsIndex]。  

Surface [Duo エミュレーターを使用][DualScreensAndroidEmulator]すると、折りたたみ可能なデュアルスクリーン デバイスの新しいクラスで Web コンテンツがどのようにレンダリングされるのかテストできます。  エミュレーターは Android オペレーティング システムを実行し、Android アプリMicrosoft Edge[提供します][AndroidEdge]。  Web コンテンツをアプリに読みMicrosoft Edge [DevTools][DevtoolsIndex]でデバッグMicrosoft Edgeします。 [][AndroidEdge]  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="Surface Duo Microsoft Edgeで実行されているアプリの一部" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   Surface Duo Microsoft Edgeのアプリ  
:::image-end:::  

Surface Duo エミュレーターで実行Microsoft Edge開いているタブまたは PWA の一覧を含む `edge://inspect` [][DesktopEdge]**SurfaceDuoEmulator**が表示されるデスクトップ インスタンス[][PwaIndex][の][DualScreensAndroidEmulator]ページです。  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="[edge://inspect] ページには、エミュレーターで実行されているアプリMicrosoft Edgeタブの一覧が表示されます。" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   この `edge://inspect` ページには、エミュレーターで実行されているアプリMicrosoft Edgeタブの一覧が表示されます。
:::image-end:::  

デバッグ**する**タブまたはデバッグするPWAを調Microsoft Edge[選択します][DevtoolsIndex]。  Surface Duo エミュレーターで Web コンテンツをリモートでデバッグするには、ステップ[バイ ステップ ガイドに従います][DevtoolsRemoteDebugDuoEmulator]。  

### <a name="resize-the-devtools-drawer-more-easily"></a>DevTools ドロワーのサイズを簡単に変更する  

83 Microsoft Edge以前のバージョンでは、ドロワーのツールバー内をホバリングして[Devtools ドロ][DevtoolsDrawer]ワーのサイズを変更するのみ可能でした。  ドロワーの動作は、DevTools 内のペインの他のサイズ変更コントロールとは異なって動作し、ウィンドウの枠線にマウス ポインターを移動してサイズを変更しました。  次の画像を選択すると、ドロワーのサイズ変更がバージョン 83 以前のバージョンでどのように機能Microsoft Edge。  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="DevTools ドロワーのサイズ変更 (Microsoft Edge 83)" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   DevTools ドロワーのサイズ変更 (Microsoft Edge 83)
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

84 Microsoft Edgeから、ドロワーの枠線にカーソルを合わせて、ドロワーのサイズを変更できます。  この変更により、DevTools ドロワーのサイズを変更する動作と、DevTools 内の他のウィンドウのサイズを変更する方法が揃います。  次の画像を選択して、84 のサイズ変更をMicrosoft Edgeします。  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="DevTools ドロワーのサイズ変更 (Microsoft Edge 84)" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   DevTools ドロワーのサイズ変更 (Microsoft Edge 84)
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

Chromium[問題#1076112][CR1076112]  

### <a name="screencasting-navigation-buttons-display-focus"></a>スクリーン キャスト ナビゲーション ボタンにフォーカスが表示される  

[Android][DevtoolsRemoteDebugAndroid]デバイス[、Windows 10][DevtoolsRemoteDebugWindows]デバイス、[または Surface Duo][DevtoolsRemoteDebugDuoEmulator]エミュレーターをリモート デバッグする場合は ![ 、DevTools の左上隅にある [画面キャストの切り替え] アイコンを使用してスクリーン キャストを切り替えられます。 ](../../../media/toggle-screencast-icon.msft.png)  スクリーンキャストが有効になっている場合は、リモート デバイスMicrosoft Edge DevTools ウィンドウからタブを移動できます。  84 Microsoft Edge、これらのナビゲーション ボタンはキーボードでもアクセス可能です。  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="スクリーン キャストされた URL バーから [Shift+ Tab] を選択すると、[更新] ボタンにフォーカスが表示されます" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   スクリーン `Shift` + `Tab` キャストされた URL バーから選択すると、[更新] ボタンにフォーカスが**表示**されます
:::image-end:::  

Chromium[問題#1081486][CR1081486]  

### <a name="network-panel-details-pane-is-now-accessible"></a>ネットワーク パネルの [詳細] ウィンドウにアクセス可能  

84 Microsoft Edgeでは、ネットワーク ログ[][DevtoolsNetworkDetails]でリソースを開**** く際に、[ネットワーク] ツールの [詳細] ウィンドウにフォーカス[が集中します][DevtoolsNetworkLog]。  この変更により、スクリーン リーダーは詳細ウィンドウのコンテンツを読み取り、 **操作** できます。  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text="[ネットワーク] パネルの [詳細] ウィンドウが開いたときにフォーカスを受け取る" lightbox="../../media/2020/05/network-details.msft.png":::
   ネットワーク **ツールの** [詳細] **ウィンドウが** 開いたときにフォーカスを受け取る
:::image-end:::  

Chromium[の問題][CR963183]#963183  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

次のセクションでは、プロジェクトのオープン ソースにMicrosoft Edgeされた 84 で利用可能な追加のChromiumします。  

### <a name="fix-site-issues-with-the-new-issues-tool-in-the-devtools-drawer"></a>DevTools ドロワーの新しい Issues ツールでサイトの問題を修正する

**DevTools ドロワー**の新しい問題ツールは、コンソールの通知の疲労と混乱を軽減するために構築**されました**。  現在、**コンソールは、Web**サイトの開発者、ライブラリ、フレームワーク、およびユーザーがメッセージ、警告、エラー Microsoft Edgeを記録する中心的な場所です。  Issues ツールは、構造化された、集約された、操作可能な方法でブラウザーからの警告を集約し、Microsoft Edge DevTools 内の影響を受けるリソースへのリンク、および問題の修正方法に関するガイダンスを提供します。 ****  時間がたつ間に、コンソールではなく問題ツールの Microsoft Edge で多**** くの警告が表示され、コンソール**** の混乱を減らすのに役立**ちます**。  

開始するには、[DevTools の問題の検索と修正] ツールMicrosoft Edge[に移動します][DevtoolsIssuesIndex]。  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="DevTools ドロワーの問題ツール" lightbox="../../media/2020/05/issues.msft.png":::
   **DevTools**ドロワーの問題ツール  
:::image-end:::  

Chromiumの問題[#1068116][CR1068116]  

### <a name="view-accessibility-information-in-the-inspect-mode-tooltip"></a>[検査モード] ツールヒントでアクセシビリティ情報を表示する  

[**検査モード]** ツールヒントは、要素にアクセス可能な名前[][WebhintHintsAxeNameRoleValue]と役割を持ち、キーボードフォーカスが可能[かどうかを示します][WebhintHintsAxeKeyboard]。  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="アクセシビリティ情報を含む検査モードのヒント" lightbox="../../media/2020/05/a11y.msft.png":::
  アクセシビリティ **情報を含** む検査モードのヒント  
:::image-end:::  

Chromium[問題#1040025][CR1040025]  

### <a name="performance-panel-updates"></a>[パフォーマンス] パネルの更新  

#### <a name="view-total-blocking-time-information-in-the-footer"></a>フッターにブロック時間の合計情報を表示する  

読み込みパフォーマンスを記録すると、[ **パフォーマンス** ] パネルにフッターに [合計ブロック時間] \(TBT\) 情報が表示されます。  TBT は読み込みパフォーマンスの指標で、ページが使用できる時間を数値化するのに役立ちます。  基本的には、ページが使用できる \(コンテンツが screen\にレンダリングされるので)使用できる時間を測定します。JavaScript がメイン スレッドをブロックするため、ページはユーザー入力に応答しないので、実際には使用できません。  TBT は、最初の入力遅延を近似する主な指標です。  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

[合計ブロック時間] 情報を取得するには、**** ページ読み込みパフォーマンスを記録するために [ページの更新] ページの更新アイコン ![ ](../../../media/refresh-page-icon.msft.png) ワークフローを使用しない必要があります。  

代わりに、[ **レコード] アイコンを**選択し、ページを手動で再読み込みし、ページが読み込むのを待ち、記録 ![ ](../../../media/record-icon.msft.png) を停止します。  

表示 `Total Blocking Time: Unavailable` されている場合はMicrosoft Edge DevTools で内部プロファイル データから必要な情報を取得Microsoft Edge。  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text="パフォーマンス パネルの記録のフッターの合計ブロック時間情報" lightbox="../../media/2020/05/tbt.msft.png":::
   パフォーマンス パネルの記録のフッターの合計 **ブロック時間** 情報  
:::image-end:::  

Chromium[問題#1054381][CR1054381]  

#### <a name="layout-shift-events-in-the-new-experience-section"></a>[新しいエクスペリエンス] セクションの [Shift イベントのレイアウト]  

[パフォーマンス **] パネルの** 新しい **[エクスペリエンス] セクション** を使用すると、レイアウトシフトを検出できます。  累積レイアウト シフト \(CLS\) は、望ましくない視覚不安定を定量化するのに役立つ指標です。

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

[レイアウト **シフト] イベントを** 選択して、[概要] ウィンドウにレイアウト シフトの詳細 **を表示** します。  [移動先 **] フィールドと [****移動先**] フィールドにカーソルを合わせると、レイアウトシフトが発生した場所を視覚化できます。  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="レイアウト シフトの詳細" lightbox="../../media/2020/05/cls.msft.png":::
   レイアウト シフトの詳細  
:::image-end:::  

### <a name="more-accurate-promise-terminology-in-the-console"></a>コンソールのより正確な約束の用語  

ログを記録すると `Promise` 、 **コンソールに正** しく指定されていない `PromiseStatus` 値がに設定されます `resolved` 。  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="古い解決済み用語を使用するコンソールの例" lightbox="../../media/2020/05/resolved.msft.png":::
   古い用語を **使用した** コンソールの `resolved` 例  
:::image-end:::  

コンソール **では** 、仕様に合 `fulfilled` わせて用語が使用 `Promise` されます。  仕様の詳細については、「States `Promise` and [Fates on GitHub 」 に移動します](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)。  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="新しい満たされた用語を使用するコンソールの例" lightbox="../../media/2020/05/fulfilled.msft.png":::
  新しい用語を **使用する** コンソールの `fulfilled` 例  
:::image-end:::  

V8 の [問題#6751][CRV86751]  

### <a name="styles-pane-updates"></a>スタイル ウィンドウの更新  

#### <a name="support-for-the-revert-keyword"></a>revert キーワードのサポート  

スタイル ウィンドウのオートコンプリート UI**** で[、元に][MDNRevert]戻す CSS キーワードが検出され、プロパティのカスケード値が要素のスタイル設定に適用された以前の値に戻ります。  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="プロパティの値を元に戻す設定" lightbox="../../media/2020/05/revert.msft.png":::
  プロパティの値を元に戻す設定  
:::image-end:::  

Chromiumの問題[#1075437][CR1075437]  

#### <a name="image-previews"></a>画像のプレビュー  

[スタイル] `background-image` ウィンドウの値に **カーソルを合** わせると、ツールヒントに画像のプレビューが表示されます。  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="背景画像の値にカーソルを合わせる" lightbox="../../media/2020/05/image-preview.msft.png":::
  値の上にカーソルを移動 `background-image` する  
:::image-end:::  

Chromium[の問題][CR1040019]#1040019  

#### <a name="color-picker-now-uses-space-separated-functional-color-notation"></a>カラー ピッカーでスペース区切りの機能色表記が使用される  

[CSS Color Module Level 4][CSSWGDraftsColor4Changes3] は、スペースで区切られた引数をサポートするカラー関数 (など) `rgb()` を指定します。  たとえば、`rgb(0, 0, 0)` は `rbg(0 0 0)` と同じです。  

[色の選択][][DevtoolsCssReferenceColorPicker]ウィンドウで色を選択するか、[スタイル] ウィンドウ**** で色表現を交互に選択する場合は、値を保持して選択すると、スペースで区切られた引数構文 `Shift` `background-color` が表示されます。  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="[スタイル] ウィンドウでのスペース区切り引数の使用" lightbox="../../media/2020/05/color.msft.png":::
  [スタイル] ウィンドウでのスペース区切り引数 **の** 使用  
:::image-end:::  

また、[計算済み] ウィンドウと [ **検査** モード] ツールヒントにも **構文を表示する必要** があります。  

Microsoft Edge[Color()][CSSWGDraftsColor4Property]などの今後の CSS 機能では、廃止されたコンマ区切り引数構文がサポートされないので、DevTools は新しい構文を使用しています。  

スペースで区切られた引数の構文は、ほとんどのブラウザーでしばらくサポートされています。  詳細については、「使用できる:スペースで区切られた機能の色表記 [」に移動します。][CaniuseMDNSpaceSeparatedFunctionalColorNotations]  

Chromium[問題#1072952][CR1072952]  

### <a name="deprecation-of-the-properties-pane-in-the-elements-panel"></a>[要素] パネルの [プロパティ] ウィンドウの廃止  

[ **要素]** ツールの **[プロパティ] ウィンドウ** は非推奨です。  代 `console.dir($0)` わりにコンソール **で** 実行します。  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text="非推奨の [プロパティ] ウィンドウ" lightbox="../../media/2020/05/properties.msft.png":::
   非推奨の **[プロパティ]** ウィンドウ  
:::image-end:::  

#### <a name="references"></a>参考資料  

*   [console.dir()][DevtoolsConsoleApiDir]  
*   [$0][DevtoolsConsoleUtilitiesRecentlyChosenElementJavascriptObject]  

### <a name="app-shortcuts-support-in-the-manifest-pane"></a>マニフェスト ウィンドウでのアプリ ショートカットのサポート  

アプリのショートカット を使用すると、Web アプリ内で一般的または推奨されるタスクをすばやく開始できます。  アプリのショートカット メニューは、ユーザーのデスクトップまたはモバイル デバイスにインストールされている [プログレッシブ Web][PwaIndex] アプリにのみ表示されます。  

<!--For more information, navigate to [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text="マニフェスト ウィンドウのアプリ ショートカット" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  マニフェスト ウィンドウのアプリ**ショートカット**  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Devtools チームとMicrosoft Edgeする  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

<!--[DevtoolsWhatsNew201901Inspect]: ../../../whats-new/2019/01/devtools.md#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[DevtoolsConsoleApiDir]: ../../../console/api.md#dir "dir - コンソール API リファレンス |Microsoft Docs"  
[DevtoolsConsoleUtilitiesRecentlyChosenElementJavascriptObject]: ../../../console/utilities.md#recently-chosen-element-or-javascript-object "最近選択した要素または JavaScript オブジェクト - コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsCssReferenceColorPicker]: ../../../css/reference.md#change-colors-with-the-color-picker "カラー ピッカー - CSS リファレンス を使用して色を変更|Microsoft Docs"  
[DevtoolsDrawer]: ../../../customize/index.md#drawer "ドロワー - カスタマイズの概要|Microsoft Docs"  
[DevtoolsIndex]: ../../../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../../../issues/index.md "DevTools の [問題] タブの [Microsoft Edgeを検索して修正|Microsoft Docs"  
[DevtoolsNetworkDetails]: ../../../network/index.md#inspect-the-details-of-the-resource "リソース リソースの詳細を調|Microsoft Docs"  
[DevtoolsNetworkLog]: ../../../network/index.md#log-network-activity "ネットワーク アクティビティのログ |Microsoft Docs"  
[DevtoolsRemoteDebugAndroid]: ../../../remote-debugging/index.md "はじめに リモート デバッグ Android デバイスの使用|Microsoft Docs"  
[DevtoolsRemoteDebugDuoEmulator]: ../../../remote-debugging/surface-duo-emulator.md "はじめに Surface Duo エミュレーターの使用|Microsoft Docs"  
[DevtoolsRemoteDebugWindows]: ../../../remote-debugging/windows.md "Windows 10 デバイスのリモート デバッグの概要 | Microsoft Docs"  

[PwaIndex]: ../../../../progressive-web-apps-chromium/index.md "Windows 上のプログレッシブ Web アプリ | Microsoft Docs"  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用|Microsoft Docs"

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft EdgeAndroid アプリ"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "スペースで区切られた機能的な色表記 - MDN |使用できる"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可|Chromiumバグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG 準拠の|Chromiumバグ"  
[CR1040019]: https://crbug.com/1040019 "DevTools: [スタイル] ウィンドウの [スタイル] ウィンドウで画像と背景画像を簡単にプレビュー|Chromiumバグ"  
[CR1040025]: https://crbug.com/1040025 "DevTools: 要素ポップオーバー の基本 a11y 情報を表示|Chromiumバグ"  
[CR1048378]: https://crbug.com/1048378 "ハイ コントラスト モードの DevTools UI の|Chromiumバグ"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromiumバグ"  
[CR1068116]: https://crbug.com/1068116 "[出荷の問題] パネル|Chromiumバグ"  
[CR1072952]: https://crbug.com/1072952 "DevTools: カラー ピッカーは、最新の CSS カラー構文を生成|Chromiumバグ"  
[CR1075437]: https://crbug.com/1075437 "DevTools: CSS 'revert' キーワード/値のサポートを追加|Chromiumバグ"  
[CR1076112]: https://crbug.com/1076112 "Devtools 個人用設定 - ドロワーリサイズ"  
[CR1081486]: https://crbug.com/1081486 "スクリーンキャスト モードのナビゲーション ボタンにキーボード フォーカスが表示されない|Chromiumバグ"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus は 'fulfilled' で、&quot;解決済み&quot; の|V8 のバグ"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 "色 3 からの変更 - CSS カラー モジュール レベル 4 |W3C CSS ワーキング グループ エディターの下書き"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. 前景色: 'color' - CSS Color Module Level 4 |W3C CSS ワーキング グループ エディターの下書き"  

[DesktopEdge]: https://www.microsoft.com/edge/ "新しい機能のMicrosoft Edge"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "状態と運命 - domenic/promises-unwrapping |GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "元に戻す|MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "ブラウザーの互換性|MDN"  

[VisualStudioCodeMain]: https://code.visualstudio.com/ "Visual Studio Code"  
[VisualStudioCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Code の Windows 用キーボード ショートカット"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "Axe: キーボード |WebHint"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "Axe: Name Role Value |WebHint"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "ハイ コントラスト モードのオンとオフを切り替Windows |Windowsサポート"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edgeプレビュー チャネル"  
[TheWebWeWantMain]: https://aka.ms/webwewant "必要とされる Web"  

<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebdevCoreWebVitals]: https://alphabet-dev/vitals#core-web-vitals "Core Web Vitals | alphabet-dev"  -->  

> [!NOTE]
> このページの一部は、[Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更であり、「[Creative Commons Attribution 4.0 International License][CCA4IL]」に記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developer.chrome.com/blog/new-in-devtools-84) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
