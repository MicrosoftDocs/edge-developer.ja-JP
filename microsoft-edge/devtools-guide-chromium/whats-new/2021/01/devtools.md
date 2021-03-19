---
description: 新機能ツールが Welcome になりました。[スタイル] ウィンドウの Visual Font Editor、CSS Flexbox デバッグ ツールなど。
title: DevTools の新機能 (Microsoft Edge 89)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/15/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.localizationpriority: high
ms.openlocfilehash: f04884c4022394ad96f1bd47236047d16ae5ccb9
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439648"
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
# <a name="whats-new-in-devtools-microsoft-edge-89"></a>DevTools の新機能 (Microsoft Edge 89)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="whats-new-is-now-welcome"></a>新機能が Welcome になりました  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Microsoft Edge DevTools の **新機能** ツールに新しい外観と新しい名前ができあがりました:  **Welcome**。  **Welcome** ツールでは、最新の DevTools ニュースと更新プログラムが引き続き表示されます。  また、Microsoft Edge DevTools のドキュメントへのリンク、フィードバックの送信方法なども含まれています。  Microsoft Edge への更新後 **Welcome** ツールを表示するには、タイトルで **更新ごとにタブを開く** の横にあるチェック ボックスを選択します。  **Welcome** ツールを閉じるには、タブ タイトルの右側にある **[X]** を選択します。  元の **新機能** ツールを使用する場合は、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**Welcome タブを有効にする** の横にあるチェック ボックスを選択します。  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="Welcome ツールが強調表示されます" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   **Welcome** ツールが強調表示されます  
:::image-end:::  

## <a name="visual-font-editor-in-the-styles-pane"></a>[スタイル] ウィンドウの Visual Font Editor  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

CSS でフォントを使用する場合は、新しい Visual [Font Editor][DevtoolsInspectStylesEditFonts] を使用します。  フォールバック フォントを定義しスライダーを使用して、フォントの太さ、サイズ、線の高さ、間隔を定義できます。  **Font Editor** を使用すると次のアクションを実行できます。  

*   異なるフォント プロパティの単位を切り替える  
*   異なるフォント プロパティのキーワードを切り替える  
*   単位を変換  
*   正確な CSS コードを生成  
    
この実験を有効にするには、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**[スタイル] ウィンドウ内の Visual Font Editor ツールを有効にする** の横にあるチェック ボックスを選択します。  詳細については、[DevTools の [スタイル] ウィンドウで CSS フォント スタイルと設定を編集][DevtoolsInspectStylesEditFonts] に移動します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1093229][CR1093229] に移動します。  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="[スタイル] ウィンドウで Visual Font Editor が強調表示されます" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   **スタイル** ウィンドウで Visual **Font Editor** が強調表示されます  
:::image-end:::  

## <a name="css-flexbox-debugging-tools"></a>CSS Flexbox デバッグ ツール  

Flexbox のデバッグ機能は、開発途中です。  次の 2 つの機能の実験を有効にするには、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**新しい CSS Flexbox デバッグ機能を有効にする** の横にあるチェック ボックスを選択します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1136394][CR1136394] と [1139949][CR1139949] に移動します。  

### <a name="new-flexbox-flex-icon-helps-identify-and-display-flex-containers"></a>新しい Flexbox (flex) アイコンを使用すると、flex コンテナーの識別と表示ができます。  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

**要素** ツールで、新しい Flexbox (flex) アイコンを使用すると、コード内の Flexbox コンテナーを識別できます。  Flexbox \(flex\) アイコンを選択すると、Flexbox コンテナーのアウトラインを示すオーバーレイ効果を有効または無効にできます。  **スタイル** ウィンドウと **計算済み** ウィンドウの横にある**レイアウト** ウィンドウでオーバーレイの色をカスタマイズできます。  

:::row:::
   :::column span="":::
      Flexbox コンテナーのアウトラインを示すオーバーレイ効果を有効または無効にするには、Flexbox \(`flex`\) アイコンを選択します。  
   :::column-end:::
   :::column span="":::
      **スタイル** ウィンドウと **計算済み** ウィンドウの横にある**レイアウト** ウィンドウでオーバーレイの色をカスタマイズできます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="Flexbox (flex) アイコンと Web ページを強調表示しました" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         **Flexbox** \(`flex`\) アイコンと Web ページを強調表示しました :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text="Flexbox オーバーレイをレイアウト ウィンドウで強調表示しました" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         **Flexbox オーバーレイ** を **レイアウト** ウィンドウで強調表示しました  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-alignment-icons-and-gridlines-when-flexbox-layouts-change-using-css-properties"></a>CSS プロパティを使用して Flexbox レイアウトが変更された場合に配置アイコンとグリッド線を表示  

