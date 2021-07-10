---
description: IE モードと Microsoft Edge (Chromium) DevTools
title: Internet Explorerと DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, ie11, internet explorer 11, ie mode
ms.openlocfilehash: 070bf970c784b4f2173ebc52e4494fc6807b4a8e
ms.sourcegitcommit: 7cba715ef71cbac4ee0ebe8f07c0c0e4a2c64221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643236"
---
# <a name="internet-explorer-mode-and-the-devtools"></a>Internet Explorerと DevTools  

この記事では、Internet Explorer \(IE モード\) を \(Chromium\Microsoft Edge) DevTools と統合する方法について説明します。  

## <a name="understanding-ie-mode"></a>IE モードについて  

IE モードを使用すると、企業は 11 でしか動作しない web サイトのInternet Explorerできます。  Microsoft Edge \(Chromium\) でこれらの Web サイトに移動すると、Internet Explorer 11 のインスタンスが実行され、サイトがタブに表示されます。 この機能により、企業は現在最新の Web ブラウザーと互換性がないテクノロジとの互換性を管理できます。  IE モードでは、次のテクノロジのサポートが含まれています。  

*   IE ドキュメント モード  
*   ActiveX コントロール  
*   その他の従来のコンポーネント  

IE モードでは、レンダリング プロセスは 11 のInternet Explorerされます。  Microsoft Edge \(Chromium\) プロセス マネージャーは、レンダリング プロセスの有効期間を処理します。  特定のサイト \(または app\) のタブの有効期間に制限されます。  タブが IE モードでレンダリングされる場合、特定のタブのアドレス バーにバッジが表示されます。  

:::image type="complex" source="../media/ie-mode-badge.msft.png" alt-text="アドレス バーの IE モード バッジ" lightbox="../media/ie-mode-badge.msft.png":::
   アドレス バーの IE モード バッジ  
:::image-end:::  

IE モードは現在、Windows 10 バージョン 1903 \(May 2019 Update\) で使用可能ですが、サポートされているすべてのプラットフォームWindows予定です。  

## <a name="launching-the-devtools-on-a-tab-in-ie-mode"></a>IE モードでタブで DevTools を起動する  

IE モードで Web サイトのドキュメント モードを表示する場合は、アドレス バーでバッジを選択します。  

:::image type="complex" source="../media/ie-mode-badge-doc-mode.msft.png" alt-text="IE モード バッジを使用してドキュメント モードを表示する" lightbox="../media/ie-mode-badge-doc-mode.msft.png":::
   IE モード バッジを使用してドキュメント モードを表示する  
:::image-end:::  

タブが IE モードを使用している場合、DevTools は動作し、次の条件が発生します。

*   選択または選択 `F12` した場合 `Ctrl` + `Shift` + `I` は Microsoft Edge、\(Chromium\) DevTools が起動された場合、\(Chromium\) の空白のインスタンスが表示されます。  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   コンテキスト メニュー \(右クリック\) を開き、[**** ソースの表示] を選択すると、メモ帳されます。  
*   コンテキスト メニュー \(右クリック\) を開いた場合 **、Inspect 要素は** 表示されません。  

DevTools \(Network and **Performance tools\**など)**** 内の多くのツールが機能しない理由は、レンダリング エンジンが IE モードで Chromium から Internet Explorer 11 に切り替わるからです。  フィードバックを提供するには[、DevTools チームと連絡を取るMicrosoft Edge移動します](#getting-in-touch-with-the-microsoft-edge-devtools-team)。  

:::image type="complex" source="../media/ie-mode-devtools.msft.png" alt-text="IE モードで起動された DevTools" lightbox="../media/ie-mode-devtools.msft.png":::
   IE モードで起動された DevTools  
:::image-end:::  

11 Internet Explorer 11 および IE モードで 11 ベースの web サイト \(または app\) をInternet Explorerするには、次の手順を実行します。  

1.  11 Internet Explorer開きます。  
    *   [Windows 10 11] のショートカットをInternet Explorerします。
        1.  **[スタート] メニュー**  > **Windowsアクセサリ**  > **Internet Explorer 11**.  
    *   [Windows 7] で、[11] Internet Explorer探します。
        1.  **[スタート] メニュー**  > **Internet Explorer 11**.  
1.  [Internet Explorer 11] で、同じ Web ページを開きます。  
1.  DevTools Internet Explorer起動します。  
    *   `F12` を選択します。  
    *   任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[Inspect 要素] **を選択します**。  これらのツールの使用方法の詳細については、「F12 開発者ツールを使用する [」に移動します][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]。  

Windows 11 など、Windows 11 で 11 を使用できない場合は、IEChooser を使用して Internet Explorer DevTools を起動して、IE モード タブのコンテンツをデバッグできます。 Internet Explorer IEChooser を使用するには、次の手順を実行します。

1.  IEChooser を開きます。
    1. [ファイル名を指定して実行] ダイアログ ボックスを開きます。 たとえば、 を押 `Windows logo key`  +  `R` します。
    2. を `%systemroot%\system32\f12\IEChooser.exe` 入力し **、[OK] を選択します**。
2.  IEChooser で、[IE モード] タブのエントリを選択します。


## <a name="remote-debugging-and-ie-mode"></a>リモート デバッグと IE モード  

コマンド Microsoft Edgeからリモート デバッグを有効Chromium\(Chromium\) を起動します。  Microsoft Visual Studio、Microsoft Visual Studioコード、その他の開発ツールは通常、コマンドを実行してコマンドを起動Microsoft Edge。  次のコマンドは、リモート デバッグ Microsoft Edgeに設定されたコマンドを起動します `9222` 。  

```shell
start msedge --remote-debugging-port=9222
```  

コマンド ライン引数Microsoft Edge \(Chromium\) を起動すると、IE モードは使用できません。  IE モードで表示される Web サイト \(または apps\) に移動することもできます。  Web サイト \(または app\) コンテンツは、11 ではなく、ChromiumをInternet Explorerします。  IE11 に依存する web ページの部分 (ActiveXなど) が正しく表示されないと予想します。  IE モード バッジはアドレス バーに表示されません。  

\(Chromium\) を完全に閉じて再起動するまで、IE モードはMicrosoft Edge使用できません。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "F12 開発者ツールを使用|Microsoft Docs"  
