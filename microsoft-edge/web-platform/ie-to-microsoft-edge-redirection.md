---
description: Internet Explorer から Microsoft Edge にユーザーを移動する
title: Internet Explorer から Microsoft Edge にユーザーを移動する
author: MSEdgeTeam
ms.date: 11/13/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム、internet explorer
ms.openlocfilehash: 872bd5ec52f471e4958ef7354c046ec30f1ba72e
ms.sourcegitcommit: 62258ce0ef469948ca8af42141d02aa9719243f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168368"
---
# <span data-ttu-id="755b2-104">Internet Explorer から Microsoft Edge にユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="755b2-104">Moving users to Microsoft Edge from Internet Explorer</span></span>  

<span data-ttu-id="755b2-105">最新の web サイトの多くには、Internet Explorer \ (IE \) と互換性のないデザインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="755b2-105">Many modern websites have designs that are incompatible with Internet Explorer \(IE\).</span></span>  <span data-ttu-id="755b2-106">IE ユーザーが互換性のない一般向け web サイトにアクセスすると、ユーザーにメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="755b2-106">When an IE user visits an incompatible public website, the user may get a message.</span></span>  <span data-ttu-id="755b2-107">このメッセージは、web サイトがブラウザーに対応していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="755b2-107">The message states that the website is incompatible with the browser.</span></span>  <span data-ttu-id="755b2-108">メッセージが表示された後、ユーザーは、最新のブラウザーに手動で切り替えるように求められます。</span><span class="sxs-lookup"><span data-stu-id="755b2-108">After the message is displayed, the user is expected to manually switch to a modern browser.</span></span>  <span data-ttu-id="755b2-109">バージョン84以降では、中断を最小限にするために、Microsoft Edge はユーザーを自動的にリダイレクトする新機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="755b2-109">To minimize disruptions, starting with version 84, Microsoft Edge supports a new capability that automatically redirects users.</span></span>  <span data-ttu-id="755b2-110">Ie と互換性のない web サイトに IE ユーザーが移動すると、Windows はユーザーを Microsoft Edge に自動的にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="755b2-110">When an IE user navigates to a website that is incompatible with IE, Windows automatically redirects the user to Microsoft Edge.</span></span>  <span data-ttu-id="755b2-111">リスト上の web サイトを確認するには、「 [Microsoft Edge リストが必要][MicrosoftEdgeNeededgeV1]ですか?」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="755b2-111">To review the websites on the list, navigate to [Need Microsoft Edge list][MicrosoftEdgeNeededgeV1].</span></span>

<span data-ttu-id="755b2-112">この記事では、次の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="755b2-112">This article describes the following concepts.</span></span>  

*   <span data-ttu-id="755b2-113">Web サイトがリストに追加される理由</span><span class="sxs-lookup"><span data-stu-id="755b2-113">Why a website is added to the list</span></span>  
*   <span data-ttu-id="755b2-114">リダイレクトのユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="755b2-114">The user experience for redirection</span></span>  
*   <span data-ttu-id="755b2-115">リストの更新を要求する</span><span class="sxs-lookup"><span data-stu-id="755b2-115">Request an update to the list</span></span>  
    
## <span data-ttu-id="755b2-116">Web サイトが IE 互換性リストに追加されているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="755b2-116">Why is a website added to the IE compatibility list?</span></span>  

<span data-ttu-id="755b2-117">IE 互換性リストは、次の操作が発生した場合にのみ web サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="755b2-117">The IE compatibility List only adds a website when the following actions occur.</span></span>  

*   <span data-ttu-id="755b2-118">互換性の理由により、ユーザーが別のブラウザーを使用する必要があることを示すメッセージが IE ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="755b2-118">Shows an IE user a message suggesting the user should use a different browser for compatibility reasons.</span></span>  
*   <span data-ttu-id="755b2-119">所有者要求。 IE 互換性の一覧に web サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="755b2-119">Owner requests to add the website to the IE compatibility list.</span></span>  

## <span data-ttu-id="755b2-120">リダイレクト エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="755b2-120">Redirection experience</span></span>

