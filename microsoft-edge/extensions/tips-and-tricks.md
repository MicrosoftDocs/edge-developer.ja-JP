---
description: Microsoft Edge extensions に関する便利なヒントとテクニックについて説明します。
title: 拡張機能-ヒントとテクニック
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: db15aa49649432a6c4400b4e6830501c40485a83
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569427"
---
# ヒント  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

現在 Microsoft Edge 拡張機能を使用している場合も、既に公開している場合も、次のヒントとテクニックが役に立つことがあります。

## Microsoft Store の内線番号への直接リンクを取得する
Windows デベロッパーセンターダッシュボードでは、Microsoft Store の内線番号への直接リンクを見つけることができます。 このリンクは、お客様の内線番号の広告や共有に役立ちます。


Windows デベロッパーセンターにログインし、ダッシュボードを使用して内線番号に移動した後、[アプリ id] ページで、[**ストアプロトコル] リンク**行に次のリンクが表示されます。

![ストアプロトコルリンク](./media/store-link.png)
 
## Microsoft Store のポリシーに従っていることを確認する
拡張機能を作成する場合は、Microsoft store の[ポリシー](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx)で強調表示されている microsoft store に提出するためのガイドラインに留意してください。 
 
Microsoft Edge extensions には、次のような追加のポリシーのセットも用意[されています](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)。

## Microsoft Store で拡張機能の発見性を向上させる

拡張機能の申請にキーワードを追加して、検索によって検索結果を imporove することができます。 たとえば、"Microsoft Edge Extensions" と "内線名" のように指定します。 

これは、Windows デベロッパーセンターの拡張機能の [説明] セクションで行うことができます。 これらのキーワードは、拡張機能でサポートされているすべての言語に対して追加する必要があります。

![レビューに返信を送信する](./media/keywords.png)

## Microsoft ストアへの申請を自動化する
新しい Microsoft ストア申請 API を使用すると、microsoft ストアへの申請を自動化および合理化することができます。これにより、アプリ/ゲーム、アドオン (アプリ内購入)、およびパッケージフライトを REST API で更新できます。 [ドキュメントとサンプル](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services)をご覧になるか、またはオープンソースの[送信 API の VSTS 拡張機能](https://github.com/Microsoft/windows-dev-center-vsts-extension)を使って作業を開始してください。

## Windows フィードバック Hub を使用して、フィードバック/レビュー/機能のリクエストを収集する

拡張機能をポイントするリンクを埋め込むことにより、ユーザーを拡張機能の Windows フィードバック Hub サブカテゴリに導くことができます。 このリンクは、次の形式を使用して作成する必要があります。 

`feedback-hub://?tabid=2&appid=<PFN>!App`

`<PFN>`パッケージファミリ名の内線番号に置き換える必要があります。 これは、Windows デベロッパーセンターの拡張機能の [**アプリ id** ] セクションにあります。

## 評価とレビューを確認する
定期的にログインして、ユーザーのレビューと評価を確認します。 UWP アプリには、現在のユーザー市場に関する情報しかありませんが、Windows デベロッパーセンターにログインすると、すべての市場での平均評価が表示されます。

## ユーザーレビューに返信する
Microsoft ストアのユーザーレビューには、Windows デベロッパーセンターのダッシュボードを通じて返信することができます。 拡張機能に移動し、[分析] で [**レビュー**] を選択します。 顧客に直接返信できるようにするための各レビューの下にリンクが表示されます。 この通信チャネルを使用すると、フィードバック、解決策、またはレビューを送信することができます。

![レビューに返信を送信する](./media/reviews.png)
