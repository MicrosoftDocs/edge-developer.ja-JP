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
# <span data-ttu-id="09966-104">アクセス可能な Web サイトの設計</span><span class="sxs-lookup"><span data-stu-id="09966-104">Designing Accessible Websites</span></span>  

<span data-ttu-id="09966-105">包括的なデザインを作成すると、年齢、教育、地理的位置、言語、障がいを問いません。</span><span class="sxs-lookup"><span data-stu-id="09966-105">Creating an inclusive design makes technology usable by all people no matter their age, education, geographic location, language, or disability.</span></span>  <span data-ttu-id="09966-106">テクノロジを使用して Web を閲覧するユーザーには、さまざまな機能と好みがあります。</span><span class="sxs-lookup"><span data-stu-id="09966-106">People using technology and browsing the web have a wide range of abilities and preferences.</span></span>  <span data-ttu-id="09966-107">Web サイトを設計する場合は、次の主要なアクセシビリティ シナリオに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09966-107">As you design your website, keep in mind the following key accessibility scenarios:</span></span>

*   <span data-ttu-id="09966-108">スクリーン リーダー- 視覚障がい者または視覚障がい者は、アプリの UI を解釈して操作するためにスクリーン リーダーに依存します。</span><span class="sxs-lookup"><span data-stu-id="09966-108">Screen readers—Users who are blind or visually impaired rely on screen readers to interpret and interact with the UI of your app.</span></span>  <span data-ttu-id="09966-109">解釈には、UI 要素名、役割、値など、読み取り、UI との対話には、フォーカスをある要素から別の要素に移動し、機能を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="09966-109">Interpreting involves reading the UI element names, roles, values, and so on, and interacting with the UI involves moving the focus from one element to another and invoking functionality.</span></span>
*   <span data-ttu-id="09966-110">キーボードアクセシビリティ - 多くのアクセシビリティ ユーザーは、次の方法で UI を移動および操作するためにキーボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="09966-110">Keyboard accessibility—Many accessibility users rely on the keyboard to navigate and operate the UI by:</span></span>
    *   <span data-ttu-id="09966-111">Tab キーを使用して要素間でフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="09966-111">Moving focus among elements by using the Tab key.</span></span>
    *   <span data-ttu-id="09966-112">矢印キーを使用して、リスト、グリッド、ツリー ビューなどのコンテナー要素内を移動します。</span><span class="sxs-lookup"><span data-stu-id="09966-112">Navigating in container elements such as lists, grids, and tree views by using the arrow keys.</span></span>
    *   <span data-ttu-id="09966-113">Enter キーまたは Space キーを使用して機能 \(actions\を呼び出す) をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="09966-113">Activating functionality \(invoking actions\) by using the Enter or Space key.</span></span>
    *   <span data-ttu-id="09966-114">ショートカット キーを使用して、他のアプリ機能に効率的にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="09966-114">Using shortcut keys to efficiently access other app functionality.</span></span>
*   <span data-ttu-id="09966-115">アクセス可能な視覚効果 : 視覚障害のあるユーザーには、テキスト コンテンツに対して十分なテキストコントラスト比が必要であり、全体的にハイ コントラスト テーマを使用した優れたビジュアル エクスペリエンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="09966-115">Accessible visual experience—Users who are visually impaired need a sufficient text contrast ratio for text content, and a good visual experience with high contrast themes overall.</span></span>  <span data-ttu-id="09966-116">色覚を持つユーザーは、色以外の方法で情報を伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="09966-116">Users who are color blind need information to be conveyed in ways other than through color.</span></span>

<span data-ttu-id="09966-117">Web 上の多くの一般的なアクセシビリティの問題は、コーディングの優れた方法で解決できます。</span><span class="sxs-lookup"><span data-stu-id="09966-117">Many common accessibility issues on the web can be solved through good coding practice.</span></span>  <span data-ttu-id="09966-118">[Web コンテンツ アクセシビリティ ガイドライン (WCAG) 2.0](https://www.w3.org/TR/WCAG20)のドキュメントには、よりアクセスしやすい動的 Web アプリケーションの設計に役立つ手法とベスト プラクティスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="09966-118">The [Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/WCAG20) documentation provides techniques and best practices to help you design more accessible dynamic web applications.</span></span>  <span data-ttu-id="09966-119">アクセス可能な Web サイトの構築の詳細については、「Building [Accessible Websites」を参照してください](./build/index.md) 。</span><span class="sxs-lookup"><span data-stu-id="09966-119">For more information on building accessible websites, navigate to [Building Accessible Websites](./build/index.md) .</span></span>

## <span data-ttu-id="09966-120">リソース</span><span class="sxs-lookup"><span data-stu-id="09966-120">Resources</span></span>  

#### [<span data-ttu-id="09966-121">組み込み用の設計</span><span class="sxs-lookup"><span data-stu-id="09966-121">Designing for Inclusion</span></span>](https://w3.org/WAI/users/Overview.html)  

<span data-ttu-id="09966-122">W3C Web アクセシビリティ イニシアティブによる組み込みのための設計では、障がいを持つユーザーを理解し、それらを念頭に置いて Web サイトを設計する方法を理解するのに役立つリソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="09966-122">Designing for Inclusion by the W3C Web Accessibility Initiative provides resources to help you better understand users with disabilities and how to design your website with them in mind.</span></span>

#### [<span data-ttu-id="09966-123">包括的なソフトウェアの設計</span><span class="sxs-lookup"><span data-stu-id="09966-123">Designing inclusive software</span></span>](https://msdn.microsoft.com/windows/uwp/accessibility/designing-inclusive-software)  

<span data-ttu-id="09966-124">包括的なソフトウェアの設計では、ユニバーサル Windows プラットフォーム (UWP) の設計原則とプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="09966-124">Designing inclusive software discusses Microsoft design principles and practices for the Universal Windows Platform (UWP).</span></span>

#### [<span data-ttu-id="09966-125">障がいを持つユーザーが Web を使用する方法</span><span class="sxs-lookup"><span data-stu-id="09966-125">How People with Disabilities Use the Web</span></span>](https://www.w3.org/WAI/intro/people-use-web/Overview.html)  

<span data-ttu-id="09966-126">W3C のこのリソースは、年齢に関連する障がいを持つユーザーを含む障がい者が Web を使用する方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="09966-126">This resource by the W3C introduces how people with disabilities, including people with age-related impairments, use the Web.</span></span>

#### [<span data-ttu-id="09966-127">インクルーシブ デザイン Toolkit</span><span class="sxs-lookup"><span data-stu-id="09966-127">Inclusive Design Toolkit</span></span>](https://www.microsoft.com/design/practice#howwemake-section)  

<span data-ttu-id="09966-128">Microsoft は、人間の多様性Toolkit設計上の制約を生み出す方法と、一見ニッチなソリューションをより広範な市場に接続する方法を示す包括的なデザイン ソリューションを開発しました。</span><span class="sxs-lookup"><span data-stu-id="09966-128">Microsoft developed the Inclusive Design Toolkit to show how human diversity can create better design constraints and how to connect seemingly niche solutions to broader markets.</span></span>
