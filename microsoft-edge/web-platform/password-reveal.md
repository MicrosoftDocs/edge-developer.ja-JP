---
description: パスワード表示ボタンの表示のカスタマイズに関するガイダンスを提供します。
title: パスワード表示ボタンをカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: Microsoft Edge, 互換性, Web プラットフォーム, パスワード表示, 目のアイコン
ms.openlocfilehash: af8120aad7316ffc051113591e770fa913814eb3
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327721"
---
# <span data-ttu-id="637a6-104">パスワード表示ボタンをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="637a6-104">Customize the password reveal button</span></span>  

<span data-ttu-id="637a6-105">`password`Microsoft Edge の入力の種類には、パスワード表示**コントロールが含**まれています。</span><span class="sxs-lookup"><span data-stu-id="637a6-105">The `password` input type in Microsoft Edge includes a **password reveal** control.</span></span>  <span data-ttu-id="637a6-106">ユーザーは、パスワード入力ボタン **を選択して** パスワード フィールドを **表示** できます。</span><span class="sxs-lookup"><span data-stu-id="637a6-106">A user may choose the **password input** button to reveal the **password** field.</span></span>  <span data-ttu-id="637a6-107">表示されたパスワード **フィールドは** 、ユーザーがパスワードが正しいか確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="637a6-107">The revealed **password** field helps the user verify if the password is correctly.</span></span>  <span data-ttu-id="637a6-108">ユーザーがパスワード フィールドにテキストを入力 した後、ユーザーはパスワード表示ボタン を選択するか、入力の表示/非表示を切り替 `Alt` + `F8` える選択を行います。</span><span class="sxs-lookup"><span data-stu-id="637a6-108">After a user has entered text in the **password** field, a user may choose the **password reveal** button or select `Alt`+`F8` to toggle visibility of the input.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="637a6-109">ユーザー **が** 入力した文字をドットで非表示にしたパスワード フィールド。</span><span class="sxs-lookup"><span data-stu-id="637a6-109">A **password** field with dots hiding the characters entered by a user.</span></span>  <span data-ttu-id="637a6-110">パスワード **表示ボタン** は、パスワード フィールドの右側に **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="637a6-110">The **password reveal** button appears to the right of the **password** field.</span></span>
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-off.msft.png" alt-text="目の形をしたアイコンが、パスワード テキストを非表示にするドットの横に表示されます。" lightbox="./media/mdn-demo-password-reveal-off.msft.png":::
         <span data-ttu-id="637a6-112">目の形をしたアイコンが、パスワード テキストを非表示にするドットの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="637a6-112">The eye-shaped icon appears next to the dots that hide the password text</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="637a6-113">パスワード表示 **ボタンを切** り替え、目のアイコンをスラッシュで目のアイコンに変更し、元のパスワード テキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="637a6-113">Toggle the **password reveal** button to change the eye icon to an eye icon with a slash through it, and to reveal the original password text.</span></span>  
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-on.msft.png" alt-text="目の形をしたアイコンにはスラッシュが付き、元のパスワード テキストが表示されます。" lightbox="./media/mdn-demo-password-reveal-on.msft.png":::
         <span data-ttu-id="637a6-115">目の形をしたアイコンにはスラッシュが付き、元のパスワード テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="637a6-115">The The eye-shaped icon has a slash on it and the original password text is displayed</span></span> :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="637a6-116">既定では、パスワード表示 **ボタンは** 、設定が設定されているすべての HTML 要素のシャドウ DOM `input` `type` に挿入されます `"password"` 。</span><span class="sxs-lookup"><span data-stu-id="637a6-116">By default, the **password reveal** button inserts into the Shadow DOM of all HTML `input` elements with the `type` set to `"password"`.</span></span>  <span data-ttu-id="637a6-117">Microsoft Edge バージョン 87 から、 [ユーザーまたは企業][DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled] は、この機能をグローバルに無効にできます。</span><span class="sxs-lookup"><span data-stu-id="637a6-117">Starting with Microsoft Edge Version 87, users or [enterprises][DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled] may disable this feature globally.</span></span>  <span data-ttu-id="637a6-118">Web デザイナーと開発者は、ほとんどの Microsoft Edge ユーザーに既定のエクスペリエンスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="637a6-118">You, web designers and developers, should expect most Microsoft Edge users to have the default experience.</span></span>  

## <span data-ttu-id="637a6-119">パスワード表示コントロールを削除する</span><span class="sxs-lookup"><span data-stu-id="637a6-119">Remove the password reveal control</span></span>  

<span data-ttu-id="637a6-120">擬似要素をターゲットにすることで **、パスワード** 表示ボタンを完全に `::-ms-reveal` 削除できます。</span><span class="sxs-lookup"><span data-stu-id="637a6-120">You may completely remove the **password reveal** button by targeting the `::-ms-reveal` pseudo element.</span></span>  

```css
::-ms-reveal {
    display: none;
}
```  

