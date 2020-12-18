---
description: 拡張機能をさまざまな言語でアクセス可能にし、国際化ガイドで言語文字列をテストします。
title: 拡張機能 - 国際化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bbbc847ebd2103cba2eca8a791009b4e72f93a6f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234956"
---
# <span data-ttu-id="01214-104">国際化</span><span class="sxs-lookup"><span data-stu-id="01214-104">Internationalization</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="01214-105">さまざまなユーザーが拡張機能にアクセスしやすくするために、他の国を念頭に置いて開発することが重要です。</span><span class="sxs-lookup"><span data-stu-id="01214-105">In order to make your extension accessible to a variety of different people, it is important to develop with other countries in mind.</span></span> <span data-ttu-id="01214-106">Microsoft Edge 拡張機能を使用すると、さまざまな言語文字列を拡張機能に追加して、言語を簡単に変更できます。</span><span class="sxs-lookup"><span data-stu-id="01214-106">Microsoft Edge extensions allows you to add different language strings to your extensions so that their language can easily be changed.</span></span>

<span data-ttu-id="01214-107">拡張機能の国際化について詳しくは、MDN の国際化ガイド [をご覧ください](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization)。</span><span class="sxs-lookup"><span data-stu-id="01214-107">For more information on internationalizing your extension, check out MDN's [Internationalization guide](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization).</span></span>


## <span data-ttu-id="01214-108">言語のテスト</span><span class="sxs-lookup"><span data-stu-id="01214-108">Testing languages</span></span>

<span data-ttu-id="01214-109">言語文字列をテストするには、まず Windows 表示言語をテストする言語に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01214-109">To test your language strings, you first need to set the Windows display language to the language that you want to test for.</span></span>

<span data-ttu-id="01214-110">Windows 表示言語を変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="01214-110">Follow the steps below to change the Windows display language:</span></span>

1. <span data-ttu-id="01214-111">設定アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="01214-111">Open the Settings app.</span></span>

   ![設定アプリケーション](./../media/loc-settings.png)
2. <span data-ttu-id="01214-113">[言語の時刻&選択します。</span><span class="sxs-lookup"><span data-stu-id="01214-113">Select "Time & language".</span></span>
3. <span data-ttu-id="01214-114">[地域の言語&選択します。</span><span class="sxs-lookup"><span data-stu-id="01214-114">Select "Region & language".</span></span>
4. <span data-ttu-id="01214-115">[+ 言語の追加] を選択して、使用できる言語の一覧に言語を追加します。</span><span class="sxs-lookup"><span data-stu-id="01214-115">Select "+ Add a language" to add the language to the list of possible languages.</span></span>
5. <span data-ttu-id="01214-116">テストする言語の一覧から言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="01214-116">Choose the language from the "Languages" list that you want to test.</span></span>
6. <span data-ttu-id="01214-117">[既定として設定] ボタンを選択します (PC の再起動が必要な場合があります)。</span><span class="sxs-lookup"><span data-stu-id="01214-117">Select the "Set as default" button (you may need to restart your PC).</span></span>
7. <span data-ttu-id="01214-118">Microsoft Edge を開き、ロケールに定義されている文字列が期待通り表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="01214-118">Open Microsoft Edge and verify that the strings defined for the locale appear as expected.</span></span>

<span data-ttu-id="01214-119">[NavigatorLanguage.language](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language)プロパティを使用すると、Microsoft Edge が Windows 表示言語と判断した言語が正しいか確認できます。</span><span class="sxs-lookup"><span data-stu-id="01214-119">By using the [NavigatorLanguage.language](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language) property, you can verify that the language Microsoft Edge has determined to be the Windows display language is correct.</span></span>

<span data-ttu-id="01214-120">ブラウザーの表示言語を確認するには、以下の CodePen のボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="01214-120">Click the button in the CodePen below to see the display language of your browser.</span></span>

<iframe height='300' scrolling='no' title='<span data-ttu-id="01214-121">ロケールを取得する</span><span class="sxs-lookup"><span data-stu-id="01214-121">Get locale</span></span>' src='//codepen.io/MSEdgeDev/embed/VaRWwR/?height=300&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="01214-122">CodePen で MSEdgeDev ( @MSEdgeDev ) による Pen Get ロケール <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'> </a> <a href='http://codepen.io/MSEdgeDev'> </a> <a href='http://codepen.io'> を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="01214-122">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'>Get locale</a>by MSEdgeDev (<a href='http://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span>
</iframe>
