---
ms.assetid: 737ac54c-ad89-4b3f-bbe2-4e4169d3f364
description: Web サイトのアクセシビリティの評価に役立つツールとテスト手順を確認します。
title: アクセシビリティ - テスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセス可能な Web サイト、エッジ、Web 開発、ARIA、開発者、UIA、UI オートメーション
ms.openlocfilehash: b3aeb5ede1519352c12ab190fa6fbef9eee2ae12
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397882"
---
# <a name="accessibility-testing"></a><span data-ttu-id="c9c5a-104">アクセシビリティテスト</span><span class="sxs-lookup"><span data-stu-id="c9c5a-104">Accessibility Testing</span></span>  

<span data-ttu-id="c9c5a-105">アクセシビリティ テストは、Web サイトがすべてのユーザーが使用できると確認する使いやすさテストの一形態です。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-105">Accessibility testing is a form of usability testing to verify your website is usable by all people.</span></span> <span data-ttu-id="c9c5a-106">テストを実行する必要がある [場合、](https://www.w3.org/wiki/Accessibility_testing) テスト要件、サイトをテストする必要があるユーザーなどについては、W3C アクセシビリティ テスト ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-106">Check out the W3C [Accessibility Testing](https://www.w3.org/wiki/Accessibility_testing) page for information on when testing should be done, testing requirements, who should test your site, etc.</span></span>

<span data-ttu-id="c9c5a-107">Web サイトのアクセシビリティを評価するには、次のツールとテストプロデューサーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-107">Use the following tools and testing producers to evaluate your website for accessibility:</span></span>

#### [<a name="accessibility-evaluation-resources"></a><span data-ttu-id="c9c5a-108">アクセシビリティ評価リソース</span><span class="sxs-lookup"><span data-stu-id="c9c5a-108">Accessibility Evaluation Resources</span></span>](https://www.w3.org/WAI/eval/Overview.html)  

<span data-ttu-id="c9c5a-109">アクセシビリティ評価リソースは、Web サイトでアクセシビリティを評価するためのさまざまな方法を概説する、W3C による複数ページのリソースです。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-109">Accessibility Evaluation Resources is a multi-page resource by the W3C that outlines different approaches for evaluating websites for accessibility.</span></span>

#### [<a name="assistive-technology-compatibility-tests"></a><span data-ttu-id="c9c5a-110">支援テクノロジの互換性テスト</span><span class="sxs-lookup"><span data-stu-id="c9c5a-110">Assistive technology compatibility tests</span></span>](http://www.powermapper.com/tests)  

<span data-ttu-id="c9c5a-111">スクリーン リーダーのような支援テクノロジ (AT) で異なるコンテンツ タイプと標準がどのように動作するのかを示すテスト結果。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-111">Test results showing how different content types and standards behave in assistive technologies (AT) like screen readers.</span></span>

#### [<a name="easy-checks--a-first-review-of-web-accessibility"></a><span data-ttu-id="c9c5a-112">簡単なチェック – Web アクセシビリティの最初のレビュー</span><span class="sxs-lookup"><span data-stu-id="c9c5a-112">Easy Checks – A First Review of Web Accessibility</span></span>](https://www.w3.org/WAI/eval/preliminary.html)  

<span data-ttu-id="c9c5a-113">WEB ページのアクセシビリティを評価するのに役立つ、一連の WAI によるクイック チェック。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-113">A series of quick checks by the WAI that help you assess the accessibility of a web page.</span></span>

#### [<a name="how-to-meet-wcag-20"></a><span data-ttu-id="c9c5a-114">WCAG 2.0 を満たす方法</span><span class="sxs-lookup"><span data-stu-id="c9c5a-114">How to Meet WCAG 2.0</span></span>](https://www.w3.org/WAI/WCAG20/quickref)  

<span data-ttu-id="c9c5a-115">Web コンテンツ アクセシビリティ ガイドライン \(WCAG\) 2.0 の要件 (成功基準) と手法のクイック リファレンス。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-115">A quick reference to Web Content Accessibility Guidelines \(WCAG\) 2.0 requirements (success criteria) and techniques.</span></span>

#### [<a name="html5accessibility"></a><span data-ttu-id="c9c5a-116">HTML5Accessibility</span><span class="sxs-lookup"><span data-stu-id="c9c5a-116">HTML5Accessibility</span></span>](https://html5accessibility.com)  

<span data-ttu-id="c9c5a-117">このサイトでは、主要なブラウザーでサポートされている新しい HTML5 機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-117">This site tests which new HTML5 features are accessibly supported by major browsers.</span></span> 

#### [<a name="webhint"></a><span data-ttu-id="c9c5a-118">Webhint</span><span class="sxs-lookup"><span data-stu-id="c9c5a-118">webhint</span></span>](https://webhint.io)  

<span data-ttu-id="c9c5a-119">[webhint を](https://webhint.io/)使用して、古いライブラリ、セキュリティの改善、パフォーマンスの問題、アクセシビリティの問題などについて確認します。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-119">Use [webhint](https://webhint.io/) to check for out-of-date libraries, security improvements, performance problems, accessibility issues and more.</span></span>

#### [<a name="web-accessibility-checker"></a><span data-ttu-id="c9c5a-120">Web アクセシビリティ チェッカー</span><span class="sxs-lookup"><span data-stu-id="c9c5a-120">Web Accessibility Checker</span></span>](https://visualstudiogallery.msdn.microsoft.com/3aabefab-1681-4fea-8f95-6a62e2f0f1ec)  

<span data-ttu-id="c9c5a-121">任意Visual Studio Web アプリでアクセシビリティ チェックを実行するASP.NET拡張機能。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-121">A Visual Studio extension that performs accessibility checks on any ASP.NET web app.</span></span>

#### [<a name="web-accessibility-evaluation-tools-list"></a><span data-ttu-id="c9c5a-122">Web アクセシビリティ評価ツールの一覧</span><span class="sxs-lookup"><span data-stu-id="c9c5a-122">Web Accessibility Evaluation Tools List</span></span>](https://www.w3.org/WAI/ER/tools/index.html)  

<span data-ttu-id="c9c5a-123">Web サイトがアクセシビリティ ガイドラインを満たしているかどうかを判断するための Web アクセシビリティ評価ツールの一覧。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-123">A list of web accessibility evaluation tools to help determine if websites meet accessibility guidelines.</span></span>
