---
ms.assetid: 8e2f75c4-fb7f-4892-a6c2-23bac081581a
description: Microsoft Edge 拡張機能のエンタープライズ固有の側面について説明し、UWP アプリとどのように似ているかについて説明します。
title: エンタープライズ向け拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7c23bc24e20b7b00b8779f209dcac8c795067fd5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235043"
---
# <span data-ttu-id="aa1ba-104">エンタープライズ向け拡張機能</span><span class="sxs-lookup"><span data-stu-id="aa1ba-104">Extensions for Enterprise</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="aa1ba-105">Microsoft Edge 拡張機能は、他のエンタープライズ UWP アプリと比較した場合と同様のワークフローを持っています。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-105">Microsoft Edge extensions have a similar workflow when compared to other enterprise UWP apps.</span></span> <span data-ttu-id="aa1ba-106">次の情報では、Microsoft Edge 拡張機能のエンタープライズ固有の側面について詳しい説明を示します。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-106">The information below details enterprise specific aspects of Microsoft Edge extensions.</span></span>

## <span data-ttu-id="aa1ba-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="aa1ba-107">Prerequisites</span></span>
<span data-ttu-id="aa1ba-108">エンタープライズ向け Microsoft Edge 拡張機能を開発、パッケージ化、展開するには、次の項目をお勧めしています。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-108">The following items are suggested to develop, package, and deploy a Microsoft Edge extension for enterprise:</span></span>

