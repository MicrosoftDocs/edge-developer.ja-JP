---
description: セッション記憶域のウィンドウと本体を使って、sessionStorage の表示と編集を行う方法について説明します。
title: Microsoft Edge DevTools を使ってセッションストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 24fca3fd3a068f3b2ffbe4ec1c23e6b80b968953
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993549"
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





# <span data-ttu-id="a2f48-104">Microsoft Edge DevTools を使ってセッションストレージを表示および編集する</span><span class="sxs-lookup"><span data-stu-id="a2f48-104">View and edit Session Storage with Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="a2f48-105">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って、キーと値のペアを表示、編集、削除する方法について説明し [`sessionStorage`][MDNSessionStorage] ます。</span><span class="sxs-lookup"><span data-stu-id="a2f48-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [`sessionStorage`][MDNSessionStorage] key-value pairs.</span></span>  

## <span data-ttu-id="a2f48-106">SessionStorage のキーと値の表示</span><span class="sxs-lookup"><span data-stu-id="a2f48-106">View sessionStorage keys and values</span></span>   

1.  <span data-ttu-id="a2f48-107">[ **アプリケーション** ] タブを選択して、[ **アプリケーション** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a2f48-107">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="a2f48-108">**マニフェスト**ウィンドウは既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2f48-108">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="a2f48-110">**マニフェスト**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a2f48-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a2f48-111">[ **セッションストレージ** ] メニューを展開します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-111">Expand the **Session Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage.msft.png" alt-text="[セッション記憶域] メニュー" lightbox="../media/storage-application-storage-session-storage.msft.png":::
       <span data-ttu-id="a2f48-113">[ **セッション記憶域** ] メニュー</span><span class="sxs-lookup"><span data-stu-id="a2f48-113">The **Session Storage** Menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a2f48-114">ドメインを選択して、キーと値のペアを表示します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-114">Select a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain.msft.png" alt-text=""SessionStorage" キーと値のペア" lightbox="../media/storage-application-storage-session-storage-domain.msft.png":::
       <span data-ttu-id="a2f48-116">`sessionStorage`キーと値のペア</span><span class="sxs-lookup"><span data-stu-id="a2f48-116">The `sessionStorage` key-value pairs</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a2f48-117">テーブルの行を選択して、テーブルの下に表示されているビューアーの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-117">Select a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png" alt-text="X sid キーの値を表示する" lightbox="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png":::
       <span data-ttu-id="a2f48-119">キーの値を表示する `x-sid`</span><span class="sxs-lookup"><span data-stu-id="a2f48-119">View the value of the `x-sid` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a2f48-120">新しい sessionStorage のキーと値のペアを作成する</span><span class="sxs-lookup"><span data-stu-id="a2f48-120">Create a new sessionStorage key-value pair</span></span>   

1.  <span data-ttu-id="a2f48-121">[ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-121">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="a2f48-122">表の空の部分をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2f48-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="a2f48-123">DevTools で新しい行を作成し、 **キー** 列にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="a2f48-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png":::
       <span data-ttu-id="a2f48-125">新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分</span><span class="sxs-lookup"><span data-stu-id="a2f48-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a2f48-126">SessionStorage のキーまたは値を編集する</span><span class="sxs-lookup"><span data-stu-id="a2f48-126">Edit sessionStorage keys or values</span></span>   

1.  <span data-ttu-id="a2f48-127">[ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-127">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="a2f48-128">キーまた**は値の列の**セルをダブルクリックし**て、その**キーまたは値を編集します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png" alt-text="セッションストレージキーを編集する" lightbox="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png":::
       <span data-ttu-id="a2f48-130">キーを編集する `sessionStorage`</span><span class="sxs-lookup"><span data-stu-id="a2f48-130">Edit a `sessionStorage` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a2f48-131">セッションストレージのキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="a2f48-131">Delete sessionStorage key-value pairs</span></span>   

1.  <span data-ttu-id="a2f48-132">[ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-132">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="a2f48-133">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-133">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="a2f48-134">DevTools は、青色を強調表示して、選択されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="a2f48-135">キーを押す `Delete` か、[ **選択した** ものを削除] をクリックし ![ ます (選択した \ を削除 ][ImageDeleteIcon] )。</span><span class="sxs-lookup"><span data-stu-id="a2f48-135">Press the `Delete` key or click **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="a2f48-136">ドメインのすべてのセッション記憶域のキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="a2f48-136">Delete all sessionStorage key-value pairs for a domain</span></span>   

1.  <span data-ttu-id="a2f48-137">[ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-137">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="a2f48-138">[ **すべてクリア** ] を選択し ![ ][ImageClearIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="a2f48-138">Select **Clear All** \(![Clear All][ImageClearIcon]\).</span></span>  
    
## <span data-ttu-id="a2f48-139">コンソールからセッションストレージを操作する</span><span class="sxs-lookup"><span data-stu-id="a2f48-139">Interact with sessionStorage from the Console</span></span>   

<span data-ttu-id="a2f48-140">JavaScript は**本体**で実行できるため、**本体**はページの javascript コンテキストにアクセスできるため、コンソールから操作することができ `sessionStorage` ます。 **Console**</span><span class="sxs-lookup"><span data-stu-id="a2f48-140">Since you can run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `sessionStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="a2f48-141">使用しているページ以外のドメインのキーと値のペアにアクセスする場合は、 **javascript のコンテキスト** メニューを使って **本体** の javascript コンテキストを変更し `sessionStorage` ます。</span><span class="sxs-lookup"><span data-stu-id="a2f48-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `sessionStorage` key-value pairs of a domain other than the page you are on.</span></span>  
    
    :::image type="complex" source="../media/storage-console-domain-selection.msft.png" alt-text="本体の JavaScript のコンテキストを変更する" lightbox="../media/storage-console-domain-selection.msft.png":::
       <span data-ttu-id="a2f48-143">本体の JavaScript のコンテキストを変更する</span><span class="sxs-lookup"><span data-stu-id="a2f48-143">Change the JavaScript context of the Console</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a2f48-144">`sessionStorage`JavaScript と同じように、コンソールで式を実行します。</span><span class="sxs-lookup"><span data-stu-id="a2f48-144">Run your `sessionStorage` expressions in the Console, the same as you would in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-session-storage-keys.msft.png" alt-text="コンソールからセッションストレージを操作する" lightbox="../media/storage-console-session-storage-keys.msft.png":::
       <span data-ttu-id="a2f48-146">`sessionStorage`**コンソール**から操作する</span><span class="sxs-lookup"><span data-stu-id="a2f48-146">Interact with `sessionStorage` from the **Console**</span></span>  
    :::image-end:::  
    
<!--  
   

  
-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "セッションストレージ |MDN"  

> [!NOTE]
> <span data-ttu-id="a2f48-149">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2f48-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a2f48-150">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="a2f48-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a2f48-152">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a2f48-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
