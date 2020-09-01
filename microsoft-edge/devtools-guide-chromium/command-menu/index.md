---
title: Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 09adaadd6f62710b219911f69fbe39ba8edfb61a
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982554"
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

  

コマンドメニューを使うと、Microsoft Edge の DevTools UI をすばやく移動し、 [JavaScript を無効][JavascriptDisable]にするなどの一般的な作業を実行することができます。  コマンド [パレット][VisualStudioCodeUICommandPalette]と呼ばれる Visual Studio コードと同様の機能 (コマンドメニューの元のインスピレーション) に精通していることがあります。  

:::image type="complex" source="../media/command-menu-run-command-java.msft.png" alt-text="コマンドメニューを使用して JavaScript を無効にする" lightbox="../media/command-menu-run-command-java.msft.png":::
   コマンドメニューを使用して JavaScript を無効にする  
:::image-end:::  

## コマンドメニューを開く   

`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。 または、[ **DevTools のカスタマイズと制御**] をクリックし、[ `...` **コマンドの実行**] を選択します。  

:::image type="complex" source="../media/command-menu-options-run-command.msft.png" alt-text="コマンドの実行" lightbox="../media/command-menu-options-run-command.msft.png":::
   コマンドの実行  
:::image-end:::  

## 使用可能なその他の操作を表示する   

[ [コマンドメニューを開く](#open-the-command-menu)] でアウトライン表示されたワークフローを使用している場合、コマンドメニューが開き、 `>` コマンドメニューのテキストボックスに前に "延期" という文字が表示されます。  

:::image type="complex" source="../media/command-menu-run-command.msft.png" alt-text="コマンド文字" lightbox="../media/command-menu-run-command.msft.png":::
   コマンド文字  
:::image-end:::  

`>`文字と入力を削除し `?` て、コマンドメニューから利用可能なその他の操作を確認します。  

:::image type="complex" source="../media/command-menu-help.msft.png" alt-text="その他の使用可能なアクション" lightbox="../media/command-menu-help.msft.png":::
   その他の使用可能なアクション  
:::image-end:::  

 



<!-- links -->  

[JavascriptDisable]: ../javascript/disable.md "Microsoft Edge DevTools で JavaScript を無効にする |Microsoft ドキュメント"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "コマンドパレット-Visual Studio コード UI"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
