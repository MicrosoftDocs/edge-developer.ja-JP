---
description: フレームワーク ライブラリ コードから [コンテンツ スクリプトをライブラリ コードとして設定 >する] を有効にする。
title: コンテンツ スクリプトをライブラリ コードとしてマークする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e3c2e89e8635b568d0beea8df8720bbb28beb711
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564029"
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

ソース ツールを使用**して**コードを[][DevToolsJavascriptStepThroughCode]ステップ実行すると、認識できないコードを一時停止する場合があります。  おそらく、インストールした拡張機能のいずれかのコードMicrosoft Edge一時停止している可能性があります。  拡張機能コードを一時停止しない場合は、次の操作を実行します。  

1.  DevTools の右上で、歯車アイコン (設定)**を選択します**。  **[設定]** ページが表示されます。  
1.  [リスト**設定] の下の**[リストの**無視] を選択します**。  [**フレームワーク ライブラリ コード]** セクション**が設定**されます。  
1.  [コンテンツ スクリプトを **ライブラリ コードとしてマークする] チェック ボックスをオン** にします。  
    
    :::image type="complex" source="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png" alt-text="[コンテンツ スクリプトをライブラリ コードとしてマークする] チェック ボックスをオンにする" lightbox="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png":::
       [コンテンツ スクリプト **をライブラリ コードとしてマークする] チェック ボックスをオン** にする  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "手順 4: コードをステップ実行する - DevTools アプリケーションの JavaScript のデバッグMicrosoft Edge開始|Microsoft Docs"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
