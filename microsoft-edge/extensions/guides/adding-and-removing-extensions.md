---
description: 拡張機能の追加と削除、および [アドレス] バーの横にある拡張機能のボタンを移動する方法について説明します。
title: 拡張機能の追加と削除
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、css、javascript、開発者、拡張機能
ms.custom: seodec18
ms.localizationpriority: high
ms.openlocfilehash: aeebc0f18d6b4a743c790571b8287a209233e73f
ms.sourcegitcommit: 1e33cd41e5afb2e6dbdc19353011ff6c2b019f9c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2020
ms.locfileid: "10866079"
---
# <span data-ttu-id="1623a-104">Microsoft Edge の拡張機能の追加、移動、および削除</span><span class="sxs-lookup"><span data-stu-id="1623a-104">Adding, moving, and removing extensions for Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="1623a-105">Microsoft Edge の拡張機能のサポートが、**Windows 10 Anniversary Update** に追加されました。</span><span class="sxs-lookup"><span data-stu-id="1623a-105">Microsoft Edge support for extensions was introduced in the **Windows 10 Anniversary Update**.</span></span> <span data-ttu-id="1623a-106">Microsoft Edge 拡張機能を開発していて、それを読み込ませる場合、または既に所有していて削除したい場合は、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1623a-106">If you're developing a Microsoft Edge extension and want to load it up, or if you already have and now want to remove it, check out the steps below.</span></span>
<span data-ttu-id="1623a-107">また、ブラウザーで拡張機能アイコンの場所を変更する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="1623a-107">Also included are details on how to change your extension icon's location in the browser.</span></span>

## <span data-ttu-id="1623a-108">拡張機能を追加する</span><span class="sxs-lookup"><span data-stu-id="1623a-108">Adding an extension</span></span>

1. <span data-ttu-id="1623a-109">Microsoft Edgeを開き、アドレスバーに 'about:flags' と入力します。</span><span class="sxs-lookup"><span data-stu-id="1623a-109">Open Microsoft Edge and type 'about:flags' into the address bar.</span></span>

