---
description: Microsoft Edge (Chromium) 開発者ツールについて
title: Microsoft Edge (Chromium) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fa407393f8ecb79a3382294742bf9061787ec04a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397705"
---
# <a name="microsoft-edge-chromium-developer-tools-overview"></a>Microsoft Edge (クロム) 開発者ツールの概要  

Microsoft Edge は、クロム オープンソース プロジェクトを採用しています。  新しい Microsoft Edge ブラウザーを使用すると、Web の互換性が向上し、さまざまな Web プラットフォームの断片化が軽減されます。  この変更により、Microsoft Edge で Web ページのビルドとテストが容易になります。  新しい Microsoft Edge は、他のクロム ベースのブラウザーで開いた場合、Web ページが期待通り動作するのに役立ちます。  クロムベースのブラウザーには、Google Chrome、Vivaldi、Opera、Brave、新しい Microsoft Edge が含まれます。  

Web は、デバイスの種類が増え続け、さまざまな種類のデバイスで使い方が増え続け始めていました。  Web ページのテストに伴う複雑性とオーバーヘッドは急速に増加しています。  このような Web 開発者は、さまざまなシステムに対してテストする必要があります。  すべてのデバイスの種類とブラウザーで Web ページが適切に機能するために、特に小規模な会社で働く場合は、ほとんど不可能な場合があります。  新しい Microsoft Edge は、クロムに基づくものに変更しました。  Microsoft Edge チームは、Microsoft Edge Web プラットフォームを他のクロム ベースのブラウザーに合わせて配置することで、マトリックスを簡略化しました。  新しい Microsoft Edge は、クラス最高の開発エクスペリエンスを提供します。  このエクスペリエンスは、ブラウザー内や、日常使用する他の開発者ツール (コードなど) とVisual Studioされます。  

クロムベースのブラウザー開発者として、新しい Microsoft Edge ブラウザーに快適に対応する必要があります。  Microsoft Edge \(Chromium\) DevTools は、既に知っている開発者ツールと同様に機能します。  Microsoft Edge \(Chromium\) 開発者ツールは、Microsoft Edge \(Chromium\) DevTools または DevTools と呼ばれることが多い。  詳細については、「Microsoft Edge [(クロム) DevTools の新機能」に移動します][DevtoolsGuideChromiumWhatsNewIndex]。  

:::image type="complex" source="./media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools" lightbox="./media/devtools.png":::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

以前に Microsoft Edge \(EdgeHTML\) 用に開発し、新しい Microsoft Edge を評価している場合は、Web ページをより簡単かつ迅速に構築およびテストするための優れた新しいツールが提供されます。  

## <a name="open-the-devtools"></a>DevTools を開く  

Microsoft Edge DevTools は、Microsoft Edge ブラウザーに直接組み込む一連のツールです。  DevTools を使用すると、ブラウザー内で以下のタスクを直接実行できます。  

*   HTML Web ページの検査と変更  
*   CSS を編集し、Web ページのレンダリング方法をプレビューする  
*   フロントエンド `console.log()` JavaScript コードのすべてのステートメントを確認する  
*   スクリプトをデバッグし、ブレークポイントを設定し、コードを 1 行に 1 行にステップ実行する  
    
DevTools が提供する機能のその他の例を使用すると、Microsoft Edge で Web ページを簡単かつ迅速に構築およびテストできます。  

DevTools を開く方法  

