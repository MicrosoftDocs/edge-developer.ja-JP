---
ms.assetid: 4d3fa934-4fa8-4c02-b9b5-88506c76baac
description: Microsoft Edge のブラウザー機能のガイドです。
title: ブラウザー - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2579fad881496e2197f9f696bb2c12c47c7f723e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234891"
---
# ブラウザーの機能  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

## 自動再生のポリシー  

 Microsoft Edge は、Web 上の注意をそらす操作を最小限に抑え、帯域幅を節約するために、音声でメディアを自動再生する Web サイトの閲覧設定をカスタマイズする機能をユーザーに提供します。  ユーザーは、グローバル自動再生コントロールとサイトごとの自動再生コントロールの両方でメディアの動作をカスタマイズできます。  さらに、Microsoft Edge では、バックグラウンド タブでのメディアの自動再生が自動的に抑制されます。  

サイトで [ホストされているメディアのユーザー](./browser-features/autoplay-policies.md) エクスペリエンスを向上するために、詳細とベスト プラクティスについては、自動再生ポリシーをご覧ください。  

## Flash  

Flash がページで使用されているが、ユーザーが有効にしていない場合、Microsoft Edge は通常、アドレス バーにパズルの一部のアイコンを表示します。  ページの読み込み後に Flash コントロールを動的に追加する場合は、パズル アイコンが表示されない可能性があります。この場合は [、Flash](./browser-features/flash.md) が読み込まれているかテストし、存在しない場合は適切なフォールバック エクスペリエンスを提供します。  

## 読み取りビュー  

Microsoft Edge[](./browser-features/reading-view.md)は、ページ上の無関係なコンテンツや他のセカンダリ コンテンツを気を散らさずに、より合理化された書籍のような Web ページの閲覧エクスペリエンスのための閲覧ビューを提供します。  ここでは、サイトの閲覧表示エクスペリエンスを向上する方法に関するヒントと、サイトを閲覧ビューからオプトアウトするための手順を示します。  

## 検索プロバイダーの検出  

リッチ検索の統合は、Microsoft Edge アドレス バーに組み込み、検索候補、Web からの結果、閲覧履歴、お気に入りを含む。  Microsoft Edge[のサポートを提供する](./browser-features/search-provider-discovery.md)検索プロバイダーについて詳しくは、次をご覧ください。  
