---
title: Microsoft Edge DevTools で JavaScript を無効にする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f3838b4e8eccf83aaa71be35ff477ec56cbe7455
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581811"
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





# Microsoft Edge DevTools で JavaScript を無効にする   



JavaScript が無効になっているときに、web ページの外観と動作を確認するには、次の操作を行います。  

1.  [Microsoft Edge DevTools を開き][DevToolsOpen]ます。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。  
    
    > ##### 図 1  
    > コマンドメニュー  
    > ![コマンドメニュー][ImageCommandMenu]  
    
1.  入力を開始し、[JavaScript を無効にする] を `javascript` 選択して、キーを押してコマンドを実行し**Disable JavaScript** `Enter` ます。  JavaScript が無効になりました。  
    
    > ##### 図 2  
    > コマンドメニューの [ **JavaScript を無効**にする] を選択する  
    > ![コマンドメニューの [JavaScript を無効にする] を選択する][ImageDisableJS]  
    
    [**ソース**] の横にある黄色の警告アイコンは、JavaScript が無効になっていることを通知します。  
    
    > ##### 図 3  
    > **ソース**の横にある警告アイコン  
    > ![ソースの横にある警告アイコン][ImageDisableJSWarning]  

DevTools が開いている限り、JavaScript はこのタブでは無効のままです。  

読み込み中にページが JavaScript に依存するかどうかとその方法を確認するには、ページの再読み込みが必要になることがあります。  

JavaScript を再び有効にするには:  

*   もう一度**コマンドメニュー**を開き、コマンドを実行し `Enable JavaScript` ます。  
*   DevTools を閉じます。  

## フィードバック   



<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-command.msft.png "図 1: コマンドメニュー"  
[ImageDisableJS]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-command-javascript.msft.png "図 2: コマンドメニューの [JavaScript を無効にする] を選ぶ"  
[ImageDisableJSWarning]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-javascript-disabled-warning.msft.png "図 3: ソースの隣にある警告アイコン"  

<!-- links -->  

[DevToolsOpen]: ../open.md "Microsoft Edge DevTools を開く"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/disable)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
