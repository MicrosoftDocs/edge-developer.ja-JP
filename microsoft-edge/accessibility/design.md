---
ms.assetid: 8468f8e1-9f4a-426c-a969-76eab9419137
description: 包括的な設計ツールとベストプラクティスのリソースについては、こちらを参照してください。
title: アクセシビリティ-デザイン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセシビリティ対応の web サイト、edge、web 開発、ARIA、開発者、UIA、UI オートメーション
ms.openlocfilehash: c9dfd6dfb9a45f7f8bb3f6d8ebad6c826f3f9e99
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568807"
---
# <span data-ttu-id="885d3-104">アクセシビリティの高い Web サイトを設計する</span><span class="sxs-lookup"><span data-stu-id="885d3-104">Designing Accessible Websites</span></span>

<span data-ttu-id="885d3-105">包括的な設計を作成することで、年齢、教育、地理的な位置、言語、障碍などに関係なく、すべてのユーザーがテクノロジを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="885d3-105">Creating an inclusive design makes technology usable by all people no matter their age, education, geographic location, language, or disability.</span></span> <span data-ttu-id="885d3-106">技術を利用して web を閲覧するユーザーには、さまざまな機能と環境設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="885d3-106">People using technology and browsing the web have a wide range of abilities and preferences.</span></span> <span data-ttu-id="885d3-107">Web サイトを設計する際には、次のようなアクセシビリティシナリオを念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="885d3-107">As you design your website, keep in mind the following key accessibility scenarios:</span></span>

* <span data-ttu-id="885d3-108">スクリーンリーダー-視覚障碍のあるユーザーは、スクリーンリーダーを使用して、アプリの UI を解釈し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="885d3-108">Screen readers—Users who are blind or visually impaired rely on screen readers to interpret and interact with your app's UI.</span></span> <span data-ttu-id="885d3-109">解釈では、UI 要素の名前、役割、値などを読み取り、UI を操作するときに、ある要素から別の要素にフォーカスを移動して機能を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="885d3-109">Interpreting involves reading the UI element names, roles, values, and so on, and interacting with the UI involves moving the focus from one element to another and invoking functionality.</span></span>
* <span data-ttu-id="885d3-110">キーボードのアクセシビリティ: 多くのアクセシビリティユーザーは、キーボードを使用して UI の移動と操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="885d3-110">Keyboard accessibility—Many accessibility users rely on the keyboard to navigate and operate the UI by:</span></span>
  * <span data-ttu-id="885d3-111">Tab キーを使用して要素間でフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="885d3-111">Moving focus among elements by using the Tab key.</span></span>
  * <span data-ttu-id="885d3-112">方向キーを使用して、リスト、グリッド、ツリービューなどのコンテナー要素内を移動します。</span><span class="sxs-lookup"><span data-stu-id="885d3-112">Navigating in container elements such as lists, grids, and tree views by using the arrow keys.</span></span>
  * <span data-ttu-id="885d3-113">Enter キーまたは Space キーを使用した機能のアクティブ化 (アクションの呼び出し)</span><span class="sxs-lookup"><span data-stu-id="885d3-113">Activating functionality (invoking actions) by using the Enter or Space key.</span></span>
  * <span data-ttu-id="885d3-114">ショートカットキーを使用した、他のアプリの機能への効率的なアクセス。</span><span class="sxs-lookup"><span data-stu-id="885d3-114">Using shortcut keys to efficiently access other app functionality.</span></span>
* <span data-ttu-id="885d3-115">アクセシビリティの高いビジュアルエクスペリエンス。視覚障碍のあるユーザーは、テキストコンテンツに十分なテキストコントラスト比が必要です。また、ハイコントラストテーマ全体を使用すると、視覚的に優れたエクスペリエンスを実現できます。</span><span class="sxs-lookup"><span data-stu-id="885d3-115">Accessible visual experience—Users who are visually impaired need a sufficient text contrast ratio for text content, and a good visual experience with high contrast themes overall.</span></span> <span data-ttu-id="885d3-116">色覚に障碍のあるユーザーは、色以外の方法で情報を伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="885d3-116">Users who are color blind need information to be conveyed in ways other than through color.</span></span>

