---
description: What's New ツールがウェルカム、スタイル ウィンドウの Visual Font Editor、CSS Flexbox デバッグ ツールなどです。
title: DevTools の新機能 (Microsoft Edge 89)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/03/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cfaee927d2d914cf0d816505ea2cf6b36a225d64
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313264"
---
# DevTools の新機能 (Microsoft Edge 89)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## 新機能へようこそ  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Microsoft **** Edge DevTools の新機能ツールに、新しい外観と新しい名前 "ようこそ" が追加**されています**。  ウェルカム **ツールには** 、最新の DevTools ニュースと更新プログラムが引き続き表示されます。  また、Microsoft Edge DevTools ドキュメントへのリンク、フィードバックの送信方法なども含まれています。  Microsoft Edge への更新 **の後** にウェルカム ツールを表示するには、タイトルの更新ごとに [開く] タブの横 **にある** チェック ボックスをオンにします。  ウェルカム ツールを **閉** じるには、タブ タイトルの右側にある **[X]** を選択します。  元の新機能ツール**が**必要な場合は、[設定の実験[][DevtoolsCustomizeIndexSettings]] に移動し、[ようこそ] タブの横にある  >  ******チェック ボックスをオフにします**。  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="ウェルカム ツールが強調表示されている" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   ウェルカム **ツール** が強調表示されている  
:::image-end:::  

## [スタイル] ウィンドウの Visual Font Editor  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

CSS でフォントを使用する場合は、新しいビジュアル フォント エディター [を使用します][DevtoolsInspectStylesEditFonts]。  フォールバック フォントを定義し、スライダーを使ってフォントの太さ、サイズ、行の高さ、間隔を定義できます。  フォント **エディターを使用すると** 、次の操作を実行できます。  

*   さまざまなフォント プロパティの単位を切り替える  
*   さまざまなフォント プロパティのキーワードを切り替える  
*   単位を変換する  
*   正確な CSS コードを生成する  
    
この実験を有効にするには、[設定の[][DevtoolsCustomizeIndexSettings]実験] に移動し、[スタイル] ウィンドウで新しいフォント エディター ツールを有効にするの横にある  >  ******チェック ボックスをオンにします**。  詳細については、DevTools の [スタイル] ウィンドウの [CSS フォントのスタイルと設定 [の編集] に移動します][DevtoolsInspectStylesEditFonts]。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1093229][CR1093229] に移動します。  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="ビジュアル フォント エディターが [スタイル] ウィンドウで強調表示されている" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   [スタイル **] ウィンドウで** 、視覚的なフォント エディター **が強調表示** されている  
:::image-end:::  

## CSS Flexbox デバッグ ツール  

Flexbox のデバッグ機能は、アクティブな開発中です。  次の 2 つの機能の実験を有効にするには[][DevtoolsCustomizeIndexSettings]、[設定の実験] に移動し、[新しい CSS Flexbox デバッグ機能を有効にする] の横にあるチェック ボックス  >  ******をオンにします**。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[問題] [1136394][CR1136394] および [1139949][CR1139949] に移動します。  

### 新しい Flexbox (flex) アイコンは、flex コンテナーの識別と表示に役立ちます  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Elements ツール **では** 、新しい Flexbox (flex) アイコンを使用して、コード内の Flexbox コンテナーを識別できます。  Flexbox \(flex\) アイコンを選択して、Flexbox コンテナーの輪郭を表示するオーバーレイ効果をオンまたはオフにします。  [レイアウト] ウィンドウの [スタイルと**** 計算] の横にあるオーバーレイの色**を****カスタマイズできます**。  

:::row:::
   :::column span="":::
      Flexbox コンテナーの輪郭を引くオーバーレイ効果のオンとオフを切り替える場合は、Flexbox \( `flex` \) アイコンを選択します。  
   :::column-end:::
   :::column span="":::
      [スタイルと計算] の横の [ **レイアウト** ] ウィンドウでオーバーレイ **の色** を **カスタマイズできます**。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="Flexbox (flex) アイコンと Web ページが強調表示されている" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         **Flexbox** \( `flex` \) アイコンと Web ページが強調表示されている :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text="レイアウト ウィンドウで強調表示されている Flexbox オーバーレイ" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         レイアウト**ウィンドウで強調表示**されている Flexbox**オーバーレイ**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### CSS プロパティを使用して Flexbox レイアウトが変更された場合に配置アイコンとグリッド線を表示する  

