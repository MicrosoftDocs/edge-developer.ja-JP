---
description: '[ローカル] ウィンドウと [コンソール] を使用して localStorage Storage編集する方法。'
title: DevTools を使用してローカル Storageを表示Microsoft Edge編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5088a1b9d7ab2b92051d099e76b8b07bbd5db5f8
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565051"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="view-and-edit-local-storage-with-microsoft-edge-devtools"></a><span data-ttu-id="c5cd8-104">DevTools を使用してローカル ストレージを表示Microsoft Edge編集する</span><span class="sxs-lookup"><span data-stu-id="c5cd8-104">View and edit local storage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="c5cd8-105">このガイドでは[、devTools][MicrosoftEdgeDevTools]のMicrosoft Edgeを使用して[localStorage][MDNWindowsLocalStorage]のキーと値のペアを表示、編集、および削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [localStorage][MDNWindowsLocalStorage] key-value pairs.</span></span>  

## <a name="view-localstorage-keys-and-values"></a><span data-ttu-id="c5cd8-106">localStorage キーと値の表示</span><span class="sxs-lookup"><span data-stu-id="c5cd8-106">View localStorage keys and values</span></span>  

1.  <span data-ttu-id="c5cd8-107">[アプリケーション] **タブを** 選択して、[アプリケーション] ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-107">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="c5cd8-108">既定 **では、[マニフェスト** ] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-108">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="c5cd8-110">[ **マニフェスト]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="c5cd8-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c5cd8-111">[ローカル]**メニュー Storage**展開します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-111">Expand the **Local Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="[ローカル] Storageメニュー" lightbox="../media/storage-application-local-storage.msft.png":::
       <span data-ttu-id="c5cd8-113">[**ローカル] Storage**メニュー</span><span class="sxs-lookup"><span data-stu-id="c5cd8-113">The **Local Storage** menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c5cd8-114">キーと値のペアを表示するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-114">Choose a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="ドメインの localStorage キーと値の https://www.bing.com ペア" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       <span data-ttu-id="c5cd8-116">ドメイン `localStorage` のキーと値のペア `https://www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="c5cd8-116">The `localStorage` key-value pairs for the `https://www.bing.com` domain</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c5cd8-117">テーブルの行を選択して、テーブルの下のビューアーで値を表示します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-117">Choose a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="キーの値をeventLogQueue_Onlineする" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       <span data-ttu-id="c5cd8-119">キーの値を表示 `eventLogQueue_Online` する</span><span class="sxs-lookup"><span data-stu-id="c5cd8-119">View the value of the `eventLogQueue_Online` key</span></span>  
    :::image-end:::  
    
## <a name="create-a-new-localstorage-key-value-pair"></a><span data-ttu-id="c5cd8-120">新しい localStorage キーと値のペアを作成する</span><span class="sxs-lookup"><span data-stu-id="c5cd8-120">Create a new localStorage key-value pair</span></span>  

1.  <span data-ttu-id="c5cd8-121">[ドメインの localStorage キーと値のペアを表示します](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-121">[View the localStorage key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="c5cd8-122">テーブルの空の部分をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="c5cd8-123">DevTools は新しい行を作成し、[キー] 列にカーソルを **移動** します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       <span data-ttu-id="c5cd8-125">新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分</span><span class="sxs-lookup"><span data-stu-id="c5cd8-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <a name="edit-localstorage-keys-or-values"></a><span data-ttu-id="c5cd8-126">localStorage キーまたは値の編集</span><span class="sxs-lookup"><span data-stu-id="c5cd8-126">Edit localStorage keys or values</span></span>  

1.  <span data-ttu-id="c5cd8-127">[ドメインの localStorage キーと値のペアを表示します](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-127">[View the localStorage key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="c5cd8-128">[キー] 列または [値] 列の**セル\*\*\*\*をダブルクリック**して、そのキーまたは値を編集します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="localStorage キーの編集" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       <span data-ttu-id="c5cd8-130">キーの `localStorage` 編集</span><span class="sxs-lookup"><span data-stu-id="c5cd8-130">Edit a `localStorage` key</span></span>  
    :::image-end:::  
    
## <a name="delete-localstorage-key-value-pairs"></a><span data-ttu-id="c5cd8-131">localStorage キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="c5cd8-131">Delete localStorage key-value pairs</span></span>  

1.  <span data-ttu-id="c5cd8-132">[ドメインの `localStorage` キーと値のペアを表示します](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-132">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="c5cd8-133">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-133">Choose the key-value pair that you want to delete.</span></span>  <span data-ttu-id="c5cd8-134">DevTools は青色で強調表示され、選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="c5cd8-135">キーを `Delete` 選択するか、[ **選択した \(** Delete ![ Selected \) を削除する] ](../media/delete-icon.msft.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-135">Select the `Delete` key or choose **Delete Selected** \(![Delete Selected](../media/delete-icon.msft.png)\).</span></span>  
    
## <a name="delete-all-localstorage-key-value-pairs-for-a-domain"></a><span data-ttu-id="c5cd8-136">ドメインのすべての `localStorage` キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="c5cd8-136">Delete all `localStorage` key-value pairs for a domain</span></span>  

1.  <span data-ttu-id="c5cd8-137">[ドメインの `localStorage` キーと値のペアを表示します](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-137">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="c5cd8-138">[ **すべてクリア]** \( ![ Clear All ](../media/clear-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-138">Choose **Clear All** \(![Clear All](../media/clear-icon.msft.png)\).</span></span>  
    
## <a name="interact-with-localstorage-from-the-console"></a><span data-ttu-id="c5cd8-139">コンソールから localStorage を操作する</span><span class="sxs-lookup"><span data-stu-id="c5cd8-139">Interact with localStorage from the Console</span></span>  

<span data-ttu-id="c5cd8-140">コンソールで JavaScript を実行できます。\*\*\*\* また、コンソールはページ\*\*\*\* の JavaScript コンテキストにアクセスできますので、コンソールから操作 `localStorage` **できます**。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-140">Since you are able to run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `localStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="c5cd8-141">表示される**ページ以外の**ドメインのキーと値のペアにアクセスする\*\*\*\* 場合は、JavaScript コンテキスト メニューを使用してコンソールの JavaScript コンテキストを `localStorage` 変更します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `localStorage` key-value pairs of a domain other than the page that is displayed.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="コンソールの JavaScript コンテキストを変更する" lightbox="../media/storage-console-local-storage.msft.png":::
       <span data-ttu-id="c5cd8-143">コンソールの JavaScript コンテキストを変更する</span><span class="sxs-lookup"><span data-stu-id="c5cd8-143">Change the JavaScript context of the Console</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c5cd8-144">JavaScript と同じように、コンソールで式 `localStorage` を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-144">Run your `localStorage` expressions in the Console, the same as you do in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="コンソールから localStorage を操作する" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       <span data-ttu-id="c5cd8-146">コンソールからの `localStorage` **操作**</span><span class="sxs-lookup"><span data-stu-id="c5cd8-146">Interact with `localStorage` from the **Console**</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c5cd8-147">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c5cd8-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "Window.localStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="c5cd8-150">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c5cd8-151">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c5cd8-153">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c5cd8-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
