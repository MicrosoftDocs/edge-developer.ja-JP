---
description: '[新機能] ツールがようこそ、スタイル ウィンドウの Visual Font Editor、CSS Flexbox デバッグ ツールなどです。'
title: DevTools の新機能 (Microsoft Edge 89)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2722da0093b3ba6521b5190e61bb208e02a2041e
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408340"
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

## <a name="whats-new-is-now-welcome"></a>新機能はウェルカムです  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Microsoft **Edge DevTools の** [新機能] ツールに新しい外観と新しい名前が追加  **されています**。  ウェルカム **ツールには** 、最新の DevTools ニュースと更新プログラムが引き続き表示されます。  また、Microsoft Edge DevTools のドキュメントへのリンク、フィードバックの送信方法なども含まれています。  Microsoft Edge への更新 **の後** にウェルカム ツールを表示するには、タイトルの更新後に [開く] タブの横 **にあるチェック ボックス** をオンにします。  ようこそツールを **閉** じるには、タブ タイトルの右側にある **[X]** を選択します。  元の [What's **New]** ツールを[][DevtoolsCustomizeIndexSettings]使用する場合は、[設定の実験] に移動し、[ようこそ] タブを有効にするの横にあるチェック  >  ******ボックスをオフにします**。  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="ウェルカム ツールが強調表示されている" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   ウェルカム **ツール** が強調表示されている  
:::image-end:::  

## <a name="visual-font-editor-in-the-styles-pane"></a>[スタイル] ウィンドウの [Visual Font Editor]  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

CSS でフォントを使用する場合は、新しいビジュアル フォント エディター [を使用します][DevtoolsInspectStylesEditFonts]。  フォールバック フォントを定義し、スライダーを使用してフォントの太さ、サイズ、線の高さ、間隔を定義できます。  フォント **エディターを使用すると** 、次のアクションを実行できます。  

*   さまざまなフォント プロパティの単位を切り替える  
*   異なるフォント プロパティのキーワードを切り替える  
*   単位の変換  
*   正確な CSS コードを生成する  
    
この実験を有効にするには、[設定の[][DevtoolsCustomizeIndexSettings]実験] に移動し、[スタイル] ウィンドウの [新しいフォント エディター ツールを有効にする] の横にある  >  ******チェック ボックスをオンにします**。  詳細については [、DevTools][DevtoolsInspectStylesEditFonts]の [スタイル] ウィンドウの [CSS フォントスタイルと設定の編集] に移動します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1093229 に移動します][CR1093229]。  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="[スタイル] ウィンドウでビジュアル フォント エディターが強調表示されます。" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   [スタイル **] ウィンドウで** ビジュアル フォント エディターが **強調表示** されます。  
:::image-end:::  

## <a name="css-flexbox-debugging-tools"></a>CSS Flexbox デバッグ ツール  

Flexbox のデバッグ機能は、アクティブな開発中です。  次の 2 つの機能の実験を有効にするには[][DevtoolsCustomizeIndexSettings]、[設定の実験] に移動し、[新しい CSS Flexbox デバッグ機能を有効にする] の横にあるチェック ボックス  >  ******をオンにします**。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issues [1136394 および 1139949][CR1136394] に [移動][CR1139949]します。  

### <a name="new-flexbox-flex-icon-helps-identify-and-display-flex-containers"></a>新しい Flexbox (flex) アイコンは、flex コンテナーの識別と表示に役立ちます  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

要素ツール **で** 、新しい Flexbox (flex) アイコンを使用すると、コード内の Flexbox コンテナーを識別できます。  Flexbox コンテナーのアウトラインを示すオーバーレイ効果をオンまたはオフにする場合は、[Flexbox\(flex\)] アイコンを選択します。  [レイアウト] ウィンドウの [スタイルと**** 計算] の横にあるオーバーレイの色**を****カスタマイズできます**。  

