---
description: Microsoft Edge DevTools を開くすべての方法。
title: Microsoft Edge DevTools を開く
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ce46f08be176fb58161355d67167c3e39043e83b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234374"
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

Microsoft Edge DevTools を開く方法は多数あります。さまざまなユーザーが DevTools UI の異なる部分に高速にアクセスする必要があるためです。  

## 要素パネルを開き、DOM または CSS を検査する  

次の各タスクを使用すると、DOM ノードのスタイルまたは属性を検査できます。

*   要素にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[検査] を選択 **します**。  
*   `Control` + `Shift` + `C` \(Windows,Linux\) または `Command` + `Option` + `C` \(macOS\) を選択します。  詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。  

:::image type="complex" source="../media/bing-right-click-inspect.msft.png" alt-text="[検査] オプション" lightbox="../media/bing-right-click-inspect.msft.png":::
   [ **検査]** オプション  
:::image-end:::  

<!--Navigate to [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## コンソール パネルを開く  

次の各タスクでは、コンソール ウィンドウを[][DevToolsConsoleIndex]開き、ログに記録されたメッセージを表示したり、JavaScript を実行できます。  

*   次の手順を使用して、コンソール ウィンドウ [を開][DevToolsConsoleIndex] きます。  
    
    1.  [DevTools を開きます](#open-microsoft-edge-devtools)。  
    1.  コンソール ウィンドウ [を選択][DevToolsConsoleIndex] します。  

*   コンソール ウィンドウに直接移動[するには][DevToolsConsoleIndex] `Control` + `Shift` + `J` 、\(Windows,Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。  

<!--See [Get Started With The Console][ConsoleGetStarted].  -->

## 前のパネルを開く  

開いた前のパネルに移動するには `Control` + `Shift` + `I` 、\(Windows,Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。  詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。  

## Microsoft Edge DevTools を開く  

次の各タスクでは、DevTools を開きます。  

*   次の手順を使用して、Microsoft Edge DevTools を開きます。  
    
    1.  アイコン  `...` \([設定とその **他] アイコン\) を** 選択します。  
    1.  [その **他のツール] を選択します**。  
    1.  [ **開発者ツール] を選択します**。  
    
*   Microsoft Edge DevTools を開くには `F12` `Control` + `Shift` + `I` 、\(Windows,Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。  詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。  

:::image type="complex" source="../media/bing-customize-more-tools-developer-tools-transparent.msft.png" alt-text="Microsoft Edge のメイン メニューから DevTools を開く" lightbox="../media/bing-customize-more-tools-developer-tools-transparent.msft.png":::
   Microsoft Edge のメイン メニューから DevTools を開く  
:::image-end:::  

## すべての新しいタブで DevTools を自動開く  

新しいタブごとに DevTools を自動的に開くには、コマンドラインから Microsoft Edge を開き、フラグを渡 `--auto-open-devtools-for-tabs` します。  

#### [CMD (Windows)](#tab/cmd-Windows/)  

<a id="auto-open-devtools-command-line"></a>  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

#### [PowerShell (Windows)](#tab/powershell-Windows/)  

<a id="auto-open-devtools-command-line"></a>  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

#### [bash (macOS)](#tab/bash-macos/)  

<a id="auto-open-devtools-command-line"></a>  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

#### [bash (Linux)](#tab/bash-linux/)  

<a id="auto-open-devtools-command-line"></a>  

```bash
microsoft-edge-dev --auto-open-devtools-for-tabs
```  

* * *  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleIndex]: ../console/index.md "コンソールの概要 | Microsoft Docs"  
[DevtoolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット - Microsoft Docs"  

<!--[ConsoleGetStarted]: /microsoft-edge/devtools-guide-chromium/console/get-started ""  -->  
<!--[GetStartedCSS]: /microsoft-edge/devtools-guide-chromium/css "CSS"  -->

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/open) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
