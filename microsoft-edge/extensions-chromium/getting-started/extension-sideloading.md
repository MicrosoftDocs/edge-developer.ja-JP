---
description: ブラウザーで拡張機能をサイドローディングしてテストする
title: 内線番号をサイドローディング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: 7070878b9608e6d239179078390f2315e0b289a1
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104775"
---
# <span data-ttu-id="50e89-104">内線番号をサイドローディングする</span><span class="sxs-lookup"><span data-stu-id="50e89-104">Sideload an extension</span></span>

<span data-ttu-id="50e89-105">開発時には、Microsoft Edge \ (Chromium \) ブラウザーを使って、拡張機能を安全に実行してデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="50e89-105">During development, you may use the Microsoft Edge \(Chromium\) browser to run and debug your extension safely.</span></span> <span data-ttu-id="50e89-106">ブラウザーで拡張機能をローカルにサイドローディングすることで、拡張機能を実行してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="50e89-106">By sideloading your extension locally in your browser, you can run and test your extension.</span></span> <span data-ttu-id="50e89-107">この記事では、Microsoft Edge に拡張機能をサイドローディングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50e89-107">This article explains how to sideload extensions into Microsoft Edge.</span></span>

<span data-ttu-id="50e89-108">内線番号をサイドローディングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="50e89-108">To sideload your extension, follow these steps.</span></span>

1.  <span data-ttu-id="50e89-109">`edge://extensions`ブラウザーの上部にある3つの点を選んで、[**拡張機能**] を選択してページを開きます。</span><span class="sxs-lookup"><span data-stu-id="50e89-109">Open the `edge://extensions` page by choosing the three dots at the top of your browser, and then selecting **Extensions**.</span></span>

       :::image type="complex" source="./media/part1-threedots.png" alt-text="[Edge://extensions] ページを開く":::
          <span data-ttu-id="50e89-111">[Edge://extensions] ページを開く</span><span class="sxs-lookup"><span data-stu-id="50e89-111">Open the edge://extensions page</span></span> :::image-end:::

1.  <span data-ttu-id="50e89-112">[拡張機能の管理] ページで `edge://extensions` 、ページの左下にあるトグルを使用して **開発者モード** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="50e89-112">On the extension management page at `edge://extensions`, turn on **Developer mode** using the toggle at the bottom left of the page.</span></span>

       :::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="[Edge://extensions] ページを開く":::
          <span data-ttu-id="50e89-114">開発者モードを有効にする</span><span class="sxs-lookup"><span data-stu-id="50e89-114">Turn on Developer Mode</span></span> :::image-end:::

1.  <span data-ttu-id="50e89-115">拡張機能を初めてインストールする場合は、[解凍された **読み込み**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="50e89-115">When installing your extension for the first time, choose **Load Unpacked**.</span></span>  <span data-ttu-id="50e89-116">拡張機能のソースファイルを含むディレクトリの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="50e89-116">You'll be prompted for the directory with your extension source files.</span></span>  <span data-ttu-id="50e89-117">拡張子は、ストアからインストールされた拡張機能と同様に、ブラウザーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="50e89-117">Your extension is installed in your browser, similar to extensions installed from the store.</span></span>  

       :::image type="complex" source="./media/part1-installed-extension.png" alt-text="[Edge://extensions] ページを開く":::
          <span data-ttu-id="50e89-119">サイドローディング拡張機能が表示されている [インストールされた拡張機能] ページ</span><span class="sxs-lookup"><span data-stu-id="50e89-119">Installed extensions page showing a sideloaded extension</span></span> :::image-end:::

<span data-ttu-id="50e89-120">開発中に、次のタスクを実行することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="50e89-120">During development, you may also need to perform the following tasks.</span></span>
* <span data-ttu-id="50e89-121">拡張機能を更新します。</span><span class="sxs-lookup"><span data-stu-id="50e89-121">Update the extension.</span></span> <span data-ttu-id="50e89-122">に移動し `edge://extensions` 、[ **再読み込み** ] を選択して拡張機能を更新します。</span><span class="sxs-lookup"><span data-stu-id="50e89-122">Navigate to `edge://extensions`, and then select **Reload** to update your extension.</span></span>  
* <span data-ttu-id="50e89-123">ブラウザーから拡張機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="50e89-123">Remove the extension from your browser.</span></span> <span data-ttu-id="50e89-124">に移動して `edge://extensions` 、拡張機能を選択し `Remove` ます。</span><span class="sxs-lookup"><span data-stu-id="50e89-124">Navigate to `edge://extensions`, and then select `Remove` on your extension.</span></span>