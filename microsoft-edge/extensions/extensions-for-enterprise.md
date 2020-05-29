---
ms.assetid: 8e2f75c4-fb7f-4892-a6c2-23bac081581a
description: Microsoft Edge Extensions のエンタープライズ固有の側面について説明し、それが UWP アプリとどのように類似しているかを確認します。
title: エンタープライズ向けの拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: 8f50c282fce11d2654f990bf135941e0616af3f3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569521"
---
# <span data-ttu-id="6700e-104">エンタープライズ向けの拡張機能</span><span class="sxs-lookup"><span data-stu-id="6700e-104">Extensions for Enterprise</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="6700e-105">Microsoft Edge extensions のワークフローは、他のエンタープライズ UWP アプリと比較した場合に似ています。</span><span class="sxs-lookup"><span data-stu-id="6700e-105">Microsoft Edge extensions have a similar workflow when compared to other enterprise UWP apps.</span></span> <span data-ttu-id="6700e-106">以下では、Microsoft Edge extensions のエンタープライズ固有の側面について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="6700e-106">The information below details enterprise specific aspects of Microsoft Edge extensions.</span></span>

## <span data-ttu-id="6700e-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="6700e-107">Prerequisites</span></span>
<span data-ttu-id="6700e-108">エンタープライズ向け Microsoft Edge 拡張機能を開発、パッケージ化、展開するには、次の項目を提案します。</span><span class="sxs-lookup"><span data-stu-id="6700e-108">The following items are suggested to develop, package, and deploy a Microsoft Edge extension for enterprise:</span></span>

