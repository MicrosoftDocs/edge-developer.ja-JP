---
description: Microsoft Edge DevTools で使用されていない JavaScript と CSS コードを検索して分析する方法について説明します。
title: Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 08c4daaabd30296b53ad57a81caa0e7b155a4fc9
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125189"
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

# Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける  

Microsoft Edge の DevTools の [カバレッジ] タブは、使用されていない JavaScript と CSS コードを見つけるのに役立ちます。  使用されていないコードを削除すると、ページの読み込みが速くなり、モバイルユーザーの携帯電話のデータが保存される可能性があります。  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="コードカバレッジの分析" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   コードカバレッジの分析  
:::image-end:::  

> [!WARNING]
> 使用されていないコードの検索は比較的簡単です。  ただし、コードベースをリファクタリングして、各ページが必要な JavaScript と CSS を確実に出荷することが難しい場合があります。  このガイドでは、コードベースをリファクターして使用されていないコードを回避する方法については説明しません。これらの refactors はテクノロジスタックに依存しているためです。  

## 概要  

使用されていない JavaScript または CSS は、web 開発での一般的な問題です。  たとえば、ページで [ブートストラップボタンコンポーネント][BootstrapButtons] を使用するとします。  Button コンポーネントを使用するには、次のように HTML のブートストラップスタイルシートへのリンクを追加する必要があります。  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

このスタイルシートには、button コンポーネントのコードは含まれていません。  このファイルには、 **すべて** のブートストラップコンポーネントの CSS が含まれています。  ただし、他のブートストラップコンポーネントは使用していません。  このため、ページでは不要な CSS をダウンロードしようとしています。  このエクストラ CSS は、次のような理由で問題になります。  

*   余分なコードを使用すると、ページの読み込み速度が遅くなります。  <!--See [Render-Blocking CSS][render].  -->  
*   ユーザーがモバイルデバイスでページにアクセスすると、追加のコードによって携帯電話のデータが使用されます。  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## [カバレッジ] タブを開く  

1.  [コマンドメニューを開き][DevToolsCommandMenu]ます。  
1.  入力を開始し、[ `coverage` **カバレッジの表示** ] コマンドを選択して、コマンドを `Enter` 実行します。  [ **補充** ] タブが **引き出し**で開きます。  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="コードカバレッジの分析" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       [ **カバレッジ** ] タブ  
    :::image-end:::  
    
## コードカバレッジの記録  

1.  [ **カバレッジ** ] タブで、次のいずれかのボタンをクリックします。  
    *   **Start Instrumenting Coverage And Reload Page** ![ ][ImageReloadIcon] ページの読み込みに必要なコードを確認するには、[インストルメント化の開始] と [ページの再読み込み] を選びます。  
    *   **Instrument Coverage** ![ ][ImageRecordIcon] ページを操作した後で使用されるコードを確認する場合は、[インストルメント化の対象] ([インストルメントのカバレッジ]) を選択します。  
1.  コードカバレッジの記録を停止する場合は **、[インストルメントの実装を停止し、結果を表示** する ( ![ インストルメント化の停止と結果の表示)] を選び ][ImageStopIcon] ます。  
    
## コードカバレッジの分析  

[ **カバレッジ** ] タブの表には、分析されたリソースと、各リソース内で使用されているコードの量が表示されます。  [ **ソース** ] パネルで行をクリックしてそのリソースを開き、使用されているコードと未使用コードの行ごとの内訳を確認します。  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="コードカバレッジの分析" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   コードカバレッジレポート  
:::image-end:::  

*   **Url**列は、分析されたリソースの url です。  
*   [ **Type** ] 列には、リソースに CSS、JavaScript、またはその両方が含まれているかどうかが示されます。  
*   **Total bytes**列は、リソースの合計サイズ (バイト単位) です。  
*   **未使用バイト**列は、使用されなかったバイト数です。  
*   最後の名前が付いていない列は、[ **合計のバイト** 数] 列と [ **未使用のバイト数** ] 列の視覚エフェクトです。  バーの赤い部分は未使用のバイトです。  緑のセクションは、バイトを使用しています。  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageReloadIcon]: ../media/reload-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png  
[ImageStopIcon]: ../media/stop-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "ボタン-ブートストラップ"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/coverage/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
