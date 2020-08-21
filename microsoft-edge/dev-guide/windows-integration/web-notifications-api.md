---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: Web 通知 API を使用して Web サイトでユーザーに通知を送信する方法について説明します。
title: Web Notifications API - デベロッパー ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 24b8a7b25fb3e0f0221f6d81b105d5d0374ea423
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941797"
---
# <span data-ttu-id="6eca2-104">Web 通知 API</span><span class="sxs-lookup"><span data-stu-id="6eca2-104">Web Notifications API</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="6eca2-105">Web Notifications API を使用すると、Web サイトは Microsoft Edge ブラウザー内の Web ページのコンテキスト外でユーザーに通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-105">The Web Notifications API allows websites to send users notifications outside the context of a webpage within the Microsoft Edge browser.</span></span>  <span data-ttu-id="6eca2-106">この機能の例として、Skype のようなメッセージング アプリケーションが使用されています。</span><span class="sxs-lookup"><span data-stu-id="6eca2-106">An example of this feature in action would be with a messaging application like Skype.</span></span>  <span data-ttu-id="6eca2-107">ユーザーが新しいメッセージを受信すると、デスクトップに通知が表示され、メッセージが通知されます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-107">When a user would receive a new message, a notification would appear on their desktop, alerting them of the message.</span></span>  <span data-ttu-id="6eca2-108">Web 通知は、Windows 10 内の通知プラットフォームとアクション センターと完全に統合されています。</span><span class="sxs-lookup"><span data-stu-id="6eca2-108">Web Notifications are fully integrated with the Notification Platform and the Action Center within Windows 10.</span></span>  

## <span data-ttu-id="6eca2-109">通知の作成</span><span class="sxs-lookup"><span data-stu-id="6eca2-109">Creating a notification</span></span>  

<span data-ttu-id="6eca2-110">以下の CodePen は、タイトル、アイコン、および本文オプションを設定した[Notification](https://msdn.microsoft.com/library/mt710818)通知オブジェクトを作成[title](https://msdn.microsoft.com/library/mt710826)して、[icon](https://msdn.microsoft.com/library/mt710814)マッキピボの Skype 通知[を](https://msdn.microsoft.com/library/mt710811)作成します。</span><span class="sxs-lookup"><span data-stu-id="6eca2-110">The CodePen below creates a mock Skype notification by making a [Notification](https://msdn.microsoft.com/library/mt710818) object with the [title](https://msdn.microsoft.com/library/mt710826), [icon](https://msdn.microsoft.com/library/mt710814), and [body](https://msdn.microsoft.com/library/mt710811) options set:</span></span>  

<iframe height='295' scrolling='no' title='<span data-ttu-id="6eca2-111">Web 通知</span><span class="sxs-lookup"><span data-stu-id="6eca2-111">Web notifications</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="6eca2-112"><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> </a> CodePen で Microsoft Edge Docs <a href='https://codepen.io/MicrosoftEdgeDocumentation'> (@MicrosoftEdgeDocumentation) によるペン Web の通知 </a> <a href='https://codepen.io'> を確認できます </a> 。</span><span class="sxs-lookup"><span data-stu-id="6eca2-112">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'>Web notifications</a> by Microsoft Edge Docs (<a href='https://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

<span data-ttu-id="6eca2-113">通知ごとにアイコンを指定すること **を** 強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6eca2-113">It is strongly recommended that an **icon** be specified for each notification.</span></span>  <span data-ttu-id="6eca2-114">これにより、UI のビューに表示される通知は改善されるだけでなく、通知の送信先をユーザーに通知するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-114">This not only improves a notification from a UI point of view, but also helps alert users of where the notification is being sent from.</span></span>  

<span data-ttu-id="6eca2-115">下のビデオでは、Web 通知の作成方法と、Windows 10 内での動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-115">Watch the video below for a walkthrough on creating a web notification and to see it's behavior within Windows 10!</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]  

### <span data-ttu-id="6eca2-116">通知のプロパティ</span><span class="sxs-lookup"><span data-stu-id="6eca2-116">Notification properties</span></span>  

<span data-ttu-id="6eca2-117">次のプロパティを使用して通知を設定できます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-117">Notifications can be set with the following properties:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-118">body</span><span class="sxs-lookup"><span data-stu-id="6eca2-118">body</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/body)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-119">通知の本文テキスト。</span><span class="sxs-lookup"><span data-stu-id="6eca2-119">The body text of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-120">dir</span><span class="sxs-lookup"><span data-stu-id="6eca2-120">dir</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/dir)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-121">通知のテキストの方向。</span><span class="sxs-lookup"><span data-stu-id="6eca2-121">The direction of the notification's text.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-122">icon</span><span class="sxs-lookup"><span data-stu-id="6eca2-122">icon</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/icon)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-123">通知の URL はアイコンに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-123">The notification's URL that is used for its icon.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-124">lang</span><span class="sxs-lookup"><span data-stu-id="6eca2-124">lang</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/lang)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-125">通知の言語。</span><span class="sxs-lookup"><span data-stu-id="6eca2-125">The language of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-126">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="6eca2-126">permission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-127">現在の通知表示アクセス許可は、ユーザーが現在の送信先の送信先の位置を付与したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="6eca2-127">The current notification display permission the user has granted for the current origin.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-128">tag</span><span class="sxs-lookup"><span data-stu-id="6eca2-128">tag</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/tag)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-129">通知のタグ。</span><span class="sxs-lookup"><span data-stu-id="6eca2-129">The tag of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-130">title</span><span class="sxs-lookup"><span data-stu-id="6eca2-130">title</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/title)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-131">通知のタイトル。</span><span class="sxs-lookup"><span data-stu-id="6eca2-131">The title of the notification.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="6eca2-132">通知イベント</span><span class="sxs-lookup"><span data-stu-id="6eca2-132">Notification events</span></span>  