:::row:::
   :::column span="":::
      Flexbox コンテナーの輪郭を示すオーバーレイ効果のオンとオフを切り替える場合は、Flexbox \( \) アイコンを `flex` 選択します。  
   :::column-end:::
   :::column span="":::
      [スタイルと計算] の横の [ **レイアウト** ] ウィンドウでオーバーレイの **色** を **カスタマイズできます**。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="強調表示されている Flexbox (flex) アイコンと Web ページ" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         **強調表示されている Flexbox** \( `flex` \) アイコンと Web ページ :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text="レイアウト ウィンドウで強調表示されている Flexbox オーバーレイ" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         レイアウト**ウィンドウで強調表示**されている Flexbox**オーバーレイ**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-alignment-icons-and-gridlines-when-flexbox-layouts-change-using-css-properties"></a>CSS プロパティを使用して Flexbox レイアウトが変更された場合に配置アイコンとグリッド線を表示する  

<!--  Title: Display alignment icons and gridlines for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Flexbox レイアウトの CSS を編集すると、[スタイル] ウィンドウの**** CSS オートコンプリートに、関連する Flexbox プロパティの横に便利なアイコンが表示されます。  この新機能を試す場合は、[要素] ツール **を開** き、flex コンテナーを選択します。  次に、[スタイル] ウィンドウで、そのコンテナーのプロパティを **追加または変更** します。  

:::row:::
   :::column span="":::
      オートコンプリート メニューには、次のような配置プロパティの効果を示すアイコンが表示 `align-content` されます `align-items` 。  
   :::column-end:::
   :::column span="":::
      さらに、DevTools には CSS プロパティの確認に役立つガイドラインが `align-items` 表示されます。  `gap`CSS プロパティもサポートされています。  次の図では `gap` 、CSS プロパティがに設定され、各ギャップの `gap: 12px;` ハッチング パターンが表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text="align- で始まる CSS プロパティで強調表示されたオートコンプリート メニュー" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         で始まる CSS プロパティで強調表示されているオートコンプリート メニュー `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS プロパティと Web ページの Flexbox ギャップが強調表示されている" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         CSS プロパティ `gap` と Web ページの Flexbox が強調表示されている  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="add-tools-quickly-with-new-more-tools-button"></a>新しい [その他のツール] ボタンでツールをすばやく追加する  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

これで、Microsoft Edge DevTools で他のツールを開く新しい方法が追加されています。  この実験を有効にした後、[ **その** 他のツール] アイコンは、メイン パネルの右側にプラス記号 ( `+` ) として表示されます。  メイン パネルに追加する他のツールの一覧を表示するには、[その他のツール] **\(** `+` \) アイコンを選択します。  この実験を有効にするには、[設定の[][DevtoolsCustomizeIndexSettings]実験] に移動し、[有効にする] + [ボタン] タブ メニューの横にあるチェック ボックスをオンにして、その他のツール  >  ******を開きます**。  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="DevTools で強調表示されているその他のツール" lightbox="../../media/2021/01/more-tools.msft.png":::
   **DevTools** で強調表示されているその他のツール  
:::image-end:::  

## <a name="assistive-technologies-now-announce-position-and-count-of-css-suggestions"></a>支援テクノロジが CSS の提案の位置と数を発表する  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

CSS を編集すると、機能のドロップダウンが表示されます。  この機能は、Microsoft Edge バージョン 89 で発表されたので、支援テクノロジのユーザーは利用できません。  支援テクノロジのユーザーが、[スタイル] ウィンドウで CSS 候補を **移動する場合** があります。  Microsoft Edge バージョン 88 以前では、ユーザーとして発表された支援テクノロジは、[スタイル] ウィンドウで CSS を編集するときに提案の一覧を `Suggestion` **移動** しました。  Microsoft Edge バージョン 89 では、支援テクノロジのユーザーが現在の提案の位置と数を聞く。  各提案は、ユーザーが提案の一覧 (5 の提案 3 など) を移動すると発表されます。  DevTools での CSS の記述の詳細については、「CSS の変更」 [に移動します][DevtoolsCssReferenceChangeCss]。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issue [1157329 に移動します][CR1157329]。  

この実験を有効にした状態でいくつかの提案を表示および読み上げるビデオを表示するには、YouTube で [devtools](https://youtu.be/9TcUpleEwwA) オプションを発表する Voiceover に移動します。  

:::image type="complex" source="../../media/2021/01/announce-css-suggestion.msft.png" alt-text="[スタイル] ウィンドウで強調表示されている候補" lightbox="../../media/2021/01/announce-css-suggestion.msft.png":::
   [ `suggestion` スタイル] ウィンドウで強調表示**されているリスト**  
:::image-end:::  

## <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a>Surface Duo と Samsung Galaxy Fold のエミュレート  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

Microsoft Edge の次のデバイスで、Web サイトまたはアプリの外観をテストします。  

*   [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [Samsung Galaxy Fold][SamsungUsMobileGalaxyFold]  
    
実験的な **Web プラットフォーム機能をオン** にし、新しい [CSS メディア画面][DualScreenWebCssMediaSpanning] スパン機能にアクセスし [、getWindowSegments JavaScript API にアクセスします][DualScreenWebJavascriptGetwindowsegments]。  [実験用 `edge://flags` Web プラットフォームの機能] の横にあるフラグ **に移動し、切り替える**。  デュアルスクリーン デバイスと折りたたみ式デバイスのために Web サイトやアプリを強化するには、[デバイスをエミュレート][DevtoolsDeviceModeIndex]するときに次の機能を使用します。  

