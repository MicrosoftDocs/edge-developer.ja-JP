---
description: Microsoft Edge (EdgeHTML) 開発者ツールについて理解する
title: Microsoft Edge (EdgeHTML) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/05/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
experimental: true
experiment_id: 51fe4b97-3e55-41
localization_priority: Priority
ms.openlocfilehash: 56edfa3aa39fc20d37d95fb8fde029a702732336
ms.sourcegitcommit: 985cfb79a64951afd5beb7981b26afbed30a8972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "10629505"
---
# Microsoft Edge (EdgeHTML) 開発者ツール  

[!INCLUDE [new-devtools-version-note](includes/new-devtools-version-note.md)]  

Microsoft Edge \ (EdgeHTML \) DevTools は、新しいフロントエンドワークフローに最適化された、[オープンソース][GithubMicrosoftChakracore]を使った[TypeScript][|::ref1::|Index]を使用して構築され、microsoft Store で[スタンドアロン Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview]として利用できるようになりました。  

最新機能の詳細については、「 [Windows 10 の最新の更新プログラム (EdgeHTML 18) での Devtools」][DevtoolsGuideEdgehtmlWhatsnew]を参照してください。  

## コアツール  

:::image type="complex" source="./devtools-guide/media/devtools.png" alt-text="Microsoft Edge (EdgeHTML) DevTools":::
   Microsoft Edge (EdgeHTML) DevTools
:::image-end:::

<!--![Microsoft Edge \(EdgeHTML\) DevTools][ImageDevtoolsEdgehtml]  -->  

Microsoft Edge \ (EdgeHTML \) DevTools には以下のものがあります。  

*   HTML と CSS の編集、アクセシビリティプロパティの検査、イベントリスナーの表示、DOM 変異のブレークポイントの設定を行うための[要素][DevtoolsGuideEdgehtml|::ref2::|]パネル  
*   ログメッセージを表示してフィルター処理し、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウまたはフレームのコンテキストで JavaScript を実行する[本体][DevtoolsGuideEdgehtml|::ref3::|]  
*   コードをステップ実行して、ウォッチとブレークポイントを設定し、コードをリアルタイムで編集し、web ストレージと cookie キャッシュを検査する[デバッガー][DevtoolsGuideEdgehtml|::ref4::|]  
*   ネットワークとブラウザーのキャッシュから要求と応答を監視および検査するための[ネットワーク][DevtoolsGuideEdgehtml|::ref5::|]パネル  
*   サイトで必要な時間とシステムリソースをプロファイルするための[パフォーマンス][DevtoolsGuideEdgehtml|::ref6::|]パネル  
*   メモリリソースの使用を測定し、コードランタイムのさまざまな状態でヒープスナップショットを比較するための[メモリ][DevtoolsGuideEdgehtml|::ref7::|]パネル  
*   Web ストレージ、IndexedDB、cookies、キャッシュデータを検査および管理するための[ストレージ][DevtoolsGuideEdgehtml|::ref8::|]パネル  
*   サービスワーカーを管理およびデバッグするための[サービスワーカー][DevtoolsGuideEdgehtmlServiceworkers]パネル  
*   さまざまなブラウザープロファイル、画面解像度、GPS 位置座標を使ってサイトをテストする[エミュレーション][DevtoolsGuideEdgehtml|::ref9::|]パネル  

