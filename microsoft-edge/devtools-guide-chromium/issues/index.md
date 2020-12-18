---
description: 問題ツールを使用して、Web サイトの問題を見つけて修正します。
title: Microsoft Edge DevTools Issues ツールの問題を見つけて修正する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8bd3e5950572a9d3fdce71ec6cd935f6b6d6a0b7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230664"
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

# Microsoft Edge DevTools Issues ツールの問題を見つけて修正する  

Microsoft **Edge DevTools** の Issues ツールを使用すると、本体の通知の煩雑さや煩雑な作業が軽減 **されます**。  Cookie の問題や混在したコンテンツなど、ブラウザーで検出された問題の解決策を見つけるために使用します。  

> [!NOTE]
> Microsoft Edge 84 では、問題 **ツールは** 次の 3 種類の問題をサポートしています。  
> *   [Cookie の問題][MDNSameSiteCookies]  
> *   [混在コンテンツ][MDNMixedContent]  
> *   [COEP の問題][W3CCOEPSpec]
> 
> Microsoft Edge DevTools チームは、今後のバージョンの Microsoft Edge で、より多くの問題の種類をサポートする予定です。  

## DevTools ドロワーで問題ツールを開く  

1.  修正する問題が含samesite-sandbox.glitch.me [ページに][GlitchSamesiteSandbox]アクセスします。  
1.  [DevTools を開きます][DevtoolsOpen]。  
1.  :::row:::
       :::column span="":::
          黄色の **警告バーの [問題に移動** ] ボタンを選択します。  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="問題が検出された場合に黄色の警告バーの [問題] ボタンに移動する" lightbox="../media/issues-open-issues-tab.msft.png":::
             問題 **が検出された場合** 、黄色の警告バーの [問題に移動] ボタン。  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          または、[その他の **ツール] メニュー** から [問題 **] を選択** します。  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text="[その他のツール] メニューの [問題] ツール" lightbox="../media//issues-more-tools-menu.msft.png":::
             **[その他** のツール] **メニューの [問題]** ツール  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  必要に応 **じて、[ページの再読み込** み] ボタンを選択します。  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="ページの再読み込みボタンを含む DevTools ドロワーの問題ツール" lightbox="../media/issues-tab-before-refresh.msft.png":::
       **ページの再** 読み込みボタンを含む DevTools ドロワー **の問題** ツール  
    :::image-end:::  

    コンソールで報告 **される問題** (次の図の Cookie の警告など) を理解するのは非常に難しい場合があります。  報告された問題に基づいて、実行する必要がある操作が明確ではない場合があります。  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="3 つの Cookie の問題がある DevTools ドロワーの問題ツール" lightbox="../media/issues-tab-after-refresh.msft.png":::
       **3 つの** Cookie の問題がある DevTools ドロワーの問題ツール  
    :::image-end:::  
    
## 問題ツールでアイテムを表示する  

**DevTools**ドロワーの問題ツールは、構造化された、集計された、操作可能な方法で警告を表示します。  

1.  問題の修正 **方法と影響** を受けるリソースの検索方法に関するガイダンスを取得するには、問題ツールで項目を選択します。  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="クロスサイト Cookie をセキュリティで保護された問題としてマークする問題ツールで開く" lightbox="../media/issues-tab-issue-open.msft.png":::
       **クロスサイト Cookie をセキュリティで保護された** 問題としてマークする問題 **ツールで開** く  
    :::image-end:::  
    
    各アイテムには、次の 4 つのコンポーネントがあります。  
    
    *   問題を説明する見出し。  
    *   コンテキストとソリューションを提供する説明。  
    *   ネットワーク **パネルなどの適切** な DevTools コンテキスト内のリソースにリンクする、影響を受けるリソース セクション。  
    *   その他のガイダンスへのリンク。  
    
1.  影響を受ける **リソース内のアイテムを選択して** 詳細を表示します。  次の例では、クロスサイト Cookie をセキュリティで保護 **された** 問題としてマークすると、1 つの Cookie と 2 つの要求に影響します。  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="[問題ドロワー] タブで開いている影響を受けるリソース" lightbox="../media/issues-tab-affected-resources.msft.png":::
       DevTools ドロワーの **問題** ツールで開いている影響を受けるリソース  
    :::image-end:::  
    
## 問題をコンテキストで表示する  

1.  DevTools 内の適切なコンテキストでアイテムを表示するリソース リンクを選択します。  次の例では、[要求] の下で選択して、その要求に添付 `samesite-sandbox.glitch.me` された Cookie を**** 表示します。  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="DevTools ネットワーク パネルで影響を受ける Cookie を表示する" lightbox="../media/issues-tab-view-request.msft.png":::
       DevTools ネットワーク パネルで影響を受ける Cookie を **表示** する  
    :::image-end:::  

1.  スクロールして問題のあるアイテムを表示します。次の例では Cookie `ck02` です。  SameSite 列 **にカーソル** を合わせると、問題 `None` が検出された値が表示されます。  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="DevTools ネットワーク パネルの ck02 Cookie の SameSite 列の値なし" lightbox="../media/issues-tab-view-issue.msft.png":::
       `None` DevTools ネットワーク パネルの **Cookie** の `ck02` SameSite 列 **の** 値  
    :::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite Cookie テスト |Glitch"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite Cookie |MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "混在コンテンツ |MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "クロスオリジン 埋め込みポリシー |Web のコミュニティ グループ"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/issues/index) つかり [、Sam Dutton][SamDutton] \(Developer Developer Developer\) によって作成されています。  
[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[SamDutton]: https://developers.google.com/web/resources/contributors/samdutton  
