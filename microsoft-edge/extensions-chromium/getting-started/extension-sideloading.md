---
description: ブラウザーで拡張機能をサイドローディングしてテストする
title: 内線番号をサイドローディング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: 7070878b9608e6d239179078390f2315e0b289a1
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104775"
---
# 内線番号をサイドローディングする

開発時には、Microsoft Edge \ (Chromium \) ブラウザーを使って、拡張機能を安全に実行してデバッグすることができます。 ブラウザーで拡張機能をローカルにサイドローディングすることで、拡張機能を実行してテストすることができます。 この記事では、Microsoft Edge に拡張機能をサイドローディングする方法について説明します。

内線番号をサイドローディングするには、次の手順を実行します。

1.  `edge://extensions`ブラウザーの上部にある3つの点を選んで、[**拡張機能**] を選択してページを開きます。

       :::image type="complex" source="./media/part1-threedots.png" alt-text="[Edge://extensions] ページを開く":::
          [Edge://extensions] ページを開く :::image-end:::

1.  [拡張機能の管理] ページで `edge://extensions` 、ページの左下にあるトグルを使用して **開発者モード** を有効にします。

       :::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="[Edge://extensions] ページを開く":::
          開発者モードを有効にする :::image-end:::

1.  拡張機能を初めてインストールする場合は、[解凍された **読み込み**] を選びます。  拡張機能のソースファイルを含むディレクトリの入力を求められます。  拡張子は、ストアからインストールされた拡張機能と同様に、ブラウザーにインストールされます。  

       :::image type="complex" source="./media/part1-installed-extension.png" alt-text="[Edge://extensions] ページを開く":::
          サイドローディング拡張機能が表示されている [インストールされた拡張機能] ページ :::image-end:::

開発中に、次のタスクを実行することが必要になる場合もあります。
* 拡張機能を更新します。 に移動し `edge://extensions` 、[ **再読み込み** ] を選択して拡張機能を更新します。  
* ブラウザーから拡張機能を削除します。 に移動して `edge://extensions` 、拡張機能を選択し `Remove` ます。