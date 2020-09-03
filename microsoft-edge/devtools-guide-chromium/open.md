---
description: Microsoft Edge DevTools を開くすべての方法。
title: Microsoft Edge DevTools を開く
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ffc05a1eff2cdb7f3020a7dbb853a7520a0502dd
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993598"
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

次の各タスクによって、DOM ノードのスタイルまたは属性を調べることができます。

*   要素にマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[ **検査**] を選びます。  
*   `Control` + `Shift` + `C` \ (Windows \) または `Command` + `Option` + `C` \ (macOS \) を押します。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  

:::image type="complex" source="./media/bing-right-click-inspect.msft.png" alt-text="* * 検査 * * オプション" lightbox="./media/bing-right-click-inspect.msft.png":::
   [ **検査** ] オプション  
:::image-end:::  

<!--See [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## コンソールパネルを開く  

次の各タスクを使用すると、 [コンソール][DevToolsConsoleIndex] ウィンドウを開いて、ログに記録されたメッセージを表示したり、JavaScript を実行したりすることができます。  

*   [コンソール][DevToolsConsoleIndex]ウィンドウを開くには、次の手順を実行します。  
    
    1.  [DevTools を開き](#open-microsoft-edge-devtools)ます。  
    1.  [ [コンソール][DevToolsConsoleIndex] ] ウィンドウを選択します。  

*   [コンソール][DevToolsConsoleIndex]ウィンドウに直接ジャンプするには、 `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  

<!--See [Get Started With The Console][ConsoleGetStarted].  -->

## 前のパネルを開く  

開いていた前のパネルにジャンプするに `Control` + `Shift` + `I` は、\ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を押します。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  

## Microsoft Edge DevTools を開く  

次の各タスクを使用すると、DevTools を開くことができます。  

*   Microsoft Edge DevTools を開くには、次の手順を使用します。  
    
    1.  `...`アイコン (**設定など**のアイコン) を選びます。  
    1.  [ **その他のツール**] を選びます。  
    1.  [ **開発者ツール**] を選択します。  
    
*   Microsoft Edge devtools を開くに `F12` は、または `Control` + `Shift` + `I` \ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を押します。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  

:::image type="complex" source="./media/bing-customize-more-tools-developer-tools-transparent.msft.png" alt-text="Microsoft Edge のメインメニューから DevTools を開く" lightbox="./media/bing-customize-more-tools-developer-tools-transparent.msft.png":::
   Microsoft Edge のメインメニューから DevTools を開く  
:::image-end:::  

## すべての新しいタブで DevTools を自動で開く  

すべての新しいタブで DevTools を自動的に開くには、コマンドラインから Microsoft Edge を開き、 `--auto-open-devtools-for-tabs` フラグを渡します。  

#### [CMD (Windows)](#tab/cmd-windows/)  

<a id="selenium-tools-install"></a>  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

#### [PowerShell (Windows)](#tab/powershell-windows/)  

<a id="selenium-tools-install"></a>  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

#### [bash (macOS)](#tab/bash-macos/)  

<a id="selenium-tools-install"></a>  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

* * *  

<!-- links -->  

[DevToolsConsoleIndex]: ./console/index.md "本体の概要 |Microsoft ドキュメント"  
[DevtoolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット-Microsoft ドキュメント"  

<!--[ConsoleGetStarted]: /microsoft-edge/devtools-guide-chromium/console/get-started ""  -->  
<!--[GetStartedCSS]: /microsoft-edge/devtools-guide-chromium/css "CSS"  -->

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/open) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