*   [スパニング][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: Web サイト (またはアプリ) が両方の画面に表示されます。  
*   [シームのレンダリング][DualScreenIntroductionHowToWorkWithSeam]: シームとは、2 つの画面の間の領域のことです。  
    
Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issue [1054281 に移動します][CR1054281]。  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="デュアルスクリーンをエミュレートする" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   デュアルスクリーンをエミュレートする  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-112"></a>Microsoft Edge Developer Tools for Visual Studio コード バージョン 1.1.2  

[Microsoft Edge Developer Tools for Visual Studio コード][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]拡張バージョン 1.1.2 for Microsoft Visual Studio コードは、前のリリース以降に次の変更を加えます。  Microsoft Visual Studioコードは拡張機能を自動的に更新します。  バージョン 1.1.2 に手動で更新するには、[拡張機能を手動で更新 [する] に移動します][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。  

*   ターゲット リスト **の各アイテム** に [インスタンスを閉じる] ボタンを追加しました[\(][GithubMicrosoftVscodeEdgeDevtoolsPull248]#248 \)  
*   84.0.522.63 から[85.0.564.40][DevtoolsWhatsNew85] [\(][GithubMicrosoftVscodeEdgeDevtoolsPull235]#235 \) [][DevtoolsMain]  
*   依存関係 [として Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] 用デバッガーが含まれている[\(][GithubMicrosoftVscodeEdgeDevtoolsPull233]#233 \)  
*   拡張テーマ \( #229 \)[を変更する設定オプションを][GithubMicrosoftVscodeEdgeDevtoolsPull229]実装しました  
    
[vscode-edge-devtools GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]で問題をファイルし、拡張機能に貢献することができます。  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="capture-node-screenshot-beyond-viewport"></a>ビューポートを越えてノードのスクリーンショットをキャプチャする  

Microsoft Edge バージョン 89 では、ノードのスクリーンショットの精度が高く、ノードのコンテンツがビューポートに表示されない場合でも、ノード全体がキャプチャされます。  [要素 **] ツールで** 、要素にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[キャプチャ] ノードのスクリーンショット **を選択します**。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1003629 に移動します][CR1003629]。  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="要素ツールのコンテキスト メニューで強調表示されているキャプチャ ノードのスクリーンショット" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   **要素ツールのコンテキスト**メニューで強調表示されているキャプチャ ノード**のスクリーンショット**  
:::image-end:::  

### <a name="elements-tool-updates"></a>要素ツールの更新  

#### <a name="support-forcing-the-target-css-state"></a>:target CSS 状態の適用のサポート  

DevTools を使用して、強制的に [:target][MdnDocsWebCssTarget] CSS 擬似クラスを使用できます。  擬似 `:target` クラスは、一意の要素 \(target 要素\) が URL のフラグメントと一致する場合 `id` にトリガーされます。  たとえば `http://www.example.com/index.html#section1` 、URL は、 を使用して HTML 要素の `:target` 擬似クラスをトリガーします `id="section1"` 。  セクション 1 が強調表示されたデモを試す場合は [、[CSS:target demo] に移動します][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1156628 に移動します][CR1156628]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="強制的な CSS で強調表示された Web ページ" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         強制 CSS で強調表示された Web ページ  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text=":target CSS 強制と Web ページの強調表示" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` CSS の強制と Web ページの強調表示  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <a name="use-duplicate-elements-to-copy-elements"></a>要素をコピーするには、Duplicate 要素を使用する  

新しい **Duplicate 要素ショートカットを使用して** 、要素を複製します。  [要素 **] ツールで** 、要素にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[要素の複製] **を選択します**。  選択した要素の下に新しい要素が作成されます。  キーボード ショートカットで要素を複製するには `Shift` + `Alt` + `Down Arrow` 、\(Windows/Linux\) または `Shift` + `Option` + `Down Arrow` \(macOS\) を選択します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issue [1150797 に移動します][CR1150797]。  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="Duplicate 要素は、[要素] ツールの要素のコンテキスト メニューで強調表示されます。" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   **Duplicate 要素は**、[要素] ツールの要素のコンテキスト メニューで**強調表示**されます。  
:::image-end:::  

#### <a name="color-pickers-for-custom-css-properties"></a>カスタム CSS プロパティのカラー ピッカー  

[ **スタイル] ウィンドウ** に、カスタム CSS プロパティのカラー ピッカーが表示されます。  色の値の RGBA、HSLA、および Hex 形式を循環するには、カラー ピッカー `Shift` を長押しして選択します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issue [1147016][CR1147016]に移動します。  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="カスタム CSS プロパティのカラー ピッカー" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   カスタム CSS プロパティのカラー ピッカー  
:::image-end:::  

#### <a name="copy-css-classes-and-properties"></a>CSS クラスとプロパティのコピー  

コンテキスト メニューでいくつかの新しいオプションを使用して、CSS プロパティを迅速にコピーできます。  [要素 **] ツール** で、要素を選択します。  値をコピーするには、[スタイル]**** ウィンドウで CSS クラスまたは CSS プロパティをポイントし、コンテキスト メニュー \(右クリック\) を開き、コピー オプションを選択します。  

:::row:::
   :::column span="":::
      CSS クラスのオプションをコピーします。  
      
      | オプション | 詳細 |  
      |:--- |:--- |  
      | **コピー セレクター** | 現在のセレクター名をコピーします。 |  
      | **コピー ルール** | 現在のセレクターのルールをコピーします。 |  
      | **すべての宣言をコピーする** | 無効なプロパティとプレフィックス付きプロパティを含む、現在のルールの下のすべての宣言をコピーします。 |  
   :::column-end:::
   :::column span="":::
      CSS プロパティのオプションをコピーします。  
      
      | オプション | 詳細 |      
      |:--- |:--- |  
      | **Copy 宣言** | 現在の行の宣言をコピーします。 |  
      | **Copy プロパティ** | 現在の行のプロパティをコピーします。 |  
      | **値のコピー** | 現在の行の値をコピーします。 |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="コンテキスト メニューで CSS クラスのオプションをコピーする" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         コンテキスト メニューで CSS クラスのオプションをコピーする  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="コンテキスト メニューの CSS プロパティのオプションをコピーする" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         コンテキスト メニューの CSS プロパティのオプションをコピーする  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issue [1152391 に移動します][CR1152391]。  

### <a name="cookies-updates"></a>Cookie の更新  

#### <a name="new-option-to-display-url-decoded-cookies"></a>URL デコードされた Cookie を表示する新しいオプション  

これで、[Cookie] ウィンドウに URL デコードされた Cookie の値を **表示** できます。  デコードされた Cookie を表示するには、[**** アプリケーション Cookie] ウィンドウに移動し、一覧で任意の Cookie を選択し、[デコードされた URL を表示する] の横にあるチェック  >  ******ボックスをオンにします**。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [997625 に移動します][CR997625]。  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="URL デコードされた Cookie を表示するオプション" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   URL デコードされた Cookie を表示するオプション  
:::image-end:::  

#### <a name="filter-and-clear-visible-cookies"></a>表示される Cookie をフィルター処理してクリアする  

Microsoft Edge バージョン 88 以前**** では、アプリケーション ツールは[すべての Cookie をクリアする] ボタンを使用してすべての Cookie をクリア**する方法のみを提供**しました。  Microsoft Edge バージョン 89 では、[**** フィルター処理された Cookie のクリア] を選択して、フィルター処理された Cookie のみを削除できます。  Cookie をフィルターするには、[アプリケーション Cookie]**に**  >  **移動**し、[フィルター] テキスト ボックス**に**入力します。  表示された Cookie を削除するには、[フィルター処理された Cookie の **クリア] ボタンを選択** します。  他のすべての Cookie を表示するには、フィルター テキストをクリアします。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [978059 に移動します][CR978059]。  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="表示されている Cookie のみをクリアする" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   表示されている Cookie のみをクリアする  
:::image-end:::  

#### <a name="new-option-to-clear-third-party-cookies-in-the-storage-pane"></a>ストレージ ウィンドウでサードパーティの Cookie をクリアする新しいオプション  

DevTools では、既定でファースト パーティ Cookie のみをクリアしました。  Web サイトデータとファースト パーティ Cookie のみをクリアするには、[**アプリケーション**ストレージ] に移動し、[サイト データのクリア  >  ****]**を選択します**。  

Web サイトのデータとすべての Cookie をクリアするには、[アプリケーション ストレージ]**に**  >  **移動します**。  [サードパーティの Cookie を含む] の **横にあるチェック ボックスをオン**にして、[サイト データのクリア **] を選択します**。  

Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1012337 に移動します][CR1012337]。  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="サードパーティの Cookie をクリアするオプション" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   サードパーティの Cookie をクリアするオプション  
:::image-end:::  

### <a name="network-tool-updates"></a>ネットワーク ツールの更新  

#### <a name="persist-record-network-log-setting"></a>[レコードの保持] ネットワーク ログの設定  

Microsoft Edge バージョン 88 以前では、DevTools は Web ページの更新時にネットワーク ログの記録設定をリセットします。 ****  Microsoft Edge バージョン 89 では、DevTools はレコード ネットワーク ログ **設定を保持** します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1122580 に移動します][CR1122580]。  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="ネットワーク ログの記録" lightbox="../../media/2021/01/network-log.msft.png":::
   ネットワーク ログの記録  
:::image-end:::  

#### <a name="online-option-is-now-no-throttling-option"></a>[オンライン オプション] が [調整なし] オプション  

ネットワーク エミュレーション オプション **Online の** 名前が [調整なし **] に変更されました**。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issue [1028078 に移動します][CR1028078]。  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="調整オプションなし" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   **調整オプション** なし  
:::image-end:::  

### <a name="new-copy-options-in-the-console-tool-sources-tool-and-styles-pane"></a>[コンソール] ツール、ソース ツール、および [スタイル] ウィンドウの新しいコピー オプション

#### <a name="copy-object-in-the-console-and-sources-tool"></a>[コンソールとソース] ツールのオブジェクトをコピーする  

[コンソール] ツールと [ソース] **ツールでオブジェクト** 値 **をコピー** できます。  オブジェクト値をコピーする機能は、大きなオブジェクトを操作する場合に便利です。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issues [1148353 および 1149859][CR1148353] に [移動][CR1149859]します。  

:::row:::
   :::column span="":::
      コンソール ツール **で、** オブジェクトにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[オブジェクトのコピー] **を選択します**。  
   :::column-end:::
   :::column span="":::
      [ソース **]** ツールのブレークポイントで、オブジェクトにマウス ポインターを置き****、[オブジェクト] ポップアップ ウィンドウでオブジェクトを強調表示し、コンテキスト メニュー \(右クリック\) を開き、[オブジェクトのコピー] を選択します。 ****  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/console-copy-object.msft.png" alt-text="コンソールでオブジェクトをコピーする" lightbox="../../media/2021/01/console-copy-object.msft.png":::
         コンソールでオブジェクトをコピー **する**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png" alt-text="Sources のオブジェクトをコピーする" lightbox="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png":::
         Sources の **オブジェクトをコピーする**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="copy-file-name-in-the-sources-tool-and-styles-pane"></a>[ソース] ツールと [スタイル] ウィンドウでファイル名をコピーする  

これで、コンテキスト メニューを使用してファイル名をコピーできます。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[問題 [1155120] に移動します][CR1155120]。  

:::row:::
   :::column span="":::
      [ソース **] ツールで** 、ファイル名をホバーし、コンテキスト メニュー \(右クリック\) を開き、[ファイル名のコピー] **を選択します**。  
   :::column-end:::
   :::column span="":::
      [要素] **ツール** の **[>] ウィンドウ** で、ファイル名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[ファイル名のコピー] を **選択します**。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="[ソース] のファイル名をコピーする" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         [ソース] のファイル **名をコピーする**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="[スタイル] ウィンドウでファイル名をコピーする" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         [スタイル] ウィンドウでファイル **名をコピー** する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="updates-to-frame-details"></a>フレームの詳細の更新  

#### <a name="service-workers-information-in-frame-details"></a>フレームの詳細のサービス ワーカー情報  

DevTools には、親フレームの下に専用のサービス ワーカーが一覧表示されます。  次の図では、サービス ワーカーの詳細が表示されます。  サービス ワーカーの詳細を表示するには **、[Application**Frames Service Workers] に移動し、  >  ****  >  `top`  >  **** サービス ワーカーを選択します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1122507 に移動します][CR1122507]。  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="フレームの詳細のサービス ワーカー情報" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   **フレームの詳細**のサービス ワーカー**情報**  
:::image-end:::  

#### <a name="measure-memory-information-in-frame-details"></a>フレームの詳細でメモリ情報を測定する  

API `performance.measureMemory()` の状態が [API 可用性] セクション **の下に表示** されます。  新しい `performance.measureMemory()` API は、Web ページ全体のメモリ使用量を推定します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1139899 に移動します][CR1139899]。  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="メモリの測定" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   メモリの測定  
:::image-end:::  

### <a name="dropped-frames-in-the-performance-tool"></a>パフォーマンス ツールでのフレームのドロップ  

パフォーマンス ツール[で読み込みパフォーマンスを分析すると、[][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]フレーム] セクションでドロップされたフレームが赤でマークされます。 ****  フレームレートを表示するには、ドロップしたフレームにカーソルを合わせる。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1075865 に移動します][CR1075865]。  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="ドロップされたフレーム" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   ドロップされたフレーム  
:::image-end:::  

#### <a name="new-color-contrast-calculation---advanced-perceptual-contrast-algorithm-apca"></a>新しいカラー コントラスト計算 - Advanced Perceptual Contrast Algorithm (APCA)  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

高度[な知覚コントラスト アルゴリズム (APCA) は][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]、カラー ピッカーの[AA][W3cWaiWcag21QuickrefContrastMinimum]AAA ガイドラインのコントラスト比に置 / [][W3cWaiWcag21QuickrefContrastEnhanced][き換えてください][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]。  APCA は、コントラストを計算する新しい方法です。  これは、色知覚に関する最新の研究に基づいて行います。  AA/AAA ガイドラインと比較して、APCA はコンテキストに依存します。  コントラストは、テキスト、色、コンテキストの次の空間プロパティに基づいて計算されます。  

*   フォントの太さおよびサイズを含むテキストの空間プロパティ。  
*   テキストと背景のコントラストを含む色の空間プロパティ。  
*   環境光、周囲、および目的を含むコンテキストの空間プロパティ。  
    
この実験を有効にするには、[設定の[][DevtoolsCustomizeIndexSettings]実験] に移動し、[以前のコントラスト比と AA/AAA ガイドラインを置き換える新しい高度な知覚コントラスト アルゴリズム  >  ******(APCA)** を有効にする] の横にあるチェック ボックスをオンにします。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、Issue [1121900 に移動します][CR1121900]。  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="カラー ピッカーの APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   カラー ピッカーの APCA  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows、Linux、または macOS を使用している場合は、 [既定][MicrosoftEdgePreviewChannels] の開発ブラウザーとして Microsoft Edge プレビュー チャネルの使用を検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "DevTools (Microsoft Edge 85) の新機能 |Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "Color Picker - アクセシビリティ リファレンス ページでテキスト要素のコントラスト比を表示|Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "CSS の変更 - CSS 参照|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "折りたたみおよびデュアルスクリーン デバイスでのテスト - Microsoft Edge DevTools アプリケーションでデュアルスクリーンおよび折りたたみ可能なデバイスをエミュレート|Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイル ビューポートのシミュレート - Microsoft Edge DevTools アプリケーションでモバイル デバイスをエミュレート|Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "レコードの読み込みパフォーマンス - パフォーマンス分析リファレンス |Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 開発者ツールの概要 |Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "セクション 1 - CSS :DevTools の新機能のターゲット デモ (Microsoft Edge 89) |GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "プル 229: 設定でドロップダウンを実装して、テーマの設定を変更|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "プル 233: 依存関係ファイルとして Microsoft Edge 用デバッガーを含|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "プル 235: Edge DevTools バージョンを 85.0.564.40 バージョンにアップグレード|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "プル 248: インスタンス パネルに 1 つの閉じるボタンを追加|GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "フォントの特性と背景色を選択して、読みやすさを向上するために十分な|W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "信頼できる型|W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新しい Surface Duo |Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 Marketplace |Visual Studioコード"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio コード |Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge アプリケーションのデバッガー|Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "クロムのバグ"  
[CR978059]: https://crbug.com/978059 "問題 978059: フィルター処理時に Cookie を削除し、フィルター処理された Cookie を削除する|クロムのバグ"  
[CR997625]: https://crbug.com/997625 "問題 997625: 新機能 Req |Cookie で url デコードされた値を表示するオプションが必要|クロムのバグ"  
[CR1003629]: https://crbug.com/1003629 "問題 1003629: キャプチャ ノードは、もうフォールドの下のノードのスクリーンショットを撮りません。|クロムのバグ"  
[CR1012337]: https://crbug.com/1012337 "問題 1012337: サイト データを消去すると、Google 以外のサイトで Google セッションが破棄|クロムのバグ"  
[CR1028078]: https://crbug.com/1028078 "問題 1028078: [オンライン] と [オフライン] をリスト 内の横に置|クロムのバグ"  
[CR1054281]: https://crbug.com/1054281 "問題 1054281: 機能要求: DevTools は、折りたたみ可能デバイスとデュアルスクリーン デバイスをエミュレートする必要|クロムのバグ"  
[CR1075865]: https://crbug.com/1075865 "問題 1075865: devtools タイムラインにドロップされたフレームを表示|クロムのバグ"  
[CR1093229]: https://crbug.com/1093229 "問題 1093229: DevTools: 特殊な書体エディター UI を提供|クロムのバグ"  
[CR1121900]: https://crbug.com/1121900 "問題 1121900: DevTools: 新しい仕様ごとにコントラスト計算ロジックを更新|クロムのバグ"  
[CR1122507]: https://crbug.com/1122507 "問題 1122507: フレーム ツリー ビューでの Surface ワーカー情報 | Chromium のバグ"  
[CR1122580]: https://crbug.com/1122580 "問題 1122580: 再読み込み時にネットワーク記録を無効に|クロムのバグ"  
[CR1136394]: https://crbug.com/1136394 "問題 1136394: Flexbox ツール | Chromium のバグ"  
[CR1139899]: https://crbug.com/1139899 "問題 1139899: フレーム詳細ビューでゲート API の可用性を報告する | Chromium のバグ"  
[CR1139949]: https://crbug.com/1139949 "問題 1139949: Flexbox オーバーレイ |クロムのバグ"  
[CR1147016]: https://crbug.com/1147016 "問題 1147016: カラー ピッカーは var() 関数に表示されません。|クロムのバグ"  
[CR1148353]: https://crbug.com/1148353 "問題 1148353: 機能要求: devtools コンソール からオブジェクトをコピー|クロムのバグ"  
[CR1149859]: https://crbug.com/1149859 "Issue 1149859: [feature request][Console] add copy object to clipboard item to contextual menu |クロムのバグ"  
[CR1150797]: https://crbug.com/1150797 "問題 1150797: [要素] パネル の [要素] コンテキスト メニューに [Duplicate] 要素を追加|クロムのバグ"  
[CR1152391]: https://crbug.com/1152391 "問題 1152391: スタイル パネルの CSS コンテキスト メニューのコピー|クロムのバグ"  
[CR1155120]: https://crbug.com/1155120 "問題 1155120: [FR]サポート コピー ファイル名と行番号|クロムのバグ"  
[CR1156628]: https://crbug.com/1156628 "問題 1156628: DevTools: :target in force 要素の状態機能のサポートを追加|クロムのバグ"  
[CR1157329]: https://crbug.com/1157329 "問題 1157329: アクセシビリティ - ナレーター: ナレーターは、[スタイル] タブの [コードで使用できる候補の数と位置を発表|クロムのバグ"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target ":target |MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "コントラスト (拡張) - WCAG (クイック リファレンス) を満たす|W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "コントラスト (最小) - WCAG を満たす方法 (クイック リファレンス) |W3C"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2021/01/devtools/index)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen

[SpanningPlaceholder]: link-t-b-d "スパン プレースホルダー"  
