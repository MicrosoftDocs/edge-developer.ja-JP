---
title: Microsoft Edge DevTools でページリソースを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0977d0a9132c19742c3337f9dc0c3e1240508a3d
ms.sourcegitcommit: 4c24edbd1c591914cb4109511534851570a614cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611918"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  





# Microsoft Edge DevTools でページリソースを表示する   

  

このガイドでは、Microsoft Edge DevTools を使って web ページのリソースを表示する方法について説明します。  リソースは、適切に表示するためにページに必要なファイルです。  リソースの例として、CSS、JavaScript、HTML ファイル、画像などがあります。  

このガイドは、 [web 開発][MDNLearnWebDevelopment]と[Microsoft Edge devtools][MicrosoftEdgeDevTools]の基本について理解していることを前提としています。  

## リソースを開く   

検査するリソースの名前がわかっている場合、[**コマンド] メニュー**でリソースをすばやく開くことができます。  

1.  `Control` + `P` \ (Windows \) または `Command` + `P` \ (macOS \) を押します。  [**ファイルを開く**] ダイアログが開きます。  
    
    > ##### 図 1  
    > [**ファイルを開く**] ダイアログボックス  
    > ![[ファイルを開く] ダイアログボックス][ImageOpenFile]  
    
1.  ドロップダウンからファイルを選択するか、ファイル名の入力を開始し、[ `Enter` オートコンプリート] ボックスで正しいファイルが強調表示されたら、1回押します。  
    
    > ##### 図 2  
    > [**ファイルを開く**] ダイアログボックスにファイル名を入力する  
    > ![[ファイルを開く] ダイアログボックスにファイル名を入力する][ImageFileSearch]  
    
### [ネットワーク] パネルでリソースを開く   

「[リソースの詳細を調べる][DevtoolsNetworkInspectDetailsResource]」を参照してください。  

> ##### 図 3  
> [ネットワーク] パネルでリソースを検査する  
> ![[ネットワーク] パネルでリソースを検査する][ImageNetworkResponse]  

### [ネットワーク] パネルのリソースを他のパネルから公開する   

