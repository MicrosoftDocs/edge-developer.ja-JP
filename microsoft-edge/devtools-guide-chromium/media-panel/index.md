---
description: メディア ツールを使用して、情報を表示し、ブラウザータブごとにメディア プレーヤーをデバッグします。
title: メディア プレーヤーの情報を表示およびデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7680faa13f65a2ea6f0a8b085316b5ed67bfdaba
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398407"
---
<!-- Copyright Jecelyn Yeen

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <a name="view-and-debug-media-players-information"></a>メディア プレーヤーの情報を表示およびデバッグする  

Microsoft Edge **DevTools** のメディア ツールを使用して、情報を表示し、ブラウザータブごとにメディア プレーヤーをデバッグします。  

## <a name="open-the-media-tool"></a>メディア ツールを開く  

メディア **ツール** は、Web ページのメディア プレーヤーを検査する DevTools の主要な場所です。

1.  [DevTools を開きます][DevtoolsGuideChromiumOpen]。  
1.  [メディア] パネル**を開く**場合は **、[DevTools のその他のツールメディアのカスタマイズと制御** `...`  >  **] を**  >  **選択します**。  
    
    :::image type="complex" source="../media/media-panel-empty.msft.png" alt-text="メディア パネル" lightbox="../media/media-panel-empty.msft.png":::
       **メディア** パネル  
    :::image-end:::  
    
## <a name="view-media-players-information"></a>メディア プレーヤーの情報を表示する  

1.  次の Web ページなどのメディア プレーヤーを含む Web ページに移動します。  
    
    [エッジ開発者ツールによる生産性の最大化][BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]  
    
1.  [プレイヤー **] メニュー** の下に、メディア プレーヤーが表示されます。  
1.  プレイヤーを選択します。  [ **プロパティ]** パネルには、メディア プレーヤーのプロパティが表示されます。  
    
    :::image type="complex" source="../media/media-panel-view.msft.png" alt-text="メディア プロパティ" lightbox="../media/media-panel-view.msft.png":::
       メディア プロパティ  
    :::image-end:::  
    
1.  すべてのメディア プレイヤー イベントを表示するには、[イベント] パネル **を選択** します。  
    
    :::image type="complex" source="../media/media-panel-events.msft.png" alt-text="メディア イベント" lightbox="../media/media-panel-events.msft.png":::
       メディア イベント  
    :::image-end:::  
    
1.  メディア プレーヤーのメッセージ ログを表示するには、[メッセージ] パネル **を選択** します。  ログ レベルまたは文字列でメッセージをフィルター処理できます。  
    
    :::image type="complex" source="../media/media-panel-messages.msft.png" alt-text="メディア メッセージ" lightbox="../media/media-panel-messages.msft.png":::
       メディア メッセージ  
    :::image-end:::  
    
1.  [タイムライン **] パネル** では、メディアの再生とバッファーの状態がライブで表示されます。  
    
    :::image type="complex" source="../media/media-panel-timeline.msft.png" alt-text="メディアタイムライン" lightbox="../media/media-panel-timeline.msft.png":::
       メディアタイムライン  
    :::image-end:::  
    
### <a name="remote-debugging"></a>リモート デバッグ  

Windows または macOS コンピューターから Android デバイスのメディア プレーヤー情報を表示します。  

1.  リモート デバッグを設定するには、[Android デバイスのリモート デバッグの開始 [] に移動します][DevtoolsGuideChromiumRemoteDebuggingIndex]。  
1.  メディア プレーヤーの情報をリモートで表示します。  
    
    <!-- TODO: recreate image using an Android device -->  
    <!--  
    :::image type="complex" source="../media/media-panel-remote-debug.msft.png" alt-text="Remote debugging" lightbox="../media/media-panel-remote-debug.msft.png":::
       Remote debugging  
    :::image-end:::  
    -->  
    
## <a name="hide-and-show-media-players"></a>メディア プレーヤーの非表示と表示  

Web ページで複数のメディア プレーヤーを実行する場合や、同じブラウザー タブを使用して異なる Web ページを参照する場合があります。各 Web ページはメディア プレーヤーを使用します。

デバッグを容易にするために、各メディア プレーヤーを \(または show\) を非表示にできます。  

1.  同じブラウザー タブを使用して、複数の異なるビデオ Web ページを参照します。  
1.  メディア プレーヤーを非表示にする場合は、次のいずれかの操作を実行します。  
    *   1 つのメディア プレーヤーを非表示にする場合は、メディア プレーヤーにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[プレイヤーを非表示にする] **を選択します**。  
    *   他のすべてのメディア プレーヤーを非表示にする場合は、メディア プレーヤーにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[他のすべてのメディア プレーヤーを非表示にする] を **選択します**。  
    
    :::image type="complex" source="../media/media-panel-hide-show.msft.png" alt-text="メディア プレーヤーを非表示にする" lightbox="../media/media-panel-hide-show.msft.png":::
       メディア プレーヤーを非表示にする  
    :::image-end:::  
    
## <a name="export-media-player-information"></a>メディア プレーヤー情報のエクスポート  

1.  メディア プレーヤー情報を JSON ファイルとしてダウンロードするには、メディア プレーヤーにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[プレイヤー情報の保存] を **選択します**。  
    
    :::image type="complex" source="../media/media-panel-save.msft.png" alt-text="メディア情報のエクスポート" lightbox="../media/media-panel-save.msft.png":::
       メディア情報のエクスポート  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "Microsoft Edge (クロム) DevTools ファイルを開|Microsoft Docs"  

[DevtoolsGuideChromiumRemoteDebuggingIndex]: ../remote-debugging/index.md "Android デバイスのリモート デバッグの開始|Microsoft Docs"  

[BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]: https://www.bing.com/videos/search?view=detail&mid=DE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8 "エッジ開発者ツール を使用して生産性を最大化|Bing ビデオ"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/tools/chrome-devtools/media-panel/index)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

