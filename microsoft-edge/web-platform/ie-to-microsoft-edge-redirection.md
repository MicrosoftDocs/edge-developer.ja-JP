---
description: Internet Explorer から Microsoft Edge にユーザーを移動させる
title: Internet Explorer から Microsoft Edge にユーザーを移動させる
author: MSEdgeTeam
ms.date: 11/13/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge, 互換性, Web プラットフォーム, internet explorer
ms.openlocfilehash: c2106955ed79bd28dc1f847dee220944bb014689
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461137"
---
# <a name="moving-users-to-microsoft-edge-from-internet-explorer"></a><span data-ttu-id="c4f56-104">Internet Explorer から Microsoft Edge にユーザーを移動させる</span><span class="sxs-lookup"><span data-stu-id="c4f56-104">Moving users to Microsoft Edge from Internet Explorer</span></span>  

<span data-ttu-id="c4f56-105">多くの最新の Web サイトには、Internet Explorer \(IE\) と互換性のないデザインがあります。</span><span class="sxs-lookup"><span data-stu-id="c4f56-105">Many modern websites have designs that are incompatible with Internet Explorer \(IE\).</span></span>  <span data-ttu-id="c4f56-106">IE ユーザーが互換性のないパブリック Web サイトにアクセスすると、メッセージを受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4f56-106">When an IE user visits an incompatible public website, the user may get a message.</span></span>  <span data-ttu-id="c4f56-107">このメッセージには、Web サイトがブラウザーと互換性がないという旨が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-107">The message states that the website is incompatible with the browser.</span></span>  <span data-ttu-id="c4f56-108">メッセージが表示された後、ユーザーは最新のブラウザーに手動で切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4f56-108">After the message is displayed, the user is expected to manually switch to a modern browser.</span></span>  <span data-ttu-id="c4f56-109">中断を最小限に抑えるために、バージョン 84 から、Microsoft Edge では、ユーザーを自動的にリダイレクトする新しい機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c4f56-109">To minimize disruptions, starting with version 84, Microsoft Edge supports a new capability that automatically redirects users.</span></span>  <span data-ttu-id="c4f56-110">IE ユーザーが IE と互換性のない Web サイトに移動すると、Windows によってユーザーが自動的に Microsoft Edge にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-110">When an IE user navigates to a website that is incompatible with IE, Windows automatically redirects the user to Microsoft Edge.</span></span>  <span data-ttu-id="c4f56-111">一覧の Web サイトを確認するには、[[Microsoft Edge　一覧が必要][MicrosoftEdgeNeededgeV1]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-111">To review the websites on the list, navigate to [Need Microsoft Edge list][MicrosoftEdgeNeededgeV1].</span></span>

<span data-ttu-id="c4f56-112">この記事では、次の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-112">This article describes the following concepts.</span></span>  

*   <span data-ttu-id="c4f56-113">Web サイトがリストに追加されている理由</span><span class="sxs-lookup"><span data-stu-id="c4f56-113">Why a website is added to the list</span></span>  
*   <span data-ttu-id="c4f56-114">リダイレクトのユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c4f56-114">The user experience for redirection</span></span>  
*   <span data-ttu-id="c4f56-115">リストへの更新を要求する</span><span class="sxs-lookup"><span data-stu-id="c4f56-115">Request an update to the list</span></span>  
    
## <a name="why-is-a-website-added-to-the-ie-compatibility-list"></a><span data-ttu-id="c4f56-116">IE 互換性リストに Web サイトが追加される理由</span><span class="sxs-lookup"><span data-stu-id="c4f56-116">Why is a website added to the IE compatibility list?</span></span>  

<span data-ttu-id="c4f56-117">IE 互換性リストは、次のアクションが発生した場合にのみ Web サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-117">The IE compatibility List only adds a website when the following actions occur.</span></span>  

*   <span data-ttu-id="c4f56-118">互換性上の理由から、ユーザーが別のブラウザーを使用する必要があるというメッセージを IE ユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-118">Shows an IE user a message suggesting the user should use a different browser for compatibility reasons.</span></span>  
*   <span data-ttu-id="c4f56-119">所有者が、IE 互換性リストに Web サイトを追加する要求を行います。</span><span class="sxs-lookup"><span data-stu-id="c4f56-119">Owner requests to add the website to the IE compatibility list.</span></span>  

## <a name="redirection-experience"></a><span data-ttu-id="c4f56-120">リダイレクト エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c4f56-120">Redirection experience</span></span>

