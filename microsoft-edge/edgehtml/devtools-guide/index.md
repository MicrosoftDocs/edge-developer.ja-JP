---
description: Microsoft Edge (EdgeHTML) 開発者ツールを理解する
title: Microsoft Edge (EdgeHTML) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 89fdbcdf10d10c57836067ca7d02afa3fd48cbc9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234585"
---
# Microsoft Edge (EdgeHTML) 開発者ツール  

[!INCLUDE [new-devtools-version-note](../includes/new-devtools-version-note.md)]  

Microsoft Edge \ (EdgeHTML \) DevTools は、[TypeScript][|::ref1::|Index] で構築され、[オープン ソース][GithubMicrosoftChakracore] で動作し、最新のフロントエンド ワークフローを対象として最適化された [スタンドアロン Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview] として Microsoft Store で利用できます。  

最新の機能の詳細については、「[Windows 10 の最新の更新プログラムの DevTools (EdgeHTML 18)][DevtoolsGuideEdgehtmlWhatsnew]」 を参照してください。  

## コア ツール  

:::image type="complex" source="./media/devtools.png" alt-text="Microsoft Edge (EdgeHTML) DevTools":::
   Microsoft Edge (EdgeHTML) DevTools
:::image-end:::

<!--![Microsoft Edge \(EdgeHTML\) DevTools][ImageDevtoolsEdgehtml]  -->  

Microsoft Edge \ (EdgeHTML \) DevTools には、以下のものがあります。  

*   [要素][DevtoolsGuideEdgehtml|::ref2::|] は、パネルHTML および CSS の編集、アクセシビリティのプロパティの検査、イベント リスナーの表示、DOM 変異のブレークポイントの設定を行います。  
*   [コンソール][DevtoolsGuideEdgehtml|::ref3::|] は、ログ メッセージを表示およびフィルタリングし、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウやフレームのコンテキストでの JavaScript を実行します。  
*   [デバッガー][DevtoolsGuideEdgehtml|::ref4::|] は、コードのステップ実行、ウォッチポイントとブレークポイントの設定、コードのライブ編集、Web ストレージおよび cookie キャッシュの検査を行います。  
*   [ネットワーク][DevtoolsGuideEdgehtml|::ref5::|] パネルは、ネットワークとブラウザーのキャッシュからの要求や応答を監視および検査します。  
*   [パフォーマンス][DevtoolsGuideEdgehtml|::ref6::|] パネルは、サイトに必要な時間とシステム リソースをプロファイルします。  
*   [メモリ][DevtoolsGuideEdgehtml|::ref7::|] パネルは、メモリ リソースの使用状況を測定し、コード ランタイムの異なる状態でヒープ スナップショットを比較します。  
*   [ストレージ][DevtoolsGuideEdgehtml|::ref8::|] パネルは、Web ストレージ、IndexedDB、cookie、および キャッシュ データを検査および管理します。  
*   [サービス ワーカー][DevtoolsGuideEdgehtmlServiceworkers] パネルは、サービス ワーカーを管理およびデバッグします。  
*   [エミュレーション][DevtoolsGuideEdgehtml|::ref9::|] パネルは、異なるブラウザー プロファイル、画面解像度、GPS の位置座標でサイトをテストします。  

