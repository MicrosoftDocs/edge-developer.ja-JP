---
title: Microsoft Edge DevTools を使ってローカルストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f7e187662aec8231f2cc4e99baab1b4b8e2048ad
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612012"
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



このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って、キーと値のペアを表示、編集、削除する方法について説明し [`localStorage`][MDNWindowsLocalStorage] ます。  

## LocalStorage のキーと値の表示   

1.  [**アプリケーション**] タブを選択して、[**アプリケーション**] パネルを開きます。  **マニフェスト**ウィンドウは既定で表示されます。  
    
    > ##### 図 1  
    > マニフェストウィンドウ  
    > ![マニフェストウィンドウ][ImageManifest]  

1.  [**ローカルストレージ**] メニューを展開します。  
    
    > ##### 図 2  
    > [**ローカルストレージ**] メニューには2つのドメインが表示され `https://business.bing.com` ます。 `https://www.bing.com`  
    > ![[ローカルストレージ] メニュー][ImageLocalStorageMenu]  

1.  ドメインを選択して、キーと値のペアを表示します。  
    
    > ##### 図 3  
    > `localStorage`ドメインのキーと値のペア `https://www.bing.com`  
    > ![ドメインのローカルストレージのキーと値のペア https://www.bing.com][ImageLocalStorage]  

1.  テーブルの行を選択して、テーブルの下に表示されているビューアーの値を確認します。  
    
    > ##### 図 4  
    > キーの値を表示する `eventLogQueue_Online`  
    > ![EventLogQueue_Online キーの値を表示する][ImageLocalStorageViewer]  

## 新しい `localStorage` キーと値のペアを作成する   

1.  [ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。  
1.  表の空の部分をダブルクリックします。  DevTools で新しい行を作成し、**キー**列にカーソルをフォーカスします。  
    
    > ##### 図 5  
    > 新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分  
    > ![新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分][ImageLocalStorageCreate]  

## `localStorage`キーまたは値を編集する   

1.  [ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。  
1.  キーまた**は値の列の**セルをダブルクリックし**て、その**キーまたは値を編集します。  
    
    > ##### 図 6  
    > キーを編集する `localStorage`  
    > ![ローカルストレージキーを編集する][ImageLocalStorageEdit]  

## `localStorage`キーと値のペアを削除する   

1.  [ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。  
1.  削除するキーと値のペアを選択します。  DevTools は、青色を強調表示して、選択されていることを示します。  

1.  キーを押すか、[選択した `Delete` 削除の削除] をクリックし**Delete Selected** ![ ][ImageDeleteIcon] ます。  

## `localStorage`ドメインのすべてのキーと値のペアを削除する   

1.  [ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。  

1.  [**すべて**クリア] を選択し ![ ][ImageClearIcon] ます。  

## `localStorage`コンソールから操作する   

JavaScript は**本体**で実行できますが、**本体**はページの javascript コンテキストにアクセスできるため、コンソールから操作することもでき `localStorage` ます。 **Console**  

1.  表示さ**JavaScript contexts**れて**Console** `localStorage` いるページ以外のドメインのキーと値のペアにアクセスする場合は、javascript コンテキストメニューを使って本体の javascript コンテキストを変更します。  
    
    > ##### 図 7  
    > **本体**の JavaScript コンテキストの変更  
    > ![本体の JavaScript コンテキストの変更][ImageJSContext]  

1.  `localStorage`JavaScript と同じように、コンソールで式を実行します。  
    
    > ##### 図 8  
    > `localStorage`**コンソール**からの操作  
    > ![コンソールからローカルストレージを操作する][ImageLocalStorageConsole]  

 



<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageLocalStorageMenu]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage.msft.png "図 2: [ローカルストレージ] メニュー"  
[ImageLocalStorage]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-view-key-value.msft.png "図 3: ドメインのローカルストレージのキーと値のペア https://www.bing.com"  
[ImageLocalStorageViewer]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-view-key-value-selected.msft.png "図 4: eventLogQueue_Online キーの値を表示する"  
[ImageLocalStorageCreate]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-new-key-value.msft.png "図 5: 新しいキーと値のペアを作成するために、表の空の部分をダブルクリックする"  
[ImageLocalStorageEdit]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-edit-key-value.msft.png "図 6: ローカルストレージキーを編集する"  
[ImageJSContext]: /microsoft-edge/devtools-guide-chromium/media/storage-console-local-storage.msft.png "図 7: 本体の JavaScript コンテキストの変更"  
[ImageLocalStorageConsole]: /microsoft-edge/devtools-guide-chromium/media/storage-console-local-storage-interaction.msft.png "図 8: コンソールからローカルストレージを操作する"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "ウィンドウ。 localStorage |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
