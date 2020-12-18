---
description: セッション ストレージ ウィンドウとコンソールを使用して sessionStorage を表示および編集する方法について説明します。
title: Microsoft Edge DevTools を使用してセッション ストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e31e45abc5eac26d297cd9bc9fca43778dd74300
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231196"
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

# <span data-ttu-id="6b1af-104">Microsoft Edge DevTools を使用してセッション ストレージを表示および編集する</span><span class="sxs-lookup"><span data-stu-id="6b1af-104">View and edit Session Storage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="6b1af-105">このガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使用して [sessionStorage][MDNSessionStorage] キーと値のペアを表示、編集、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b1af-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [sessionStorage][MDNSessionStorage] key-value pairs.</span></span>  

## <span data-ttu-id="6b1af-106">sessionStorage キーと値を表示する</span><span class="sxs-lookup"><span data-stu-id="6b1af-106">View sessionStorage keys and values</span></span>  

1.  <span data-ttu-id="6b1af-107">[アプリケーション **] タブ** を選択して、アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="6b1af-107">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="6b1af-108">マニフェスト **ウィンドウ** は既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b1af-108">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="6b1af-110">マニフェスト**ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="6b1af-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b1af-111">[セッション ストレージ **] メニューを展開** します。</span><span class="sxs-lookup"><span data-stu-id="6b1af-111">Expand the **Session Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage.msft.png" alt-text="[セッション記憶域] メニュー" lightbox="../media/storage-application-storage-session-storage.msft.png":::
       <span data-ttu-id="6b1af-113">[ **セッション記憶域]** メニュー</span><span class="sxs-lookup"><span data-stu-id="6b1af-113">The **Session Storage** Menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b1af-114">キーと値のペアを表示するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b1af-114">Choose a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain.msft.png" alt-text="sessionStorage キーと値のペア" lightbox="../media/storage-application-storage-session-storage-domain.msft.png":::
       <span data-ttu-id="6b1af-116">キー `sessionStorage` と値のペア</span><span class="sxs-lookup"><span data-stu-id="6b1af-116">The `sessionStorage` key-value pairs</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b1af-117">テーブルの行を選択して、テーブルの下のビューアーに値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6b1af-117">Choose a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png" alt-text="x-sid キーの値を表示する" lightbox="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png":::
       <span data-ttu-id="6b1af-119">キーの値を表示 `x-sid` する</span><span class="sxs-lookup"><span data-stu-id="6b1af-119">View the value of the `x-sid` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="6b1af-120">新しい sessionStorage キーと値のペアを作成する</span><span class="sxs-lookup"><span data-stu-id="6b1af-120">Create a new sessionStorage key-value pair</span></span>  

1.  <span data-ttu-id="6b1af-121">[ドメインの sessionStorage キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="6b1af-121">[View the sessionStorage key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="6b1af-122">テーブルの空の部分をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b1af-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="6b1af-123">DevTools によって新しい行が作成され、カーソルが [キー] 列に **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6b1af-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png":::
       <span data-ttu-id="6b1af-125">新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分</span><span class="sxs-lookup"><span data-stu-id="6b1af-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="6b1af-126">sessionStorage キーまたは値の編集</span><span class="sxs-lookup"><span data-stu-id="6b1af-126">Edit sessionStorage keys or values</span></span>  

1.  <span data-ttu-id="6b1af-127">[ドメインの sessionStorage キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="6b1af-127">[View the sessionStorage key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="6b1af-128">[キー] 列または\*\*\*\*[値] 列のセルを**ダブルクリック**して、そのキーまたは値を編集します。</span><span class="sxs-lookup"><span data-stu-id="6b1af-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png" alt-text="sessionStorage キーを編集する" lightbox="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png":::
       <span data-ttu-id="6b1af-130">キーを編集 `sessionStorage` する</span><span class="sxs-lookup"><span data-stu-id="6b1af-130">Edit a `sessionStorage` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="6b1af-131">sessionStorage キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="6b1af-131">Delete sessionStorage key-value pairs</span></span>  

1.  <span data-ttu-id="6b1af-132">[ドメインの `sessionStorage` キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="6b1af-132">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="6b1af-133">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b1af-133">Choose the key-value pair that you want to delete.</span></span>  <span data-ttu-id="6b1af-134">DevTools では、青色が強調表示され、選択されている状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="6b1af-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="6b1af-135">Select the `Delete` key or choose Delete **Selected** \( ![ Delete Selected ][ImageDeleteIcon] \).</span><span class="sxs-lookup"><span data-stu-id="6b1af-135">Select the `Delete` key or choose **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="6b1af-136">ドメインのすべての sessionStorage キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="6b1af-136">Delete all sessionStorage key-value pairs for a domain</span></span>  

1.  <span data-ttu-id="6b1af-137">[ドメインの `sessionStorage` キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="6b1af-137">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="6b1af-138">Choose **Clear All** \( Clear All ![ ][ImageClearIcon] \).</span><span class="sxs-lookup"><span data-stu-id="6b1af-138">Choose **Clear All** \(![Clear All][ImageClearIcon]\).</span></span>  
    
## <span data-ttu-id="6b1af-139">コンソールから sessionStorage を操作する</span><span class="sxs-lookup"><span data-stu-id="6b1af-139">Interact with sessionStorage from the Console</span></span>  

<span data-ttu-id="6b1af-140">コンソールで JavaScript を実行\*\*\*\* できます。また、コンソール\*\*\*\* はページの JavaScript コンテキストにアクセスできるので、コンソールから操作 `sessionStorage` **することができます**。</span><span class="sxs-lookup"><span data-stu-id="6b1af-140">Since you may run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `sessionStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="6b1af-141">ページ以外のドメインのキーと値のペアにアクセスする場合は\*\*\*\*\*\*、JavaScript\*\*コンテキスト メニューを使用してコンソールの JavaScript コンテキスト `sessionStorage` を変更します。</span><span class="sxs-lookup"><span data-stu-id="6b1af-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `sessionStorage` key-value pairs of a domain other than the page you are on.</span></span>  
    
    :::image type="complex" source="../media/storage-console-domain-selection.msft.png" alt-text="コンソールの JavaScript コンテキストを変更する" lightbox="../media/storage-console-domain-selection.msft.png":::
       <span data-ttu-id="6b1af-143">コンソールの JavaScript コンテキストを変更 **する**</span><span class="sxs-lookup"><span data-stu-id="6b1af-143">Change the JavaScript context of the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b1af-144">JavaScript `sessionStorage` の場合と **同**じように、コンソールで式を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b1af-144">Run your `sessionStorage` expressions in the **Console**, the same as you would in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-session-storage-keys.msft.png" alt-text="コンソールから sessionStorage を操作する" lightbox="../media/storage-console-session-storage-keys.msft.png":::
       <span data-ttu-id="6b1af-146">コンソールから `sessionStorage` 操作 **する**</span><span class="sxs-lookup"><span data-stu-id="6b1af-146">Interact with `sessionStorage` from the **Console**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="6b1af-147">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="6b1af-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "Window.sessionStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="6b1af-150">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b1af-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6b1af-151">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="6b1af-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6b1af-153">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6b1af-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
