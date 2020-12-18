---
description: Microsoft Edge (Chromium) 開発者ツールについて
title: Microsoft Edge (Chromium) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fcae8f0974244e87ba781b94221cb5d8a1bb3dce
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234380"
---
# Microsoft Edge (Chromium) 開発者ツールの概要  

Microsoft Edge では、Chromium オープン ソース プロジェクトを採用して、Web の互換性を向上し、異なる基盤となる Web プラットフォームの断片化を減らしています。  この変更により、Microsoft Edge で Web サイトを簡単に構築してテストし、それぞれが別の Chromium ベースのブラウザー \(Google Chrome、Vivaldi、Opera、または Brave\ など) で表示されている場合でも、それぞれにおいて期待通りに機能することを確認できます。  

デバイスの種類が拡大するにつれて、Web の利用も拡大し、Web サイトのテストに伴う複雑性とオーバーヘッドが大きく増加しました。 Web 開発者 \(特に小規模企業の開発者\) は、非常に多くの異なるシステムに対してテストを行う必要があるため、サイトがすべてのデバイスの種類とすべてのブラウザーで適切に動作することを確認するのは、ほぼ不可能に近いことです。  Microsoft Edge が Chromium に基づいているので、Microsoft Edge チームは、Microsoft Edge Web プラットフォームを他の Chromium ベースのブラウザーと一致することでマトリックスを簡略化し、ブラウザー内と、毎日使用する他の開発者ツール (Visual Studio Code\ など) の両方で、クラス最高の開発者ツール エクスペリエンスを実現しました。  

Microsoft Edge をチェック アウトしており、主に Chromium ベースのブラウザーで開発を行っている場合は、自宅にいるような安心感を感じることでしょう。  Microsoft Edge \(Chromium\) 開発者ツール は、既に使用している開発者ツールと同じように機能します。  詳細については [、Microsoft Edge (Chromium) DevTools の新機能に移動します][DevtoolsGuideChromiumWhatsNewIndex]。  

:::image type="complex" source="./media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools" lightbox="./media/devtools.png":::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

新しい Microsoft Edge をチェックアウトし、以前に Microsoft Edge \(EdgeHTML\) で開発した場合、Microsoft Edge での Web サイトのビルドとテストをより簡単かつ迅速に行える新しいツールがいくつか追加されました。  

## DevTools を開く  

DevTools を使用したことがない方のために説明しますと、Microsoft Edge 開発者ツールは、Microsoft Edge ブラウザーに直接組み込まれているツール セットです。  DevTools を使用すると、次の操作を実行できます。  

*   HTML Web サイトを検査して変更する  
*   CSS を編集し、Web サイトのレンダリング方法のプレビューを即座に確認する  
*   フロントエンド JavaScript コードから、すべての `console.log()` ステートメントを参照する  
*   ブレークポイントを設定し、1 行ずつステップ実行してスクリプトをデバッグする  
    
すべてはブラウザー内で直接行います。  これらは、Microsoft Edge で Web サイトを簡単かつ迅速に構築およびテストするために、DevTools が提供する機能の一部の例です。  

DevTools を開く方法  

*   選択する `F12` 
*   Select `Ctrl` + `Shift` + `I` on Windows/Linux \( `Command` + `Option` + `I` on macOS\)  
    
サイト上の要素の HTML または CSS を表示する場合は、要素を右クリックし、[**検査**] を選択して [要素] パネルに移動します。  Windows/Linux の場合、`Ctrl` + `Shift` + `C` を押す \(macOS の場合、`Command` + `Option` + `C` を押す\) と、を押して**要素の検査モード**で DevTools を開くと、サイト上の要素を選択し、**[要素]** パネルに HTML と CSS を表示することができます。  

フロントエンド JavaScript コードのログを表示する場合や、スクリプトをすばやく実行する場合は、Windows/Linux または macOS 上で選択して `Ctrl` + `Shift` + `J` `Command` + `Option` + `J` 、DevTools**** のコンソール パネルを起動します。  

