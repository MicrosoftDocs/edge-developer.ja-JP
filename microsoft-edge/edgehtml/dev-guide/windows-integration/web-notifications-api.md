---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: Web 通知 API を使用して、Web サイトが Microsoft Edge ブラウザーのコンテキスト外でユーザーに通知を送信する方法について説明します。
title: Web 通知 API - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2be201a790c6fca1526c8b6eb13e4203e8e53206
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234822"
---
# <span data-ttu-id="b74d6-104">Web 通知 API</span><span class="sxs-lookup"><span data-stu-id="b74d6-104">Web Notifications API</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="b74d6-105">Web 通知 API を使用すると、Web サイトは Microsoft Edge ブラウザー内の Web ページのコンテキスト外でユーザーに通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="b74d6-105">The Web Notifications API allows websites to send users notifications outside the context of a webpage within the Microsoft Edge browser.</span></span>  <span data-ttu-id="b74d6-106">この機能の動作の例として、Skype のようなメッセージング アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="b74d6-106">An example of this feature in action would be with a messaging application like Skype.</span></span>  <span data-ttu-id="b74d6-107">ユーザーが新しいメッセージを受信すると、デスクトップに通知が表示され、メッセージが通知されます。</span><span class="sxs-lookup"><span data-stu-id="b74d6-107">When a user would receive a new message, a notification would appear on their desktop, alerting them of the message.</span></span>  <span data-ttu-id="b74d6-108">Web 通知は、Windows 10 内の通知プラットフォームおよびアクション センターと完全に統合されています。</span><span class="sxs-lookup"><span data-stu-id="b74d6-108">Web Notifications are fully integrated with the Notification Platform and the Action Center within Windows 10.</span></span>  

## <span data-ttu-id="b74d6-109">通知の作成</span><span class="sxs-lookup"><span data-stu-id="b74d6-109">Creating a notification</span></span>  

