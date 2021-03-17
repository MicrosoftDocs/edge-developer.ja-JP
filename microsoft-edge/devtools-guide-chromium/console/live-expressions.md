---
description: コンソールに同じ JavaScript 式を繰り返し入力する場合は、代わりに Live 式を試してください。
title: Live 式を使用して JavaScript 式の値をリアルタイムで確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: af920de1c395489dc09b83f3cc0f24814c4f5cbe
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439227"
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

# <a name="watch-javascript-expression-values-in-real-time-with-live-expressions"></a>Live 式を使用して JavaScript 式の値をリアルタイムで確認する  

コンソールで同じ JavaScript 式を繰り返し入力すると、Live 式の作成が簡単になる **場合があります**。  Live **Expression を使用すると** 、一度式を入力し、本体の上部にピン留めします。  式の値は、ほぼリアルタイムで更新されます。  

## <a name="create-a-live-expression"></a>Live 式の作成  

1.  [コンソールを開きます][DevToolsConsoleReferenceOpenConsole]。  
1.  [Live **Expression \(** Create ![ Live Expression ](../media/create-live-expression-icon.msft.png) \] を選択します)。  [Live **Expression]** テキスト ボックスが表示されます。  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="[Live 式] テキスト ボックスに document.activeElement と入力する" lightbox="../media/console-create-live-expression.msft.png":::
       [Live `document.activeElement` 式] **テキスト ボックスに入力** する  
    :::image-end:::  
    
1.  `Control` + `Enter` \(Windows,Linux\) または `Command` + `Enter` \(macOS\)**** を選択して式を保存するか、[Live 式] テキスト ボックスの外側を選択します。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "コンソール - コンソール リファレンス を開|Microsoft Docs"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