<span data-ttu-id="6eca2-133">Notification オブジェクトで次のイベントが [使用](https://developer.mozilla.org/docs/Web/API/Notification) されます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-133">The following events are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-134">onclick</span><span class="sxs-lookup"><span data-stu-id="6eca2-134">onclick</span></span>](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-135">ユーザーが通知をクリックしたときに、ファイアウォールします。</span><span class="sxs-lookup"><span data-stu-id="6eca2-135">Fires when a notification is clicked by the user.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-136">onclose</span><span class="sxs-lookup"><span data-stu-id="6eca2-136">onclose</span></span>](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-137">ユーザーまたは自動タイムアウトによって通知が閉じたときに、通知が閉じたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-137">Fires when a notification is closed by the user or an auto timeout.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-138">onerror</span><span class="sxs-lookup"><span data-stu-id="6eca2-138">onerror</span></span>](https://developer.mozilla.org/docs/Web/API/Element/error_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-139">通知の処理中にエラーが発生したときに、ファイアウォールを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eca2-139">Fires when an error occurs while handling a notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-140">オン</span><span class="sxs-lookup"><span data-stu-id="6eca2-140">onshow</span></span>](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-141">通知が表示されたときにファイアウォールを行います。</span><span class="sxs-lookup"><span data-stu-id="6eca2-141">Fires when a notification is displayed.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="6eca2-142">通知方法</span><span class="sxs-lookup"><span data-stu-id="6eca2-142">Notification methods</span></span>  

<span data-ttu-id="6eca2-143">Notification オブジェクトでは、次のメソッド [が使用](https://developer.mozilla.org/docs/Web/API/Notification) されます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-143">The following methods are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-144">close</span><span class="sxs-lookup"><span data-stu-id="6eca2-144">close</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/close)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-145">表示された通知を閉じます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-145">Closes a displayed notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6eca2-146">requestPermission</span><span class="sxs-lookup"><span data-stu-id="6eca2-146">requestPermission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6eca2-147">現在の場所に通知を表示することを許可する権限をユーザーに要求します。</span><span class="sxs-lookup"><span data-stu-id="6eca2-147">Requests permission from the user to allow notifications to be displayed by the current origin.</span></span>  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="6eca2-148">通知のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6eca2-148">Notification permissions</span></span>  

<span data-ttu-id="6eca2-149">Microsoft Edge を使用すると、ユーザーは特定の Web サイト ドメインに対する通知権限を管理できます。</span><span class="sxs-lookup"><span data-stu-id="6eca2-149">Microsoft Edge allows users to manage notifications permissions for each specific website domain.</span></span>  <span data-ttu-id="6eca2-150">ユーザーに通知を表示する準備ができた **ら、[はい** ] または **[い** いえ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6eca2-150">It's up to the user to either select **Yes** or **No** when asked by the domain to let it show notifications.</span></span>  <span data-ttu-id="6eca2-151">[requestPermission メ](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)ソッドは、アクセス許可状態をいずれかのアクセス許可状態として、または `granted` `denied` `default`</span><span class="sxs-lookup"><span data-stu-id="6eca2-151">The [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission) method is used to signal the permission state as either `granted`, `denied`, or `default`.</span></span>  <span data-ttu-id="6eca2-152">値は、ユーザーが同等の決める決める決済 `default` を下す値を示します `denied` 。</span><span class="sxs-lookup"><span data-stu-id="6eca2-152">A value of `default` indicates that the user hasn't made a decision, which is seen as the equivalent of `denied`.</span></span>  

## <span data-ttu-id="6eca2-153">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="6eca2-153">API reference</span></span>  

[<span data-ttu-id="6eca2-154">Web 通知</span><span class="sxs-lookup"><span data-stu-id="6eca2-154">Web Notifications</span></span>](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## <span data-ttu-id="6eca2-155">Specification</span><span class="sxs-lookup"><span data-stu-id="6eca2-155">Specification</span></span>  

[<span data-ttu-id="6eca2-156">Web 通知</span><span class="sxs-lookup"><span data-stu-id="6eca2-156">Web Notifications</span></span>](https://notifications.spec.whatwg.org)  
