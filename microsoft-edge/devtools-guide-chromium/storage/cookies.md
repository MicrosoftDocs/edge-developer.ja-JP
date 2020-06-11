---
title: Microsoft Edge DevTools を使った Cookie の表示、編集、削除
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4bfd99a36a6a3f8fdf8dbd7787bd54cde87d79da
ms.sourcegitcommit: f010f43604bd4363af6827f79dbc071b9afcb667
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "10708948"
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

# <span data-ttu-id="7121a-103">Microsoft Edge DevTools を使った cookie の表示、編集、削除</span><span class="sxs-lookup"><span data-stu-id="7121a-103">View, edit, and delete cookies with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="7121a-104">[HTTP cookie][MDNHTTPCookies]は主に、ユーザーセッションを管理するために使用され、ユーザーの個人設定の設定を保存し、ユーザーの動作を追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7121a-104">[HTTP Cookies][MDNHTTPCookies] are mainly used to manage user sessions, store user personalization preferences, and track user behavior.</span></span>  <span data-ttu-id="7121a-105">Cookie は、web 上で表示される、"このページに cookie が使用されています" という承諾フォームもあります。</span><span class="sxs-lookup"><span data-stu-id="7121a-105">Cookies are also the cause of all of the annoying "this page uses cookies" consent forms that you see across the web.</span></span>  <span data-ttu-id="7121a-106">次のガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って、ページの HTTP cookie の表示、編集、削除を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7121a-106">The following guide teaches you how to view, edit, and delete the HTTP cookies for a page with [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="7121a-107">[Cookies] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="7121a-107">Open the Cookies pane</span></span>  

