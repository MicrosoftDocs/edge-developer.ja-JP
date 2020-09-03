---
description: セッション記憶域のウィンドウと本体を使って、sessionStorage の表示と編集を行う方法について説明します。
title: Microsoft Edge DevTools を使ってセッションストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 24fca3fd3a068f3b2ffbe4ec1c23e6b80b968953
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993549"
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





# Microsoft Edge DevTools を使ってセッションストレージを表示および編集する   

  

このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って、キーと値のペアを表示、編集、削除する方法について説明し [`sessionStorage`][MDNSessionStorage] ます。  

## SessionStorage のキーと値の表示   

1.  [ **アプリケーション** ] タブを選択して、[ **アプリケーション** ] パネルを開きます。  **マニフェスト**ウィンドウは既定で表示されます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       **マニフェスト**ウィンドウ  
    :::image-end:::  
    
1.  [ **セッションストレージ** ] メニューを展開します。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage.msft.png" alt-text="[セッション記憶域] メニュー" lightbox="../media/storage-application-storage-session-storage.msft.png":::
       [ **セッション記憶域** ] メニュー  
    :::image-end:::  
    
1.  ドメインを選択して、キーと値のペアを表示します。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain.msft.png" alt-text=""SessionStorage" キーと値のペア" lightbox="../media/storage-application-storage-session-storage-domain.msft.png":::
       `sessionStorage`キーと値のペア  
    :::image-end:::  
    
1.  テーブルの行を選択して、テーブルの下に表示されているビューアーの値を確認します。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png" alt-text="X sid キーの値を表示する" lightbox="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png":::
       キーの値を表示する `x-sid`  
    :::image-end:::  
    
## 新しい sessionStorage のキーと値のペアを作成する   

1.  [ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。  
1.  表の空の部分をダブルクリックします。  DevTools で新しい行を作成し、 **キー** 列にカーソルをフォーカスします。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png":::
       新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分  
    :::image-end:::  
    
## SessionStorage のキーまたは値を編集する   

1.  [ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。  
1.  キーまた**は値の列の**セルをダブルクリックし**て、その**キーまたは値を編集します。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png" alt-text="セッションストレージキーを編集する" lightbox="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png":::
       キーを編集する `sessionStorage`  
    :::image-end:::  
    
## セッションストレージのキーと値のペアを削除する   

1.  [ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。  
1.  削除するキーと値のペアを選択します。  DevTools は、青色を強調表示して、選択されていることを示します。  
1.  キーを押す `Delete` か、[ **選択した** ものを削除] をクリックし ![ ます (選択した \ を削除 ][ImageDeleteIcon] )。  
    
## ドメインのすべてのセッション記憶域のキーと値のペアを削除する   

1.  [ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。  
1.  [ **すべてクリア** ] を選択し ![ ][ImageClearIcon] ます。  
    
## コンソールからセッションストレージを操作する   

JavaScript は**本体**で実行できるため、**本体**はページの javascript コンテキストにアクセスできるため、コンソールから操作することができ `sessionStorage` ます。 **Console**  

1.  使用しているページ以外のドメインのキーと値のペアにアクセスする場合は、 **javascript のコンテキスト** メニューを使って **本体** の javascript コンテキストを変更し `sessionStorage` ます。  
    
    :::image type="complex" source="../media/storage-console-domain-selection.msft.png" alt-text="本体の JavaScript のコンテキストを変更する" lightbox="../media/storage-console-domain-selection.msft.png":::
       本体の JavaScript のコンテキストを変更する  
    :::image-end:::  
    
1.  `sessionStorage`JavaScript と同じように、コンソールで式を実行します。  
    
    :::image type="complex" source="../media/storage-console-session-storage-keys.msft.png" alt-text="コンソールからセッションストレージを操作する" lightbox="../media/storage-console-session-storage-keys.msft.png":::
       `sessionStorage`**コンソール**から操作する  
    :::image-end:::  
    
<!--  
   

  
-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "セッションストレージ |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
