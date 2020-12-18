---
description: 包括的なデザイン ツールとベスト プラクティスに関するリソースを参照してください。
title: アクセシビリティ - デザイン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/27/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 8468f8e1-9f4a-426c-a969-76eab9419137
keywords: アクセシビリティ, 開発者向けアクセシビリティ, アクセシビリティ対応の Web サイト, エッジ, Web 開発, ARIA, 開発者, UIA, UI オートメーション
ms.openlocfilehash: 8d31f7b32cb92794ff8592c239436f3b101a3859
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230818"
---
# アクセス可能な Web サイトの設計  

包括的な設計を作成すると、年齢、教育、地理的な場所、言語、障がいを問いませんが、すべてのユーザーがテクノロジを使用できます。  テクノロジを使用し、Web を閲覧するユーザーには、さまざまな機能と好みがあります。  Web サイトを設計する場合、次の主要なアクセシビリティ シナリオに注意してください。

*   スクリーン リーダー - 視覚障がいのあるユーザーは、アプリの UI の解釈と操作をスクリーン リーダーに依存します。  解釈には、UI 要素名、ロール、値の読み取り、UI の操作が含まれます。また、UI を操作するには、要素間でフォーカスを移動し、機能を呼び出します。
*   キーボードのアクセシビリティ - 多くのアクセシビリティ ユーザーは、次の方法で UI を移動および操作するためにキーボードを使用します。
    *   Tab キーを使用して要素間でフォーカスを移動する。
    *   方向キーを使用して、リスト、グリッド、ツリー ビューなどのコンテナー要素内を移動します。
    *   Enter キーまたは Space キーを使用して機能 \(アクションを呼び出す\) をアクティブ化する。
    *   ショートカット キーを使って他のアプリの機能に効率的にアクセスする。
*   アクセス可能な視覚エクスペリエンス — 視覚障がいのあるユーザーには、テキスト コンテンツに対して十分なテキスト コントラスト比と、ハイ コントラスト テーマ全体の優れたビジュアル エクスペリエンスが必要です。  色覚に関するユーザーには、色を通じて以外の方法で情報を伝える必要があります。

Web 上の多くの一般的なアクセシビリティの問題は、優れたコーディング方法で解決できます。  [Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/WCAG20)のドキュメントには、よりアクセシビリティの高い動的な Web アプリケーションを設計するのに役立つ手法とベスト プラクティスが用意されています。  アクセス可能な Web サイトの構築の詳細については、「アクセス可能な Web サイトを構築 [する」に移動します](./build/index.md) 。

## リソース  

#### [包含の設計](https://w3.org/WAI/users/Overview.html)  

W3C Web Accessibility Initiative による包含のための設計では、障がいのあるユーザーと、障がいのあるユーザーを念頭に置いて Web サイトを設計する方法をよりよく理解するのに役立つリソースを提供します。

#### [包括的なソフトウェアの設計](https://msdn.microsoft.com/windows/uwp/accessibility/designing-inclusive-software)  

包括的なソフトウェアの設計では、ユニバーサル Windows プラットフォーム (UWP) の Microsoft 設計の原則とプラクティスについて説明します。

#### [障がいのある方が Web を使用する方法](https://www.w3.org/WAI/intro/people-use-web/Overview.html)  

W3C によるこのリソースは、障がいのある方 (年齢関連の障がいのある方を含む) が Web を使用する方法を紹介しています。

#### [包括的なデザイン Toolkit](https://www.microsoft.com/design/practice#howwemake-section)  

Microsoft では、包括的な設計Toolkitを開発し、人間の多様性によってどのように設計上の制約が生み出され、一見一見優れたソリューションをより広い市場に接続する方法を示しています。
