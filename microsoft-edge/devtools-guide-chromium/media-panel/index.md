---
description: メディアパネルを使用して情報を表示し、[ブラウザー] タブごとにメディアプレーヤーをデバッグします。
title: メディアプレーヤー情報を表示してデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: dfcf17861c0296e347007bc3a1a02a2b80661e6f
ms.sourcegitcommit: 912609aa49864e3363aaa3b245ff2aa4bec3fc3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11105204"
---
# メディアプレーヤー情報を表示してデバッグする  

Microsoft Edge DevTools の **メディア** パネルを使用して、情報を表示し、ブラウザータブごとにメディアプレーヤーをデバッグします。  

## メディアパネルを開く  

**メディア**パネルは、web ページのメディアプレーヤーを調べるための devtools の主要な場所です。

1.  [DevTools を開き][DevtoolsGuideChromiumOpen]ます。  
1.  **メディア**パネルを開くには、[カスタマイズ] を選択し、[ **devtools** `...`  >  **その他のツール**  >  **メディア**] をコントロールします。  
    
    :::image type="complex" source="../media/media-panel-empty.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-empty.msft.png":::
       **メディア** パネル  
    :::image-end:::  
    
## メディアプレーヤー情報の表示  

1.  次の web ページのように、メディアプレーヤーを使用して web ページに移動します。  
    
    [Microsoft Edge 開発者ツールを使用した生産性の最大化][BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]  
    
1.  [ **プレーヤー** ] メニューには、メディアプレーヤーが表示されます。  
1.  プレーヤーを選択します。  [ **プロパティ** ] タブには、メディアプレーヤーのプロパティが表示されます。  
    
    :::image type="complex" source="../media/media-panel-view.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-view.msft.png":::
       メディアのプロパティ  
    :::image-end:::  
    
1.  メディアプレーヤーのイベントをすべて表示するには、[ **イベント** ] タブを選択します。  
    
    :::image type="complex" source="../media/media-panel-events.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-events.msft.png":::
       メディアイベント  
    :::image-end:::  
    
1.  メディアプレーヤーのメッセージログを表示するには、[ **メッセージ** ] タブを選びます。 ログレベルまたは文字列でメッセージをフィルター処理することができます。  
    
    :::image type="complex" source="../media/media-panel-messages.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-messages.msft.png":::
       メディアメッセージ  
    :::image-end:::  
    
1.  [ **タイムライン** ] タブでは、メディアの再生とバッファーの状態がライブで表示されます。  
    
    :::image type="complex" source="../media/media-panel-timeline.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-timeline.msft.png":::
       メディアタイムライン  
    :::image-end:::  
    
### リモート デバッグ  

Windows または macOS コンピューターから Android デバイスでメディアプレーヤー情報を表示します。  

1.  リモートデバッグをセットアップするには、「 [リモートデバッグの Android デバイスの使用を開始][DevtoolsGuideChromiumRemoteDebuggingIndex]する」に移動します。  
1.  メディアプレーヤー情報をリモートで表示します。  
    
    <!-- TODO: recreate image using an Android device -->  
    <!--  
    :::image type="complex" source="../media/media-panel-remote-debug.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-remote-debug.msft.png":::
       Remote debugging  
    :::image-end:::  
    -->  
    
## メディアプレーヤーの表示と非表示を切り替える  

複数のメディアプレーヤーを web ページで実行している場合、または同じブラウザーのタブを使用して別の web ページを参照している場合があります。それぞれのメディアプレーヤーを使用します。

簡単なデバッグエクスペリエンスを実現するために、各メディアプレーヤーを非表示にすることができます。  

1.  同じブラウザータブを使用して、複数の異なるビデオ web ページを参照します。  
1.  メディアプレーヤーを非表示にするには、次のいずれかの操作を実行します。  
    *   1つのメディアプレーヤーを非表示にするには、メディアプレーヤーにマウスポインターを合わせて、コンテキストメニューを開き (\ を右クリックし)、[ **プレーヤーを表示**しない] を選びます。  
    *   他のすべてのメディアプレーヤーを非表示にするには、メディアプレーヤーにマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開いて、[ **すべてのユーザーを表示**しない] を選びます。  
    
    :::image type="complex" source="../media/media-panel-hide-show.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-hide-show.msft.png":::
       メディアプレーヤーを非表示にする  
    :::image-end:::  
    
## メディアプレーヤー情報をエクスポートする  

1.  メディアプレーヤー情報を JSON ファイルとしてダウンロードするには、メディアプレーヤーにマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[ **プレーヤーの情報を保存**] を選択します。  
    
    :::image type="complex" source="../media/media-panel-save.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-save.msft.png":::
       メディア情報をエクスポートする  
    :::image-end:::  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "Microsoft Edge DevTools を開く"  

[DevtoolsGuideChromiumRemoteDebuggingIndex]: ../remote-debugging/index.md "Android デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  

[BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]: https://www.bing.com/videos/search?view=detail&mid=DE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8 "Microsoft Edge 開発者向けツールを使った生産性の最大化 |Bing ビデオ"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/media-panel/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

