---
description: '[設定] から [コンテンツ スクリプトをライブラリ コードとしてマークする] を有効>フレームワーク ライブラリ コードを使用します。'
title: コンテンツ スクリプトをライブラリ コードとしてマークする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ffc27cdd04ce28df888507fb2e1dc460d5bb4f21
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398953"
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

# <a name="mark-content-scripts-as-library-code"></a>コンテンツ スクリプトをライブラリ コードとしてマークする  

Microsoft Edge **** DevTools の [ソース][][DevToolsJavascriptStepThroughCode]パネルを使用してコードをステップ実行する場合は、認識できないコードを一時停止する場合があります。  おそらく、インストールした Microsoft Edge 拡張機能のコードを一時停止した可能性があります。  拡張機能コードを一時停止しない場合は、次の手順を実行します。  

1.  DevTools を開き **、[DevTools** \( \) をカスタマイズして制御 `...` する] を選択し、[設定] > **します**。  [設定] を **選択して開** く場合があります `F1` 。  

1.  [設定] **の [フレームワーク** ライブラリ コード] **セクションを開く [ライブラリ** コード] パネルを **選択します**。  
1.  [コンテンツ スクリプトを **ライブラリ コードとしてマークする] チェック ボックスをオン** にします。  
    
    :::image type="complex" source="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png" alt-text="[コンテンツ スクリプトをライブラリ コードとしてマークする] チェック ボックスをオンにする" lightbox="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png":::
       [コンテンツ スクリプト **をライブラリ コードとしてマークする] チェック ボックスをオン** にする  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "手順 4: コードをステップ実行する - Microsoft Edge DevTools の JavaScript のデバッグの|Microsoft Docs"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
