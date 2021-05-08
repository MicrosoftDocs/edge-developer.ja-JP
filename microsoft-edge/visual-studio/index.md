---
description: Microsoft Edge (クロム) と Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/18/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, vs, visual studio, デバッガー
ms.openlocfilehash: 562952ef238c05922e468501706ab75e1976273d
ms.sourcegitcommit: 661e8def3f27cea381c59ac38954789e736c18f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387272"
---
# <a name="visual-studio"></a>Visual Studio  

Microsoft [Visual Studio][MicrosoftVisualstudioVs] は、統合された開発環境 \(IDE\) です。   Web アプリの編集、デバッグ、ビルド、発行に使用します。  これは、Web 開発の多くの側面で使用できる機能豊富なプログラムです。  ほとんどの ID が提供する標準エディターとデバッガーの上に、Visual Studio機能が含まれています。  

*   コンパイラ  
*   コード補完ツール  
*   グラフィカル デザイナー  
*   より多くの  
    
ファイルをまだ使用していない場合はVisual Studioに移動 [し][MicrosoftVisualstudioDownloads] 、Visual Studioダウンロードします。  

現在、Visual Studio 2019 では、Microsoft Edge での JavaScript のデバッグがサポートされ、ASP.NET Core アプリ ASP.NET サポートされています。  Microsoft Edge のデバッグに使用するVisual Studio手順を実行します。  

## <a name="launch-microsoft-edge"></a>Microsoft Edge の起動  

Visual Studioボタンを使用して次のワークフローを完了します。  

1.  コア アプリ ASP.NET と ASP.NET 作成します。  
1.  Web サーバーを起動します。  
1.  Microsoft Edge を起動します。  
1.  デバッガーをVisual Studioします。  
    
簡略化されたワークフローを使用すると、MICROSOFT Edge で実行される JavaScript を IDE から直接デバッグできます。  

### <a name="create-a-new-aspnet-core-web-app"></a>コア Web アプリ ASP.NET 作成する  

2019 Visual Studio開き、[新しいプロジェクトの作成 **] を選択します**。  次の画面で、[コア Web アプリ**ASP.NET] を**  >  **選択します**。  

:::image type="complex" source="./media/create-new-project.png" alt-text="コア Web アプリ ASP.NET 作成する" lightbox="./media/create-new-project.png":::
   コア Web アプリ ASP.NET 作成する  
:::image-end:::  

新しいプロジェクト **のプロジェクト名を** 指定し、[作成] を **選択します**。  この例では、テンプレートとして ** [React.js] ** を選択し、[作成] を **選択します**。  この **React.js** テンプレートは、コア アプリにReact.jsを ASP.NET します。  

### <a name="launch-microsoft-edge-from-visual-studio"></a>Microsoft Edge をアプリから起動Visual Studio  

プロジェクトを作成した後、開きます `ClientApp/src/components/Counter.js` 。  ここで、JavaScript をデバッグVisual Studioするには、緑色の [再生] ボタンと******[IIS Express]** の横にあるドロップダウンを選択します。  

:::image type="complex" source="./media/vs-dropdown.png" alt-text="緑の [再生] ボタンと IIS Express の横にあるドロップダウン" lightbox="./media/vs-dropdown.png":::
   緑の [再生] ボタンと **IIS** Express の横 **にあるドロップダウン**  
:::image-end:::  

[スクリプト**のデバッグが有効]**  >  **を選択します**。  

:::image type="complex" source="./media/enable-script-debugging.png" alt-text="スクリプトのデバッグを有効にする方法をVisual Studio" lightbox="./media/enable-script-debugging.png":::
   スクリプトのデバッグを有効にする方法をVisual Studio  
:::image-end:::  

同じドロップダウンで **、[Web ブラウザー** ] > Microsoft Edge のプレビュー チャネル (Microsoft Edge Canary、Dev、Beta など) を起動する Visual Studio を選択します。  Microsoft Edge プレビュー チャネルをまだ使用していない場合は [、[Microsoft Edge Insider][MicrosoftedgeinsiderDownload] チャネルのダウンロード] に移動してダウンロードします。  

:::image type="complex" source="./media/set-web-browser.png" alt-text="起動する Microsoft Edge のプレビュー チャネルVisual Studio選択する" lightbox="./media/set-web-browser.png":::
   起動する Microsoft Edge のプレビュー チャネルVisual Studio選択する  
:::image-end:::  

> [!NOTE]
> [Microsoft Edge\(EdgeHTML\] ) を選択した場合、Visual Studio代わりに Microsoft Edge \(Chromium\) を起動します。  [Microsoft Edge のプレビュー][MicrosoftedgeinsiderDownload] チャネルの 1 つをインストールするか、コンピューターにインストールされている Microsoft Edge のバージョンが Microsoft Edge \(Chromium\) であり、Microsoft Edge \(EdgeHTML\) ではインストールされていないことを確認します。  

これで、Visual Studioが正しく構成されたので、緑色の [再生] ボタン **を選択** します。  Visual Studioをビルドし、Web サーバーを起動し、Microsoft Edge を起動し、に指定されているポートに移動します `https://localhost:44362/` `launchSettings.json` 。  

:::image type="complex" source="./media/edge-launch.png" alt-text="Microsoft Edge がアプリから起動Visual Studio" lightbox="./media/edge-launch.png":::
   Microsoft Edge がアプリから起動Visual Studio  
