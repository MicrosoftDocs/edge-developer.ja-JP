---
description: Internet Explorer から Microsoft Edge にユーザーを移動する
title: Internet Explorer から Microsoft Edge にユーザーを移動する
author: MSEdgeTeam
ms.date: 11/04/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム、internet explorer
ms.openlocfilehash: 48f0f4121fb444d80603dcbb408397679c64753d
ms.sourcegitcommit: 7b4441b7656c8317139650f904b70cc87797d37e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154334"
---
# <span data-ttu-id="6fd04-104">Internet Explorer から Microsoft Edge にユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="6fd04-104">Moving users to Microsoft Edge from Internet Explorer</span></span> 

<span data-ttu-id="6fd04-105">最新の web サイトの多くには、Internet Explorer \ (IE \) と互換性のないデザインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6fd04-105">Many modern websites have designs that are incompatible with Internet Explorer \(IE\).</span></span>  <span data-ttu-id="6fd04-106">IE ユーザーが互換性のない一般向け web サイトにアクセスすると、ユーザーにメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6fd04-106">When an IE user visits an incompatible public website, the user may get a message.</span></span>  <span data-ttu-id="6fd04-107">このメッセージは、web サイトがブラウザーに対応していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6fd04-107">The message states that the website is incompatible with the browser.</span></span>  <span data-ttu-id="6fd04-108">メッセージが表示された後、ユーザーは、最新のブラウザーに手動で切り替えるように求められます。</span><span class="sxs-lookup"><span data-stu-id="6fd04-108">After the message is displayed, the user is expected to manually switch to a modern browser.</span></span>  <span data-ttu-id="6fd04-109">バージョン84以降では、中断を最小限にするために、Microsoft Edge はユーザーを自動的にリダイレクトする新機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6fd04-109">To minimize disruptions, starting with version 84, Microsoft Edge supports a new capability that automatically redirects users.</span></span>  <span data-ttu-id="6fd04-110">Ie と互換性のない web サイトに IE ユーザーが移動すると、Windows はユーザーを Microsoft Edge に自動的にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="6fd04-110">When an IE user navigates to a website that is incompatible with IE, Windows automatically redirects the user to Microsoft Edge.</span></span>  <span data-ttu-id="6fd04-111">リスト上の web サイトを確認するには、「 [Microsoft Edge リストが必要][MicrosoftEdgeNeededgeV1]ですか?」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fd04-111">To review the websites on the list, navigate to [Need Microsoft Edge list][MicrosoftEdgeNeededgeV1].</span></span>

<span data-ttu-id="6fd04-112">この記事では、次の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fd04-112">This article describes the following concepts.</span></span>  

*   <span data-ttu-id="6fd04-113">リダイレクトのユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="6fd04-113">The user experience for redirection</span></span>  
*   <span data-ttu-id="6fd04-114">IE 互換性の一覧に web サイトを追加する方法</span><span class="sxs-lookup"><span data-stu-id="6fd04-114">How to add your website to the IE compatibility list</span></span>  
*   <span data-ttu-id="6fd04-115">IE 互換性リストから web サイトを削除する方法</span><span class="sxs-lookup"><span data-stu-id="6fd04-115">How to remove your website from the IE compatibility list</span></span>  
    
## <span data-ttu-id="6fd04-116">Web サイトが IE 互換性リストに追加されているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="6fd04-116">Why is a website added to the IE compatibility list?</span></span>  

<span data-ttu-id="6fd04-117">IE 互換性リストは、次の操作が発生した場合にのみ web サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fd04-117">The IE compatibility List only adds a website when the following actions occur.</span></span>  

*   <span data-ttu-id="6fd04-118">互換性の理由により、ユーザーが別のブラウザーを使用する必要があることを示すメッセージが IE ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fd04-118">Shows an IE user a message suggesting the user should use a different browser for compatibility reasons.</span></span>  
*   <span data-ttu-id="6fd04-119">所有者要求。 IE 互換性の一覧に web サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fd04-119">Owner requests to add the website to the IE compatibility list.</span></span>  
    
## <span data-ttu-id="6fd04-120">IE 互換性の一覧を更新する</span><span class="sxs-lookup"><span data-stu-id="6fd04-120">Update the IE compatibility list</span></span>  

<span data-ttu-id="6fd04-121">IE 互換性リストは、 [microsoft.com][MicrosoftOfficialHome]上の XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="6fd04-121">The IE compatibility list is an XML file on [microsoft.com][MicrosoftOfficialHome].</span></span>  <span data-ttu-id="6fd04-122">ユーザーと web サイトの開発者が web サイトを追加または削除することを要求するように、リストが定期的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="6fd04-122">The list is regularly updated in response to user's and website developers requests to have websites added or removed.</span></span>  <span data-ttu-id="6fd04-123">リストの更新は、ユーザーのコンピューターに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="6fd04-123">Updates to the list are automatically downloaded to user machines.</span></span>  

<span data-ttu-id="6fd04-124">Web サイトを IE 互換リストから追加または削除するには、次の情報を [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] にメールで送信します。</span><span class="sxs-lookup"><span data-stu-id="6fd04-124">Email the following information to [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] for your website to be added or removed from the IE compatibility list.</span></span>    

*   <span data-ttu-id="6fd04-125">所有者の名前</span><span class="sxs-lookup"><span data-stu-id="6fd04-125">Owner name</span></span>  
*   <span data-ttu-id="6fd04-126">企業タイトル</span><span class="sxs-lookup"><span data-stu-id="6fd04-126">Corporate title</span></span>  
*   <span data-ttu-id="6fd04-127">メール アドレス</span><span class="sxs-lookup"><span data-stu-id="6fd04-127">Email address</span></span>  
*   <span data-ttu-id="6fd04-128">会社名</span><span class="sxs-lookup"><span data-stu-id="6fd04-128">Company name</span></span>  
*   <span data-ttu-id="6fd04-129">住所</span><span class="sxs-lookup"><span data-stu-id="6fd04-129">Street address</span></span>  
*   <span data-ttu-id="6fd04-130">Web サイトのアドレス</span><span class="sxs-lookup"><span data-stu-id="6fd04-130">Website address</span></span>  
<!--  *   Telephone number  -->  
<!--  *   Target platform \(desktop, phone, Xbox\)  -->  
    
<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "Ietoedge@microsoft.com にメールを送信する"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft オフィシャルホーム"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "Microsoft Edge リスト v1 xml が必要です |Microsoft Edge"  
