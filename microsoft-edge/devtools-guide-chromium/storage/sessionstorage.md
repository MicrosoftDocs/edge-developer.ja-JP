---
description: セッション ストレージ ウィンドウとコンソールを使用して sessionStorage を表示および編集する方法。
title: Microsoft Edge DevTools を使用してセッション ストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cf00d71302e7a1f16ba1cceaa17c9380245d12f8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398008"
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

# <a name="view-and-edit-session-storage-with-microsoft-edge-devtools"></a>Microsoft Edge DevTools を使用してセッション ストレージを表示および編集する  

このガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使用して [sessionStorage][MDNSessionStorage] キーと値のペアを表示、編集、および削除する方法について説明します。  

## <a name="view-sessionstorage-keys-and-values"></a>sessionStorage キーと値の表示  

1.  [アプリケーション] **タブを** 選択して、[アプリケーション] ツール **を開** きます。  既定 **では、[マニフェスト** ] パネルが表示されます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       [ **マニフェスト]** ウィンドウ  
    :::image-end:::  
    
1.  [セッション ストレージ **] メニューを展開** します。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage.msft.png" alt-text="[セッション ストレージ] メニュー" lightbox="../media/storage-application-storage-session-storage.msft.png":::
       [ **セッション ストレージ]** メニュー  
    :::image-end:::  
    
1.  キーと値のペアを表示するドメインを選択します。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain.msft.png" alt-text="sessionStorage キーと値のペア" lightbox="../media/storage-application-storage-session-storage-domain.msft.png":::
       キー `sessionStorage` と値のペア  
    :::image-end:::  
    
1.  テーブルの行を選択して、テーブルの下のビューアーで値を表示します。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png" alt-text="x-sid キーの値を表示する" lightbox="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png":::
       キーの値を表示 `x-sid` する  
    :::image-end:::  
    
## <a name="create-a-new-sessionstorage-key-value-pair"></a>新しい sessionStorage キーと値のペアを作成する  

1.  [ドメインの sessionStorage キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。  
1.  テーブルの空の部分をダブルクリックします。  DevTools は新しい行を作成し、[キー] 列にカーソルを **移動** します。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png":::
       新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分  
    :::image-end:::  
    
## <a name="edit-sessionstorage-keys-or-values"></a>sessionStorage キーまたは値の編集  

1.  [ドメインの sessionStorage キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。  
1.  [キー] 列または [値] 列の**セル****をダブルクリック**して、そのキーまたは値を編集します。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png" alt-text="sessionStorage キーの編集" lightbox="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png":::
       キーの `sessionStorage` 編集  
    :::image-end:::  
    
## <a name="delete-sessionstorage-key-value-pairs"></a>sessionStorage キーと値のペアを削除する  

1.  [ドメインの `sessionStorage` キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。  
1.  削除するキーと値のペアを選択します。  DevTools は青色で強調表示され、選択されているかどうかを示します。  
1.  キーを `Delete` 選択するか、[ **選択した \(** Delete ![ Selected \) を削除する] ][ImageDeleteIcon] を選択します。  
    
## <a name="delete-all-sessionstorage-key-value-pairs-for-a-domain"></a>ドメインのすべての sessionStorage キーと値のペアを削除する  

1.  [ドメインの `sessionStorage` キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。  
1.  [ **すべてクリア]** \( ![ Clear All ][ImageClearIcon] \) を選択します。  
    
## <a name="interact-with-sessionstorage-from-the-console"></a>コンソールから sessionStorage を操作する  

コンソールで JavaScript を実行**** できます。また、コンソール**** はページの JavaScript コンテキストにアクセスできますので、コンソールから操作 `sessionStorage` **できます**。  

1.  現在の**ページ以外**のドメインのキーと値のペアにアクセスする**** 場合は、JavaScript コンテキスト メニューを使用してコンソールの JavaScript コンテキスト `sessionStorage` を変更します。  
    
    :::image type="complex" source="../media/storage-console-domain-selection.msft.png" alt-text="コンソールの JavaScript コンテキストを変更する" lightbox="../media/storage-console-domain-selection.msft.png":::
       コンソールの JavaScript コンテキストを変更 **する**  
    :::image-end:::  
    
1.  JavaScript `sessionStorage` と同**** じ条件式をコンソールで実行します。  
    
    :::image type="complex" source="../media/storage-console-session-storage-keys.msft.png" alt-text="コンソールから sessionStorage を操作する" lightbox="../media/storage-console-session-storage-keys.msft.png":::
       コンソールからの `sessionStorage` **操作**  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (クロム) 開発者向け|Microsoft Docs"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "Window.sessionStorage |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