:::image-end:::  

### <a name="debug-javascript-running-in-microsoft-edge"></a>Microsoft Edge で実行されている JavaScript のデバッグ  

再び Visual Studio に切り替えます。  で `Counter.js` 、13 行目にブレークポイントを設定するには、行の横にあるガターを選択します。  

:::image type="complex" source="./media/set-breakpoint.png" alt-text="[13 行目] の横にあるCounter.jsを選択して、ブレークポイントを設定Visual Studio" lightbox="./media/set-breakpoint.png":::
   [13 行目] の横にあるガターを選択して、ブレークポイントを設定 `Counter.js` Visual Studio  
:::image-end:::  

次に、起動した Microsoft Edge のインスタンスVisual Studioします。  Web ページ **の左側** にある NavMenu の [カウンター] を選択します。  次に、[増分] **を選択します**。  

:::image type="complex" source="./media/edge-counter.png" alt-text="コア Web アプリの [ASP.NET] ページ" lightbox="./media/edge-counter.png":::
   コア Web アプリの [ASP.NET] ページ  
:::image-end:::  

このページの JavaScript デバッガー Visual Studioで設定したブレークポイントにヒットします `Counter.js` 。  Visual Studio、Microsoft Edge で実行されている JavaScript のランタイムを一時停止し、スクリプトを 1 行に 1 行で実行できます。  

:::image type="complex" source="./media/hit-breakpoint.png" alt-text="Visual Studioが Microsoft Edge で実行されている JavaScript を一時停止する" lightbox="./media/hit-breakpoint.png":::
   Visual Studioが Microsoft Edge で実行されている JavaScript を一時停止する  
:::image-end:::  

この例は、ユーザーが使用できる機能の小さなデモンストレーションVisual Studio。  2019 の機能の詳細については、Visual Studioドキュメントに [Visual Studioしてください][VisualStudioWindowsIndex]。  

## <a name="attach-to-microsoft-edge"></a>Microsoft Edge に接続する  

以前は、Microsoft Edge をアプリから起動する必要Visual Studio。  これで、実行中の Microsoft Edge Visual Studioデバッガーを接続できます。  

最初に、Microsoft Edge の実行中のインスタンスが含めずに確認します。  次に、コマンド ラインから次のコマンドを実行します。  

```console
start msedge –remote-debugging-port=9222
```  

[Visual Studio] メニューを**開**き、[プロセスに添付]**を選択**するか、 を選択します `Ctrl` + `Alt` + `P` 。  

:::image type="complex" source="./media/attach-to-process.png" alt-text="[プロセスに添付] を選択Visual Studio" lightbox="./media/attach-to-process.png":::
   [ **プロセスに添付]** を選択Visual Studio  
:::image-end:::  

[プロセス**に接続] ダイアログで****、[接続の**種類] を **[Chrome devtools プロトコル websocket] (認証なし) に設定します**。  [接続先 **] テキスト ボックス** で、と入力して `http://localhost:9222/` 選択します `Enter` 。  [プロセスに添付] ダイアログボックスに表示されている Microsoft Edge にある開いているタブ **の一覧を確認** します。  

:::image type="complex" source="./media/attach-to-process-dialog.png" alt-text="[プロセスに添付] ダイアログ ボックスを構成Visual Studio" lightbox="./media/attach-to-process-dialog.png":::
   [プロセスに **添付] ダイアログ ボックス** を構成Visual Studio  
:::image-end:::  

**[Select...] を選択>** **JavaScript (Microsoft Edge – Chromium) の**横にあるチェック ボックスをオンにします。  タブを追加するには、新しいタブに移動し、タブを閉じて、[プロセスに添付****] ダイアログに反映された変更を表示するには、[更新] ボタン**を選択**します。  デバッグするタブを選択し、[アタッチ] を **選択します**。  

これでVisual Studioデバッガーが Microsoft Edge に接続されました。  JavaScript の実行を一時停止し、ブレークポイントを設定し、ステートメントを確認するには、次のページの [デバッグ出力] ウィンドウで直接 `console.log()` Visual Studio。  

## <a name="getting-in-touch-with-the-microsoft-visual-studio-team"></a>Microsoft のチームと連絡を取Visual Studioする  

Microsoft Visual Studioおよび Microsoft Edge チームは、JavaScript を使用する方法の詳細について、Visual Studio。  フィードバックを送信するには、[フィードバックの**** 送信] アイコンをVisual Studioまたはツイート@VisualStudio[を@EdgeDevTools。][TwitterIntentTweetViualstudioEdgdevtools]  

:::image type="complex" source="./media/feedback-icon.png" alt-text="[フィードバックの送信] Visual Studio" lightbox="./media/feedback-icon.png":::
   [ **フィードバックの送信** ] Visual Studio  
:::image-end:::  

<!-- links -->  

[VisualStudioWindowsIndex]: /visualstudio/windows/index "Visual Studioドキュメント|Microsoft Docs"  

[MicrosoftVisualstudioDownloads]: https://visualstudio.microsoft.com/downloads "ダウンロード Visual Studio"  
[MicrosoftVisualstudioVs]: https://visualstudio.microsoft.com/vs "Visual Studio IDE"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[TwitterIntentTweetViualstudioEdgdevtools]: https://twitter.com/intent/tweet?text=@VisualStudio+@EdgeDevTools "ツイートして@VisualStudioと@EdgeDevTools |Twitter"  
