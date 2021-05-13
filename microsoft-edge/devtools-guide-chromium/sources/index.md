---
description: '[ソース] ツールを使用して、サーバーから返される JavaScript を表示、変更、およびデバッグし、現在の Web ページを構成するリソースを検査します。  Sources ツールを開発環境として使用するには、ワークスペースにソース ファイルを追加します。'
title: ソース ツールの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d3ef49bf986d8827216bd0bc183e45806aa0a2c3
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564715"
---
# <a name="sources-tool-overview"></a>ソース ツールの概要  

ソース ツール **を使用して** 、フロントエンド JavaScript コードを表示、変更、デバッグし、現在の Web ページを構成するリソースを検査します。  ソース **ツールには、** 次の 3 つのウィンドウがあります。  

| ウィンドウ | アクション |  
|:--- |:--- |  
| **[ナビゲーター** ] ウィンドウ | サーバーから返されるリソース間を移動して、現在の Web ページを作成します。  ファイル、画像、その他のリソースを選択し、そのパスを表示します。  必要に応じて、ローカル ワークスペースをセットアップして、変更をソース ファイルに直接保存します。  |  
| **エディター** ウィンドウ | サーバーから返される JavaScript、HTML、CSS、その他のファイルを表示します。  JavaScript または CSS を実験的に編集します。  変更は、ページを更新するまで保持され、Workspaces を使用してローカル ファイルに保存した場合はページ更新後も保持されます。  Workspaces または Overrides を使用する場合は、HTML ファイルも編集できます。  |  
| **デバッガー ウィンドウ** | JavaScript デバッガーを使用してブレークポイントを設定し、JavaScript の実行を一時停止し、指定した JavaScript 式を確認しながら、行った編集内容を含むコードをステップ実行します。  現在のコード行のスコープ内にある変数の値を監視し、手動で変更します。  |  

次の図は、DevTools の左上隅に赤いボックスで強調表示されたナビゲーター ウィンドウ、右上**** で強調表示されているエディター ウィンドウ、および下部で強調表示された**デバッガー**ウィンドウを示しています。 ****  左側はブラウザー ウィンドウのメイン部分で、デバッガーがブレークポイントで一時停止している場合に、レンダリングされた Web ページが灰色表示で表示されます。

:::image type="complex" source="../media/sources-panes-narrow-layout.msft.png" alt-text="狭いレイアウトの [ソース] ツールのウィンドウ" lightbox="../media/sources-panes-narrow-layout.msft.png":::
   狭いレイアウトの [ソース] ツールのウィンドウ  
:::image-end:::  

DevTools が広い場合****、デバッガー ウィンドウは右側に配置され **、Scope**と Watch が含**まれます**。  

:::image type="complex" source="../media/sources-panes-wide-layout.msft.png" alt-text="サーバーから返される JavaScript の移動、表示、編集、デバッグ" lightbox="../media/sources-panes-wide-layout.msft.png":::
   サーバーから返される JavaScript の移動、表示、編集、デバッグ  
:::image-end:::  

Sources ツールのサイズを最大化するには、DevTools を別のウィンドウにドッキング解除し、必要に応じて DevTools ウィンドウを別のモニターに移動します。  「Change [Microsoft Edge DevTools プレースメント (Undock、Dock to bottom、Dock to left)」を参照してください][DevToolsCustomizePlacement]。

