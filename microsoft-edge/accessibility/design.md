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
# <span data-ttu-id="ed881-104">アクセス可能な Web サイトの設計</span><span class="sxs-lookup"><span data-stu-id="ed881-104">Designing Accessible Websites</span></span>  

<span data-ttu-id="ed881-105">包括的な設計を作成すると、年齢、教育、地理的な場所、言語、障がいを問いませんが、すべてのユーザーがテクノロジを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed881-105">Creating an inclusive design makes technology usable by all people no matter their age, education, geographic location, language, or disability.</span></span>  <span data-ttu-id="ed881-106">テクノロジを使用し、Web を閲覧するユーザーには、さまざまな機能と好みがあります。</span><span class="sxs-lookup"><span data-stu-id="ed881-106">People using technology and browsing the web have a wide range of abilities and preferences.</span></span>  <span data-ttu-id="ed881-107">Web サイトを設計する場合、次の主要なアクセシビリティ シナリオに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ed881-107">As you design your website, keep in mind the following key accessibility scenarios:</span></span>

*   <span data-ttu-id="ed881-108">スクリーン リーダー - 視覚障がいのあるユーザーは、アプリの UI の解釈と操作をスクリーン リーダーに依存します。</span><span class="sxs-lookup"><span data-stu-id="ed881-108">Screen readers—Users who are blind or visually impaired rely on screen readers to interpret and interact with the UI of your app.</span></span>  <span data-ttu-id="ed881-109">解釈には、UI 要素名、ロール、値の読み取り、UI の操作が含まれます。また、UI を操作するには、要素間でフォーカスを移動し、機能を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ed881-109">Interpreting involves reading the UI element names, roles, values, and so on, and interacting with the UI involves moving the focus from one element to another and invoking functionality.</span></span>
*   <span data-ttu-id="ed881-110">キーボードのアクセシビリティ - 多くのアクセシビリティ ユーザーは、次の方法で UI を移動および操作するためにキーボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ed881-110">Keyboard accessibility—Many accessibility users rely on the keyboard to navigate and operate the UI by:</span></span>
    *   <span data-ttu-id="ed881-111">Tab キーを使用して要素間でフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="ed881-111">Moving focus among elements by using the Tab key.</span></span>
    *   <span data-ttu-id="ed881-112">方向キーを使用して、リスト、グリッド、ツリー ビューなどのコンテナー要素内を移動します。</span><span class="sxs-lookup"><span data-stu-id="ed881-112">Navigating in container elements such as lists, grids, and tree views by using the arrow keys.</span></span>
    *   <span data-ttu-id="ed881-113">Enter キーまたは Space キーを使用して機能 \(アクションを呼び出す\) をアクティブ化する。</span><span class="sxs-lookup"><span data-stu-id="ed881-113">Activating functionality \(invoking actions\) by using the Enter or Space key.</span></span>
    *   <span data-ttu-id="ed881-114">ショートカット キーを使って他のアプリの機能に効率的にアクセスする。</span><span class="sxs-lookup"><span data-stu-id="ed881-114">Using shortcut keys to efficiently access other app functionality.</span></span>
*   <span data-ttu-id="ed881-115">アクセス可能な視覚エクスペリエンス — 視覚障がいのあるユーザーには、テキスト コンテンツに対して十分なテキスト コントラスト比と、ハイ コントラスト テーマ全体の優れたビジュアル エクスペリエンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed881-115">Accessible visual experience—Users who are visually impaired need a sufficient text contrast ratio for text content, and a good visual experience with high contrast themes overall.</span></span>  <span data-ttu-id="ed881-116">色覚に関するユーザーには、色を通じて以外の方法で情報を伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed881-116">Users who are color blind need information to be conveyed in ways other than through color.</span></span>

<span data-ttu-id="ed881-117">Web 上の多くの一般的なアクセシビリティの問題は、優れたコーディング方法で解決できます。</span><span class="sxs-lookup"><span data-stu-id="ed881-117">Many common accessibility issues on the web can be solved through good coding practice.</span></span>  <span data-ttu-id="ed881-118">[Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/WCAG20)のドキュメントには、よりアクセシビリティの高い動的な Web アプリケーションを設計するのに役立つ手法とベスト プラクティスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ed881-118">The [Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/WCAG20) documentation provides techniques and best practices to help you design more accessible dynamic web applications.</span></span>  <span data-ttu-id="ed881-119">アクセス可能な Web サイトの構築の詳細については、「アクセス可能な Web サイトを構築 [する」に移動します](./build/index.md) 。</span><span class="sxs-lookup"><span data-stu-id="ed881-119">For more information on building accessible websites, navigate to [Building Accessible Websites](./build/index.md) .</span></span>

## <span data-ttu-id="ed881-120">リソース</span><span class="sxs-lookup"><span data-stu-id="ed881-120">Resources</span></span>  

#### [<span data-ttu-id="ed881-121">包含の設計</span><span class="sxs-lookup"><span data-stu-id="ed881-121">Designing for Inclusion</span></span>](https://w3.org/WAI/users/Overview.html)  

<span data-ttu-id="ed881-122">W3C Web Accessibility Initiative による包含のための設計では、障がいのあるユーザーと、障がいのあるユーザーを念頭に置いて Web サイトを設計する方法をよりよく理解するのに役立つリソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="ed881-122">Designing for Inclusion by the W3C Web Accessibility Initiative provides resources to help you better understand users with disabilities and how to design your website with them in mind.</span></span>

#### [<span data-ttu-id="ed881-123">包括的なソフトウェアの設計</span><span class="sxs-lookup"><span data-stu-id="ed881-123">Designing inclusive software</span></span>](https://msdn.microsoft.com/windows/uwp/accessibility/designing-inclusive-software)  

<span data-ttu-id="ed881-124">包括的なソフトウェアの設計では、ユニバーサル Windows プラットフォーム (UWP) の Microsoft 設計の原則とプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ed881-124">Designing inclusive software discusses Microsoft design principles and practices for the Universal Windows Platform (UWP).</span></span>

#### [<span data-ttu-id="ed881-125">障がいのある方が Web を使用する方法</span><span class="sxs-lookup"><span data-stu-id="ed881-125">How People with Disabilities Use the Web</span></span>](https://www.w3.org/WAI/intro/people-use-web/Overview.html)  

<span data-ttu-id="ed881-126">W3C によるこのリソースは、障がいのある方 (年齢関連の障がいのある方を含む) が Web を使用する方法を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="ed881-126">This resource by the W3C introduces how people with disabilities, including people with age-related impairments, use the Web.</span></span>

#### [<span data-ttu-id="ed881-127">包括的なデザイン Toolkit</span><span class="sxs-lookup"><span data-stu-id="ed881-127">Inclusive Design Toolkit</span></span>](https://www.microsoft.com/design/practice#howwemake-section)  

<span data-ttu-id="ed881-128">Microsoft では、包括的な設計Toolkitを開発し、人間の多様性によってどのように設計上の制約が生み出され、一見一見優れたソリューションをより広い市場に接続する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ed881-128">Microsoft developed the Inclusive Design Toolkit to show how human diversity can create better design constraints and how to connect seemingly niche solutions to broader markets.</span></span>
