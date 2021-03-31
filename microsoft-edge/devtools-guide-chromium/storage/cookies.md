---
description: Microsoft Edge DevTools を使用してページの HTTP Cookie を表示、編集、および削除する方法について説明します。
title: Microsoft Edge DevTools で Cookie を表示、編集、および削除する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c208ca628fe91ed5922bc36566be2b9bdd20ec0b
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439683"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="view-edit-and-delete-cookies-with-microsoft-edge-devtools"></a><span data-ttu-id="50f1d-104">Microsoft Edge DevTools で Cookie を表示、編集、および削除する</span><span class="sxs-lookup"><span data-stu-id="50f1d-104">View, edit, and delete cookies with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="50f1d-105">[HTTP Cookie は][MDNHTTPCookies] 、主にユーザー セッションの管理、ユーザーの個人用設定の保存、ユーザーの動作の追跡に使用されます。</span><span class="sxs-lookup"><span data-stu-id="50f1d-105">[HTTP Cookies][MDNHTTPCookies] are mainly used to manage user sessions, store user personalization preferences, and track user behavior.</span></span>  <span data-ttu-id="50f1d-106">Cookie は、このページが Web 全体で見つかった **Cookie** 同意フォームを使用しているすべての迷惑な原因です。</span><span class="sxs-lookup"><span data-stu-id="50f1d-106">Cookies are also the cause of all of the annoying **this page uses cookies** consent forms that are found across the web.</span></span>  <span data-ttu-id="50f1d-107">次のガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使用して Web ページの HTTP Cookie を表示、編集、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50f1d-107">The following guide teaches you how to view, edit, and delete the HTTP cookies for a webpage with [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <a name="open-the-cookies-pane"></a><span data-ttu-id="50f1d-108">Cookie ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="50f1d-108">Open the Cookies pane</span></span>  

1.  <span data-ttu-id="50f1d-109">[DevTools を開きます][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="50f1d-109">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="50f1d-110">[アプリケーション] **タブを** 選択して、[アプリケーション] パネル **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="50f1d-110">Choose the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="50f1d-111">[ **マニフェスト] ウィンドウ** が開きます。</span><span class="sxs-lookup"><span data-stu-id="50f1d-111">The **Manifest** pane should open.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="50f1d-113">図 1: マニフェスト ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="50f1d-113">Figure 1:  The Manifest pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="50f1d-114">[記憶域 **] で** **[Cookie] を展開**し、原点を選択します。</span><span class="sxs-lookup"><span data-stu-id="50f1d-114">Under **Storage** expand **Cookies**, then select an origin.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-cookies-selected.msft.png" alt-text="[Cookie] ウィンドウ" lightbox="../media/storage-application-storage-cookies-selected.msft.png":::
       <span data-ttu-id="50f1d-116">図 2: Cookie ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="50f1d-116">Figure 2:  The Cookies pane</span></span>  
    :::image-end:::  

## <a name="fields"></a><span data-ttu-id="50f1d-117">フィールド</span><span class="sxs-lookup"><span data-stu-id="50f1d-117">Fields</span></span>  

<span data-ttu-id="50f1d-118">Cookie **テーブルには** 、次のフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="50f1d-118">The **Cookies** table contains the following fields.</span></span>  

*   <span data-ttu-id="50f1d-119">**[名前]**。</span><span class="sxs-lookup"><span data-stu-id="50f1d-119">**Name**.</span></span>  <span data-ttu-id="50f1d-120">Cookie の名前。</span><span class="sxs-lookup"><span data-stu-id="50f1d-120">The name of the cookie.</span></span>  
*   <span data-ttu-id="50f1d-121">**値**。</span><span class="sxs-lookup"><span data-stu-id="50f1d-121">**Value**.</span></span>  <span data-ttu-id="50f1d-122">Cookie の値。</span><span class="sxs-lookup"><span data-stu-id="50f1d-122">The value of the cookie.</span></span>  
*   <span data-ttu-id="50f1d-123">**ドメイン**.</span><span class="sxs-lookup"><span data-stu-id="50f1d-123">**Domain**.</span></span>  <span data-ttu-id="50f1d-124">Cookie の受信を許可されているホスト。</span><span class="sxs-lookup"><span data-stu-id="50f1d-124">The hosts that are allowed to receive the cookie.</span></span>  <span data-ttu-id="50f1d-125">[Cookie の [スコープ] に移動します][MDNHTTPCookiesScope]。</span><span class="sxs-lookup"><span data-stu-id="50f1d-125">Navigate to [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="50f1d-126">**Path**.</span><span class="sxs-lookup"><span data-stu-id="50f1d-126">**Path**.</span></span>  <span data-ttu-id="50f1d-127">ヘッダーを送信するために要求された URL に存在する必要 `Cookie` がある URL。</span><span class="sxs-lookup"><span data-stu-id="50f1d-127">The URL that must exist in the requested URL in order to send the `Cookie` header.</span></span>  <span data-ttu-id="50f1d-128">[Cookie の [スコープ] に移動します][MDNHTTPCookiesScope]。</span><span class="sxs-lookup"><span data-stu-id="50f1d-128">Navigate to [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="50f1d-129">**有効期限 / 最大経過時間**。</span><span class="sxs-lookup"><span data-stu-id="50f1d-129">**Expires / Max-Age**.</span></span>  <span data-ttu-id="50f1d-130">Cookie の有効期限または最大有効期限。</span><span class="sxs-lookup"><span data-stu-id="50f1d-130">The expiration date or maximum age of the cookie.</span></span>  <span data-ttu-id="50f1d-131">[永続的な [Cookie] に移動します][MDNHTTPCookiesPermanent]。</span><span class="sxs-lookup"><span data-stu-id="50f1d-131">Navigate to [Permanent cookies][MDNHTTPCookiesPermanent].</span></span>  <span data-ttu-id="50f1d-132">セッション [Cookie の場合、][MDNHTTPCookiesSession] この値は常にです `Session` 。</span><span class="sxs-lookup"><span data-stu-id="50f1d-132">For [session cookies][MDNHTTPCookiesSession] this value is always `Session`.</span></span>  
*   <span data-ttu-id="50f1d-133">**サイズ**.</span><span class="sxs-lookup"><span data-stu-id="50f1d-133">**Size**.</span></span>  <span data-ttu-id="50f1d-134">Cookie のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="50f1d-134">The size, in bytes, of the cookie.</span></span>  
*   <span data-ttu-id="50f1d-135">**HTTP**.</span><span class="sxs-lookup"><span data-stu-id="50f1d-135">**HTTP**.</span></span>  <span data-ttu-id="50f1d-136">true の場合、このフィールドは Cookie を HTTP でのみ使用し、JavaScript の変更は許可されません。</span><span class="sxs-lookup"><span data-stu-id="50f1d-136">If true, this field indicates that the cookie should only be used over HTTP and JavaScript modification is not allowed.</span></span>  <span data-ttu-id="50f1d-137">[HttpOnly Cookie に移動します][MDNHTTPCookiesSecure]。</span><span class="sxs-lookup"><span data-stu-id="50f1d-137">Navigate to [HttpOnly cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="50f1d-138">**セキュリティで保護されています**。</span><span class="sxs-lookup"><span data-stu-id="50f1d-138">**Secure**.</span></span>  <span data-ttu-id="50f1d-139">true の場合、このフィールドは、セキュリティで保護された HTTPS 接続経由でのみ Cookie をサーバーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50f1d-139">If true, this field indicates that the cookie must be sent to the server only over a secure, HTTPS connection.</span></span>  <span data-ttu-id="50f1d-140">[セキュリティで保護 [された Cookie] に移動します][MDNHTTPCookiesSecure]。</span><span class="sxs-lookup"><span data-stu-id="50f1d-140">Navigate to [Secure cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="50f1d-141">**SameSite**.</span><span class="sxs-lookup"><span data-stu-id="50f1d-141">**SameSite**.</span></span>  <span data-ttu-id="50f1d-142">Cookie が `strict` 実験的 `lax` な Samesite 属性を使用している場合 [またはを含][MDNHTTPCookiesSamesite] む。</span><span class="sxs-lookup"><span data-stu-id="50f1d-142">Contains `strict` or `lax` if the cookie is using the experimental [Samesite][MDNHTTPCookiesSamesite] attribute.</span></span>  
*   <span data-ttu-id="50f1d-143">**優先度**。</span><span class="sxs-lookup"><span data-stu-id="50f1d-143">**Priority**.</span></span>  <span data-ttu-id="50f1d-144">\(default\)、または Cookie が非推奨の Cookie Priority 属性を使用 `low` `medium` `high` [している場合を含][ChromiumIssue232693] む。</span><span class="sxs-lookup"><span data-stu-id="50f1d-144">Contains `low`, `medium` \(default\), or `high` if the cookie is using the deprecated [cookie Priority][ChromiumIssue232693] attribute.</span></span>

## <a name="filter-cookies"></a><span data-ttu-id="50f1d-145">フィルター Cookie</span><span class="sxs-lookup"><span data-stu-id="50f1d-145">Filter cookies</span></span>  

<span data-ttu-id="50f1d-146">[フィルター]**テキスト ボックス**を使用して、名前または値で**Cookie をフィルター処理します**。</span><span class="sxs-lookup"><span data-stu-id="50f1d-146">Use the **Filter** text box to filter cookies by **Name** or **Value**.</span></span>  <span data-ttu-id="50f1d-147">他のフィールドによるフィルター処理はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="50f1d-147">Filtering by other fields is not supported.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-filter-id.msft.png" alt-text="テキスト ID を含む Cookie をフィルター処理する" lightbox="../media/storage-application-storage-cookies-filter-id.msft.png":::
   <span data-ttu-id="50f1d-149">図 3: テキストを含む Cookie をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="50f1d-149">Figure 3:  Filtering out any cookies that do not contain the text</span></span> `ID`  
:::image-end:::  

## <a name="edit-a-cookie"></a><span data-ttu-id="50f1d-150">Cookie を編集する</span><span class="sxs-lookup"><span data-stu-id="50f1d-150">Edit a cookie</span></span>  

<span data-ttu-id="50f1d-151">[**名前]、[値]、[ドメイン]、[パス**]、および **[有効期限] / [最大年齢**] フィールドは編集可能です。</span><span class="sxs-lookup"><span data-stu-id="50f1d-151">The **Name**, **Value**, **Domain**, **Path**, and **Expires / Max-Age** fields are editable.</span></span>  
<span data-ttu-id="50f1d-152">フィールドをダブルクリックして編集します。</span><span class="sxs-lookup"><span data-stu-id="50f1d-152">Double-click a field to edit it.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-rename.msft.png" alt-text="Cookie の名前を DEVTOOLS に設定する!" lightbox="../media/storage-application-storage-cookies-rename.msft.png":::
   <span data-ttu-id="50f1d-154">図 4: Cookie の名前をに設定する</span><span class="sxs-lookup"><span data-stu-id="50f1d-154">Figure 4:  Setting the name of a cookie to</span></span> `DEVTOOLS!`  
:::image-end:::  

## <a name="delete-cookies"></a><span data-ttu-id="50f1d-155">Cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="50f1d-155">Delete cookies</span></span>  

<span data-ttu-id="50f1d-156">Cookie を選択し **、[Delete Selected** \( Delete Selected \) ] を選択して、特定の Cookie ![ ](../media/delete-icon.msft.png) を削除します。</span><span class="sxs-lookup"><span data-stu-id="50f1d-156">Choose a cookie and choose **Delete Selected** \(![Delete Selected](../media/delete-icon.msft.png)\) to delete the specific cookie.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-delete-selected.msft.png" alt-text="特定の Cookie の削除" lightbox="../media/storage-application-storage-cookies-delete-selected.msft.png":::
   <span data-ttu-id="50f1d-158">図 5: 特定の Cookie の削除</span><span class="sxs-lookup"><span data-stu-id="50f1d-158">Figure 5:  Deleting a specific cookie</span></span>  
:::image-end:::  

<span data-ttu-id="50f1d-159">[ **すべてクリア]** \( ![ Clear All ](../media/clear-icon.msft.png) \) を選択して、すべての Cookie を削除します。</span><span class="sxs-lookup"><span data-stu-id="50f1d-159">Choose **Clear All** \(![Clear All](../media/clear-icon.msft.png)\) to delete all cookies.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-clear-all.msft.png" alt-text="すべての Cookie のクリア" lightbox="../media/storage-application-storage-cookies-clear-all.msft.png":::
   <span data-ttu-id="50f1d-161">図 6: すべての Cookie をクリアする</span><span class="sxs-lookup"><span data-stu-id="50f1d-161">Figure 6:  Clearing all cookies</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="50f1d-162">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="50f1d-162">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (クロム) 開発者ツール"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  

[ChromiumIssue232693]: https://bugs.chromium.org/p/chromium/issues/detail?id=232693 "クロムの問題 232693: Cookie の優先度フィールドの実装|クロム バグ"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP cookie |MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP Cookie - 永続的な cookie |MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP Cookie - SameSite cookie |MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookie - Cookie の範囲と|MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP Cookie - セキュリティで保護された HttpOnly |MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP Cookie - セッション cookie |MDN"  

> [!NOTE]
> <span data-ttu-id="50f1d-172">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="50f1d-172">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="50f1d-173">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cookies) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="50f1d-173">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cookies) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="50f1d-175">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="50f1d-175">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
