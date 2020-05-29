---
title: Microsoft Edge DevTools の問題を見つけて解決する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cd6123f235af4ccb87338e1d4db12c03a93a9eaa
ms.sourcegitcommit: a5392ab44133d742c0e1fa500ad9a872989b7c3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684860"
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





# Microsoft Edge DevTools の問題を見つけて解決する   



Microsoft Edge DevTools の [**問題**] ツールは、**本体**の通知の疲労と低優先メールを削減します。  Cookie の問題や混在したコンテンツなど、ブラウザーで検出された問題の解決策を見つけるために使います。  

> [!NOTE]
> Microsoft Edge 84 の**問題**ツールでは、次の3種類の問題がサポートされています。  
> *   [Cookie に関する問題][MDNSameSiteCookies]  
> *   [混在したコンテンツ][MDNMixedContent]  
> *   [COEP の問題][W3CCOEPSpec]
> 
> Microsoft edge DevTools チームは、今後のバージョンの Microsoft Edge で、より多くの問題の種類をサポートする予定です。  

## DevTools のドローワで問題ツールを開く   

1.  修正する問題が含まれているページ ( [samesite-sandbox.glitch.me][GlitchSamesiteSandbox]など) にアクセスします。  
1.  [DevTools を開き][DevtoolsOpen]ます。  
1.  :::row:::
       :::column span="":::
          黄色の警告バーの [**問題に移動**] を選択します。  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="問題が検出されたときに黄色の警告バーにある [懸案事項] ボタンに移動する" lightbox="../media/issues-open-issues-tab.msft.png":::
             図 1.   問題が検出されたときの黄色の警告バーの **[問題に移動**] ボタン。  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          または、[**その他のツール**] メニューから [**問題**] を選択します。  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text="[その他のツール] メニューの [問題] ツール" lightbox="../media//issues-more-tools-menu.msft.png":::
             図 2.   [**その他のツール**] メニューの [**問題**] ツール  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  必要に応じて、[**ページの再読み込み**] ボタンを選択します。  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="[ページの再読み込み] ボタンがある DevTools ドローワの問題ツール" lightbox="../media/issues-tab-before-refresh.msft.png":::
       図 3.   [**ページの再読み込み**] ボタンがある Devtools ドローワの**問題**ツール  
    :::image-end:::  

    **コンソール**で報告される問題は、次の画像の cookie の警告など、非常に理解しにくくなります。  報告された問題に基づいて、何を行う必要があるかが明確でない場合があります。  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="3つの cookie の問題が発生した DevTools の [問題] ツール" lightbox="../media/issues-tab-after-refresh.msft.png":::
       図 4:   3つの cookie の問題が発生した DevTools の [**問題**] ツール  
    :::image-end:::  
    
## 懸案事項ツールのアイテムを表示する   

DevTools のドローワの**問題**ツールでは、構造化され、集計され、実行可能な方法で警告が表示されます。  

1.  問題を修正し、影響を受けるリソースを見つける方法についてのガイダンスを表示するには、[**案件**] ツールのアイテムを選択します。  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="[問題] ツールで、クロスサイト cookie をセキュリティで保護された問題としてマークする" lightbox="../media/issues-tab-issue-open.msft.png":::
       図 5:   [**問題**] ツールで、**クロスサイト Cookie をセキュリティで保護された問題としてマーク**する  
    :::image-end:::  
    
    各項目には、次の4つのコンポーネントがあります。  
    
    *   問題を説明するヘッドライン。  
    *   コンテキストとソリューションを提供する説明。  
    *   [ネットワーク] パネルなどの適切な DevTools コンテキスト内のリソースにリンクしている、**影響を受けるリソース**セクション。  
    *   詳しいガイダンスへのリンクです。  
    
1.  [影響を**受けるリソース**] 内のアイテムを選択して、詳細を表示します。  次の例では、1つの cookie と2つの要求が**セキュリティで保護された問題としてマークさ**れています。  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="[問題の引き出し] タブで表示される影響を受けるリソース" lightbox="../media/issues-tab-affected-resources.msft.png":::
       図 6.   DevTools のドローワの [**問題**] ツールで、影響を受けるリソースが開かれる  
    :::image-end:::  
    
## コンテキストの問題を表示する   

1.  リソースリンクを選んで、DevTools 内の適切なコンテキストで項目を表示します。  次の例では、 `samesite-sandbox.glitch.me` [**要求**] の下で、その要求に関連付けられている cookie を表示します。  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="DevTools ネットワークパネルで影響を受ける cookie を表示する" lightbox="../media/issues-tab-view-request.msft.png":::
       図 7.  DevTools ネットワークパネルで影響を受ける cookie を表示する  
    :::image-end:::  

1.  スクロールして、問題のあるアイテムを表示します。次の例では、cookie が表示されます。 `ck02`  **SameSite**列の上にマウスポインターを移動すると、 `None` 問題が検出された値が表示されます。  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="DevTools ネットワークパネルの ck02 cookie の SameSite 列の値なし" lightbox="../media/issues-tab-view-issue.msft.png":::
       図 8.  `None` **SameSite** `ck02` devtools**ネットワーク**パネルの cookie の [SameSite] 列の値  
    :::image-end:::  

<!--## Feedback  -->  



<!-- image links -->  

<!-- links -->  

[DevtoolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite cookie のテスト |故障"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite クッキー |MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "混在したコンテンツ |MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "Embedder のクロスオリジンのポリシー |Web Incubator コミュニティグループ"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/issues/index)にあり、 [Sam Dutton][SamDutton] \ (開発者向け) で作成されています。  
[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[SamDutton]: https://developers.google.com/web/resources/contributors/samdutton  
