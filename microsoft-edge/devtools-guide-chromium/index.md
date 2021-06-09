---
description: Microsoft Edge (Chromium) 開発者ツールについて
title: Microsoft Edge (Chromium) 開発者ツールの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7f9a4288980dd938a43b229e1d5396adc7937c67
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597011"
---
# <a name="microsoft-edge-chromium-developer-tools-overview"></a>Microsoft Edge (Chromium) 開発者ツールの概要  

アプリケーションをインストールするとMicrosoft Edgeブラウザーが表示されます。 また、Web プロジェクトを検査、デバッグ、作成する強力な方法も提供します。  ブラウザーに同梱されている開発者ツールは、Chromium オープンソース プロジェクトのツールに基づいて作成されます。そのため、ツールに関する理解が既にある可能性があります。  この記事では、説明を短くするために、 と `Microsoft Edge Developer Tools` 呼ばれます `DevTools` 。  

DevTools を使用して、次の開発タスクについて確認し、詳細を確認します。  

*   [ブラウザーで現在の Web ページのライブを][DevtoolsGuideDomIndex] 検査および変更します。  
*   [製品が異なるデバイスでどのように動作するのかをエミュレートし、][DevtoolsGuideDeviceModeIndex] 異なるネットワーク条件を満たしたモバイル環境をシミュレートします。  
*   [ビジュアル インターフェイスを備えるライブ ツール][DevtoolsGuideInspectStylesEditFonts] を使用して、Web ページ内の要素のスタイルを検査、調整、および変更します。  
*   [ブレークポイントのデバッグとライブ][DevtoolsGuideJavascriptIndex] コンソールを使用して JavaScript [をデバッグします][DevtoolsGuideConsoleIndex]。  
*   製品 [のアクセシビリティ、パフォーマンス、互換性][DevtoolsGuideIssuesIndex] 、セキュリティの問題を確認し、DevTools を使用してそれぞれの問題を解決する方法について説明します。  
*   [ネットワーク トラフィックを検査し][DevtoolsGuideNetworkIndex] 、問題の場所を確認します。  
*   [ブラウザーがコンテンツをさまざまな形式で保存][DevtoolsGuideStorageSessionstorage] した場所を調します。  
*   [製品のパフォーマンスを][DevtoolsGuideEvaluatePerformanceIndex] 評価して、メモリの問題 [とレンダリングの][DevtoolsGuideMemoryProblemsIndex] 問題 [を見つける][DevtoolsGuideRenderingToolsIndex]。  
*   [開発環境を使用して][DevtoolsGuideSourcesIndex][、DevTools][DevtoolsGuideWorkspacesIndex]の変更をファイル システムと同期し、Web[からファイル][DevtoolsGuideJavascriptOverrides]を上書きします。  
    
<!-- Is the link meant to be local or session storage for "inspect where the browser stored content"? -->  

そして、より多くの。  すべては、DevTools を開き、各ツールをニーズに合わせてカスタマイズするときに開始されます。  

## <a name="open-the-devtools"></a>DevTools を開く  

DevTools を開いて探索するには、次のいずれかのアクションを使用します。  

