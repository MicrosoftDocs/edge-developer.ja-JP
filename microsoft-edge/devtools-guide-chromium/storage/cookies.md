---
title: Microsoft Edge DevTools を使った Cookie の表示、編集、削除
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 084c4116cd4c9c5e70b2fe341257fa68ba2c8ae7
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612069"
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





# <span data-ttu-id="b4afb-103">Microsoft Edge DevTools を使った Cookie の表示、編集、削除</span><span class="sxs-lookup"><span data-stu-id="b4afb-103">View, Edit, And Delete Cookies With Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="b4afb-104">[HTTP cookie][MDNHTTPCookies]は主に、ユーザーセッションを管理するために使用され、ユーザーの個人設定の設定を保存し、ユーザーの動作を追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b4afb-104">[HTTP Cookies][MDNHTTPCookies] are mainly used to manage user sessions, store user personalization preferences, and track user behavior.</span></span>  <span data-ttu-id="b4afb-105">また、これらのページは、web 上で表示される cookie の承認フォームを使用していることもあります。</span><span class="sxs-lookup"><span data-stu-id="b4afb-105">They are also the cause of all of those annoying "this page uses cookies" consent forms that you see across the web.</span></span>  <span data-ttu-id="b4afb-106">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って、ページの HTTP cookie を表示、編集、削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4afb-106">This guide teaches you how to view, edit, and delete the HTTP cookies for a page with [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="b4afb-107">[Cookies] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="b4afb-107">Open the Cookies pane</span></span>   

