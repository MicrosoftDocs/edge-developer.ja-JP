---
description: コンソールを開き、Live 式を作成し、式を document.activeElement に設定します。
title: フォーカスされている要素を追跡する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3f3e59c4ee6f10b8e162f30efbff337ca2beec8d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398316"
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

# <a name="track-which-element-has-focus"></a>フォーカスされている要素を追跡する  

ページのキーボード ナビゲーションアクセシビリティをテストするとします。  キーを使用してページを移動すると、フォーカスのある要素が非表示のため、フォーカス リング `Tab` が表示されなくなる場合があります。  

DevTools でフォーカスされた要素を追跡するには、次のアクションを実行します。  

1.  コンソールを **開きます**。  
1.  [Live **Expression \(** Create ![ Live Expression ][ImageCreateIcon] \] を選択します)。  
    
    :::image type="complex" source="../media/accessibility-console-create-live-expression-empty.msft.png" alt-text="Live 式の作成" lightbox="../media/accessibility-console-create-live-expression-empty.msft.png":::
       Live 式の作成  
    :::image-end:::  
    
1.  「`document.activeElement`」と入力します。  
1.  保存する Live 式 UI **の外部を** 選択します。  
    
次に示す値 `document.activeElement` は、式の結果です。  

この式は常にフォーカスされた要素を表すので、フォーカスがある要素を常に追跡できます。  

*   結果にカーソルを合わせると、ビューポート内のフォーカスされた要素が強調表示されます。  
*   結果にカーソルを合わせると、コンテキスト メニュー \(右クリック\)**** を開き、[要素] パネルで [表示] を選択して、要素ツールの DOM ツリーに要素を**表示**します。  
*   結果にカーソルを置き、コンテキスト メニュー \(右クリック\)**** を開き、[グローバル変数として格納] を選択して、コンソールで使用できるノードへの変数参照を作成**します**。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCreateIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