<span data-ttu-id="755b2-121">Microsoft Edge へのリダイレクトでは、ユーザーは次のスクリーンショットに1回限りのダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="755b2-121">On redirection to Microsoft Edge, the user is shown the one-time dialog in the next screenshot.</span></span>  <span data-ttu-id="755b2-122">このダイアログボックスでは、次の情報をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="755b2-122">The dialog provides the user with the following information.</span></span>  

*   <span data-ttu-id="755b2-123">Web サイトがリダイレクトされる理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="755b2-123">It explains why the website is being redirected.</span></span>  
*   <span data-ttu-id="755b2-124">IE から Microsoft Edge への参照データと基本設定のコピーに同意することをユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="755b2-124">It prompts the user for consent to copy browsing data and preferences from IE to Microsoft Edge.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="755b2-125">次の参照データがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="755b2-125">The following browsing data is imported.</span></span>  
      
      *   <span data-ttu-id="755b2-126">お気に入り</span><span class="sxs-lookup"><span data-stu-id="755b2-126">Favorites</span></span>  
      *   <span data-ttu-id="755b2-127">パスワード</span><span class="sxs-lookup"><span data-stu-id="755b2-127">Passwords</span></span>  
      *   <span data-ttu-id="755b2-128">検索エンジン</span><span class="sxs-lookup"><span data-stu-id="755b2-128">Search engines</span></span>  
      *   <span data-ttu-id="755b2-129">タブを開く</span><span class="sxs-lookup"><span data-stu-id="755b2-129">Open tabs</span></span>  
      *   <span data-ttu-id="755b2-130">履歴</span><span class="sxs-lookup"><span data-stu-id="755b2-130">History</span></span>  
      *   <span data-ttu-id="755b2-131">設定</span><span class="sxs-lookup"><span data-stu-id="755b2-131">Settings</span></span>  
      *   <span data-ttu-id="755b2-132">Cookie</span><span class="sxs-lookup"><span data-stu-id="755b2-132">Cookies</span></span>  
      *   <span data-ttu-id="755b2-133">ホームページ</span><span class="sxs-lookup"><span data-stu-id="755b2-133">The Home Page</span></span>  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/neededge-dialog1.msft.png" alt-text="閲覧通知とデータと基本設定のインポートを求めるメッセージ" lightbox="../media/neededge-dialog1.msft.png":::
         <span data-ttu-id="755b2-135">閲覧通知とデータと基本設定のインポートを求めるメッセージ</span><span class="sxs-lookup"><span data-stu-id="755b2-135">Browsing notification and prompt to import data and preferences</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="755b2-136">ユーザーが **[Internet Explorer からデータと基本設定を常に**表示する] チェックボックスをオンにしても同意しない場合、ユーザーは [**参照の続行**] を選んで   閲覧セッションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="755b2-136">If the user does not consent by choosing the **Always bring over my browsing data and preferences from Internet Explorer** checkbox, the user may choose **Continue browsing** to continue the browsing session.</span></span>  

<span data-ttu-id="755b2-137">最後に、web サイトの非互換性のバナーは、各リダイレクションのアドレスバーの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="755b2-137">Finally, a website incompatibility banner is displayed under the address bar for each redirection.</span></span>  <span data-ttu-id="755b2-138">Web サイトの互換性のないバナーの例は、次の図のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="755b2-138">An example of a website incompatibility banner is displayed in following figure.</span></span>

:::image type="complex" source="../media/neededge-banner.msft.png" alt-text="モダンサイトに関する通知と Microsoft edge を既定のブラウザーとして設定するか、Microsoft Edge を調査するように求めるメッセージ" lightbox="../media/neededge-banner.msft.png":::
   <span data-ttu-id="755b2-140">モダンサイトに関する通知と Microsoft edge を既定のブラウザーとして設定するか、Microsoft Edge を調査するように求めるメッセージ</span><span class="sxs-lookup"><span data-stu-id="755b2-140">Notification about modern sites and prompt to set Microsoft Edge as default browser or explore Microsoft Edge</span></span>  
:::image-end:::

<span data-ttu-id="755b2-141">Web サイトの非互換性のバナーには、ユーザーに対して次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="755b2-141">The website incompatibility banner provides the following details to the user.</span></span>  

