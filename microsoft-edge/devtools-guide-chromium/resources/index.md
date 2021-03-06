---
description: フレーム、ドメイン、種類、その他の条件でリソースを整理します。
title: Microsoft Edge DevTools を使用してページ リソースを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 75063b23f23c25ff4fe2e7f6e044a2de9a7b1ccd
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398225"
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

# <a name="view-page-resources-with-microsoft-edge-devtools"></a>Microsoft Edge DevTools を使用してページ リソースを表示する  

このガイドでは、Microsoft Edge DevTools を使用して Web ページのリソースを表示する方法について説明します。  リソースは、ページが正しく表示するために必要なファイルです。  リソースの例としては、CSS、JavaScript、HTML ファイル、および画像が含まれます。  

このガイドでは、Web 開発の基本と Microsoft [][MDNLearnWebDevelopment] [Edge DevTools][MicrosoftEdgeDevTools]に精通している必要があります。  

## <a name="open-resources"></a>リソースを開く  

検査するリソースの名前がわかっている場合は、コマンド メニューを**** 使用してリソースを高速に開きます。  

1.  `Control` + `P` \(Windows, Linux\) または `Command` + `P` \(macOS\) を選択します。  [ **ファイルを開く]** ダイアログボックスが開きます。  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text="[ファイルを開く] ダイアログ" lightbox="../media/resources-command-menu-empty.msft.png":::
       [ **ファイルを開く]** ダイアログ  
    :::image-end:::  
    
1.  ドロップダウンからファイルを選択するか、ファイル名の入力を開始し、オートコンプリート ボックスで正しいファイルが強調表示された後 `Enter` で選択します。  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="[ファイルを開く] ダイアログボックスにファイル名を入力する" lightbox="../media/resources-command-menu-file-search.msft.png":::
       [ファイルを開く] ダイアログボックス **にファイル名を入力** する  
    :::image-end:::  
    
### <a name="open-resources-in-the-network-tool"></a>ネットワーク ツールでリソースを開く  

[リソースの [詳細を検査する] に移動します][DevtoolsNetworkInspectDetailsResource]。  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="ネットワーク ツールでリソースを検査する" lightbox="../media/resources-network-response.msft.png":::
   ネットワーク ツールでリソース **を検査** する  
:::image-end:::  

### <a name="reveal-resources-in-the-network-tool-from-other-panels"></a>他のパネルからネットワーク ツールのリソースを表示する  

下 [の [リソースの](#browse-resources) 参照] セクションでは、DevTools UI のさまざまな部分からリソースを表示する方法を示します。  ネットワーク ツールでリソースを検査する場合は****、リソースにカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[ネットワーク] パネルで [表示] を**選択します**。  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="[ネットワーク] パネルで表示する" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **[ネットワーク] パネルで表示する**  
:::image-end:::  

## <a name="browse-resources"></a>リソースの参照  

### <a name="browse-resources-in-the-network-panel"></a>[ネットワーク] パネルでリソースを参照する  

[ネットワーク アクティビティ [のログ記録] に移動します][DevtoolsNetworkLogActivity]。  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="ネットワーク ログのページ リソース" lightbox="../media/resources-network-resources.msft.png":::
   ネットワーク ログの**ページ リソース**  
:::image-end:::  

### <a name="browse-by-directory"></a>ディレクトリで参照する  

ディレクトリ別に整理されたページのリソースを表示するには、次の方法を実行します。  

1.  [ソース] **ツールを選択** して 、[ソース] **パネルを開** きます。  
1.  [ページ **] パネルを** 選択して、ページのリソースを表示します。  [ **ページ] ウィンドウが** 開きます。  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="ページウィンドウ" lightbox="../media/resources-sources-page-empty.msft.png":::
       [ **ページ]** パネル  
    :::image-end:::  
    
    前の図の非明白な項目の内訳を次に示します。  
    
    | ページ アイテム | 説明 |  
    |:--- |:--- |  
    | `top` | メイン ドキュメントの [参照コンテキスト][MDNInlineFrame]です。 |  
    | `airhorner.com` | ドメイン。  その下に入れ子になったすべてのリソースは、そのドメインから来ます。  たとえば、ファイルの完全な URL `comlink.global.j` はおそらく `https://airhorner.com/scripts/comlink.global.js` です。 |  
    | `scripts` | ディレクトリ。 |  
    | `(index)` | メインの HTML ドキュメント。 |  
    | `sw.js` | サービス ワーカーのランタイム コンテキスト。 |  
    
1.  エディターで表示するリソースを選択 **します**。  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="エディターでファイルを表示する" lightbox="../media/resources-sources-page-resource.msft.png":::
       エディターでファイルを表示 **する**  
    :::image-end:::  
    
### <a name="browse-by-filename"></a>ファイル名で参照する  

既定では **、Page パネルはリソース** をディレクトリ別にグループ化します。  このグループ化を無効にして、各ドメインのリソースをフラット リストとして表示するには、次のコマンドを実行します。  

1.  [ページ] **パネルを開** きます。  [ディレクトリで [参照] に移動します](#browse-by-directory)。  
1.  [その **他のオプション]** `...` を選択し、[ **フォルダー別グループ化] を無効にします**。  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text="[フォルダー別にグループ化] オプション" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       [ **フォルダー別にグループ化]** オプション  
    :::image-end:::  
    
    リソースはファイルの種類別に整理されます。  各ファイルの種類では、リソースはアルファベット順に整理されます。  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="Group By Folder を無効にした後のページ パネル" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       Group **By** Folder を無効にした **後のページ パネル**  
    :::image-end:::  
    
### <a name="browse-by-file-type"></a>ファイルの種類別に参照する  

ファイルの種類に基づいてリソースをグループ化するには、次のコマンドを使用します。  

1.  [アプリケーション] **タブを選択** します。 [ **アプリケーション] ツール** が開きます。  既定では、通常 **、マニフェスト ウィンドウ** が最初に開きます。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="アプリケーション ツール" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       アプリケーション**ツール**  
    :::image-end:::  
    
1.  [フレーム] ウィンドウまで **下にスクロール** します。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text="[フレーム] ウィンドウ" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       [ **フレーム]** ウィンドウ  
    :::image-end:::  
    
1.  興味のあるセクションを展開します。  
1.  リソースを選択して表示します。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="[アプリケーション] パネルでリソースを表示する" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       [アプリケーション] パネルでリソース **を表示** する  
    :::image-end:::  
    
#### <a name="browse-files-by-type-in-the-network-panel"></a>[ネットワーク] パネルの種類別にファイルを参照する  

[リソースの [種類でフィルター] に移動します][DevtoolsNetworkFilterByResourceType]。  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="ネットワーク ログの CSS のフィルター" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   ネットワーク ログの CSS **の** フィルター  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (クロム) 開発者向け|Microsoft Docs"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "リソースの種類によるフィルター - Microsoft Edge DevTools のネットワーク アクティビティを調|Microsoft Docs"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "リソースの詳細を調す - Microsoft Edge DevTools サーバーでネットワーク アクティビティを|Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "ネットワーク アクティビティのログ - Microsoft Edge DevTools サーバーでネットワーク アクティビティを|Microsoft Docs"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: Inline Frame 要素|MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "Web 開発の詳細|MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/resources/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