+ <span data-ttu-id="6700e-109">Windows デベロッパーポータルアカウント。エンタープライズプライベートストアの内線番号に署名してリリースします。</span><span class="sxs-lookup"><span data-stu-id="6700e-109">Windows Developer Portal account, to sign and release the extension to the enterprise private store.</span></span> <span data-ttu-id="6700e-110">詳細については[、「開発者アカウントを開く](/windows/uwp/publish/opening-a-developer-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6700e-110">See [Opening a developer account](/windows/uwp/publish/opening-a-developer-account) for more details.</span></span>
+ <span data-ttu-id="6700e-111">ビジネスまたは教育機関向けの Microsoft ストア。アプリケーションを企業に配布します。</span><span class="sxs-lookup"><span data-stu-id="6700e-111">Microsoft Store for Business or Education, to distribute the application to the enterprise.</span></span> <span data-ttu-id="6700e-112">詳細については、「一般[法人向け Microsoft ストアと教育機関向けドキュメント](/microsoft-store/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6700e-112">See the [Microsoft Store for Business and Education documentation](/microsoft-store/) for more details.</span></span>
+ <span data-ttu-id="6700e-113">Microsoft Edge 拡張機能を実行する Windows 10 のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="6700e-113">Identify which versions of Windows 10 will be running the Microsoft Edge extension.</span></span> <span data-ttu-id="6700e-114">既存の Windows 10 リリースの一覧については、「 [windows 10 リリース情報](https://www.microsoft.com/itpro/windows-10/release-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6700e-114">See [Windows 10 release information](https://www.microsoft.com/itpro/windows-10/release-information) for a listing of existing Windows 10 releases.</span></span>

> [!NOTE]
> <span data-ttu-id="6700e-115">サイドローディングは、Windows 開発者ポータルを使用して延長をリリースする代わりの方法と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="6700e-115">Sideloading can be considered an alternative to using the Windows Developer Portal to sign the release the extension.</span></span> <span data-ttu-id="6700e-116">詳細については、以下のサイドローディング拡張機能の動作を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6700e-116">See the behaviour of sideloading extensions below for more details.</span></span>

## <span data-ttu-id="6700e-117">Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="6700e-117">Windows Information Protection</span></span>
<span data-ttu-id="6700e-118">Microsoft Edge extensions は現在、Windows Information Protection (WIP) 設定を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="6700e-118">Microsoft Edge extensions currently don't honor Windows Information Protection (WIP) settings.</span></span> <span data-ttu-id="6700e-119">企業がデータ保護を懸念している場合は、Microsoft Edge で拡張機能のサポートを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6700e-119">If an enterprise is concerned about data protection, extensions support should not be enabled for Microsoft Edge.</span></span>

<span data-ttu-id="6700e-120">従業員の内線番号を無効にするには、グループポリシーと Microsoft Intune の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6700e-120">To disable extensions for employees, configure Group Policy and Microsoft Intune settings.</span></span> <span data-ttu-id="6700e-121">構成するポリシーの詳細については、「 [Microsoft Edge で利用可能なポリシー](https://technet.microsoft.com/itpro/microsoft-edge/available-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6700e-121">For more info on which policies to configure, see [Available policies for Microsoft Edge](https://technet.microsoft.com/itpro/microsoft-edge/available-policies).</span></span>

## <span data-ttu-id="6700e-122">パッケージ化の拡張機能</span><span class="sxs-lookup"><span data-stu-id="6700e-122">Packaging Extensions</span></span>
<span data-ttu-id="6700e-123">企業が、内線番号を従業員に配布するには、最初にパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6700e-123">Before an enterprise can distribute an extension to its employees, it must first be packaged.</span></span> <span data-ttu-id="6700e-124">パッケージ化の拡張については、「[パッケージ](./guides/packaging.md)ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6700e-124">Instructions on packaging extensions are available in the [Packaging](./guides/packaging.md) guide.</span></span>

> [!TIP]
> <span data-ttu-id="6700e-125">配布前に正常に動作するように、Windows 10 のすべてのバージョンで拡張機能をインストールして実行してください。</span><span class="sxs-lookup"><span data-stu-id="6700e-125">Be sure to test installing and running your extension on all the versions of Windows 10 to ensure it will work as expected before distributing.</span></span>

## <span data-ttu-id="6700e-126">内線番号の配布</span><span class="sxs-lookup"><span data-stu-id="6700e-126">Distributing Extensions</span></span>
<span data-ttu-id="6700e-127">パッケージ化された拡張機能は、Microsoft Store、一般法人向け Microsoft Store、またはサイドローディングによって従業員に配布できます。</span><span class="sxs-lookup"><span data-stu-id="6700e-127">Once an extension has been packaged, it can be distributed to employees through the Microsoft Store, Microsoft Store for Business, or by sideloading.</span></span>

<span data-ttu-id="6700e-128">一般法人向け Microsoft Store で配布された拡張機能は、従業員に割り当てるか、すべての従業員がアクセスできるプライベートストアに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6700e-128">Extensions distributed though the Microsoft Store for Business can either be assigned to employees, or added to a private store where all employees can access them.</span></span> <span data-ttu-id="6700e-129">これを行うには、 [「基幹業務 (LOB) アプリを企業向けガイドに配布する](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6700e-129">This can be done by following the [Distribute "Line-of-Business" (LOB) apps to enterprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) guide.</span></span>

<span data-ttu-id="6700e-130">サイドローディングの拡張機能を使用するには、サイドローディングについてデバイス (非管理または管理されているもの) のロックを解除する</span><span class="sxs-lookup"><span data-stu-id="6700e-130">To sideload extensions, devices (unmanaged or managed) must be unlocked for sideloading.</span></span> <span data-ttu-id="6700e-131">パッケージ化された拡張機能のサイドローディング方法の詳細については、「 [Windows 10 のサイドローディング LOB アプリ](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6700e-131">See [Sideload LOB apps in Windows 10](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) for more info on how to sideload packaged extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6700e-132">企業が社内で拡張機能の開発と配布を行っている場合、企業は、一般法人向け Microsoft Store (または教育機関) と Windows 開発者ポータルアカウントの両方を必要とします。</span><span class="sxs-lookup"><span data-stu-id="6700e-132">If the enterprise is both developing and distributing the extension internally, the enterprise will require both the Microsoft Store for Business (or Education) and a Windows Developer Portal account.</span></span>

### <span data-ttu-id="6700e-133">サイドローディング Extensions の動作</span><span class="sxs-lookup"><span data-stu-id="6700e-133">Behavior of Sideloaded Extensions</span></span>
<span data-ttu-id="6700e-134">Microsoft Store (または一般法人向け Microsoft Store) 経由で配布された拡張機能とは異なり、Microsoft Edge では、サイドローディング extensions の取り扱いは異なります。</span><span class="sxs-lookup"><span data-stu-id="6700e-134">Unlike extensions distributed through the Microsoft Store (or the Microsoft Store for Business), sideloaded extensions are treated differently in Microsoft Edge.</span></span>

<span data-ttu-id="6700e-135">最初の違いは、インストール後のサイドローディングの拡張機能の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="6700e-135">The first difference affects how sideloaded extensions behave after installation.</span></span> <span data-ttu-id="6700e-136">Microsoft Store の拡張機能とは異なり、サイドローディング extensions では "新しい拡張子を持っています" という通知はすぐには表示されず、ユーザーが手動で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6700e-136">Unlike extensions from the Microsoft Store, sideloaded extensions do not immediately display the "You have a new extension" notification and need to be manually turned on by the user.</span></span>

<span data-ttu-id="6700e-137">拡張機能を有効にするには、[**詳細 (...)** ] メニューを開き、[**拡張機能**] を選択すると、インストールされている拡張機能の一覧にサイドローディング拡張子が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6700e-137">To turn on the extension, open the **More (...)** menu, select **"Extensions"** and you should see the sideloaded extension in the list of installed extensions.</span></span> <span data-ttu-id="6700e-138">拡張機能をクリックして有効にします。</span><span class="sxs-lookup"><span data-stu-id="6700e-138">Click on the extension and turn it on.</span></span>

<span data-ttu-id="6700e-139">2つ目の違いは、ブラウザーでのサイドローディング extensions の表示方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="6700e-139">The second difference affects how sideloaded extensions appear in the browser.</span></span> <span data-ttu-id="6700e-140">たとえば、"新しい拡張機能" 通知とインストールされている拡張機能の一覧には、不明なソースからの拡張機能であることを示す警告が追加されます。</span><span class="sxs-lookup"><span data-stu-id="6700e-140">For example, both the "You have a new extension" notification and the list of installed extensions include an additional warning stating that the extension is from an unknown source.</span></span>

![サイドローディング警告1](./media/sideload-permissionflyout.PNG)

![サイドローディング警告2](./media/sideload-l1warning.PNG)

<span data-ttu-id="6700e-143">第3の違いは、ブラウザーの起動時にサイドローディングの拡張機能がどのように動作するかに影響します。</span><span class="sxs-lookup"><span data-stu-id="6700e-143">The third and final difference affects how sideloaded extensions behave on browser startup.</span></span> <span data-ttu-id="6700e-144">ドメイン参加または MDM 対応のデバイス上のサイドローディング拡張機能は、Microsoft Store の拡張機能と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="6700e-144">Sideloaded extensions on devices that are either domain-joined or MDM enabled will behave like extensions from the Microsoft Store.</span></span> <span data-ttu-id="6700e-145">ただし、ドメインに参加していないデバイス、または MDM が有効になっているデバイス上のサイドローディング拡張機能は、ブラウザーの起動時にオフになり、ユーザーが明示的に操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6700e-145">However, sideloaded extensions on devices that are not domain-joined or MDM enabled will be turned off during browser startup and require the user to take explicit action.</span></span>

<span data-ttu-id="6700e-146">ブラウザーの起動時のまもなく (アイドル状態が10秒未満の場合)、次の通知がウィンドウの下部付近に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6700e-146">Shortly after browser startup (after ~10 seconds of inactivity) the following notification will appear near the bottom of the window.</span></span>

![サイドローディング通知](./media/sideload-scareUI.PNG)

<span data-ttu-id="6700e-148">Microsoft Edge が起動されるたびに、拡張機能を使用するために、ユーザーは "このままオンにする" を選ぶ必要があります。</span><span class="sxs-lookup"><span data-stu-id="6700e-148">Each time Microsoft Edge is launched, users will need to select "Turn on anyway" in order to use the extension.</span></span>