*   選択する `F12` 
*   `Ctrl` + `Shift` + `I` [\(Windows/Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。  
    
サイト上の要素の HTML または CSS を表示する場合は、要素を右クリックし****、[検査] を選択して [要素] ツールに**移動**します。  要素の検査モードで DevTools を開く**場合**は `Ctrl` + `Shift` + `C` 、[\(Windows/Linux\) または `Command` + `Option` + `C` \(macOS\) を選択します。 要素 **の検査モードを** 使用すると、Web ページで要素を選択し、[要素] ツールに HTML と CSS を **表示** できます。  

フロントエンド JavaScript コードからログを確認する場合や、スクリプトをすばやく実行する場合は、コンソール を開 **きます**。   DevTools で**コンソール**ツールを起動するには `Ctrl` + `Shift` + `J` 、[\(Windows/Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  

## <a name="core-tools"></a>コア ツール  

:::image type="complex" source="./media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools コア ツール" lightbox="./media/devtools-core-tools.png":::
   Microsoft Edge (Chromium) DevTools コア ツール  
:::image-end::: 

Microsoft Edge \(Chromium\) DevTools には、次のツールが含まれています。  

*   HTML **と** CSS の編集、アクセシビリティ プロパティの検査、イベント リスナーの表示、DOM ミューテーション ブレークポイントの設定を行う要素ツール  
*   ログ **メッセージの** 確認とフィルター処理、JavaScript オブジェクトと DOM ノードの検査、および選択したウィンドウまたはフレームのコンテキストでの JavaScript の実行を行うコンソール  
*   コード **を開** いて編集し、ブレークポイントを設定し、コードをステップ実行し、Web ページの状態を表示するソース ツール
*   ネットワーク **キャッシュ** とブラウザー キャッシュからの要求と応答を監視および検査するネットワーク ツール   
*   サイト **で** 必要な時間とシステム リソースをプロファイルするパフォーマンス ツール  
*   メモリ **リソース** の使用を測定し、異なる状態のコード ランタイムでヒープ スナップショットを比較するメモリ ツール  
*   Web **アプリ** マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグするアプリケーション ツール。  また、アプリケーション ツールからストレージ、データベース、キャッシュを検査および **管理** することもできます。  
*   セキュリティ **の** 問題をデバッグし、Web ページに HTTPS が適切に実装されていることを確認するためのセキュリティ ツール。  HTTPS は、サイトとサイト上に個人情報を入力するユーザーの両方に対して、重要なセキュリティとデータの整合性を提供します。  
*   Web **ページの監査** を実行する監査ツール \( **名前が変更**されました。  監査の結果は、次の方法でサイトの品質を向上させるのに役立ちます。  
    *   Web ページへのアクセス、セキュリティ保護、パフォーマンスに関する一般的なエラーをキャッチします。  
    *   各エラーを修正します。  
    *   PWA を構築します。  
        
[!INCLUDE [audits-panel-note](./includes/audits-panel-note.md)]  

フィードバックと [機能要求を送信します](#getting-in-touch-with-the-microsoft-edge-devtools-team)。  

## <a name="extensions"></a>拡張機能  

Web ページ \(または apps\) の構築中に問題を診断してデバッグすると、拡張機能を使用して DevTools にアクセスした可能性があります。 Microsoft Edge 拡張機能は [、Microsoft Edge アドオンから取得されます][MicrosoftEdgeAddonsExtensions]。  [Microsoft Edge アドオンで][MicrosoftEdgeAddonsExtensions]、[開発者ツール] カテゴリから DevTools 拡張機能を参照するか、特定の拡張機能を検索します。 ****  

[Chrome Web ストア][GoogleChromeWebstoreExtensions]から拡張機能を追加することもできます。  

:::image type="complex" source="./media/allow-extensions-from-stores.png" alt-text="Microsoft Edge の Chrome Web ストア" lightbox="./media/allow-extensions-from-stores.png":::
   Microsoft Edge の Chrome Web ストア  
:::image-end:::  

上部の [他のストアからの拡張機能を許可する] を **選択** し、表示されるダイアログで [ **許可** ] を選択します。  

> [!NOTE]
> Microsoft Store 以外のソースからインストールされた拡張機能は未確認であり、ブラウザーのパフォーマンスに影響を与える可能性があります。  

[Chrome **に追加] を** 選択して、DevTools 拡張機能を Microsoft Edge に追加します。  

:::image type="complex" source="./media/install-extension-from-chrome-store.png" alt-text="Chrome Web ストアから Microsoft Edge に拡張機能を追加する" lightbox="./media/install-extension-from-chrome-store.png":::
   Chrome Web ストアから Microsoft Edge に拡張機能を追加する  
:::image-end:::  

## <a name="shortcuts"></a>ショートカット  

次のショートカットは、メインの DevTools ウィンドウを制御します。すべてのツール間で動作するか、または両方を実行します。  

| Action | Windows/Linux | macOS |  
|:--- |:--- | :--- |  
| DevTools \(開いて最後に表示されたツール\) を表示/非表示にする | `F12` または `Ctrl`+`Shift`+`I` | `Command`+`Option`+`I` |  
| コンソールの表示 | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 要素を選択して **要素ツールに** HTML と CSS を表示できる要素の検査モードで DevTools を **表示** する | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| 設定の表示 | `?` または `Fn`+`F1` | `?` または `Fn`+`F1` |  
| 次のパネルを表示する | `Ctrl`+`]` | `Command`+`]` |  
| 前のパネルを表示する | `Ctrl`+`[` | `Command`+`[` |  
| DevTools を最後に使用した位置にドッキングします。  DevTools がセッション全体の既定の位置に残っている場合、ショートカットは DevTools を別のウィンドウにドッキング解除します。 | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| **デバイス モード**の切り替え | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| 要素 **を選択し** 、[要素] ツールで HTML と CSS を表示できる要素の検査モードの切り **替** え | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| コマンド メニューを表示する | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| ドロワーの表示/非表示 | `Esc` | `Esc` |  
| 更新。  キャッシュを使用して Web ページを更新します。  | `F5` または `Ctrl`+`R` | `Command`+`R` |  
| ハードの更新。  Microsoft Edge にリソースの再ダウンロードと再読み込みを強制的に行います。  使用されるリソースは、キャッシュされたバージョンから取得される可能性があります。 | `Ctrl`+`F5` または `Ctrl`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 現在のパネル内のテキストを検索します。  監査、アプリケーション、およびセキュリティ ツールではサポートされていません | `Ctrl`+`F` | `Command`+`F` |  
| ドロワーに検索ツールを表示し、読み込まれたすべてのリソースでテキストを検索できます | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| ソース パネルでファイルを開く | `Ctrl`+`O` または `Ctrl`+`P` | `Command`+`O` または `Command`+`P` |  
| 拡大する | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 縮小 | `Ctrl`+`-` | `Command`+`-` |  
| 既定のズーム レベルを復元する | `Ctrl`+`0` | `Command`+`0` |  
| スニペットを実行する | `Ctrl`+`O``Ctrl` + `P` または、次 `!` にスクリプトの名前を入力してから、 `Enter` | を `Command` + `O` 選択 `Command` + `P` するか、 `!` スクリプトの名前を入力してから、 `Enter` |  
| 編集できない HTML ソース コードを新しいタブに表示する | `Ctrl`+`U` | 該当せず |  

> [!NOTE]
> デバッグ中にブレークポイントで一時停止している場合は、最初に**更新**ショートカットがランタイムを再開します。  

## <a name="see-also"></a>関連項目  

*   [初級向け DevTools: HTML と DOM の使用を開始する][DevtoolsGuideChromiumBeginnersHtml]  
*   [Microsoft Edge (Chromium) DevTools プロトコル][DevtoolsProtocolChromiumIndex]  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

近々ある [DevTools][DevtoolsGuideChromiumWhatsNewIndex] の最新の機能をプレビューする場合は、毎晩ビルドされる [Microsoft Edge Canary][MicrosoftedgeinsiderDownload] をダウンロードします。  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "初級向け DevTools: HTML と DOM の使用を開始する | Microsoft Docs"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/11/devtools "Microsoft Edge (Chromium) DevTools の新機能 | Microsoft Docs"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools プロトコル | Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge アドオン"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channelsをダウンロードする"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "拡張機能 | Chrome Web ストア"  
