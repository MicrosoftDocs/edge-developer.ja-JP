---
description: IE モードと Microsoft Edge (Chromium) DevTools
title: Internet Explorer モードと DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、ie11、internet explorer 11、ie モード
ms.openlocfilehash: b059cae3ff48a45fe92cbf69e37ad692e329b200
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "11003971"
---
# Internet Explorer モードと DevTools  

この記事では、Internet Explorer モード \ (IE モード \) と Microsoft Edge \ (Chromium \) DevTools との統合方法について説明します。  

## IE モードについて  

IE モードでは、組織は、Internet Explorer 11 でのみ機能する web サイトのリストを指定することができます。  Microsoft Edge \ (Chromium \) でこれらの web サイトに移動すると、Internet Explorer 11 のインスタンスが実行され、タブに表示されます。 この機能により、エンタープライズは最新の web ブラウザーと互換性のないテクノロジとの互換性を管理することができます。  次のテクノロジのサポートは、IE モードに含まれています。  

*   IE ドキュメントモード  
*   ActiveX コントロール  
*   その他のレガシコンポーネント  

IE モードでは、レンダリングプロセスは Internet Explorer 11 に基づいています。  Microsoft Edge \ (Chromium \) プロセスマネージャーは、レンダリング処理の有効期間を処理します。  特定のサイト \ (またはアプリ \) のタブの有効期間に制限されています。  タブが IE モードでレンダリングされると、特定のタブのアドレスバーにバッジが表示されます。  

:::image type="complex" source="./media/ie-mode-badge.msft.png" alt-text="アドレスバーの IE モードバッジ" lightbox="./media/ie-mode-badge.msft.png":::
   アドレスバーの IE モードバッジ  
:::image-end:::  

IE モードは現在、Windows 10 バージョン 1903 (2019 の更新プログラム \) で使用できますが、サポートされているすべての Windows プラットフォームに近い将来利用可能になります。  

## IE モードのタブで DevTools を起動する  

IE モードで web サイトのドキュメントモードを表示しようとしている場合は、アドレスバーでバッジを選択します。  

:::image type="complex" source="./media/ie-mode-badge-doc-mode.msft.png" alt-text="IE モードバッジを使用したドキュメントモードの表示" lightbox="./media/ie-mode-badge-doc-mode.msft.png":::
   IE モードバッジを使用したドキュメントモードの表示  
:::image-end:::  

タブが IE モードを使っている場合、DevTools は動作せず、次の条件が満たされます。

*   選択 `F12` または選択すると `Ctrl` + `Shift` + `I` 、Microsoft Edge \ (Chromium \) devtools の空のインスタンスが起動します。次のメッセージが表示されます。  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   コンテキストメニューを開くと (\ を右クリックし)、[ **ソースの表示**] を選択すると、メモ帳が起動します。  
*   コンテキストメニューを開くと (右クリック \)、 **検査要素** は表示されません。  

DevTools \ ( **Network** や **Performance** tools など) 内の多数のツールが動作しない理由は、Chromium から INTERNET Explorer 11 に IE モードで切り替えたときです。  フィードバックを提供するには、「 [Microsoft Edge DevTools チームに連絡する」](#getting-in-touch-with-the-microsoft-edge-devtools-team)に移動します。  

:::image type="complex" source="./media/ie-mode-devtools.msft.png" alt-text="IE モードで起動した DevTools" lightbox="./media/ie-mode-devtools.msft.png":::
   IE モードで起動した DevTools  
:::image-end:::  

Internet explorer 11 ベースの web サイト \ (またはアプリ \) を Internet Explorer 11 と IE モードでテストするには、次の手順を実行します。  

1.  Internet Explorer 11 を開きます。  
    *   Windows 10 では、Internet Explorer 11 のショートカットを見つけます。
        1.  **[スタート] メニュー**  > **Windows アクセサリ**  > **Internet Explorer 11**。  
    *   Windows 7 の場合は、Internet Explorer 11 を探します。
        1.  **[スタート] メニュー**  > **Internet Explorer 11**。  
1.  Internet Explorer 11 で、同じ web ページを開きます。  
1.  Internet Explorer DevTools を起動します。  
    *   を選択し `F12` ます。  
    *   任意の場所にマウスポインターを置いてコンテキストメニューを開き (\ を右クリックし)、[ **要素の検査**] を選びます。  これらのツールの使用方法の詳細については、「 [F12 開発者ツール][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]」を参照してください。  

## リモートデバッグと IE モード  

コマンドラインインターフェイスからリモートデバッグを有効にして、Microsoft Edge \ (Chromium \) を起動します。  通常、visual Studio、Visual Studio コード、および他の開発ツールは、Microsoft Edge を起動するためのコマンドを実行します。  次のコマンドは、リモートデバッグポートがに設定された Microsoft Edge を起動し `9222` ます。  

```shell
start msedge --remote-debugging-port=9222
```  

コマンドライン引数を使用して Microsoft Edge \ (Chromium \) を起動した後、IE モードは使用できません。  ただし、他の方法で表示される IE モードの web サイトに移動することができます。 Web サイト \ (またはアプリ \) コンテンツは、Internet Explorer 11 ではなく Chromium を使用してレンダリングされます。  ActiveX コントロールなど、IE11 に依存しているページの一部が正しく表示されないようにします。  IE モードのバッジはアドレスバーに表示されません。  

IE モードは、Microsoft Edge \ (Chromium \) を完全に閉じて再起動するまで使用できません。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "F12 開発者ツールを使用する |Microsoft ドキュメント"  