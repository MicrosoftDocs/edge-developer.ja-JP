---
description: Windows ハイコントラストモードの DevTools を使用して、DevTools のキーボードショートカットを VS コードに一致させることができます。
title: DevTools の新機能 (Microsoft Edge 84)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 62f261b381b0382561e166bca67f77f37225b764
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992889"
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

以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。 これらを確認して、DevTools、VS コード拡張などの新機能を試してみてください。  開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。  

### Windows のハイコントラストモードで DevTools を使う

Windows がハイコントラストモードの場合は、Microsoft Edge DevTools がハイコントラストモードで表示されるようになりました。  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="ハイコントラストモードの Microsoft Edge DevTools" lightbox="../../media/2020/05/high-contrast.msft.png":::
   ハイコントラストモードの Microsoft Edge DevTools  
:::image-end:::  

[指示に従って、Windows でハイコントラストモードをオン][MicrosoftSupportWindows10HighContrastMode]にします。  またはを押して、Microsoft Edge で DevTools を開き `F12` `Ctrl` + `Shift` + `I` ます。  DevTools はハイコントラストモードで表示されます。  

> [!NOTE]
> Microsoft Edge DevTools は現在、macOS ではサポートされていませんが、Windows のハイコントラストモードをサポートしています。 

Chromium の問題 [#1048378][CR1048378]  

### 開発ツールのキーボードショートカットを VS コードに一致させる  

[フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team)と[Chromium の公開問題の追跡][CRIssuesList]ツールでは、Microsoft Edge DevTools チームが、devtools でキーボードショートカットをカスタマイズする機能が必要であることを学習しました。  Microsoft Edge 84 では、DevTools のキーボードショートカットを、ショートカットのカスタマイズについてチームが作業している機能の1つである [VS コード][VSCode]に一致させることができるようになりました。  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="開発ツールのキーボードショートカットを VS コードに一致させる" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   ハイコントラストモードの Microsoft Edge DevTools  
:::image-end:::  

実験を試みるには、devtools `?` ![ ][ImageSettingsIcon] の右上隅にある [devtools の設定] アイコンをクリックまたは選択して、Devtools の設定を開きます。  [ **実験** ] セクションに移動し、[ユーザー設定の **キーボードショートカットを有効にする] をオンにします (再読み込みが必要)**。  次に、DevTools を再読み込みし、設定をもう一度開き、[ **ショートカット** ] セクションに移動します。  

[**標準のショートカットキー**の選択] ドロップダウンで [ **Devtools (既定値)** ] を選び、[ **Visual Studio コード**] を選びます。  DevTools のキーボードショートカットは、VS コードで同等のアクションのショートカットと一致するようになりました。  

たとえば、 [VS コード][VSCodeShortcuts] でスクリプトを一時停止または実行し続けるためのキーボードショートカットは、 `F5` です。  **Devtools (既定)** の事前設定を使用すると、devtools の同じショートカットが `F8` **Visual Studio のコード**プリセットでも使用できるようになりました `F5` 。  

この機能は、現在 Microsoft Edge 84 で実験として提供されているので、チームと [フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team) を共有してください。  

Chromium の問題 [#174309][CR174309]  

### リモートデバッグ Surface Duo エミュレーター  

[Microsoft Edge DevTools][DevToolsChromiumGuide]の全機能を使用して、 [Surface Duo エミュレーター][DualScreensAndroidEmulator]で実行されている web コンテンツをリモートでデバッグできるようになりました。  

[Surface Duo エミュレーター][DualScreensAndroidEmulator]を使用すると、折りたたみ式とデュアルスクリーンデバイスの新しいクラスで web コンテンツがどのようにレンダリングされるかをテストすることができます。  エミュレーターは Android オペレーティングシステムを実行し、 [Microsoft Edge Android アプリ][AndroidEdge]を提供します。  [Microsoft edge アプリ][AndroidEdge]で web コンテンツを読み込み、 [Microsoft edge devtools][DevToolsChromiumGuide]を使ってデバッグします。  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="Surface Duo エミュレーターで実行されている Microsoft Edge アプリ" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   Surface Duo エミュレーター上の Microsoft Edge アプリ  
:::image-end:::  

`edge://inspect` [Microsoft Edge][DesktopEdge]のデスクトップインスタンスのページには、 [Surface Duo エミュレーター][DualScreensAndroidEmulator]で実行されている開いているタブまたは[pwas][PwaIndex]の一覧が表示された**SurfaceDuoEmulator**が示されています。  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="Edge://inspect ページには、エミュレーターで実行されている Microsoft Edge アプリの開いているタブの一覧が表示されます。" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   このページには、 `edge://inspect` エミュレーターで実行されている Microsoft Edge アプリの開いているタブの一覧が表示されます。
:::image-end:::  

デバッグするタブまたは PWA の [ **検査** ] を選ぶと、 [Microsoft Edge devtools][DevToolsChromiumGuide]が開きます。  [次のステップバイステップガイドを参照して、Surface Duo エミュレーターで web コンテンツをリモートでデバッグ][DevToolsRemoteDebugDuoEmulator]します。  

### DevTools のドローワのサイズをより簡単に変更する  

Microsoft Edge 83 以前のバージョンでは、ドロアーのツールバー内にマウスポインターを置くことによって、 [Devtools の引き出し][DevToolsDrawer] のサイズを変更することはできませんでした。  ドロワーの動作は、ウィンドウの枠線をポイントしてサイズを変更する DevTools のウィンドウの他のサイズ変更コントロールとは異なります。  次の画像を選択して、Microsoft Edge のバージョン83またはそれ以前のドロアーのサイズ変更の動作を確認します。  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="Microsoft Edge 83 の DevTools の引き出しのサイズ変更" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   Microsoft Edge 83 の DevTools の引き出しのサイズ変更
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

Microsoft Edge 84 以降では、ドロアーの境界線の上にマウスポインターを置くと、引き出しのサイズを変更できるようになりました。  この変更によって、devtools の他のペインのサイズを変更する方法で、DevTools のドローワのサイズ変更動作が揃えられます。  Microsoft Edge 84 でのサイズ変更の動作を確認するには、次の画像を選択します。  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="Microsoft Edge 84 の DevTools の引き出しのサイズ変更" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   Microsoft Edge 84 の DevTools の引き出しのサイズ変更
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

Chromium の問題 [#1076112][CR1076112]  

### Screencasting ナビゲーションボタンにフォーカスが表示  

[Android デバイス][DevToolsRemoteDebugAndroid]、 [Windows 10 デバイス][DevToolsRemoteDebugWindows]、 [Surface Duo エミュレーター][DevToolsRemoteDebugDuoEmulator]をリモートでデバッグしている場合、 ![ ][ImageScreencastingIcon] Devtools の左上隅にあるトグル Screencast アイコンを使用して screencasting を切り替えることができます。  Screencasting を有効にすると、DevTools ウィンドウからリモートデバイスの Microsoft Edge でタブ内を移動できます。  Microsoft Edge 84 では、これらのナビゲーションボタンは、キーボードからアクセスできるようになりました。  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="Screencasted URL バーから Shift + Tab キーを押すと、[更新] ボタンにフォーカスが表示される" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   `Shift` + `Tab` Screencasted URL バーを押すと、[**更新**] ボタンにフォーカスが表示される
:::image-end:::  

Chromium の問題 [#1081486][CR1081486]  

### ネットワークパネルの詳細ウィンドウにアクセスできるようになりました  

Microsoft Edge 84 では、ネットワーク[ログ][DevToolsNetworkLog]内のリソースに対して [**ネットワーク**] パネルを開くと、[[詳細] ウィンドウ][DevToolsNetworkDetails]がフォーカスされます。  この変更により、スクリーンリーダーは **詳細** ウィンドウの内容を読み上げて操作できるようになります。  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text="[ネットワーク] パネルの詳細ウィンドウでは、開いたときにフォーカスが移動します。" lightbox="../../media/2020/05/network-details.msft.png":::
   [**ネットワーク**] パネルの**詳細**ウィンドウでは、開いたときにフォーカスが移動します。
:::image-end:::  

Chromium の問題 [#963183][CR963183]  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 84 で利用可能なその他の機能を示します。  

### DevTools のドローワの新しい問題ツールでサイトの問題を解決する

DevTools のドロアーの新しい **問題** ツールは、 **本体**の通知の疲労と低優先メールを削減するために構築されました。  現時点では、 **コンソール** は、web サイトの開発者、ライブラリ、フレームワーク、Microsoft Edge がメッセージ、警告、エラーをログに記録するための中心的な場所です。  **懸案事項**ツールは、ブラウザーからの警告を、構造化された、集計された実用的な方法で収集します。 Microsoft Edge devtools 内の影響を受けるリソースへのリンク、問題の修正方法のガイダンスを提供します。  時間の経過と共に、Microsoft Edge のツールでは **、本体で**はなく、[**問題**のツール] で、より多くの警告が表示されます。これにより、**本体**の低優先メール数を減らすことができます。  

始めるには、「 [Microsoft Edge DevTools の問題を見つけて解決][DevtoolsIssuesIndex]する」を参照してください。  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="DevTools のドローワの問題ツール" lightbox="../../media/2020/05/issues.msft.png":::
   DevTools のドローワの **問題** ツール  
:::image-end:::  

Chromium の問題 [#1068116][CR1068116]  

### 検査モードのヒントでアクセシビリティ情報を表示する  

**検査モード**のヒントは、要素にアクセシビリティ対応の[名前とロール][WebhintHintsAxeNameRoleValue]があり、[キーボードフォーカス][WebhintHintsAxeKeyboard]可能であるかどうかを示します。  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="アクセシビリティ情報が含まれる検査モードのヒント" lightbox="../../media/2020/05/a11y.msft.png":::
  アクセシビリティ情報が含まれる **検査モード** のヒント  
:::image-end:::  

Chromium の問題 [#1040025][CR1040025]  

### パフォーマンスパネルの更新  

#### フッターのブロック時間情報の合計を表示する  

ロードパフォーマンスの記録後、[ **パフォーマンス** ] パネルには、フッター内のブロック時間 (tbt) 情報が表示されるようになりました。  TBT は、ページが使用可能になるまでにかかる時間を数値化するのに役立つロードパフォーマンスメトリックです。  基本的には、ページが使用可能になるまでの時間を測定します (コンテンツが画面にレンダリングされるためです)。ただし、JavaScript がメインスレッドをブロックしているため、実際には使用できません。そのため、ページはユーザー入力に応答しません。  TBT は、おおよその最初の入力遅延の主な基準となります。  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

ブロックの合計時間情報を取得するには、 **Refresh Page**ページの ![ ][ImageRefreshPageIcon] 読み込みのパフォーマンスを記録するために、ページの更新ページの更新アイコンのワークフローを使わないでください。  

代わりに、[レコードレコード] アイコン **を選択し**、ページを手動で読み込むか ![ ][ImageRecordIcon] 、ページが読み込まれるのを待ってから、記録を停止します。  

`Total Blocking Time: Unavailable`Microsoft Edge DevTools では、Microsoft edge の内部プロファイリングデータから必要な情報を取得できませんでした。  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text="パフォーマンスパネル記録のフッターのブロック時間情報の合計" lightbox="../../media/2020/05/tbt.msft.png":::
   **パフォーマンス**パネル記録のフッターのブロック時間情報の合計  
:::image-end:::  

Chromium の問題 [#1054381][CR1054381]  

#### [新しいエクスペリエンス] セクションのレイアウトシフトのイベント  

[**パフォーマンス**] パネルの [新しい**エクスペリエンス**] セクションでは、レイアウトシフトを検出できます。  累積レイアウトシフト \ (CLS \) は、表示が不安定になるのを防ぐためのメトリックです。

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

[ **レイアウトシフト** ] イベントを選択して、[ **概要** ] ウィンドウのレイアウトシフトの詳細を表示します。  **移動**先と**移動**先のフィールドの上にマウスポインターを移動すると、レイアウトのシフトが発生した場所が表示されます。  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="レイアウトシフトの詳細" lightbox="../../media/2020/05/cls.msft.png":::
   レイアウトシフトの詳細  
:::image-end:::  

### 本体のより正確な promise 用語  

ログインしたときに、 `Promise` **コンソール** の値が正しく指定されて `PromiseStatus` `resolved` いません。  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="以前の解決された用語を使用した本体の例" lightbox="../../media/2020/05/resolved.msft.png":::
   古い用語を使用した**本体**の例 `resolved`  
:::image-end:::  

これで、 **本体** で指定された用語が使用されるようになりました `fulfilled` `Promise` 。  仕様の詳細につい `Promise` ては、「 [GitHub の状態と Fates](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)」を参照してください。  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="新しいフルフィルメント用語を使用した本体の例" lightbox="../../media/2020/05/fulfilled.msft.png":::
  新しい用語を使用した**本体**の例 `fulfilled`  
:::image-end:::  

V8 の問題 [#6751][CRV86751]  

### スタイルウィンドウの更新  

#### Revert キーワードのサポート  

[ **スタイル** ] ウィンドウのオートコンプリート UI で、[CSS の [元に戻す][MDNRevert] ] キーワードが検出されるようになりました。これにより、プロパティのカスケード値が、要素のスタイル設定に適用された前の値に戻ります。  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="元に戻すプロパティの値を設定する" lightbox="../../media/2020/05/revert.msft.png":::
  元に戻すプロパティの値を設定する  
:::image-end:::  

Chromium の問題 [#1075437][CR1075437]  

#### イメージのプレビュー  

[スタイル] ウィンドウの値の上にマウスポインターを置くと、 `background-image` ヒントに画像のプレビューが表示されます。 **Styles**  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="背景画像の値の上にマウスポインターを置く" lightbox="../../media/2020/05/image-preview.msft.png":::
  値の上にマウスポインターを置く `background-image`  
:::image-end:::  

Chromium の問題 [#1040019][CR1040019]  

#### カラーピッカーでスペースで区切られた機能カラー表記が使用されるようになりました  

[CSS カラーモジュールレベル 4][CSSWGDraftsColor4Changes3] では、などのカラー関数でスペース区切り引数をサポートすることを指定し `rgb()` ます。  たとえば、`rgb(0, 0, 0)` は `rbg(0 0 0)` と同じです。  

[**スタイル**] ウィンドウで、値を保持して選択することにより、[カラーピッカー][DevtoolsCssReferenceColorPicker]で色を選ぶか、色表現の代わりに色を選ぶと `Shift` `background-color` 、スペース区切りの引数構文が表示されます。  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="[スタイル] ウィンドウでスペースで区切られた引数を使用する" lightbox="../../media/2020/05/color.msft.png":::
  [ **スタイル** ] ウィンドウでスペースで区切られた引数を使用する  
:::image-end:::  

また、 **計算** されるウィンドウと **検査モード** のヒントで構文を確認する必要があります。  

Microsoft Edge DevTools では、新しい構文が使用されています。これは、 [color ()][CSSWGDraftsColor4Property] などの CSS 機能では、非推奨のコンマ区切り引数構文がサポートされていないためです。  

スペース区切りの引数構文は、ほとんどのブラウザーでしばらくサポートされています。  詳細については、「[スペースで区切られた機能カラー表記][CaniuseMDNSpaceSeparatedFunctionalColorNotations]」を参照してください。  

Chromium の問題 [#1072952][CR1072952]  

### [要素] パネルの [プロパティ] ウィンドウの廃止  

[**要素**] パネルの [**プロパティ**] ウィンドウは使われなくなりました。  `console.dir($0)`代わりに**本体**で実行します。  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text="廃止されたプロパティのウィンドウ" lightbox="../../media/2020/05/properties.msft.png":::
   廃止された **プロパティ** のウィンドウ  
:::image-end:::  

#### 参考資料  

*   [console. dir ()][DevtoolsConsoleApiDir]  
*   [$0][DevtoolsConsoleUtilitiesDom]  

### [マニフェスト] ウィンドウでのアプリのショートカットのサポート  

アプリのショートカットを使用すると、web アプリ内で一般的または推奨されるタスクをすばやく開始できます。  アプリのショートカットメニューは、ユーザーのデスクトップまたはモバイルデバイスにインストールされている [プログレッシブ Web アプリ][PwaIndex] についてのみ表示されます。  

<!--For more information, see [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text="[マニフェスト] ウィンドウのアプリのショートカット" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  [ **マニフェスト** ] ウィンドウのアプリのショートカット  
:::image-end:::  

## Microsoft Edge preview チャネルをダウンロードする  

Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge Devtools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools の設定アイコン"
[ImageScreencastingIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/images/toggle-screencast-icon.msft.png "DevTools トグル Screencasting アイコン"
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-page-icon.msft.png "DevTools のパフォーマンスパネルのページの更新アイコン"
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png "DevTools のパフォーマンスパネルのレコードアイコン"

<!-- links -->  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用する |Microsoft ドキュメント"

[DevtoolsConsoleApiDir]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir-本体 API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesDom]: /microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選んだ要素または JavaScript オブジェクト-コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "カラーピッカーで色を変更する-CSS リファレンス |Microsoft ドキュメント"  
[DevToolsDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "引き出し-概要のカスタマイズ |Microsoft ドキュメント"  
[DevToolsChromiumGuide]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "Microsoft Edge DevTools の [問題] タブの問題を見つけて解決する |Microsoft ドキュメント"  
[DevToolsRemoteDebugAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "Android デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  
[DevToolsRemoteDebugDuoEmulator]: /microsoft-edge/devtools-guide-chromium/remote-debugging/surface-duo-emulator "リモートデバッグ Surface Duo エミュレーターの概要 |Microsoft ドキュメント"  
[DevToolsRemoteDebugWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  
[DevToolsNetworkDetails]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "リソースの詳細を調べる |Microsoft ドキュメント"  
[DevToolsNetworkLog]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワークアクティビティのログ |Microsoft ドキュメント"  
[PwaIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows のプログレッシブ Web アプリ |Microsoft ドキュメント"  
<!--[DevtoolsWhatsNew201901Inspect]: /microsoft-edge/devtools-guide-chromium/whats-new/2019/01/devtools#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android アプリ"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "スペースで区切られた機能カラーの表記法-MDN |使用できますか"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"

[CR174309]: https://crbug.com/174309 "DevTools: キーボードショートカット/キーバインディングのカスタマイズを許可する |Chromium のバグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG に準拠していません |Chromium のバグ"  
[CR1040019]: https://crbug.com/1040019 "DevTools: [スタイル] ウィンドウで画像や背景画像を簡単にプレビューできます。Chromium のバグ"  
[CR1040025]: https://crbug.com/1040025 "DevTools: 要素 popover での基本的な a11y 情報の表示 |Chromium のバグ"  
[CR1048378]: https://crbug.com/1048378 "DevTools UI のハイコントラストモードのサポート |Chromium のバグ"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromium のバグ"  
[CR1068116]: https://crbug.com/1068116 "出荷問題パネル |Chromium のバグ"  
[CR1072952]: https://crbug.com/1072952 "DevTools: color picker は、モダン CSS の色の構文を生成する必要があります。Chromium のバグ"  
[CR1075437]: https://crbug.com/1075437 "DevTools: CSS ' revert ' キーワード/値のサポートを追加します。Chromium のバグ"  
[CR1076112]: https://crbug.com/1076112 "Devtools の個人用設定-引き出しのポインター"  
[CR1081486]: https://crbug.com/1081486 "キーボードフォーカスは、screencast モードのナビゲーションボタンには表示されません。Chromium のバグ"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus は「フルフィルメント」であり、「解決済み」ではないV8 のバグ"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 "色の変更 3-CSS の色モジュールレベル 4 |W3C CSS ワーキンググループエディターの下書き"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. フォアグラウンド色: ' color '-CSS カラーモジュールレベル 4 |W3C CSS ワーキンググループエディターの下書き"  

[DesktopEdge]: https://www.microsoft.com/edge/ "新しい Microsoft Edge の紹介"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "州と Fates-domenic/promise-ラップする |GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "元に戻す |MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "ブラウザーの互換性 |MDN"  

[VSCode]: https://code.visualstudio.com/ "Visual Studio コード"  
[VSCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Windows 用 Visual Studio コードのキーボードショートカット"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "アックス: キーボード |Web ヒント"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "アックス: Name Role 値 |Web ヒント"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "Windows でハイコントラストモードをオンまたはオフにする |Windows のサポート"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題-Microsoft のドキュメント/エッジ-開発者"  
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
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2020/05/devtools/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
