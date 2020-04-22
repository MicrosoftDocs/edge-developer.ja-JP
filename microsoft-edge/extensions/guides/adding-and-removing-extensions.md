---
description: 拡張機能を追加および削除する方法、およびアドレスバーの横にある拡張機能のボタンを移動する方法について説明します。
title: 拡張機能の追加と削除
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者、拡張機能
ms.custom: seodec18
localization_priority: Priority
ms.openlocfilehash: fdc6950962e7ce7e0a720d0bafa7e2c63ebd7098
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569498"
---
# <span data-ttu-id="eeac4-104">Microsoft Edge の拡張機能の追加、移動、削除</span><span class="sxs-lookup"><span data-stu-id="eeac4-104">Adding, moving, and removing extensions for Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="eeac4-105">Microsoft Edge の拡張機能のサポートは、 **Windows 10 の記念日更新プログラム**で導入されています。</span><span class="sxs-lookup"><span data-stu-id="eeac4-105">Microsoft Edge support for extensions was introduced in the **Windows 10 Anniversary Update**.</span></span> <span data-ttu-id="eeac4-106">Microsoft Edge 拡張機能を開発していて、それを読み込む必要がある場合、または既に所有している場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eeac4-106">If you're developing a Microsoft Edge extension and want to load it up, or if you already have and now want to remove it, check out the steps below.</span></span>
<span data-ttu-id="eeac4-107">また、ブラウザーで拡張機能アイコンの場所を変更する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="eeac4-107">Also included are details on how to change your extension icon's location in the browser.</span></span>

## <span data-ttu-id="eeac4-108">拡張機能の追加</span><span class="sxs-lookup"><span data-stu-id="eeac4-108">Adding an extension</span></span>

1. <span data-ttu-id="eeac4-109">Microsoft Edge を開き、"about: flags" をアドレスバーに入力します。</span><span class="sxs-lookup"><span data-stu-id="eeac4-109">Open Microsoft Edge and type 'about:flags' into the address bar.</span></span>

