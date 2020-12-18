---
description: Windows 開発者アカウントにサインアップし、Microsoft Edge 拡張機能の名前を予約する方法について説明します。
title: パートナー センターの拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 90c5d35e7df30d01eecb6dc87572f81a49905eee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234932"
---
# <span data-ttu-id="68725-104">Windows 開発者アカウントへの登録とパートナー センターでの名前の予約</span><span class="sxs-lookup"><span data-stu-id="68725-104">Registering for a Windows Developer account and reserving names in Partner Center</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="68725-105">[パートナー センター](https://partner.microsoft.com/dashboard) では、Windows デバイス用のすべてのアプリを公開して管理できます。</span><span class="sxs-lookup"><span data-stu-id="68725-105">[Partner Center](https://partner.microsoft.com/dashboard) lets you publish and manage all of your apps for Windows devices.</span></span> <span data-ttu-id="68725-106">ここで開発者アカウントにサインアップし、サインアップ[](https://developer.microsoft.com/store/register)プロセスについて質問がある場合[](https://docs.microsoft.com/windows/uwp/publish/opening-a-developer-account)は、開発者アカウントのドキュメントを開く方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68725-106">You can sign up for a developer account [here](https://developer.microsoft.com/store/register), and refer to the [opening a developer account documentation](https://docs.microsoft.com/windows/uwp/publish/opening-a-developer-account) for any questions you may have about the sign up process.</span></span>
> [!NOTE]
> <span data-ttu-id="68725-107">開発者アカウントに [サインアップするには、Microsoft](https://login.live.com/) アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="68725-107">You will need a [Microsoft account](https://login.live.com/) to sign up for a developer account.</span></span>

### <span data-ttu-id="68725-108">Microsoft Store のマルチユーザー組織アカウント管理</span><span class="sxs-lookup"><span data-stu-id="68725-108">Multi-users organization account management for Microsoft Store</span></span>  

<span data-ttu-id="68725-109">大規模な組織では、Microsoft Edge 拡張機能を管理するために、異なるアカウントに異なる役割を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="68725-109">In a large organization, you may assign different roles to different accounts for managing your Microsoft Edge Extension.</span></span> <span data-ttu-id="68725-110">Azure Active Directory を使用してさまざまな [ロールを割り当て、](https://msdn.microsoft.com/windows/uwp/publish/manage-account-users) パートナー センター アカウントでアカウント ユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="68725-110">You can assign different roles [using Azure Active Directory to manage account users](https://msdn.microsoft.com/windows/uwp/publish/manage-account-users) in your Partner Center account.</span></span>

<span data-ttu-id="68725-111">たとえば、次の構造を設定できます。</span><span class="sxs-lookup"><span data-stu-id="68725-111">For example, you could set up the following structure:</span></span>
- <span data-ttu-id="68725-112">エンジニアリング チームは、パッケージの作成とアップロードを担当します。</span><span class="sxs-lookup"><span data-stu-id="68725-112">The engineering team is responsible for creating and uploading the package.</span></span>
- <span data-ttu-id="68725-113">マーケティング チームは、拡張機能の配布を担当します。</span><span class="sxs-lookup"><span data-stu-id="68725-113">The marketing team is responsible for the distribution of the extension.</span></span>
- <span data-ttu-id="68725-114">クリエイティブ チームは、クリエイティブなアセットと拡張機能のスクリーンショットをアップロードする責任があります。</span><span class="sxs-lookup"><span data-stu-id="68725-114">The creative team is responsible for uploading creative assets and screenshots of the extension.</span></span>

<span data-ttu-id="68725-115">各ユーザー/グループまたは Azure AD アプリケーションには、アカウントに対する特定のアクセス許可のセットを付与するロールが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="68725-115">Each user/group/or Azure AD application is assigned a role that gives them a specific set of permissions to the account.</span></span>

### <span data-ttu-id="68725-116">名前の予約</span><span class="sxs-lookup"><span data-stu-id="68725-116">Name reservation</span></span>

<span data-ttu-id="68725-117">名前の予約は、Microsoft Store で拡張機能を取得する最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="68725-117">Reserving a name is the first step towards getting your extension in the Microsoft Store.</span></span>
<span data-ttu-id="68725-118">他のユーザーが [取得する前](/windows/uwp/publish/create-your-app-by-reserving-a-name) に、パートナー センターを通じてできるだけ早く拡張機能の名前を予約するようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68725-118">It's recommended that you [reserve the name of your extension](/windows/uwp/publish/create-your-app-by-reserving-a-name) as soon as possible through Partner Center before it gets taken by someone else.</span></span> <span data-ttu-id="68725-119">これは、拡張機能の構築をまだ開始していない場合でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="68725-119">You can do this even if you haven't started building your extension yet.</span></span>

> [!NOTE]
> <span data-ttu-id="68725-120">ここで選択する名前は、拡張機能の JSON マニフェストで指定されている名前と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="68725-120">The name chosen here has to match the name that is specified in the JSON manifest for the extension.</span></span> 

<span data-ttu-id="68725-121">拡張機能 [に使用する](https://msdn.microsoft.com/windows/uwp/publish/manage-app-names)追加の名前を予約することもできます。これは、拡張機能を複数の言語で提供し、異なる言語に異なる名前を使用する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="68725-121">You can also [reserve additional names to use for your extension](https://msdn.microsoft.com/windows/uwp/publish/manage-app-names), which is especially useful if you are offering the extension in multiple languages and want to use different names for different languages.</span></span> <span data-ttu-id="68725-122">ローカライズの詳細については、「拡張パッケージのローカライズ [」を参照してください](./localizing-extension-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="68725-122">You can find more information on localization in [Localizing extension packages](./localizing-extension-packages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="68725-123">Microsoft Store に [アクセス](https://aka.ms/extension-request) して拡張機能の提供が承認された後は、アプリの申請のチェックリスト [を確認してください](https://docs.microsoft.com/windows/uwp/publish/app-submissions)。</span><span class="sxs-lookup"><span data-stu-id="68725-123">Once you've [reached out to us](https://aka.ms/extension-request) and have been approved to have your extension in the Microsoft Store, check out the [app submission checklist](https://docs.microsoft.com/windows/uwp/publish/app-submissions).</span></span>
