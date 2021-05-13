---
description: '[ローカル] ウィンドウと [コンソール] を使用して localStorage Storage編集する方法。'
title: DevTools を使用してローカル Storageを表示Microsoft Edge編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5088a1b9d7ab2b92051d099e76b8b07bbd5db5f8
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565051"
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
# <a name="view-and-edit-local-storage-with-microsoft-edge-devtools"></a>DevTools を使用してローカル ストレージを表示Microsoft Edge編集する  

このガイドでは[、devTools][MicrosoftEdgeDevTools]のMicrosoft Edgeを使用して[localStorage][MDNWindowsLocalStorage]のキーと値のペアを表示、編集、および削除する方法を示します。  

## <a name="view-localstorage-keys-and-values"></a>localStorage キーと値の表示  

1.  [アプリケーション] **タブを** 選択して、[アプリケーション] ツール **を開** きます。  既定 **では、[マニフェスト** ] ウィンドウが表示されます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       [ **マニフェスト]** ウィンドウ  
    :::image-end:::  
    
1.  [ローカル]**メニュー Storage**展開します。  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="[ローカル] Storageメニュー" lightbox="../media/storage-application-local-storage.msft.png":::
       [**ローカル] Storage**メニュー  
    :::image-end:::  
    
1.  キーと値のペアを表示するドメインを選択します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="ドメインの localStorage キーと値の https://www.bing.com ペア" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       ドメイン `localStorage` のキーと値のペア `https://www.bing.com`  
    :::image-end:::  
    
1.  テーブルの行を選択して、テーブルの下のビューアーで値を表示します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="キーの値をeventLogQueue_Onlineする" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       キーの値を表示 `eventLogQueue_Online` する  
    :::image-end:::  
    
## <a name="create-a-new-localstorage-key-value-pair"></a>新しい localStorage キーと値のペアを作成する  

1.  [ドメインの localStorage キーと値のペアを表示します](#view-localstorage-keys-and-values)。  
1.  テーブルの空の部分をダブルクリックします。  DevTools は新しい行を作成し、[キー] 列にカーソルを **移動** します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分  
    :::image-end:::  
    
## <a name="edit-localstorage-keys-or-values"></a>localStorage キーまたは値の編集  

1.  [ドメインの localStorage キーと値のペアを表示します](#view-localstorage-keys-and-values)。  
1.  [キー] 列または [値] 列の**セル****をダブルクリック**して、そのキーまたは値を編集します。  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="localStorage キーの編集" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       キーの `localStorage` 編集  
    :::image-end:::  
    
## <a name="delete-localstorage-key-value-pairs"></a>localStorage キーと値のペアを削除する  

1.  [ドメインの `localStorage` キーと値のペアを表示します](#view-localstorage-keys-and-values)。  
1.  削除するキーと値のペアを選択します。  DevTools は青色で強調表示され、選択されているかどうかを示します。  
1.  キーを `Delete` 選択するか、[ **選択した \(** Delete ![ Selected \) を削除する] ](../media/delete-icon.msft.png) を選択します。  
    
## <a name="delete-all-localstorage-key-value-pairs-for-a-domain"></a>ドメインのすべての `localStorage` キーと値のペアを削除する  

1.  [ドメインの `localStorage` キーと値のペアを表示します](#view-localstorage-keys-and-values)。  
1.  [ **すべてクリア]** \( ![ Clear All ](../media/clear-icon.msft.png) \) を選択します。  
    
## <a name="interact-with-localstorage-from-the-console"></a>コンソールから localStorage を操作する  

コンソールで JavaScript を実行できます。**** また、コンソールはページ**** の JavaScript コンテキストにアクセスできますので、コンソールから操作 `localStorage` **できます**。  

1.  表示される**ページ以外の**ドメインのキーと値のペアにアクセスする**** 場合は、JavaScript コンテキスト メニューを使用してコンソールの JavaScript コンテキストを `localStorage` 変更します。  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="コンソールの JavaScript コンテキストを変更する" lightbox="../media/storage-console-local-storage.msft.png":::
       コンソールの JavaScript コンテキストを変更する  
    :::image-end:::  
    
1.  JavaScript と同じように、コンソールで式 `localStorage` を実行します。  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="コンソールから localStorage を操作する" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       コンソールからの `localStorage` **操作**  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

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
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
