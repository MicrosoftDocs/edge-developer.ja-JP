---
title: Microsoft Edge DevTools を使ってローカルストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 72aee823d3a3143ae7399c7057f3b606bd1078c3
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10983521"
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





# Microsoft Edge DevTools を使ってローカルストレージを表示および編集する   



このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って、 [localstorage][MDNWindowsLocalStorage] のキーと値のペアを表示、編集、削除する方法について説明します。  

## LocalStorage のキーと値の表示   

1.  [ **アプリケーション** ] タブを選択して、[ **アプリケーション** ] パネルを開きます。  **マニフェスト**ウィンドウは既定で表示されます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       **マニフェスト**ウィンドウ  
    :::image-end:::  
    
1.  [ **ローカルストレージ** ] メニューを展開します。  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="[ローカルストレージ] メニュー" lightbox="../media/storage-application-local-storage.msft.png":::
       [ **ローカルストレージ** ] メニュー  
    :::image-end:::  
    
1.  ドメインを選択して、キーと値のペアを表示します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="ドメインのローカルストレージのキーと値のペア https://www.bing.com" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       `localStorage`ドメインのキーと値のペア `https://www.bing.com`  
    :::image-end:::  
    
1.  テーブルの行を選択して、テーブルの下に表示されているビューアーの値を確認します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="EventLogQueue_Online キーの値を表示する" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       キーの値を表示する `eventLogQueue_Online`  
    :::image-end:::  
    
## 新しい localStorage キーと値のペアを作成する   

1.  [ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。  
1.  表の空の部分をダブルクリックします。  DevTools で新しい行を作成し、 **キー** 列にカーソルをフォーカスします。  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分  
    :::image-end:::  
    
## ローカルストレージのキーまたは値を編集する   

1.  [ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。  
1.  キーまた**は値の列の**セルをダブルクリックし**て、その**キーまたは値を編集します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="ローカルストレージキーを編集する" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       キーを編集する `localStorage`  
    :::image-end:::  
    
## LocalStorage のキーと値のペアを削除する   

1.  [ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。  
1.  削除するキーと値のペアを選択します。  DevTools は、青色を強調表示して、選択されていることを示します。  
1.  キーを押す `Delete` か、[ **選択した** ものを削除] をクリックし ![ ます (選択した \ を削除 ][ImageDeleteIcon] )。  
    
## `localStorage`ドメインのすべてのキーと値のペアを削除する   

1.  [ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。  
1.  [ **すべてクリア** ] を選択し ![ ][ImageClearIcon] ます。  
    
## コンソールからローカルストレージを操作する   

JavaScript は**本体**で実行できますが、**本体**はページの javascript コンテキストにアクセスできるため、コンソールから操作することもでき `localStorage` ます。 **Console**  

1.  表示さ**JavaScript contexts**れて**Console** `localStorage` いるページ以外のドメインのキーと値のペアにアクセスする場合は、javascript コンテキストメニューを使って本体の javascript コンテキストを変更します。  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="本体の JavaScript のコンテキストを変更する" lightbox="../media/storage-console-local-storage.msft.png":::
       本体の JavaScript のコンテキストを変更する  
    :::image-end:::  
    
1.  `localStorage`JavaScript と同じように、コンソールで式を実行します。  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="コンソールからローカルストレージを操作する" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       `localStorage`**コンソール**から操作する  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "ウィンドウ。 localStorage |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