上記のデバッグ デモ Web ページを読み込むには、以下の「デバッガーを使用 [する基本的な方法」を](#the-basic-approach-to-using-a-debugger)参照してください。

## <a name="using-the-navigator-pane-to-select-files"></a>[ナビゲーター] ウィンドウを使用してファイルを選択する

サーバーから **返** されるリソース間を移動して現在の Web ページを作成するには、ナビゲーター ウィンドウ \(左側\) を使用します。  ファイル、画像、その他のリソースを選択し、そのパスを表示します。  

:::image type="complex" source="../media/navigator-pane.msft.png" alt-text="[ナビゲーター] ウィンドウ" lightbox="../media/navigator-pane.msft.png":::
   [ **ナビゲーター]** ウィンドウ
:::image-end:::  

ナビゲーター ウィンドウの非表示のタブにアクセスするには、[その他の ![ タブ ](../media/more-tabs-icon.msft.png) ] \( [**その他のタブ**] \) を選択します。

次のサブセクションでは、ナビゲーター ウィンドウについて説明します。  

*   [[ページ] タブを使用して、現在の Web ページを作成するリソースを確認する](#using-the-page-tab-to-explore-resources-that-construct-the-current-webpage)  
*   [[ファイルシステム] タブを使用してローカル ワークスペースを定義する](#using-the-filesystem-tab-to-define-a-local-workspace)  
*   [[上書き] タブを使用してサーバー ファイルをローカル ファイルで上書きする](#using-the-overrides-tab-to-override-server-files-with-local-files)  
*   [拡張機能の [コンテンツ スクリプト] タブMicrosoft Edgeする](#using-the-content-scripts-tab-for-microsoft-edge-extensions)  
*   [[スニペット] タブを使用して任意のページで JavaScript コード スニペットを実行する](#using-the-snippets-tab-to-run-javascript-code-snippets-on-any-webpage)  
*   [コマンド メニューを使用してファイルを開く](#using-the-command-menu-to-open-files)  
    
### <a name="using-the-page-tab-to-explore-resources-that-construct-the-current-webpage"></a>[ページ] タブを使用して、現在の Web ページを作成するリソースを確認する

[ナビゲーター] **ウィンドウの** [ **ページ** ] タブを使用して、サーバーから返されるファイル システムを探索して、現在の Web ページを作成します。  JavaScript ファイルを選択して、表示、編集、およびデバッグします。  [ **ページ]** タブには、ページが読み込まれたすべてのリソースが一覧表示されます。

:::image type="complex" source="../media/sources-page-tab.msft.png" alt-text="[ソース] ツールの [ナビゲーター] ウィンドウの [ページ] タブ" lightbox="../media/sources-page-tab.msft.png":::
   [**ソース]** ツールの **[ナビゲーター** ] ウィンドウの **[ページ] タブ**
:::image-end:::  

[エディター] ウィンドウにファイル **を表示するには** 、[ページ] タブでファイル **を選択** します。 イメージの場合、イメージのプレビューが表示されます。  
リソースの URL またはパスを表示するには、リソースの上にマウス ポインターを置きます。  
ブラウザーの新しいタブにファイルを読み込む場合、または他のアクションを表示するには、ファイル名を右クリックします。  

#### <a name="icons-in-the-page-tab"></a>[ページ] タブのアイコン

[ **ページ] タブ** には、次のアイコンが使用されます。  

*   ウィンドウ **アイコン** とラベルは、HTML フレームであるメイン ドキュメント フレーム `top` を [表します][W3CHtml4Frames]。  
*   クラウド **アイコンは** 原点を [表します][WhatwgHtmlSpecMulitpageOriginHtmlOrigin]。  
*   フォルダー **アイコンは** 、ディレクトリを表します。  
*   ページ **アイコンは** リソースを表します。  
    
#### <a name="group-files-by-folder-or-as-a-flat-list"></a>フォルダーまたはフラット リストとしてファイルをグループ化する

[ **ページ]** タブには、サーバーとディレクトリ、またはフラット リストでグループ化されたファイルまたはリソースが表示されます。

リソースのグループ化方法を変更するには、次の方法を使用します。

1.  [ナビゲーター] ウィンドウ \(左\) のタブの横にある **... \(** More options \) ボタン**を**選択します。  メニューが表示されます。  
1.  [フォルダー別にグループ化 **] オプションを選択またはオフ** にします。  
    
### <a name="using-the-filesystem-tab-to-define-a-local-workspace"></a>[ファイルシステム] タブを使用してローカル ワークスペースを定義する

[ナビゲーター **] ウィンドウ** の [ **ファイルシステム** ] タブを使用して、ファイルをワークスペースに追加し、DevTools で行った変更をローカル ファイル システムに保存します。  
ワークスペース内のファイルは、DevTools 全体で、ファイル名の横に緑色のドットで示されます。  

:::image type="complex" source="../media/sources-filesystem-tab.msft.png" alt-text="ワークスペースの [ファイル システム] タブ" lightbox="../media/sources-filesystem-tab.msft.png":::
   ワークスペース **の** [ファイル システム] タブ
:::image-end:::  

既定では、[ソース] ツールでファイルを**** 編集すると、Web ページを更新すると変更は破棄されます。  Sources **ツール** は、Web サーバーから返されるフロントエンド リソースのコピーを使用します。  サーバーによって返されるこれらのフロントエンド ファイルを変更しても、ソース ファイルを変更しなかったため、変更は保持されません。  また、実際のソース コードで編集内容を適用してから、サーバーに再展開する必要があります。  
これに対し、Workspace を使用すると、Web ページを更新するときにフロントエンド コードに加えた変更は保持されます。  Workspace では、サーバーから返されるフロントエンド コードを編集すると、ソース ツールによって編集内容がローカル ソース コードにも適用されます。  その後、他のユーザーが変更を確認するには、変更されたソース ファイルのみをサーバーに再展開する必要があります。  
サーバーから返される JavaScript コードがローカルの JavaScript ソース コードと同じ場合、ワークスペースは適切に機能します。  ワークスペースは、ワークフローがソース コードの変換 (minification や [TypeScript][TypescriptlangMain] のコンパイルなど) を伴う場合にも機能しません。  

詳細については、「Workspaces を使用してファイル [を編集する」のチュートリアルを参照してください][DevtoolsGuideChromiumWorkspacesIndex]。

### <a name="using-the-overrides-tab-to-override-server-files-with-local-files"></a>[上書き] タブを使用してサーバー ファイルをローカル ファイルで上書きする

[ナビゲーター] **ウィンドウの** [上書 **き]** タブを使用して、ローカル フォルダーのファイルでページアセット \(images\など) を上書きします。  
このタブのアイテムは、サーバーがアセットを送信した後でも、サーバーがブラウザーに送信する処理を上書きします。  

:::image type="complex" source="../media/overrides-tab.msft.png" alt-text="ナビゲーター ウィンドウの [オーバーライド] タブ" lightbox="../media/overrides-tab.msft.png":::
   ナビゲーター**ウィンドウの**[オーバーライド]**タブ**
:::image-end:::  

オーバーライド **機能は** ワークスペースに似ています。  Web ページの変更を試し、Web ページを更新した後も変更を保持する必要があるが、変更を Web ページのソース コードにマッピングする場合は、オーバーライドを使用します。  

サーバーによって返されるファイルを上書きするファイルは、DevTools 全体で、ファイル名の横に紫色のドットで示されます。

#### <a name="see-also"></a>関連項目

*   [DevTools を使用して Web ページ リソースをローカル コピー Microsoft Edgeオーバーライドする][DevtoolsJavascriptOverrides]  
*   [前処理されたコードをソース コードにマップする][DevToolsJavaScriptSourceMaps]  
    
### <a name="using-the-content-scripts-tab-for-microsoft-edge-extensions"></a>拡張機能の [コンテンツ スクリプト] タブMicrosoft Edgeする

ナビゲーター ウィンドウ**の [コンテンツ スクリプト**] タブを使用して、インストールした拡張機能によって読み込まれたMicrosoft Edgeを表示します。 ****  

:::image type="complex" source="../media/content-scripts-tab.msft.png" alt-text="ナビゲーター ウィンドウの [コンテンツ スクリプト] タブ" lightbox="../media/content-scripts-tab.msft.png":::
   ナビゲーター**ウィンドウの**[コンテンツ スクリプト **] タブ**
:::image-end:::  

デバッガーが認識しないコードにステップ インすると、そのコードをライブラリ コードとしてマークして、そのコードにステップ インしないようにすることができます。  「 [コンテンツ スクリプトをライブラリ コードとしてマークする」を参照してください][DevToolsJavaScriptGuidesMarkContentScriptsLibraryCode]。

#### <a name="see-also"></a>関連項目

*   [コンテンツ スクリプト][MdnAddOnsWebextensionsContentScripts]  
*   [拡張機能のチュートリアルを作成する パート 2][ExtensionsChromiumGetstartPart2ContentScripts]  
    
### <a name="using-the-snippets-tab-to-run-javascript-code-snippets-on-any-webpage"></a>[スニペット] タブを使用して任意の Web ページで JavaScript コード スニペットを実行する

任意の **Web ページで** これらのスニペットを簡単に実行できるよう、 **ナビゲーター** ウィンドウの [スニペット] タブを使用して JavaScript コード スニペットを作成および保存します。

:::image type="complex" source="../media/snippet.msft.png" alt-text="web ページに jQuery ライブラリを挿入するスニペット" lightbox="../media/snippet.msft.png":::
   web ページに jQuery ライブラリを挿入するスニペット  
:::image-end:::  

たとえば、コンソールで次のコードを頻繁に入力して、jQuery ライブラリをページに挿入して、コンソールから jQuery コマンドを実行できると**します**。 ****  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

代わりに、このコードをスニペットに保存し****、必要なときにいつでも簡単に実行できます。  `Ctrl` + `S` \(Windows/Linux\) または `Command` + `S` \(macOS\) を選択すると、DevTools**** はスニペットをファイル システムに保存します。  

スニペットを実行する方法は複数あります。  

*   [ナビゲーター **] ウィンドウ** で、[スニペット] **タブを** 選択し、スニペット ファイルを選択して開きます。  次に、[エディター] ウィンドウの下部にある [ **実行** ] \( [実行] ![ ボタン \) を ](../media/run-snippet-icon.msft.png) 選択します。  
*   DevTools にフォーカスがある場合は `Ctrl` + `P` 、[\(Windows/Linux\) または `Command` + `P` [][DevToolsCommandMenuIndex]\(macOS\) `!` を選択してコマンド メニューを開き、 と入力します。  
    
スニペット は bookmarklets に似ています。

#### <a name="see-also"></a>関連項目

*   [DevTools を使用して任意の Web ページで JavaScript のスニペットMicrosoft Edge実行する][DevtoolsGuideChromiumJavascriptSnippets]  
    
### <a name="using-the-command-menu-to-open-files"></a>コマンド メニューを使用してファイルを開く

ファイルを開く場合は、[ソース]**** ツール内の****[ナビゲーター] ウィンドウを使用する以外に、DevTools 内の任意の場所からコマンド メニューを使用できます。

*   DevTools の任意の場所から、Windows/Linux または `Ctrl` + `P` `Command` + `P` macOS で選択します。  [コマンド] メニューが表示され、[ソース] ツールの [ナビゲーター]**** ウィンドウのタブにあるすべてのリソース**が一覧表示**されます。  
*   または、[ソース] ツールの****[ナビゲーター]**** ウィンドウのタブの横にある **...** \(**More options**\) ボタンを選択し、[ファイルを開く]**を選択します**。  

すべてのファイルの一覧を表示して選択するには.jsを入力します `.js` 。

:::image type="complex" source="../media/sources-command-menu-to-open-file.msft.png" alt-text="コマンド メニューを使用してファイルを開く" lightbox="../media/sources-command-menu-to-open-file.msft.png":::
   コマンド メニューを使用してファイルを開く
:::image-end:::

入力した場合、 `?` コマンド メニューには 、..を含むいくつかのコマンド **が表示されます。 ファイルを開きます**。  コマンド メニューを `Backspace` オフにした場合は、ファイルの一覧が表示されます。

詳細については[、「DevTools コマンド メニューを使用してコマンドMicrosoft Edge実行する」を参照してください][DevToolsCommandMenuIndex]。

## <a name="using-the-editor-pane-to-view-or-edit-files"></a>[エディター] ウィンドウを使用してファイルを表示または編集する

[エディター **] ウィンドウ** を使用して、サーバーから返されるフロントエンド ファイルを表示して、JavaScript、HTML、CSS、イメージ ファイルなどの現在の Web ページを作成します。  エディター ウィンドウでフロントエンド ファイルを編集すると****、DevTools によって Web ページが更新され、変更されたコードが実行されます。  

:::image type="complex" source="../media/editor-pane.msft.png" alt-text="[ソース] ツールの [エディター] ウィンドウ" lightbox="../media/editor-pane.msft.png":::
   [ **ソース** ] ツールの **[エディター]** ウィンドウ  
:::image-end:::

[ **エディター]** ウィンドウには、さまざまな種類のファイルに対する次のレベルのサポートがあります。  

| ファイルの種類 | サポートされているアクション |  
|:--- |:--- |  
| JavaScript | 表示、編集、デバッグを行います。  |  
| CSS | 表示と編集。  |  
| HTML | 表示と編集。  |  
| 画像 | [表示] を選びます。  |  

既定では、Web ページを更新すると編集は破棄されます。  変更をファイル システムに保存する方法については、上記の「Using the Filesystem tab to define a local [Workspace」を参照](#using-the-filesystem-tab-to-define-a-local-workspace)してください。

次のサブセクションでは、[エディター] ウィンドウについて説明します。  

*   [JavaScript ファイルの編集](#editing-a-javascript-file)  
*   [美しい印刷を使用して、Minified JavaScript ファイルを再フォーマットする](#reformatting-a-minified-javascript-file-with-pretty-print)  
*   [読み取り可能なコードを表示するソース コードへのマイニング コードのマッピング](#mapping-minified-code-to-your-source-code-to-show-readable-code)  
*   [ソース コードからコンパイル済みのフロントエンド コードへの変換](#transformations-from-source-code-to-compiled-front-end-code)  
*   [CSS ファイルの編集](#editing-a-css-file)  
*   [HTML ファイルの編集](#editing-an-html-file)  
*   [行番号または関数にアクセスする](#going-to-a-line-number-or-function)  
*   [別のツールを使用する場合のソース ファイルの表示](#displaying-source-files-when-using-a-different-tool)  
    
### <a name="editing-a-javascript-file"></a>JavaScript ファイルの編集

DevTools で JavaScript ファイルを編集するには、[ソース] ツール **内の [** エディター] **ウィンドウを使用** します。

:::image type="complex" source="../media/editing-js-in-editor-pane.msft.png" alt-text="[エディター] ウィンドウでの JavaScript の編集" lightbox="../media/editing-js-in-editor-pane.msft.png":::
   [ **エディター** ] ウィンドウでの JavaScript の編集  
:::image-end:::

ファイルをエディター ウィンドウに読み込むには****、ナビゲーター ウィンドウ**** \(左側\) の [ページ] タブを使用します。  または、 **次のようにコマンド**メニューを使用します。DevTools の右上隅で **、[DevTools** \( \) のカスタマイズと制御] を選択し、[ファイルを開く] を `...` **選択します**。

#### <a name="save-and-undo"></a>保存と元に戻す

JavaScript の変更を有効にするには`Ctrl`+`S` [\(Windows, Linux\)] または`Command`+`S` [\(macOS\)] を選択します。  

ファイルを変更すると、ファイル名の横にアスタリスクが表示されます。  

*   変更を保存するには、Windows/Linux または `Ctrl` + `S` `Command` + `S` macOS で選択します。  
*   変更を元に戻すには、Windows/Linux または `Ctrl` + `Z` `Command` + `Z` macOS で選択します。  
    
既定では、Web ページを更新すると編集内容は破棄されます。  ローカル ファイル システムに変更を保存する方法の詳細については、「Workspaces を使用してファイルを編集する [」を参照してください][DevtoolsGuideChromiumWorkspacesIndex]。

#### <a name="find-and-replace"></a>検索と置換

現在のファイル内のテキストを検索するには、[**** エディター] ウィンドウを選択してフォーカスを設定し `Ctrl` + `F` 、Windows/Linux、 `Command` + `F` または macOS で選択します。  

:::image type="complex" source="../media/find-replace.msft.png" alt-text="検索と置換(Sources ツールのエディター ウィンドウ)" lightbox="../media/find-replace.msft.png":::
   **検索**と**置換**、ソース ツール**の**エディター**ウィンドウで**
:::image-end:::

テキストを検索して置き換える**** 場合は、[検索] テキスト ボックスの左側にある **[\( A-\>B**\) の置換] ボタン**を**選択します。  編集可能 **な** ファイルを表示**すると、[\( A-\>B**\) を置き換える] ボタンが表示されます。

#### <a name="showing-the-changes-you-made"></a>行った変更の表示

ファイルに加えた変更を確認するには、[エディター] ウィンドウで右**** クリックし、[ローカル変更]**を選択します**。

**DevTools**の下部にドロワーが開き、[変更] タブに変更が**表示**されます。

:::image type="complex" source="../media/local-modifications.msft.png" alt-text="ドロワーの [変更] タブでローカル変更を表示する" lightbox="../media/local-modifications.msft.png":::
   ドロワー **の [** 変更] タブ **で** 、ローカル変更を表示 **する**
:::image-end:::

#### <a name="changes-inside-a-function-take-effect"></a>関数内の変更が有効

DevTools はスクリプトを再実行しないので、有効な JavaScript の変更は、関数内で行う変更のみです。  たとえば、次の図では、サーバーによって返される JavaScript に次のコードを追加しました。  
*   任意の関数の外部に `console.log('A')` ステートメントを追加しました。  
*   関数内にステートメント `console.log('B')` を追加 `onClick` しました。  
その後、変更を保存し、フォームに番号を入力し、フォームを送信するフォーム ボタンを選択しました。  

グローバル スコープにあるフォームを送信した後は実行されませんが、関数内で実行され、コンソール `console.log('A')` `console.log('B')` `onClick` `B` に出力されます。

:::image type="complex" source="../media/edit-js.msft.png" alt-text="グローバル スコープの JavaScript が再実行されない" lightbox="../media/edit-js.msft.png":::
   グローバル スコープの JavaScript が再実行されない  
:::image-end:::

### <a name="reformatting-a-minified-javascript-file-with-pretty-print"></a>美しい印刷を使用して、Minified JavaScript ファイルを再フォーマットする

ファイルを読み取り可能な形式に変更するには、[エディター] ウィンドウの**** 下部に中かっことして表示される [プリティ印刷] ボタン \( ![ Format \) を選択します。 ](../media/format-icon.msft.png)  または、[エディター] **ウィンドウの** 上部に [印刷] ボタンが表示されている場合は、そのボタンを選択できます。

:::image type="complex" source="../media/minified.msft.png" alt-text="[プリティ印刷] ボタン" lightbox="../media/minified.msft.png":::
   [ **プリティ印刷]** ボタン  
:::image-end:::  

再フォーマットされたファイルが新しいタブに表示され、ファイル `:formatted` 名に追加されます。  再フォーマットされたコードは読み取り専用です。  

:::image type="complex" source="../media/pretty-printed.msft.png" alt-text="かなり印刷された (再フォーマットされた) JavaScript ファイル" lightbox="../media/pretty-printed.msft.png":::
   かなり印刷された \(reformatted\) JavaScript ファイル  
:::image-end:::  

再フォーマットされたファイルを、minified ファイルで選択したコードまでスクロールするには、次の方法を実行します。  

1.  [再フォーマットされたファイル] タブが開いている場合は、閉じます。  
1.  [エディター] ウィンドウで、マイニング ファイル内のコードを選択します。
1.  [きれいな印刷 **] ボタンを選択** します。  
     
書式設定されたコードが新しいタブに表示され、選択したコードまでスクロールされます。

詳細については、「美しい印刷 [を使用して、ミニマ化された JavaScript ファイルを再フォーマットする」を参照してください][DevToolsJavaScriptReferenceReformat]。  

### <a name="mapping-minified-code-to-your-source-code-to-show-readable-code"></a>読み取り可能なコードを表示するソース コードへのマイニング コードのマッピング

プリプロセッサからのソース マップを使用すると、DevTools は、サーバーによって返される、変換された、最小化された JavaScript ファイルに加えて、元の JavaScript ソース ファイルを読み込む原因になります。  次に、ブレークポイントを設定し、コードをステップ実行しながら、元のソース ファイルを表示します。  一方、Microsoft Edgeコードが実際に実行されています。  

[エディター **] ウィンドウ**で JavaScript ファイルを右クリックし、[ソース**** マップの追加] を選択すると、ポップアップ ボックスが表示され、[ソース マップ**URL]** テキスト ボックスと [追加] ボタンが**表示**されます。

ソース マッピングの方法では、結合、ミニファイ、またはコンパイルした後でも、フロントエンド コードを人間が読み取り、デバッグできます。
詳細については、「前処理された [コードをソース コードにマップする」を参照してください][DevToolsJavaScriptSourceMaps]。

### <a name="transformations-from-source-code-to-compiled-front-end-code"></a>ソース コードからコンパイル済みのフロントエンド コードへの変換

javaScript ファイルを変換するフレームワーク (React など) を使用する場合、ローカル ソース JavaScript が、サーバーによって返されるフロントエンド JavaScript とは異なる場合があります。  このシナリオではワークスペースはサポートされていませんが、このシナリオではソース コードマッピングがサポートされています。  

開発環境では、サーバーにソース マップと、ユーザーの元のマップまたはファイルが含 `.ts` `.jsx` React。  [ **ソース] ツール** は、これらのファイルを表示しますが、これらのファイルを編集できます。  ブレークポイントを設定してデバッガーを使用すると、DevTools は元のファイルまたはファイルを表示しますが、実際には JavaScript ファイルの最小バージョンを `.ts` `.jsx` ステップスルーします。

このシナリオでは **、Sources** ツールは、サーバーから返される変換済みフロントエンド JavaScript の検査とステップスルーに役立ちます。  デバッガーを使用してウォッチ式を定義し、コンソールを使用して JavaScript 式を入力してスコープ内のデータを操作します。

### <a name="editing-a-css-file"></a>CSS ファイルの編集

DevTools で CSS を編集するには、次の 2 つの方法があります。  

*   要素ツール **では** 、ユーザー インターフェイス コントロールを使用して、一度に 1 つの CSS 設定を操作します。  ほとんどの場合、この方法をお勧めします。  詳細については、「スタイル」ウィンドウ [の「EDIT CSS フォント スタイルと設定」を参照してください][DevToolsInspectStylesEditFonts]。  
*   [ソース **] ツールでは** 、テキスト エディターを使用します。  
    
Sources ツールでは、CSS ファイルの直接編集がサポートされています。  たとえば、以下のスタイル ルールに一致するワークスペース[][DevtoolsGuideChromiumWorkspacesIndex]を使用してファイルを編集するチュートリアルから CSS ファイルを編集すると、レンダリングされた Web ページの左上にある要素が緑色 `H1` に変わります。

```css
h1 {
  color: green;
}  
```  

:::image type="complex" source="../media/edit-css.msft.png" alt-text="[エディター] ウィンドウで CSS を編集して、H1 見出しのテキストの色を緑に変更する" lightbox="../media/edit-css.msft.png":::
   [エディター] ウィンドウで CSS **を** 編集して、見出しのテキストの色を `H1` 緑に変更する  
:::image-end:::  

CSS の変更は直ちに有効になります。変更を手動で保存する必要はありません。

#### <a name="see-also"></a>関連項目  

*   [[スタイル] ウィンドウで CSS フォントのスタイルと設定を編集する][DevToolsInspectStylesEditFonts]  
*   [初級者向け DevTools: CSS の使用を開始][DevToolsBeginnersCss] する - チュートリアル  
    
### <a name="editing-an-html-file"></a>HTML ファイルの編集

DevTools で HTML を編集するには、次の 2 つの方法があります。  

*   要素ツール **では** 、ユーザー インターフェイス コントロールを使用して、一度に 1 つの HTML 要素を操作します。  
*   [ソース **] ツールでは** 、テキスト エディターを使用します。  
    
:::image type="complex" source="../media/sources-html-editor.msft.png" alt-text="ソース ツールの HTML エディター" lightbox="../media/sources-html-editor.msft.png":::
   ソース ツールの HTML**エディター**
:::image-end:::  

JavaScript ファイルや CSS ファイルとは異なり、Web サーバーから返される HTML ファイルをソース ツールで直接編集することはできません。  ソース ツールのエディターを使用して HTML ファイルを編集するには、HTML ファイルがワークスペースまたは [上書き] タブ **にある必要** があります。 現在の記事の次のサブセクションを参照してください。  

*   [[ファイルシステム] タブを使用してローカル ワークスペースを定義する](#using-the-filesystem-tab-to-define-a-local-workspace)  
*   [[上書き] タブを使用してサーバー ファイルをローカル ファイルで上書きする](#using-the-overrides-tab-to-override-server-files-with-local-files)  
   
変更を保存するには、Windows/Linux または `Ctrl` + `S` `Command` + `S` macOS で選択します。  編集したファイルにはアスタリスクが付きます。  
テキストを見つけるには、Windows/Linux または `Ctrl` + `F` `Command` + `F` macOS で選択します。  
編集を元に戻すには、Windows/Linux または `Ctrl` + `Z` `Command` + `Z` macOS で選択します。  
HTML ファイルの編集中に他のコマンドを表示するには、[エディター] ウィンドウで HTML ファイルを右クリックします。  
また、DevTools ではなく HTML エディターを使用して HTML を編集することもできます。  たとえば、記事 [「DevTools for beginners: Get started][DevToolsBeginnersHtml] with HTML and THE DOM は Web ページ内で HTML 編集を可能にする Web サイトを使用します。  

### <a name="going-to-a-line-number-or-function"></a>行番号または関数にアクセスする

エディター ウィンドウで開いているファイル内の行番号または記号 \(関数名\など) に移動するには、ファイルをスクロールするのではなく、コマンド メニューを使用できます。

1.  [ナビゲーター **] ウィンドウで**、省略記号 \( \) \( More options \) を選択し、[ファイルを開く `...` ]**を選択します**。****  [コマンド] メニューが表示されます。  
1.  次のいずれかの文字を入力します。  
     
| 文字 | コマンド名 | 目的 |  
|:--- |:--- |:--- |  
| \: | **行に移動する** | 行番号に移動します。  |  
| \@ | **記号に移動する** | 関数に移動します。  入力すると、[エディター] ウィンドウで開いている JavaScript ファイルにある関数がコマンド `@` メニューに一覧表示されます。  |  
   
詳細については[、「DevTools コマンド メニューを使用してコマンドMicrosoft Edge実行する」を参照してください][DevToolsCommandMenuIndex]。

### <a name="displaying-source-files-when-using-a-different-tool"></a>別のツールを使用する場合のソース ファイルの表示

DevTools でソース ファイルを表示する主な場所は、ソース ツール **内** です。  ただし、ソース ファイルの表示または編集中に **、Elements** や **Console**などの他のツールにアクセスする必要がある場合があります。  ドロワー **で [クイック ソース]** ツールを使用 [します][DevtoolsCustomizeIndexDrawer]。  

1.  [要素] ツールなど、[ソース] ツール **以外** のツール **を選択** します。  
1.  `Ctrl` + `Shift` + `P` \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  [コマンド] メニューが開きます。  
1.  を `Quick Source` 入力し、[クイック ソースの **表示] を選択します**。  DevTools ウィンドウの下部に、[クイック ソース] パネルが選択されたドロワー **が** 表示されます。  [**クイック ソース]** パネルには、ソース ツールで編集**** した最後のファイルが、コンパクト バージョンの DevTools コード エディター内に表示されます。  
1.  `Ctrl` + `P` \(Windows Linux\) または \(macOS\) を選択して、[ファイルを開く `Command` + `P` ]**ダイアログを開**きます。  
    
## <a name="using-the-debugger-pane-to-debug-javascript-code"></a>デバッガー ウィンドウを使用して JavaScript コードをデバッグする

JavaScript デバッガーを使用して、サーバーから返される JavaScript コードをステップ実行します。  
デバッガーには、 **デバッガー ウィンドウ** と、エディター ウィンドウのコード行に設定したブレークポイントが **含** まれます。

デバッガーを使用して、指定した JavaScript 式を確認しながら、コードをステップ実行します。  変数の値を監視して手動で変更し、現在のステートメントのスコープ内にある変数を自動的に表示します。

:::image type="complex" source="../media/sources-paused-breakpoint-highlight-debug-pane.msft.png" alt-text="ソース ツールのデバッガー ウィンドウ  " lightbox="../media/sources-paused-breakpoint-highlight-debug-pane.msft.png":::
   ソース**ツール**のデバッガー**ウィンドウ**  
:::image-end:::  

デバッガーは、次のような標準的なデバッグ アクションをサポートしています。  

*   ブレークポイントを設定し、コードを一時停止します。  
*   コードをステップ実行します。  
*   プロパティと変数の表示と編集。  
*   JavaScript 式の値を確認する。  
*   呼び出し履歴\ (ここまでの関数呼び出しのシーケンス\) を表示します。  
    
DevTools のデバッガーは、デバッガーと同じ外観、外観、[][VisualStudioCodeDocsEditorDebugging]および動作をVisual Studio Codeのデバッガー[と][VisualStudioDebuggerNavigatingThroughCodeWithTheDebugger]同Visual Studio。

次のサブセクションでは、デバッグについて説明します。  

*   [デバッガーを使用する基本的な方法](#the-basic-approach-to-using-a-debugger)  
*   [デバッガーの Watch と Scope over console.log の利点](#advantages-of-the-debuggers-watch-and-scope-over-consolelog)  
*   [直接Visual Studio Codeデバッグ](#debug-from-visual-studio-code-directly)  
*   [デバッグに関する記事](#articles-about-debugging)  
    
### <a name="the-basic-approach-to-using-a-debugger"></a>デバッガーを使用する基本的な方法

JavaScript コードのトラブルシューティングを行う場合は、[エディター] ウィンドウ `console.log()` にステートメントを **挿入** します。  もう 1 つの強力な方法は、DevTools のデバッガー Microsoft Edgeです。  デバッガーの使用は、デバッガーのアプローチに慣れたら、より `console.log()` 簡単です。

Web ページでデバッガーを使用するには、通常、ブレークポイントを設定し、次のように Web ページからフォームを送信します。

1.  ブラウザーの新しいタブで Web ページを開きます。  たとえば、このフォーム Web ページを新しいタブで開きます:Demo: はじめに デバッグ JavaScript with Microsoft Edge [(Chromium) DevTools][GlitchMicrosoftEdgeChromiumDevtoolsDebugJsGetStarted].  
1.  `F12` **[DevTools] ウィンドウを開き、[** ソース] タブ**を選択します**。  
1.  [ナビゲーター **] ウィンドウ**\(左側\) で****、[ページ] タブを選択し、 などの JavaScript ファイルを選択します `get-started.js` 。  
1.  [エディター **] ウィンドウ** で、疑わしいコード行の近くの行番号を選択して、その行にブレークポイントを設定します。  下の図では、ブレークポイントが行に設定されています `var sum = addend1 + addend2;` 。  
1.  Web ページで値を入力し、フォームを送信します。  たとえば、番号を入力し、[番号 1 の追加] ボタンと [番号 `5` `1` **2] を選択します**。  
    
    デバッガーは JavaScript コードを実行し、ブレークポイントで一時停止します。  デバッガーが一時停止モードに切り替わるので、スコープ内のプロパティの値を検査し、コードをステップ実行できます。  
    
    :::image type="complex" source="../media/sources-paused-breakpoint-highlights.msft.png" alt-text="デバッガーの一時停止モードに入る" lightbox="../media/sources-paused-breakpoint-highlights.msft.png":::
        デバッガーの一時停止モードに入る  
    :::image-end:::  
    
    上の図では、ウォッチ式と、ブレークポイントを越えた `sum` `typeof sum` 2 行のステップを追加しました。  
    
1.  [スコープ] ウィンドウの **値を** 調べて、現在のブレークポイントのスコープ内のすべての変数またはプロパティとその値を表示します。  または、[ウォッチ] ウィンドウに式 **を追加** します。  これらの式は、コードをデバッグするためにステートメント内で記述する式 `console.log` と同じです。  JavaScript コマンドを実行して現在のコンテキストでデータを操作するには、コンソール を使用 **します**。  コンソールを開く場合は、 を選択します `Esc` 。  
1.  デバッガー ウィンドウの上部にあるコントロール (Step \( **** \) など) を使用して、コード**を** `F9` ステップ実行します。
    
#### <a name="see-also"></a>関連項目

*   [JavaScript のデバッグの開始][DevtoolsGuideChromiumJavascriptIndex] - いくつかのフォーム コントロールを含む既存の単純な Web ページを使用したチュートリアル。
    
### <a name="advantages-of-the-debuggers-watch-and-scope-over-consolelog"></a>デバッガー\'s Watch and Scope over console\.log の利点  

これら 3 つの方法は同等です。

*   ステートメントを一時的に `console.log(sum)` 追加 `console.log(typeof sum)` し、スコープ内の `sum` コードに追加します。  
*   デバッガーがスコープ内の場所で一時停止されている場合に、DevTools の [コンソール] ウィンドウでステートメント `sum` `console.log(typeof sum)` **** `sum` を発行します。  
*   [ウォッチ式 **]** と `sum` [ `typeof sum` デバッガー] ウィンドウ **を設定** します。  
    
変数がスコープ内で、その値がデバッガー ウィンドウの [スコープ] セクションに自動的に表示され、計算される [エディター] ウィンドウにもオーバーレイ `sum` `sum` ******** `sum` されます。  そのため、ウォッチ式を定義する必要はおそらくない `sum` でしょう。

デバッガーは、ステートメントよりもリッチで柔軟性の高い表示と環境を提供 `console.log` します。  たとえば、デバッガーでコードをステップ実行すると、現在定義されているプロパティと変数の値を表示および変更できます。  スコープ内の配列の値を変更するなどの**** JavaScript ステートメントをコンソールで発行することもできます。  \(コンソールを表示するには **、Esc**.\) を選択します。

ブレークポイントとウォッチ式は、Web ページを更新すると保持されます。

### <a name="debug-from-visual-studio-code-directly"></a>直接Visual Studio Codeデバッグ

DevTools デバッガーの代わりに Visual Studio Code のよりフル機能のデバッガーを使用するには、Microsoft Edge**ツールを**VS Code拡張機能Visual Studio Code。

:::image type="complex" source="../media/microsoft-edge-tools-for-vs-code-extension.msft.png" alt-text="[Microsoft Edge ツール] VS Codeの拡張機能Visual Studio Code" lightbox="../media/microsoft-edge-tools-for-vs-code-extension.msft.png":::
   **[Microsoft Edgeツール] VS Code**の拡張機能Visual Studio Code  
:::image-end:::  

この拡張機能は、DevTools**** の要素とネットワーク ツールMicrosoft Edgeコード内からMicrosoft Visual Studioします。 ****  

詳細については、「開発者向[け][VisualStudioCodeIndex]ツールVisual Studio Codeの概要」および「GitHub Readme」ページ[Microsoft Edgeを参照Visual Studio Code。][GithubMicrosoftVscodeEdgeDevtools]

### <a name="articles-about-debugging"></a>デバッグに関する記事

次の記事では、デバッガー ウィンドウ **と** ブレークポイントについて説明します。

*   [DevTools での JavaScript][DevtoolsGuideChromiumJavascriptIndex]のデバッグMicrosoft Edge始める - 既存の単純なプロジェクトを使用したチュートリアル \(screen captures\を使用)。  
*   [デバッガー機能を使用][DevToolsJavaScriptReference] する - デバッガーを使用してブレークポイントの設定、コードのステップ実行、変数値の表示と変更、JavaScript 式の監視、通話履歴の表示を行う方法。  
*   [ブレークポイントでコードを一時停止する][DevToolsJavaScriptBreakpoints] - デバッガーで基本的なブレークポイントと特殊なブレークポイントを設定する方法。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsBeginnersCss]: ../beginners/css.md "初級者向け DevTools: CSS の使用|Microsoft Docs"  
[DevToolsBeginnersHtml]: ../beginners/html.md "初級者向け DevTools: HTML と DOM の使用を|Microsoft Docs"  
[DevToolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行する | Microsoft Docs"   
[DevtoolsCustomizeIndexDrawer]: ../customize/index.md#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "DevTools Microsoft Edge配置を変更する (Undock、Dock to bottom、Dock to left) |Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptIndex]: ../javascript/index.md "DevTools アプリケーションの JavaScript のデバッグMicrosoft Edge開始|Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptSnippets]: ../javascript/snippets.md "DevTools を使用して任意の Web ページで JavaScript のスニペットMicrosoft Edge実行|Microsoft Docs"  
[DevtoolsGuideChromiumWorkspacesIndex]: ../workspaces/index.md "Workspaces を使用してファイルを編集|Microsoft Docs"  
[DevToolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "[スタイル] ウィンドウの [CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevToolsJavaScriptBreakpoints]: ../javascript/breakpoints.md "ブレークポイントを使用してコードを一時停止|Microsoft Docs"  
[DevToolsJavaScriptGuidesMarkContentScriptsLibraryCode]: ../javascript/guides/mark-content-scripts-library-code.md "コンテンツ スクリプトをライブラリ コード としてマーク|Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ../javascript/overrides.md "DevTools を使用して Web ページ リソースをローカル コピー Microsoft Edgeオーバーライド|Microsoft Docs"  
[DevToolsJavaScriptReference]: ../javascript/reference.md "デバッガー機能を使用|Microsoft Docs"  
[DevToolsJavaScriptReferenceReformat]: ../javascript/reference.md#reformat-a-minified-javascript-file-with-pretty-print "簡易印刷を使用して、ミニマ化された JavaScript ファイルを再フォーマットする - デバッガー機能を使用|Microsoft Docs"  
[DevToolsJavaScriptSourceMaps]: ../javascript/source-maps.md "前処理されたコードをソース コード にマップ|Microsoft Docs"  
[VisualStudioCodeIndex]: ../../visual-studio-code/index.md "Visual Studio Code概要|Microsoft Docs"  
[ExtensionsChromiumGetstartPart2ContentScripts]: ../../extensions-chromium/getting-started/part2-content-scripts.md "拡張機能チュートリアルの作成 パート 2 |Microsoft Docs"  

[VisualStudioDebuggerNavigatingThroughCodeWithTheDebugger]: /visualstudio/debugger/navigating-through-code-with-the-debugger "デバッガー ウィンドウを使用してコードVisual Studio移動|Microsoft Docs"  

[VisualStudioCodeDocsEditorDebugging]: https://code.visualstudio.com/docs/editor/debugging "デバッグ|Visual Studio Code"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "Microsoft Edge開発者向けツール Visual Studio Code |GitHub"  

[GlitchMicrosoftEdgeChromiumDevtoolsDebugJsGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "デモ: はじめに (Chromium) DevTools を使用Microsoft Edge JavaScript のデバッグ|Microsoft Docs"  

[WhatwgHtmlSpecMulitpageOriginHtmlOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "Origin |HTML 標準"  

[MdnAddOnsWebextensionsContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "コンテンツ スクリプト|MDN"  

[TypescriptlangMain]: https://www.typescriptlang.org "TypeScript"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "フレーム |W3C"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/sources) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  

<!--todo: needs an accessibility review to replace "view", "see", and "look" with "display", exception is "see also" headings -->  

<!--todo: need a consistency review to replace all UI interactions with "choose" and all keyboard interactions with "select" -->  