1.  <span data-ttu-id="7121a-108">[DevTools を開き][DevToolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="7121a-108">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="7121a-109">[**アプリケーション**] タブを選択して、[**アプリケーション**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7121a-109">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="7121a-110">**マニフェスト**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="7121a-110">The **Manifest** pane should open.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="7121a-112">図 1: [マニフェスト] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7121a-112">Figure 1:  The Manifest pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="7121a-113">[**記憶域**] で [ **cookie**] を展開し、[起点] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7121a-113">Under **Storage** expand **Cookies**, then select an origin.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-cookies-selected.msft.png" alt-text="[Cookie] ウィンドウ" lightbox="../media/storage-application-storage-cookies-selected.msft.png":::
       <span data-ttu-id="7121a-115">図 2: [Cookie] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7121a-115">Figure 2:  The Cookies pane</span></span>  
    :::image-end:::  

## <span data-ttu-id="7121a-116">フィールド</span><span class="sxs-lookup"><span data-stu-id="7121a-116">Fields</span></span>  

<span data-ttu-id="7121a-117">**Cookies**テーブルには、次のフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7121a-117">The **Cookies** table contains the following fields.</span></span>  

*   <span data-ttu-id="7121a-118">**[名前]**。</span><span class="sxs-lookup"><span data-stu-id="7121a-118">**Name**.</span></span>  <span data-ttu-id="7121a-119">Cookie の名前。</span><span class="sxs-lookup"><span data-stu-id="7121a-119">The name of the cookie.</span></span>  
*   <span data-ttu-id="7121a-120">**値**。</span><span class="sxs-lookup"><span data-stu-id="7121a-120">**Value**.</span></span>  <span data-ttu-id="7121a-121">Cookie の値。</span><span class="sxs-lookup"><span data-stu-id="7121a-121">The value of the cookie.</span></span>  
*   <span data-ttu-id="7121a-122">**ドメイン**。</span><span class="sxs-lookup"><span data-stu-id="7121a-122">**Domain**.</span></span>  <span data-ttu-id="7121a-123">Cookie の受信を許可されているホスト。</span><span class="sxs-lookup"><span data-stu-id="7121a-123">The hosts that are allowed to receive the cookie.</span></span>  <span data-ttu-id="7121a-124">「 [Cookie のスコープ][MDNHTTPCookiesScope]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7121a-124">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="7121a-125">**Path**。</span><span class="sxs-lookup"><span data-stu-id="7121a-125">**Path**.</span></span>  <span data-ttu-id="7121a-126">ヘッダーを送信するために要求された URL 内に存在する必要がある URL `Cookie` 。</span><span class="sxs-lookup"><span data-stu-id="7121a-126">The URL that must exist in the requested URL in order to send the `Cookie` header.</span></span>  <span data-ttu-id="7121a-127">「 [Cookie のスコープ][MDNHTTPCookiesScope]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7121a-127">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="7121a-128">**有効期限/最長年齢**。</span><span class="sxs-lookup"><span data-stu-id="7121a-128">**Expires / Max-Age**.</span></span>  <span data-ttu-id="7121a-129">Cookie の有効期限日または最大年齢。</span><span class="sxs-lookup"><span data-stu-id="7121a-129">The expiration date or maximum age of the cookie.</span></span>  <span data-ttu-id="7121a-130">「[永続的な cookie][MDNHTTPCookiesPermanent]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7121a-130">See [Permanent cookies][MDNHTTPCookiesPermanent].</span></span>  <span data-ttu-id="7121a-131">[セッション cookie][MDNHTTPCookiesSession]の場合、この値は常に使用され `Session` ます。</span><span class="sxs-lookup"><span data-stu-id="7121a-131">For [session cookies][MDNHTTPCookiesSession] this value is always `Session`.</span></span>  
*   <span data-ttu-id="7121a-132">**サイズ**。</span><span class="sxs-lookup"><span data-stu-id="7121a-132">**Size**.</span></span>  <span data-ttu-id="7121a-133">Cookie のサイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="7121a-133">The size, in bytes, of the cookie.</span></span>  
*   <span data-ttu-id="7121a-134">**HTTP**。</span><span class="sxs-lookup"><span data-stu-id="7121a-134">**HTTP**.</span></span>  <span data-ttu-id="7121a-135">True の場合、このフィールドは、cookie が HTTP 経由でのみ使用され、JavaScript の変更が許可されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="7121a-135">If true, this field indicates that the cookie should only be used over HTTP and JavaScript modification is not allowed.</span></span>  <span data-ttu-id="7121a-136">「 [Httponly cookie][MDNHTTPCookiesSecure]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7121a-136">See [HttpOnly cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="7121a-137">**セキュリティ保護さ**れます。</span><span class="sxs-lookup"><span data-stu-id="7121a-137">**Secure**.</span></span>  <span data-ttu-id="7121a-138">True の場合、このフィールドは、cookie がセキュリティで保護された HTTPS 接続を介してのみサーバーに送信される必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="7121a-138">If true, this field indicates that the cookie must be sent to the server only over a secure, HTTPS connection.</span></span>  <span data-ttu-id="7121a-139">「[安全な cookie][MDNHTTPCookiesSecure]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7121a-139">See [Secure cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="7121a-140">**SameSite**。</span><span class="sxs-lookup"><span data-stu-id="7121a-140">**SameSite**.</span></span>  <span data-ttu-id="7121a-141">`strict` `lax` Cookie が実験的な[Samesite][MDNHTTPCookiesSamesite]属性を使用しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7121a-141">Contains `strict` or `lax` if the cookie is using the experimental [Samesite][MDNHTTPCookiesSamesite] attribute.</span></span>  
*   <span data-ttu-id="7121a-142">**優先度**。</span><span class="sxs-lookup"><span data-stu-id="7121a-142">**Priority**.</span></span>  <span data-ttu-id="7121a-143">含ま `low` れる `medium` 場合は、\ (既定値 \)、または `high` cookie が "減価償却[cookie の優先順位][ChromiumIssue232693]" 属性を使っているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7121a-143">Contains `low`, `medium` \(default\), or `high` if the cookie is using the depreciated [cookie Priority][ChromiumIssue232693] attribute.</span></span>

## <span data-ttu-id="7121a-144">Cookie をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="7121a-144">Filter cookies</span></span>  

<span data-ttu-id="7121a-145">**名前**または**値**で cookie をフィルター処理するには、[**フィルター** ] テキストボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7121a-145">Use the **Filter** text box to filter cookies by **Name** or **Value**.</span></span>  <span data-ttu-id="7121a-146">他のフィールドによるフィルター処理はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7121a-146">Filtering by other fields is not supported.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-filter-id.msft.png" alt-text="テキスト ID が含まれていないすべての cookie をフィルターで除外する" lightbox="../media/storage-application-storage-cookies-filter-id.msft.png":::
   <span data-ttu-id="7121a-148">図 3: テキストが含まれていないすべての cookie をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="7121a-148">Figure 3:  Filtering out any cookies that do not contain the text</span></span> `ID`  
:::image-end:::  

## <span data-ttu-id="7121a-149">Cookie を編集する</span><span class="sxs-lookup"><span data-stu-id="7121a-149">Edit a cookie</span></span>  

<span data-ttu-id="7121a-150">[**名前**]、[**値**]、[**ドメイン**]、[**パス**]、[**有効期限**]、[最大有効期限] の各フィールドは編集できます。</span><span class="sxs-lookup"><span data-stu-id="7121a-150">The **Name**, **Value**, **Domain**, **Path**, and **Expires / Max-Age** fields are editable.</span></span>  
<span data-ttu-id="7121a-151">フィールドをダブルクリックして編集します。</span><span class="sxs-lookup"><span data-stu-id="7121a-151">Double-click a field to edit it.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-rename.msft.png" alt-text="DEVTOOLS に cookie の名前を設定します。" lightbox="../media/storage-application-storage-cookies-rename.msft.png":::
   <span data-ttu-id="7121a-153">図 4: クッキーの名前を設定する</span><span class="sxs-lookup"><span data-stu-id="7121a-153">Figure 4:  Setting the name of a cookie to</span></span> `DEVTOOLS!`  
:::image-end:::  

## <span data-ttu-id="7121a-154">Cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="7121a-154">Delete cookies</span></span>  

<span data-ttu-id="7121a-155">Cookie を選択して、[選択した削除の**削除] を**選択し ![ ][ImageDeleteIcon] 、特定の cookie を削除します。</span><span class="sxs-lookup"><span data-stu-id="7121a-155">Select a cookie and select **Delete Selected** ![Delete Selected][ImageDeleteIcon]  to delete the specific cookie.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-delete-selected.msft.png" alt-text="特定の cookie を削除する" lightbox="../media/storage-application-storage-cookies-delete-selected.msft.png":::
   <span data-ttu-id="7121a-157">図 5: 特定の cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="7121a-157">Figure 5:  Deleting a specific cookie</span></span>  
:::image-end:::  

<span data-ttu-id="7121a-158">すべて**Clear All**の ![ ][ImageClearIcon] cookie を削除するには、[すべてクリア] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7121a-158">Select **Clear All** ![Clear All][ImageClearIcon]  to delete all cookies.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-clear-all.msft.png" alt-text="すべての cookie をクリアする" lightbox="../media/storage-application-storage-cookies-clear-all.msft.png":::
   <span data-ttu-id="7121a-160">図 6: すべての cookie をクリアする</span><span class="sxs-lookup"><span data-stu-id="7121a-160">Figure 6:  Clearing all cookies</span></span>  
:::image-end:::  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  

[ChromiumIssue232693]: https://bugs.chromium.org/p/chromium/issues/detail?id=232693 "Chromium の問題 232693: Cookie の優先度フィールドの実装 |Chromium のバグ"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP クッキー |MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP クッキー-永続的な cookie |MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP クッキー-SameSite クッキー |MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookie-cookie のスコープ |MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP クッキー-セキュアおよび HttpOnly クッキー |MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP クッキー-セッションクッキー |MDN"  

> [!NOTE]
> <span data-ttu-id="7121a-170">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="7121a-170">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7121a-171">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cookies)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="7121a-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cookies) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="7121a-173">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="7121a-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