*   <span data-ttu-id="755b2-142">ユーザーによる Microsoft Edge への切り替えをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="755b2-142">Recommends that the user to switch to Microsoft Edge.</span></span>  
*   <span data-ttu-id="755b2-143">Microsoft Edge を既定のブラウザーとして設定することを提供します。</span><span class="sxs-lookup"><span data-stu-id="755b2-143">Offers to set Microsoft Edge as the default browser.</span></span>  
*   <span data-ttu-id="755b2-144">Microsoft Edge を調査するためのオプションをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="755b2-144">Gives the user the option to explore Microsoft Edge.</span></span>    
    
<span data-ttu-id="755b2-145">Web サイトが Internet Explorer から Microsoft Edge にリダイレクトされると、次のいずれかの操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="755b2-145">When a website is redirected from Internet Explorer to Microsoft Edge, one of the following actions occurs.</span></span>

*   <span data-ttu-id="755b2-146">アクティブな IE タブに以前の内容が含まれていない場合は、閉じられます。</span><span class="sxs-lookup"><span data-stu-id="755b2-146">If the active IE tab had no prior content, it is closed.</span></span>  
*   <span data-ttu-id="755b2-147">アクティブな IE タブに以前の内容が含まれている場合は、microsoft [Edge に web サイトがリダイレクトされた理由を説明する microsoft サポートページ][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]に移動します。</span><span class="sxs-lookup"><span data-stu-id="755b2-147">If the active IE tab had prior content, it navigates to the [Microsoft support page that explains why the website was redirected to Microsoft Edge][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer].</span></span>  

> [!NOTE]
> <span data-ttu-id="755b2-148">リダイレクト後、IE の互換性の一覧にない web サイトでは、ユーザーが引き続き IE を使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="755b2-148">After a redirection, users may continue to use IE for websites that are not on the IE compatibility list.</span></span>  

## <span data-ttu-id="755b2-149">IE 互換性の一覧の更新を要求する</span><span class="sxs-lookup"><span data-stu-id="755b2-149">Request an update to the IE compatibility list</span></span>  

<span data-ttu-id="755b2-150">IE 互換性リストは、 [microsoft.com][MicrosoftOfficialHome]上の XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="755b2-150">The IE compatibility list is an XML file on [microsoft.com][MicrosoftOfficialHome].</span></span>  <span data-ttu-id="755b2-151">リストは、ユーザーと web サイトの開発者からの要求に応じて定期的に更新され、web サイトを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="755b2-151">The list is regularly updated in response to user and website developer requests to have websites added or removed.</span></span>  <span data-ttu-id="755b2-152">リストの更新は、ユーザーのコンピューターに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="755b2-152">Updates to the list are automatically downloaded to user machines.</span></span>  

<span data-ttu-id="755b2-153">Web サイトを IE 互換リストから追加または削除するには、次の情報を [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] にメールで送信します。</span><span class="sxs-lookup"><span data-stu-id="755b2-153">Email the following information to [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] for your website to be added or removed from the IE compatibility list.</span></span>    

*   <span data-ttu-id="755b2-154">所有者の名前</span><span class="sxs-lookup"><span data-stu-id="755b2-154">Owner name</span></span>  
*   <span data-ttu-id="755b2-155">企業タイトル</span><span class="sxs-lookup"><span data-stu-id="755b2-155">Corporate title</span></span>  
*   <span data-ttu-id="755b2-156">メール アドレス</span><span class="sxs-lookup"><span data-stu-id="755b2-156">Email address</span></span>  
*   <span data-ttu-id="755b2-157">会社名</span><span class="sxs-lookup"><span data-stu-id="755b2-157">Company name</span></span>  
*   <span data-ttu-id="755b2-158">住所</span><span class="sxs-lookup"><span data-stu-id="755b2-158">Street address</span></span>  
*   <span data-ttu-id="755b2-159">Web サイトのアドレス</span><span class="sxs-lookup"><span data-stu-id="755b2-159">Website address</span></span>  
    
> [!NOTE]
> <span data-ttu-id="755b2-160">IE 互換性リストは、パブリックサイトでのみ動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="755b2-160">The IE compatibility list is designed to work with public sites only.</span></span>  

<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "Ietoedge@microsoft.com にメールを送信する"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft オフィシャルホーム"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "Microsoft Edge リスト v1 xml が必要です |Microsoft Edge"  

[MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]: https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554 "接続しようとしていた web サイトは、Internet Explorer で動作しません |Microsoft Office サポート"  
