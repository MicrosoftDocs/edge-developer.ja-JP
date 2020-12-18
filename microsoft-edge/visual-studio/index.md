---
description: Microsoft Edge (Chromium) と Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, vs, visual studio, debugger
ms.openlocfilehash: f3796a040fe6c658211b4009445b5c179ab9b077
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231210"
---
# Visual Studio

Microsoft [Visual Studio](https://visualstudio.microsoft.com/vs/) は、Web アプリケーションの編集、デバッグ、ビルド、発行に使用できる統合された開発環境 (IDE) です。 これは、Web 開発の多くの側面に使用できる豊富な機能を備えるプログラムです。 Visual Studio には、ほとんどの ID で提供される標準のエディターとデバッガー以上の機能が用意されています。Visual Studio には、開発プロセスを容易にするためのコンパイラ、コード完了ツール、グラフィカル デザイナー、その他の多くの機能が含まれています。 まだ使用 [していない場合](https://visualstudio.microsoft.com/downloads/) は、Visual Studioページにアクセスしてダウンロードしてください。

現在、Visual Studio 2019 では、ASP\.NET Framework および ASP\.NET Core アプリケーションの Microsoft Edge での JavaScript のデバッグがサポートされています。 次の手順に従って、Microsoft Edge をVisual Studio。

## Microsoft Edge を起動する
Visual Studio ASP\.NET と ASP\.NET Core アプリケーションをビルドし、Web サーバーを起動し、Microsoft Edge を起動して、1 つのボタンをクリックすると Visual Studio デバッガーを接続します。 これにより、MICROSOFT Edge で実行されている JavaScript を IDE から直接デバッグできます。

### 新しい ASP.NET Core Web アプリケーションを作成する

2019 Visual Studio開き、[新しいプロジェクトの **作成] を選択します**。 次の画面で **、[ASP\.NET Core Web アプリケーション** ] を選択し、[次へ] を **クリックします**。

> ##### 図 1  
> 新しい ASP.NET Core Web アプリケーションを作成する 新しい ASP.NET ![ Core Web アプリケーションを作成する](./media/create-new-project.png)  

新しいプロジェクト **のプロジェクト名を** 入力し、[作成] をクリック **します**。 この例の目的上、React.jsを**** React.js Core アプリケーションと統合する方法を示すテンプレートとして ASP.NET を選択し、[作成] をクリック**します**。

### Microsoft Edge をアプリから起動Visual Studio

プロジェクトを作成したら **、ClientApp/src/components/Counter.js。 ** 次に、Visual Studio再生ボタンと**IIS Express**の横にあるドロップダウンを選択して、JavaScript をデバッグする必要があります。 **** 

> ##### 図 2  
> 緑色の [再生]**** ボタンと **[IIS Express]** ドロップダウンの横にある、緑色の再生ボタンと IIS Express の横にある 
> ![ ドロップダウン](./media/vs-dropdown.png)  

[スクリプト **のデバッグ] を選択し、[** 有効] を **クリックします**。

> ##### 図 3  
> [スクリプトのデバッグを有効にする] Visual Studio ![ でスクリプトのデバッグを有効Visual Studio](./media/enable-script-debugging.png)  

同じドロップダウンで **、[Web ブラウザー** ] を選択し、Visual Studio起動する Microsoft Edge のプレビュー チャネル (Microsoft Edge Canary、Dev、Beta) をクリックします。 まだインストールしていない場合は、この [ページにアクセス](https://www.microsoftedgeinsider.com/download) して Microsoft Edge プレビュー チャネルをインストールしてください。

> ##### 図 4  
> 起動する Microsoft Edge のプレビュー チャネルをVisual Studio Microsoft Edge のプレビュー チャネルを選択し、Visual Studio ![ します。](./media/set-web-browser.png)  

> [!NOTE]
> Microsoft Edge (EdgeHTML) を選択するとVisual Studio Microsoft Edge (Chromium) の代わりに起動します。 [Microsoft Edge の](https://www.microsoftedgeinsider.com/download) プレビュー チャネルをインストールし、それらを選択するか、コンピューターにインストールされている Microsoft Edge のバージョンが Microsoft Edge (Chromium) であり、Microsoft Edge (EdgeHTML) ではインストールされていないことを確認します。

これで、Visual Studio構成が完了しました。緑色の [再生] ボタン **をクリック** します。 Visual Studioアプリケーションを構築し、Web サーバーを起動し、Microsoft Edge を起動して、そのアプリケーションで指定されているポートまたはポートに `https://localhost:44362/` **launchSettings.jsします**。

> ##### 図 5  
> Microsoft Edge は、microsoft Edge Visual Studio ![ から起動された Microsoft Edge からVisual Studio](./media/edge-launch.png)  

### Microsoft Edge で実行されている JavaScript のデバッグ

再び Visual Studio に切り替えます。 次 **Counter.js**行 13 のブレークポイントを設定するには、その行の横にあるとじしろをクリックします。

> ##### 図 6
> Visual Studio にブレークポイントを設定するには、Counter.jsの行 13 の横にあると**** じしろをクリックし、Visual Studio の行 13 の横にあるとじしろをクリック 
> ![ Counter.js](./media/set-breakpoint.png)  

起動した Microsoft Edge のインスタンスにVisual Studioします。 ページの **左側にある** NavMenu の [カウンター] をクリックします。 ここで、[増分] **をクリックします**。

> ##### 図 7
> ASP.NET Core Web アプリケーションの ASP.NET ページの [ ![ カウンター] ページ](./media/edge-counter.png)  

JavaScript debugger in Visual Studio is going to hit the breakpoint we set in **Counter.js**. Visual Studio Microsoft Edge で実行されている JavaScript の実行を一時停止し、スクリプトを 1 行に 1 行ステップ実行できます。

> ##### 図 8
> Visual Studio Microsoft Edge で実行されている JavaScript の一時停止Visual Studio Microsoft Edge で ![ 実行されている JavaScript の一時停止](./media/hit-breakpoint.png)  

この例は、次の例で使用できる機能の簡単なVisual Studio。 2019 年 1 月 2019 年にVisual Studio詳細については、ドキュメントを [参照してください](/visualstudio/windows/?view=vs-2019&preserve-view=true)。

## Microsoft Edge に接続する
前のワークフローでは、Microsoft Edge Visual Studio起動します。 このワークフローを使用すると、既に実行されている Microsoft Edge Visual Studioデバッガーをアタッチできます。 

最初に、Microsoft Edge の実行中のインスタンスが含めずに確認します。 次に、ターミナルから次のコマンドを実行します。

```console
start msedge –remote-debugging-port=9222
```

次Visual Studio、[デバッグ] メニュー**を開**き、[プロセスにアタッチ **] を**選択するか、押します `Ctrl`  +  `Alt`  +  `P` 。

> ##### 図 9
> Selecting **Attach to Process** in Visual Studio ![ Selecting **Attach to Process** in Visual Studio](./media/attach-to-process.png)  

[プロセス **にアタッチ]** ダイアログで、[接続の **種類** ] を **Chrome devtools プロトコル websocket (認証なし) に設定します**。 [接続先 **] テキストボックスに** 、入力して `http://localhost:9222/` 押 `Enter` します。 Microsoft Edge で開いているタブの一覧が 、[プロセスにアタッチ] ダイアログ **ボックスに一覧表示** されます。

> ##### 図 10
> [プロセスに **アタッチ]** ダイアログボックスをVisual Studioの [プロセスにアタッチ] ![ ダイアログ ボックスをVisual Studio](./media/attach-to-process-dialog.png)  

**[Select...] をクリックします。** JavaScript **(Microsoft Edge – Chromium) を確認します**。 [最新の情報に更新] ボタンをクリックすると、タブの追加、新しいタブへの**** 移動、およびタブの終了を行い、[プロセスにアタッチ] ダイアログに反映された変更**を確認**できます。 デバッグするタブを選択し、[アタッチ] を **クリックします**。

これでVisual Studioデバッガーが Microsoft Edge にアタッチされました。 JavaScript の実行を一時停止し、ブレークポイントを設定し、次のコマンドの [デバッグ出力] ウィンドウでステートメント `console.log()` を直接Visual Studio。

## Microsoft Visual Studio チームと連絡を取る  

JavaScript を使用する方法の詳細については、このページVisual Studio。  Please send us feedback by clicking the **Feedback** icon in Visual Studio or by twittering [ @VisualStudio and @EdgeDevTools](https://twitter.com/intent/tweet?text= @VisualStudio+@EdgeDevTools).  

> ##### 図 11
> [ **フィードバック** ] アイコンVisual Studioの ![ [フィードバック] アイコンVisual Studio](./media/feedback-icon.png)  
