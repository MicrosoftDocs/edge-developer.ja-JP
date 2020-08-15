---
description: Microsoft Edge (Chromium) 開発者ツールについて理解する
title: Microsoft Edge (Chromium) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cb51e16083e4798478817910e54c571721d094f8
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931225"
---
# Microsoft Edge (Chromium) 開発者ツール  

Microsoft Edge では、Chromium open source プロジェクトを採用して、より良い web 互換性と、さまざまな基盤 web プラットフォームの断片化の少ない機能を作成しました。  この変更により、Microsoft Edge で web サイトを作成してテストして、それぞれが Chromium ベースのブラウザーで表示されていても期待どおりに動作するようになります (Google Chrome、Vivaldi、Opera、Brave など)。  

Web はさまざまな種類のデバイスにわたって使用されていますが、web サイトのテストに関わる複雑さとオーバーヘッドが増大しています。 Web 開発者 (特に小規模企業向けのもの) では、さまざまなシステムをテストする必要があるため、サイトがすべてのデバイスの種類とすべてのブラウザーで適切に動作することを確認することは不可能です。  Microsoft edge が Chromium をベースとしているため、microsoft edge チームは、Microsoft Edge web platform を他の Chromium ベースのブラウザーと連携させることで、優れた開発者ツールエクスペリエンスを、ブラウザー内と、毎日 (Visual Studio コードなど) で使用している他の開発者ツールで提供しています。  

Microsoft Edge をチェックしていて、Chromium ベースのブラウザーで主に開発している場合は、自宅で適切なことを考えてください。  Microsoft Edge \ (Chromium \) 開発者ツールは、既に知っていて使用している開発者ツールと同じ方法で機能します。  詳細については、「 [Microsoft Edge (Chromium) DevTools の新機能][DevtoolsGuideChromiumWhatsNewIndex]」を参照してください。  

:::image type="complex" source="./devtools-guide-chromium/media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

Microsoft edge の次のバージョンを確認していて、以前に Microsoft edge \ (EdgeHTML \) で開発したことがある場合は、Microsoft Edge で web サイトを簡単かつ迅速に構築およびテストするための新しいツールが追加されました。  

## DevTools を開く  

以前に DevTools を使ったことがない場合は、microsoft edge 開発者ツールは Microsoft Edge ブラウザーに直接組み込まれている一連のツールです。  これらの DevTools を使用すると、次の操作を実行できます。  

*   HTML web サイトを検査して変更を加える  
*   CSS を編集し、web サイトの表示をプレビューで確認する  
*   `console.log()`フロントエンド JavaScript コードのすべてのステートメントを表示する  
*   ブレークポイントを設定し、行ごとにステップスルーすることによってスクリプトをデバッグする  

ブラウザー内で直接。  ここでは、Microsoft Edge で web サイトを作成してテストするために、DevTools が提供するいくつかの機能の例を紹介します。  

DevTools を開くには  

*   キーを押し `F12` 
*   `Ctrl` + `Shift` + `I` Windows \ ( `Command` + `Option` + `I` macOS) を押します。  

サイトの要素の HTML または CSS を表示する場合は、要素を右クリックして [ **検査** ] を選択し、[要素] パネルに移動します。  また、 `Ctrl` + `Shift` + `C` Windows \ ( `Command` + `Option` + `C` macOS で) を押して、[**要素の検査] モード**で、サイトの要素を選択し、[**要素**] パネルで HTML と CSS を確認することができます。  

フロントエンドの JavaScript コードからログを表示する場合、またはスクリプトをすばやく実行する場合は、 `Ctrl` + `Shift` + `J` Windows または macOS を押して、 `Command` + `Option` + `J` devtools でコンソールパネルを起動します。  

## コア ツール  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools コアツール":::
   Microsoft Edge (Chromium) DevTools コアツール  
:::image-end::: 

Microsoft Edge \ (Chromium \) DevTools には、次のパネルが含まれています。  

