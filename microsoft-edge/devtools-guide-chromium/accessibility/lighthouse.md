---
description: DevTools 内からライトハウスを使用してアクセシビリティをテストします。
title: Lighthouse を使用してアクセシビリティをテストする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 822c25240ba30df31416ca783bf48d6d9ba52ed2
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624634"
---
<!-- this article was created on 05/11/2021 by moving a section out from the "Accessibility reference" article (reference.md) -->
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

# <a name="test-accessibility-using-lighthouse"></a>Lighthouse を使用してアクセシビリティをテストする

DevTools 内のライトハウスを使用して、ページのアクセシビリティを監査し、レポートを生成できます。 ライトハウス ツールを使用して、次の情報を確認できます。

*   ページがスクリーン リーダー用に適切にマークされているかどうかを指定します。  
*   ページ上のテキスト要素に、カラー ピッカーを使用して十分なコントラスト比を設定するかどうかを指定します。 詳細については、「Color Picker を使用 [してテキストと色のコントラストをテストする」に移動します](color-picker.md)。   

> [!NOTE]
> ライト **ハウス ツール** は、サードパーティの Web サイトでホストされているコンテンツへのリンクを提供します。  Microsoft は、これらのサイトのコンテンツおよび収集される可能性があるデータについて責任を負いません。  

ライトハウス ツールを使用してページを監査するには、次の手順を実行します。

1.  監査する URL に移動します。
1.  DevTools で、ライトハウス ツール **を** 選択します。  構成オプションが表示されます。
    
    :::image type="complex" source="../media/accessibility-lighthouse.msft.png" alt-text="ライトハウスの構成オプション" lightbox="../media/accessibility-lighthouse.msft.png":::
       ライトハウスの構成オプション
    :::image-end:::  
    
1.  [**デバイス]****で、モバイル**デバイスをシミュレートする場合は、[モバイル] を選択します。  このオプションは、ユーザー エージェントの文字列を変更し、ビューポートのサイズを変更します。  このオプションは、監査結果に影響を与える可能性があります。
1.  [カテゴリ] **セクションで** 、[アクセシビリティ] **を選択します**。
1.  [レポート **の生成] を選択します**。 10 ~ 30 秒後、DevTools はレポートを表示します。  このレポートには、ページのアクセシビリティを向上させる方法に関するヒントが示されています。  
    
    :::image type="complex" source="../media/accessibility-lighthouse-result.msft.png" alt-text="アクセシビリティ カテゴリのライトハウス レポート" lightbox="../media/accessibility-lighthouse-result.msft.png":::
       アクセシビリティ カテゴリの **ライトハウス** レポート
    :::image-end:::  
    
1.  レポート内のアイテムを選択して、詳細を確認します。  
    
    :::image type="complex" source="../media/accessibility-lighthouse-result-issue-expanded.msft.png" alt-text="ライトハウス レポートの拡張された問題" lightbox="../media/accessibility-lighthouse-result-issue-expanded.msft.png":::
       ライトハウス レポートの拡張された問題
    :::image-end:::  
    
1.  [詳細] **リンクを選択** して、問題のドキュメントを表示します。
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="問題のドキュメントを表示する" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       問題のドキュメントを表示する
    :::image-end:::  

1.  構成オプションに戻る場合は、DevTools で [監査の実行 ] () **を選択** します `+` 。    


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  


<!-- links -->  
[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd "axe - Web アクセシビリティ テスト - Chrome ウェブストア"  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
