---
ms.assetid: ffd1bc60-2ef1-4f11-8156-b63544cede77
description: Microsoft Edge で ARIA の情報を認識して、Microsoft UI オートメーション Api を使用できる支援技術に公開する方法について説明します。
title: アクセシビリティ-ARIA と UI オートメーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセシビリティ対応の web サイト、edge、web 開発、ARIA、開発者、UIA、UI オートメーション
ms.custom: seodec18
ms.openlocfilehash: 2fcc8160c830b5a62d8023a5cb7cc9df376c49ca
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568809"
---
# <span data-ttu-id="e9427-104">Microsoft Edge の ARIA と UI オートメーション</span><span class="sxs-lookup"><span data-stu-id="e9427-104">ARIA and UI Automation in Microsoft Edge</span></span>

<span data-ttu-id="e9427-105">W3C は、動的な web コンテンツとカスタム UI を作成するための構文として、アクセシビリティに対応したリッチインターネットアプリケーション (ARIA) を定義しています。</span><span class="sxs-lookup"><span data-stu-id="e9427-105">The W3C defines Accessible Rich Internet Applications (ARIA) as a syntax for making dynamic web content and custom UI accessible.</span></span> <span data-ttu-id="e9427-106">Microsoft Edge は、ARIA の役割、状態、プロパティの情報を認識して、支援技術に公開します。これにより、 [MICROSOFT UI オートメーション](https://blogs.msdn.microsoft.com/winuiautomation/)api を使って情報を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e9427-106">Microsoft Edge recognizes the ARIA role, state, and property information and exposes it to assistive technologies, which in turn can use the [Microsoft UI Automation](https://blogs.msdn.microsoft.com/winuiautomation/) APIs to retrieve the information.</span></span>

<span data-ttu-id="e9427-107">Microsoft Edge でサポートされている新しい HTML5 機能 accessibly については、 [HTML5Accessibility](https://html5accessibility.com)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9427-107">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

<span data-ttu-id="e9427-108">Microsoft Edge レンダリングエンジン (EdgeHTML) は、次の W3C 仕様に準拠した、アクセシビリティに対応した web ページの予測を構築します。</span><span class="sxs-lookup"><span data-stu-id="e9427-108">The Microsoft Edge rendering engine (EdgeHTML) builds an accessible projection of web pages, conforming to the following W3C specifications:</span></span>

1. <span data-ttu-id="e9427-109">[Html アクセシビリティ API マッピング](https://w3.org/TR/html-aam-1.0/)の仕様では、html 要素と属性が ARIA と UI オートメーションオブジェクトにどのようにマッピングされるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="e9427-109">The [HTML Accessibility API Mappings](https://w3.org/TR/html-aam-1.0/) specification defines how HTML elements and attributes map to ARIA and UI Automation objects.</span></span>
   * <span data-ttu-id="e9427-110">[ドラフト](https://w3.org/TR/html-aam-1.0/)-安定バージョンの仕様</span><span class="sxs-lookup"><span data-stu-id="e9427-110">[Working draft](https://w3.org/TR/html-aam-1.0/) - stable version of the specification</span></span>
   * <span data-ttu-id="e9427-111">[編集者の下書き](https://w3c.github.io/html-aam/)-作業中。</span><span class="sxs-lookup"><span data-stu-id="e9427-111">[Editor's draft](https://w3c.github.io/html-aam/) - work in progress.</span></span> <span data-ttu-id="e9427-112">この仕様には最新の変更が含まれていますが、変更は Microsoft Edge ではまだ利用できない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9427-112">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>


2. <span data-ttu-id="e9427-113">[コアアクセシビリティ API マッピング](https://w3.org/TR/core-aam-1.1/)仕様では、アクセシビリティツリーを構築し、ARIA 要素と属性を UI オートメーションオブジェクトにマッピングするための一般的な原則を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9427-113">The [Core Accessibility API Mappings](https://w3.org/TR/core-aam-1.1/) specification defines general principles for building the accessibility tree and mapping ARIA elements and attributes to UI Automation objects.</span></span>
   * <span data-ttu-id="e9427-114">[ドラフト](https://w3.org/TR/core-aam-1.1/)-安定バージョンの仕様</span><span class="sxs-lookup"><span data-stu-id="e9427-114">[Working draft](https://w3.org/TR/core-aam-1.1/) - stable version of the specification</span></span>
   * <span data-ttu-id="e9427-115">[編集者の下書き](https://w3c.github.io/core-aam/)-作業中。</span><span class="sxs-lookup"><span data-stu-id="e9427-115">[Editor's draft](https://w3c.github.io/core-aam/) - work in progress.</span></span> <span data-ttu-id="e9427-116">この仕様には最新の変更が含まれていますが、変更は Microsoft Edge ではまだ利用できない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9427-116">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>  

3. <span data-ttu-id="e9427-117">[アクセシビリティ対応の名前と説明: 計算と API のマッピング](https://w3.org/TR/accname-aam-1.1/)の仕様では、アクセシビリティの高い要素で使用できる、HTML と ARIA の要素と属性の値を指定して、アクセシビリティの高いオブジェクトの名前と説明を計算する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9427-117">The [Accessible Name and Description: Computation and API Mappings](https://w3.org/TR/accname-aam-1.1/) specification defines how to compute the name and description of accessible objects given the HTML and the ARIA elements and attributes values available for the accessible elements.</span></span>
   * <span data-ttu-id="e9427-118">[ドラフト](https://w3.org/TR/accname-aam-1.1/)-安定バージョンの仕様</span><span class="sxs-lookup"><span data-stu-id="e9427-118">[Working draft](https://w3.org/TR/accname-aam-1.1/) - stable version of the specification</span></span>  
   * <span data-ttu-id="e9427-119">[編集者の下書き](https://w3c.github.io/accname/)-作業中。</span><span class="sxs-lookup"><span data-stu-id="e9427-119">[Editor's draft](https://w3c.github.io/accname/) - work in progress.</span></span> <span data-ttu-id="e9427-120">この仕様には最新の変更が含まれていますが、変更は Microsoft Edge ではまだ利用できない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9427-120">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>   

<span data-ttu-id="e9427-121">Microsoft Edge のアクセシビリティアーキテクチャについて詳しくは、「アクセシビリティの[高い web platform ブログの投稿を作成する](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e9427-121">For more information about the accessibility architecture in Microsoft Edge, check out the [Building a more accessible web platform](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/) blog post.</span></span>  <span data-ttu-id="e9427-122">新しいアーキテクチャがエンドユーザーのエクスペリエンスを向上させる方法、特にマークアップでスクリーンリーダーなどの支援技術を使用したナビゲーションの操作性を定義する方法については、「 [HTML5 と UIA を使用してアクセシビリティの高いユーザーエクスペリエンスを構築](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9427-122">For examples of how the new architecture improves the end user's experience, and specifically how markup defines the experience of navigating with assistive technologies like screen readers, visit [Building a more accessible user experience with HTML5 and UIA](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/).</span></span>
