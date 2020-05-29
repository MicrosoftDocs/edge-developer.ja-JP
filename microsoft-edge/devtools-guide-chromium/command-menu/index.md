---
title: Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 748008b347a3498008748b9c3f9ecc1445c47f12
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601748"
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





# Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する   

  

コマンドメニューを使うと、Microsoft Edge の DevTools UI をすばやく移動し、 [JavaScript を無効][JavascriptDisable]にするなどの一般的な作業を実行することができます。  コマンド[パレット][VisualStudioCodeUICommandPalette]と呼ばれる Visual Studio コードと同様の機能 (コマンドメニューの元のインスピレーション) に精通していることがあります。  

> ##### 図 1  
> コマンドメニューを使用して JavaScript を無効にする  
> ![コマンドメニューを使用して JavaScript を無効にする][ImageDisableJS]  

## コマンドメニューを開く   

`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。 または、[ **DevTools のカスタマイズと制御**] をクリックし、[ `...` **コマンドの実行**] を選択します。  

> ##### 図 2  
> コマンドの実行  
> ![コマンドの実行][ImageRunCommand]  

## 使用可能なその他の操作を表示する   

[コマンドメニューを[開く]](#open-the-command-menu)でアウトライン表示されたワークフローを使用した場合、コマンドメニューが開き、コマンドメニューの `>` テキストボックスの先頭に文字が表示されます。  

> ##### 図 3  
> コマンド文字  
> ![コマンド文字][ImageCommandCharacter]  

`>`文字と入力を削除し `?` て、コマンドメニューから利用可能なその他の操作を確認します。  

> ##### 図 4  
> その他の使用可能なアクション  
> ![その他の使用可能なアクション][ImageActions]  

 



<!-- image links -->  

[ImageDisableJS]: /microsoft-edge/devtools-guide-chromium/media/command-menu-run-command-java.msft.png "図 1: コマンドメニューを使用して JavaScript を無効にする"  
[ImageRunCommand]: /microsoft-edge/devtools-guide-chromium/media/command-menu-options-run-command.msft.png "図 2: コマンドの実行"  
[ImageCommandCharacter]: /microsoft-edge/devtools-guide-chromium/media/command-menu-run-command.msft.png "図 3: コマンド文字"  
[ImageActions]: /microsoft-edge/devtools-guide-chromium/media/command-menu-help.msft.png "図 4: 使用可能なその他の操作"  

<!-- links -->  

[JavascriptDisable]: /microsoft-edge/devtools-guide-chromium/javascript/disable "Microsoft Edge DevTools で JavaScript を無効にする"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "コマンドパレット-Visual Studio コード UI"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/command-menu/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
