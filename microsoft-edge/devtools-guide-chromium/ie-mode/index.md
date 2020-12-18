---
description: IE モードと Microsoft Edge (Chromium) DevTools
title: Internet Explorerモードと DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Microsoft Edge, Web 開発, f12 ツール, devtools, ie11, internet explorer 11, ie モード
ms.openlocfilehash: c88da78e073a75a664561aba899ca5c8ada78477
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234379"
---
# Internet Explorerモードと DevTools  

この記事では、Internet Explorer \(IE mode\) を Microsoft Edge \(Chromium\) DevTools と統合する方法について説明します。  

## IE モードについて  

IE モードでは、企業は 11 か月 11 日にのみ動作する Web サイトのInternet Explorerできます。  Microsoft Edge \(Chromium\) でこれらの Web サイトに移動すると、Internet Explorer 11 のインスタンスが実行され、サイトがタブに表示されます。 この機能により、企業は現在、最新の Web ブラウザーと互換性がないテクノロジとの互換性を管理できます。  次のテクノロジのサポートは、IE モードに含まれています。  

*   IE ドキュメント モード  
*   ActiveX コントロール  
*   その他のレガシ コンポーネント  

IE モードでは、レンダリング プロセスは 11 Internet Explorerされます。  Microsoft Edge \(Chromium\) プロセス マネージャーは、レンダリング プロセスの有効期間を処理します。  これは、特定のサイト \(または app\) のタブの有効期間に制限されます。  タブが IE モードでレンダリングされる場合、特定のタブのアドレス バーにバッジが表示されます。  

:::image type="complex" source="../media/ie-mode-badge.msft.png" alt-text="アドレス バーの IE モード バッジ" lightbox="../media/ie-mode-badge.msft.png":::
   アドレス バーの IE モード バッジ  
:::image-end:::  

IE モードは現在、Windows 10 バージョン 1903 \(May 2019 Update\) で利用できますが、サポートされている Windows プラットフォームはすべて近日公開される予定です。  

## IE モードのタブで DevTools を起動する  

WEB サイトのドキュメント モードを IE モードで表示する場合は、アドレス バーでバッジを選択します。  

:::image type="complex" source="../media/ie-mode-badge-doc-mode.msft.png" alt-text="IE モード バッジを使ったドキュメント モードの表示" lightbox="../media/ie-mode-badge-doc-mode.msft.png":::
   IE モード バッジを使ったドキュメント モードの表示  
:::image-end:::  

タブが IE モードを使用している場合、DevTools は動作しなく、次の条件が発生します。

*   選択または選択 `F12` すると `Ctrl` + `Shift` + `I` 、Microsoft Edge \(Chromium\) DevTools の空のインスタンスが起動すると、次のメッセージが表示されます。  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   コンテキスト メニュー \(右クリック\) を開き、[ソースの表示] を選択 **すると、メモ**帳が起動します。  
*   コンテキスト メニュー \(右クリック\) を開いた場合 **、Inspect 要素** は表示されません。  

DevTools \(Network **and** **Performance** tools\) 内の多くのツールが動作しない理由は、レンダリング エンジンが IE モードで Chromium から Internet Explorer 11 に切り替わるという点です。  フィードバックを提供するには [、Microsoft Edge DevTools](#getting-in-touch-with-the-microsoft-edge-devtools-team)チームと連絡を取る方法に移動します。  

:::image type="complex" source="../media/ie-mode-devtools.msft.png" alt-text="IE モードで起動された DevTools" lightbox="../media/ie-mode-devtools.msft.png":::
   IE モードで起動された DevTools  
:::image-end:::  

Internet Explorer 11 Internet Explorer IE モードで 11 ベースの Web サイト \(または app\) をテストするには、次の手順を実行します。  

1.  Internet Explorer 11 を開きます。  
    *   Windows 10 で、Windows 11 のショートカットInternet Explorerします。
        1.  **[スタート] メニュー**  > **Windows アクセサリ**  > **Internet Explorer 11**.  
    *   Windows 7 で、11 をInternet Explorerします。
        1.  **[スタート] メニュー**  > **Internet Explorer 11**.  
1.  このInternet Explorer 11 で、同じ Web ページを開きます。  
1.  DevTools Internet Explorer起動します。  
    *   `F12` を選択します。  
    *   任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き **、Inspect 要素を選択します**。  これらのツールの使い方について詳しくは [、「F12][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]開発者ツールの使用」をご覧ください。  

## リモート デバッグと IE モード  

コマンド ライン インターフェイスからリモート デバッグを有効にした状態で Microsoft Edge \(Chromium\) を起動します。  Visual Studio、Visual Studio、および他の開発ツールは、通常、Microsoft Edge を起動するコマンドを実行します。  次のコマンドは、リモート デバッグ ポートを設定して Microsoft Edge を起動します `9222` 。  

```shell
start msedge --remote-debugging-port=9222
```  

コマンド ライン引数を使って Microsoft Edge \(Chromium\) を起動すると、IE モードは使用できません。  IE モードで表示される Web サイト \(またはアプリ\) に移動することもできます。  Web サイト \(または app\) コンテンツは、11 ではなく Chromium をInternet Explorerします。  IE11 に依存する Web ページの部分 (ActiveXなど) が正しくレンダリングされない可能性があります。  IE モード バッジがアドレス バーに表示されません。  

Microsoft Edge \(Chromium\) を完全に閉じて再起動するまで、IE モードは使用できません。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "F12 開発者ツールを使用する |Microsoft Docs"  