<!--  Title: Display alignment icons and gridlines for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Flexbox レイアウトの CSS を編集すると、関連する Flexbox プロパティの横に便利なアイコンが表示されるようになった **スタイル** ウィンドウで CSS のオートコンプリートが行われます。  この新機能を試す場合は、**要素** ツールを開き任意の flex コンテナーを選択します。  次に、**スタイル** ウィンドウでそのコンテナーに任意のプロパティを追加または変更します。  

:::row:::
   :::column span="":::
      オートコンプリート メニューには、`align-content` や `align-items` のような配置プロパティの効果を示すアイコンが表示されるようになりました。  
   :::column-end:::
   :::column span="":::
      さらに、DevTools には ガイドラインが表示され、`align-items` CSS プロパティを詳細に確認できるようになりました。  `gap` CSS プロパティもサポートされています。  次の図では、`gap` CSS プロパティが `gap: 12px;` に設定され、各ギャップのハッチング パターンが表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text="align- で始まる CSS プロパティへのオートコンプリート メニューを強調表示しました" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         CSS プロパティへのオートコンプリート メニューを強調表示しました `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS プロパティと Web ページの Flexbox ギャップを強調表示しました" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         CSS プロパティと Web ページの Flexbox `gap` を強調表示しました  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="add-tools-quickly-with-new-more-tools-button"></a>新しい [その他のツール] ボタンを使用してツールをすばやく追加  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

これで、他のツールを Microsoft Edge DevTools で開く新しい方法が使用できるようになりました。  この実験を有効にすると、**その他のツール** アイコンは、メイン パネルの右側にプラス記号 ( `+` ) で表示されます。  メイン パネルに追加する他のツールの一覧を表示するには、**その他のツール** \(`+`\) アイコンを選択します。  この実験を有効にするには、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**+ ボタン タブ メニューを有効にしてその他のツールを開く** の横にあるチェック ボックスを選択します。  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="その他のツールを DevTools で強調表示しました" lightbox="../../media/2021/01/more-tools.msft.png":::
   **その他のツール** を DevTools で強調表示しました  
:::image-end:::  

## <a name="assistive-technologies-now-announce-position-and-count-of-css-suggestions"></a>支援技術では CSS 候補の位置と数を発表しています  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

CSS を編集すると、機能のドロップダウンが表示されます。  この機能は Microsoft Edge バージョン 89 で発表されているので、支援技術のユーザーは利用できません。  支援技術のユーザーは、**スタイル** ウィンドウで CSS 候補に移動できます。  Microsoft Edge バージョン 88 以前には、**スタイル** ウィンドウで CSS を編集する場合、支援技術で候補リストから移動したユーザーを `Suggestion` と表現していました。  Microsoft Edge バージョン 89 では、支援技術のユーザーが現在の提案の位置と数を確かめることがきます。  各提案では、候補リストから移動したユーザーを提案 3/5 などのように表現しています。  DevTools での CSS 記述方法に関するの詳細は、[CSS を変更][DevtoolsCssReferenceChangeCss] に移動します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1157329][CR1157329]に移動します。  

この実験を有効にした状態で、ビデオで提案を表示しながら読み上げを聞くには、YouTube で [devtools オプションのボイスオーバー](https://youtu.be/9TcUpleEwwA) に移動します。  

:::image type="complex" source="../../media/2021/01/announce-css-suggestion.msft.png" alt-text="候補を [スタイル] ウィンドウで強調表示しました" lightbox="../../media/2021/01/announce-css-suggestion.msft.png":::
   `suggestion` リストを **スタイル** ウィンドウで強調表示しました  
:::image-end:::  

## <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a>Surface Duo と Samsung Galaxy Fold のエミュレート  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

Microsoft Edge の次のデバイスで、Web サイトの外観やアプリの外観をテストします。  

*   [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [Samsung Galaxy Fold][SamsungUsMobileGalaxyFold]  
    
**実験用 Web プラットフォーム機能をオン** にし、新しい [CSS メディアの画面スパン機能][DualScreenWebCssMediaSpanning] と [getWindowSegments JavaScript API][DualScreenWebJavascriptGetwindowsegments] にアクセスします。  `edge://flags` まで移動し、**実験用 Web プラットフォーム機能** 横にあるフラグの設定を切り替えます。  デュアルスクリーン デバイスと折りたたみ式デバイスのために Web サイトやアプリを強化するには、[デバイスをエミュレート][DevtoolsDeviceModeIndex]するときに次の機能を使用します。  

