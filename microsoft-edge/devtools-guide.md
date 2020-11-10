---
description: Microsoft Edge (EdgeHTML) 開発者ツールのタイトルを理解する
title: Microsoft Edge (EdgeHTML) 開発者ツールの作成者
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web development, f12 tools, devtools
experimental: true
experiment_id: "51fe4b97-3e55-41"
ms.localizationpriority: high
---

# Microsoft Edge (EdgeHTML) 開発者ツール  

[!INCLUDE [new-devtools-version-note](includes/new-devtools-version-note.md)]  

Microsoft Edge (EdgeHTML) 開発者ツールは、[TypeScript][TypeScriptIndex] で構築され、[オープン ソース][GithubMicrosoftChakracore] を利用し、最新のフロントエンド ワークフロー用に最適化されており、Microsoft Store で [スタンドアロンの Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview] として利用できるようになりました。  

最新機能の詳細については、「[Windows 10 の最新の更新プログラム (EdgeHTML 18) の開発者ツール][DevtoolsGuideEdgehtmlWhatsnew]」を確認してください。  

## コア ツール  

:::image type="complex" source="./devtools-guide/media/devtools.png" alt-text="Microsoft Edge (EdgeHTML) DevTools":::
  Microsoft Edge (EdgeHTML) 開発者ツール
:::image-end:::

<!--![Microsoft Edge \(EdgeHTML\) DevTools][ImageDevtoolsEdgehtml]  -->  

Microsoft Edge (EdgeHTML) 開発者ツールは次のとおりです:  

*   HTML と CSS の編集、アクセシビリティ プロパティの検査、イベント リスナーの表示、DOM ミューテーション ブレークポイントの設定を行うための [要素][DevtoolsGuideEdgehtmlElements] パネル  
*   ログ メッセージの表示とフィルター処理、JavaScript オブジェクトと DOM ノードの検査、選択したウィンドウまたはフレームのコンテキストでの JavaScript の実行のための [コンソール][DevtoolsGuideEdgehtmlConsole]  
*   コードのステップ スルー、ウォッチとブレークポイントの設定、コードのライブ編集、Web ストレージと Cookie キャッシュの検査のための [デバッガー][DevtoolsGuideEdgehtmlDebugger]  
*   ネットワークおよびブラウザ キャッシュからの要求と応答を監視および検査するための [ネットワーク][DevtoolsGuideEdgehtmlNetwork] パネル  
*   サイトに必要な時間とシステム リソースをプロファイルする [パフォーマンス][DevtoolsGuideEdgehtmlPerformance] パネル  
*   メモリ リソースの使用状況を測定し、コード ランタイムのさまざまな状態でヒープ スナップショットを比較するための [メモリ][DevtoolsGuideEdgehtmlMemory] パネル  
*   Web ストレージ、IndexedDB、Cookie、キャッシュ データを検査および管理するための [ストレージ][DevtoolsGuideEdgehtmlStorage] パネル  
*   サービス ワーカーを管理およびデバッグするための [サービス ワーカー][DevtoolsGuideEdgehtmlServiceworkers] パネル  
*   さまざまなブラウザー プロファイル、画面解像度、GPS 位置座標を使用してサイトをテストするための [エミュレーション][DevtoolsGuideEdgehtmlEmulation] パネル  