<!--  Title: Display alignment icons and gridlines for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Flexbox レイアウトの CSS を編集すると、[スタイル] ウィンドウの**** CSS オートコンプリートに、関連する Flexbox プロパティの横に便利なアイコンが表示されます。  この新機能を試す場合は **、Elements** ツールを開き、flex コンテナーを選択します。  次に、[スタイル] ウィンドウで、そのコンテナーのプロパティを **追加または変更** します。  

:::row:::
   :::column span="":::
      オートコンプリート メニューに、配置プロパティの効果を示すアイコンが表示 `align-content` されます `align-items` 。  
   :::column-end:::
   :::column span="":::
      さらに、DevTools には CSS プロパティの確認に役立つガイド行が `align-items` 表示されます。  `gap`CSS プロパティもサポートされています。  次の図では、CSS プロパティが設定され、ギャップごとにパターン `gap` `gap: 12px;` が表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text="配置で始まる CSS プロパティで強調表示されたオートコンプリート メニュー" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         次で始まる CSS プロパティで強調表示されたオートコンプリート メニュー `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS プロパティと Web ページの Flexbox ギャップが強調表示されている" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         CSS プロパティ `gap` と Web ページの Flexbox が強調表示されている  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 新しい [その他のツール] ボタンを使用してツールをすばやく追加する  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

これで、Microsoft Edge DevTools でさらに多くのツールを開く新しい方法が追加されています。  この実験を有効にした後、[**** その他のツール] アイコンは、メイン パネルの右側にプラス記号 ( `+` ) として表示されます。  メイン パネルに追加する他のツールの一覧を表示するには、[その他のツール] **\(** `+` \) アイコンを選択します。  この実験を有効にするには、[[設定][DevtoolsCustomizeIndexSettings]の実験] に移動し、[+] ボタン タブ メニューの横にあるチェック ボックスをオンにして、その他の  >  ******ツールを開きます**。  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="DevTools で強調表示されているその他のツール" lightbox="../../media/2021/01/more-tools.msft.png":::
   **DevTools** で強調表示されているその他のツール  
:::image-end:::  

## 支援技術が CSS 候補の位置と数をアナウンスする  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

CSS を編集すると、機能のドロップダウンが表示されます。  この機能は、Microsoft Edge バージョン 89 で発表されたので、支援技術のユーザーは利用できません。  支援技術のユーザーが、[スタイル] ウィンドウで CSS 候補内を **移動する場合** があります。  Microsoft Edge バージョン 88 以前では、ユーザーが [スタイル] ウィンドウで CSS を編集するときに提案の一覧を探して、支援技術が `Suggestion` **発表** されました。  Microsoft Edge バージョン 89 では、支援技術のユーザーに現在の提案の位置と数が聞こえる状態です。  各提案は、ユーザーが提案の一覧 (5 の提案 3 など) を移動すると発表されます。  DevTools での CSS の記述の詳細については、「CSS の変更」に移動 [してください][DevtoolsCssReferenceChangeCss]。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1157329][CR1157329] に移動します。  

<!--To view a video that displays and reads aloud several suggestions with this experiment turned on, navigate to [Voiceover announcing devtools options](https://youtu.be/9TcUpleEwwA) on YouTube.  -->  

次のビデオ リンクは、この実験を有効にした状態で、いくつかの提案を表示して読み上げます。  

> [!VIDEO https://youtu.be/9TcUpleEwwA]  

## Surface Duo と Samsung Galaxy Fold のエミュレート  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

Microsoft Edge の次のデバイスで、Web サイトまたはアプリの外観をテストします。  

*   [Surface の一方][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [Samsung Galaxy Fold][SamsungUsMobileGalaxyFold]  
    
試験的 **な Web プラットフォーム機能** を有効にし、新しい [CSS メディア][DualScreenWebCssMediaSpanning] 画面スパン機能にアクセスし [、getWindowSegments JavaScript API を取得します][DualScreenWebJavascriptGetwindowsegments]。  試験的 `edge://flags` な Web プラットフォーム機能の横にあるフラグ **に移動し、切り替える**。  デュアルスクリーン デバイスと折りたたみ式デバイスのために Web サイトやアプリを強化するには、[デバイスをエミュレート][DevtoolsDeviceModeIndex]するときに次の機能を使用します。  

