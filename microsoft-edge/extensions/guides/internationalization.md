---
description: さまざまな言語の拡張機能にアクセスできるようにし、国際化ガイドを使用して言語の文字列をテストします。
title: 拡張機能-国際化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: d1f553d0e3e39192e68665fe6720daa811777c0b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569467"
---
# <span data-ttu-id="06558-104">」</span><span class="sxs-lookup"><span data-stu-id="06558-104">Internationalization</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="06558-105">内線番号をさまざまなユーザーが利用できるようにするには、その他の国で開発することが重要です。</span><span class="sxs-lookup"><span data-stu-id="06558-105">In order to make your extension accessible to a variety of different people, it is important to develop with other countries in mind.</span></span> <span data-ttu-id="06558-106">Microsoft Edge extensions では、言語を簡単に変更できるように、さまざまな言語の文字列を拡張子に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="06558-106">Microsoft Edge extensions allows you to add different language strings to your extensions so that their language can easily be changed.</span></span>

<span data-ttu-id="06558-107">拡張機能の国際化の詳細については、「MDN の[国際化ガイド」](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="06558-107">For more information on internationalizing your extension, check out MDN's [Internationalization guide](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization).</span></span>


## <span data-ttu-id="06558-108">言語のテスト</span><span class="sxs-lookup"><span data-stu-id="06558-108">Testing languages</span></span>

<span data-ttu-id="06558-109">言語の文字列をテストするには、最初に Windows の表示言語をテスト対象の言語に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06558-109">To test your language strings, you first need to set the Windows display language to the language that you want to test for.</span></span>

<span data-ttu-id="06558-110">Windows の表示言語を変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="06558-110">Follow the steps below to change the Windows display language:</span></span>

1. <span data-ttu-id="06558-111">[設定] アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="06558-111">Open the Settings app.</span></span>

   ![設定アプリケーション](./../media/loc-settings.png)
2. <span data-ttu-id="06558-113">[時刻 & 言語] を選びます。</span><span class="sxs-lookup"><span data-stu-id="06558-113">Select "Time & language".</span></span>
3. <span data-ttu-id="06558-114">[地域 & 言語] を選びます。</span><span class="sxs-lookup"><span data-stu-id="06558-114">Select "Region & language".</span></span>
4. <span data-ttu-id="06558-115">[+ 言語の追加] を選択して、利用可能な言語のリストに言語を追加します。</span><span class="sxs-lookup"><span data-stu-id="06558-115">Select "+ Add a language" to add the language to the list of possible languages.</span></span>
5. <span data-ttu-id="06558-116">テストする [言語] リストから言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="06558-116">Choose the language from the "Languages" list that you want to test.</span></span>
6. <span data-ttu-id="06558-117">[既定に設定] ボタンを選択します (PC の再起動が必要な場合があります)。</span><span class="sxs-lookup"><span data-stu-id="06558-117">Select the "Set as default" button (you may need to restart your PC).</span></span>
7. <span data-ttu-id="06558-118">Microsoft Edge を開き、ロケールに対して定義された文字列が予期したとおりに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="06558-118">Open Microsoft Edge and verify that the strings defined for the locale appear as expected.</span></span>

<span data-ttu-id="06558-119">[NavigatorLanguage](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language)プロパティを使うと、Microsoft Edge が Windows の表示言語に正しいと判断したことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="06558-119">By using the [NavigatorLanguage.language](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language) property, you can verify that the language Microsoft Edge has determined to be the Windows display language is correct.</span></span>

<span data-ttu-id="06558-120">以下の CodePen のボタンをクリックすると、お使いのブラウザーの表示言語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="06558-120">Click the button in the CodePen below to see the display language of your browser.</span></span>

<iframe height='300' scrolling='no' title='<span data-ttu-id="06558-121">ロケールを取得する</span><span class="sxs-lookup"><span data-stu-id="06558-121">Get locale</span></span>' src='//codepen.io/MSEdgeDev/embed/VaRWwR/?height=300&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="06558-122"><a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'> </a> CodePen の「MSEdgeDev (@MSEdgeDev) でペンを取得する」を参照してください <a href='http://codepen.io/MSEdgeDev'> </a> <a href='http://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="06558-122">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'>Get locale</a>by MSEdgeDev (<a href='http://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span>
</iframe>