2. <span data-ttu-id="1623a-110">[**拡張機能の開発者機能を有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1623a-110">Select the **Enable extension developer features** checkbox.</span></span>

   ![「about:flags」 で開発者機能をオンにする。](./../media/sideload-aboutflags.png)
   > [!NOTE]
   > <span data-ttu-id="1623a-112">Windows 10 Anniversary Update 以降のバージョンをお持ちでない場合は、このオプションはご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="1623a-112">If you don't have the Windows 10 Anniversary Update or later, this option will not be available.</span></span>

3. <span data-ttu-id="1623a-113">メニューを開くには、 **[その他] の (...)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1623a-113">Select **More (...)** to open the menu.</span></span>

   ![[その他] ボタン](./../media/morebutton.png)  

4. <span data-ttu-id="1623a-115">メニューから [**拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1623a-115">Select **Extensions** from the menu.</span></span>

5. <span data-ttu-id="1623a-116">[**拡張機能の読み込み**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1623a-116">Select the **Load extension** button.</span></span>

   ![読み込む拡張機能の選択](./../media/sideload-load-extension.png)

6. <span data-ttu-id="1623a-118">拡張機能のフォルダーに移動し、[**フォルダーの選択**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1623a-118">Navigate to your extension's folder and select the  **Select folder** button.</span></span>
   ![読み込む拡張機能フォルダーを選択する](./../media/sideload-select-extension.png)
   > [!NOTE]
   > <span data-ttu-id="1623a-120">拡張機能の読み込み中にエラーメッセージが表示される場合は、「[トラブルシューティング](./../troubleshooting.md)」 のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1623a-120">If you encounter an error message when loading your extension, refer to the [troubleshooting](./../troubleshooting.md) page for guidance.</span></span>


**<span data-ttu-id="1623a-121">準備が完了しました。</span><span class="sxs-lookup"><span data-stu-id="1623a-121">You're all set!</span></span> <span data-ttu-id="1623a-122">拡張機能が Microsoft Edge の拡張機能ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1623a-122">You should now see the extension listed in Microsoft Edge's extension pane.</span></span>**

![拡張機能ウィンドウの拡張機能](./../media/sideload-extension-installed.png)

> [!NOTE]
> <span data-ttu-id="1623a-124">未署名の拡張機能は、その後の Microsoft Edge の起動時に自動的にオフになります。</span><span class="sxs-lookup"><span data-stu-id="1623a-124">Unsigned extensions are automatically turned off on subsequent launches of Microsoft Edge.</span></span> <span data-ttu-id="1623a-125">ブラウザーがアイドル状態になると (約10秒間動作しなくなったとき)、次の通知がウィンドウの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1623a-125">When the browser enters an idle state (after approximately 10 seconds of inactivity) you will see the following notification at the bottom of the window.</span></span> ![<span data-ttu-id="1623a-126">危険な通知](./../media/riskynotification.png) 署名されていない拡張機能をオンにするには、[設定を有効にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1623a-126">risky notification](./../media/riskynotification.png) To turn on the unsigned extensions, click "Turn on anyway".</span></span>



## <span data-ttu-id="1623a-127">[拡張機能] ボタンの移動</span><span class="sxs-lookup"><span data-stu-id="1623a-127">Moving the extension button</span></span>
<span data-ttu-id="1623a-128">拡張機能の設定によっては、**[その他] の (...)** メニューに表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1623a-128">Depending on your extension's settings, it could appear in the **More (...)** menu.</span></span>

   ![[アクション] メニュー](./../media/browseraction.png)  


<span data-ttu-id="1623a-130">簡単にアクセスできるように、このメニューからボタンを移動する場合:</span><span class="sxs-lookup"><span data-stu-id="1623a-130">If you want to move the button out of this menu for easier access:</span></span>

1. <span data-ttu-id="1623a-131">[拡張機能] ボタンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="1623a-131">Right-click the extension button.</span></span>

2. <span data-ttu-id="1623a-132">「**アドレス バーの隣にボタンを表示**」 を選択します。</span><span class="sxs-lookup"><span data-stu-id="1623a-132">Select **Show button next to address bar**.</span></span>

   ![[アクション] メニュー](./../media/browseraction_contextmenu.png)  

<span data-ttu-id="1623a-134">または、[拡張機能の詳細] ページで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1623a-134">Alternatively, you may do this from the extensions details page:</span></span>

1. <span data-ttu-id="1623a-135">[拡張機能] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1623a-135">Click on the extension button.</span></span>
2. <span data-ttu-id="1623a-136">「**アドレス バーの隣にボタンを表示**」 をオンに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="1623a-136">Toggle **Show button next to address bar** to on.</span></span>

   ![[表示] ボタンをオンに切り替える](./../media/show-button-toggle.png)

> [!NOTE]
> <span data-ttu-id="1623a-138">ボタンを右クリックして 「**アドレスバーの隣に表示**」 の選択を解除するか、拡張機能の詳細ページで 「**アドレス バーの隣にボタンを表示**」 をオフに切り替えることで、いつでも **[その他] (...)** メニューに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="1623a-138">You can always move the button back to the **More (...)** menu by right-clicking it and unselecting **Show next to address bar** or by going to the extension details page and toggling **Show button next to address bar** to off.</span></span>


## <span data-ttu-id="1623a-139">拡張機能を削除する</span><span class="sxs-lookup"><span data-stu-id="1623a-139">Removing an extension</span></span>

1. <span data-ttu-id="1623a-140">Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="1623a-140">Open Microsoft Edge.</span></span>

2. <span data-ttu-id="1623a-141">メニューを開くには、 **[その他] の (...)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1623a-141">Select **More (...)** to open the menu.</span></span>

3. <span data-ttu-id="1623a-142">メニューから [**拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1623a-142">Select **Extensions** from the menu.</span></span>

4. <span data-ttu-id="1623a-143">削除する拡張機能を右クリックし、[**削除**] を選択するか、または拡張機能を選択して、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1623a-143">Right-click the extension you want to remove and select **Remove**, or select the extension and click the **Remove** button.</span></span>

   ![[アクション] メニュー](./../media/remove.png)  

**<span data-ttu-id="1623a-145">拡張機能が Microsoft Edge のリストに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="1623a-145">The extension should disappear from the list in Microsoft Edge.</span></span>**
