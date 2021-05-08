---
ms.assetid: ffd1bc60-2ef1-4f11-8156-b63544cede77
description: ARIA 情報Microsoft Edge認識し、Microsoft UI オートメーション API を使用できる支援テクノロジに公開する方法について説明します。
title: アクセシビリティ - ARIA と UI オートメーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセス可能な Web サイト、エッジ、Web 開発、ARIA、開発者、UIA、UI オートメーション
ms.custom: seodec18
ms.openlocfilehash: 2fcc8160c830b5a62d8023a5cb7cc9df376c49ca
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568809"
---
# <span data-ttu-id="9b3fd-104">ARIA と UI オートメーション (Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9b3fd-104">ARIA and UI Automation in Microsoft Edge</span></span>

<span data-ttu-id="9b3fd-105">W3C は、アクセス可能なリッチ インターネット アプリケーション (ARIA) を、動的 Web コンテンツとカスタム UI をアクセス可能にするための構文として定義します。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-105">The W3C defines Accessible Rich Internet Applications (ARIA) as a syntax for making dynamic web content and custom UI accessible.</span></span> <span data-ttu-id="9b3fd-106">Microsoft Edge、ARIA の役割、状態、およびプロパティの情報を認識し、支援テクノロジに公開し[、Microsoft UI オートメーション API](https://blogs.msdn.microsoft.com/winuiautomation/)を使用して情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-106">Microsoft Edge recognizes the ARIA role, state, and property information and exposes it to assistive technologies, which in turn can use the [Microsoft UI Automation](https://blogs.msdn.microsoft.com/winuiautomation/) APIs to retrieve the information.</span></span>

<span data-ttu-id="9b3fd-107">[HTML5Accessibility に](https://html5accessibility.com)アクセスして、ユーザーがサポートする新しい HTML5 機能に関する情報Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-107">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

<span data-ttu-id="9b3fd-108">次Microsoft Edgeレンダリング エンジン (EdgeHTML) は、次の W3C 仕様に準拠して、Web ページのアクセス可能なプロジェクションを構築します。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-108">The Microsoft Edge rendering engine (EdgeHTML) builds an accessible projection of web pages, conforming to the following W3C specifications:</span></span>

1. <span data-ttu-id="9b3fd-109">[HTML アクセシビリティ API Mappings 仕様は](https://w3.org/TR/html-aam-1.0/)、HTML 要素と属性が ARIA オブジェクトおよび UI オートメーション オブジェクトにマップする方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-109">The [HTML Accessibility API Mappings](https://w3.org/TR/html-aam-1.0/) specification defines how HTML elements and attributes map to ARIA and UI Automation objects.</span></span>
   * <span data-ttu-id="9b3fd-110">[作業下書](https://w3.org/TR/html-aam-1.0/) き - 仕様の安定版</span><span class="sxs-lookup"><span data-stu-id="9b3fd-110">[Working draft](https://w3.org/TR/html-aam-1.0/) - stable version of the specification</span></span>
   * <span data-ttu-id="9b3fd-111">[編集者の下書き](https://w3c.github.io/html-aam/) - 進行中の作業。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-111">[Editor's draft](https://w3c.github.io/html-aam/) - work in progress.</span></span> <span data-ttu-id="9b3fd-112">この仕様には最新の変更点が含まれる一方で、この変更は現在のバージョンMicrosoft Edgeがあります。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-112">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>


2. <span data-ttu-id="9b3fd-113">Core [Accessibility API Mappings 仕様](https://w3.org/TR/core-aam-1.1/) は、アクセシビリティ ツリーを構築し、ARIA 要素と属性を UI オートメーション オブジェクトにマッピングするための一般的な原則を定義します。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-113">The [Core Accessibility API Mappings](https://w3.org/TR/core-aam-1.1/) specification defines general principles for building the accessibility tree and mapping ARIA elements and attributes to UI Automation objects.</span></span>
   * <span data-ttu-id="9b3fd-114">[作業下書](https://w3.org/TR/core-aam-1.1/) き - 仕様の安定版</span><span class="sxs-lookup"><span data-stu-id="9b3fd-114">[Working draft](https://w3.org/TR/core-aam-1.1/) - stable version of the specification</span></span>
   * <span data-ttu-id="9b3fd-115">[編集者の下書き](https://w3c.github.io/core-aam/) - 進行中の作業。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-115">[Editor's draft](https://w3c.github.io/core-aam/) - work in progress.</span></span> <span data-ttu-id="9b3fd-116">この仕様には最新の変更点が含まれる一方で、この変更は現在のバージョンMicrosoft Edgeがあります。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-116">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>  

3. <span data-ttu-id="9b3fd-117">[ [アクセス可能な名前](https://w3.org/TR/accname-aam-1.1/) と説明: 計算と API マッピング] 仕様では、HTML およびアクセス可能な要素で使用できる ARIA 要素と属性の値を指定して、アクセス可能なオブジェクトの名前と説明を計算する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-117">The [Accessible Name and Description: Computation and API Mappings](https://w3.org/TR/accname-aam-1.1/) specification defines how to compute the name and description of accessible objects given the HTML and the ARIA elements and attributes values available for the accessible elements.</span></span>
   * <span data-ttu-id="9b3fd-118">[作業下書](https://w3.org/TR/accname-aam-1.1/) き - 仕様の安定版</span><span class="sxs-lookup"><span data-stu-id="9b3fd-118">[Working draft](https://w3.org/TR/accname-aam-1.1/) - stable version of the specification</span></span>  
   * <span data-ttu-id="9b3fd-119">[編集者の下書き](https://w3c.github.io/accname/) - 進行中の作業。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-119">[Editor's draft](https://w3c.github.io/accname/) - work in progress.</span></span> <span data-ttu-id="9b3fd-120">この仕様には最新の変更点が含まれる一方で、この変更は現在のバージョンMicrosoft Edgeがあります。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-120">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>   

<span data-ttu-id="9b3fd-121">ユーザー補助アーキテクチャの詳細については、「Microsoft Edge Web プラットフォームのブログ投稿を作成する[」を](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/)参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-121">For more information about the accessibility architecture in Microsoft Edge, check out the [Building a more accessible web platform](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/) blog post.</span></span>  <span data-ttu-id="9b3fd-122">新しいアーキテクチャがエンド ユーザーのエクスペリエンスを向上させる方法の例、特にマークアップがスクリーン リーダーなどの支援テクノロジを使用して移動するエクスペリエンスを定義する方法の例については [、「HTML5](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/)と UIA を使用して、よりアクセスしやすいユーザー エクスペリエンスを構築する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9b3fd-122">For examples of how the new architecture improves the end user's experience, and specifically how markup defines the experience of navigating with assistive technologies like screen readers, visit [Building a more accessible user experience with HTML5 and UIA](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/).</span></span>