2. <span data-ttu-id="eeac4-110">[**拡張開発者向け機能を有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="eeac4-110">Select the **Enable extension developer features** checkbox.</span></span>

   ![バージョン情報: フラグ開発者向け機能を有効にする](./../media/sideload-aboutflags.png)
   > [!NOTE]
   > <span data-ttu-id="eeac4-112">Windows 10 記念日更新プログラムを持っていない場合、このオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="eeac4-112">If you don't have the Windows 10 Anniversary Update or later, this option will not be available.</span></span>

3. <span data-ttu-id="eeac4-113">[**その他 (...)** ] を選択してメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="eeac4-113">Select **More (...)** to open the menu.</span></span>

   ![[その他] ボタン](./../media/morebutton.png)  

4. <span data-ttu-id="eeac4-115">メニューから [**拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eeac4-115">Select **Extensions** from the menu.</span></span>

5. <span data-ttu-id="eeac4-116">[**拡張機能の読み込み**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="eeac4-116">Select the **Load extension** button.</span></span>

   ![[読み込み拡張機能の選択]](./../media/sideload-load-extension.png)

6. <span data-ttu-id="eeac4-118">拡張機能のフォルダーに移動し、 **[フォルダーの選択**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="eeac4-118">Navigate to your extension's folder and select the  **Select folder** button.</span></span>
   ![読み込む拡張フォルダーの選択](./../media/sideload-select-extension.png)
   > [!NOTE]
   > <span data-ttu-id="eeac4-120">拡張機能の読み込み時にエラーメッセージが表示される場合は、「[トラブルシューティング](./../troubleshooting.md)」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eeac4-120">If you encounter an error message when loading your extension, refer to the [troubleshooting](./../troubleshooting.md) page for guidance.</span></span>


**<span data-ttu-id="eeac4-121">お手続きが完了しました。</span><span class="sxs-lookup"><span data-stu-id="eeac4-121">You're all set!</span></span> <span data-ttu-id="eeac4-122">これで、Microsoft Edge の [拡張機能] ウィンドウに、拡張機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eeac4-122">You should now see the extension listed in Microsoft Edge's extension pane.</span></span>**

![拡張機能ウィンドウの拡張機能](./../media/sideload-extension-installed.png)

> [!NOTE]
> <span data-ttu-id="eeac4-124">署名されていない拡張子は、Microsoft Edge の以降の起動時に自動的にオフになります。</span><span class="sxs-lookup"><span data-stu-id="eeac4-124">Unsigned extensions are automatically turned off on subsequent launches of Microsoft Edge.</span></span> <span data-ttu-id="eeac4-125">ブラウザーでアイドル状態になると (約10秒間の操作が完了すると)、ウィンドウの下部に次の通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eeac4-125">When the browser enters an idle state (after approximately 10 seconds of inactivity) you will see the following notification at the bottom of the window.</span></span> ![<span data-ttu-id="eeac4-126">危険な](./../media/riskynotification.png)通知未署名の拡張子を有効にするには、[このままオンにする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eeac4-126">risky notification](./../media/riskynotification.png) To turn on the unsigned extensions, click "Turn on anyway".</span></span>



## <span data-ttu-id="eeac4-127">[拡張] ボタンの移動</span><span class="sxs-lookup"><span data-stu-id="eeac4-127">Moving the extension button</span></span>
<span data-ttu-id="eeac4-128">拡張機能の設定によっては、[**詳細 (...)** ] メニューに表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="eeac4-128">Depending on your extension's settings, it could appear in the **More (...)** menu.</span></span>

   ![[アクション] メニュー](./../media/browseraction.png)  


<span data-ttu-id="eeac4-130">簡単にアクセスできるように、このメニューからボタンを移動する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eeac4-130">If you want to move the button out of this menu for easier access:</span></span>

1. <span data-ttu-id="eeac4-131">[拡張機能] ボタンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="eeac4-131">Right-click the extension button.</span></span>

2. <span data-ttu-id="eeac4-132">**アドレスバーの横にある [表示] ボタン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="eeac4-132">Select **Show button next to address bar**.</span></span>

   ![[アクション] メニュー](./../media/browseraction_contextmenu.png)  

<span data-ttu-id="eeac4-134">または、[拡張機能の詳細] ページから行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="eeac4-134">Alternatively, you may do this from the extensions details page:</span></span>

1. <span data-ttu-id="eeac4-135">[拡張機能] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eeac4-135">Click on the extension button.</span></span>
2. <span data-ttu-id="eeac4-136">[**アドレスバー] の横にある [表示] ボタン**をオンにします。</span><span class="sxs-lookup"><span data-stu-id="eeac4-136">Toggle **Show button next to address bar** to on.</span></span>

   ![ボタン切り替えボタン](./../media/show-button-toggle.png)

> [!NOTE]
> <span data-ttu-id="eeac4-138">ボタンを右クリックして [アドレスバー **] の\*\*\*\*横に**ある [表示] をクリックするか、[アドレスバー] の横にある [表示] をクリックして、[アドレスバー] の横にある [**表示] ボタン**をクリックし、[アドレスバー] の横にある [表示] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="eeac4-138">You can always move the button back to the **More (...)** menu by right-clicking it and unselecting **Show next to address bar** or by going to the extension details page and toggling **Show button next to address bar** to off.</span></span>


## <span data-ttu-id="eeac4-139">拡張機能の削除</span><span class="sxs-lookup"><span data-stu-id="eeac4-139">Removing an extension</span></span>

1. <span data-ttu-id="eeac4-140">Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="eeac4-140">Open Microsoft Edge.</span></span>

2. <span data-ttu-id="eeac4-141">[**その他 (...)** ] を選択してメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="eeac4-141">Select **More (...)** to open the menu.</span></span>

3. <span data-ttu-id="eeac4-142">メニューから [**拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eeac4-142">Select **Extensions** from the menu.</span></span>

4. <span data-ttu-id="eeac4-143">削除する拡張機能を右クリックし、[**削除**] を選択するか、拡張機能を選択して [**削除**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eeac4-143">Right-click the extension you want to remove and select **Remove**, or select the extension and click the **Remove** button.</span></span>

   ![[アクション] メニュー](./../media/remove.png)  

**<span data-ttu-id="eeac4-145">拡張機能は、Microsoft Edge の一覧に表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="eeac4-145">The extension should disappear from the list in Microsoft Edge.</span></span>**