1.  <span data-ttu-id="b4afb-108">[DevTools を開き][DevToolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="b4afb-108">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="b4afb-109">[**アプリケーション**] タブを選択して、[**アプリケーション**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b4afb-109">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="b4afb-110">**マニフェスト**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="b4afb-110">The **Manifest** pane should open.</span></span>  
    
    > ##### <span data-ttu-id="b4afb-111">図 1</span><span class="sxs-lookup"><span data-stu-id="b4afb-111">Figure 1</span></span>  
    > <span data-ttu-id="b4afb-112">マニフェストウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b4afb-112">The Manifest pane</span></span>  
    > ![マニフェストウィンドウ][ImageManifest]  

1.  <span data-ttu-id="b4afb-114">[**記憶域**] で [ **cookie**] を展開し、[起点] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4afb-114">Under **Storage** expand **Cookies**, then select an origin.</span></span>  
    
    > ##### <span data-ttu-id="b4afb-115">図 2</span><span class="sxs-lookup"><span data-stu-id="b4afb-115">Figure 2</span></span>  
    > <span data-ttu-id="b4afb-116">[Cookie] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b4afb-116">The Cookies pane</span></span>  
    > ![[Cookie] ウィンドウ][ImageCookies]  

## <span data-ttu-id="b4afb-118">フィールド</span><span class="sxs-lookup"><span data-stu-id="b4afb-118">Fields</span></span>   

<span data-ttu-id="b4afb-119">**Cookies**テーブルには、次のフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4afb-119">The **Cookies** table contains the following fields:</span></span>  

*   <span data-ttu-id="b4afb-120">**[名前]**。</span><span class="sxs-lookup"><span data-stu-id="b4afb-120">**Name**.</span></span>  <span data-ttu-id="b4afb-121">Cookie の名前。</span><span class="sxs-lookup"><span data-stu-id="b4afb-121">The name of the cookie.</span></span>  
*   <span data-ttu-id="b4afb-122">**値**。</span><span class="sxs-lookup"><span data-stu-id="b4afb-122">**Value**.</span></span>  <span data-ttu-id="b4afb-123">Cookie の値。</span><span class="sxs-lookup"><span data-stu-id="b4afb-123">The value of the cookie.</span></span>  
*   <span data-ttu-id="b4afb-124">**ドメイン**。</span><span class="sxs-lookup"><span data-stu-id="b4afb-124">**Domain**.</span></span>  <span data-ttu-id="b4afb-125">Cookie の受信を許可されているホスト。</span><span class="sxs-lookup"><span data-stu-id="b4afb-125">The hosts that are allowed to receive the cookie.</span></span>  <span data-ttu-id="b4afb-126">「 [Cookie のスコープ][MDNHTTPCookiesScope]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b4afb-126">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="b4afb-127">**Path**。</span><span class="sxs-lookup"><span data-stu-id="b4afb-127">**Path**.</span></span>  <span data-ttu-id="b4afb-128">ヘッダーを送信するために要求された URL 内に存在する必要がある URL `Cookie` 。</span><span class="sxs-lookup"><span data-stu-id="b4afb-128">The URL that must exist in the requested URL in order to send the `Cookie` header.</span></span>  <span data-ttu-id="b4afb-129">「 [Cookie のスコープ][MDNHTTPCookiesScope]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b4afb-129">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="b4afb-130">**有効期限/最長年齢**。</span><span class="sxs-lookup"><span data-stu-id="b4afb-130">**Expires / Max-Age**.</span></span>  <span data-ttu-id="b4afb-131">Cookie の有効期限日または最大年齢。</span><span class="sxs-lookup"><span data-stu-id="b4afb-131">The expiration date or maximum age of the cookie.</span></span>  <span data-ttu-id="b4afb-132">「[永続的な cookie][MDNHTTPCookiesPermanent]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4afb-132">See [Permanent cookies][MDNHTTPCookiesPermanent].</span></span>  <span data-ttu-id="b4afb-133">[セッション cookie][MDNHTTPCookiesSession]の場合、この値は常に使用され `Session` ます。</span><span class="sxs-lookup"><span data-stu-id="b4afb-133">For [session cookies][MDNHTTPCookiesSession] this value is always `Session`.</span></span>  
*   <span data-ttu-id="b4afb-134">**サイズ**。</span><span class="sxs-lookup"><span data-stu-id="b4afb-134">**Size**.</span></span>  <span data-ttu-id="b4afb-135">Cookie のサイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="b4afb-135">The size, in bytes, of the cookie.</span></span>  
*   <span data-ttu-id="b4afb-136">**HTTP**。</span><span class="sxs-lookup"><span data-stu-id="b4afb-136">**HTTP**.</span></span>  <span data-ttu-id="b4afb-137">True の場合、このフィールドは、cookie が HTTP 経由でのみ使用され、JavaScript の変更が許可されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b4afb-137">If true, this field indicates that the cookie should only be used over HTTP and JavaScript modification is not allowed.</span></span>  <span data-ttu-id="b4afb-138">「 [Httponly cookie][MDNHTTPCookiesSecure]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4afb-138">See [HttpOnly cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="b4afb-139">**セキュリティ保護さ**れます。</span><span class="sxs-lookup"><span data-stu-id="b4afb-139">**Secure**.</span></span>  <span data-ttu-id="b4afb-140">True の場合、このフィールドは、cookie がセキュリティで保護された HTTPS 接続を介してのみサーバーに送信される必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="b4afb-140">If true, this field indicates that the cookie must be sent to the server only over a secure, HTTPS connection.</span></span>  <span data-ttu-id="b4afb-141">「[安全な cookie][MDNHTTPCookiesSecure]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b4afb-141">See [Secure cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="b4afb-142">**SameSite**。</span><span class="sxs-lookup"><span data-stu-id="b4afb-142">**SameSite**.</span></span>  <span data-ttu-id="b4afb-143">`strict` `lax` Cookie が実験的な[Samesite][MDNHTTPCookiesSamesite]属性を使用しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b4afb-143">Contains `strict` or `lax` if the cookie is using the experimental [Samesite][MDNHTTPCookiesSamesite] attribute.</span></span>  

## <span data-ttu-id="b4afb-144">Cookie をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="b4afb-144">Filter cookies</span></span>   

<span data-ttu-id="b4afb-145">**名前**または**値**で cookie をフィルター処理するには、[**フィルター** ] テキストボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4afb-145">Use the **Filter** text box to filter cookies by **Name** or **Value**.</span></span>  <span data-ttu-id="b4afb-146">他のフィールドによるフィルター処理はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b4afb-146">Filtering by other fields is not supported.</span></span>  

> ##### <span data-ttu-id="b4afb-147">図 3</span><span class="sxs-lookup"><span data-stu-id="b4afb-147">Figure 3</span></span>  
> <span data-ttu-id="b4afb-148">テキストが含まれていないすべての cookie をフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="b4afb-148">Filtering out any cookies that do not contain the text</span></span> `ID`  
> ![テキスト ID が含まれていないすべての cookie をフィルターで除外する][ImageCookiesFilter]  

## <span data-ttu-id="b4afb-150">Cookie を編集する</span><span class="sxs-lookup"><span data-stu-id="b4afb-150">Edit a cookie</span></span>   

<span data-ttu-id="b4afb-151">[**名前**]、[**値**]、[**ドメイン**]、[**パス**]、[**有効期限**]、[最大有効期限] の各フィールドは編集できます。</span><span class="sxs-lookup"><span data-stu-id="b4afb-151">The **Name**, **Value**, **Domain**, **Path**, and **Expires / Max-Age** fields are editable.</span></span>  
<span data-ttu-id="b4afb-152">フィールドをダブルクリックして編集します。</span><span class="sxs-lookup"><span data-stu-id="b4afb-152">Double-click a field to edit it.</span></span>  

> ##### <span data-ttu-id="b4afb-153">図 4</span><span class="sxs-lookup"><span data-stu-id="b4afb-153">Figure 4</span></span>  
> <span data-ttu-id="b4afb-154">クッキーの名前の設定</span><span class="sxs-lookup"><span data-stu-id="b4afb-154">Setting the name of a cookie to</span></span> `DEVTOOLS!`  
> ![DEVTOOLS に cookie の名前を設定します。][ImageEditCookie]  

## <span data-ttu-id="b4afb-156">Cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="b4afb-156">Delete cookies</span></span>   

<span data-ttu-id="b4afb-157">Cookie を選択し、[**選択し**た削除の削除] をクリックし ![ て、 ][ImageDeleteIcon] 1 つの cookie を削除します。</span><span class="sxs-lookup"><span data-stu-id="b4afb-157">Select a cookie and then click **Delete Selected** ![Delete Selected][ImageDeleteIcon]  to delete that one cookie.</span></span>  

> ##### <span data-ttu-id="b4afb-158">図 5</span><span class="sxs-lookup"><span data-stu-id="b4afb-158">Figure 5</span></span>  
> <span data-ttu-id="b4afb-159">特定の cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="b4afb-159">Deleting a specific cookie</span></span>  
> ![特定の cookie を削除する][ImageDeleteCookie]  

<span data-ttu-id="b4afb-161">すべて**Clear All**の ![ ][ImageClearIcon] cookie を削除するには、[すべてクリア] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4afb-161">Select **Clear All** ![Clear All][ImageClearIcon]  to delete all cookies.</span></span>  

> ##### <span data-ttu-id="b4afb-162">図 6</span><span class="sxs-lookup"><span data-stu-id="b4afb-162">Figure 6</span></span>  
> <span data-ttu-id="b4afb-163">すべての cookie をクリアする</span><span class="sxs-lookup"><span data-stu-id="b4afb-163">Clearing all cookies</span></span>  
> ![すべての cookie をクリアする][ImageClearAllCookies]  

<!--    -->  

  

<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest-empty.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageCookies]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-selected.msft.png "図 2: [Cookie] ウィンドウ"  
[ImageCookiesFilter]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-filter-id.msft.png "図 3: テキスト ID が含まれていない cookie をフィルター処理する"  
[ImageEditCookie]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-rename.msft.png "図 4: DEVTOOLS に cookie の名前を設定する"  
[ImageDeleteCookie]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-delete-selected.msft.png "図 5: 特定の cookie を削除する"  
[ImageClearAllCookies]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-clear-all.msft.png "図 6: すべての cookie をクリアする"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP クッキー |MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP クッキー-永続的な cookie |MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP クッキー-SameSite クッキー |MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookie-cookie のスコープ |MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP クッキー-セキュアおよび HttpOnly クッキー |MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP クッキー-セッションクッキー |MDN"  

> [!NOTE]
> <span data-ttu-id="b4afb-179">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="b4afb-179">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b4afb-180">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cookies)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="b4afb-180">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cookies) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b4afb-182">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b4afb-182">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