*   [スパニング][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: Web サイト (またはアプリ) が両方の画面に表示されます。  
*   [シームのレンダリング][DualScreenIntroductionHowToWorkWithSeam]: シームとは、2 つの画面の間の領域のことです。  
    
Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1054281][CR1054281] に移動します。  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="デュアルスクリーンをエミュレートする" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   デュアルスクリーンをエミュレートする  
:::image-end:::  

## Microsoft Edge Developer Tools for Visual Studio Code Version 1.1.2  

[Microsoft Edge Developer Tools for Visual Studio Code extension][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] version 1.1.2 for Microsoft Visual Studio Code には、前のリリース以降に次の変更があります。  Microsoft Visual Studioコードは拡張機能を自動的に更新します。  バージョン 1.1.2 に手動で更新するには、[拡張機能を手動で [更新する] に移動します][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。  

*   ターゲット リスト **\( #248** \) の各アイテムに [インスタンス[を閉じる] ボタンを][GithubMicrosoftVscodeEdgeDevtoolsPull248]追加しました  
*   84.0.522.63 から[85.0.564.40][DevtoolsWhatsNew85] \([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235]\) [][DevtoolsMain]  
*   依存関係 [\(][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] #233 \) として Microsoft Edge[のデバッガーが含][GithubMicrosoftVscodeEdgeDevtoolsPull233]まれています  
*   拡張テーマ \( #229 \)[を変更する設定オプションを][GithubMicrosoftVscodeEdgeDevtoolsPull229]実装しました  
    
[vscode-edge-devtools GitHub][GithubMicrosoftVscodeEdgeDevtools]リポジトリで問題を解決し、拡張機能に投稿することができます。  

## Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### ビューポートを越えたキャプチャ ノードのスクリーンショット  

Microsoft Edge バージョン 89 では、ノードのスクリーンショットの方が正確で、ノードのコンテンツがビューポートに表示されない場合でも、ノード全体がキャプチャされます。  要素ツール **で要素** をポイントし、コンテキスト メニュー \(右クリック\) を開き、[キャプチャ] ノードのスクリーンショット **を選択します**。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1003629][CR1003629] に移動します。  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="要素ツールのコンテキスト メニューで強調表示されているキャプチャ ノードのスクリーンショット" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   **要素ツールの** コンテキスト メニューで強調表示されているキャプチャ ノード **の** スクリーンショット  
:::image-end:::  

### 要素ツールの更新  

#### :target CSS 状態の適用のサポート  

DevTools を使って [、:target][MdnDocsWebCssTarget] CSS 擬似クラスを強制的に使う場合があります。  擬似クラスは、一意の要素 \(target element\) に URL のフラグメントと一致する要素がある `:target` `id` 場合にトリガーされます。  たとえば、URL は `http://www.example.com/index.html#section1` HTML 要素で擬似クラスを `:target` トリガーします `id="section1"` 。  セクション 1 が強調表示されているデモを試す場合は [、CSS :target デモに移動します][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1156628][CR1156628] に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="強制 CSS がない Web ページが強調表示されている" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         強制 CSS を使用して強調表示された Web ページ  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text=":target CSS forced and web-highlighted" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` CSS の強制と Web ページの強調表示  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### Duplicate 要素を使用して要素をコピーする  

新しい **Duplicate 要素ショートカットを使用して** 、要素を複製します。  要素ツール **で要素** をポイントし、コンテキスト メニュー \(右クリック\) を開き、[要素の複製] を **選択します**。  選択した要素の下に新しい要素が作成されます。  キーボード ショートカットで要素を複製するには `Shift` + `Alt` + `Down Arrow` 、\(Windows/Linux\) または `Shift` + `Option` + `Down Arrow` \(macOS\) を選択します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issue [1150797][CR1150797]] に移動します。  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="要素ツールの要素のコンテキスト メニューで Duplicate 要素が強調表示されている" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   **要素ツールの**要素のコンテキスト メニューで Duplicate 要素が**強調表示**されている  
:::image-end:::  

#### カスタム CSS プロパティのカラー ピッカー  

[ **スタイル]** ウィンドウに、カスタム CSS プロパティのカラー ピッカーが表示されます。  色の値の RGBA、HSLA、および Hex 形式を循環するには、カラー ピッカーを長押 `Shift` しして選択します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1147016][CR1147016] に移動します。  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="カスタム CSS プロパティのカラー ピッカー" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   カスタム CSS プロパティのカラー ピッカー  
:::image-end:::  

#### CSS クラスとプロパティをコピーする  

コンテキスト メニューのいくつかの新しいオプションを使用して、CSS プロパティを迅速にコピーできます。  要素ツール **で** 、要素を選択します。  値をコピーするには、[スタイル]**** ウィンドウで、CSS クラスまたは CSS プロパティをポイントし、コンテキスト メニュー \(右クリック\) を開き、コピー オプションを選択します。  

:::row:::
   :::column span="":::
      CSS クラスのオプションをコピーします。  
      
      | オプション | 詳細 |  
      |:--- |:--- |  
      | **コピー セレクター** | 現在のセレクター名をコピーします。 |  
      | **ルールをコピーする** | 現在のセレクターのルールをコピーします。 |  
      | **すべての宣言をコピーする** | 無効なプロパティとプレフィックス付きプロパティを含む、現在のルールのすべての宣言をコピーします。 |  
   :::column-end:::
   :::column span="":::
      CSS プロパティのオプションをコピーします。  
      
      | オプション | 詳細 |      
      |:--- |:--- |  
      | **Copy 宣言** | 現在の行の宣言をコピーします。 |  
      | **Copy プロパティ** | 現在の行のプロパティをコピーします。 |  
      | **値をコピーする** | 現在の行の値をコピーします。 |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="コンテキスト メニューの CSS クラスのコピー オプション" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         コンテキスト メニューの CSS クラスのコピー オプション  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="コンテキスト メニューの CSS プロパティのオプションをコピーする" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         コンテキスト メニューの CSS プロパティのコピー オプション  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1152391][CR1152391] に移動します。  

### Cookie の更新  

#### URL デコードされた Cookie を表示する新しいオプション  

これで、[Cookie] ウィンドウに URL デコードされた Cookie の **値を表示** できます。  デコードされた Cookie を表示するには、[**アプリケーション**Cookie] ウィンドウに移動し、一覧から任意の Cookie を選択し、[デコードされた URL を表示する] の横にあるチェック  >  ******ボックスをオンにします**。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[997625][CR997625] に移動します。  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="URL デコードされた Cookie を表示するオプション" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   URL デコードされた Cookie を表示するオプション  
:::image-end:::  

#### 表示されている Cookie のフィルター処理とクリア  

Microsoft Edge バージョン 88 以前**** では、アプリケーション ツールは、[すべての Cookie をクリア] ボタンを使用してすべての Cookie をクリアする方法**のみを提供**しました。  Microsoft Edge バージョン 89 では、[**** フィルター処理された Cookie のクリア] を選択して、フィルター処理された Cookie のみを削除できます。  Cookie をフィルター処理するには、[**アプリケーション Cookie] に**  >  **移動**し、[フィルター] テキスト ボックス**に**入力します。  表示された Cookie を削除するには、[フィルター処理された Cookie のクリア **] ボタンを選択** します。  他のすべての Cookie を表示するには、フィルター テキストをクリアします。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issue [978059][CR978059]] に移動します。  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="表示されている Cookie のみをクリアする" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   表示されている Cookie のみをクリアする  
:::image-end:::  

#### ストレージ ウィンドウでサード パーティの Cookie をクリアする新しいオプション  

DevTools は、既定でファースト パーティの Cookie のみをクリアします。  Web サイトのデータとファースト パーティの Cookie のみをクリアするには、[**アプリケーション**ストレージ] に移動し、[サイト データのクリア]  >  ******を選択します**。  

Web サイトのデータとすべての Cookie をクリアするには、[アプリケーション ストレージ]**に移動**  >  **します**。  [サード パーティの Cookie **を含む**] の横にあるチェック ボックスをオンにし、[サイト データのクリア **] を選択します**。  

Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1012337][CR1012337] に移動します。  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="サード パーティの Cookie をクリアするオプション" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   サード パーティの Cookie をクリアするオプション  
:::image-end:::  

### ネットワーク ツールの更新  

#### [レコードの保持] ネットワーク ログの設定  

Microsoft Edge バージョン 88 以前では、DevTools は Web ページが更新された際に **Record** ネットワーク ログ設定をリセットします。  Microsoft Edge バージョン 89 では、DevTools はレコード ネットワーク ログの **設定を保持** します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1122580][CR1122580] に移動します。  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="ネットワーク ログを記録する" lightbox="../../media/2021/01/network-log.msft.png":::
   ネットワーク ログを記録する  
:::image-end:::  

#### オンライン オプションが調整オプションなし  

ネットワーク エミュレーション オプション **Online の** 名前が [調整なし] **に変更されました**。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issue [1028078][CR1028078]] に移動します。  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="調整オプションなし" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   **調整オプション** なし  
:::image-end:::  

### コンソール ツール、ソース ツール、および [スタイル] ウィンドウの新しいコピー オプション

#### コンソール ツールとソース ツールでオブジェクトをコピーする  

コンソール ツールとソース ツールでオブジェクトの **値** を **コピー** できます。  オブジェクト値をコピーする機能は、大きなオブジェクトを操作する場合に便利です。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issues [1148353][CR1148353] および [1149859][CR1149859] に移動します。  

:::row:::
   :::column span="":::
      コンソール ツール **で** オブジェクトをポイントし、コンテキスト メニュー \(右クリック\) を開き、[オブジェクトのコピー] を **選択します**。  
   :::column-end:::
   :::column span="":::
      ソース**ツールの**ブレークポイントで、オブジェクトをポイントし、[オブジェクト] ポップアップ**** ウィンドウでオブジェクトを強調表示し、コンテキスト メニュー \(右クリック\) を開き、[オブジェクトのコピー] を選択**します。**  
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

#### [ソース] ツールと [スタイル] ウィンドウでファイル名をコピーする  

コンテキスト メニューを使用してファイル名をコピーできます。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issues [1155120][CR1155120]] に移動します。  

:::row:::
   :::column span="":::
      ソース ツール **で、** ファイル名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[ファイル名のコピー] を **選択します**。  
   :::column-end:::
   :::column span="":::
      [ **要素]** ツールの [> **スタイル** ] ウィンドウで、ファイル名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[ファイル名のコピー] を **選択します**。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="Sources のファイル名をコピーする" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         Sources のファイル名 **をコピーする**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="[スタイル] ウィンドウでファイル名をコピーする" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         [スタイル] ウィンドウでファイル名 **をコピー** する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### フレームの詳細の更新  

#### フレームの詳細のサービス ワーカー情報  

DevTools では、親フレームの下に専用のサービス ワーカーが一覧表示されます。  次の図では、サービス ワーカーの詳細が表示されます。  サービス ワーカーの詳細を表示するには **、[Application**Frames Service Workers] に移動し、サービス  >  ****  >  `top`  >  **** ワーカーを選択します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1122507][CR1122507] に移動します。  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="フレームの詳細のサービス ワーカー情報" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   **フレームの詳細**のサービス ワーカー**情報**  
:::image-end:::  

#### フレームの詳細でメモリ情報を測定する  

これで `performance.measureMemory()` 、API の状態が [API の可用性] **セクションに表示** されます。  新しい `performance.measureMemory()` API は、Web ページ全体のメモリ使用量を見積もっています。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issue [1139899][CR1139899]] に移動します。  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="メモリを測定する" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   メモリを測定する  
:::image-end:::  

### パフォーマンス ツールでフレームがドロップされました  

パフォーマンス ツール [で読み込みパフォーマンスを分析][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]すると **、[Frames]** セクションでドロップされたフレームが赤としてマークされます。  フレーム レートを表示するには、ドロップしたフレームをポイントします。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issue [1075865][CR1075865]] に移動します。  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="破棄されたフレーム" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   破棄されたフレーム  
:::image-end:::  

#### 新しいカラー コントラスト計算 - 高度な知覚コントラスト アルゴリズム (APCA)  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

色の選択で[AA][W3cWaiWcag21QuickrefContrastMinimum]AAA ガイドラインのコントラスト比を置き換える[APCA (Advanced Perceptual Contrast Algorithm)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] / [][W3cWaiWcag21QuickrefContrastEnhanced][です][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]。  APCA は、コントラストを計算する新しい方法です。  色の認識に関する最新の調査に基づいて作成されます。  AA/AAA ガイドラインと比較すると、APCA はコンテキストに依存します。  コントラストは、テキスト、色、コンテキストの次の空間プロパティに基づいて計算されます。  

*   フォントの太さおよびサイズを含むテキストの空間プロパティ。  
*   テキストと背景のコントラストを含む色の空間プロパティ。  
*   環境光、周囲、および目的を含むコンテキストの空間プロパティ。  
    
この実験を有効にするには、[設定の[][DevtoolsCustomizeIndexSettings]実験] に移動し、以前のコントラスト比と AA/AAA ガイドラインを置き換える新しい ADVANCED  >  **** **Perceptual Contrast Algorithm (APCA)** を有効にするチェック ボックスをオンにします。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[1121900][CR1121900] に移動します。  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="カラー ピッカーの APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   カラー ピッカーの APCA  
:::image-end:::  

## Microsoft Edge プレビュー チャネルをダウンロードする  

Windows、Linux、または macOS を使用している場合は、 [既定][MicrosoftEdgePreviewChannels] の開発ブラウザーとして Microsoft Edge プレビュー チャネルの使用を検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "DevTools (Microsoft Edge 85) の新機能 |Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "色の選択コントロールのテキスト要素のコントラスト比を表示する - ユーザー補助|Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "CSS の変更 - CSS 参照|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "折りたたみ可能なデュアルスクリーン デバイスでのテスト - Microsoft Edge DevTools アプリケーションでデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレート|Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイル ビューポートをシミュレートする - Microsoft Edge DevTools アプリケーションでモバイル デバイスをエミュレート|Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "レコード読み込みパフォーマンス - パフォーマンス分析リファレンス |Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "DevTools プロジェクトの [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 開発者ツールの概要|Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "セクション 1 - DevTools の新機能 (Microsoft Edge 89) の CSS :target デモ|GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "プル 229: 設定にドロップダウンを実装してテーマを変更|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "プル 233: 依存関係オブジェクトとして Microsoft Edge のデバッガーを含|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "プル 235: Edge DevTools バージョンを 85.0.564.40 バージョンにアップグレード|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "プル 248: インスタンス パネルに 1 つの閉じるボタンを追加|GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "フォントの特性と背景の色を選択して、読みやすさを向上するために十分なコントラスト|W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "信頼できる型|W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface の新しい |Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - Extension Marketplace |Visual Studio コード"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code |Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge アプリケーションのデバッガー|Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

<!--[CR174309]: https://crbug.com/174309 "Issue 174309: DevTools: Allow to customize keyboard shortcuts/key bindings | Chromium bugs"  -->  
<!--[CR772558]: https://crbug.com/772558 "Issue 772558: DevTools: Update to latest version of Lighthouse | Chromium bugs"  -->  
[CR978059]: https://crbug.com/978059 "Issue 978059: Deleting cookies when filtering them, delete all the cookies not just the filtered ones |Chromium bugs"  
[CR997625]: https://crbug.com/997625 "Issue 997625: New Feature Req |Cookie で URL デコードされた値を表示するオプションが必要|Chromium bugs"  
[CR1003629]: https://crbug.com/1003629 "問題 1003629: キャプチャ ノードはもう 2 つ下のノードをスクリーンショットに表示しません。 |Chromium bugs"  
[CR1012337]: https://crbug.com/1012337 "問題 1012337: Clear Site Data destroys Google session on non-Google sites |Chromium bugs"  
[CR1028078]: https://crbug.com/1028078 "Issue 1028078: Put Online and Offline next to each to the list |Chromium bugs"  
[CR1054281]: https://crbug.com/1054281 "Issue 1054281: Feature Request: DevTools should emulate foldable and dual-screen devices |Chromium bugs"  
<!--[CR1073909]: https://crbug.com/1073909 "Issue 1073909: BLOCKED | Chromium bugs"  -->  
[CR1075865]: https://crbug.com/1075865 "問題 1075865: devtools タイムラインにドロップ されたフレームを表示|Chromium bugs"  
[CR1093229]: https://crbug.com/1093229 "Issue 1093229: DevTools: offer a specialized typeface editor UI |Chromium bugs"  
[CR1121900]: https://crbug.com/1121900 "問題 1121900: DevTools: 新しい仕様ごとにコントラスト計算ロジックを更新|Chromium bugs"  
[CR1122507]: https://crbug.com/1122507 "Issue 1122507: Surface worker information in frame tree view |Chromium bugs"  
[CR1122580]: https://crbug.com/1122580 "問題 1122580: 再読み込み時にネットワーク記録を無効|Chromium bugs"  
<!--[CR1126824]: https://crbug.com/1126824 "Issue 1126824: ☂ Support Trust Token debugging in DevTools | Chromium bugs"  -->  
[CR1136394]: https://crbug.com/1136394 "問題 1136394: Flexbox ツール |Chromium bugs"  
<!--[CR1137837]: https://crbug.com/1137837 "Issue 1137837: ☂ Improve Trusted Types support in DevTools | Chromium bugs"  -->  
[CR1139899]: https://crbug.com/1139899 "Issue 1139899: Report gated API availability in frame details view |Chromium bugs"  
[CR1139949]: https://crbug.com/1139949 "問題 1139949: Flexbox オーバーレイ |Chromium bugs"  
<!--[CR1142804]: https://crbug.com/1142804 "Issue 1142804: Implement break-on-trusted-type-violation | Chromium bugs"  -->  
<!--[CR1144127]: https://crbug.com/1144127 "Issue 1144127: BLOCKED | Chromium bugs"  -->  
[CR1147016]: https://crbug.com/1147016 "問題 1147016: カラー ピッカーは var() 関数に表示されません。 |Chromium bugs"  
[CR1148353]: https://crbug.com/1148353 "Issue 1148353: Feature Request: Copy Object from the devtools console |Chromium bugs"  
[CR1149859]: https://crbug.com/1149859 "問題 1149859: [feature request][Console] add copy object to clipboard item to contextual menu |Chromium bugs"  
[CR1150797]: https://crbug.com/1150797 "Issue 1150797: Add Duplicate element context menu in Element panel |Chromium bugs"  
<!--[CR1150883]: https://crbug.com/1150883 "Issue 1150883: Remove TT messages from the console but keep underlining in the sources tab | Chromium bugs"  -->  
<!--[CR1152290]: https://crbug.com/1152290 "Issue 1152290: Devtools support for QuicTransport | Chromium bugs"  -->  
[CR1152391]: https://crbug.com/1152391 "Issue 1152391: Support for copy CSS context menu in styles panel |Chromium bugs"  
[CR1155120]: https://crbug.com/1155120 "Issue 1155120: [FR]Support copy file name and line number |Chromium bugs"  
[CR1156628]: https://crbug.com/1156628 "問題 1156628: DevTools: :target in force 要素状態機能のサポートを追加|Chromium bugs"  
[CR1157329]: "問題 1157329: アクセシビリティ - ナレーター: ナレーターは、[スタイル] タブのコードで使用可能な候補の数と位置を https://crbug.com/1157329 発表|Chromium bugs"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target ":target |MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "Contrast (拡張) - WCAG を満たす方法 (クイック リファレンス) |W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "Contrast (最小) - WCAG を満たす方法 (クイック リファレンス) |W3C"  

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