<span data-ttu-id="c4f56-121">Microsoft Edge へのリダイレクト時に、ユーザーは次のスクリーンショットに示すような 1 回限りのダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-121">On redirection to Microsoft Edge, the user is shown the one-time dialog in the next screenshot.</span></span>  <span data-ttu-id="c4f56-122">このダイアログは、ユーザーに次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-122">The dialog provides the user with the following information.</span></span>  

*   <span data-ttu-id="c4f56-123">Web サイトがリダイレクトされる理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-123">It explains why the website is being redirected.</span></span>  
*   <span data-ttu-id="c4f56-124">閲覧データとユーザー設定を IE から Microsoft Edge にコピーすることに同意するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-124">It prompts the user for consent to copy browsing data and preferences from IE to Microsoft Edge.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c4f56-125">次の参照データがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-125">The following browsing data is imported.</span></span>  
      
      *   <span data-ttu-id="c4f56-126">お気に入り</span><span class="sxs-lookup"><span data-stu-id="c4f56-126">Favorites</span></span>  
      *   <span data-ttu-id="c4f56-127">パスワード</span><span class="sxs-lookup"><span data-stu-id="c4f56-127">Passwords</span></span>  
      *   <span data-ttu-id="c4f56-128">検索エンジン</span><span class="sxs-lookup"><span data-stu-id="c4f56-128">Search engines</span></span>  
      *   <span data-ttu-id="c4f56-129">タブを開く</span><span class="sxs-lookup"><span data-stu-id="c4f56-129">Open tabs</span></span>  
      *   <span data-ttu-id="c4f56-130">履歴</span><span class="sxs-lookup"><span data-stu-id="c4f56-130">History</span></span>  
      *   <span data-ttu-id="c4f56-131">設定</span><span class="sxs-lookup"><span data-stu-id="c4f56-131">Settings</span></span>  
      *   <span data-ttu-id="c4f56-132">Cookie</span><span class="sxs-lookup"><span data-stu-id="c4f56-132">Cookies</span></span>  
      *   <span data-ttu-id="c4f56-133">ホーム ページ</span><span class="sxs-lookup"><span data-stu-id="c4f56-133">The Home Page</span></span>  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/neededge-dialog1.msft.png" alt-text="閲覧通知とデータと基本設定のインポートを求めるプロンプト" lightbox="../media/neededge-dialog1.msft.png":::
         <span data-ttu-id="c4f56-135">閲覧通知とデータと基本設定のインポートを求めるプロンプト</span><span class="sxs-lookup"><span data-stu-id="c4f56-135">Browsing notification and prompt to import data and preferences</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="c4f56-136">ユーザーが **[常に閲覧データとユーザー設定を Internet Explorer から引き継ぐ**] のチェック ボックスをオンにして同意しない場合、ユーザーは **[閲覧の続行]** を選択して閲覧セッションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-136">If the user does not consent by choosing the **Always bring over my browsing data and preferences from Internet Explorer** checkbox, the user may choose **Continue browsing** to continue the browsing session.</span></span>  

<span data-ttu-id="c4f56-137">最後に、リダイレクトごとにアドレス バーの下に Web サイトの非互換性バナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-137">Finally, a website incompatibility banner is displayed under the address bar for each redirection.</span></span>  <span data-ttu-id="c4f56-138">次の図に、Web サイトの非互換性バナーの例を示します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-138">An example of a website incompatibility banner is displayed in following figure.</span></span>

:::image type="complex" source="../media/neededge-banner.msft.png" alt-text="最新のサイトに関する通知と、既定のブラウザーを Microsoft Edge に設定するか、Microsoft Edge を探索するかを促すプロンプト" lightbox="../media/neededge-banner.msft.png":::
   <span data-ttu-id="c4f56-140">最新のサイトに関する通知と、既定のブラウザーを Microsoft Edge に設定するか、Microsoft Edge を探索するかを促すプロンプト</span><span class="sxs-lookup"><span data-stu-id="c4f56-140">Notification about modern sites and prompt to set Microsoft Edge as default browser or explore Microsoft Edge</span></span>  
:::image-end:::

<span data-ttu-id="c4f56-141">Web サイトの非互換性バナーは、ユーザーに次の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-141">The website incompatibility banner provides the following details to the user.</span></span>  