## コア ツール  

:::image type="complex" source="./media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools コア ツール" lightbox="./media/devtools-core-tools.png":::
   Microsoft Edge (Chromium) DevTools コア ツール  
:::image-end::: 

Microsoft Edge \(Chromium\) DevTools には、次のパネルが含まれます。  

*   **要素** は、パネルHTML および CSS の編集、アクセシビリティのプロパティの検査、イベント リスナーの表示、DOM 変異のブレークポイントの設定を行います。  
*   **コンソール** は、ログ メッセージを表示およびフィルタリングし、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウやフレームのコンテキストでの JavaScript を実行します。  
*   コードを開いてライブ編集し、ブレークポイントを設定し、コードをステップ実行して、一度に 1 行の JavaScript だけでWeb サイトの状態を確認する**ソース** パネル  
*   **ネットワーク** パネルは、ネットワークとブラウザーのキャッシュからの要求や応答を監視および検査します。   
*   **パフォーマンス** パネルは、サイトに必要な時間とシステム リソースをプロファイルします。  
*   **メモリ** パネルは、メモリ リソースの使用状況を測定し、コード ランタイムの異なる状態でヒープ スナップショットを比較します。  
*   Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカーのキャッシュを検査、変更、デバッグする **[アプリケーション]** パネル。  **[アプリケーション]** パネルからストレージ、データベース、およびキャッシュを検査および管理することもできます。  
*   セキュリティの問題をデバッグし、Web サイトに HTTPS を適切に実装した **[セキュリティ]** パネル。  HTTPS は、サイトとサイト上に個人情報を入力するユーザーの両方に対して、重要なセキュリティとデータの整合性を提供します。  
*   Web サイトの監査を実行するために、**監査**パネル \(現在は **Lighthouse**\ という名前に変更されました)。  監査の結果は、次の方法でサイトの品質を向上させるのに役立ちます。  
    *   Web サイトのアクセス性、セキュリティ、パフォーマンスの確保に関連する一般的なエラーを発見します。  
    *   各エラーを修正します。  
    *   PWA を構築します。  
        
[!INCLUDE [audits-panel-note](./includes/audits-panel-note.md)]  

