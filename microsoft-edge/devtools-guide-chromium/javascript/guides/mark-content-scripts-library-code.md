---
title: コンテンツスクリプトをライブラリコードとしてマークする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fe34d8f2fb656283b1821441162b93d47d51d24e
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581790"
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





# <span data-ttu-id="629eb-103">コンテンツスクリプトをライブラリコードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="629eb-103">Mark Content Scripts as Library Code</span></span>   



<span data-ttu-id="629eb-104">Microsoft Edge DevTools の**ソース**パネルを使用して[コードをステップ実行][DevToolsJavascriptStepThroughCode]するときに、認識できないコードを一時停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="629eb-104">When using the **Sources** panel of Microsoft Edge DevTools to [step through code][DevToolsJavascriptStepThroughCode], sometimes you pause on code that you do not recognize.</span></span>  <span data-ttu-id="629eb-105">インストールした Microsoft Edge 拡張機能のいずれかのコードで一時停止している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="629eb-105">You probably paused on code for one of the Microsoft Edge Extensions that you installed.</span></span>  <span data-ttu-id="629eb-106">次の手順を実行して、拡張コードに一時停止しないようにします。</span><span class="sxs-lookup"><span data-stu-id="629eb-106">Complete the following steps to not pause on extension code.</span></span>  

1.  <span data-ttu-id="629eb-107">DevTools を開き、[ **devtools のカスタマイズと制御**] を選択し `...` て、[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="629eb-107">Open DevTools, select **Customize and control DevTools** `...` and click **Settings**.</span></span>  <span data-ttu-id="629eb-108">または、を押して**設定**を開くこともでき `F1` ます。</span><span class="sxs-lookup"><span data-stu-id="629eb-108">You may also open **Settings** by pressing `F1`.</span></span>  

1.  <span data-ttu-id="629eb-109">[**ライブラリコード**] タブを選択すると、[**設定**] の**フレームワークライブラリコード**セクションが開きます。</span><span class="sxs-lookup"><span data-stu-id="629eb-109">Select the **Library code** tab which opens the **Framework Library Code** section of **Settings**.</span></span>  
1.  <span data-ttu-id="629eb-110">[**コンテンツスクリプトをライブラリコードとしてマーク**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="629eb-110">Enable the **Mark content scripts as Library code** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="629eb-111">図 1</span><span class="sxs-lookup"><span data-stu-id="629eb-111">Figure 1</span></span>  
    > <span data-ttu-id="629eb-112">[**コンテンツスクリプトをライブラリコードとしてマーク**する] チェックボックスを有効にする</span><span class="sxs-lookup"><span data-stu-id="629eb-112">Enable the **Mark content scripts as Library code** checkbox</span></span>  
    > ![[コンテンツスクリプトをライブラリコードとしてマークする] チェックボックスを有効にする][ImageMarkContentScriptsLibraryCode]  

<!--## Feedback   -->  



<!-- image links -->  

[ImageMarkContentScriptsLibraryCode]: /microsoft-edge/devtools-guide-chromium/media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png "図 1: [コンテンツスクリプトをライブラリコードとしてマークする] チェックボックスを有効にする"  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "手順 4: コードをステップ実行する-「Microsoft Edge DevTools で JavaScript のデバッグを開始する」をご覧ください。"  

> [!NOTE]
> <span data-ttu-id="629eb-116">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="629eb-116">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="629eb-117">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome devtools & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="629eb-117">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="629eb-119">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="629eb-119">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
