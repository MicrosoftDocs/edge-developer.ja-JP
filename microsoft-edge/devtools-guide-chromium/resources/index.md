---
description: フレーム、ドメイン、種類、その他の条件でリソースを整理します。
title: Microsoft Edge DevTools を使用してページ リソースを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 353c36a9d98dac287c3fdaaa3feed2fe3b17cd07
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230776"
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

# Microsoft Edge DevTools を使用してページ リソースを表示する  

  

このガイドでは、Microsoft Edge DevTools を使用して Web ページのリソースを表示する方法について説明します。  リソースは、ページを正しく表示するために必要なファイルです。  リソースの例としては、CSS、JavaScript、HTML ファイル、画像があります。  

このガイドでは、Web 開発と Microsoft Edge [][MDNLearnWebDevelopment] [DevTools][MicrosoftEdgeDevTools]の基礎を理解している必要があります。  

## リソースを開く  

検査するリソースの名前が分かっている場合、コマンド メニューを**** 使用すると、リソースを高速に開く方法が提供されます。  

1.  `Control` + `P` \(Windows,Linux\) または `Command` + `P` \(macOS\) を選択します。  [ **ファイルを開く]** ダイアログボックスが開きます。  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text="[ファイルを開く] ダイアログ" lightbox="../media/resources-command-menu-empty.msft.png":::
       [ **ファイルを開く]** ダイアログ  
    :::image-end:::  
    
1.  ドロップダウンからファイルを選択するか、ファイル名の入力を開始し、オートコンプリート ボックスで正しいファイルが強調表示された後 `Enter` で選択します。  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="[ファイルを開く] ダイアログボックスにファイル名を入力する" lightbox="../media/resources-command-menu-file-search.msft.png":::
       [ファイルを開く] ダイアログ **ボックスにファイル名を入力** する  
    :::image-end:::  
    
### [ネットワーク] パネルでリソースを開く  

[リソースの [詳細を検査する] に移動します][DevtoolsNetworkInspectDetailsResource]。  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="[ネットワーク] パネルでリソースを検査する" lightbox="../media/resources-network-response.msft.png":::
   [ネットワーク] パネルでリソースを **検査** する  
:::image-end:::  

### 他のパネルからネットワーク パネルの表示リソースを表示する  

以下 [の「](#browse-resources) リソースの参照」セクションでは、DevTools UI のさまざまな部分からリソースを表示する方法を示します。  [ネットワーク] パネルでリソースを検査する**** 場合は、リソースを右クリックし、[ネットワーク] パネルで [表示 **] を選択します**。  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="ネットワーク パネルでの表示" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **ネットワーク パネルでの表示**  
:::image-end:::  

## リソースを参照する  

### [ネットワーク] パネルでリソースを参照する  

[ネットワーク アクティビティ [のログ] に移動します][DevtoolsNetworkLogActivity]。  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="ネットワーク ログのページ リソース" lightbox="../media/resources-network-resources.msft.png":::
   ネットワーク ログの **ページ** リソース  
:::image-end:::  

### ディレクトリで参照  

ディレクトリごとに整理されたページのリソースを表示するには:  

1.  [ソース **] タブを** クリックして、[ソース] パネル **を開** きます。  
1.  ページの **リソースを** 表示するには、[ページ] タブをクリックします。  [ **ページ] ウィンドウ** が開きます。  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="ページウィンドウ" lightbox="../media/resources-sources-page-empty.msft.png":::
       **ページ**ウィンドウ  
    :::image-end:::  
    
    前の図の明白でない項目の詳細を次に示します。  
    
    | ページ アイテム | 説明 |  
    |:--- |:--- |  
    | `top` | メイン ドキュメントの [参照コンテキスト][MDNInlineFrame]。 |  
    | `airhorner.com` | ドメイン。  その下に入れ子になっているすべてのリソースは、そのドメインから提供されます。  たとえば、ファイルの完全な URL `comlink.global.j` は、おそらく `https://airhorner.com/scripts/comlink.global.js` . |  
    | `scripts` | ディレクトリ。 |  
    | `(index)` | メイン HTML ドキュメント。 |  
    | `sw.js` | サービス ワーカー ランタイム コンテキスト。 |  
    
1.  リソースをクリックしてエディターに表示 **します**。  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="エディターでファイルを表示する" lightbox="../media/resources-sources-page-resource.msft.png":::
       エディターでファイルを表示 **する**  
    :::image-end:::  
    
### ファイル名で参照  

既定では、ページ **ウィンドウは** リソースをディレクトリ別にグループ化します。  このグループ化を無効にして、各ドメインのリソースをフラット リストとして表示するには、次のようにします。  

1.  ページ ウィンドウ **を開** きます。  ディレクトリで [参照に移動します](#browse-by-directory)。  
1.  [その **他のオプション] を** `...` 選択し、[ **フォルダー別グループ化] を無効にします**。  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text="[フォルダーでグループ化] オプション" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       [ **フォルダーでグループ化]** オプション  
    :::image-end:::  
    
    リソースはファイルの種類ごとに整理されています。  各ファイルの種類内では、リソースはアルファベット順に整理されます。  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="フォルダー別グループを無効にした後のページ ウィンドウ" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       フォルダー **別グループ** を無効にした **後のページ ウィンドウ**  
    :::image-end:::  
    
### ファイルの種類で参照  

ファイルの種類に基づいてリソースをグループ化するには:  

1.  [アプリケーション] **タブをクリック** します。 [ **アプリケーション]** パネルが開きます。  既定では、通常 **、マニフェスト ウィンドウ** が最初に開きます。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="[アプリケーション] パネル" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       [ **アプリケーション]** パネル  
    :::image-end:::  
    
1.  フレーム ウィンドウまで **下にスクロール** します。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text="[フレーム] ウィンドウ" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       [ **フレーム]** ウィンドウ  
    :::image-end:::  
    
1.  必要なセクションを展開します。  
1.  リソースをクリックして表示します。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="[アプリケーション] パネルでリソースを表示する" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       [アプリケーション] パネルでリソース **を表示** する  
    :::image-end:::  
    
#### [ネットワーク] パネルで種類別にファイルを参照する  

[リソースの [種類でフィルター] に移動します][DevtoolsNetworkFilterByResourceType]。  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="ネットワーク ログで CSS をフィルター処理する" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   ネットワーク ログで CSS を **フィルター** 処理する  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "リソースの種類によるフィルター - Microsoft Edge DevTools でネットワーク アクティビティを検査する |Microsoft Docs"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "リソースの詳細を検査する - Microsoft Edge DevTools でネットワーク アクティビティを検査する |Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "ネットワーク アクティビティをログに記録する - Microsoft Edge DevTools でネットワーク アクティビティを検査する |Microsoft Docs"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: Inline Frame 要素 |MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "Web 開発について |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/resources/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