[フィードバックと機能のリクエストを](#feedback)送信してください。  

> [!TIP]
> [Microsoft Edge \ (EdgeHTML \) で任意のブラウザーから無料でテスト][BrowserstackEdgehtml]します。  
> Microsoft Edge チームは、 [Browserstack][BrowserstackEdgehtml]と提携して、microsoft edge \ (EdgeHTML \) での無料のライブテストと自動テストを提供します。  

## Microsoft ストア アプリ  

**Microsoft Edge \ (EdgeHTML \) DevTools**は、ブラウザー内 \`F12`(\) のツールエクスペリエンスに加えて、 [microsoft ストアからスタンドアロンの Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview]として[利用できるようになりました][DevtoolsGuideEdgehtmlWhatsnew]。  ストアバージョンでは、ローカルとリモートのページターゲットを開くための**セレクター**パネルが用意されています。これには、devtools インスタンス間で簡単に切り替えるためのタブ付きレイアウトが用意されています。  

### ローカルデバッグ  

ページをローカルでデバッグするには、Microsoft Edge DevTools アプリを起動するだけです。  セレクターの**ローカル**パネルには、開いている [Edge browser] タブ、 [pwas][PwasEdgehtmlIndex] \ (`WWAHost.exe`プロセス \)、 [webview][HostingWebview]コントロールなど、すべてのアクティブな EdgeHTML コンテンツプロセスが表示されます。  目的のターゲットを選択して、DevTools の新しいタブインスタンスを添付して開きます。  

:::image type="complex" source="./devtools-guide/media/chooser_local.png" alt-text="DevTools アプリのローカルパネル":::
   DevTools アプリのローカルパネル
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### リモートデバッグ  

Microsoft Edge DevTools アプリは、新しくリリースされた[Devtools プロトコル][DevtoolsProtocolEdgehtmlIndex]を使ってリモートコンピューター上のページをデバッグするための基本的なサポートを提供します。  最新のリリースでは、[デバッガー][DevtoolsGuideEdgehtml|::ref10::|]のコア機能へのリモートアクセス、[要素][DevtoolsGuideEdgehtml|::ref11::|]\ (読み取り専用操作の場合)、[コンソール][DevtoolsGuideEdgehtml|::ref12::|]パネルが使用されています。  リモートデバッグは、デスクトップホストを実行している Microsoft Edge \ (EdgeHTML \) に限定され、将来のリリースで使用される他の EdgeHTML ホストと Windows 10 デバイスをサポートします。  

はじめに、 [Devtools プロトコル][DevtoolsProtocolEdgehtmlIndex]ドキュメントの[*Microsoft Edge devtools*][DevtoolsProtocolEdgehtmlClientsEdgePreview]セクションを確認してください。  

:::image type="complex" source="./devtools-guide/media/chooser_remote.png" alt-text="DevTools アプリのリモートパネル":::
   DevTools アプリのリモートパネル
:::image-end:::

<!--![DevTools app Remote panel][ImageDevtoolsGuideEdgehtmlRemote]  -->  

## 一般的なショートカットキー  

> [!IMPORTANT]
> 最新バージョンの Windows では、すべてのショートカットが確認されています。  
> ショートカットを使用できない場合は、Windows のコピーを更新してください。  

これらのショートカットは、主要な DevTools ウィンドウを制御し、すべてのツールで動作する必要があります。  

| 操作 | キー |  
|:--- |:--- |  
| DevTools の表示/非表示を切り替える \ (最後に表示したパネルに表示されます) | `F12`, `Ctrl`+`Shift`+`I` |  
| ドッキングの切り替え \ (アンドック/ボトム/右) | `Ctrl`+`Shift`+`D` |  
| ファイルを開く | `Ctrl`+`P`, `Ctrl`+`O` |  
| デバッガーで編集不可の HTML ソースコードを表示する | `Ctrl`+`U` |  
| 他のツールの下部に本体の表示/非表示を切り替える  | `Ctrl`+`` ` `` |  
| 要素に切り替える \ (DOM Explorer \) | `Ctrl`+`1` |  
| コンソールに切り替える |  `Ctrl`+`2` |  
| デバッガーに切り替える | `Ctrl`+`3` |  
| ネットワークに切り替える | `Ctrl`+`4` |  
| パフォーマンスに切り替える | `Ctrl`+`5` |  
| メモリに切り替える | `Ctrl`+`6` |  
| エミュレーションに切り替える | `Ctrl`+`7` |  
| ヘルプドキュメント | `F1` |  
| 次のツール | `Ctrl`+`F6` |  
| 前のツール | `Ctrl`+`Shift`+`F6` |  
| 前のツール \ (履歴から) | `Ctrl`+`Shift`+`[` |  
| 次のツール \ (履歴から) | `Ctrl`+`Shift`+`]` |  
| 次のサブフレーム | `F6` |  
| 前のサブフレーム | `Shift`+`F6` |  
| 検索ボックス内の次の検索結果 | `F3` |  
| 検索ボックス内の前の一致 | `Shift`+`F3` |  
| [検索] ボックスで検索 | `Ctrl`+`F` |  
| フォーカスをコンソールの下部に移動する | `Alt`+`Shift`+`I` |  
| コンソールで DevTools を起動する | `Ctrl`+`Shift`+`J` |  
| ページを最新の情報に更新する | `Ctrl`+`Shift`+`F5`, `Ctrl`+`R` |  

> [!NOTE]
> デバッグしてブレークポイントで一時停止している場合、"**ページを更新**する" アクションでは最初にランタイムが再開されます。  

## フィードバック  

Microsoft Edge \ (EdgeHTML \) DevTools の向上に役立てるため、フィードバックを送信してください。  ツール \ (`F12`\) を開いて、[[フィードバックの送信](#microsoft-edge-edgehtml-developer-tools)] ボタンを選択します。  

[Windows Insider][WindowsInsiderProgram]になると、 [devtools の最新機能][DevtoolsGuideEdgehtmlWhatsnew]をプレビューできます。  Windows フィードバック Hub アプリを使用して、Windows の一般的な提案と問題の投稿、事後投票、追跡、サポートを行います。  

<!-- image links  -->  

<!--[ImageDevtoolsEdgehtml]: /microsoft-edge/devtools-guide/media/devtools.png "Microsoft Edge (EdgeHTML) DevTools"  -->  
<!--[ImageDevtoolsGuideEdgehtmlChooselocal]: /microsoft-edge/devtools-guide/media/chooser_local.png "DevTools app Local panel"  -->  
<!--[ImageDevtoolsGuideEdgehtmlRemote]: /microsoft-edge/devtools-guide/media/chooser_remote.png "DevTools app Remote panel"  -->  

<!-- links  -->  

[DevtoolsGuideEdgehtmlConsole]: /microsoft-edge/devtools-guide/console "コンソ"  
[DevtoolsGuideEdgehtmlDebugger]: /microsoft-edge/devtools-guide/debugger "ブレーク"  
[DevtoolsGuideEdgehtmlElements]: /microsoft-edge/devtools-guide/elements "エレメント"  
[DevtoolsGuideEdgehtmlEmulation]: /microsoft-edge/devtools-guide/emulation "エミュレーション"  
[DevtoolsGuideEdgehtmlMemory]: /microsoft-edge/devtools-guide/memory "メモリライザーカード"  
[DevtoolsGuideEdgehtmlNetwork]: /microsoft-edge/devtools-guide/network "ネットワーク"  
[DevtoolsGuideEdgehtmlPerformance]: /microsoft-edge/devtools-guide/performance "処理"  
[DevtoolsGuideEdgehtmlServiceworkers]: /microsoft-edge/devtools-guide/service-workers "サービス員"  
[DevtoolsGuideEdgehtmlStorage]: /microsoft-edge/devtools-guide/storage "容量"  
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新の Windows 10 更新プログラム (EdgeHTML 18) の DevTools"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge (EdgeHTML) DevTools プロトコル"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools のプレビュー-DevTools プロトコルクライアント"  
[HostingWebview]: /microsoft-edge/hosting/webview "Windows 10 アプリ用 WebView (EdgeHTML)"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows のプログレッシブ Web アプリ (EdgeHTML)"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools プレビュー"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows Insider プログラム"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "Microsoft Edge ブラウザーの無料テストBrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore |GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
