---
description: F12 Developer Tools では、拡張機能のバックグラウンド スクリプト、コンテンツ スクリプト、および拡張ページをデバッグする方法について説明します。
title: デバッグ|拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, javascript, developer, debug, debuging
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a23c7558080cca7671cdfc9790705a8d8c9ed705
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399366"
---
# <a name="debugging-extensions"></a>拡張機能のデバッグ  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

F12 Developer Tools を使用して、Microsoft Edge で拡張機能をデバッグできます。  

次のビデオでは、バグのある Microsoft Edge 拡張機能を使用して、各デバッグ シナリオを実行し、途中で修正します。  詳細については、以下の手順を参照してください。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Debugging-Microsoft-Edge-Extensions/player]  

> [!NOTE]
> F12 で拡張機能のデバッグを利用するには、まず about:flags で開発者機能を有効にする必要があります。  この [方法の詳細については、「拡張機能の追加](./adding-and-removing-extensions.md) と削除」を参照してください。  

## <a name="background-script-debugging"></a>バックグラウンド スクリプトのデバッグ  

拡張機能のバックグラウンド スクリプトのデバッグを開始するには、次のコマンドを実行します。  

1.  [詳細 **] (...)** の後に [拡張機能] **をクリックして** 、拡張機能ウィンドウに移動します。  
    
    ![[その他] ボタン](../media/morebutton.png)  
    
1.  デバッグする拡張機能をクリックします。  
1.  [背景] **ページリンクをクリック** して、バックグラウンド プロセスの F12 を表示します。  
    
    ![[検査] リンクを含むオプションの選択された拡張機能ビュー](../media/debug-inspect.png)  
    
1.  F12 **の [** デバッガー] タブを選択します。  
1.  拡張機能のバックグラウンド スクリプトに移動して選択します。  
1.  ソース コード行番号の左側をクリックして、デバッグ用のブレークポイントを配置します。  
    
    ![f12 コンソールに、ブレーク ポイントを含むバックグラウンド スクリプトを表示する](../media/debug-f12-background.png)  
    
1.  [コンソール] **タブを** 選択し、コマンドを `location.reload()` 実行します。  これにより、バックグラウンド スクリプトが再び実行され、コードをステップ実行できます。  
    
    ![location.reload が入力されたコンソール](../media/debug-f12-background-console.png)  
    
## <a name="content-script-debugging"></a>コンテンツ スクリプトのデバッグ  

拡張機能のコンテンツ スクリプトのデバッグを開始するには、次のコマンドを実行します。  

1.  [詳細] **(....)** ボタンに移動し **、[F12 Developer Tools]** を選択するか、キーボードを押して F12 `F12` を起動します。  
1.  拡張機能のコンテンツ スクリプトに移動して選択します。  現在実行されている拡張機能のコンテンツ スクリプトは、拡張機能ごとに異なるフォルダーで表示されます。  
    
    > [!NOTE]
    > 実行中のコンテンツ スクリプトだけが表示されます。  
    
1.  ソース コード行番号の左側をクリックして、デバッグ用のブレークポイントを配置します。  
    
    ![コンテンツ スクリプトがデバッグされている f12](../media/debug-content-f12.png)  
    
1.  ブラウザー タブを更新して、コードのステップ実行を開始します。  
    
## <a name="extension-page-debugging"></a>拡張ページのデバッグ  

拡張ページのソース コードにアクセスしてデバッグするために使用できる方法は 2 種類あります。  1 つのメソッドは、さまざまなページに適用されます。もう 1 つはポップアップ ページでのみ機能します。  

### <a name="debugging-any-extension-page"></a>拡張ページのデバッグ  

次のメソッドは、オプション ページやポップアップなど、すべての拡張ページで機能します。  

1.  ページの背景を右クリックします。  
1.  [ソース **の表示] を選択します**。  
    
    ![ポップアップ デバッグを f12 で開く](../media/debug-popup-select.png)  
    
1.  F12 が開いたら、デバッグするファイル内にブレークポイントを配置します。  
    
    ![f12 を使用したポップアップ デバッグ](../media/debug-popup-f12.png)  
    
1.  [コンソール] **タブを** 選択し、コマンドを実行します `location.reload()` 。  これにより、ページ スクリプトが再び実行され、コードをステップ実行できます。  
    
    ![location.reload が入力されたコンソール](../media/debug-f12-background-console.png)  
    
### <a name="debugging-a-popup-extension-page"></a>ポップアップ拡張機能ページのデバッグ  

拡張ページのデバッグ方法は、ポップアップ拡張ページにも適用されます。次の手順では、ポップアップをデバッグする別の方法について説明します。  

1.  拡張機能のアイコンを右クリックします。  
1.  [ポップアップ **の検査] を選択します**。  
    
    ![ポップアップ デバッグの検査](../media/debug-popup-inspect.png)  
    
1.  ブレークポイントを配置し、ポップアップを再読み込みするには、上記の手順 3 と 4 に従います。  
    