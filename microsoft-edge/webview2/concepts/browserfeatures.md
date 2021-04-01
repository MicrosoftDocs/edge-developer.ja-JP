---
説明: Microsoft Edge と WebView2 タイトルの機能の違い: Microsoft Edge と WebView2 作成者の機能の違い: MSEdgeTeam ms.author: msedgedevrel ms.date: 03/31/2021 ms.topic: conceptual ms.prod: microsoft-edge ms.technology: webview キーワード: IWebView2, IWebView2WebView、WebView2、Webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html no-loc:
- "Autofill for Addresses"
- "Autofill for Passwords"
- "Autofill for Payments""
- "Browser Extensions""
- "Browser Task Manager"
- "Collections"
- "Continue-where-I-left-off prompt"
- "Downloads"
- "Edge Shopping"
- "Family Safety"
- "Favorites"
- "Hotkeys"
- "IE Mode"
- "Immersive Reader"
- "Intrusive Ads"
- "Read Aloud"
- "Smart Screen"
- "Translate"
- "Tracking Prevention"
- "Profile and Identity"
- "Web Payment API"
- "Windows Defender Application Guard"
- "edge:// URLs"

---
# <a name="browser-feature-differences-between-microsoft-edge-and-webview2"></a>Microsoft Edge と WebView2 のブラウザー機能の違い  

WebView2 は、新しい Microsoft Edge ブラウザーに基づいて作成されます。  ブラウザーから WebView2 ベースのアプリに機能を拡張する機会があります。これは便利です。  ただし、WebView2 はブラウザーのようなアプリに限定されないので、変更または削除する必要があるブラウザー機能があります。   この記事では、次の情報を提供します。  

*   変更されたブラウザー機能とサポート情報。   
*   機能のオンとオフを切り替える機能。  
*   キーボード ショートカットに関するガイダンス。  
    
## <a name="design-guidelines"></a>設計ガイドライン  

WebView2 のコンテキストでは、ブラウザー機能は次の設計ガイドラインに従います。  

*   ほとんどの機能は、WebView2 と Microsoft Edge で同じように動作します。  WebView2 のコンテキストや他の理由で機能が意味をなさない場合、機能は変更または無効になります。 
*   WebView2 の機能には、Microsoft Edge のブランド化は含めかねない。  
    
## <a name="features"></a>機能  

次の表に、Microsoft Edge ブラウザーとは異なる WebView2 機能を示します。   

*   **既定の** 状態は、機能が新しい WebView2 インスタンスの既定のエクスペリエンスの一部を示します。  
*   **[構成** 可能] は、WebView2 API またはコマンド ライン スイッチを使用して機能を有効またはオフにできる可能性を示します。  
    
> [!NOTE]  
> この記事では、コマンド ライン スイッチを使用した機能の変更について説明します。  コマンド ライン スイッチを使用して機能をオンまたはオフにする方法の詳細については、「クロム コマンド ライン スイッチの一覧 [」に移動します][PeterExperimentsChromiumCommandLineSwitches]。  
    