<span data-ttu-id="637a6-121">ただし、パスワード表示ボタンの利用 **を検討する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="637a6-121">However, you should consider taking advantage of the **password reveal** button.</span></span>  <span data-ttu-id="637a6-122">ネイティブの **パスワード表示ボタンには** 、動作 [に組み込みの](#visibility-of-the-control) 重要なセキュリティ対策があります。</span><span class="sxs-lookup"><span data-stu-id="637a6-122">The native **password reveal** button has important [security measures](#visibility-of-the-control) built into the behavior.</span></span>  

## <span data-ttu-id="637a6-123">コントロール スタイルをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="637a6-123">Customize the control style</span></span>  

<span data-ttu-id="637a6-124">代わりに、コントロールを完全に削除する代わりに、パスワード表示ボタンのスタイルを Web サイトの表示言語に合わせて変更できます。</span><span class="sxs-lookup"><span data-stu-id="637a6-124">Instead of fully removing the control, you may instead modify the styling of the **password reveal** button to better match the visual language of the website.</span></span>  <span data-ttu-id="637a6-125">次のスニペットは、このようなスタイルの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="637a6-125">The following snippet provides an example of such styling.</span></span>  

```css
::-ms-reveal {
    border: 1px solid transparent;
    border-radius: 50%;
    box-shadow: 0 0 3px currentColor;
}
```  

<span data-ttu-id="637a6-126">パスワード表示ボタンのスタイルを設定する場合は、次の **ことを念頭に置いてお** きます。</span><span class="sxs-lookup"><span data-stu-id="637a6-126">Keep the following things in mind when you style the **password reveal** button.</span></span>  

*   <span data-ttu-id="637a6-127">目のアイコンは背景画像として実装されます。</span><span class="sxs-lookup"><span data-stu-id="637a6-127">The eye icon implements as a background image.</span></span>  <span data-ttu-id="637a6-128">パスワード表示ボタンに背景色を追加 するには、shorthand プロパティの代わりに CSS `background-color` `background` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="637a6-128">To add a background color to the **password reveal** button, use the CSS `background-color` property instead of the `background` shorthand property.</span></span>  
*   <span data-ttu-id="637a6-129">パスワード表示ボタンのサイズとスケール **を調整** できます。</span><span class="sxs-lookup"><span data-stu-id="637a6-129">You may adjust the size and scale of the **password reveal** button.</span></span>  
    
    > [!NOTE]
    ><span data-ttu-id="637a6-130">ブラウザーは、パスワード入力コントロールの境界の外側でオーバーフローを非表示にしています。</span><span class="sxs-lookup"><span data-stu-id="637a6-130">The browser hides any overflow outside of the bounds of the password input control.</span></span>  
    
*   <span data-ttu-id="637a6-131">現在、パスワード表示ボタンのトグル状態のスタイルを設定できる **状態セレクターはありません** 。</span><span class="sxs-lookup"><span data-stu-id="637a6-131">Currently, no state selectors are available to style the toggled state of the **password reveal** button.</span></span>  
    
## <span data-ttu-id="637a6-132">コントロールの可視性</span><span class="sxs-lookup"><span data-stu-id="637a6-132">Visibility of the control</span></span>  

<span data-ttu-id="637a6-133">パスワード **表示ボタンは** 、ユーザーがパスワード フィールドにテキストを入力するまで **使用** できません。</span><span class="sxs-lookup"><span data-stu-id="637a6-133">The **password reveal** button is unavailable until the user enters text into the **password** field.</span></span>  <span data-ttu-id="637a6-134">ユーザーのパスワード 入力をセキュリティで保護するために、ブラウザーは次のシナリオでボタンを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="637a6-134">To help keep the user's password entry secure, the browser suppresses the button in the following scenarios.</span></span>

*   <span data-ttu-id="637a6-135">フォーカスがパスワード フィールドから離 **れた場合** 、ブラウザーはパスワード表示ボタン **を削除** します。</span><span class="sxs-lookup"><span data-stu-id="637a6-135">If focus moves away from the **password** field, the browser removes the **password reveal** button.</span></span>  
*   <span data-ttu-id="637a6-136">スクリプトがパスワード フィールド **を変更すると** 、ブラウザーはパスワード表示ボタン **を削除** します。</span><span class="sxs-lookup"><span data-stu-id="637a6-136">If scripts modify the **password** field, the browser removes the **password reveal** button.</span></span>  
*   <span data-ttu-id="637a6-137">ユーザーがパスワード表示**ボタンを削除**した場合、パスワード表示ボタンが再び表示される 前に、ユーザーはパスワード フィールドの**内容を削除**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="637a6-137">If a user removes the **password reveal** button, the user must delete the contents of the **password** field before the **password reveal** button displays again.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="637a6-138">この機能により、ユーザーがロック解除されたデバイスから離れた場合に、ユーザーがパスワードを表示するために細かい調整を行うのを防ぐことができません。</span><span class="sxs-lookup"><span data-stu-id="637a6-138">This feature prevents someone from making a minor adjustment to view the password, should the user step away from an unlocked device.</span></span>
    
<span data-ttu-id="637a6-139">パスワード**マネージャーを使用**してパスワード フィールド がオートフィルされた場合、パスワード表示ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="637a6-139">The **password reveal** button is unavailable if the **password** field autofills using the password manager.</span></span>  

<!-- links -->  

[DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled]: /deployedge/microsoft-edge-policies#passwordrevealenabled "PasswordRevealEnabled - Microsoft Edge - ポリシー|Microsoft Docs"  
