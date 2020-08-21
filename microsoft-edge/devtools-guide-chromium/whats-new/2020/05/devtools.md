---
title: DevTools の新機能 (Microsoft Edge 84)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: aa39e5d7811d4a614e055a8e0479c74278efbefd
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942185"
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

# DevTools の新機能 (Microsoft Edge 84)  

## Microsoft Edge DevTools チームからのお知らせ  

以下のセクションは、Microsoft Edge DevTools チームに見つからない可能性があるお知らせの一覧です。 デベロッパー、VS コード拡張機能などで新機能を試すようにしてください。  開発者ツールの最新機能と最大の機能をすべて最新の状態に保つためには [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを [ダウンロードし、Twitter でフォローしてください][EdgeDevToolsTwitterAccount]。  

### Windows ハイ コントラスト モードで DevTools を使用する

Windows がハイコントラスト モードの場合、Microsoft Edge DevTools がハイ コントラスト モードで表示されるようになりました。  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="ハイ コントラスト モードの Microsoft Edge DevTools" lightbox="../../media/2020/05/high-contrast.msft.png":::
   ハイ コントラスト モードの Microsoft Edge DevTools  
:::image-end:::  

[指示に従って、Windows のハイ コントラスト モードをオンにします][MicrosoftSupportWindows10HighContrastMode]。  Microsoft Edge で DevTools を開くには、キーを押すか、キーを `F12` 押します `Ctrl` + `Shift` + `I` 。  ハイ コントラスト モードで DevTools が表示されます。  

> [!NOTE]
> 現在 Microsoft Edge DevTools は現在、Windows でハイ コントラスト モードをサポートしていますが、macOS ではサポートされていません。 

Chromium の [問題#1048378][CR1048378]  

### DevTools のキーボード ショートカットを VS コードに一致する  

お客様の [フィードバックと](#getting-in-touch-with-microsoft-edge-devtools-team) [Chromium パ][CRIssuesList]ブリックの問題トラッカーから、DevTools でキーボード ショートカットをカスタマイズできるようにしたい Microsoft Edge DevTools チームからお客様のフィードバックをお寄せいただけます。  Microsoft Edge 84 では、デベロッパーツールのキーボード ショートカットを [VS コードに][VSCode]対応できるようになりました。これは、チームが作業している機能の 1 つです。  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="DevTools のキーボード ショートカットを VS コードに一致する" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   ハイ コントラスト モードの Microsoft Edge DevTools  
:::image-end:::  

試してみるには、DevTools の右上隅にある [DevTools の設定] アイコンアイコンを押するか `?` ![ ][ImageSettingsIcon] 、選択します。  [環境設定]**セクションに移動し**、[カスタム キーボード ショートカットの**設定] タブを有効にする (再読み込む必要があります)。**  開発ツールを再読み込みし、[設定] をもう一度開き、ショートカット セクション **に移動** します。  

事**前設定されている [一致] ショートカットのドロップダウンから [DevTools](既定)** を選択し、[コード **] Visual Studioします**。 **Match shortcuts from preset**  DevTools のキーボード ショートカットが VS コード内の等当な操作のショートカットと一致できるようになりました。  

たとえば、VS コードでスクリプトを一時的に実行または実行するためのキーボード [ショートカットは、次のとおり][VSCodeShortcuts] です `F5` 。  **DevTools (既定)** のプリセットでは、DevTools で同じショートカットが `F8` あっても **、Visual Studio Code**の事前設定でもそのショートカットがインストールされています `F5` 。  

現在この機能は Microsoft Edge 84 で実用的な機能を実現しているため、フィードバックを [チームと共有](#getting-in-touch-with-microsoft-edge-devtools-team) してください。  

Chromium の [問題#174309][CR174309]  

### リモート デバッグ Surface Duo エミュレーター  

[Microsoft Edge DevTools][DevToolsChromiumGuide]の完全機能を利用し[、Surface Duo エ][DualScreensAndroidEmulator]ミュレーターで実行されている Web コンテンツをリモートでデバッグできるようになりました。  

Surface [Duo エミュレータ][DualScreensAndroidEmulator]ーでは、新しいフォールドやデュアルスクリーン デバイスの新しいクラスで Web コンテンツのレンダリング方法をテストすることができます。  エミュレーターは Android オペレーティング システムを実行し [、Microsoft Edge Android アプリを提供します][AndroidEdge]。  Microsoft Edge アプリで Web コンテンツを読 [み込][AndroidEdge] み [、Microsoft Edge DevTools でデバッグします][DevToolsChromiumGuide]。  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="Surface Duo エミュレーター上で実行されている Microsoft Edge アプリ" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   Surface Duo エミュレーター上の Microsoft Edge アプリ  
:::image-end:::  

Microsoft Edge のデスクトップ インスタンスには `edge://inspect` **、Surface DuoEmulator**上で実行されている開いているタブ[または PWA の][PwaIndex]一覧が[表示されます][DualScreensAndroidEmulator]。 [Microsoft Edge][DesktopEdge]  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="エedge://inspectージ モリューターで実行されている Microsoft Edge アプリで開いているタブのリストが表示されます。" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   ページには、エミュレーター上で実行されている Microsoft Edge アプリで開いているタブの `edge://inspect` リストが表示されます。
:::image-end:::  

デ **バッグする** タブまたは PWA について検査を選択すると [、Microsoft Edge DevTools が開きます][DevToolsChromiumGuide]。  [Surface Duo エミュレ][DevToolsRemoteDebugDuoEmulator]ーター上の Web コンテンツをリモートでデバッグするには、ステップ バイ ステップ ガイドに従います。  

### より簡単に DevTools 図面のサイズを変更する  

Microsoft Edge 83 以前では、描画ツールのツール バー内を [移動して DevTools Drawer][DevToolsDrawer] のサイズを変更することができました。  図面の機能は、ウィンドウの境界線をマウスで置くと、サイズを変更する開発ツールのウィンドウのその他のサイズ変更コントロールとは異なります。  次の画像を選択して、83 以前の Microsoft Edge での図面のサイズ変更方法を確認します。  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="Microsoft Edge 83 で DevTools Drawer のサイズを変更する" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   Microsoft Edge 83 で DevTools Drawer のサイズを変更する
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

Microsoft Edge 84 以降では、描画ツールの枠線の上にマウス ポインターを合わせると、描画パターのサイズを変更できるようになりました。  これにより、DevTools の図面のサイズ変更と、DevTools の他のウィンドウ サイズを変更する方法で、DevTools Drawer のサイズ変更が行えます。  次の画像を選択して、Microsoft Edge 84 での動作のサイズ変更を確認します。  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="Microsoft Edge 84 で DevTools Drawer のサイズを変更する" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   Microsoft Edge 84 で DevTools Drawer のサイズを変更する
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

Chromium の問題 [#1076112][CR1076112]  

### ナビゲーション ボタンのフォーカスが表示される画面キャッシュ  

[Android][DevToolsRemoteDebugAndroid]デバイス[、Windows 10][DevToolsRemoteDebugWindows]デバイス、[または Surface Duo エ][DevToolsRemoteDebugDuoEmulator]ミュレーターのリモート デバッグを行う場合、DevTools の左上隅にある [画面の切り替え] アイコンを使用して画面キャストを切 ![ ][ImageScreencastingIcon] り替えられます。  画面が有効になっている場合は、DevTools ウィンドウからリモート デバイスの Microsoft Edge のタブ間を移動することができます。  Microsoft Edge 84 では、これらのナビゲーション ボタンにもキーボードがアクセスできるようになりました。  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="画面に表示された URL バーから Shift + Tab キーを押すと、[更新] ボタンにフォーカスが表示されます。" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   スクリーンキ `Shift` + `Tab` ャストした URL バーから押すと、[更新] ボタンにフォーカスが**表示**されます
:::image-end:::  

Chromium の [問題はc#1081486][CR1081486]  

### ネットワーク パネルの詳細ウィンドウにアクセスできるようになりました  

Microsoft Edge 84 では[、[ネットワーク][DevToolsNetworkDetails]ログ**Network**] でリソースを開くと、[ネットワーク パネルの詳細] ウィンドウがフォーカスされる[ようになりました][DevToolsNetworkLog]。  この変更により、スクリーン リーダーは詳細ウィンドウの内容を読み取り、操作**することができます。**  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text="開いたときに、ネットワーク パネルの詳細ウィンドウがフォーカスされた状態で移動します。" lightbox="../../media/2020/05/network-details.msft.png":::
   開 **いた** ときに **、ネットワーク** パネルの詳細ウィンドウがフォーカスされた状態で移動します。
:::image-end:::  

Chromium の問題 [#963183][CR963183]  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、オープン ソース Chromium プロジェクトに投稿された Microsoft Edge 84 で利用可能なその他の機能について説明します。  

### DevTools 図面の新しい問題ツールでサイトの問題を解決する

DevTools **図面の** 新しい問題ツールが、本体の通知のフトラッシュと集中性を下 **げるのに役立てました**。  現在、 **本体** は Web サイトの開発者、ライブラリ、フレームワーク、および Microsoft Edge がメッセージ、警告、エラーをログに記録する中間的な場所です。  **問題ツール**は、構造化、集約、実行可能な方法でブラウザーからの警告を集約し、Microsoft Edge DevTools 内の影響を受けるリソースへのリンク、問題の修正方法に関するガイダンスを提供します。  本体の問題に対する Microsoft Edge の警告は本体より **も問題** ツールで表示されるようになるため **、** 本体での余分な機能を下げる **のに役立ちます**。  

使用を開始するには [、Microsoft Edge DevTools の][DevtoolsIssuesIndex]問題ツールに関する問題を見つして修正します。  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="DevTools 図面の問題ツール" lightbox="../../media/2020/05/issues.msft.png":::
   **DevTools**図面の問題ツール  
:::image-end:::  

Chromium の [問題#1068116][CR1068116]  

### 検査モードのヒントでアクセシビリティ情報を表示する  

検 **査モードのヒン** トは、要素にアクセス可能な名前がで、 [キーボード][WebhintHintsAxeNameRoleValue] フォーカスがあるかどうか [を示します][WebhintHintsAxeKeyboard]。  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="アクセシビリティ情報が含された検査モードのヒント" lightbox="../../media/2020/05/a11y.msft.png":::
  アクセシビリティ **情報が含された** 検査モードのヒント  
:::image-end:::  

Chromium の問題はキ [#1040025][CR1040025]  

### パフォーマンス パネルの更新  

#### フッターに "禁止時間" の情報を表示する  

読み込みのパフォーマンス を記録すると、 **パフ** ォーマンス パネルにフッターに "ブロック時間 "合計ブロック時間 \(TBT\) の情報が表示されるようになりました。  TBT は読み込みのパフォーマンス メトリックで、ページが使用可能になった時間を数量にするのに役立ちます。  コンテンツは画面\にレンダリングされるため、ページが使用可能な時間を測定します (コンテンツは画面\にレンダリングされるため)。ただし、JavaScript がメイン スレッドをブロックしているため、ページはユーザー入力に応答しないため、実際に使用することはできません。  TBT は、First Input Delay におおおるメトリックです。  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

総ブロック時間情報を取得するには、[ページの読み**Refresh Page**込み時の更新] アイコン ワークフローを使用してページ読み込みのパフォー ![ ][ImageRefreshPageIcon] マンスを記録しないでください。  

代わりに、[ **レコード録音]** アイコン ![ を ][ImageRecordIcon] 選択し、ページを手動で再読み込み、ページが読み込みの待ってから記録を停止します。  

表示されていなかった場合、Microsoft Edge DevTools は内部プロファイリング データから必要な情報を `Total Blocking Time: Unavailable` 取得しませんでした。  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text="パフォーマンス パネルの記録のフッターの [ブロック時間] の合計情報" lightbox="../../media/2020/05/tbt.msft.png":::
   パフォーマンス パネルの記録のフッターの [ **ブロック** 時間] の合計情報  
:::image-end:::  

Chromium の問題は、chromium [の#1054381][CR1054381]  

#### 新しいエクスペリエンス セクションのレイアウト シフト イベント  

パフォ**ーマン****ス**パネルの新しい [エクスペリエンス] セクションを使用すると、レイアウト シフトを検出できます。  累積レイアウトシフト \(CLS\) は、不必要な視覚的なインストーリーを検出するのに役立つメトリックです。

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

[レイアウト シ **フト]** イベントを選択すると、概要ウィンドウにレイアウト シフトの詳細 **が表示** されます。  [移動] と [ **移動した** ] フィールド **にカーソ** ルを合って、レイアウトシフトが発生した位置を視覚化します。  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="レイアウト シフトの詳細" lightbox="../../media/2020/05/cls.msft.png":::
   レイアウト シフトの詳細  
:::image-end:::  

### 本体での正確なプロミス用語  

ログ記録時に、 `Promise` **本体が** 誤って提供された `PromiseStatus` 値を設定していません `resolved` 。  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="古い解決用語を使用した本体の例" lightbox="../../media/2020/05/resolved.msft.png":::
   古い用 **語を** 使用した本体 `resolved` の例  
:::image-end:::  

本 **体では** 用語が使用され、指定した用語と `fulfilled` 合わせて配置 `Promise` されます。  具体名の詳細 `Promise` については [、GitHub の「都道府県」と「Fates」を参照してください](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)。  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="新しいフルフィルフィルタされた用語を使用した本体の例" lightbox="../../media/2020/05/fulfilled.msft.png":::
  新しい用 **語を使用** した本 `fulfilled` 体の例  
:::image-end:::  

V8 の [問題#6751][CRV86751]  

### [スタイル] ウィンドウの更新  

#### リバート キーワードのサポート  

[スタイル] ウィンドウのオ**Styles**ートコンプリート[UI][MDNRevert]で、要素のスタイリングに適用された、プロパティのカスケード値を前の値に戻します。  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="戻すプロパティの値を設定する" lightbox="../../media/2020/05/revert.msft.png":::
  戻すプロパティの値を設定する  
:::image-end:::  

Chromium [の問題#1075437][CR1075437]  

#### 画像のプレビュー  

[スタイル] ウィンドウの `background-image` 値にマウス ポイン **ターを置** くと、ヒントに画像のプレビューが表示されます。  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="背景画像の値の上にマウス ポインターを置く" lightbox="../../media/2020/05/image-preview.msft.png":::
  値の上にマウス カーソルを `background-image` 置く  
:::image-end:::  

Chromium の問題 [#1040019][CR1040019]  

#### [色の選択] で、スペースで区切った関数カラー表を使用する  

[CSS カラー モジュール レベル 4 は、スペース][CSSWGDraftsColor4Changes3] 区切り引数をサポートする必要がある、色のモジュール レベル 4 `rgb()` を指定します。  たとえば、`rgb(0, 0, 0)` は `rbg(0 0 0)` と同じです。  

[スタイル] ウィンドウで色を選ぶ[か、値][DevtoolsCssReferenceColorPicker]を選んで選択することで色の選択を切り替**Styles**えると、スペース区切り `Shift` 引数の `background-color` 構文が表示されます。  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="[スタイル] ウィンドウでスペース区切り引数を使用する" lightbox="../../media/2020/05/color.msft.png":::
  [スタイル] ウィンドウでスペース区切り引数 **を使用** する  
:::image-end:::  

また、[コンピュート] ウィンドウと [検**Computed**査モード] のヒントにも**構文**が表示されます。  

Microsoft Edge DevTools では、カラー [(color()][CSSWGDraftsColor4Property] などの CSS 機能では非前の引数の構文をサポートしないため、Microsoft Edge DevTools では新しい構文が使用されています。  

スペース区切り引数の構文は、ほとんどのブラウザーでサポートされています。  詳細については、「スペース区切りの関数の色表にスペース [区切りの表を挿入する」を参照してください。][CaniuseMDNSpaceSeparatedFunctionalColorNotations]  

Chromium の [問題#1072952][CR1072952]  

### [要素] パネルの [プロパティ] ウィンドウの廃い  

要素 **パネ** ルの [ **プロパティ** ] ウィンドウは廃減されました。  代 `console.dir($0)` わりに **本体で** 実行します。  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text="非保持されたプロパティ ウィンドウ" lightbox="../../media/2020/05/properties.msft.png":::
   非保持されたプロパティ**ウィンドウ**  
:::image-end:::  

#### 参考資料  

*   [console.dir()][DevtoolsConsoleApiDir]  
*   [$0][DevtoolsConsoleUtilitiesDom]  

### [マニフェスト] ウィンドウでのアプリ ショートカット  

アプリ のショートカットにより、ユーザーは Web アプリ内で一般的なまたは推奨タスクをすばやく開始できます。  アプリのショートカット メニューは、ユーザーのデスクトップまたはモバイル デバイスにインストールされている進行中の [Web アプリ][PwaIndex] に対してのみ表示されます。  

<!--For more information, see [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text="マニフェスト ウィンドウのアプリ ショートカット" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  マニフェ**スト ウィンドウのアプリ ショートカット**  
:::image-end:::  

## Microsoft Edge のプレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge Devtools チームとのつながりを教える  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "[開発ツールの設定] アイコン"
[ImageScreencastingIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/images/toggle-screencast-icon.msft.png "DevTools の切り替えアイコン"
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-page-icon.msft.png "DevTools のパフォーマンス パネルの [ページの更新] アイコン"
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png "DevTools パフォーマンス パネルの [レコード] アイコン"

<!-- links -->  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用する |Microsoft ドキュメント"

[DevtoolsConsoleApiDir]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir - 本体 API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesDom]: /microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選択した要素または JavaScript オブジェクト - 本体のユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "色の作成で色を変更する - CSS リファレンス |Microsoft ドキュメント"  
[DevToolsDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "[図形描画] - 概要のカスタマイズ |Microsoft ドキュメント"  
[DevToolsChromiumGuide]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "Microsoft Edge DevTools の問題タブに関する問題を見つけ、解決する |Microsoft ドキュメント"  
[DevToolsRemoteDebugAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "リモート デバッグの Android デバイスの使用を開始する |Microsoft ドキュメント"  
[DevToolsRemoteDebugDuoEmulator]: /microsoft-edge/devtools-guide-chromium/remote-debugging/surface-duo-emulator "Surface Duo エミュレーターのリモート デバッグの使用を開始する |Microsoft ドキュメント"  
[DevToolsRemoteDebugWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモート デバッグの使用を開始する |Microsoft ドキュメント"  
[DevToolsNetworkDetails]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "リソースの詳細を検査する |Microsoft ドキュメント"  
[DevToolsNetworkLog]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワーク アクティビティを記録する |Microsoft ドキュメント"  
[PwaIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上のプレイ Web アプリ |Microsoft ドキュメント"  
<!--[DevtoolsWhatsNew201901Inspect]: /microsoft-edge/devtools-guide-chromium/whats-new/2019/01/devtools#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android アプリ"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "スペース区切りの機能カラー表 - MDN |使用できる"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キーバインドのカスタマイズを許可する |Chromium のバグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG 準準に準プライアンスされない |Chromium のバグ"  
[CR1040019]: https://crbug.com/1040019 "DevTools: [スタイル] ウィンドウで画像と背景画像を簡単にプレビューする |Chromium のバグ"  
[CR1040025]: https://crbug.com/1040025 "DevTools: 要素ポップオーバーに基本的な a11y 情報を表示する |Chromium のバグ"  
[CR1048378]: https://crbug.com/1048378 "ハイ コントラスト モードの DevTools UI のサポート |Chromium のバグ"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromium のバグ"  
[CR1068116]: https://crbug.com/1068116 "配送のパネル |Chromium のバグ"  
[CR1072952]: https://crbug.com/1072952 "DevTools: カラー ピッカーが最新の CSS カラー構文を作成する必要があります |Chromium のバグ"  
[CR1075437]: https://crbug.com/1075437 "DevTools: CSS の 'リバート' キーと値のサポートを追加する |Chromium のバグ"  
[CR1076112]: https://crbug.com/1076112 "開発ツールの個人用設定 - 図面のサイズ変更"  
[CR1081486]: https://crbug.com/1081486 "スクリーンキャスト モードのナビゲーション ボタンにキーボード フォーカスが表示されない |Chromium のバグ"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus は 'fulfilled' で、'解決' でない ' にする必要があります |V8 バグ"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 "色 3 - CSS カラー モジュール レベル 4 からの変更 |W3C CSS 作業グループ エディターの下書き"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. Foreground Color: 'color' - CSS カラー モジュール レベル 4 |W3C CSS 作業グループ エディターの下書き"  

[DesktopEdge]: https://www.microsoft.com/edge/ "新しい Microsoft Edge のご説明"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "都道府県と Fates - domenic/promises-unwrapping |GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "リバート |MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "ブラウザーの互換性 |MDN"  

[VSCode]: https://code.visualstudio.com/ "Visual Studioコード"  
[VSCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Windows のコード ショートカット"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "軸: キーボード |WebHint"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "軸: 名前の役割値 |WebHint"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "Windows でハイ コントラスト モードをオンまたはオフにする |Windows サポート"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |チェットを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "Twitter アカウント@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge 開発者"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"  

<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebdevCoreWebVitals]: https://alphabet-dev/vitals#core-web-vitals "Core Web Vitals | alphabet-dev"  -->  

> [!NOTE]
> このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。  
> ここには元のページが表示[され](https://developers.google.com/web/updates/2020/05/devtools/index)[、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools \& Lighthouse\) によって作成されます。  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
