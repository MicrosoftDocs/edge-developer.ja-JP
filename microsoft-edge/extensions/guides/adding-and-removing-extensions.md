---
description: 拡張機能の追加と削除、および [アドレス] バーの横にある拡張機能のボタンを移動する方法について説明します。
title: 拡張機能の追加と削除
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、css、javascript、開発者、拡張機能
ms.custom: seodec18
ms.localizationpriority: high
ms.openlocfilehash: aeebc0f18d6b4a743c790571b8287a209233e73f
ms.sourcegitcommit: 1e33cd41e5afb2e6dbdc19353011ff6c2b019f9c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2020
ms.locfileid: "10866079"
---
# Microsoft Edge の拡張機能の追加、移動、および削除  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

Microsoft Edge の拡張機能のサポートが、**Windows 10 Anniversary Update** に追加されました。 Microsoft Edge 拡張機能を開発していて、それを読み込ませる場合、または既に所有していて削除したい場合は、次の手順を参照してください。
また、ブラウザーで拡張機能アイコンの場所を変更する方法についても説明します。

## 拡張機能を追加する

1. Microsoft Edgeを開き、アドレスバーに 'about:flags' と入力します。

2. [**拡張機能の開発者機能を有効にする**] チェックボックスをオンにします。

   ![「about:flags」 で開発者機能をオンにする。](./../media/sideload-aboutflags.png)
   > [!NOTE]
   > Windows 10 Anniversary Update 以降のバージョンをお持ちでない場合は、このオプションはご利用いただけません。

3. メニューを開くには、 **[その他] の (...)** を選択します。

   ![[その他] ボタン](./../media/morebutton.png)  

4. メニューから [**拡張機能**] を選択します。

5. [**拡張機能の読み込み**] ボタンを選択します。

   ![読み込む拡張機能の選択](./../media/sideload-load-extension.png)

6. 拡張機能のフォルダーに移動し、[**フォルダーの選択**] ボタンを選択します。
   ![読み込む拡張機能フォルダーを選択する](./../media/sideload-select-extension.png)
   > [!NOTE]
   > 拡張機能の読み込み中にエラーメッセージが表示される場合は、「[トラブルシューティング](./../troubleshooting.md)」 のページを参照してください。


**準備が完了しました。 拡張機能が Microsoft Edge の拡張機能ウィンドウに表示されます。**

![拡張機能ウィンドウの拡張機能](./../media/sideload-extension-installed.png)

> [!NOTE]
> 未署名の拡張機能は、その後の Microsoft Edge の起動時に自動的にオフになります。 ブラウザーがアイドル状態になると (約10秒間動作しなくなったとき)、次の通知がウィンドウの下部に表示されます。 ![危険な通知](./../media/riskynotification.png) 署名されていない拡張機能をオンにするには、[設定を有効にする] をクリックします。



## [拡張機能] ボタンの移動
拡張機能の設定によっては、**[その他] の (...)** メニューに表示されることがあります。

   ![[アクション] メニュー](./../media/browseraction.png)  


簡単にアクセスできるように、このメニューからボタンを移動する場合:

1. [拡張機能] ボタンを右クリックします。

2. 「**アドレス バーの隣にボタンを表示**」 を選択します。

   ![[アクション] メニュー](./../media/browseraction_contextmenu.png)  

または、[拡張機能の詳細] ページで次の操作を行います。

1. [拡張機能] ボタンをクリックします。
2. 「**アドレス バーの隣にボタンを表示**」 をオンに切り替えます。

   ![[表示] ボタンをオンに切り替える](./../media/show-button-toggle.png)

> [!NOTE]
> ボタンを右クリックして 「**アドレスバーの隣に表示**」 の選択を解除するか、拡張機能の詳細ページで 「**アドレス バーの隣にボタンを表示**」 をオフに切り替えることで、いつでも **[その他] (...)** メニューに戻すことができます。


## 拡張機能を削除する

1. Microsoft Edge を開きます。

2. メニューを開くには、 **[その他] の (...)** を選択します。

3. メニューから [**拡張機能**] を選択します。

4. 削除する拡張機能を右クリックし、[**削除**] を選択するか、または拡張機能を選択して、[**削除**] をクリックします。

   ![[アクション] メニュー](./../media/remove.png)  

**拡張機能が Microsoft Edge のリストに表示されなくなります。**
