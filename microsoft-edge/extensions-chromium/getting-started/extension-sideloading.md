---
description: ブラウザーで拡張機能をサイドローディングしてテストする
title: 拡張機能をサイドロードする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, Web 開発, html, css, javascript, developer, extensions
ms.openlocfilehash: 7070878b9608e6d239179078390f2315e0b289a1
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104775"
---
# <span data-ttu-id="da7ab-104">拡張機能をサイドロードする</span><span class="sxs-lookup"><span data-stu-id="da7ab-104">Sideload an extension</span></span>

<span data-ttu-id="da7ab-105">開発中に、Microsoft Edge \(Chromium\) ブラウザーを使用して、拡張機能を安全に実行およびデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="da7ab-105">During development, you may use the Microsoft Edge \(Chromium\) browser to run and debug your extension safely.</span></span> <span data-ttu-id="da7ab-106">ブラウザーで拡張機能をローカルにサイドロードすることで、拡張機能を実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="da7ab-106">By sideloading your extension locally in your browser, you can run and test your extension.</span></span> <span data-ttu-id="da7ab-107">この記事では、拡張機能をサイドロードする方法について説明Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="da7ab-107">This article explains how to sideload extensions into Microsoft Edge.</span></span>

<span data-ttu-id="da7ab-108">拡張機能をサイドロードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="da7ab-108">To sideload your extension, follow these steps.</span></span>

1.  <span data-ttu-id="da7ab-109">ブラウザーの上部にある 3 つのドットを選択し、[拡張機能] を選択してページ `edge://extensions` **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="da7ab-109">Open the `edge://extensions` page by choosing the three dots at the top of your browser, and then selecting **Extensions**.</span></span>

       :::image type="complex" source="./media/part1-threedots.png" alt-text="[ページ] edge://extensions 開く":::
          <span data-ttu-id="da7ab-111">[ページ] edge://extensions 開く</span><span class="sxs-lookup"><span data-stu-id="da7ab-111">Open the edge://extensions page</span></span> :::image-end:::

1.  <span data-ttu-id="da7ab-112">[拡張機能の管理] ページで、ページの左下にあるトグルを使用して開発者 `edge://extensions` モードを有効にします。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="da7ab-112">On the extension management page at `edge://extensions`, turn on **Developer mode** using the toggle at the bottom left of the page.</span></span>

       :::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="開発者モードを有効にする":::
          <span data-ttu-id="da7ab-114">開発者モードを有効にする</span><span class="sxs-lookup"><span data-stu-id="da7ab-114">Turn on Developer Mode</span></span> :::image-end:::

1.  <span data-ttu-id="da7ab-115">拡張機能を初めてインストールする場合は、[アンパックの読み込 **み] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="da7ab-115">When installing your extension for the first time, choose **Load Unpacked**.</span></span>  <span data-ttu-id="da7ab-116">拡張ソース ファイルを含むディレクトリの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da7ab-116">You'll be prompted for the directory with your extension source files.</span></span>  <span data-ttu-id="da7ab-117">拡張機能は、ストアからインストールされた拡張機能と同様に、ブラウザーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="da7ab-117">Your extension is installed in your browser, similar to extensions installed from the store.</span></span>  

       :::image type="complex" source="./media/part1-installed-extension.png" alt-text="サイドロードされた拡張機能を示すインストール済み拡張機能ページ":::
          <span data-ttu-id="da7ab-119">サイドロードされた拡張機能を示すインストール済み拡張機能ページ</span><span class="sxs-lookup"><span data-stu-id="da7ab-119">Installed extensions page showing a sideloaded extension</span></span> :::image-end:::

<span data-ttu-id="da7ab-120">開発中に、次のタスクを実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="da7ab-120">During development, you may also need to perform the following tasks.</span></span>
* <span data-ttu-id="da7ab-121">拡張機能を更新します。</span><span class="sxs-lookup"><span data-stu-id="da7ab-121">Update the extension.</span></span> <span data-ttu-id="da7ab-122">に移動し `edge://extensions` 、[再読み込み] **を選択** して拡張機能を更新します。</span><span class="sxs-lookup"><span data-stu-id="da7ab-122">Navigate to `edge://extensions`, and then select **Reload** to update your extension.</span></span>  
* <span data-ttu-id="da7ab-123">ブラウザーから拡張機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="da7ab-123">Remove the extension from your browser.</span></span> <span data-ttu-id="da7ab-124">に移動 `edge://extensions` し、拡張機能 `Remove` を選択します。</span><span class="sxs-lookup"><span data-stu-id="da7ab-124">Navigate to `edge://extensions`, and then select `Remove` on your extension.</span></span>