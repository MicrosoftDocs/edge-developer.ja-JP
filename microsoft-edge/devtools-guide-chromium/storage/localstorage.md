---
description: ローカル ストレージ ウィンドウとコンソールを使用して localStorage を表示および編集する方法について説明します。
title: Microsoft Edge DevTools を使ったローカル ストレージの表示と編集
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c68f11b8ba2c10a0792f10acf5c5ededf2ad8e8d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231189"
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

# <span data-ttu-id="7a091-104">Microsoft Edge DevTools を使用してローカル ストレージを表示および編集する</span><span class="sxs-lookup"><span data-stu-id="7a091-104">View and edit local storage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="7a091-105">このガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使用して [localStorage][MDNWindowsLocalStorage] キーと値のペアを表示、編集、削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a091-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [localStorage][MDNWindowsLocalStorage] key-value pairs.</span></span>  

## <span data-ttu-id="7a091-106">localStorage キーと値を表示する</span><span class="sxs-lookup"><span data-stu-id="7a091-106">View localStorage keys and values</span></span>  

1.  <span data-ttu-id="7a091-107">[アプリケーション **] タブ** を選択して、アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="7a091-107">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="7a091-108">マニフェスト **ウィンドウ** は既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a091-108">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="7a091-110">マニフェスト**ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="7a091-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="7a091-111">[ローカル ストレージ **] メニューを展開** します。</span><span class="sxs-lookup"><span data-stu-id="7a091-111">Expand the **Local Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="[ローカル ストレージ] メニュー" lightbox="../media/storage-application-local-storage.msft.png":::
       <span data-ttu-id="7a091-113">[ **ローカル ストレージ]** メニュー</span><span class="sxs-lookup"><span data-stu-id="7a091-113">The **Local Storage** menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="7a091-114">キーと値のペアを表示するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a091-114">Choose a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="ドメインの localStorage キーと値の https://www.bing.com ペア" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       <span data-ttu-id="7a091-116">ドメイン `localStorage` のキーと値の `https://www.bing.com` ペア</span><span class="sxs-lookup"><span data-stu-id="7a091-116">The `localStorage` key-value pairs for the `https://www.bing.com` domain</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="7a091-117">テーブルの行を選択して、テーブルの下のビューアーに値を表示します。</span><span class="sxs-lookup"><span data-stu-id="7a091-117">Choose a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="キーの値をeventLogQueue_Onlineする" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       <span data-ttu-id="7a091-119">キーの値を表示 `eventLogQueue_Online` する</span><span class="sxs-lookup"><span data-stu-id="7a091-119">View the value of the `eventLogQueue_Online` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="7a091-120">新しい localStorage キーと値のペアを作成する</span><span class="sxs-lookup"><span data-stu-id="7a091-120">Create a new localStorage key-value pair</span></span>  

1.  <span data-ttu-id="7a091-121">[ドメインの localStorage キーと値のペアを表示します](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="7a091-121">[View the localStorage key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="7a091-122">テーブルの空の部分をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a091-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="7a091-123">DevTools によって新しい行が作成され、カーソルが [キー] 列に **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="7a091-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       <span data-ttu-id="7a091-125">新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分</span><span class="sxs-lookup"><span data-stu-id="7a091-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="7a091-126">localStorage キーまたは値を編集する</span><span class="sxs-lookup"><span data-stu-id="7a091-126">Edit localStorage keys or values</span></span>  

1.  <span data-ttu-id="7a091-127">[ドメインの localStorage キーと値のペアを表示します](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="7a091-127">[View the localStorage key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="7a091-128">[キー] 列または\*\*\*\*[値] 列のセルを**ダブルクリック**して、そのキーまたは値を編集します。</span><span class="sxs-lookup"><span data-stu-id="7a091-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="localStorage キーを編集する" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       <span data-ttu-id="7a091-130">キーを編集 `localStorage` する</span><span class="sxs-lookup"><span data-stu-id="7a091-130">Edit a `localStorage` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="7a091-131">localStorage のキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="7a091-131">Delete localStorage key-value pairs</span></span>  

1.  <span data-ttu-id="7a091-132">[ドメインの `localStorage` キーと値のペアを表示します](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="7a091-132">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="7a091-133">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a091-133">Choose the key-value pair that you want to delete.</span></span>  <span data-ttu-id="7a091-134">DevTools では、青色が強調表示され、選択されている状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="7a091-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="7a091-135">Select the `Delete` key or choose Delete **Selected** \( ![ Delete Selected ][ImageDeleteIcon] \).</span><span class="sxs-lookup"><span data-stu-id="7a091-135">Select the `Delete` key or choose **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="7a091-136">ドメインのすべての `localStorage` キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="7a091-136">Delete all `localStorage` key-value pairs for a domain</span></span>  

1.  <span data-ttu-id="7a091-137">[ドメインの `localStorage` キーと値のペアを表示します](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="7a091-137">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="7a091-138">Choose **Clear All** \( Clear All ![ ][ImageClearIcon] \).</span><span class="sxs-lookup"><span data-stu-id="7a091-138">Choose **Clear All** \(![Clear All][ImageClearIcon]\).</span></span>  
    
## <span data-ttu-id="7a091-139">コンソールから localStorage を操作する</span><span class="sxs-lookup"><span data-stu-id="7a091-139">Interact with localStorage from the Console</span></span>  

<span data-ttu-id="7a091-140">コンソールで JavaScript を実行できます。\*\*\*\* また、コンソールはページ\*\*\*\* の JavaScript コンテキストにアクセスできるので、コンソールから操作 `localStorage` **できます**。</span><span class="sxs-lookup"><span data-stu-id="7a091-140">Since you are able to run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `localStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="7a091-141">表示される**ページ以外**のドメインのキーと値のペアにアクセスする\*\*\*\* 場合は、JavaScript コンテキスト メニューを使用してコンソールの JavaScript コンテキストを `localStorage` 変更します。</span><span class="sxs-lookup"><span data-stu-id="7a091-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `localStorage` key-value pairs of a domain other than the page that is displayed.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="コンソールの JavaScript コンテキストを変更する" lightbox="../media/storage-console-local-storage.msft.png":::
       <span data-ttu-id="7a091-143">コンソールの JavaScript コンテキストを変更する</span><span class="sxs-lookup"><span data-stu-id="7a091-143">Change the JavaScript context of the Console</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="7a091-144">JavaScript `localStorage` と同じように、コンソールで式を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a091-144">Run your `localStorage` expressions in the Console, the same as you do in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="コンソールから localStorage を操作する" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       <span data-ttu-id="7a091-146">コンソールから `localStorage` 操作 **する**</span><span class="sxs-lookup"><span data-stu-id="7a091-146">Interact with `localStorage` from the **Console**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="7a091-147">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="7a091-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "Window.localStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="7a091-150">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a091-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7a091-151">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="7a091-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="7a091-153">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="7a091-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
