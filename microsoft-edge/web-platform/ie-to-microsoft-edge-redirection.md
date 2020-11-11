---
description: Internet Explorer から Microsoft Edge にユーザーを移動する
title: Internet Explorer から Microsoft Edge にユーザーを移動する
author: MSEdgeTeam
ms.date: 11/06/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム、internet explorer
ms.openlocfilehash: 2e1488359e405247e290ad8f6300c480a7e20af6
ms.sourcegitcommit: 6ef48c8cda392c6bf8217cff5f696ac620d10739
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163208"
---
# <span data-ttu-id="8702f-104">Internet Explorer から Microsoft Edge にユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="8702f-104">Moving users to Microsoft Edge from Internet Explorer</span></span> 

<span data-ttu-id="8702f-105">最新の web サイトの多くには、Internet Explorer \ (IE \) と互換性のないデザインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8702f-105">Many modern websites have designs that are incompatible with Internet Explorer \(IE\).</span></span>  <span data-ttu-id="8702f-106">IE ユーザーが互換性のない一般向け web サイトにアクセスすると、ユーザーにメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="8702f-106">When an IE user visits an incompatible public website, the user may get a message.</span></span>  <span data-ttu-id="8702f-107">このメッセージは、web サイトがブラウザーに対応していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8702f-107">The message states that the website is incompatible with the browser.</span></span>  <span data-ttu-id="8702f-108">メッセージが表示された後、ユーザーは、最新のブラウザーに手動で切り替えるように求められます。</span><span class="sxs-lookup"><span data-stu-id="8702f-108">After the message is displayed, the user is expected to manually switch to a modern browser.</span></span>  <span data-ttu-id="8702f-109">バージョン84以降では、中断を最小限にするために、Microsoft Edge はユーザーを自動的にリダイレクトする新機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8702f-109">To minimize disruptions, starting with version 84, Microsoft Edge supports a new capability that automatically redirects users.</span></span>  <span data-ttu-id="8702f-110">Ie と互換性のない web サイトに IE ユーザーが移動すると、Windows はユーザーを Microsoft Edge に自動的にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="8702f-110">When an IE user navigates to a website that is incompatible with IE, Windows automatically redirects the user to Microsoft Edge.</span></span>  <span data-ttu-id="8702f-111">リスト上の web サイトを確認するには、「 [Microsoft Edge リストが必要][MicrosoftEdgeNeededgeV1]ですか?」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8702f-111">To review the websites on the list, navigate to [Need Microsoft Edge list][MicrosoftEdgeNeededgeV1].</span></span>

<span data-ttu-id="8702f-112">この記事では、次の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="8702f-112">This article describes the following concepts.</span></span>  

*   <span data-ttu-id="8702f-113">リダイレクトのユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="8702f-113">The user experience for redirection</span></span>  
*   <span data-ttu-id="8702f-114">リストの更新を要求する方法</span><span class="sxs-lookup"><span data-stu-id="8702f-114">How to request an update to the list</span></span>  
    
## <span data-ttu-id="8702f-115">Web サイトが IE 互換性リストに追加されているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="8702f-115">Why is a website added to the IE compatibility list?</span></span>  

<span data-ttu-id="8702f-116">IE 互換性リストは、次の操作が発生した場合にのみ web サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="8702f-116">The IE compatibility List only adds a website when the following actions occur.</span></span>  

*   <span data-ttu-id="8702f-117">互換性の理由により、ユーザーが別のブラウザーを使用する必要があることを示すメッセージが IE ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8702f-117">Shows an IE user a message suggesting the user should use a different browser for compatibility reasons.</span></span>  
*   <span data-ttu-id="8702f-118">所有者要求。 IE 互換性の一覧に web サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="8702f-118">Owner requests to add the website to the IE compatibility list.</span></span>  
    
## <span data-ttu-id="8702f-119">IE 互換性の一覧を更新する</span><span class="sxs-lookup"><span data-stu-id="8702f-119">Update the IE compatibility list</span></span>  

<span data-ttu-id="8702f-120">IE 互換性リストは、 [microsoft.com][MicrosoftOfficialHome]上の XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="8702f-120">The IE compatibility list is an XML file on [microsoft.com][MicrosoftOfficialHome].</span></span>  <span data-ttu-id="8702f-121">リストは、ユーザーと web サイトの開発者からの要求に応じて定期的に更新され、web サイトを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="8702f-121">The list is regularly updated in response to user and website developer requests to have websites added or removed.</span></span>  <span data-ttu-id="8702f-122">リストの更新は、ユーザーのコンピューターに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="8702f-122">Updates to the list are automatically downloaded to user machines.</span></span>  

<span data-ttu-id="8702f-123">Web サイトを IE 互換リストから追加または削除するには、次の情報を [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] にメールで送信します。</span><span class="sxs-lookup"><span data-stu-id="8702f-123">Email the following information to [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] for your website to be added or removed from the IE compatibility list.</span></span>    

*   <span data-ttu-id="8702f-124">所有者の名前</span><span class="sxs-lookup"><span data-stu-id="8702f-124">Owner name</span></span>  
*   <span data-ttu-id="8702f-125">企業タイトル</span><span class="sxs-lookup"><span data-stu-id="8702f-125">Corporate title</span></span>  
*   <span data-ttu-id="8702f-126">メール アドレス</span><span class="sxs-lookup"><span data-stu-id="8702f-126">Email address</span></span>  
*   <span data-ttu-id="8702f-127">会社名</span><span class="sxs-lookup"><span data-stu-id="8702f-127">Company name</span></span>  
*   <span data-ttu-id="8702f-128">住所</span><span class="sxs-lookup"><span data-stu-id="8702f-128">Street address</span></span>  
*   <span data-ttu-id="8702f-129">Web サイトのアドレス</span><span class="sxs-lookup"><span data-stu-id="8702f-129">Website address</span></span>  
    
> [!NOTE]
> <span data-ttu-id="8702f-130">IE 互換性リストは、パブリックサイトでのみ動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8702f-130">The IE compatibility list is designed to work with public sites only.</span></span>  

<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "Ietoedge@microsoft.com にメールを送信する"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft オフィシャルホーム"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "Microsoft Edge リスト v1 xml が必要です |Microsoft Edge"  
