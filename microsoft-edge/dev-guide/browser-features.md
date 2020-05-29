---
ms.assetid: 4d3fa934-4fa8-4c02-b9b5-88506c76baac
description: Microsoft Edge のブラウザー機能のガイド。
title: 開発ガイド-ブラウザー
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/28/2018
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: e7b13b18048e0a703ca5e2a0e5b52712f41c2101
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568838"
---
# ブラウザーの機能

## 自動再生ポリシー

 Microsoft Edge では、web 上の集中を最小限に抑え、帯域幅を節約するために、メディアを自動再生する web サイトの閲覧の設定をカスタマイズすることができます。 ユーザーは、グローバルおよびサイトごとの自動再生コントロールの両方でメディアの動作をカスタマイズできます。 また、Microsoft Edge では、バックグラウンドタブでのメディアの自動再生が自動的に抑制されます。

サイトでホストされているメディアでユーザーエクスペリエンスを向上させるための詳細とベストプラクティスについては、[自動再生ポリシー](./browser-features/autoplay-policies.md)を確認してください。

## フラッシュ
ページで Flash が使用されていても、ユーザーが有効にしていない場合、Microsoft Edge では通常、アドレスバーにパズルのピースアイコンが表示されます。 ページの読み込み後にフラッシュコントロールを動的に追加している場合は、パズルアイコンが表示されないことがあります。この場合、 [flash が読み込まれているか](./browser-features/flash.md)どうかをテストし、存在しない場合は、正常なフォールバックエクスペリエンスを提供します。

## 読み取りビュー
Microsoft Edge では、ページ上の関連性のない、または他の二次的なコンテンツに煩わされることなく、web ページをより効率的に整理するための[閲覧表示](./browser-features/reading-view.md)が用意されています。 ここでは、サイトで優れた読み取り操作エクスペリエンスを実現するためのヒントと、サイトを閲覧表示から除外する方法について説明します。

## 検索プロバイダーの検出

Microsoft Edge のアドレスバーには、検索候補、web の結果、閲覧履歴、お気に入りなど、リッチ検索の統合機能が組み込まれています。 Microsoft Edge のサポートを提供する[検索プロバイダーの詳細については、こちら](./browser-features/search-provider-discovery.md)を参照してください。
