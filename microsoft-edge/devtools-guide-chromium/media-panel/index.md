---
description: メディア パネルを使って、ブラウザー タブごとに情報を表示し、メディア プレーヤーをデバッグします。
title: メディア プレーヤー情報の表示とデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e6259cf573b76df7e281527ad30360b8f473a165
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230951"
---
# メディア プレーヤー情報の表示とデバッグ  

Microsoft **** Edge DevTools のメディア パネルを使用して、ブラウザータブごとに情報を表示し、メディア プレーヤーをデバッグします。  

## メディア パネルを開く  

メディア **パネル** は、Web ページのメディア プレーヤーを検査する DevTools の主要な場所です。

1.  [DevTools を開きます][DevtoolsGuideChromiumOpen]。  
1.  メディア パネルを開**く場合**は **、[DevTools** More tools Media のカスタマイズと制御 `...`  >  **] を選択**  >  **します**。  
    
    :::image type="complex" source="../media/media-panel-empty.msft.png" alt-text="メディア パネル" lightbox="../media/media-panel-empty.msft.png":::
       **メディア** パネル  
    :::image-end:::  
    
## メディア プレーヤー情報の表示  

1.  次の Web ページなど、メディア プレーヤーを使用して Web ページに移動します。  
    
    [エッジ開発者ツールによる生産性の最大化][BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]  
    
1.  [ **プレイヤー] メニュー** の下に、メディア プレーヤーが表示されます。  
1.  プレイヤーを選択します。  [ **プロパティ]** タブには、メディア プレーヤーのプロパティが表示されます。  
    
    :::image type="complex" source="../media/media-panel-view.msft.png" alt-text="メディア プロパティ" lightbox="../media/media-panel-view.msft.png":::
       メディア プロパティ  
    :::image-end:::  
    
1.  すべてのメディア プレーヤー イベントを表示するには、[イベント] タブ **を選択** します。  
    
    :::image type="complex" source="../media/media-panel-events.msft.png" alt-text="メディア イベント" lightbox="../media/media-panel-events.msft.png":::
       メディア イベント  
    :::image-end:::  
    
1.  メディア プレーヤーのメッセージ ログを表示するには、[メッセージ] タブ **を選択** します。 メッセージはログ レベルまたは文字列でフィルター処理できます。  
    
    :::image type="complex" source="../media/media-panel-messages.msft.png" alt-text="メディア メッセージ" lightbox="../media/media-panel-messages.msft.png":::
       メディア メッセージ  
    :::image-end:::  
    
1.  [ **タイムライン] タブ** では、メディアの再生とバッファーの状態がライブで表示されます。  
    
    :::image type="complex" source="../media/media-panel-timeline.msft.png" alt-text="メディアのタイムライン" lightbox="../media/media-panel-timeline.msft.png":::
       メディアのタイムライン  
    :::image-end:::  
    
### リモート デバッグ  

Windows または macOS コンピューターから Android デバイスのメディア プレーヤー情報を表示します。  

1.  リモート デバッグをセットアップするには、Android デバイスのリモート デバッグの [開始に移動します][DevtoolsGuideChromiumRemoteDebuggingIndex]。  
1.  メディア プレーヤーの情報をリモートで表示します。  
    
    <!-- TODO: recreate image using an Android device -->  
    <!--  
    :::image type="complex" source="../media/media-panel-remote-debug.msft.png" alt-text="Remote debugging" lightbox="../media/media-panel-remote-debug.msft.png":::
       Remote debugging  
    :::image-end:::  
    -->  
    
## メディア プレーヤーの非表示と表示  

1 つの Web ページで複数のメディア プレーヤーを実行したり、同じブラウザー タブを使用して異なる Web ページを参照したり、メディア プレーヤーが表示される場合があります。

デバッグを容易にするために、各メディア プレーヤーを \(または show\) 非表示にできます。  

1.  同じブラウザー タブを使用して、複数の異なるビデオ Web ページを参照します。  
1.  メディア プレーヤーを非表示にする場合は、次のいずれかの操作を実行します。  
    *   1 つのメディア プレーヤーを非表示にする場合は、メディア プレーヤーをポイントし、コンテキスト メニュー \(右クリック\) を開き、[プレイヤーを非表示にする] **を選択します**。  
    *   他のすべてのメディア プレーヤーを非表示にする場合は、メディア プレーヤーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[他のすべてのメディア プレーヤーを非表示にする] を選択 **します**。  
    
    :::image type="complex" source="../media/media-panel-hide-show.msft.png" alt-text="メディア プレーヤーを非表示にする" lightbox="../media/media-panel-hide-show.msft.png":::
       メディア プレーヤーを非表示にする  
    :::image-end:::  
    
## メディア プレーヤー情報のエクスポート  

1.  メディア プレーヤーの情報を JSON ファイルとしてダウンロードするには、メディア プレーヤーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[プレイヤー情報の保存] を **選択します**。  
    
    :::image type="complex" source="../media/media-panel-save.msft.png" alt-text="メディア情報のエクスポート" lightbox="../media/media-panel-save.msft.png":::
       メディア情報のエクスポート  
    :::image-end:::  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "Microsoft Edge (Chromium) DevTools を開く |Microsoft Docs"  

[DevtoolsGuideChromiumRemoteDebuggingIndex]: ../remote-debugging/index.md "Android デバイスのリモート デバッグの概要 |Microsoft Docs"  

[BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]: https://www.bing.com/videos/search?view=detail&mid=DE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8 "エッジ開発者ツールを使用して生産性を最大化する |Bing ビデオ"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/tools/chrome-devtools/media-panel/index)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