*   <span data-ttu-id="c4f56-142">ユーザーに Microsoft Edge に切り替えることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-142">Recommends that the user to switch to Microsoft Edge.</span></span>  
*   <span data-ttu-id="c4f56-143">既定のブラウザー Microsoft Edge を設定するよう提案します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-143">Offers to set Microsoft Edge as the default browser.</span></span>  
*   <span data-ttu-id="c4f56-144">Microsoft Edge を探索するオプションをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-144">Gives the user the option to explore Microsoft Edge.</span></span>    
    
<span data-ttu-id="c4f56-145">Web サイトが Internet Explorer から Microsoft Edge にリダイレクトされると、次のいずれかのアクションが発生します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-145">When a website is redirected from Internet Explorer to Microsoft Edge, one of the following actions occurs.</span></span>

*   <span data-ttu-id="c4f56-146">アクティブな IE タブに以前のコンテンツがない場合は、閉じます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-146">If the active IE tab had no prior content, it is closed.</span></span>  
*   <span data-ttu-id="c4f56-147">アクティブな IE タブに以前のコンテンツがある場合は、[Web サイトが Microsoft Edge にリダイレクトされた理由を説明する Microsoft サポート ページ][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4f56-147">If the active IE tab had prior content, it navigates to the [Microsoft support page that explains why the website was redirected to Microsoft Edge][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer].</span></span>  

> [!NOTE]
> <span data-ttu-id="c4f56-148">リダイレクト後、ユーザーは IE 互換性リストに含されていない Web サイトに引き続き IE を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-148">After a redirection, users may continue to use IE for websites that are not on the IE compatibility list.</span></span>  

## <a name="request-an-update-to-the-ie-compatibility-list"></a><span data-ttu-id="c4f56-149">IE 互換性リストへの更新を要求する</span><span class="sxs-lookup"><span data-stu-id="c4f56-149">Request an update to the IE compatibility list</span></span>  

<span data-ttu-id="c4f56-150">IE 互換性リストは、[microsoft.com][MicrosoftOfficialHome] にある XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c4f56-150">The IE compatibility list is an XML file on [microsoft.com][MicrosoftOfficialHome].</span></span>  <span data-ttu-id="c4f56-151">このリストは、Web サイトを追加または削除するユーザーおよび Web サイト開発者の要求に応じて定期的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-151">The list is regularly updated in response to user and website developer requests to have websites added or removed.</span></span>  <span data-ttu-id="c4f56-152">リストの更新プログラムは、ユーザーのコンピューターに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-152">Updates to the list are automatically downloaded to user machines.</span></span>  

<span data-ttu-id="c4f56-153">IE 互換性リストに追加または削除される Web　サイトについては、次の情報を [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] にメールしてください。</span><span class="sxs-lookup"><span data-stu-id="c4f56-153">Email the following information to [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] for your website to be added or removed from the IE compatibility list.</span></span>    

*   <span data-ttu-id="c4f56-154">所有者名</span><span class="sxs-lookup"><span data-stu-id="c4f56-154">Owner name</span></span>  
*   <span data-ttu-id="c4f56-155">企業タイトル</span><span class="sxs-lookup"><span data-stu-id="c4f56-155">Corporate title</span></span>  
*   <span data-ttu-id="c4f56-156">メール アドレス</span><span class="sxs-lookup"><span data-stu-id="c4f56-156">Email address</span></span>  
*   <span data-ttu-id="c4f56-157">会社名</span><span class="sxs-lookup"><span data-stu-id="c4f56-157">Company name</span></span>  
*   <span data-ttu-id="c4f56-158">住所</span><span class="sxs-lookup"><span data-stu-id="c4f56-158">Street address</span></span>  
*   <span data-ttu-id="c4f56-159">Web サイトのアドレス</span><span class="sxs-lookup"><span data-stu-id="c4f56-159">Website address</span></span>  
    
<span data-ttu-id="c4f56-160">IE 互換性リストは 1 週間以内に更新されます。</span><span class="sxs-lookup"><span data-stu-id="c4f56-160">The IE compatibility list is updated within a week.</span></span>

> [!NOTE]
> <span data-ttu-id="c4f56-161">IE の互換性リストは、パブリック サイトでのみ動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c4f56-161">The IE compatibility list is designed to work with public sites only.</span></span>  

<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "メールを ietoedge@microsoft.com に送信する"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft Official Home"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "リスト v1 Microsoft Edge xml ファイルが必要 | Microsoft Edge"  

[MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]: https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554 "アクセスしようとしていた Web サイトは、ユーザーがアクセス Internet Explorer で動作しません | Microsoft Office サポート"  