以下の「[リソースの参照](#browse-resources)」セクションでは、DEVTOOLS UI のさまざまな部分からリソースを表示する方法について説明します。  **ネットワーク**パネルでリソースを検査する場合は、リソースを右クリックして、[**ネットワークパネルで**表示] を選択します。  

> ##### 図 4  
> [**ネットワークパネルで**表示する] オプション  
> ![[ネットワーク] パネルでの表示][ImageRevealNetwork]  

## リソースを参照する   

### [ネットワーク] パネルでリソースを参照する   

「[ネットワークアクティビティのログ記録][DevtoolsNetworkLogActivity]」を参照してください。  

> ##### 図 5  
> ネットワークログのページリソース  
> ![ネットワークログのページリソース][ImageNetworkLog]  

### ディレクトリで参照   

ディレクトリごとに整理されたページのリソースを表示するには、次の操作を行います。  

1.  [**ソース**] タブをクリックして、[**ソース**] パネルを開きます。  
1.  [**ページ**] タブをクリックして、ページのリソースを表示します。  [**ページ**] ウィンドウが開きます。  
    
    > ##### 図 6  
    > **ページ**ウィンドウ  
    > ![ページウィンドウ][ImagePage]  
    
    [図 6](#figure-6)の明白でない項目の詳細を次に示します。  
    
    | ページアイテム | 説明 |  
    |:--- |:--- |  
    | `top` | メイン文書の[閲覧コンテキスト][MDNInlineFrame]。 |  
    | `airhorner.com` | ドメイン。  下位にあるすべてのリソースがそのドメインから取得されます。  たとえば、ファイルの完全な URL はおそらくのように `comlink.global.j` `https://airhorner.com/scripts/comlink.global.js` なります。 |  
    | `scripts` | ディレクトリ。 |  
    | `(index)` | メインの HTML 文書。 |  
    | `sw.js` | サービスワーカーランタイムコンテキスト。 |  
    
1.  リソースをクリックして**エディター**で表示します。  
    
    > ##### 図 7  
    > **エディター**でのファイルの表示  
    > ![エディターでのファイルの表示][ImageSourcesView]  
    
### ファイル名で参照   

既定では、**ページ**ウィンドウはディレクトリ別にリソースをグループ化します。  このグループ化を無効にして、各ドメインのリソースをフラットなリストとして表示するには、次の操作を行います。  

1.  **ページ**ウィンドウを開きます。  「[ディレクトリで参照」を](#browse-by-directory)参照してください。  
1.  [**その他のオプション**] をクリックし `...` て、[**グループ化**] を無効にします。  
    
    > ##### 図 8  
    > [**フォルダーでグループ化**] オプション  
    > ![[フォルダーでグループ化] オプション][ImageGroupByFolder]  
    
    リソースはファイルの種類別に整理されます。  各ファイルの種類では、リソースがアルファベット順に構成されています。  
    
    > ##### 図 9  
    > [**グループ化] フォルダーを**無効にした後の**ページ**ウィンドウ  
    > ![[グループ化] フォルダーを無効にした後のページウィンドウ][ImageFileNames]  
    
### ファイルの種類で参照する   

ファイルの種類に基づいてリソースをグループ化するには、次の操作を行います。  

1.  [**アプリケーション**] タブをクリックします。 **アプリケーション**パネルが開きます。  既定では、最初に**マニフェスト**ウィンドウが開きます。  
    
    > ##### 図 10  
    > **アプリケーション**パネル  
    > ![アプリケーションパネル][ImageApplication]  
    
1.  [**フレーム**] ウィンドウまで下にスクロールします。  
    
    > ##### 図 11  
    > [**フレーム**] ウィンドウ  
    > ![[フレーム] ウィンドウ][ImageFrames]  
    
1.  目的のセクションを展開します。  
1.  リソースをクリックして表示します。  
    
    > ##### 図 12  
    > **アプリケーション**パネルでのリソースの表示  
    > ![アプリケーションパネルでのリソースの表示][ImageApplicationView]  

#### [ネットワーク] パネルでファイルの種類を参照する   

「[リソースの種類でフィルター処理][DevtoolsNetworkFilterByResourceType]する」をご覧ください。  

> ##### 図 13  
> ネットワークログの CSS をフィルター処理する  
> ![ネットワークログの CSS をフィルター処理する][ImageCSS]  

<!--  -->  



<!-- image links -->  

[ImageOpenFile]: /microsoft-edge/devtools-guide-chromium/media/resources-command-menu-empty.msft.png "図 1: [ファイルを開く] ダイアログボックス"  
[ImageFileSearch]: /microsoft-edge/devtools-guide-chromium/media/resources-command-menu-file-search.msft.png "図 2: [ファイルを開く] ダイアログボックスにファイル名を入力する"  
[ImageNetworkResponse]: /microsoft-edge/devtools-guide-chromium/media/resources-network-response.msft.png "図 3: * * Network * * パネルでリソースを検査する"  
[ImageRevealNetwork]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-reveal-in-network-panel.msft.png "図 4: ネットワークパネルでの表示"  
[ImageNetworkLog]: /microsoft-edge/devtools-guide-chromium/media/resources-network-resources.msft.png "図 5: ネットワークログのページリソース"  
[ImagePage]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-empty.msft.png "図 6: [ページ] ウィンドウ"  
[ImageSourcesView]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-resource.msft.png "図 7: エディターでファイルを表示する"  
[ImageGroupByFolder]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-resource-group-by-folder.msft.png "図 8: [フォルダーでグループ化] オプション"  
[ImageFileNames]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png "図 9: [グループ化] フォルダーを無効にした後のページウィンドウ"  
[ImageApplication]: /microsoft-edge/devtools-guide-chromium/media/resources-application-mainfest-airhorner.msft.png "図 10: アプリケーションパネル"  
[ImageFrames]: /microsoft-edge/devtools-guide-chromium/media/resources-application-mainfest-airhorner-frames-expanded.msft.png "図 11: [フレーム] ウィンドウ"  
[ImageApplicationView]: /microsoft-edge/devtools-guide-chromium/media/resources-application-mainfest-airhorner-expanded-resources.msft.png "図 12: アプリケーションパネルでのリソースの表示"  
[ImageCSS]: /microsoft-edge/devtools-guide-chromium/media/resources-network-resources-filter-css.msft.png "図 13: ネットワークログの CSS をフィルター処理する"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevtoolsNetworkFilterByResourceType]: /microsoft-edge/devtools-guide-chromium/network/index#filter-by-resource-type "リソースの種類によるフィルター-Microsoft Edge DevTools でネットワークアクティビティを検査する"  
[DevtoolsNetworkInspectDetailsResource]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "リソースの詳細を調べる-Microsoft Edge DevTools でのネットワークアクティビティの調査"  
[DevtoolsNetworkLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワークアクティビティのログ-Microsoft Edge DevTools でネットワークアクティビティを検査する"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: インラインフレームの要素 |MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "Web 開発について学ぶ |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/resources/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
