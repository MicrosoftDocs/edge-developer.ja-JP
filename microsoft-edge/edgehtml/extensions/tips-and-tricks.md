---
description: Microsoft Edge 拡張機能に関する便利なヒントとコツについて説明します。
title: ヒントと|拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, developer, extensions
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8a5ea19152f5524d86d17d6f978c677c45f8f3a8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399352"
---
# <a name="tips-and-tricks"></a>ヒントとテクニック  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

Microsoft Edge 拡張機能で現在作業している場合でも、既に公開済みである場合でも、次のヒントとコツが役立つ場合があります。  

## <a name="get-a-direct-link-to-your-extension-in-the-microsoft-store"></a>Microsoft Store で拡張機能への直接リンクを取得する  

Windows デベロッパー センター ダッシュボードでは、Microsoft Store で拡張機能への直接リンクを見つけることができます。  このリンクは、広告や拡張機能の共有に役立ちます。  

Windows デベロッパー センターにログインし、ダッシュボードを介して拡張機能に移動すると、[アプリ ID] ページの [ストア プロトコル] リンク行にリンク **が表示** されます。  

![ストア プロトコル リンク](./media/store-link.png)  
 
## <a name="make-sure-youre-following-the-microsoft-store-policy"></a>Microsoft Store ポリシーに従っている必要があります。  

拡張機能を作成する場合は [、Microsoft](/windows/uwp/publish/store-policies)ストア ポリシーで強調表示されている Microsoft Store に提出するためのガイドラインに注意してください。  
 
Microsoft Edge 拡張機能には、ここに示すポリシーの追加セットも用意 [されています](/windows/uwp/publish/store-policies#pol_10_12)。  

## <a name="improve-your-extensions-discoverability-in-the-microsoft-store"></a>Microsoft Store での拡張機能の検出可能性を向上させる  

拡張機能の申請にキーワードを追加して、検索を通じて検出可能性を向上させることができます。  たとえば、 `Microsoft Edge Extensions` および `name of my extension` .  

これは、拡張機能の説明セクションの Windows デベロッパー センターで行います。  これらのキーワードは、拡張機能でサポートされている言語ごとに追加する必要があります。  

![キーワードを使用してレビューに応答を送信する](./media/keywords.png)  

## <a name="automate-your-submission-to-the-microsoft-store"></a>Microsoft Store への申請を自動化する  

新しい Microsoft Store 申請 API を使用すると、アプリ/ゲーム、アドオン \(アプリ内購入\)、REST API を使用してフライトをパッケージ化することで、Microsoft Store への申請を自動化および合理化できます。  ドキュメントとサンプル [を確認するか、](/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) オープンソースの申請 [API VSTS](https://github.com/Microsoft/windows-dev-center-vsts-extension) 拡張機能を使用して開始します。  

## <a name="use-the-windows-feedback-hub-to-gather-feedbackreviewsfeature-requests"></a>Windows フィードバック ハブを使用してフィードバック/レビュー/機能要求を収集する  

ユーザーに対して、それをポイントするリンクを埋め込み、拡張機能の Windows Feedback Hub サブカテゴリにユーザーを指示できます。  このリンクは、次の形式で作成する必要があります。  

```text
feedback-hub://?tabid=2&appid=<PFN>!App
```  

拡張機能のパッケージ `<PFN>` ファミリ名で置き換える必要があります。  これは、Windows デベロッパー **センターの拡張機能** の [アプリ ID] セクションにあります。  

## <a name="check-out-your-ratings-and-reviews"></a>評価とレビューを確認する  

定期的にログインして、ユーザーのレビューと評価を確認します。  UWP アプリには現在のユーザー 市場に関する情報しか表示されませんが、Windows デベロッパー センターにログインすると、すべての市場で平均評価が表示されます。  

## <a name="respond-to-user-reviews"></a>ユーザー レビューに応答する  

Windows デベロッパー センターのダッシュボードを使用して、Microsoft ストアのユーザー レビューに応答できます。  拡張機能に移動し、[分析] で [レビュー] **を選択します**。  各レビューの下に、顧客に直接対応できるリンクが表示されます。  このコミュニケーション チャネルを使用すると、フィードバック、解決策を提供したり、レビューに対して感謝のメッセージを送信することができます。  

![ユーザー レビューに応答する](./media/reviews.png)  
