---
title: どの要素にフォーカスがあるかを追跡する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a1bcb7e97357d1348b363ecd4842d1b6a78feb45
ms.sourcegitcommit: 8bfa239274e7a4856b961b9cf163b08d96463c10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "10581532"
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





# どの要素にフォーカスがあるかを追跡する   



ページのキーボードナビゲーションのアクセシビリティをテストするとします。  キーを使用してページ内を移動するときに `Tab` 、フォーカスがある要素が非表示になることがあるため、フォーカスリングが消えることがあります。  DevTools で優先要素を追跡するには、次の操作を行います。  

1.  **本体**を開きます。  
1.  [**ライブ式** ![ の作成] をクリックし ][ImageCreateIcon] ます。  

    > ##### 図 1  
    > **ライブ式**の作成  
    > ![ライブ式の作成][ImageLiveExpression]  
    
1.  「`document.activeElement`」と入力します。
1.  **ライブ式**UI の外側をクリックして保存します。

以下に表示される値 `document.activeElement` は、式の結果です。  
この式は常に優先要素を表しているため、フォーカスがある要素を常に追跡する方法が用意されました。  

*   結果にマウスポインターを合わせて、ビューポート内の優先要素を強調表示します。  
*   結果を右クリックし、[要素**パネルで**表示] を選択して、 **[要素] パネルの**DOM ツリーに要素を表示します。  
*   結果を右クリックし、[**グローバル変数として保存**] を選択して、**コンソール**で使うことができるノードへの可変参照を作成します。  

<!--## Feedback   -->  



<!-- image links -->  

[ImageCreateIcon]: /microsoft-edge/devtools-guide-chromium/media/create-live-expression-icon.msft.png  

[ImageLiveExpression]: /microsoft-edge/devtools-guide-chromium/media/accessibility-console-create-live-expression-empty.msft.png "図 1: ライブ式の作成"  

<!-- links -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome devtools & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
