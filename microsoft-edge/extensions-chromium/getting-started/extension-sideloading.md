---
description: ブラウザーで拡張機能をサイドローディングしてテストする
title: 拡張機能をサイドロードする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, Web 開発, html, css, javascript, developer, extensions
ms.openlocfilehash: 7070878b9608e6d239179078390f2315e0b289a1
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104775"
---
# 拡張機能をサイドロードする

開発中に、Microsoft Edge \(Chromium\) ブラウザーを使用して、拡張機能を安全に実行およびデバッグできます。 ブラウザーで拡張機能をローカルにサイドロードすることで、拡張機能を実行してテストできます。 この記事では、拡張機能をサイドロードする方法について説明Microsoft Edge。

拡張機能をサイドロードするには、次の手順を実行します。

1.  ブラウザーの上部にある 3 つのドットを選択し、[拡張機能] を選択してページ `edge://extensions` **を開きます**。

       :::image type="complex" source="./media/part1-threedots.png" alt-text="[ページ] edge://extensions 開く":::
          [ページ] edge://extensions 開く :::image-end:::

1.  [拡張機能の管理] ページで、ページの左下にあるトグルを使用して開発者 `edge://extensions` モードを有効にします。 ****

       :::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="開発者モードを有効にする":::
          開発者モードを有効にする :::image-end:::

1.  拡張機能を初めてインストールする場合は、[アンパックの読み込 **み] を選択します**。  拡張ソース ファイルを含むディレクトリの入力を求めるメッセージが表示されます。  拡張機能は、ストアからインストールされた拡張機能と同様に、ブラウザーにインストールされます。  

       :::image type="complex" source="./media/part1-installed-extension.png" alt-text="サイドロードされた拡張機能を示すインストール済み拡張機能ページ":::
          サイドロードされた拡張機能を示すインストール済み拡張機能ページ :::image-end:::

開発中に、次のタスクを実行する必要がある場合があります。
* 拡張機能を更新します。 に移動し `edge://extensions` 、[再読み込み] **を選択** して拡張機能を更新します。  
* ブラウザーから拡張機能を削除します。 に移動 `edge://extensions` し、拡張機能 `Remove` を選択します。