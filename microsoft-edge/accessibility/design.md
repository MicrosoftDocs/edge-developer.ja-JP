---
description: 包括的な設計ツールとベスト プラクティスのリソースについて説明します。
title: アクセシビリティ - デザイン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/27/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 8468f8e1-9f4a-426c-a969-76eab9419137
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセス可能な Web サイト、エッジ、Web 開発、ARIA、開発者、UIA、UI オートメーション
ms.openlocfilehash: 8d31f7b32cb92794ff8592c239436f3b101a3859
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230818"
---
# アクセス可能な Web サイトの設計  

包括的なデザインを作成すると、年齢、教育、地理的位置、言語、障がいを問いません。  テクノロジを使用して Web を閲覧するユーザーには、さまざまな機能と好みがあります。  Web サイトを設計する場合は、次の主要なアクセシビリティ シナリオに注意してください。

*   スクリーン リーダー- 視覚障がい者または視覚障がい者は、アプリの UI を解釈して操作するためにスクリーン リーダーに依存します。  解釈には、UI 要素名、役割、値など、読み取り、UI との対話には、フォーカスをある要素から別の要素に移動し、機能を呼び出す必要があります。
*   キーボードアクセシビリティ - 多くのアクセシビリティ ユーザーは、次の方法で UI を移動および操作するためにキーボードを使用します。
    *   Tab キーを使用して要素間でフォーカスを移動します。
    *   矢印キーを使用して、リスト、グリッド、ツリー ビューなどのコンテナー要素内を移動します。
    *   Enter キーまたは Space キーを使用して機能 \(actions\を呼び出す) をアクティブ化します。
    *   ショートカット キーを使用して、他のアプリ機能に効率的にアクセスします。
*   アクセス可能な視覚効果 : 視覚障害のあるユーザーには、テキスト コンテンツに対して十分なテキストコントラスト比が必要であり、全体的にハイ コントラスト テーマを使用した優れたビジュアル エクスペリエンスが必要です。  色覚を持つユーザーは、色以外の方法で情報を伝える必要があります。

Web 上の多くの一般的なアクセシビリティの問題は、コーディングの優れた方法で解決できます。  [Web コンテンツ アクセシビリティ ガイドライン (WCAG) 2.0](https://www.w3.org/TR/WCAG20)のドキュメントには、よりアクセスしやすい動的 Web アプリケーションの設計に役立つ手法とベスト プラクティスが用意されています。  アクセス可能な Web サイトの構築の詳細については、「Building [Accessible Websites」を参照してください](./build/index.md) 。

##  <a name="resources"></a>リソース  

#### [組み込み用の設計](https://w3.org/WAI/users/Overview.html)  

W3C Web アクセシビリティ イニシアティブによる組み込みのための設計では、障がいを持つユーザーを理解し、それらを念頭に置いて Web サイトを設計する方法を理解するのに役立つリソースを提供します。

#### [包括的なソフトウェアの設計](https://msdn.microsoft.com/windows/uwp/accessibility/designing-inclusive-software)  

包括的なソフトウェアの設計では、ユニバーサル Windows プラットフォーム (UWP) の設計原則とプラクティスについて説明します。

#### [障がいを持つユーザーが Web を使用する方法](https://www.w3.org/WAI/intro/people-use-web/Overview.html)  

W3C のこのリソースは、年齢に関連する障がいを持つユーザーを含む障がい者が Web を使用する方法を紹介します。

#### [インクルーシブ デザイン Toolkit](https://www.microsoft.com/design/practice#howwemake-section)  

Microsoft は、人間の多様性Toolkit設計上の制約を生み出す方法と、一見ニッチなソリューションをより広範な市場に接続する方法を示す包括的なデザイン ソリューションを開発しました。
