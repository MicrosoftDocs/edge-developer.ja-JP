---
title: ライブ式を使って JavaScript の式値をリアルタイムで見る
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c388e44ca5507dd88ad9ad7b7ee985e658dfc569
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601741"
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

  

コンソールで同じ JavaScript 式を繰り返し入力したことがわかった場合は、**ライブ式**の作成が簡単になることがあります。  **ライブ式**で式を1回入力し、本体の先頭に固定します。  この式の値は、ほぼリアルタイムで更新されます。  

## ライブ式を作成する   

1.  [本体を開き][DevToolsConsoleReferenceOpenConsole]ます。  
1.  [**ライブ式** ![ の作成] をクリックし ][ImageCreateLiveExpressionIcon] ます。  [**ライブ式**] テキストボックスが表示されます。  
    
    > ##### 図 1  
    > `document.activeElement`[**ライブ式**] テキストボックスへの入力  
    > ![ライブ式のテキストボックスへの "activeElement 要素の入力][ImageLiveExpressionTextbox]  
    
1.  `Control` + `Enter` 式を保存するには、「\ (Windows \)」または「 `Command` + `Enter` \ (macOS \)」を入力するか、[**ライブ式**] テキストボックスの外側をクリックします。  

<!--todo: add reference open console (open the console) section when available  -->  

 



<!-- image links -->  

[ImageCreateLiveExpressionIcon]: /microsoft-edge/devtools-guide-chromium/media/create-live-expression-icon.msft.png  

[ImageLiveExpressionTextbox]: /microsoft-edge/devtools-guide-chromium/media/console-create-live-expression.msft.png "図 1: [ライブ式] テキストボックスへの "ドキュメントの入力" 要素"  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: /microsoft-edge/devtools-guide-chromium/console/reference#open-the-console "本体本体のリファレンスを開く"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