+ <span data-ttu-id="aa1ba-109">Windows デベロッパー ポータル アカウント。拡張情報に署名してエンタープライズ プライベート ストアにリリースします。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-109">Windows Developer Portal account, to sign and release the extension to the enterprise private store.</span></span> <span data-ttu-id="aa1ba-110">詳細 [については、「開発者アカウントを開く](/windows/uwp/publish/opening-a-developer-account) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-110">See [Opening a developer account](/windows/uwp/publish/opening-a-developer-account) for more details.</span></span>
+ <span data-ttu-id="aa1ba-111">ビジネスまたは教育向け Microsoft Store。企業にアプリケーションを配布します。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-111">Microsoft Store for Business or Education, to distribute the application to the enterprise.</span></span> <span data-ttu-id="aa1ba-112">詳細については [、ビジネスおよび教育向け Microsoft Store のドキュメント](/microsoft-store/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-112">See the [Microsoft Store for Business and Education documentation](/microsoft-store/) for more details.</span></span>
+ <span data-ttu-id="aa1ba-113">Microsoft Edge 拡張機能を実行する Windows 10 のバージョンを特定します。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-113">Identify which versions of Windows 10 will be running the Microsoft Edge extension.</span></span> <span data-ttu-id="aa1ba-114">既存 [の Windows 10 リリース](https://www.microsoft.com/itpro/windows-10/release-information) の一覧については、Windows 10 のリリース情報をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-114">See [Windows 10 release information](https://www.microsoft.com/itpro/windows-10/release-information) for a listing of existing Windows 10 releases.</span></span>

> [!NOTE]
> <span data-ttu-id="aa1ba-115">サイドローディングは、Windows デベロッパー ポータルを使用して拡張機能のリリースに署名する代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-115">Sideloading can be considered an alternative to using the Windows Developer Portal to sign the release the extension.</span></span> <span data-ttu-id="aa1ba-116">詳しくは、以下のサイドローディング拡張機能の動作をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-116">See the behaviour of sideloading extensions below for more details.</span></span>

## <span data-ttu-id="aa1ba-117">Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="aa1ba-117">Windows Information Protection</span></span>
<span data-ttu-id="aa1ba-118">現在、Microsoft Edge 拡張機能は Windows 情報保護 (WIP) の設定を受け入れることはできません。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-118">Microsoft Edge extensions currently don't honor Windows Information Protection (WIP) settings.</span></span> <span data-ttu-id="aa1ba-119">企業がデータ保護を懸念している場合、Microsoft Edge に対して拡張機能のサポートを有効にしることはできません。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-119">If an enterprise is concerned about data protection, extensions support should not be enabled for Microsoft Edge.</span></span>

<span data-ttu-id="aa1ba-120">従業員の拡張機能を無効にするには、グループ ポリシーと Microsoft Intune の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-120">To disable extensions for employees, configure Group Policy and Microsoft Intune settings.</span></span> <span data-ttu-id="aa1ba-121">構成するポリシーについて詳しくは、「Microsoft Edge で使用可能な [ポリシー」をご覧ください](https://technet.microsoft.com/itpro/microsoft-edge/available-policies)。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-121">For more info on which policies to configure, see [Available policies for Microsoft Edge](https://technet.microsoft.com/itpro/microsoft-edge/available-policies).</span></span>

## <span data-ttu-id="aa1ba-122">拡張機能のパッケージ化</span><span class="sxs-lookup"><span data-stu-id="aa1ba-122">Packaging Extensions</span></span>
<span data-ttu-id="aa1ba-123">企業が拡張機能を従業員に配布するには、まずパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-123">Before an enterprise can distribute an extension to its employees, it must first be packaged.</span></span> <span data-ttu-id="aa1ba-124">パッケージ拡張機能の手順については、パッケージ ガイドをご [覧](./guides/packaging.md) ください。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-124">Instructions on packaging extensions are available in the [Packaging](./guides/packaging.md) guide.</span></span>

> [!TIP]
> <span data-ttu-id="aa1ba-125">配布する前に、すべてのバージョンの Windows 10 で拡張機能のインストールと実行をテストし、期待した動作を確認してください。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-125">Be sure to test installing and running your extension on all the versions of Windows 10 to ensure it will work as expected before distributing.</span></span>

## <span data-ttu-id="aa1ba-126">拡張機能の配布</span><span class="sxs-lookup"><span data-stu-id="aa1ba-126">Distributing Extensions</span></span>
<span data-ttu-id="aa1ba-127">拡張機能がパッケージ化された後は、Microsoft Store、ビジネス向け Microsoft Store、またはサイドロードを通じて従業員に配布できます。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-127">Once an extension has been packaged, it can be distributed to employees through the Microsoft Store, Microsoft Store for Business, or by sideloading.</span></span>

<span data-ttu-id="aa1ba-128">ビジネス向け Microsoft Store を使って配布される拡張機能は、従業員に割り当てるか、すべての従業員がアクセスできるプライベート ストアに追加できます。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-128">Extensions distributed though the Microsoft Store for Business can either be assigned to employees, or added to a private store where all employees can access them.</span></span> <span data-ttu-id="aa1ba-129">これは、「LOB [(Line-of-Business)](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) アプリを企業に配布する」ガイドに従って行います。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-129">This can be done by following the [Distribute "Line-of-Business" (LOB) apps to enterprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) guide.</span></span>

<span data-ttu-id="aa1ba-130">拡張機能をサイドロードするには、サイドローディング用にデバイス (非管理対象または管理) のロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-130">To sideload extensions, devices (unmanaged or managed) must be unlocked for sideloading.</span></span> <span data-ttu-id="aa1ba-131">パッケージ [化された拡張機能をサイドロードする方法について詳しくは、Windows 10](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) の LOB アプリのサイドロードに関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-131">See [Sideload LOB apps in Windows 10](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) for more info on how to sideload packaged extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa1ba-132">企業が拡張機能を内部で開発および配布している場合、企業にはビジネス向け Microsoft Store (または Education) と Windows デベロッパー ポータル アカウントの両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-132">If the enterprise is both developing and distributing the extension internally, the enterprise will require both the Microsoft Store for Business (or Education) and a Windows Developer Portal account.</span></span>

### <span data-ttu-id="aa1ba-133">サイドロードされた拡張機能の動作</span><span class="sxs-lookup"><span data-stu-id="aa1ba-133">Behavior of Sideloaded Extensions</span></span>
<span data-ttu-id="aa1ba-134">Microsoft Store (またはビジネス向け Microsoft Store) を通じて配布される拡張機能とは異なり、サイドローディングされた拡張機能は Microsoft Edge で異なる方法で扱います。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-134">Unlike extensions distributed through the Microsoft Store (or the Microsoft Store for Business), sideloaded extensions are treated differently in Microsoft Edge.</span></span>

<span data-ttu-id="aa1ba-135">最初の違いは、インストール後のサイドロードされた拡張機能の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-135">The first difference affects how sideloaded extensions behave after installation.</span></span> <span data-ttu-id="aa1ba-136">Microsoft Store の拡張機能とは異なり、サイドローディングされた拡張機能では、すぐに "新しい拡張機能があります" という通知が表示されるのではなく、ユーザーが手動で有効にしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-136">Unlike extensions from the Microsoft Store, sideloaded extensions do not immediately display the "You have a new extension" notification and need to be manually turned on by the user.</span></span>

<span data-ttu-id="aa1ba-137">拡張機能を有効にする場合は、[その他 **] (...)** メニューを開き、[拡張機能 **]** を選択すると、インストールされている拡張機能の一覧にサイドロードされた拡張機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-137">To turn on the extension, open the **More (...)** menu, select **"Extensions"** and you should see the sideloaded extension in the list of installed extensions.</span></span> <span data-ttu-id="aa1ba-138">拡張機能をクリックし、有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-138">Click on the extension and turn it on.</span></span>

<span data-ttu-id="aa1ba-139">2 つ目の違いは、ブラウザーでのサイドローディングされた拡張機能の表示方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-139">The second difference affects how sideloaded extensions appear in the browser.</span></span> <span data-ttu-id="aa1ba-140">たとえば、"新しい拡張機能があります" という通知とインストールされている拡張機能の一覧の両方に、拡張機能が不明なソースからの拡張であることを示す追加の警告が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-140">For example, both the "You have a new extension" notification and the list of installed extensions include an additional warning stating that the extension is from an unknown source.</span></span>

![サイドロード警告 1](./media/sideload-permissionflyout.PNG)

![サイドロード警告 2](./media/sideload-l1warning.PNG)

<span data-ttu-id="aa1ba-143">3 番目と最後の違いは、ブラウザー起動時のサイドローディングされた拡張機能の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-143">The third and final difference affects how sideloaded extensions behave on browser startup.</span></span> <span data-ttu-id="aa1ba-144">ドメインに参加しているデバイスまたは MDM が有効になっているデバイスでサイドロードされた拡張機能は、Microsoft Store の拡張機能と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-144">Sideloaded extensions on devices that are either domain-joined or MDM enabled will behave like extensions from the Microsoft Store.</span></span> <span data-ttu-id="aa1ba-145">ただし、ドメインに参加していないデバイスや MDM が有効になっているデバイスでサイドロードされた拡張機能は、ブラウザーの起動時にオフにされ、ユーザーが明示的なアクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-145">However, sideloaded extensions on devices that are not domain-joined or MDM enabled will be turned off during browser startup and require the user to take explicit action.</span></span>

<span data-ttu-id="aa1ba-146">ブラウザーの起動後 (非アクティブな状態が最大 10 秒後) の直後に、ウィンドウの下部近くに次の通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-146">Shortly after browser startup (after ~10 seconds of inactivity) the following notification will appear near the bottom of the window.</span></span>

![サイドロード通知](./media/sideload-scareUI.PNG)

<span data-ttu-id="aa1ba-148">Microsoft Edge が起動されるたび、ユーザーは拡張機能を使用するために [オンにする] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa1ba-148">Each time Microsoft Edge is launched, users will need to select "Turn on anyway" in order to use the extension.</span></span>