*   [スパニング][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: Web サイト (またはアプリ) が両方の画面に表示されます。  
*   [シームのレンダリング][DualScreenIntroductionHowToWorkWithSeam]: シームとは、2 つの画面の間の領域のことです。  
    
Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1054281][CR1054281] に移動します。  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="デュアルスクリーンをエミュレート" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   デュアルスクリーンをエミュレート  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-112"></a>Visual Studio Code バージョン 1.1.2 用 Microsoft Edge 開発者ツール  

[Visual Studio Code 用 Microsoft Edge 開発者ツール][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]拡張バージョン 1.1.2。前回リリース以降に Microsoft Visual Studio コードで次の変更がありました。  Microsoft Visual Studio Code では拡張機能を自動的に更新しています。  バージョン 1.1.2 に手動で更新するには、[拡張機能を手動で更新][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually] に移動します。  

*   ターゲット リストの各アイテムに **インスタンスを閉じる** ボタンを追加しました \([#248][GithubMicrosoftVscodeEdgeDevtoolsPull248]\)  
*   84.0.522.63 から [85.0.564.40][DevtoolsWhatsNew85] に[Microsoft Edge DevTools][DevtoolsMain] バージョンを更新しました \([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235]\)  
*   依存関係として [Microsoft Edge 用デバッガー][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] が含まれました  \([#233][GithubMicrosoftVscodeEdgeDevtoolsPull233]\)  
*   設定オプションを実装して、拡張テーマを変更しました \([#229][GithubMicrosoftVscodeEdgeDevtoolsPull229]\)  
    
[vscode-edge-devtools GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]で問題をファイルすると、拡張機能に貢献できます。  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="capture-node-screenshot-beyond-viewport"></a>ビューポート以外のノードのスクリーンショットをキャプチャ  

Microsoft Edge バージョン 89 では、ノードのスクリーンショットはもっと精度が高く、ノードのコンテンツがビューポートに表示されない場合でも、ノード全体をキャプチャできます。  **要素** ツールで、要素にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、**ノードのスクリーンショットをキャプチャ**を選択します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1003629][CR1003629] に移動します。  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="[ノードのスクリーンショットをキャプチャ] を要素ツールのコンテキスト メニューで強調表示しました" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   **ノードのスクリーンショットをキャプチ** を **要素** ツールのコンテキスト メニューで強調表示しました  
:::image-end:::  

### <a name="elements-tool-updates"></a>要素ツールの更新  

#### <a name="support-forcing-the-target-css-state"></a>:target CSS 強制をサポート  

DevTools を使用して、[:target][MdnDocsWebCssTarget] CSS 擬似クラスを強制的に適用できるようになりました。  `:target` 擬似クラスは、一意の要素 \(the target element\) に URL のフラグメントと一致する `id` がある場合にトリガーされます。  たとえば、`http://www.example.com/index.html#section1` URL は `id="section1"` を使用して HTML 要素の `:target` 擬似クラスをトリガーします。  セクション 1 が強調表示されたデモを試す場合は、[CSS :target デモ][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1] に移動します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1156628][CR1156628] に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="Web ページを強制的に CSS を適用しないで強調表示しました" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         Web ページを強制的に CSS を適用しないで強調表示しました  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text=":target CSS を強制的に適用し、Web ページを強調表示しました" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` CSS を強制的に適用し、Web ページを強調表示しました  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <a name="use-duplicate-elements-to-copy-elements"></a>[要素を複製] を使用して要素をコピー  

新しい **要素を複製** ショートカットを使用して要素をコピーします。  **要素** ツールで、要素にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、**要素を複製**を選択します。  選択した要素の下に新しい要素が作成されます。  キーボード ショートカットを使用して要素を複製するには、`Shift`+`Alt`+`Down Arrow` \(Windows/Linux\) または `Shift`+`Option`+`Down Arrow` \(macOS\) を選択します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1150797][CR1150797] に移動します。  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="[要素を複製] が [要素] ツールの要素の上にあるコンテキスト メニューで強調表示されます" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   **要素を複製** が **要素** ツールの要素の上にあるコンテキスト メニューで強調表示されます  
:::image-end:::  

#### <a name="color-pickers-for-custom-css-properties"></a>カスタム CSS プロパティのカラー ピッカー  

**スタイル** ウィンドウ に、カスタム CSS プロパティのカラー ピッカーが表示されます。  色の値の RGBA、HSLA、および Hex 形式を循環させるには、`Shift` を長押ししてカラー ピッカー選択します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1147016][CR1147016] に移動します。  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="カスタム CSS プロパティのカラー ピッカー" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   カスタム CSS プロパティのカラー ピッカー  
:::image-end:::  

#### <a name="copy-css-classes-and-properties"></a>CSS クラスとプロパティをコピー  

コンテキスト メニューでいくつかの新しいオプションを使用して、CSS プロパティを簡単にコピーできます。  **要素** ツールで、任意の要素を選択します。  値をコピーするには、**スタイル** ウィンドウで CSS クラスまたは CSS プロパティにマウス ポインターを置いてから、コンテキスト メニュー \(右クリック\) を開き、コピー オプションを選択します。  

:::row:::
   :::column span="":::
      CSS クラスのオプションをコピーします。  
      
      | オプション | 詳細 |  
      |:--- |:--- |  
      | **セレクターをコピー** | 現在のセレクター名をコピーします。 |  
      | **ルールをコピー** | 現在のセレクターのルールをコピーします。 |  
      | **すべての宣言をコピー** | 現在のルールで無効なプロパティとプレフィックス付きプロパティを含むすべての宣言をコピーします。 |  
   :::column-end:::
   :::column span="":::
      CSS プロパティのオプションをコピーします。  
      
      | オプション | 詳細 |      
      |:--- |:--- |  
      | **宣言をコピー** | 現在の行の宣言をコピーします。 |  
      | **プロパティをコピー** | 現在の行のプロパティをコピーします。 |  
      | **値をコピー** | 現在の行の値をコピーします。 |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="コンテキスト メニューで CSS クラスのオプションをコピー" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         コンテキスト メニューで CSS クラスのオプションをコピー  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="コンテキスト メニューの CSS プロパティのオプションをコピー" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         コンテキスト メニューの CSS プロパティのオプションをコピー  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1152391][CR1152391] に移動します。  

### <a name="cookies-updates"></a>Cookie の更新  

#### <a name="new-option-to-display-url-decoded-cookies"></a>URL デコードされた Cookie を表示する新しいオプション  

これで、**Cookie** ウィンドウで URL デコードされた Cookie の値を表示できるようになりました。  デコードされた Cookie を表示するには、**アプリケーション** > **Cookie** ウィンドウの順に移動し、リストで任意の Cookie を選択してから**URL デコードを表示** の横にあるチェック ボックスを選択します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [997625][CR997625] に移動します。  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="URL デコードされた Cookie を表示するオプション" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   URL デコードされた Cookie を表示するオプション  
:::image-end:::  

#### <a name="filter-and-clear-visible-cookies"></a>表示される Cookie をフィルター処理してクリア  

Microsoft Edge バージョン 88 以前では、**アプリケーション** ツールでは **すべての Cookie をクリア** ボタンを使用して、すべての Cookie をクリアする方法のみを提供しました。  Microsoft Edge バージョン 89 では、**フィルター処理された Cookie をクリア** を選択して、フィルター処理された Cookie のみを削除できます。  Cookie をフィルター処理するには、**アプリケーション** > **Cookie** の順に移動し、**フィルター処理** テキストボックスに入力します。  表示された Cookie を削除するには、**フィルター処理された Cookie をクリア** ボタンを選択します。  他のすべての Cookie を表示するには、フィルター テキストをクリアします。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [978059][CR978059] に移動します。  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="表示されている Cookie のみをクリア" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   表示されている Cookie のみをクリア  
:::image-end:::  

#### <a name="new-option-to-clear-third-party-cookies-in-the-storage-pane"></a>ストレージ ウィンドウでサードパーティの Cookie をクリアする新しいオプション  

DevTools では、既定でファースト パーティの Cookie のみをクリアします。  Web サイトのデータとファースト パーティの Cookie のみをクリアするには、**アプリケーション** > **ストレージ** の順に移動してから、**サイト データをクリア** を選択します。  

Web サイトのデータとすべての Cookie をクリアするには、**アプリケーション** > **ストレージ** の順に移動します。  **サードパーティの Cookie を含む** の横にあるチェック ボックスを選択して、**サイトのデータをクリア** を選択します。  

Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1012337][CR1012337] に移動します。  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="サードパーティの Cookie をクリアするオプション" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   サードパーティの Cookie をクリアするオプション  
:::image-end:::  

### <a name="network-tool-updates"></a>ネットワーク ツールの更新  

#### <a name="persist-record-network-log-setting"></a>ネットワーク ログの永続記録設定  

Microsoft Edge バージョン 88 以前では、Web ページの更新時に DevTools で **ネットワーク ログを記録** の設定がリセットされていました。  Microsoft Edge バージョン 89 では、**ネットワーク ログを記録** の設定が保存されるようになりました。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1122580][CR1122580] に移動します。  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="ネットワーク ログを記録" lightbox="../../media/2021/01/network-log.msft.png":::
   ネットワーク ログを記録  
:::image-end:::  

#### <a name="online-option-is-now-no-throttling-option"></a>オンライン オプションが調整なしのオプションになりました。  

ネットワーク エミュレーション オプション **オンライン** が **調整なし** に変更されました。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1028078][CR1028078] に移動します。  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="調整オプションなし" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   **調整なし** オプション  
:::image-end:::  

### <a name="new-copy-options-in-the-console-tool-sources-tool-and-styles-pane"></a>[コンソール] ツール、[ソース] ツール、[スタイル] ウィンドウの新しいコピー オプション

#### <a name="copy-object-in-the-console-and-sources-tool"></a>[コンソール] ツール、[ソース] ツールのオブジェクトをコピー  

**[コンソール]** ツールと **[ソース]** ツールでオブジェクトの値をコピーできるようになりました。  オブジェクトの値をコピーする機能は、大きなオブジェクトを操作する場合に便利です。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、問題 [1148353][CR1148353] と問題 [1149859][CR1149859] に移動します。  

:::row:::
   :::column span="":::
      **コンソール** ツール で、オブジェクトにマウス ポインターを置いてから、コンテキスト メニュー \(右クリック\) を開いてから **オブジェクトをコピー** を選択します。  
   :::column-end:::
   :::column span="":::
      **ソース** ツールのブレークポイントで、オブジェクトにマウス ポインターを置き、**オブジェクト** ポップアップ ウィンドウでオブジェクトを強調表示してから、コンテキスト メニュー \(右クリック\) を開いて **オブジェクトをコピー** を選択します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/console-copy-object.msft.png" alt-text="コンソールでオブジェクトをコピー" lightbox="../../media/2021/01/console-copy-object.msft.png":::
         **コンソール** でオブジェクトをコピー  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png" alt-text="ソースでオブジェクトをコピー" lightbox="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png":::
         **ソース** でオブジェクトをコピー  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="copy-file-name-in-the-sources-tool-and-styles-pane"></a>[ソース] ツールと [スタイル] ウィンドウでファイル名をコピー  

これで、コンテキスト メニューを使用してファイル名をコピーできます。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1155120][CR1155120] に移動します。  

:::row:::
   :::column span="":::
      **ソース** ツールで、ファイル名にマウス ポインターを置いて、コンテキスト メニュー \(右クリック\) を開いてから **ファイル名をコピー** を選択します。  
   :::column-end:::
   :::column span="":::
      **要素** ツール > **スタイル** ウィンドウの順に移動して、ファイル名にマウス ポインターを置いてから、コンテキスト メニュー \(右クリック\) を開いて **ファイル名をコピー** を選択します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="[ソース] でファイル名をコピー" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         **ソース** でファイル名をコピー  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="[スタイル] ウィンドウでファイル名をコピー" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         **スタイル** ウィンドウでファイル名をコピー  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="updates-to-frame-details"></a>フレームの詳細の更新  

#### <a name="service-workers-information-in-frame-details"></a>フレームの詳細のサービス ワーカー情報  

DevTools では、親フレームで専用のサービス ワーカーが一覧表示されるようになりました。  次の図では、サービス ワーカーの詳細が表示されます。  サービス ワーカーの詳細を表示するには、**アプリケーション** > **フレーム** > `top` > **サービス ワーカー**の順に移動して、サービス ワーカーを選択します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1122507][CR1122507] に移動します。  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="フレームの詳細のサービス ワーカー情報" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   **フレーム** の詳細の **サービス ワーカー** 情報  
:::image-end:::  

#### <a name="measure-memory-information-in-frame-details"></a>フレームの詳細でメモリ情報を測定  

`performance.measureMemory()`API 状態が、**API 可用性** セクションの下に表示されます。  新しい `performance.measureMemory()` API は、Web ページ全体のメモリ使用量を推定します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1139899][CR1139899] に移動します。  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="メモリを測定" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   メモリを測定  
:::image-end:::  

### <a name="dropped-frames-in-the-performance-tool"></a>パフォーマンス ツールでのフレームをドロップしました  

[パフォーマンス ツールで読み込みパフォーマンスを分析][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance] する場合、**フレーム** セクションではドロップされたフレームが赤でマークされます。  フレーム レートを表示するには、ドロップしたフレームにマウス ポインターを置きます。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1075865][CR1075865] に移動します。  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="フレームをドロップしました" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   フレームをドロップしました  
:::image-end:::  

#### <a name="new-color-contrast-calculation---advanced-perceptual-contrast-algorithm-apca"></a>新しいカラー コントラスト計算 - 高度な知覚コントラスト アルゴリズム (APCA)  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

[高度な知覚コントラスト アルゴリズム (APCA)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] は、[カラー ピッカー][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker] の [AA][W3cWaiWcag21QuickrefContrastMinimum]/[AAA][W3cWaiWcag21QuickrefContrastEnhanced] ガイドラインのコントラスト比を置き換えます。  APCA は、コントラストを計算する新しい方法です。  これは、色覚に関する最新の研究に基づいています。  AA/AAA ガイドラインと比較すると、APCA はコンテキストに依存します。  コントラストは、テキスト、色、コンテキストの次の空間プロパティに基づいて計算されます。  

*   フォントの太さとサイズが含まれるテキストの空間プロパティ。  
*   テキストと背景間で認識されているコントラストが含まれる色彩空間プロパティ。  
*   環境光、周囲、および目的の意図が含まれるコンテキスト空間プロパティ。  
    
この実験を有効にするには、[設定][DevtoolsCustomizeIndexSettings] > **実験** の順に移動し、**以前のコントラスト比と AA/AAA ガイドラインを置き換える高度な知覚コントラスト アルゴリズム (APCA) を有効にする** の横にあるチェック ボックスを選択します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1121900][CR1121900] に移動します。  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="カラー ピッカーの APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   カラー ピッカーの APCA  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロード  

Windows、Linux、または macOS を使用している場合は、既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] の使用を検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "DevTools (Microsoft Edge 85) の新機能 | Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "カラー ピッカー - アクセシビリティ リファレンス ページでテキスト要素のコントラスト比を表示 | Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "CSS の変更 - CSS 参照|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "折りたたみ可能なデバイスとデュアルスクリーン デバイスでのテスト - Microsoft Edge DevTools でデュアルスクリーン デバイスと折りたたみ可能なデバイスをエミュレート | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイル ビューポートのシミュレート - Microsoft Edge DevTools でモバイル デバイスをエミュレート | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "レコードの読み込みパフォーマンス - パフォーマンス分析リファレンス | Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集 | Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 開発者ツールの概要 |Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "セクション 1 - DevTools 新機能への CSS :target デモ(Microsoft Edge 89) |GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "プル 229: 設定でドロップダウンを実装して、テーマを変更 | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "プル 233: 依存関係として Microsoft Edge 用デバッガーを含む | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "プル 235: Microsoft Edge DevTools バージョンを 85.0.564.40 にアップグレード | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "プル 248: インスタンス パネルに 1 つの[閉じる]ボタンを追加 | GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "フォントの特性と背景色を選択して、読みやすいコントラストを設定 | W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "信頼できる型 | W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新しい Surface Duo | Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Visual Studio Code 用 Microsoft Edge Tools |Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  
[CR978059]: https://crbug.com/978059 "問題 978059: フィルター処理時に Cookie を削除する場合、フィルター処理されたものだけでなくすべての Cookie が削除される | Chromium のバグ"  
[CR997625]: https://crbug.com/997625 "問題 997625: 新機能要求 | Cookie で URL デコードされた値を表示するオプションが必要 | Chromium のバグ"  
[CR1003629]: https://crbug.com/1003629 "問題 1003629: ノードをキャプチャする機能でフォールドの下のノードをスクリーンショットできない。 | Chromium のバグ"  
[CR1012337]: https://crbug.com/1012337 "問題 1012337: サイトのデータを消去すると、Google 以外のサイトで Google セッションが破棄される | Chromium のバグ"  
[CR1028078]: https://crbug.com/1028078 "問題 1028078: リストで [オンライン] と [オフライン] が並んで表示される | Chromium のバグ"  
[CR1054281]: https://crbug.com/1054281 "問題 1054281: 機能要求: DevTools で、折りたたみ可能デバイスとデュアルスクリーン デバイスをエミュレートする必要がある | Chromium のバグ"  
[CR1075865]: https://crbug.com/1075865 "問題 1075865: DevTools タイムラインにドロップ済みのフレームが表示される | Chromium のバグ"  
[CR1093229]: https://crbug.com/1093229 "問題 1093229: DevTools: 特殊な書体エディター UI を提供 | Chromium のバグ"  
[CR1121900]: https://crbug.com/1121900 "問題 1121900: DevTools: 新しい仕様ごとにコントラスト計算ロジックを更新 | Chromium のバグ"  
[CR1122507]: https://crbug.com/1122507 "問題 1122507: フレーム ツリー ビューでの Surface ワーカー情報 | Chromium のバグ"  
[CR1122580]: https://crbug.com/1122580 "問題 1122580: 再読み込み時にネットワーク記録を無効にできない | Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "問題 1136394: Flexbox ツール | Chromium のバグ"  
[CR1139899]: https://crbug.com/1139899 "問題 1139899: フレーム詳細ビューでゲート API の可用性を報告する | Chromium のバグ"  
[CR1139949]: https://crbug.com/1139949 "問題 1139949: Flexbox オーバーレイ | Chromium のバグ"  
[CR1147016]: https://crbug.com/1147016 "問題 1147016: カラー ピッカーが var() 関数に表示されない。 | Chromium のバグ"  
[CR1148353]: https://crbug.com/1148353 "問題 1148353: 機能要求: DevTools コンソール からオブジェクトをコピー | Chromium のバグ"  
[CR1149859]: https://crbug.com/1149859 "Issue 1149859: [機能要求][コンソール] のコンテキスト メニューに [オブジェクトをクリップボード アイテムにコピー] を追加 | Chromium のバグ"  
[CR1150797]: https://crbug.com/1150797 "問題 1150797: [要素] パネルに要素コンテキスト メニューの複製を追加 | Chromium のバグ"  
[CR1152391]: https://crbug.com/1152391 "問題 1152391: スタイル パネルの CSS コンテキスト メニューのコピーへのサポート | Chromium のバグ"  
[CR1155120]: https://crbug.com/1155120 "問題 1155120: [FR]サポートのコピー ファイル名と行番号 | Chromium のバグ"  
[CR1156628]: https://crbug.com/1156628 "問題 1156628: DevTools: :target 強制要素の状態機能のサポートを追加 | Chromium のバグ"  
[CR1157329]: https://crbug.com/1157329 "問題 1157329: アクセシビリティ - ナレーター: ナレーターで、[スタイル] タブのコードに使用できる候補の数と位置がアナウンスされない | Chromium のバグ"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target ":target | MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "コントラスト (拡張) - WCAGを満たす方法 (クイック リファレンス) | W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "コントラスト (最小) - WCAG を満たす方法 (クイック リファレンス) | W3C"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2021/01/devtools/index)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen

[SpanningPlaceholder]: link-t-b-d "スパニング プレースホルダー"  
