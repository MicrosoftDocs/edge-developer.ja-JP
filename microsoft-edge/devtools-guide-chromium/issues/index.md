---
description: '[問題] ツールを使用して、Web サイトの問題を見つけて修正します。'
title: Microsoft Edge DevTools の問題ツールの検索と修正
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e16bd926ea5bae35ad82f54ac5d1ae2028e3c59d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398976"
---
<!-- Copyright Sam Dutton 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <a name="find-and-fix-problems-with-the-microsoft-edge-devtools-issues-tool"></a>Microsoft Edge DevTools の問題ツールの検索と修正  

Microsoft **Edge** DevTools の Issues ツールを使用すると、コンソールの通知の疲労と煩雑さが軽減 **されます**。  Cookie の問題や混在コンテンツなど、ブラウザーによって検出された問題に対する解決策を見つける場合に使用します。  

> [!NOTE]
> Microsoft Edge 84 では **、Issues** ツールは次の 3 種類の問題をサポートしています。  
> *   [Cookie の問題][MDNSameSiteCookies]  
> *   [混在コンテンツ][MDNMixedContent]  
> *   [COEP の問題][W3CCOEPSpec]
> 
> Microsoft Edge DevTools チームは、今後のバージョンの Microsoft Edge で、より多くの問題の種類をサポートする予定です。  

## <a name="open-the-issues-tool-in-the-devtools-drawer"></a>DevTools ドロワーで [問題] ツールを開く  

1.  修正する問題を含む web [ページ][GlitchSamesiteSandbox](samesite-sandbox.glitch.meなど) に移動します。  
1.  [DevTools を開きます][DevtoolsOpen]。  
1.  :::row:::
       :::column span="":::
          黄色の **警告バーの [問題に移動** ] ボタンを選択します。  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="問題が検出された場合は、黄色の警告バーの [問題] ボタンに移動します。" lightbox="../media/issues-open-issues-tab.msft.png":::
             問題 **が検出された場合** 、黄色の警告バーの [問題に移動] ボタンをクリックします。  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          または、[その他のツール **] メニュー** から [問題 **] を選択** します。  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text="[その他のツール] メニューの [問題] ツール" lightbox="../media//issues-more-tools-menu.msft.png":::
             **[その他** のツール] **メニューの [問題]** ツール  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  必要に応 **じて、[ページの再読み込** み] ボタンを選択します。  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="[ページの再読み込み] ボタンを使用した DevTools ドロワーの問題ツール" lightbox="../media/issues-tab-before-refresh.msft.png":::
       **[ページの**再読み込み] ボタンを使用した DevTools**ドロワーの問題ツール**  
    :::image-end:::  

    コンソールで報告 **された問題は** 、次の図の Cookie の警告など、理解が非常に難しいです。  報告された問題に基づいて、何を行う必要があるのかはっきりしない場合があります。  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="3 つの Cookie の問題を持つ DevTools ドロワーの問題ツール" lightbox="../media/issues-tab-after-refresh.msft.png":::
       **3 つの** Cookie の問題を持つ DevTools ドロワーの問題ツール  
    :::image-end:::  
    
## <a name="view-items-in-the-issues-tool"></a>[問題] ツールでアイテムを表示する  

**DevTools**ドロワーの Issues ツールは、構造化、集約、および操作可能な方法で警告を表示します。  

1.  問題を解決し、影響 **を** 受けるリソースを見つける方法に関するガイダンスを取得するには、[問題] ツールでアイテムを選択します。  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="クロスサイト Cookie を [問題] ツールで開いているセキュリティで保護された問題としてマークする" lightbox="../media/issues-tab-issue-open.msft.png":::
       **クロスサイト Cookie を [問題] ツールで開** いているセキュリティで保護された **問題としてマーク** する  
    :::image-end:::  
    
    各アイテムには、次の 4 つのコンポーネントがあります。  
    
    *   問題を説明する見出し。  
    *   コンテキストとソリューションを提供する説明。  
    *   ネットワーク **パネルなどの適切** な DevTools コンテキスト内のリソースにリンクする、影響を受けるリソース セクション。  
    *   詳細なガイダンスへのリンク。  
    
1.  詳細を表示するには **、[影響を受けるリソース] で** アイテムを選択します。  次の例では、 **セキュリティで保護された問題としてクロスサイト** Cookie をマークすると、1 つの Cookie と 2 つの要求に影響します。  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="問題ツールで開いている影響を受けるリソース" lightbox="../media/issues-tab-affected-resources.msft.png":::
       DevTools ドロワーの **Issues** ツールで開く影響を受けるリソース  
    :::image-end:::  
    
## <a name="view-issues-in-context"></a>コンテキストで問題を表示する  

1.  DevTools 内の適切なコンテキストでアイテムを表示するには、リソース リンクを選択します。  次の例では、[要求] `samesite-sandbox.glitch.me` を **選択** して、その要求に添付された Cookie を表示します。  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="DevTools ネットワーク ツールで影響を受ける Cookie を表示する" lightbox="../media/issues-tab-view-request.msft.png":::
       DevTools ネットワーク ツールで影響を受ける Cookie を **表示** する  
    :::image-end:::  

1.  スクロールして、問題のあるアイテムを表示します。次の例では `ck02` 、Cookie です。  SameSite 列 **にカーソルを** 合わせると、問題 `None` が検出された値を確認できます。  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="DevTools ネットワーク ツールの ck02 Cookie の SameSite 列の値なし" lightbox="../media/issues-tab-view-issue.msft.png":::
       `None` DevTools**ネットワーク**ツールの `ck02` Cookie の SameSite 列の値****  
    :::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite Cookie のテスト|Glitch"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite cookie |MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "混在コンテンツ |MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "クロスオリジン エンベダー ポリシー |Web インキュベーター コミュニティ グループ"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/issues/index) つかり [、Sam Dutton][SamDutton] \(Developer Advocate\) によって作成されています。  
[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[SamDutton]: https://developers.google.com/web/resources/contributors/samdutton  