[フィードバックと機能のリクエスト](#getting-in-touch-with-the-microsoft-edge-devtools-team) を送信してください。  

## 拡張機能  

DevTools の拡張機能を使用して、Web サイトやアプリの構築時の問題を診断およびデバッグした可能性があります。  [Microsoft Edge アドオン][MicrosoftEdgeAddonsExtensions] ページから Microsoft Edge の拡張機能を取得できます。  [Microsoft Edge アドオン ページ][MicrosoftEdgeAddonsExtensions]から、**開発者ツール** カテゴリの DevTools 拡張機能を参照するか、特定の拡張機能を検索することができます。  

[Chrome Web ストア][GoogleChromeWebstoreExtensions]から拡張機能を追加することもできます。  

:::image type="complex" source="./media/allow-extensions-from-stores.png" alt-text="Microsoft Edge の Chrome Web ストア" lightbox="./media/allow-extensions-from-stores.png":::
   Microsoft Edge の Chrome Web ストア  
:::image-end:::  

上部にある [他のストア**からの拡張機能**を許可する] を**** 選択し、表示されるダイアログで [許可] を選択します。  

> [!NOTE]
> Microsoft Store 以外のソースからインストールされた拡張機能は未確認であり、ブラウザーのパフォーマンスに影響を与える可能性があります。  

[Chrome **に追加] を** 選択して、DevTools 拡張機能を Microsoft Edge に追加します。  

:::image type="complex" source="./media/install-extension-from-chrome-store.png" alt-text="Chrome Web ストアからの Microsoft Edge への拡張機能の追加" lightbox="./media/install-extension-from-chrome-store.png":::
   Chrome Web ストアからの Microsoft Edge への拡張機能の追加  
:::image-end:::  

## ショートカット  

これらのショートカットは、DevTools のメイン ウィンドウを制御するか、すべてのツールで機能するか、または両方を実行します。  

| Action | Windows/Linux | macOS |  
|:--- |:--- | :--- |  
| DevTools の表示/非表示 \(最後に表示されたパネルに表示される\) | `F12` または `Ctrl`+`Shift`+`I` | `Command`+`Option`+`I` |  
| コンソール パネルを表示する | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 要素の検査モードで**** DevTools を表示します。これにより、サイトで要素を選択し、[要素] パネルに HTML と CSS を**表示**できます。 | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| 設定の表示 | `?` または `Fn`+`F1` | `?` または `Fn`+`F1` |  
| 次のパネルを表示する | `Ctrl`+`]` | `Command`+`]` |  
| 前のパネルを表示する | `Ctrl`+`[` | `Command`+`[` |  
| DevTools を最後に使用した位置にドッキングします。  DevTools がセッション全体の既定の位置にとどまっている場合、ショートカットは DevTools を別のウィンドウにドッキング解除します。 | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| **デバイス モード**の切り替え | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| **[要素の検査モード] **に切り替えると、サイトで要素を選択し、**[要素]** パネルに HTML と CSS を表示することができます。 | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| コマンド メニューを表示する | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| ドロワーの表示/非表示 | `Esc` | `Esc` |  
| 更新。  キャッシュを使用してページを変更します。  | `F5` または `Ctrl`+`R` | `Command`+`R` |  
| ハードの更新。  Microsoft Edge にリソースの再ダウンロードと再読み込みを強制的に実行します。  使用されているリソースが、キャッシュされたバージョンから取得される可能性があります。 | `Ctrl`+`F5` または `Ctrl`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 現在のパネル内のテキストを検索します。  監査、アプリケーション、およびセキュリティ パネルではサポートされていません | `Ctrl`+`F` | `Command`+`F` |  
| ドロワーに検索パネルを表示すると、読み込まれたすべてのリソースでテキストを検索できます。 | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| ソース パネルでファイルを開く | `Ctrl`+`O` または `Ctrl`+`P` | `Command`+`O` または `Command`+`P` |  
| 拡大する | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 縮小 | `Ctrl`+`-` | `Command`+`-` |  
| 既定のズーム レベルを復元する | `Ctrl`+`0` | `Command`+`0` |  
| スニペットを実行する | `Ctrl`+`O` または `Ctrl` + `P`、スクリプト名の後に`!` を入力し、その後押します `Enter` | `Command` + `O` または `Command` + `P` を押し、スクリプト名の後に `!` を入力し、その後押します `Enter` |  
| 編集できない HTML ソース コードを新しいタブに表示する | `Ctrl`+`U` | 該当せず |  

> [!NOTE]
> デバッグ中にブレークポイントで一時停止している場合は、最初に**更新**ショートカットがランタイムを再開します。  

## 関連項目  

*   [初級向け DevTools: HTML と DOM の使用を開始する][DevtoolsGuideChromiumBeginnersHtml]  
*   [Microsoft Edge (Chromium) DevTools プロトコル][DevtoolsProtocolChromiumIndex]  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

近々ある [DevTools][DevtoolsGuideChromiumWhatsNewIndex] の最新の機能をプレビューする場合は、毎晩ビルドされる [Microsoft Edge Canary][MicrosoftedgeinsiderDownload] をダウンロードします。  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "初級向け DevTools: HTML と DOM の使用を開始する | Microsoft Docs"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/11/devtools "Microsoft Edge (Chromium) DevTools の新機能 | Microsoft Docs"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools プロトコル | Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge アドオン"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channelsをダウンロードする"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "拡張機能 | Chrome Web ストア"  