[フィードバックと機能のリクエスト](#getting-in-touch-with-the-microsoft-edge-devtools-team) をどんどん送ってください!  

> [!TIP]
> [Microsoft Edge \(EdgeHTML\) は、どのブラウザーからでも無料でお試しいただけます][BrowserstackEdgehtml]。  
> Microsoft Edge は [BrowserStack][BrowserstackEdgehtml] と提携して、Microsoft Edge \ (EdgeHTML) のライブ テストおよび自動テストを無料で提供しています。  

## Microsoft ストア アプリ  

**Microsoft Edge \ (EdgeHTML \) DevTools** は、ブラウザー内での \(`F12`\) のツール環境に加えて、[Microsoft Store から Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview] スタンドアロン版として [現在使用可能][DevtoolsGuideEdgehtmlWhatsnew] です。  ストア バージョンでは、ローカルとリモートのページ　ターゲットを開くために [**セレクター**] パネルが表示されます。これには、DevTools インスタンス間で簡単に切り替えられるようにタブ レイアウトが用意されています。  

### ローカル デバッグ  

ページをローカルでデバッグするのは、Microsoft Edge DevTools アプリを起動するだけでできます。  セレクターの [**ローカル**] パネルには、[Edge ブラウザーを開く] タブを含むすべてのアクティブな EdgeHTML コンテンツのプロセスが表示されます。これには、[PWA][PwasEdgehtmlIndex] \ (`WWAHost.exe`プロセス \)、および [webview][HostingWebview] コントロールなどが含まれます。  目的のターゲットを選択して、DevTools の新しいタブ インスタンスをアタッチして開きます。  

:::image type="complex" source=".//media/chooser_local.png" alt-text="DevTools アプリ ローカル パネル":::
   DevTools アプリ ローカル パネル
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### リモート デバッグ  

Microsoft Edge DevTools アプリは、新しくリリースされた [DevTools プロトコル][DevtoolsProtocolEdgehtmlIndex] を介して、リモート コンピューター上のページをデバッグするための基本的なサポートを導入しています。  最新のリリースでは、[デバッガー][DevtoolsGuideEdgehtml|::ref10::|]、[要素][DevtoolsGuideEdgehtml|::ref11::|] (読み取り専用操作の場合)、および [コンソール][DevtoolsGuideEdgehtml|::ref12::|] パネルの主な機能にリモート アクセスできます。  リモート デバッグは、Microsoft Edge \ (EdgeHTML \) が動作しているデスクトップ ホストに限定されており、他の EdgeHTML ホストと Windows 10デバイスについては、将来のリリースでサポートされる予定です。  

始めるには、[*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview] の [DevTools プロトコル][DevtoolsProtocolEdgehtmlIndex] ドキュメントにあるセクションを確認してください。  

:::image type="complex" source="./media/chooser_remote.png" alt-text="DevTools アプリのリモート パネル":::
   DevTools アプリのリモート パネル
:::image-end:::

<!--![DevTools app Remote panel][ImageDevtoolsGuideEdgehtmlRemote]  -->  

## 一般的なショートカット  

> [!IMPORTANT]
> すべてのショートカットは、最新バージョンの Windows で確認されています。  
> ショートカットを使用できない場合は、Windows のコピーを更新してください。  

これらのショートカットは、DevTools のメイン ウィンドウを制御し、すべてのツールで動作します。  

| 操作 | ショートカット |  
|:--- |:--- |  
| DevTools の表示/非表示 \ (最後に表示されたパネルに表示される \) | `F12`, `Ctrl`+`Shift`+`I` |  
| ドッキングの切り替え \ （ドッキングなし / 一番下/右 \） | `Ctrl`+`Shift`+`D` |  
| ファイルを開く | `Ctrl`+`P`, `Ctrl`+`O` |  
| デバッガーで編集不可の HTML ソース コードを表示する | `Ctrl`+`U` |  
| 他のツールの下部にあるコンソールの表示/非表示  | `Ctrl`+`` ` `` |  
| 要素に切り替える \ (DOM Explorer \) | `Ctrl`+`1` |  
| コンソールに切り替える |  `Ctrl`+`2` |  
| デバッガーに切り替える | `Ctrl`+`3` |  
| ネットワークに切り替える | `Ctrl`+`4` |  
| パフォーマンスに切り替える | `Ctrl`+`5` |  
| メモリに切り替える | `Ctrl`+`6` |  
| エミュレーションに切り替える | `Ctrl`+`7` |  
| ヘルプ ドキュメント | `F1` |  
| 次のツール | `Ctrl`+`F6` |  
| 前のツール | `Ctrl`+`Shift`+`F6` |  
| 前のツール \ (履歴から \) | `Ctrl`+`Shift`+`[` |  
| 次のツール \ (履歴から \) | `Ctrl`+`Shift`+`]` |  
| 次のサブフレーム | `F6` |  
| 前のサブフレーム | `Shift`+`F6` |  
| [検索] ボックス内の次の一致 | `F3` |  
| [検索] ボックス内の前の一致 | `Shift`+`F3` |  
| [検索] ボックス内の検索 | `Ctrl`+`F` |  
| 一番下にある [コンソール] にフォーカスを移動する | `Alt`+`Shift`+`I` |  
| コンソールに DevTools を起動する | `Ctrl`+`Shift`+`J` |  
| ページを更新する | `Ctrl`+`Shift`+`F5`, `Ctrl`+`R` |  

> [!NOTE]
> デバッグ中にブレークポイントで一時停止している場合、**ページを更新** アクションが最初にランタイムを再開します。  

## Microsoft Edge DevTools チームと連絡を取る  

フィードバックをお送りください。 Microsoft Edge \ (EdgeHTML \) DevTools の改善にご協力ください。  ツール \ (`F12` \) を開き、[[フィードバック の送信](#microsoft-edge-edgehtml-developer-tools)] ボタンを選択します。  

[Windows Insider][WindowsInsiderProgram] に加入して、[DevTools に搭載される最新機能][DevtoolsGuideEdgehtmlWhatsnew] をプレビューしてください。  Windows フィードバック Hub アプリを使用して、一般的な Windows の提案や問題に関する情報を投稿、記録、追跡して、サポートを受けることができます。  

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
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新の Windows 10 更新プログラムの DevTools (EdgeHTML 18)"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge (EdgeHTML) DevTools プロトコル"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge の DevTools プレビュー - DevTools プロトコル クライアント"  
[HostingWebview]: /microsoft-edge/hosting/webview "Windows 10 アプリの WebView (EdgeHTML)"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows でのプログレッシブ Web アプリ (EdgeHTML)"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools プレビュー"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows Insider Program"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "無料の Microsoft Edge ブラウザー テスト | BrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore | GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
