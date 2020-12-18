---
description: ローカル ストレージ ウィンドウとコンソールを使用して localStorage を表示および編集する方法について説明します。
title: Microsoft Edge DevTools を使ったローカル ストレージの表示と編集
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c68f11b8ba2c10a0792f10acf5c5ededf2ad8e8d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231189"
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

# Microsoft Edge DevTools を使用してローカル ストレージを表示および編集する  

このガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使用して [localStorage][MDNWindowsLocalStorage] キーと値のペアを表示、編集、削除する方法について説明します。  

## localStorage キーと値を表示する  

1.  [アプリケーション **] タブ** を選択して、アプリケーション ツール **を開** きます。  マニフェスト **ウィンドウ** は既定で表示されます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       マニフェスト**ウィンドウ**  
    :::image-end:::  
    
1.  [ローカル ストレージ **] メニューを展開** します。  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="[ローカル ストレージ] メニュー" lightbox="../media/storage-application-local-storage.msft.png":::
       [ **ローカル ストレージ]** メニュー  
    :::image-end:::  
    
1.  キーと値のペアを表示するドメインを選択します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="ドメインの localStorage キーと値の https://www.bing.com ペア" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       ドメイン `localStorage` のキーと値の `https://www.bing.com` ペア  
    :::image-end:::  
    
1.  テーブルの行を選択して、テーブルの下のビューアーに値を表示します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="キーの値をeventLogQueue_Onlineする" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       キーの値を表示 `eventLogQueue_Online` する  
    :::image-end:::  
    
## 新しい localStorage キーと値のペアを作成する  

1.  [ドメインの localStorage キーと値のペアを表示します](#view-localstorage-keys-and-values)。  
1.  テーブルの空の部分をダブルクリックします。  DevTools によって新しい行が作成され、カーソルが [キー] 列に **表示** されます。  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分  
    :::image-end:::  
    
## localStorage キーまたは値を編集する  

1.  [ドメインの localStorage キーと値のペアを表示します](#view-localstorage-keys-and-values)。  
1.  [キー] 列または****[値] 列のセルを**ダブルクリック**して、そのキーまたは値を編集します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="localStorage キーを編集する" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       キーを編集 `localStorage` する  
    :::image-end:::  
    
## localStorage のキーと値のペアを削除する  

1.  [ドメインの `localStorage` キーと値のペアを表示します](#view-localstorage-keys-and-values)。  
1.  削除するキーと値のペアを選択します。  DevTools では、青色が強調表示され、選択されている状態が示されます。  
1.  Select the `Delete` key or choose Delete **Selected** \( ![ Delete Selected ][ImageDeleteIcon] \).  
    
## ドメインのすべての `localStorage` キーと値のペアを削除する  

1.  [ドメインの `localStorage` キーと値のペアを表示します](#view-localstorage-keys-and-values)。  
1.  Choose **Clear All** \( Clear All ![ ][ImageClearIcon] \).  
    
## コンソールから localStorage を操作する  

コンソールで JavaScript を実行できます。**** また、コンソールはページ**** の JavaScript コンテキストにアクセスできるので、コンソールから操作 `localStorage` **できます**。  

1.  表示される**ページ以外**のドメインのキーと値のペアにアクセスする**** 場合は、JavaScript コンテキスト メニューを使用してコンソールの JavaScript コンテキストを `localStorage` 変更します。  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="コンソールの JavaScript コンテキストを変更する" lightbox="../media/storage-console-local-storage.msft.png":::
       コンソールの JavaScript コンテキストを変更する  
    :::image-end:::  
    
1.  JavaScript `localStorage` と同じように、コンソールで式を実行します。  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="コンソールから localStorage を操作する" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       コンソールから `localStorage` 操作 **する**  
    :::image-end:::  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "Window.localStorage |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
