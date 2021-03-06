---
description: コマンド メニューを開く方法、コマンドを実行する方法、その他のアクションを確認する方法などのガイド。
title: DevTools コマンド メニューでコマンドMicrosoft Edge実行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 973b440a27b0c4c06ba118fc09e4162a8fa346e8
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564491"
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
# <a name="run-commands-with-the-microsoft-edge-devtools-command-menu"></a>DevTools コマンド メニューでコマンドMicrosoft Edge実行する  

コマンド メニューを使用すると、DevTools UI をMicrosoft Edge、JavaScript の無効化などの一般的なタスクを実行[できます][JavascriptDisable]。  コマンド メニューの元のインスピレーションMicrosoft Visual Studioコマンド パレットと呼ばれるコードの[][VisualStudioCodeUICommandPalette]同様の機能についてよく知っているかもしれません。  

:::image type="complex" source="../media/command-menu-run-command-java.msft.png" alt-text="コマンド メニューを使用して JavaScript を無効にする" lightbox="../media/command-menu-run-command-java.msft.png":::
   コマンド メニューを使用して JavaScript を無効にする  
:::image-end:::  

## <a name="open-the-command-menu"></a>コマンド メニューを開く  

`Control` + `Shift` + `P` \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。 または、[ **コマンドの実行] で [DevTools** `...` \( \) のカスタマイズと制御> **選択します**。  

:::image type="complex" source="../media/command-menu-options-run-command.msft.png" alt-text="コマンドの実行" lightbox="../media/command-menu-options-run-command.msft.png":::
   コマンドの実行  
:::image-end:::  

## <a name="display-other-available-actions"></a>その他の使用可能なアクションを表示する  

[コマンド メニューを開く][](#open-the-command-menu)で説明されているワークフローを使用すると、コマンド メニューが開き、[コマンド メニュー] テキスト ボックスに文字があらかじめ `>` 入力されています。  

:::image type="complex" source="../media/command-menu-run-command.msft.png" alt-text="コマンド文字" lightbox="../media/command-menu-run-command.msft.png":::
   コマンド文字  
:::image-end:::  

コマンド メニュー `>` から使用できる `?` 他のアクションを表示するには、文字と種類を削除します。  

:::image type="complex" source="../media/command-menu-help.msft.png" alt-text="その他の使用可能なアクション" lightbox="../media/command-menu-help.msft.png":::
   その他の使用可能なアクション  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[JavascriptDisable]: ../javascript/disable.md "DevTools ファイルを使用Microsoft Edge JavaScript を無効|Microsoft Docs"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "コマンド パレット - Visual Studio Code UI"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