<span data-ttu-id="885d3-117">Web 上の一般的なアクセシビリティの問題の多くは、適切なコーディング方法で解決できます。</span><span class="sxs-lookup"><span data-stu-id="885d3-117">Many common accessibility issues on the web can be solved through good coding practice.</span></span>  <span data-ttu-id="885d3-118">[Web コンテンツのアクセシビリティガイドライン (WCAG) 2.0](https://www.w3.org/TR/WCAG20/)ドキュメントは、よりアクセシビリティの高い動的 Web アプリケーションを設計するのに役立つ手法とベストプラクティスを示しています。</span><span class="sxs-lookup"><span data-stu-id="885d3-118">The [Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/WCAG20/) documentation provides techniques and best practices to help you design more accessible dynamic web applications.</span></span> <span data-ttu-id="885d3-119">アクセシビリティの高い web サイトの構築について詳しくは、「アクセシビリティ対応の[Web サイトを作成](./build.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="885d3-119">See [Building Accessible Websites](./build.md) for more information on building accessible websites.</span></span>

## <span data-ttu-id="885d3-120">リソース</span><span class="sxs-lookup"><span data-stu-id="885d3-120">Resources</span></span>

#### [<span data-ttu-id="885d3-121">追加用の設計</span><span class="sxs-lookup"><span data-stu-id="885d3-121">Designing for Inclusion</span></span>](https://w3.org/WAI/users/Overview.html)
<span data-ttu-id="885d3-122">W3C's Web Accessibility イニシアチブによって追加されるように設計することで、障碍のある方をより詳しく理解し、web サイトを念頭に置いて設計することができます。</span><span class="sxs-lookup"><span data-stu-id="885d3-122">Designing for Inclusion by the W3C's Web Accessibility Initiative provides resources to help you better understand users with disabilities and how to design your website with them in mind.</span></span>

#### [<span data-ttu-id="885d3-123">包括的なソフトウェアの設計</span><span class="sxs-lookup"><span data-stu-id="885d3-123">Designing inclusive software</span></span>](https://msdn.microsoft.com/windows/uwp/accessibility/designing-inclusive-software)
<span data-ttu-id="885d3-124">包括的なソフトウェアの設計 Microsoft の設計原則とユニバーサル Windows プラットフォーム (UWP) のプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="885d3-124">Designing inclusive software discusses Microsoft design principles and practices for the Universal Windows Platform (UWP).</span></span>

#### [<span data-ttu-id="885d3-125">障碍のある方がどのように Web を使用しているか</span><span class="sxs-lookup"><span data-stu-id="885d3-125">How People with Disabilities Use the Web</span></span>](https://www.w3.org/WAI/intro/people-use-web/Overview.html)
<span data-ttu-id="885d3-126">W3C によるこのリソースは、年齢に関連した障碍のある方を含め、障碍のあるユーザーが Web を使用する方法を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="885d3-126">This resource by the W3C introduces how people with disabilities, including people with age-related impairments, use the Web.</span></span>

#### [<span data-ttu-id="885d3-127">包括的設計ツールキット</span><span class="sxs-lookup"><span data-stu-id="885d3-127">Inclusive Design Toolkit</span></span>](https://www.microsoft.com/design/practice#howwemake-section)
<span data-ttu-id="885d3-128">Microsoft は、包括設計ツールキットを開発して、人間の多様性によってより良いデザインの制約を作成し、見かけ上のニッチソリューションをより広範な市場に接続する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="885d3-128">Microsoft developed the Inclusive Design Toolkit to show how human diversity can create better design constraints and how to connect seemingly niche solutions to broader markets.</span></span>