*   Web ページ上の任意の要素にカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  このアクションを実行すると、[要素] **ツールが開** きます。  
*   `F12` を選択します。  
*   `Ctrl` + `Shift` + `I` [Windows/Linux または `Command` + `Option` + `I` macOS で選択します。  
    
:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-inspect.msft.png" alt-text="任意の要素のコンテキスト メニューから [検査] を選択する" lightbox="./media/devtools-intro-inspect.msft.png":::  
         任意 **の要素の** コンテキスト メニューから [検査] を選択する  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-inspect-devtools-open.png" alt-text="選択した要素が強調表示された DevTools が開きます" lightbox="./media/devtools-intro-inspect-devtools-open.png":::  
         選択した要素が強調表示された DevTools が開きます  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

DevTools を操作するには、主に 2 つの方法があります。
*   マウスを使用する  
*   [キーボード ショートカット][DevtoolsGuideShortcutsIndex]。  キーボード ショートカットは、機能にすばやくアクセスする方法を提供し、アクセシビリティのために必要です。  DevTools Microsoft Edgeチームは、キーボードやスクリーン リーダーなどの支援テクノロジを使用してすべてのツールを利用できる環境に一生懸命取り組んでいます。  DevTools でさまざまな機能を開く方法の詳細については、「DevTools キーボード ショートカット[」Microsoft Edgeに移動します][DevtoolsGuideOpenIndex]。  

## <a name="dock-the-devtools-in-your-browser"></a>ブラウザーに DevTools をドッキングする  

DevTools を開いた場合、ブラウザーの左側にドッキングされます。  DevTools のドッキング位置を変更するには、次のアクションを実行します。  

1.  **[DevTools のカスタマイズと制御]** \( `...` \) ボタンを選択します。  
1.  ページ**\(** ドック側 \) を基準に**した DevTools**の配置の右側で、[ドック側] オプション**を選択**します。  
    
詳細については[、「DevTools 配置の変更Microsoft Edge (Undock、Dock to Bottom、Dock to Left) に移動します][DevtoolsGuideCustomizePlacement]。  

:::image type="complex" source="./media/devtools-intro-docking-menu.msft.png" alt-text="DevTools のドック側メニューのスクリーンショット" lightbox="./media/devtools-intro-docking-menu.msft.png":::  
   DevTools のドック側メニューのスクリーンショット  
:::image-end:::  

[ **ドック側] で**、次のレイアウト オプションを選択します。  

*   **別のウィンドウにドッキングを解除します**。   複数のモニターを使用したり、フルスクリーン アプリで作業する必要がある場合に役立ちます。  
*   **左にドッキングするか** 、 **右にドッキングします**。  DevTools を Web 製品と並べて維持するのに役立ち、モバイル デバイスをエミュレートすると優れています。  [ **左へドック] オプションと** **[右へドッキング** ] オプションは、高解像度ディスプレイで最適に機能します。  エミュレーション デバイスの詳細については、「DevTools でモバイル デバイスをエミュレート[する」Microsoft Edge移動します][DevtoolsGuideDeviceModeIndex]。  
*   **下にドッキングします**。  水平表示領域が足りない場合や、DOM またはコンソールで長いテキストをデバッグする場合に役立 **ちます**。  
    
:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-docking-left.msft.png" alt-text="[左にドッキング] を選択する" lightbox="./media/devtools-intro-docking-left.msft.png":::  
         [左 **にドッキング] を選択する**  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-bottom.msft.png" alt-text="[下へドッキング] を選択する" lightbox="media/devtools-intro-docking-bottom.msft.png":::  
         [下 **へドッキング] を選択する**  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  
:::row:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-right.msft.png" alt-text="[右へドッキング] を選択する" lightbox="media/devtools-intro-docking-right.msft.png":::  
         [右 **へドッキング] を選択する**  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-own-window.msft.png" alt-text="[別のウィンドウにドッキングを解除する] を選択する" lightbox="media/devtools-intro-docking-own-window.msft.png":::  
         [別 **のウィンドウにドッキングを解除する] を選択する**  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

## <a name="learn-about-the-core-tools"></a>コア ツールの詳細  

DevTools を使用すると、ブラウザーに現在表示されている Web 製品を検査、デバッグ、および変更する機能が提供されます。  ほとんどのツールは、変更をライブで表示します。  ライブ更新プログラムを使用すると、Web プロジェクトを更新またはビルドすることなく、Web プロジェクトの外観とナビゲーションや機能を絞り込むツールが非常に便利です。  DevTools を使用すると、コンピューター上の Web ベースのサード パーティ製品を変更することもできます。  

DevTools は数年間にわたり成長しました。  DevTools は、最初にツールを開く際に学習するのが難しいと考える場合があります。  次のテキストでは、さまざまな部分をすばやく紹介します。  メイン ツールバーにはいくつかのセクションが用意され、セクションは左から右に並べ替えます。  

:::image type="complex" source="./media/devtools-intro-menu-bar.msft.png" alt-text="さまざまなセクションを説明するラベル付き DevTools のメニュー バーのスクリーンショット。  順序: ツール、デバイス エミュレーション ツール、ツール タブ グループ、JavaScript エラー、問題、設定、フィードバック、カスタマイズ、および閉じるを検査します。" lightbox="./media/devtools-intro-menu-bar.msft.png":::  
   さまざまなセクションを説明するラベル付き DevTools のメニュー バーのスクリーンショット。  順序: 検査ツール、デバイス エミュレーション ツール、ツール タブ グループ、JavaScript エラー、問題、設定、フィードバック、カスタマイズ、閉じる。  
:::image-end:::  

*   [検査] ツールを使用すると、現在の Web ページで要素を選択できます。  アクティブ化した後、Web ページの別の部分にマウスを移動して、要素に関する詳細情報と、サイズ、パディング、余白を表示するカラー オーバーレイを取得できます。  
    
    :::image type="complex" source="./media/devtools-intro-inspect-tool.msft.png" alt-text="この記事の最初の見出しが選択された検査ツール" lightbox="./media/devtools-intro-inspect-tool.msft.png":::  
       この記事の最初の見出しが選択された検査ツール  
    :::image-end:::  
    
*   デバイス [エミュレーション ツールは][DevtoolsGuideDeviceModeIndex] 、エミュレートされたデバイス モードで現在の Web 製品を表示します。  デバイス **エミュレーション ツールを** 使用すると、ブラウザーのサイズを変更するときに製品の反応を実行してテストできます。  また、モバイル デバイス上のレイアウトと動作を推定することもできます。  
    
    :::image type="complex" source="./media/devtools-intro-device-emulation.msft.png" alt-text="エミュレートされた携帯電話でのこの記事の DevTools 表示のスクリーンショット" lightbox="./media/devtools-intro-device-emulation.msft.png":::  
       エミュレートされた携帯電話でのこの記事の DevTools 表示のスクリーンショット  
    :::image-end:::  
    
*   [ツール] タブ グループは、さまざまなシナリオで使用されるさまざまなツールを表すタブのグループです。  各ツールをカスタマイズして、コンテキストに基づいて各ツールが変更される場合があります。  その他のツールのドロップダウン メニューを開く場合は、[ **その他]** タブ \( `>>` \) ボタンを選択します。  各ツールは、後で次のセクションで紹介します。  
*   [ツール] タブ グループの横にはオプションのエラーと問題のショートカットがあります。  現在の Web ページで JavaScript のエラーや問題が発生すると、ショートカットが表示されます。  Open **Console to view # errors, # warnings** \(**JavaScript Errors**\) ボタンは、赤い円を表示し、その後に JavaScript エラーの `X` 数を表示します。  コンソールを開き [、][DevtoolsGuideConsoleIndex] エラーの詳細を確認するには **、[JavaScript Errors] ボタンを選択** します。  [ **表示する問題を開く] #issues** \(**Issues**\) ボタンは、青いメッセージ アイコンの後に問題の数が続きます。  [問題] ツール [を開く][DevtoolsGuideIssuesIndex] 場合は、[問題] **ボタンを選択** します。  
*   **[設定]** ボタンには、歯車アイコンが表示されます。  Web ページで DevTools**設定**開く場合は、次のボタン**を設定**します。  Web**ページ設定、****基本設定の**変更、**実験のオン**、その他のメニューが表示されます。  
*   [ **フィードバックの送信]** ボタンは、その横にチャット バブルが表示された torso を表示します。  [フィードバックの送信 **] ダイアログを開** くには、[フィードバックの送信 **] ボタンを選択** します。  [ **フィードバックの送信** ] ダイアログでは、何が起こったのかを説明する情報を入力し、スクリーンショットを自動的に含めることができます。  DevTools チームと接続して、問題、問題、またはアイデアを提案するために使用します。  
*   **[Devtools \(** \) のカスタマイズと制御] ボタン `...` をクリックすると、ドロップダウン メニューが開きます。  DevTools をドッキングする場所、検索場所、さまざまなツールを開く場所を定義できます。  
    
[ツール] タブ グループで、DevTools で使用できるさまざまなツールを開く場合があります。  次の一覧では、DevTools で最も一般的に使用されるツールについて説明します。  

*   **ようこそ**。  DevTools の新機能、チームに連絡する方法、および特定の機能に関する情報が含まれています。  
*   **要素**.  HTML と CSS を編集または検査できます。  ツールの両方を編集し、ブラウザーに変更内容を表示できます。  
*   [コンソール][DevtoolsGuideConsoleIndex].  ログ メッセージを表示およびフィルター処理できます。  ログ メッセージは、ネットワーク要求や開発者が生成したログなど、ブラウザーの自動ログです。  現在のウィンドウまたはフレームのコンテキストで **、コンソール** で JavaScript を直接実行することもできます。  
*   [Sources][DevtoolsGuideSourcesIndex].  コード エディターと JavaScript デバッガー。  プロジェクトの編集、スニペットの管理、現在のプロジェクトのデバッグを行えます。  
*   [ネットワーク][DevtoolsGuideNetworkIndex].  ネットワークキャッシュとブラウザー キャッシュからの要求または応答を監視および検査できます。  ニーズに合わせて要求と応答をフィルター処理し、さまざまなネットワーク条件をシミュレートできます。  パフォーマンス、メモリ、アプリケーション、セキュリティ、監査など****、その**** 他の**** 特殊**な**ツールも**利用できます**。  

## <a name="power-tip-use-the-command-menu"></a>電源ヒント: コマンド メニューを使用する  

DevTools には、Web 製品で使用する多くの機能と機能が提供されています。  さまざまな方法で DevTools の各部分にアクセスしますが、必要な機能に最も速くアクセスするには、コマンド メニューを使用します。  詳細については、[DevTools コマンド] メニューの [[コマンドMicrosoft Edge実行] に移動します][DevtoolsGuideCommandMenuIndex]。  コマンド メニューを開く場合は、次のいずれかの操作を実行します。  

*   `Control` + `Shift` + `P` \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  
*   **[DevTools \(** \) のカスタマイズと制御 `...` ] を選択し、[コマンドの実行]**を選択します**。  

:::image type="complex" source="./media/devtools-intro-command-menu.msft.png" alt-text="DevTools のコマンド メニューのスクリーンショット" lightbox="./media/devtools-intro-command-menu.msft.png":::  
DevTools のコマンド メニューのスクリーンショット  
:::image-end:::  

コマンド メニューでは、DevTools の機能を表示、非表示、または実行するコマンドを入力できます。  コマンド メニューを開いて、変更という単語を入力 **し、[ドロ**ワーの変更の表示] **を選択します**。  変更 **ツール** が開き、CSS を編集するときに便利ですが、DevTools UI で見つけるのは困難です。  

:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-command-menu-show-changes.msft.png" alt-text="コマンド メニューは、変更を入力した後にオプションを表示します。" lightbox="./media/devtools-intro-command-menu-show-changes.msft.png":::  
         コマンド メニューは、入力後にオプションを表示します。 `changes`  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-showing-changes.msft.png" alt-text="変更ツールを開いた DevTools" lightbox="./media/devtools-intro-showing-changes.msft.png":::  
         変更ツールを開いた**DevTools**  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

## <a name="customize-the-devtools"></a>DevTools をカスタマイズする  

DevTools は、ニーズや作業方法に合わせてカスタマイズできます。  設定を変更するには、次のいずれかの操作を実行します。  

*   **[設定**\(右上の歯車アイコン\) を選択します。  
*   を `F1` 選択するか `?` 、 を選択します。  
    
[基本設定 **] セクション** では、DevTools のいくつかの部分を変更できます。  たとえば、[ブラウザー言語の一致 **]** 設定を使用して、ブラウザーで使用する DevTools で同じ言語を使用できます。  別の例として、 **テーマ設定を** 使用して DevTools のテーマを変更します。  

:::image type="complex" source="media/devtools-intro-all-settings.msft.png" alt-text="DevTools のすべての設定のスクリーンショット" lightbox="./media/devtools-intro-all-settings.msft.png":::  
   DevTools のすべての設定のスクリーンショット  
:::image-end:::  

また、次の機能を含む高度な機能の設定を変更することもできます。    

*   [Workspaces][DevtoolsGuideWorkspacesIndex].  
*   [リストを無視] を使用して **ライブラリ コードをフィルター処理します**。  
*   デバイス シミュレーション **とテスト** モードに含めるデバイスを定義します。  詳細については、「デバイス DevTools でモバイル デバイスをエミュレート[するMicrosoft Edge移動します][DevtoolsGuideDeviceModeIndex]。  
*   ネットワーク調整プロファイル **を選択** します。  
*   シミュレートされた場所 **を定義します**。  
*   キーボード ショートカットをカスタマイズします。  DevTools で同じショートカットを使用するには、次Visual Studio Code操作を実行します。  
    1.  プリセットから **[ショートカットの一致] を選択します**。  
    1.  [Visual Studio Code]**を選択します**。  
        
    :::image type="complex" source="./media/devtools-intro-match-keys.msft.png" alt-text="すべてのキーボード ショートカットとメニューのスクリーンショットで、各ショートカットと一致Visual Studio Code" lightbox="./media/devtools-intro-match-keys.msft.png":::  
       すべてのキーボード ショートカットとメニューのスクリーンショットで、各ショートカットと一致Visual Studio Code  
    :::image-end:::  
    
## <a name="try-experimental-features"></a>実験的な機能を試す  

DevTools チームは、DevTools の実験として新機能を提供します。  実験の完全な一覧を取得するには、DevTools 設定に移動し **、[** 実験]**を選択します**。  各実験をオンまたはオフにできます。  どの実験が有益かを判断するのに役立ちます。  実験の詳細については、「実験機能」 [に移動します][DevtoolsGuideExperimentalFeaturesIndex]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

近々ある [DevTools][DevtoolsGuideWhatsNew202102Devtools] の最新の機能をプレビューする場合は、毎晩ビルドされる [Microsoft Edge Canary][MicrosoftedgeinsiderDownload] をダウンロードします。  

## <a name="see-also"></a>関連項目  

*   [DevtoolsGuide for Beginners: html はじめに DOM を使用したユーザー設定][DevtoolsGuideBeginnersHtml]  
*   [Microsoft Edge (Chromium) DevTools プロトコル][DevtoolsProtocolIndex]  
    
<!-- links -->  

[DevtoolsGuideBeginnersHtml]: ./beginners/html.md "初級者向け DevTools: HTML と DOM の使用を|Microsoft Docs"  
[DevtoolsGuideCommandMenuIndex]: ./command-menu/index.md "[DevTools コマンド] メニューの [Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsGuideConsoleIndex]: ./console/index.md "コンソールの概要|Microsoft Docs"  
[DevtoolsGuideCustomizePlacement]: ./customize/placement.md "DevTools Microsoft Edge配置を変更する (Undock、Dock to Bottom、Dock to Left) |Microsoft Docs"  
[DevtoolsGuideDeviceModeIndex]: ./device-mode/index.md "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsGuideDomIndex]: ./dom/index.md "DOM ファイルの表示と変更を開始|Microsoft Docs"  
[DevtoolsGuideEvaluatePerformanceIndex]: ./evaluate-performance/index.md "ランタイム パフォーマンス の分析の開始|Microsoft Docs"  
[DevtoolsGuideExperimentalFeaturesIndex]: ./experimental-features/index.md "実験的な機能|Microsoft Docs"  
[DevtoolsGuideMemoryProblemsIndex]: ./memory-problems/index.md "メモリの問題を修正|Microsoft Docs"  
[DevtoolsGuideInspectStylesEditFonts]: ./inspect-styles/edit-fonts.md "[スタイル] ウィンドウの [CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevtoolsGuideIssuesIndex]: ./issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevtoolsGuideJavascriptIndex]: ./javascript/index.md "DevTools アプリケーションの JavaScript のデバッグMicrosoft Edge開始|Microsoft Docs"  
[DevtoolsGuideJavascriptOverrides]: ./javascript/overrides.md "DevTools を使用して Web ページ リソースをローカル コピー Microsoft Edgeオーバーライド|Microsoft Docs"  
[DevtoolsGuideNetworkIndex]: ./network/index.md "DevTools サーバーでネットワークMicrosoft Edgeを調|Microsoft Docs"  
[DevtoolsGuideOpenIndex]: ./open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  
[DevtoolsGuideRenderingToolsIndex]: ./rendering-tools/index.md "ランタイム パフォーマンス の分析|Microsoft Docs"  
[DevtoolsGuideShortcutsIndex]: ./shortcuts/index.md "Microsoft EdgeDevTools キーボード ショートカット |Microsoft Docs"  
[DevtoolsGuideSourcesIndex]: ./sources/index.md "ソース ツールの概要|Microsoft Docs"  
[DevtoolsGuideStorageSessionstorage]: ./storage/sessionstorage.md "DevTools を使用してセッション ストレージを表示Microsoft Edge編集|Microsoft Docs"  
[DevtoolsGuideWhatsNew202102Devtools]: ./whats-new/2021/02/devtools.md "DevTools の新機能 (Microsoft Edge 90) |Microsoft Docs"  
[DevtoolsGuideWorkspacesIndex]: ./workspaces/index.md "Workspaces を使用してファイルを編集|Microsoft Docs"  
[DevtoolsProtocolIndex]: ../devtools-protocol-chromium/index.md "Microsoft Edge (Chromium) DevTools プロトコルの概要 | Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge アドオン"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channelsをダウンロードする"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "拡張機能 | Chrome Web ストア"  
