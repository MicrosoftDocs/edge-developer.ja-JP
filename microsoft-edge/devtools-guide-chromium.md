---
description: Microsoft Edge (Chromium) 開発者ツールについて理解する
title: Microsoft Edge (Chromium) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 50c4fa578ffa1738649496176cda2611625908b8
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125322"
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
*   `Ctrl` + `Shift` + `I` Windows/Linux \ ( `Command` + `Option` + `I` macOS) を押します。  

サイトの要素の HTML または CSS を表示する場合は、要素を右クリックして [ **検査** ] を選択し、[要素] パネルに移動します。  また、 `Ctrl` + `Shift` + `C` Windows/Linux \ ( `Command` + `Option` + `C` macOS で) を押して、[**要素の検査] モード**で、サイトの要素を選択し、[**要素**] パネルで HTML と CSS を表示することができます。  

フロントエンド JavaScript コードからログを表示したい場合、またはスクリプトをすばやく実行する場合は、 `Ctrl` + `Shift` + `J` Windows/Linux または macOS を押して、 `Command` + `Option` + `J` devtools のコンソールパネルを起動します。  

## コア ツール  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools":::
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

:::image type="complex" source="./devtools-guide-chromium/media/allow-extensions-from-stores.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   Microsoft Edge の Chrome Web ストア  
:::image-end:::  

上部で、[ **他のストアの拡張機能を許可する** ] を選択し、表示されるダイアログボックスで [ **許可** ] を選びます。  

> [!NOTE]
> Microsoft Store 以外のソースからインストールされた拡張機能は未確認であり、ブラウザーのパフォーマンスに影響する可能性があります。  

[ **Chrome に追加** ] を選択して、Microsoft Edge に devtools 拡張機能を追加します。  

:::image type="complex" source="./devtools-guide-chromium/media/install-extension-from-chrome-store.png" alt-text="Microsoft Edge (Chromium) DevTools"  
