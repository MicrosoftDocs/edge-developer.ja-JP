---
title: ライブ式を使って JavaScript の式値をリアルタイムで見る
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 39a7967a7dd1d0b34eb802d2879e04a64afd0dd0
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982238"
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





# ライブ式を使って JavaScript の式値をリアルタイムで見る   

  

コンソールで同じ JavaScript 式を繰り返し入力したことがわかった場合は、 **ライブ式**の作成が簡単になることがあります。  **ライブ式**で式を1回入力し、本体の先頭に固定します。  この式の値は、ほぼリアルタイムで更新されます。  

## ライブ式を作成する   

1.  [本体を開き][DevToolsConsoleReferenceOpenConsole]ます。  
1.  [ **ライブ式の作成** \ ( ![ ライブ式 ][ImageCreateLiveExpressionIcon] の作成 \)] をクリックします。  [ **ライブ式** ] テキストボックスが表示されます。  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="ライブ式のテキストボックスへの "activeElement 要素の入力" lightbox="../media/console-create-live-expression.msft.png":::
       `document.activeElement`[**ライブ式**] テキストボックスへの入力  
    :::image-end:::  
    
1.  `Control` + `Enter` 式を保存するには、「\ (Windows \)」または「 `Command` + `Enter` \ (macOS \)」を入力するか、[**ライブ式**] テキストボックスの外側をクリックします。  

<!--todo: add reference open console (open the console) section when available  -->  

 



<!-- image links -->  

[ImageCreateLiveExpressionIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "本体本体のリファレンスを開く |Microsoft ドキュメント"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
