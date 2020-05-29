---
description: 拡張機能を追加および削除する方法、およびアドレスバーの横にある拡張機能のボタンを移動する方法について説明します。
title: 拡張機能の追加と削除
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者、拡張機能
ms.custom: seodec18
localization_priority: Priority
ms.openlocfilehash: fdc6950962e7ce7e0a720d0bafa7e2c63ebd7098
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569498"
---
# Microsoft Edge の拡張機能の追加、移動、削除  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

Microsoft Edge の拡張機能のサポートは、 **Windows 10 の記念日更新プログラム**で導入されています。 Microsoft Edge 拡張機能を開発していて、それを読み込む必要がある場合、または既に所有している場合は、次の手順を実行します。
また、ブラウザーで拡張機能アイコンの場所を変更する方法についても説明します。

## 拡張機能の追加

1. Microsoft Edge を開き、"about: flags" をアドレスバーに入力します。

2. [**拡張開発者向け機能を有効にする**] チェックボックスをオンにします。

   ![バージョン情報: フラグ開発者向け機能を有効にする](./../media/sideload-aboutflags.png)
   > [!NOTE]
   > Windows 10 記念日更新プログラムを持っていない場合、このオプションは使用できません。

3. [**その他 (...)** ] を選択してメニューを開きます。

   ![[その他] ボタン](./../media/morebutton.png)  

4. メニューから [**拡張機能**] を選択します。

5. [**拡張機能の読み込み**] ボタンを選択します。

   ![[読み込み拡張機能の選択]](./../media/sideload-load-extension.png)

6. 拡張機能のフォルダーに移動し、 **[フォルダーの選択**] ボタンを選択します。
   ![読み込む拡張フォルダーの選択](./../media/sideload-select-extension.png)
   > [!NOTE]
   > 拡張機能の読み込み時にエラーメッセージが表示される場合は、「[トラブルシューティング](./../troubleshooting.md)」ページを参照してください。


**お手続きが完了しました。 これで、Microsoft Edge の [拡張機能] ウィンドウに、拡張機能が表示されます。**

![拡張機能ウィンドウの拡張機能](./../media/sideload-extension-installed.png)

> [!NOTE]
> 署名されていない拡張子は、Microsoft Edge の以降の起動時に自動的にオフになります。 ブラウザーでアイドル状態になると (約10秒間の操作が完了すると)、ウィンドウの下部に次の通知が表示されます。 ![危険な通知 ](./../media/riskynotification.png) 未署名の拡張子を有効にするには、[このままオンにする] をクリックします。



## [拡張] ボタンの移動
拡張機能の設定によっては、[**詳細 (...)** ] メニューに表示されることがあります。

   ![[アクション] メニュー](./../media/browseraction.png)  


簡単にアクセスできるように、このメニューからボタンを移動する場合は、次の操作を行います。

1. [拡張機能] ボタンを右クリックします。

2. **アドレスバーの横にある [表示] ボタン**を選択します。

   ![[アクション] メニュー](./../media/browseraction_contextmenu.png)  

または、[拡張機能の詳細] ページから行うこともできます。

1. [拡張機能] ボタンをクリックします。
2. [**アドレスバー] の横にある [表示] ボタン**をオンにします。

   ![ボタン切り替えボタン](./../media/show-button-toggle.png)

> [!NOTE]
> ボタンを右クリックして [アドレスバー **] の****横に**ある [表示] をクリックするか、[アドレスバー] の横にある [表示] をクリックして、[アドレスバー] の横にある [**表示] ボタン**をクリックし、[アドレスバー] の横にある [表示] をオンにします。


## 拡張機能の削除

1. Microsoft Edge を開きます。

2. [**その他 (...)** ] を選択してメニューを開きます。

3. メニューから [**拡張機能**] を選択します。

4. 削除する拡張機能を右クリックし、[**削除**] を選択するか、拡張機能を選択して [**削除**] ボタンをクリックします。

   ![[アクション] メニュー](./../media/remove.png)  

**拡張機能は、Microsoft Edge の一覧に表示されなくなります。**