*   **要素** は、パネルHTML および CSS の編集、アクセシビリティのプロパティの検査、イベント リスナーの表示、DOM 変異のブレークポイントの設定を行います。  
*   **コンソール** は、ログ メッセージを表示およびフィルタリングし、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウやフレームのコンテキストでの JavaScript を実行します。  
*   コードのオープンとライブ編集、ブレークポイントの設定、コードのステップ実行、web サイトの1行の JavaScript の状態の表示を行うための **ソース** パネル  
*   **ネットワーク** パネルは、ネットワークとブラウザーのキャッシュからの要求や応答を監視および検査します。   
*   **パフォーマンス** パネルは、サイトに必要な時間とシステム リソースをプロファイルします。  
*   **メモリ** パネルは、メモリ リソースの使用状況を測定し、コード ランタイムの異なる状態でヒープ スナップショットを比較します。  
*   Web アプリマニフェスト、サービスワーカー、service worker キャッシュを検査、変更、デバッグする **アプリケーション** パネル。  また、 **アプリケーション** パネルからストレージ、データベース、キャッシュを調査し、管理することもできます。  
*   セキュリティの問題をデバッグし、web サイトに HTTPS が適切に実装されていることを確認するための **セキュリティ** パネル。  HTTPS は、サイトとユーザーの両方にとって重要なセキュリティとデータの整合性を提供します。これは、サイトでの個人情報の提供を目的としています。  
*   監査 **パネル \** ( **Lighthouse**\ 名前を変更しました \) で web サイトの監査が実行されます。  監査の結果は、次のような方法でサイトの品質を向上させるのに役立ちます。  
    *   Web サイトのアクセシビリティ、セキュリティ、パフォーマンスなどに関連する一般的なエラーを検出します。  
    *   各エラーを修正します。  
    *   PWA を構築します。  

[!INCLUDE [audits-panel-note](./devtools-guide-chromium/includes/audits-panel-note.md)]  

