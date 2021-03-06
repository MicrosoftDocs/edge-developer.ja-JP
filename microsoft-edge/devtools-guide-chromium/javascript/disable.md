---
description: コマンド メニューを開き、[JavaScript を無効にする] コマンドを実行します。
title: DevTools で JavaScript をMicrosoft Edgeする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c9b5605aff5680ff0f44386c4a69e4c9f7c08cc8
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564162"
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
# <a name="disable-javascript-with-microsoft-edge-devtools"></a>DevTools で JavaScript をMicrosoft Edgeする  

ブラウザーで JavaScript がサポートされていない場合の Web ページの表示方法を確認するには、JavaScript を一時的にオフにします。

JavaScript をオフにした場合の Web ページの表示方法と動作を調べるには、次のアクションを実行します。  

1.  [DevTools Microsoft Edge開きます][DevToolsOpen]。  
1.  `Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="コマンド メニュー" lightbox="../media/javascript-console-command.msft.png":::
       **コマンド メニュー**  
    :::image-end:::  
    
1.  入力を開始 `javascript` し **、[JavaScript を無効**にする] を選択し、コマンド `Enter` を実行する場合に選択します。  JavaScript が無効になりました。  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="コマンド メニューで [JavaScript を無効にする] を選択します。" lightbox="../media/javascript-console-command-javascript.msft.png":::
       コマンド **メニューで [JavaScript** を無効にする] **を選択します。**  
    :::image-end:::  
    
    [ソース] の横にある黄色の **警告** アイコンは、JavaScript が無効になっていることを通知します。  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text="[ソース] の横にある警告アイコン" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       [ソース] の横にある **警告アイコン**  
    :::image-end:::  
    
DevTools を開いている限り、JavaScript はタブで無効なままです。  

ページを更新して、読み込み中に Web ページが JavaScript に依存するかどうかと方法を確認できます。  

JavaScript を再び有効にするには、次のアクションを実行します。  

*   コマンド メニュー **を再度開** き、コマンドを実行 `Enable JavaScript` します。  
*   DevTools を閉じます。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
