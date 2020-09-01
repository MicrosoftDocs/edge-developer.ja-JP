---
title: Microsoft Edge DevTools を使ってローカルストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 72aee823d3a3143ae7399c7057f3b606bd1078c3
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10983521"
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





# <span data-ttu-id="4dea6-103">Microsoft Edge DevTools を使ってローカルストレージを表示および編集する</span><span class="sxs-lookup"><span data-stu-id="4dea6-103">View and edit local storage with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="4dea6-104">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って、 [localstorage][MDNWindowsLocalStorage] のキーと値のペアを表示、編集、削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-104">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [localStorage][MDNWindowsLocalStorage] key-value pairs.</span></span>  

## <span data-ttu-id="4dea6-105">LocalStorage のキーと値の表示</span><span class="sxs-lookup"><span data-stu-id="4dea6-105">View localStorage keys and values</span></span>   

1.  <span data-ttu-id="4dea6-106">[ **アプリケーション** ] タブを選択して、[ **アプリケーション** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4dea6-106">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="4dea6-107">**マニフェスト**ウィンドウは既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dea6-107">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="4dea6-109">**マニフェスト**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="4dea6-109">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4dea6-110">[ **ローカルストレージ** ] メニューを展開します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-110">Expand the **Local Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="[ローカルストレージ] メニュー" lightbox="../media/storage-application-local-storage.msft.png":::
       <span data-ttu-id="4dea6-112">[ **ローカルストレージ** ] メニュー</span><span class="sxs-lookup"><span data-stu-id="4dea6-112">The **Local Storage** menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4dea6-113">ドメインを選択して、キーと値のペアを表示します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-113">Select a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="ドメインのローカルストレージのキーと値のペア https://www.bing.com" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       <span data-ttu-id="4dea6-115">`localStorage`ドメインのキーと値のペア `https://www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="4dea6-115">The `localStorage` key-value pairs for the `https://www.bing.com` domain</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4dea6-116">テーブルの行を選択して、テーブルの下に表示されているビューアーの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-116">Select a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="EventLogQueue_Online キーの値を表示する" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       <span data-ttu-id="4dea6-118">キーの値を表示する `eventLogQueue_Online`</span><span class="sxs-lookup"><span data-stu-id="4dea6-118">View the value of the `eventLogQueue_Online` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="4dea6-119">新しい localStorage キーと値のペアを作成する</span><span class="sxs-lookup"><span data-stu-id="4dea6-119">Create a new localStorage key-value pair</span></span>   

1.  <span data-ttu-id="4dea6-120">[ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-120">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="4dea6-121">表の空の部分をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dea6-121">Double-click the empty part of the table.</span></span>  <span data-ttu-id="4dea6-122">DevTools で新しい行を作成し、 **キー** 列にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="4dea6-122">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       <span data-ttu-id="4dea6-124">新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分</span><span class="sxs-lookup"><span data-stu-id="4dea6-124">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="4dea6-125">ローカルストレージのキーまたは値を編集する</span><span class="sxs-lookup"><span data-stu-id="4dea6-125">Edit localStorage keys or values</span></span>   

1.  <span data-ttu-id="4dea6-126">[ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-126">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="4dea6-127">キーまた**は値の列の**セルをダブルクリックし**て、その**キーまたは値を編集します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-127">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="ローカルストレージキーを編集する" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       <span data-ttu-id="4dea6-129">キーを編集する `localStorage`</span><span class="sxs-lookup"><span data-stu-id="4dea6-129">Edit a `localStorage` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="4dea6-130">LocalStorage のキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="4dea6-130">Delete localStorage key-value pairs</span></span>   

1.  <span data-ttu-id="4dea6-131">[ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-131">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="4dea6-132">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-132">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="4dea6-133">DevTools は、青色を強調表示して、選択されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-133">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="4dea6-134">キーを押す `Delete` か、[ **選択した** ものを削除] をクリックし ![ ます (選択した \ を削除 ][ImageDeleteIcon] )。</span><span class="sxs-lookup"><span data-stu-id="4dea6-134">Press the `Delete` key or click **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="4dea6-135">`localStorage`ドメインのすべてのキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="4dea6-135">Delete all `localStorage` key-value pairs for a domain</span></span>   

1.  <span data-ttu-id="4dea6-136">[ `localStorage` ドメインのキーと値のペアを表示](#view-localstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-136">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="4dea6-137">[ **すべてクリア** ] を選択し ![ ][ImageClearIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="4dea6-137">Select **Clear All** \(![Clear All][ImageClearIcon]\).</span></span>  
    
## <span data-ttu-id="4dea6-138">コンソールからローカルストレージを操作する</span><span class="sxs-lookup"><span data-stu-id="4dea6-138">Interact with localStorage from the Console</span></span>   

<span data-ttu-id="4dea6-139">JavaScript は**本体**で実行できますが、**本体**はページの javascript コンテキストにアクセスできるため、コンソールから操作することもでき `localStorage` ます。 **Console**</span><span class="sxs-lookup"><span data-stu-id="4dea6-139">Since you are able to run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `localStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="4dea6-140">表示さ**JavaScript contexts**れて**Console** `localStorage` いるページ以外のドメインのキーと値のペアにアクセスする場合は、javascript コンテキストメニューを使って本体の javascript コンテキストを変更します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-140">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `localStorage` key-value pairs of a domain other than the page that is displayed.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="本体の JavaScript のコンテキストを変更する" lightbox="../media/storage-console-local-storage.msft.png":::
       <span data-ttu-id="4dea6-142">本体の JavaScript のコンテキストを変更する</span><span class="sxs-lookup"><span data-stu-id="4dea6-142">Change the JavaScript context of the Console</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4dea6-143">`localStorage`JavaScript と同じように、コンソールで式を実行します。</span><span class="sxs-lookup"><span data-stu-id="4dea6-143">Run your `localStorage` expressions in the Console, the same as you do in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="コンソールからローカルストレージを操作する" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       <span data-ttu-id="4dea6-145">`localStorage`**コンソール**から操作する</span><span class="sxs-lookup"><span data-stu-id="4dea6-145">Interact with `localStorage` from the **Console**</span></span>  
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
> <span data-ttu-id="4dea6-148">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="4dea6-148">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4dea6-149">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="4dea6-149">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="4dea6-151">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="4dea6-151">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
