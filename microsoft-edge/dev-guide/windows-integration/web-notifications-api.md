---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: Web 通知 API を使用して、Web サイトが Microsoft Edge ブラウザーのコンテキスト外でユーザー通知を送信できるようにする方法について説明します。
title: 開発ガイド-Web 通知 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/18/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: da563a333491ef699925adec6f97b3c21d3e54a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569172"
---
# <span data-ttu-id="20091-104">Web 通知 API</span><span class="sxs-lookup"><span data-stu-id="20091-104">Web Notifications API</span></span>

<span data-ttu-id="20091-105">Web 通知 API を使用すると、web サイトは Microsoft Edge ブラウザー内で web ページのコンテキスト外でユーザー通知を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="20091-105">The Web Notifications API allows websites to send users notifications outside the context of a webpage within the Microsoft Edge browser.</span></span> <span data-ttu-id="20091-106">この機能の例としては、Skype などのメッセージングアプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="20091-106">An example of this feature in action would be with a messaging application like Skype.</span></span> <span data-ttu-id="20091-107">ユーザーが新しいメッセージを受信すると、デスクトップに通知が表示され、メッセージが通知されます。</span><span class="sxs-lookup"><span data-stu-id="20091-107">When a user would receive a new message, a notification would appear on their desktop, alerting them of the message.</span></span> <span data-ttu-id="20091-108">Web 通知は、Windows 10 の通知プラットフォームとアクションセンターと完全に統合されています。</span><span class="sxs-lookup"><span data-stu-id="20091-108">Web Notifications are fully integrated with the Notification Platform and the Action Center within Windows 10.</span></span> 

## <span data-ttu-id="20091-109">通知の作成</span><span class="sxs-lookup"><span data-stu-id="20091-109">Creating a notification</span></span>

<span data-ttu-id="20091-110">以下の CodePen では、、、オプションセットを使用してオブジェクトを作成することで、モックの Skype 通知を作成し [`Notification`](https://msdn.microsoft.com/library/mt710818) [`title`](https://msdn.microsoft.com/library/mt710826) [`icon`](https://msdn.microsoft.com/library/mt710814) [`body`](https://msdn.microsoft.com/library/mt710811) ます。</span><span class="sxs-lookup"><span data-stu-id="20091-110">The CodePen below creates a mock Skype notification by making a [`Notification`](https://msdn.microsoft.com/library/mt710818) object with the [`title`](https://msdn.microsoft.com/library/mt710826), [`icon`](https://msdn.microsoft.com/library/mt710814), and [`body`](https://msdn.microsoft.com/library/mt710811) options set:</span></span>


<iframe height='295' scrolling='no' title='<span data-ttu-id="20091-111">Web 通知</span><span class="sxs-lookup"><span data-stu-id="20091-111">Web notifications</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="20091-112"><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> </a> CodePen で Microsoft Edge ドキュメント (@MicrosoftEdgeDocumentation) によるペン Web 通知を参照してください <a href='https://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='https://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="20091-112">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'>Web notifications</a> by Microsoft Edge Docs (<a href='https://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span>
</iframe>

<span data-ttu-id="20091-113">通知ごとに指定することを強くお勧め `icon` します。</span><span class="sxs-lookup"><span data-stu-id="20091-113">It is strongly recommended that an `icon` be specified for each notification.</span></span> <span data-ttu-id="20091-114">これにより、UI ポイントからの通知が改善されるだけでなく、通知が送信される場所をユーザーに通知することもできます。</span><span class="sxs-lookup"><span data-stu-id="20091-114">This not only improves a notification from a UI point of view, but also helps alert users of where the notification is being sent from.</span></span>

<span data-ttu-id="20091-115">Web 通知の作成と Windows 10 での動作の確認については、以下のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20091-115">Watch the video below for a walkthrough on creating a web notification and to see it's behavior within Windows 10!</span></span>


> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]

### <span data-ttu-id="20091-116">通知プロパティ</span><span class="sxs-lookup"><span data-stu-id="20091-116">Notification properties</span></span>

<span data-ttu-id="20091-117">通知を設定するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="20091-117">Notifications can be set with the following options:</span></span>

