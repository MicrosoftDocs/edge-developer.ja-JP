---
description: フレーム、ドメイン、種類、またはその他の条件によってリソースを整理します。
title: Microsoft Edge DevTools でページリソースを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4f90927cc4044c722d9a62ab4b0427aa2753e4c5
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993591"
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

このガイドは、 [web 開発][MDNLearnWebDevelopment] と [Microsoft Edge devtools][MicrosoftEdgeDevTools]の基本について理解していることを前提としています。  

## リソースを開く   

検査するリソースの名前がわかっている場合、[ **コマンド] メニュー** でリソースをすばやく開くことができます。  

1.  `Control` + `P` \ (Windows \) または `Command` + `P` \ (macOS \) を押します。  [ **ファイルを開く** ] ダイアログが開きます。  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-command-menu-empty.msft.png":::
       [ **ファイルを開く** ] ダイアログボックス  
    :::image-end:::  
    
1.  ドロップダウンからファイルを選択するか、ファイル名の入力を開始し、[ `Enter` オートコンプリート] ボックスで正しいファイルが強調表示されたら、1回押します。  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="[ファイルを開く] ダイアログボックスにファイル名を入力する" lightbox="../media/resources-command-menu-file-search.msft.png":::
       [ **ファイルを開く** ] ダイアログボックスにファイル名を入力する  
    :::image-end:::  
    
### [ネットワーク] パネルでリソースを開く   

「 [リソースの詳細を調べる][DevtoolsNetworkInspectDetailsResource]」を参照してください。  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="[ネットワーク] パネルでリソースを検査する" lightbox="../media/resources-network-response.msft.png":::
   [ **ネットワーク** ] パネルでリソースを検査する  
:::image-end:::  

### [ネットワーク] パネルのリソースを他のパネルから公開する   

以下の「 [リソースの参照](#browse-resources) 」セクションでは、DEVTOOLS UI のさまざまな部分からリソースを表示する方法について説明します。  **ネットワーク**パネルでリソースを検査する場合は、リソースを右クリックして、[**ネットワークパネルで**表示] を選択します。  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="[ネットワーク] パネルでの表示" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **[ネットワーク] パネルでの表示**  
:::image-end:::  

## リソースを参照する   

### [ネットワーク] パネルでリソースを参照する   

「 [ネットワークアクティビティのログ記録][DevtoolsNetworkLogActivity]」を参照してください。  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="ネットワークログのページリソース" lightbox="../media/resources-network-resources.msft.png":::
   **ネットワーク**ログのページリソース  
:::image-end:::  

### ディレクトリで参照   

ディレクトリごとに整理されたページのリソースを表示するには、次の操作を行います。  

1.  [ **ソース** ] タブをクリックして、[ **ソース** ] パネルを開きます。  
1.  [ **ページ** ] タブをクリックして、ページのリソースを表示します。  [ **ページ** ] ウィンドウが開きます。  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="ページウィンドウ" lightbox="../media/resources-sources-page-empty.msft.png":::
       **ページ**ウィンドウ  
    :::image-end:::  
    
    前の図の明白でない項目の詳細を次に示します。  
    
    | ページアイテム | 説明 |  
    |:--- |:--- |  
    | `top` | メイン文書の [閲覧コンテキスト][MDNInlineFrame]。 |  
    | `airhorner.com` | ドメイン。  下位にあるすべてのリソースがそのドメインから取得されます。  たとえば、ファイルの完全な URL はおそらくのように `comlink.global.j` `https://airhorner.com/scripts/comlink.global.js` なります。 |  
    | `scripts` | ディレクトリ。 |  
    | `(index)` | メインの HTML 文書。 |  
    | `sw.js` | サービスワーカーランタイムコンテキスト。 |  
    
1.  リソースをクリックして **エディター**で表示します。  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="エディターでファイルを表示する" lightbox="../media/resources-sources-page-resource.msft.png":::
       **エディター**でファイルを表示する  
    :::image-end:::  
    
### ファイル名で参照   

既定では、 **ページ** ウィンドウはディレクトリ別にリソースをグループ化します。  このグループ化を無効にして、各ドメインのリソースをフラットなリストとして表示するには、次の操作を行います。  

1.  **ページ**ウィンドウを開きます。  「 [ディレクトリで参照」を](#browse-by-directory)参照してください。  
1.  [ **その他のオプション**] をクリックし `...` て、[ **グループ化**] を無効にします。  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text="[フォルダーでグループ化] オプション" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       [ **フォルダーでグループ化** ] オプション  
    :::image-end:::  
    
    リソースはファイルの種類別に整理されます。  各ファイルの種類では、リソースがアルファベット順に構成されています。  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="[グループ化] フォルダーを無効にした後のページウィンドウ" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       [**グループ化] フォルダーを**無効にした後の**ページ**ウィンドウ  
    :::image-end:::  
    
### ファイルの種類で参照する   

ファイルの種類に基づいてリソースをグループ化するには、次の操作を行います。  

1.  [ **アプリケーション** ] タブをクリックします。 **アプリケーション** パネルが開きます。  既定では、最初に **マニフェスト** ウィンドウが開きます。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="アプリケーションパネル" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       **アプリケーション**パネル  
    :::image-end:::  
    
1.  [ **フレーム** ] ウィンドウまで下にスクロールします。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text="[フレーム] ウィンドウ" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       [ **フレーム** ] ウィンドウ  
    :::image-end:::  
    
1.  目的のセクションを展開します。  
1.  リソースをクリックして表示します。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="アプリケーションパネルでリソースを表示する" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       **アプリケーション**パネルでリソースを表示する  
    :::image-end:::  
    
#### [ネットワーク] パネルでファイルの種類を参照する   

「 [リソースの種類でフィルター処理][DevtoolsNetworkFilterByResourceType]する」をご覧ください。  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="ネットワークログの CSS をフィルター処理する" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   **ネットワーク**ログの CSS をフィルター処理する  
:::image-end:::  

<!--  
  


-->  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "リソースの種類によるフィルター-Microsoft Edge DevTools でのネットワークアクティビティの検査 |Microsoft ドキュメント"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "リソースの詳細を調べる-Microsoft Edge DevTools でのネットワークアクティビティの検査 |Microsoft ドキュメント"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "ネットワークアクティビティのログ-Microsoft Edge DevTools でネットワークアクティビティを検査するMicrosoft ドキュメント"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: インラインフレームの要素 |MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "Web 開発について学ぶ |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/resources/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