<span data-ttu-id="b74d6-110">次の CodePen は、タイトル、アイコン、本文のオプションが設定[](https://msdn.microsoft.com/library/mt710826)された[Notification](https://msdn.microsoft.com/library/mt710818)オブジェクトを作成して、Skype[のモック](https://msdn.microsoft.com/library/mt710814)[通知を](https://msdn.microsoft.com/library/mt710811)作成します。</span><span class="sxs-lookup"><span data-stu-id="b74d6-110">The CodePen below creates a mock Skype notification by making a [Notification](https://msdn.microsoft.com/library/mt710818) object with the [title](https://msdn.microsoft.com/library/mt710826), [icon](https://msdn.microsoft.com/library/mt710814), and [body](https://msdn.microsoft.com/library/mt710811) options set:</span></span>  

<iframe height='295' scrolling='no' title='<span data-ttu-id="b74d6-111">Web 通知</span><span class="sxs-lookup"><span data-stu-id="b74d6-111">Web notifications</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="b74d6-112">CodePen で Microsoft Edge Docs ( @MicrosoftEdgeDocumentation ) によるペン <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> Web </a> <a href='https://codepen.io/MicrosoftEdgeDocumentation'> </a> 通知 <a href='https://codepen.io'> を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="b74d6-112">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'>Web notifications</a> by Microsoft Edge Docs (<a href='https://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

<span data-ttu-id="b74d6-113">通知ごとにアイコンを指定 **する方法を** 強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="b74d6-113">It is strongly recommended that an **icon** be specified for each notification.</span></span>  <span data-ttu-id="b74d6-114">これにより、UI の観点からの通知が向上するだけでなく、通知の送信場所をユーザーに通知するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b74d6-114">This not only improves a notification from a UI point of view, but also helps alert users of where the notification is being sent from.</span></span>  

<span data-ttu-id="b74d6-115">Web 通知の作成に関するチュートリアルと、Windows 10 内での動作を確認するには、以下のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b74d6-115">Watch the video below for a walkthrough on creating a web notification and to see it's behavior within Windows 10!</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]  

### <span data-ttu-id="b74d6-116">通知プロパティ</span><span class="sxs-lookup"><span data-stu-id="b74d6-116">Notification properties</span></span>  

<span data-ttu-id="b74d6-117">通知は、次のプロパティで設定できます。</span><span class="sxs-lookup"><span data-stu-id="b74d6-117">Notifications can be set with the following properties:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-118">body</span><span class="sxs-lookup"><span data-stu-id="b74d6-118">body</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/body)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-119">通知の本文テキスト。</span><span class="sxs-lookup"><span data-stu-id="b74d6-119">The body text of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-120">dir</span><span class="sxs-lookup"><span data-stu-id="b74d6-120">dir</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/dir)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-121">通知のテキストの方向。</span><span class="sxs-lookup"><span data-stu-id="b74d6-121">The direction of the notification's text.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-122">icon</span><span class="sxs-lookup"><span data-stu-id="b74d6-122">icon</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/icon)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-123">アイコンに使用される通知の URL。</span><span class="sxs-lookup"><span data-stu-id="b74d6-123">The notification's URL that is used for its icon.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-124">lang</span><span class="sxs-lookup"><span data-stu-id="b74d6-124">lang</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/lang)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-125">通知の言語。</span><span class="sxs-lookup"><span data-stu-id="b74d6-125">The language of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-126">permission</span><span class="sxs-lookup"><span data-stu-id="b74d6-126">permission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-127">現在のオリジンに対してユーザーが付与した現在の通知表示アクセス許可。</span><span class="sxs-lookup"><span data-stu-id="b74d6-127">The current notification display permission the user has granted for the current origin.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-128">tag</span><span class="sxs-lookup"><span data-stu-id="b74d6-128">tag</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/tag)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-129">通知のタグ。</span><span class="sxs-lookup"><span data-stu-id="b74d6-129">The tag of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-130">title</span><span class="sxs-lookup"><span data-stu-id="b74d6-130">title</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/title)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-131">通知のタイトル。</span><span class="sxs-lookup"><span data-stu-id="b74d6-131">The title of the notification.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="b74d6-132">通知イベント</span><span class="sxs-lookup"><span data-stu-id="b74d6-132">Notification events</span></span>  

<span data-ttu-id="b74d6-133">Notification オブジェクトでは、次のイベントが [使用](https://developer.mozilla.org/docs/Web/API/Notification) されます。</span><span class="sxs-lookup"><span data-stu-id="b74d6-133">The following events are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-134">onclick</span><span class="sxs-lookup"><span data-stu-id="b74d6-134">onclick</span></span>](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-135">ユーザーが通知をクリックすると発生します。</span><span class="sxs-lookup"><span data-stu-id="b74d6-135">Fires when a notification is clicked by the user.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-136">onclose</span><span class="sxs-lookup"><span data-stu-id="b74d6-136">onclose</span></span>](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-137">ユーザーによって通知が閉じたり、自動タイムアウトが発生したりすると発生します。</span><span class="sxs-lookup"><span data-stu-id="b74d6-137">Fires when a notification is closed by the user or an auto timeout.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-138">onerror</span><span class="sxs-lookup"><span data-stu-id="b74d6-138">onerror</span></span>](https://developer.mozilla.org/docs/Web/API/Element/error_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-139">通知の処理中にエラーが発生すると発生します。</span><span class="sxs-lookup"><span data-stu-id="b74d6-139">Fires when an error occurs while handling a notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-140">onshow</span><span class="sxs-lookup"><span data-stu-id="b74d6-140">onshow</span></span>](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-141">通知が表示された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="b74d6-141">Fires when a notification is displayed.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="b74d6-142">通知メソッド</span><span class="sxs-lookup"><span data-stu-id="b74d6-142">Notification methods</span></span>  

<span data-ttu-id="b74d6-143">Notification オブジェクトでは、次のメソッドが [使用](https://developer.mozilla.org/docs/Web/API/Notification) されます。</span><span class="sxs-lookup"><span data-stu-id="b74d6-143">The following methods are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-144">close</span><span class="sxs-lookup"><span data-stu-id="b74d6-144">close</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/close)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-145">表示された通知を閉じます。</span><span class="sxs-lookup"><span data-stu-id="b74d6-145">Closes a displayed notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="b74d6-146">requestPermission</span><span class="sxs-lookup"><span data-stu-id="b74d6-146">requestPermission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b74d6-147">現在のオリジンによる通知の表示を許可するアクセス許可をユーザーに要求します。</span><span class="sxs-lookup"><span data-stu-id="b74d6-147">Requests permission from the user to allow notifications to be displayed by the current origin.</span></span>  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="b74d6-148">通知のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b74d6-148">Notification permissions</span></span>  

<span data-ttu-id="b74d6-149">Microsoft Edge を使用すると、ユーザーは特定の Web サイト ドメインごとに通知のアクセス許可を管理できます。</span><span class="sxs-lookup"><span data-stu-id="b74d6-149">Microsoft Edge allows users to manage notifications permissions for each specific website domain.</span></span>  <span data-ttu-id="b74d6-150">ドメインから通知の表示を求めるメッセージが\*\*\*\* 表示された\*\*\*\* 場合は、ユーザーが [はい] または [いいえ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b74d6-150">It's up to the user to either select **Yes** or **No** when asked by the domain to let it show notifications.</span></span>  <span data-ttu-id="b74d6-151">[requestPermission メソッドは](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)、アクセス許可の状態を 、または `granted` `denied` `default` .</span><span class="sxs-lookup"><span data-stu-id="b74d6-151">The [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission) method is used to signal the permission state as either `granted`, `denied`, or `default`.</span></span>  <span data-ttu-id="b74d6-152">値は、ユーザーが決定を行いたことがないかどうかを示します。これは、次の値 `default` と同等と見なされます `denied` 。</span><span class="sxs-lookup"><span data-stu-id="b74d6-152">A value of `default` indicates that the user hasn't made a decision, which is seen as the equivalent of `denied`.</span></span>  

## <span data-ttu-id="b74d6-153">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="b74d6-153">API reference</span></span>  

[<span data-ttu-id="b74d6-154">Web 通知</span><span class="sxs-lookup"><span data-stu-id="b74d6-154">Web Notifications</span></span>](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## <span data-ttu-id="b74d6-155">仕様</span><span class="sxs-lookup"><span data-stu-id="b74d6-155">Specification</span></span>  

[<span data-ttu-id="b74d6-156">Web 通知</span><span class="sxs-lookup"><span data-stu-id="b74d6-156">Web Notifications</span></span>](https://notifications.spec.whatwg.org)  
