---
title: Microsoft Edge DevTools を開く
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 48f80ea9f85bd3509f2ba3d834f99c25247c0761
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601888"
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
   limitations under the License. -->





# Microsoft Edge DevTools を開く   



さまざまなユーザーが DevTools UI のさまざまな部分にすばやくアクセスする必要があるため、Microsoft Edge DevTools を開くにはさまざまな方法があります。  

## [要素] パネルを開いて、DOM または CSS を検査する   

DOM ノードのスタイルまたは属性を検査する場合は、要素を右クリックして [**検査**] を選びます。  

> ##### 図 1  
> [**検査**] オプション  
> ![[検査] オプション][ImageInspectOption]  

または、 `Control` + `Shift` + `C` \ (Windows \) または `Command` + `Option` + `C` \ (macOS \) を押します。  

<!--See [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## コンソールパネルを開いて、ログに記録されたメッセージを表示したり、JavaScript を実行したりする   

`Control` + `Shift` + `J` コンソールパネルに直接ジャンプするには、\ (Windows \) または `Command` + `Option` + `J` \ **Console** (macOS \) を押します。  

<!--See [Get Started With The Console][ConsoleGetStarted].  -->

## 開いていた最後のパネルを開く   

`Control` + `Shift` + `I` \ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を押します。  

## Microsoft Edge のメインメニューから DevTools を開く  

[**設定とその他] をクリックし (Alt + F \)** `...` 、[**その他のツール**  >  **開発者ツール**] を選択します。  

> ##### 図 2  
> Microsoft Edge のメインメニューから DevTools を開く  
> ![Microsoft Edge のメインメニューから DevTools を開く][ImageOpenFromMain]  

## すべての新しいタブで DevTools を自動で開く   

コマンドラインから Microsoft Edge を開き、フラグを渡し `--auto-open-devtools-for-tabs` ます。  

Windows \ (CMD \):  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

Windows \ (PowerShell \):  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

Os  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

 



<!-- image links -->  

[ImagesMainIcon]: /microsoft-edge/devtools-guide-chromium/media/main-menu-icon.msft.png  

[ImageInspectOption]: /microsoft-edge/devtools-guide-chromium/media/bing-right-click-inspect.msft.png "図 1: [検査] オプション"  
[ImageOpenFromMain]: /microsoft-edge/devtools-guide-chromium/media/bing-customize-more-tools-developer-tools-transparent.msft.png "図 2: Microsoft Edge のメインメニューから DevTools を開く"  

<!-- links -->  

<!--[ConsoleGetStarted]: /microsoft-edge/devtools-guide-chromium/console/get-started ""  -->  
<!--[GetStartedCSS]: /microsoft-edge/devtools-guide-chromium/css "CSS"  -->

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/open)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
