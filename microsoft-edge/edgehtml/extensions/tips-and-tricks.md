---
description: Microsoft Edge 拡張機能に関する便利なヒントとコツについて説明します。
title: ヒントとコツ |拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者, 拡張機能
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cd512085f13b76c5a8e474301ef296612eeb0414
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234572"
---
# ヒントとテクニック  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

Microsoft Edge 拡張機能を現在使用している場合でも、既に公開している場合でも、次のヒントやコツが役立つ可能性があります。

## Microsoft Store で拡張機能への直接リンクを取得する

Windows デベロッパー センター ダッシュボードでは、Microsoft Store で拡張機能への直接リンクを見つけることができます。 このリンクは、拡張機能を宣伝して共有する場合に役立ちます。

Windows デベロッパー センターにログインし、ダッシュボードから拡張機能に移動すると、アプリ ID ページの [ストア プロトコル] リンク行にリンクが **表示** されます。

![ストア プロトコル リンク](./media/store-link.png)
 
## Microsoft Store ポリシーに従っている必要があります

拡張機能を作成する場合は [、Microsoft Store](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx)ポリシーで強調表示されている Microsoft Store に提出するためのガイドラインに注意してください。 
 
Microsoft Edge 拡張機能には、ここに示すポリシーの追加セットも用意 [されています](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)。

## Microsoft Store での拡張機能の検出可能性を向上させる

拡張機能の申請にキーワードを追加して、検索を通じて検出可能性を向上させることができます。 たとえば、"Microsoft Edge Extensions" や "name of my extension" などです。 

これは、拡張機能の説明セクションの下の Windows デベロッパー センターで行います。 これらのキーワードは、拡張機能がサポートする言語ごとに追加する必要があります。

![レビューへの応答の送信 - キーワード](./media/keywords.png)

## Microsoft Store への申請を自動化する

新しい Microsoft Store 申請 API を使うと、アプリ/ゲーム、アドオン (アプリ内購入)、パッケージ フライトを REST API を通じて更新できます。 ドキュメントとサンプル [を確認するか、](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) オープン ソース [の申請 API VSTS](https://github.com/Microsoft/windows-dev-center-vsts-extension) 拡張機能を使用して開始してください。

## Windows フィードバック Hub を使用して、フィードバック/レビュー/機能の要求を収集する

ユーザーに Windows フィードバック Hub サブカテゴリへのリンクを埋め込むには、そのリンクを埋め込む必要があります。 このリンクは、次の形式で作成する必要があります。 

```text
feedback-hub://?tabid=2&appid=<PFN>!App
```  

拡張機能のパッケージ `<PFN>` ファミリ名に置き換える必要があります。 これは、Windows デベロッパー **センターの拡張機能** の [アプリ ID] セクションにあります。

## 評価とレビューを確認する

定期的にログインして、ユーザーのレビューと評価を確認します。 UWP アプリには現在のユーザー市場に関する情報しか表示されませんが、Windows デベロッパー センターにログインすると、すべての市場の平均評価が表示されます。

## ユーザー レビューに応答する

Windows デベロッパー センターのダッシュボードから Microsoft Store のユーザー レビューに応答できます。 拡張機能に移動し、[分析] で [レビュー] **を選択します**。 各レビューの下にリンクが表示され、顧客に直接回答できます。 このコミュニケーション チャネルを使用すると、フィードバックや解決策を提供したり、レビューに感謝のメッセージを送信することができます。

![レビューへの応答の送信](./media/reviews.png)
