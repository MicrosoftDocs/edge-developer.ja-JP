---
description: Microsoft Edge DevTools を開くすべての方法。
title: Microsoft Edge DevTools を開く
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 770a9d3e7a0eaaecf322d2ca847d971d1ad11b9a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398267"
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

# <a name="open-microsoft-edge-devtools"></a>Microsoft Edge DevTools を開く  

さまざまなユーザーが DevTools UI の異なる部分に高速にアクセスする必要があるため、Microsoft Edge DevTools を開く方法は多数あります。  

## <a name="open-the-elements-panel-to-inspect-the-dom-or-css"></a>要素パネルを開き、DOM または CSS を検査する  

次の各タスクを使用すると、DOM ノードのスタイルまたは属性を調うことができます。

*   要素にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
*   `Control` + `Shift` + `C` \(Windows, Linux\) または `Command` + `Option` + `C` \(macOS\) を選択します。  詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevtoolsShortcutsIndex]。  

:::image type="complex" source="../media/bing-right-click-inspect.msft.png" alt-text="[検査] オプション" lightbox="../media/bing-right-click-inspect.msft.png":::
   [ **検査]** オプション  
:::image-end:::  

<!--Navigate to [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## <a name="open-the-console-panel"></a>コンソール パネルを開く  

次の各タスクを使用すると、コンソール[][DevtoolsConsoleIndex]ウィンドウを開き、ログに記録されたメッセージを表示したり、JavaScript を実行できます。  

*   次の手順を使用して、[コンソール] ウィンドウ [を開][DevtoolsConsoleIndex] きます。  
    
    1.  [DevTools を開きます](#open-microsoft-edge-devtools)。  
    1.  [コンソール] [ウィンドウを選択][DevtoolsConsoleIndex] します。  

*   コンソール ウィンドウに直接移動[するには][DevtoolsConsoleIndex] `Control` + `Shift` + `J` 、[\(Windows,Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevtoolsShortcutsIndex]。  

<!--Navigate to [Get Started With The Console][ConsoleGetStarted].  -->

## <a name="open-the-previous-panel"></a>前のパネルを開く  

開いた前のパネルに移動するには `Control` + `Shift` + `I` 、[\(Windows, Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。  詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevtoolsShortcutsIndex]。  

## <a name="open-microsoft-edge-devtools"></a>Microsoft Edge DevTools を開く  

DevTools を開く場合は、次のいずれかのオプションを使用します。  

*   Microsoft Edge UI を使用します。  
    
    1.  [その他**のツール開発者ツール**] の [設定] > `...` \( \)**アイコン**  >   **を選択します**。  
    
*   キーボードを使用します。  
    *   または `F12` `Control` + `Shift` + `I` \(Windows,Linux\) `Command` + `Option` + `I` または \(macOS\) を選択します。  

詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevtoolsShortcutsIndex]。  

:::image type="complex" source="../media/bing-customize-more-tools-developer-tools-transparent.msft.png" alt-text="Microsoft Edge メイン メニューから DevTools を開く" lightbox="../media/bing-customize-more-tools-developer-tools-transparent.msft.png":::
   Microsoft Edge メイン メニューから DevTools を開く  
:::image-end:::  

## <a name="auto-open-devtools-on-every-new-tab"></a>新しいタブごとに DevTools を自動開く  

新しいタブごとに DevTools を自動的に開くには、コマンド ラインから Microsoft Edge を開き、フラグを渡 `--auto-open-devtools-for-tabs` します。  

### [<a name="cmd-windows"></a>CMD (Windows)](#tab/cmd-Windows/)  

<a id="auto-open-devtools-command-line"></a>  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

### [<a name="powershell-windows"></a>PowerShell (Windows)](#tab/powershell-Windows/)  

<a id="auto-open-devtools-command-line"></a>  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

### [<a name="bash-macos"></a>bash (macOS)](#tab/bash-macos/)  

<a id="auto-open-devtools-command-line"></a>  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

### [<a name="bash-linux"></a>bash (Linux)](#tab/bash-linux/)  

<a id="auto-open-devtools-command-line"></a>  

```bash
microsoft-edge-dev --auto-open-devtools-for-tabs
```  

* * *  

## <a name="toggle-the-f12-keyboard-shortcut-on-or-off"></a>F12 キーボード ショートカットのオンとオフを切り替える  

`F12`DevTools を開くキーボード ショートカット設定を変更するには、次の操作を実行します。  

1.  [設定] のアイコン **を選択し、[設定]** の `...` [\( \) > **選択します**。  
1.  [ **検索の設定] に**「 」 と入力します `Developer Tools` 。  
    
    :::image type="complex" source="../media/settings-developer-tools-f12-on.msft.png" alt-text="[F12 キーが押された場合に DevTools を開く] 設定" lightbox="../media/settings-developer-tools-f12-on.msft.png":::
       **[F12 キーが押された場合に DevTools を開く] 設定**  
    :::image-end:::  
    
1.  **F12 キーが押されているときに [DevTools**を開く] を選択して、設定を \(または on\) に切り替えます。  キーボード ショートカットが DevTools を開くのを止めるには、設定を `F12` オフに切り替えます。  
    
    :::image type="complex" source="../media/settings-developer-tools-f12-off.msft.png" alt-text="[F12 キーを押した場合に DevTools を開く] 設定がオフになっている" lightbox="../media/settings-developer-tools-f12-off.msft.png":::
       **[F12 キーを押した場合に DevTools**を開く] 設定がオフになっている  
    :::image-end:::  
    
1.  トグルをオフに設定した後 `F12` 、DevTools が開かなくなったか確認します。  
    
    > [!NOTE]
    > **[F12**キーが押されているときに DevTools を開く] 設定をオフにした後、DevTools を開き、次のいずれかの操作を実行します。  
    > 
    > *   を選択します `Ctrl` + `Shift` + `I` 。  
    > *   コンテキスト メニュー \(右クリック\) を開き、[検査] > **します**。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "コンソールの概要 | Microsoft Docs"  
[DevtoolsShortcutsIndex]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

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
