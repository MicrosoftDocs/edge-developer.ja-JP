---
description: ローカルストレージウィンドウと本体で localStorage を表示および編集する方法を説明します。
title: Microsoft Edge DevTools を使ってローカルストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: aa5365d1764ea0db537ea24464f9c76441f05322
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993556"
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





# <span data-ttu-id="76c85-104">Microsoft Edge DevTools を使ってローカルストレージを表示および編集する</span><span class="sxs-lookup"><span data-stu-id="76c85-104">View and edit local storage with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="76c85-105">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って、 [localstorage][MDNWindowsLocalStorage] のキーと値のペアを表示、編集、削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="76c85-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [localStorage][MDNWindowsLocalStorage] key-value pairs.</span></span>  

## <span data-ttu-id="76c85-106">LocalStorage のキーと値の表示</span><span class="sxs-lookup"><span data-stu-id="76c85-106">View localStorage keys and values</span></span>   

1.  <span data-ttu-id="76c85-107">[ **アプリケーション** ] タブを選択して、[ **アプリケーション** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="76c85-107">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="76c85-108">**マニフェスト**ウィンドウは既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="76c85-108">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="76c85-110">**マニフェスト**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="76c85-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="76c85-111">[ **ローカルストレージ** ] メニューを展開します。</span><span class="sxs-lookup"><span data-stu-id="76c85-111">Expand the **Local Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="[ローカルストレージ] メニュー" lightbox="../media/storage-application-local-storage.msft.png":::
       <span data-ttu-id="76c85-113">[ **ローカルストレージ** ] メニュー</span><span class="sxs-lookup"><span data-stu-id="76c85-113">The **Local Storage** menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="76c85-114">ドメインを選択して、キーと値のペアを表示します。</span><span class="sxs-lookup"><span data-stu-id="76c85-114">Select a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="ドメインのローカルストレージのキーと値のペア https://www.bing.com" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       <span data-ttu-id="76c85-116">`localStorage`ドメインのキーと値のペア `https://www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="76c85-116">The `localStorage` key-value pairs for the `https://www.bing.com` domain</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="76c85-117">テーブルの行を選択して、テーブルの下に表示されているビューアーの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="76c85-117">Select a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="EventLogQueue_Online キーの値を表示する" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       <span data-ttu-id="76c85-119">キーの値を表示する `eventLogQueue_Online`</span><span class="sxs-lookup"><span data-stu-id="76c85-119">View the value of the `eventLogQueue_Online` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="76c85-120">新しい localStorage キーと値のペアを作成する</span><span class="sxs-lookup"><span data-stu-id="76c85-120">Create a new localStorage key-value pair</span></span>   

1.  <span data-ttu-id="76c85-121">[ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="76c85-121">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="76c85-122">表の空の部分をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="76c85-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="76c85-123">DevTools で新しい行を作成し、 **キー** 列にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="76c85-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       <span data-ttu-id="76c85-125">新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分</span><span class="sxs-lookup"><span data-stu-id="76c85-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="76c85-126">ローカルストレージのキーまたは値を編集する</span><span class="sxs-lookup"><span data-stu-id="76c85-126">Edit localStorage keys or values</span></span>   

1.  <span data-ttu-id="76c85-127">[ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="76c85-127">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="76c85-128">キーまた**は値の列の**セルをダブルクリックし**て、その**キーまたは値を編集します。</span><span class="sxs-lookup"><span data-stu-id="76c85-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="ローカルストレージキーを編集する" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       <span data-ttu-id="76c85-130">キーを編集する `localStorage`</span><span class="sxs-lookup"><span data-stu-id="76c85-130">Edit a `localStorage` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="76c85-131">LocalStorage のキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="76c85-131">Delete localStorage key-value pairs</span></span>   

1.  <span data-ttu-id="76c85-132">[ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="76c85-132">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="76c85-133">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="76c85-133">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="76c85-134">DevTools は、青色を強調表示して、選択されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="76c85-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="76c85-135">キーを押す `Delete` か、[ **選択した** ものを削除] をクリックし ![ ます (選択した \ を削除 ][ImageDeleteIcon] )。</span><span class="sxs-lookup"><span data-stu-id="76c85-135">Press the `Delete` key or click **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="76c85-136">`localStorage`ドメインのすべてのキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="76c85-136">Delete all `localStorage` key-value pairs for a domain</span></span>   

1.  <span data-ttu-id="76c85-137">[ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="76c85-137">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="76c85-138">[ **すべてクリア** ] を選択し ![ ][ImageClearIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="76c85-138">Select **Clear All** \(![Clear All][ImageClearIcon]\).</span></span>  
    
## <span data-ttu-id="76c85-139">コンソールからローカルストレージを操作する</span><span class="sxs-lookup"><span data-stu-id="76c85-139">Interact with localStorage from the Console</span></span>   

<span data-ttu-id="76c85-140">JavaScript は**本体**で実行できますが、**本体**はページの javascript コンテキストにアクセスできるため、コンソールから操作することもでき `localStorage` ます。 **Console**</span><span class="sxs-lookup"><span data-stu-id="76c85-140">Since you are able to run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `localStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="76c85-141">表示さ**JavaScript contexts**れて**Console** `localStorage` いるページ以外のドメインのキーと値のペアにアクセスする場合は、javascript コンテキストメニューを使って本体の javascript コンテキストを変更します。</span><span class="sxs-lookup"><span data-stu-id="76c85-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `localStorage` key-value pairs of a domain other than the page that is displayed.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="本体の JavaScript のコンテキストを変更する" lightbox="../media/storage-console-local-storage.msft.png":::
       <span data-ttu-id="76c85-143">本体の JavaScript のコンテキストを変更する</span><span class="sxs-lookup"><span data-stu-id="76c85-143">Change the JavaScript context of the Console</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="76c85-144">`localStorage`JavaScript と同じように、コンソールで式を実行します。</span><span class="sxs-lookup"><span data-stu-id="76c85-144">Run your `localStorage` expressions in the Console, the same as you do in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="コンソールからローカルストレージを操作する" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       <span data-ttu-id="76c85-146">`localStorage`**コンソール**から操作する</span><span class="sxs-lookup"><span data-stu-id="76c85-146">Interact with `localStorage` from the **Console**</span></span>  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "ウィンドウ。 localStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="76c85-149">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="76c85-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="76c85-150">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="76c85-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="76c85-152">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="76c85-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