| 機能 | 既定の状態 | 構成可能 | 詳細 |  
|:--- |:--- |:--- | :--- |  
| Autofill for Addresses | オン | あり | この機能は既定でオンになっています。WebView2 オートフィル API を使用してオンまたはオフにできます。  |  
| Autofill for Passwords | オン | あり | この機能は既定でオンになっています。WebView2 オートフィル API を使用してオンまたはオフにできます。  |  
| 支払いの自動入力 | オフ | × | この機能はオフです。  |  
| ブラウザー拡張機能 | オフ | × | この機能はオフです。  |  
| Browser Task Manager | オフ | × | この機能はオフです。  |  
| Collections | オフ | × | この機能はオフです。  |  
| Continue-where-I-left-off prompt | オフ | × | この機能はオフです。  |  
| Downloads | オン | あり | WebView2 には、ダウンロード UI をカスタマイズしてダウンロードを操作できる API が提供されています。 たとえば、ブロック、リダイレクト、保存、一時停止などです。  <!--For more information, navigate to [download API][Webview2ReferenceDownloadApi].--> |  
| Edge Shopping | オフ | × | この機能はオフです。  |  
| Family Safety | オフ | × | この機能はオフです。  |  
| Favorites | オフ | × | この機能はオフです。  |  
| IE Mode | オフ | × | この機能はオフです。  |  
| Immersive Reader | オフ | × | この機能は、操作のブラウザー UI によって異なります。  この機能はオフです。  |  
| Intrusive Ads | オフ | × | この機能はオフです。  |  
| キーボード ショートカット | レビューの詳細 | レビューの詳細 | 既定でオフになっているキーボード ショートカットは、意味をなさないか、WebView2 で問題を引き起こします。  これらのショートカットを有効またはオフにしない場合があります。  代わりに、イベントを使用してキーの組み合わせをリッスンし、必要に応じてカスタム `AcceleratorKeyPressed` 応答を作成できます。  詳細については、「その他のキーボード [ショートカット情報」に移動します](#additional-keyboard-shortcuts-information)。 |  
| Read Aloud | オフ | × | この機能はオフです。  |  
| Smart Screen | オン`*` | × | `*` この機能の UI は削除されましたが、基になる機能は引き続き使用できます。  また、コマンド ライン スイッチを Smart Screen 使用してオフにすることもできます。  |  
| Translate | オフ | × | この機能はオフです。  |  
| Tracking Prevention | オン`*` | × | `*` この機能の UI は削除されましたが、基になる機能は引き続き使用できます。  追跡防止は常にバランスに設定されます。|  
| Profile and Identity | オフ | × | お気に入り、Cookie などと同期する機能はオフになります。  |  
| Web Payment API | オフ | × | この機能はオフです。  | 
| Windows Defender Application Guard | オフ | × | この機能はオフです。  |  
| edge:// URLs | レビューの詳細 | × | Microsoft Edge ブラウザーの設定は `edge://` URL にあります。  これらの Web ページのほとんどが Microsoft Edge のブランド化を持つか、WebView2 のコンテキスト内で意味をなさないので、これらの URL の一部は無効になります。  詳細については、「ブロックされた内部 [URL」に移動します](#blocked-internal-urls)。  |  

## <a name="blocked-internal-urls"></a>ブロックされた内部 URL  

次の Microsoft Edge と Google Chrome の設定 Web ページは、WebView2 では使用できません。  

*   `chrome-search://local-ntp/local-ntp.html`  
*   `edge://application-guard-internals`  
*   `edge://apps`  
*   `edge://compat`  
*   `edge://extensions`  
*   `edge://favorites`  
*   `edge://help`  
*   `edge://management`  
*   `edge://network-error`  
*   `edge://new-tab-page`  
*   `edge://newtab`  
*   `edge://omnibox`  
*   `edge://settings`  
*   `edge://supervised-user-internals`  
*   `edge://version`  

## <a name="additional-keyboard-shortcuts-information"></a>その他のキーボード ショートカット情報  

Microsoft Edge と WebView2 では、キーボード ショートカットまたはキー バインドがサポートされています。  Microsoft Edge が更新された場合、既定のキー バインドが変更される場合があります。  さらに、WebView2 で機能がサポートされている場合は、既定で無効になっているキーボード ショートカットが有効になります。  キーボード ショートカットの変更を避けるため、ブラウザー機能にアクセスするキーはすべて無効にし、基本的なテキスト編集ショートカットと移動ショートカットはすべてオンに維持します `AreBrowserAcceleratorKeysEnabled` `FALSE` 。  

次の表に、WebView2 で常に無効になっているショートカットの一覧を示します。  アスタリスク \( \) 文字は、ショートカットがオフではないが、アクセスする機能がオフになっているか、WebView2 に適用されません。 `*`  

| 操作 | Windows |  
|:--- |:--- |  
| に追加する Favorites | `Ctrl`+`D` |  
| [すべてのタブの追加] Favorites | `Ctrl`+`Shift`+`D` |  
| フォーカスの場所 | `Ctrl`+`L, Alt`+`D` |  
| 貼り付けと移動 | `Ctrl`+`Shift`+`L` |  
| ファイルを開く | `Ctrl`+`O` |  
| Read Aloud `*` | `Ctrl`+`Shift`+`U` |  
| Web キャプチャ `*` | `Ctrl`+`Shift`+`S` |  
| サイドバー `*` | `Ctrl`+`Shift`+`E` |  
| [ページの保存] | `Ctrl`+`S` |  
| [最後のタブ] を選択する | `Ctrl`+`9` |  
| [次へ] タブを選択する | `Ctrl`+`Tab` |  
| [前へ] タブを選択する | `Ctrl`+`Shift`+`Tab` |  
| Tab \(1 - 8\) を選択する | `Ctrl`+`(1-8)` |  
| [バーの Favorites 表示] `*` | `Ctrl`+`Shift`+`B` |  
| ヘルプ | `F1` |  
| [次のウィンドウにフォーカス] `*` | `F6` |  
| [前のウィンドウにフォーカス] `*` | `Shift`+`F6` |  
| キャレットブラウズ `*` | `F7` |  
| 閲覧ビュー `*` | `F9` |  
| フォーカス メニュー バー | `F10` |  
| [ID の表示] メニュー `*` | `Ctrl`+`Shift`+`M` |  
| Browser Task Manager `*` | `Shift`+`Escape` |  
| エッジ フィードバック `*` | `Shift`+`Alt`+`I` |  
| [ミュート] タブ `*` | `Ctrl`+`M` |  
| 新しいシークレット ウィンドウ | `Ctrl`+`Shift`+`N` |  
| 新しいタブ | `Ctrl`+`T` |  
| 新しいウィンドウ | `Ctrl`+`N` |  
| [最後に閉じたタブを復元] | `Ctrl`+`Shift`+`T` |  
| Focus Favorites | `Alt`+`Shift`+`B` |  
| フォーカス 非アクティブ ポップアップ | `Alt`+`Shift`+`A` |  
| フォーカス検索 | `Ctrl`+`E`, `Ctrl`+`K`, `Search Key` |  
| [重複] タブ | `Ctrl`+`Shift`+`K` |  
| フォーカス ツールバー `*` | `Alt`+`Shift`+`T` |  
| Home | `Alt`+`Home`, `Browser Home Key` |  
| [アプリ の表示] メニュー | `Alt`+`E, Alt`+`F` |  
| 注文詳細 Favorites | `Ctrl`+`Shift`+`O` |  
| 注文詳細 Downloads | `Ctrl`+`J` |  
| 履歴の表示 | `Ctrl`+`H` |  
| 読み取りモード バーを表示する `*` | `Shift`+`Alt`+`R` |  
| 注文詳細 Collections `*` | `Ctrl`+`Shift`+`Y` |  

イベントが処理されていないときに表示されるウィンドウを除き、次のキーボード ショートカットは常 `NewWindowRequested` にオフになります。

| 操作 | Windows |  
|:--- |:--- |  
| タブを閉じる | `Ctrl`+`W, Ctrl`+`F4` |  
| ウィンドウを閉じる | `Ctrl`+`Shift`+`W` |  
| 全画面表示 | `F11` |  

に設定すると `AreBrowserAcceleratorKeysEnabled` `FALSE` 、次の追加のキーボード ショートカットがオフになります。  

| 操作 | Windows |  
|:--- |:--- |  
| Stop | `Escape` |  
| ページで検索する | `Ctrl`+`F` |  
| [次へ] を検索する | `Ctrl`+`G` |  
| 前の検索 | `Ctrl`+`Shift`+`G` |  
| 印刷 | `Ctrl`+`P` |  
| Refresh | `Ctrl`+`R`, `F5`, `Reload Key` |  
| キャッシュなしの更新 | `Ctrl`+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+`Refresh` |  
| ズームアウト | `Ctrl`+`-` |  
| 拡大 | `Ctrl`+`+` |  
| ズームのリセット | `Ctrl`+`0` |  
| [次へ] を検索する | `F3` |  
| 前の検索 | `Shift`+`F3` |  
| 戻る | `Alt`+`Left, Browser Back Key` |  
| Forward | `Alt`+`Right`, `Browser Forward Key` |  
| 印刷 | `Ctrl`+`P` |  
| DevTools を開く/閉じる | `Ctrl`+`Shift`+`I` |  
| DevTools コンソールを開く | `Ctrl`+`Shift`+`J` |  
| Open DevTools Inspect | `Ctrl`+`Shift`+`C` |  

> [!Note] 
> キーを個別にカスタマイズするには [、AcceleratorKeyPressed イベントを使用][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] します。  
  
  
## <a name="getting-in-touch-with-the-microsoft-edge-webview2-team"></a>Microsoft Edge WebView2 チームと連絡を取る  

[!INCLUDE [contact WebView2 team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

<!--[Webview2ReferenceDownloadApi]: ./download-api.md "download API | Microsoft Docs"  -->  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2controller.acceleratorkeypressed?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2Controller.AcceleratorKeyPressed イベント |Microsoft Docs"  

[DevtoolsShortcutsIndex]: ../../devtools-guide-chromium/shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

[PeterExperimentsChromiumCommandLineSwitches]: https://peter.sh/experiments/chromium-command-line-switches "クロム コマンド ライン スイッチの一覧|Peter Beverloo"  