[フィードバックと機能のリクエスト](#getting-in-touch-with-the-microsoft-edge-devtools-team) を送信してください!  

> [!ヒント]
> [ブラウザーを使用せずに Microsoft Edge (EdgeHTML) でテストします][BrowserstackEdgehtml]。  
> Microsoft Edge チームは [BrowserStack][BrowserstackEdgehtml] と提携して、Microsoft Edge (EdgeHTML) で無料のライブおよび自動テストを提供しました。  

## Microsoft Store アプリ  

**Microsoft Edge (EdgeHTML) 開発者ツール** は、ブラウザー内 (`F12`) のツール エクスペリエンスに加えて、[Microsoft Store からスタンドアロンの Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview] として [利用できるようになりました][DevtoolsGuideEdgehtmlWhatsnew]。ストア バージョンには、開いているローカル ページ ターゲットとリモート ページ ターゲットに接続するための **チューザー** パネルと、開発者ツール インスタンスを簡単に切り替えるためのタブ付きレイアウトが付属しています。  

### ローカル デバッグ  

ページをローカルでデバッグするには、Microsoft Edge 開発者ツール アプリを起動するだけです。チューザーの **ローカル** パネルには、開いている Edge ブラウザー タブ、実行中の [PWA][PwasEdgehtmlIndex] (`WWAHost.exe` プロセス)、[WebView][HostingWebview] コントロールなど、アクティブな EdgeHTML コンテンツ プロセスがすべて表示されます。目的のターゲットを選択して、開発者ツールの新しいタブ インスタンスを開きます。  

:::image type="complex" source="./devtools-guide/media/chooser_local.png" alt-text="DevTools app Local panel":::
  開発者ツール アプリ ローカル パネル
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### リモート デバッグ  

Microsoft Edge 開発者ツール アプリは、新しくリリースされた [開発者ツール プロトコル][DevtoolsProtocolEdgehtmlIndex] を介してリモート マシン上のページをデバッグするための基本的なサポートを導入します。最新のリリースでは、[デバッガー][DevtoolsGuideEdgehtmlDebugger]、[要素][DevtoolsGuideEdgehtmlElements] (読み取り専用操作)、[コンソール][DevtoolsGuideEdgehtmlConsole] パネルのコア機能へのリモート アクセスが提供されます。リモート デバッグは、デスクトップ ホストを実行している Microsoft Edge (EdgeHTML) に限定されており、他の EdgeHTML ホストと Windows 10 デバイスのサポートは将来のリリースで予定されています。  

開始するには、[開発者ツール プロトコル][DevtoolsProtocolEdgehtmlIndex] ドキュメントの [*Microsoft Edge 開発者ツール*][DevtoolsProtocolEdgehtmlClientsEdgePreview] セクションを確認してください。  

:::image type="complex" source="./devtools-guide/media/chooser_remote.png" alt-text="DevTools app Remote panel":::
  開発者ツール アプリ リモート パネル
:::image-end:::

<!--![DevTools app Remote panel][ImageDevtoolsGuideEdgehtmlRemote]  -->  

## 一般的なショートカット  

> [!重要]
> すべてのショートカットは、最新バージョンの Windows で検証されています。  
> ショートカットを使用できない場合は、Windows のコピーを更新してください。  

これらのショートカットはメインの開発者ツール ウィンドウを制御し、すべてのツールで機能します。  

| アクション | ショートカット |  
|:--- |:--- |  
| 開発者ツールの表示/非表示を切り替える (最後に表示されたパネルに表示されます) | `F12`、`Ctrl`+`Shift`+`I` |  
| ドッキングを切り替える (Undock/Bottom/Right) | `Ctrl`+`Shift`+`D` |  
| ファイルを開く | `Ctrl`+`P`、`Ctrl`+`O` |  
| デバッガーで編集不可の HTML ソース コードを表示する | `Ctrl`+`U` |  
| その他のツールの下部にあるコンソールの表示/非表示を切り替える | `Ctrl`+`` ` `` |  
| 要素に切り替える (DOM Explorer) | `Ctrl`+`1` |  
| コンソールに切り替える | `Ctrl`+`2` |  
| デバッガーに切り替える | `Ctrl`+`3` |  
| ネットワークに切り替える | `Ctrl`+`4` |  
| パフォーマンスに切り替える | `Ctrl`+`5` |  
| メモリに切り替える | `Ctrl`+`6` |  
| エミュレーションに切り替える | `Ctrl`+`7` |  
| ヘルプ ドキュメント | `F1` |  
| 次のツール | `Ctrl`+`F6` |  
| 前のツール | `Ctrl`+`Shift`+`F6` |  
| 前のツール (履歴から) | `Ctrl`+`Shift`+`[` |  
| 次のツール (履歴から) | `Ctrl`+`Shift`+`]` |  
| 次のサブフレーム | `F6` |  
| 前のサブフレーム | `Shift`+`F6` |  
| 検索ボックスの次の一致 | `F3` |  
| 検索ボックスの前の一致 | `Shift`+`F3` |  
| 検索ボックスで検索 | `Ctrl`+`F` |  
| フォーカスをコンソールの一番下に移動する | `Alt`+`Shift`+`I` |  
| 開発者ツールをコンソールに起動する | `Ctrl`+`Shift`+`J` |  
| ページを更新する | `Ctrl`+`Shift`+`F5`、`Ctrl`+`R` |  

> [!注]
> デバッグ中にブレークポイントで一時停止した場合、**[ページの更新]** アクションは最初にランタイムを再開します。  

## Microsoft Edge 開発者ツール チームと連絡を取る  

Microsoft Edge (EdgeHTML) 開発者ツールの改善に役立つフィードバックを送信してください!ツール (`F12`) を開き、[[フィードバックを送信]](#microsoft-edge-edgehtml-developer-tools) ボタンを選択するだけです。  

[Windows Insider][WindowsInsiderProgram] になって、[開発者ツールに搭載される最新機能][DevtoolsGuideEdgehtmlWhatsnew] をプレビューします。Windows フィードバック Hub アプリを使用して、Windows の一般的な提案や問題を投稿、賛成、追跡し、サポートを受けます。  

<!-- image links  -->  

<!--[ImageDevtoolsEdgehtml]: /microsoft-edge/devtools-guide/media/devtools.png "Microsoft Edge (EdgeHTML) DevTools"  -->  
<!--[ImageDevtoolsGuideEdgehtmlChooselocal]: /microsoft-edge/devtools-guide/media/chooser_local.png "DevTools app Local panel"  -->  
<!--[ImageDevtoolsGuideEdgehtmlRemote]: /microsoft-edge/devtools-guide/media/chooser_remote.png "DevTools app Remote panel"  -->  

<!-- links  -->  

[DevtoolsGuideEdgehtmlConsole]: /microsoft-edge/devtools-guide/console "コンソール"  
[DevtoolsGuideEdgehtmlDebugger]: /microsoft-edge/devtools-guide/debugger "デバッガー"  
[DevtoolsGuideEdgehtmlElements]: /microsoft-edge/devtools-guide/elements "要素"  
[DevtoolsGuideEdgehtmlEmulation]: /microsoft-edge/devtools-guide/emulation "エミュレーション"  
[DevtoolsGuideEdgehtmlMemory]: /microsoft-edge/devtools-guide/memory "メモリ"  
[DevtoolsGuideEdgehtmlNetwork]: /microsoft-edge/devtools-guide/network "ネットワーク"  
[DevtoolsGuideEdgehtmlPerformance]: /microsoft-edge/devtools-guide/performance "パフォーマンス"  
[DevtoolsGuideEdgehtmlServiceworkers]: /microsoft-edge/devtools-guide/service-workers "サービス ワーカー"  
[DevtoolsGuideEdgehtmlStorage]: /microsoft-edge/devtools-guide/storage "ストレージ"  
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新の Windows 10 更新プログラムの開発者ツール (EdgeHTML 18)"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge (EdgeHTML) 開発者ツール プロトコル"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge 開発者ツール プレビュー - 開発者ツール プロトコル クライアント"  
[HostingWebview]: /microsoft-edge/hosting/webview "Windows 10 アプリの WebView (EdgeHTML)"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows のプログレッシブ Web アプリ (EdgeHTML)"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge 開発者ツール プレビュー"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows Insider Program"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "無料の Microsoft Edge ブラウザー テスト | BrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore | GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