[フィードバックと機能のリクエストを](#getting-in-touch-with-the-microsoft-edge-devtools-team)送信してください。  

## 拡張機能  

Web サイトやアプリの構築時に発生する問題の診断とデバッグを支援するために、DevTools の拡張機能を使用している可能性があります。  Microsoft edge の [アドオン][MicrosoftEdgeAddonsExtensions] ページから microsoft edge の拡張機能を入手できます。  [Microsoft Edge のアドオン][MicrosoftEdgeAddonsExtensions]ページから、**開発者ツール**のカテゴリからの devtools 拡張機能を参照したり、特定の拡張機能を検索したりできます。  

[Chrome Web ストア][GoogleChromeWebstoreExtensions]から拡張機能を追加することもできます。  

:::image type="complex" source="./devtools-guide-chromium/media/allow-extensions-from-stores.png" alt-text="Microsoft Edge の Chrome Web ストア":::
   Microsoft Edge の Chrome Web ストア  
:::image-end:::  

上部で、[ **他のストアの拡張機能を許可する** ] を選択し、表示されるダイアログボックスで [ **許可** ] を選びます。  

> [!NOTE]
> Microsoft Store 以外のソースからインストールされた拡張機能は未確認であり、ブラウザーのパフォーマンスに影響する可能性があります。  

[ **Chrome に追加** ] を選択して、Microsoft Edge に devtools 拡張機能を追加します。  

:::image type="complex" source="./devtools-guide-chromium/media/install-extension-from-chrome-store.png" alt-text="Chrome Web ストアから Microsoft Edge に拡張機能を追加する":::
   Chrome Web ストアから Microsoft Edge に拡張機能を追加する  
:::image-end:::  

## ショートカット  

これらのショートカットは、メインの [開発ツール] ウィンドウの制御、すべてのツールの操作、またはその両方を行うことができます。  

| 操作 | Windows | macOS |  
|:--- |:--- | :--- |  
| DevTools の表示/非表示 \ (最後に表示されたパネルに表示される \) | `F12` / `Ctrl`+`Shift`+`I` | `Command`+`Option`+`I` |  
| コンソールパネルを表示する | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| サイト上の要素を選択して、[**要素**] パネルで HTML と CSS を表示できる [**要素の検査] モード**で devtools を表示します。 | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| 設定を表示する | `?` / `Fn`+`F1` | `?` / `Fn`+`F1` |  
| 次のパネルを表示 | `Ctrl`+`]` | `Command`+`]` |  
| 前のパネルを表示する | `Ctrl`+`[` | `Command`+`[` |  
| 使用されている最後の位置に DevTools をドッキングします。  DevTools がセッション全体の既定の位置に留まる場合は、このショートカットでは、DevTools を別のウィンドウにドッキング解除します。 | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| **デバイスモード**の切り替え | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| [ **要素の検査] モード** を切り替えて、サイトの要素を選択し、[ **要素** ] パネルで HTML と CSS を表示します。 | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| コマンドメニューを表示する | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| ドロワーの表示/非表示 | `Esc` | `Esc` |  
| 非.  キャッシュを使用してページが更新されます。  | `F5` / `Ctrl`+`R` | `Command`+`R` |  
| ハードリフレッシュ。  これにより、Microsoft Edge はリソースをもう一度ダウンロードして、再読み込みします。  使用されているリソースがキャッシュバージョンから取得されている可能性があります。 | `Ctrl`+`F5` / `Ctrl`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 現在のパネル内でテキストを検索します。  監査、アプリケーション、セキュリティの各パネルではサポートされません。 | `Ctrl`+`F` | `Command`+`F` |  
| 引き出しに検索パネルを表示します。これにより、読み込まれたすべてのリソースのテキストを検索することができます。 | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| [ソース] パネルでファイルを開く | `Ctrl`+`O` / `Ctrl`+`P` | `Command`+`O` / `Command`+`P` |  
| 拡大 | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 縮小 | `Ctrl`+`-` | `Command`+`-` |  
| 既定のズームレベルに戻す | `Ctrl`+`0` | `Command`+`0` |  
| スニペットの実行 | `Ctrl`+`O`または、「」と入力し、その `Ctrl` + `P` `!` 後にスクリプトの名前を入力して、 `Enter` | `Command` + `O` または、「」と入力して、 `Command` + `P` `!` 続けてスクリプトの名前を入力して、 `Enter` |  
| 編集不可の HTML ソースコードを新しいタブに表示する | `Ctrl`+`U` | 該当せず |  

> [!NOTE]
> デバッグ中にブレークポイントで一時停止している場合は、[ **更新** ] ショートカットで最初にランタイムが再開されます。  

## 関連項目  

*   [初心者向けの DevTools: HTML と DOM の使用を開始する][DevtoolsGuideChromiumBeginnersHtml]  
*   [Microsoft Edge (Chromium) DevTools プロトコル][DevtoolsProtocolChromiumIndex]  

## Microsoft Edge DevTools チームと連絡を取り合う  

フィードバックを送信してください。 Microsoft Edge チームは、Microsoft Edge DevTools の改善に進みます。  Devtools の**フィードバック**アイコンを選択するか、または `Alt` + `Shift` + `I` (macOS の場合は) Windows を押して、 `Option` + `Shift` + `I` devtools のフィードバックまたは機能のリクエストを入力します。  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge についてフィードバックを送信する":::
   Microsoft Edge についてフィードバックを送信する  
:::image-end:::  

[DevTools の最新機能][DevtoolsGuideChromiumWhatsNewIndex]をプレビューする場合は、夜間にビルドされた[Microsoft Edge カナリア][MicrosoftedgeinsiderDownload]をダウンロードしてください。  

<!-- image links -->  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "初心者向けの DevTools: HTML と DOM の使用を開始する |Microsoft ドキュメント"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools "Microsoft Edge (Chromium) DevTools の新機能 |Microsoft ドキュメント"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools Protocol |Microsoft ドキュメント"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge アドオン"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "拡張子 |Chrome Web ストア"  
