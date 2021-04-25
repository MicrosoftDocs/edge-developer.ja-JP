---
description: Microsoft Edge DevTools で使用されていない JavaScript コードと CSS コードを見つけて分析する方法。
title: Microsoft Edge DevTools の [カバレッジ] パネルで未使用の JavaScript と CSS コードを検索する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a8fccdcabf03f3894a9a11246b90db4686fd953e
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519318"
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

# <a name="find-unused-javascript-and-css-code-with-the-coverage-panel-in-microsoft-edge-devtools"></a>Microsoft Edge DevTools の [カバレッジ] パネルで未使用の JavaScript コードと CSS コードを検索する  

Microsoft **Edge DevTools** の [カバレッジ] パネルを使用すると、使用されていない JavaScript コードと CSS コードを見つけるのに役立ちます。  未使用のコードを削除すると、ページの読み込み速度が上がり、モバイル ユーザーの携帯電話データが保存される場合があります。  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="コード 範囲の分析" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   コード 範囲の分析  
:::image-end:::  

> [!WARNING]
> 使用されていないコードを見つけるのは比較的簡単です。  ただし、コードベースをリファクタリングして、必要な JavaScript と CSS のみを各ページに提供するのは難しい場合があります。  このガイドでは、これらのリファクタリングがテクノロジ スタックに大きな依存を持つため、コードベースをリファクタリングして未使用のコードを回避する方法については取り上げない。  

## <a name="overview"></a>概要  

未使用の JavaScript または CSS の配布は、Web 開発で一般的な問題です。  たとえば、ページでブートストラップ ボタン コンポーネントを [使用すると][BootstrapButtons] します。  ボタン コンポーネントを使用するには、HTML のブートストラップ スタイルシートへのリンクを次のように追加する必要があります。  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

このスタイルシートには、ボタン コンポーネントのコードが含まれるだけではありません。  すべてのブートストラップ **コンポーネントの** CSS が含まれている。  ただし、他のブートストラップ コンポーネントは使用していない。  したがって、ページは必要ない CSS の束をダウンロードしています。  この追加の CSS は、次の理由で問題です。  

*   余分なコードを使用すると、ページの読み込み速度が低下します。  <!--Navigate to [Render-Blocking CSS][render].  -->  
*   ユーザーがモバイル デバイス上のページにアクセスした場合、追加のコードは携帯データを使用します。  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## <a name="open-the-coverage-panel"></a>[カバレッジ] パネルを開く  

1.  [コマンド メニューを開きます][DevToolsCommandMenu]。  
1.  入力を開始 `coverage` し、[カバレッジの表示] コマンド **を** 選択し、コマンド `Enter` を実行する場合に選択します。  [ **引き出** し] に [カバレッジ] パネルが **開きます**。  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="[カバレッジ] パネル" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       [ **カバレッジ]** パネル  
    :::image-end:::  
    
## <a name="record-code-coverage"></a>レコード コード範囲  

1.  [カバレッジ] パネルで、次のいずれかのボタン **を選択** します。  
    *   ページ **の読み込みに** 必要なコードを確認する場合は、[インストルメントカバレッジの開始とページの再読み込み]\(インストルメントカバレッジの開始とページの再読み込み ![ ](../media/reload-icon.msft.png) \) を選択します。  
    *   ページ **を操作した** 後に使用するコードを確認する場合は、[Instrument Coverage \( Instrument ![ Coverage ](../media/record-icon.msft.png) \) ] を選択します。  
1.  コード **カバレッジの記録を停止する場合は、[** インストルメントカバレッジの停止と結果の表示] \( Stop Instrumenting Coverage and Show Results ![ ](../media/stop-icon.msft.png) \) を選択します。  
    
## <a name="analyze-code-coverage"></a>コード範囲の分析  

[カバレッジ] パネル **の表** には、分析されたリソースと、各リソース内で使用されるコードの量が表示されます。  [ソース] ツールでリソースを開**** く行を選択し、使用されているコードと未使用のコードの 1 行に 1 行の内訳を確認します。  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="コード カバレッジ レポート" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   コード カバレッジ レポート  
:::image-end:::  

*   **[URL]** 列は、分析されたリソースの URL です。  
*   **[Type]** 列には、リソースに CSS、JavaScript、または両方が含まれているかどうかを示します。  
*   [ **合計バイト数]** 列は、リソースの合計サイズ (バイト単位) です。  
*   [ **未使用のバイト数** ] 列は、使用されていないバイト数です。  
*   最後の名前のない列は、[合計バイト数]**** 列と [未使用バイト] 列**を視覚化**します。  バーの赤いセクションは未使用のバイトです。  緑色のセクションはバイト数を使用します。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "[Microsoft Edge DevTools コマンド] メニューメニューを使用してコマンドを実行|Microsoft Docs"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "ボタン - ブートストラップ"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/coverage/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