<span data-ttu-id="20091-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="20091-118">Property</span></span> | <span data-ttu-id="20091-119">説明</span><span class="sxs-lookup"><span data-stu-id="20091-119">Description</span></span>
:-------- | :----------
[<span data-ttu-id="20091-120">body</span><span class="sxs-lookup"><span data-stu-id="20091-120">body</span></span>](https://msdn.microsoft.com/library/mt710811) | <span data-ttu-id="20091-121">通知の本文テキスト。</span><span class="sxs-lookup"><span data-stu-id="20091-121">The body text of the notification.</span></span>
[<span data-ttu-id="20091-122">dir</span><span class="sxs-lookup"><span data-stu-id="20091-122">dir</span></span>](https://msdn.microsoft.com/library/mt710813) | <span data-ttu-id="20091-123">通知のテキストの方向。</span><span class="sxs-lookup"><span data-stu-id="20091-123">The direction of the notification's text.</span></span>
[<span data-ttu-id="20091-124">icon</span><span class="sxs-lookup"><span data-stu-id="20091-124">icon</span></span>](https://msdn.microsoft.com/library/mt710814) | <span data-ttu-id="20091-125">アイコンに使用される通知の URL。</span><span class="sxs-lookup"><span data-stu-id="20091-125">The notification's URL that is used for its icon.</span></span>
[<span data-ttu-id="20091-126">言語</span><span class="sxs-lookup"><span data-stu-id="20091-126">lang</span></span>](https://msdn.microsoft.com/library/mt710815) | <span data-ttu-id="20091-127">通知の言語。</span><span class="sxs-lookup"><span data-stu-id="20091-127">The language of the notification.</span></span>
[<span data-ttu-id="20091-128">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="20091-128">permission</span></span>](https://msdn.microsoft.com/library/mt670637) | <span data-ttu-id="20091-129">現在の起点に対してユーザーが付与した現在の通知表示アクセス許可。</span><span class="sxs-lookup"><span data-stu-id="20091-129">The current notification display permission the user has granted for the current origin.</span></span>
[<span data-ttu-id="20091-130">tag</span><span class="sxs-lookup"><span data-stu-id="20091-130">tag</span></span>](https://msdn.microsoft.com/library/mt710825) | <span data-ttu-id="20091-131">通知のタグ。</span><span class="sxs-lookup"><span data-stu-id="20091-131">The tag of the notification.</span></span>
[<span data-ttu-id="20091-132">title</span><span class="sxs-lookup"><span data-stu-id="20091-132">title</span></span>](https://msdn.microsoft.com/library/mt710826) | <span data-ttu-id="20091-133">通知のタイトル。</span><span class="sxs-lookup"><span data-stu-id="20091-133">The title of the notification.</span></span>

### <span data-ttu-id="20091-134">通知イベント</span><span class="sxs-lookup"><span data-stu-id="20091-134">Notification events</span></span>

<span data-ttu-id="20091-135">このオブジェクトでは、次のイベントが使用され [`Notification`](https://msdn.microsoft.com/library/mt710818) ます。</span><span class="sxs-lookup"><span data-stu-id="20091-135">The following events are used with the [`Notification`](https://msdn.microsoft.com/library/mt710818) object:</span></span>

<span data-ttu-id="20091-136">イベント</span><span class="sxs-lookup"><span data-stu-id="20091-136">Event</span></span> | <span data-ttu-id="20091-137">説明</span><span class="sxs-lookup"><span data-stu-id="20091-137">Description</span></span>
:-------- | :----------
[<span data-ttu-id="20091-138">onclick</span><span class="sxs-lookup"><span data-stu-id="20091-138">onclick</span></span>](https://msdn.microsoft.com/library/mt712180) | <span data-ttu-id="20091-139">ユーザーが通知をクリックしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="20091-139">Fires when a notification is clicked by the user.</span></span>
[<span data-ttu-id="20091-140">閉じる</span><span class="sxs-lookup"><span data-stu-id="20091-140">onclose</span></span>](https://msdn.microsoft.com/library/mt712178) | <span data-ttu-id="20091-141">ユーザーまたは自動タイムアウトによって通知が閉じられたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="20091-141">Fires when a notification is closed by the user or an auto timeout.</span></span>
[<span data-ttu-id="20091-142">時</span><span class="sxs-lookup"><span data-stu-id="20091-142">onerror</span></span>](https://msdn.microsoft.com/library/mt712181) | <span data-ttu-id="20091-143">通知の処理中にエラーが発生したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="20091-143">Fires when an error occurs while handling a notification.</span></span>
[<span data-ttu-id="20091-144">onshow</span><span class="sxs-lookup"><span data-stu-id="20091-144">onshow</span></span>](https://msdn.microsoft.com/library/mt712182) | <span data-ttu-id="20091-145">通知が表示されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="20091-145">Fires when a notification is displayed.</span></span>

### <span data-ttu-id="20091-146">通知方法</span><span class="sxs-lookup"><span data-stu-id="20091-146">Notification methods</span></span>

<span data-ttu-id="20091-147">このオブジェクトでは、次のメソッドが使用され [`Notification`](https://msdn.microsoft.com/library/mt710818) ます。</span><span class="sxs-lookup"><span data-stu-id="20091-147">The following methods are used with the [`Notification`](https://msdn.microsoft.com/library/mt710818) object:</span></span>

<span data-ttu-id="20091-148">メソッド</span><span class="sxs-lookup"><span data-stu-id="20091-148">Method</span></span> | <span data-ttu-id="20091-149">[説明]</span><span class="sxs-lookup"><span data-stu-id="20091-149">Description</span></span>
:-------- | :----------
[<span data-ttu-id="20091-150">close</span><span class="sxs-lookup"><span data-stu-id="20091-150">close</span></span>](https://msdn.microsoft.com/library/mt670636) | <span data-ttu-id="20091-151">表示された通知を閉じます。</span><span class="sxs-lookup"><span data-stu-id="20091-151">Closes a displayed notification.</span></span>
[<span data-ttu-id="20091-152">requestPermission</span><span class="sxs-lookup"><span data-stu-id="20091-152">requestPermission</span></span>](https://msdn.microsoft.com/library/mt710824) | <span data-ttu-id="20091-153">現在の起点によって通知が表示されるように、ユーザーにアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="20091-153">Requests permission from the user to allow notifications to be displayed by the current origin.</span></span>

## <span data-ttu-id="20091-154">通知のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="20091-154">Notification permissions</span></span>

<span data-ttu-id="20091-155">Microsoft Edge では、ユーザーが特定の web サイトドメインごとに通知のアクセス許可を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="20091-155">Microsoft Edge allows users to manage notifications permissions for each specific website domain.</span></span> <span data-ttu-id="20091-156">通知を表示するようにドメインによって要求された場合は、ユーザーが [はい] または [いいえ] を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="20091-156">It's up to the user to either select "Yes" or "No" when asked by the domain to let it show notifications.</span></span> <span data-ttu-id="20091-157">メソッドは、、 [`requestPermission`](https://msdn.microsoft.com/library/mt710824) 、またはのいずれかとしてアクセス許可の状態を通知するために使われ `granted` `denied` `default` ます。</span><span class="sxs-lookup"><span data-stu-id="20091-157">The [`requestPermission`](https://msdn.microsoft.com/library/mt710824) method is used to signal the permission state as either `granted`, `denied`, or `default`.</span></span> <span data-ttu-id="20091-158">値は、 `default` ユーザーが決定を行っていないことを示します。これは、という値に `denied` なります。</span><span class="sxs-lookup"><span data-stu-id="20091-158">A value of `default` indicates that the user hasn't made a decision, which is seen as the equivalent of `denied`.</span></span>




## <span data-ttu-id="20091-159">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="20091-159">API reference</span></span>

[<span data-ttu-id="20091-160">Web 通知</span><span class="sxs-lookup"><span data-stu-id="20091-160">Web Notifications</span></span>](https://msdn.microsoft.com/library/mt710827)

## <span data-ttu-id="20091-161">キャスト</span><span class="sxs-lookup"><span data-stu-id="20091-161">Specification</span></span>

[<span data-ttu-id="20091-162">Web 通知</span><span class="sxs-lookup"><span data-stu-id="20091-162">Web Notifications</span></span>](https://notifications.spec.whatwg.org)
