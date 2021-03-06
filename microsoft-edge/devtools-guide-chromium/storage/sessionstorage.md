---
description: セッション ストレージ ウィンドウとコンソールを使用して sessionStorage を表示および編集する方法。
title: Microsoft Edge DevTools を使用してセッション ストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cf00d71302e7a1f16ba1cceaa17c9380245d12f8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398008"
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

# <a name="view-and-edit-session-storage-with-microsoft-edge-devtools"></a><span data-ttu-id="4143b-104">Microsoft Edge DevTools を使用してセッション ストレージを表示および編集する</span><span class="sxs-lookup"><span data-stu-id="4143b-104">View and edit Session Storage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="4143b-105">このガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使用して [sessionStorage][MDNSessionStorage] キーと値のペアを表示、編集、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4143b-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [sessionStorage][MDNSessionStorage] key-value pairs.</span></span>  

## <a name="view-sessionstorage-keys-and-values"></a><span data-ttu-id="4143b-106">sessionStorage キーと値の表示</span><span class="sxs-lookup"><span data-stu-id="4143b-106">View sessionStorage keys and values</span></span>  

1.  <span data-ttu-id="4143b-107">[アプリケーション] **タブを** 選択して、[アプリケーション] ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="4143b-107">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="4143b-108">既定 **では、[マニフェスト** ] パネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4143b-108">The **Manifest** panel is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="4143b-110">[ **マニフェスト]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="4143b-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4143b-111">[セッション ストレージ **] メニューを展開** します。</span><span class="sxs-lookup"><span data-stu-id="4143b-111">Expand the **Session Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage.msft.png" alt-text="[セッション ストレージ] メニュー" lightbox="../media/storage-application-storage-session-storage.msft.png":::
       <span data-ttu-id="4143b-113">[ **セッション ストレージ]** メニュー</span><span class="sxs-lookup"><span data-stu-id="4143b-113">The **Session Storage** Menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4143b-114">キーと値のペアを表示するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4143b-114">Choose a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain.msft.png" alt-text="sessionStorage キーと値のペア" lightbox="../media/storage-application-storage-session-storage-domain.msft.png":::
       <span data-ttu-id="4143b-116">キー `sessionStorage` と値のペア</span><span class="sxs-lookup"><span data-stu-id="4143b-116">The `sessionStorage` key-value pairs</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4143b-117">テーブルの行を選択して、テーブルの下のビューアーで値を表示します。</span><span class="sxs-lookup"><span data-stu-id="4143b-117">Choose a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png" alt-text="x-sid キーの値を表示する" lightbox="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png":::
       <span data-ttu-id="4143b-119">キーの値を表示 `x-sid` する</span><span class="sxs-lookup"><span data-stu-id="4143b-119">View the value of the `x-sid` key</span></span>  
    :::image-end:::  
    
## <a name="create-a-new-sessionstorage-key-value-pair"></a><span data-ttu-id="4143b-120">新しい sessionStorage キーと値のペアを作成する</span><span class="sxs-lookup"><span data-stu-id="4143b-120">Create a new sessionStorage key-value pair</span></span>  

1.  <span data-ttu-id="4143b-121">[ドメインの sessionStorage キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="4143b-121">[View the sessionStorage key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="4143b-122">テーブルの空の部分をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4143b-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="4143b-123">DevTools は新しい行を作成し、[キー] 列にカーソルを **移動** します。</span><span class="sxs-lookup"><span data-stu-id="4143b-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png" alt-text="新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分" lightbox="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png":::
       <span data-ttu-id="4143b-125">新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分</span><span class="sxs-lookup"><span data-stu-id="4143b-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <a name="edit-sessionstorage-keys-or-values"></a><span data-ttu-id="4143b-126">sessionStorage キーまたは値の編集</span><span class="sxs-lookup"><span data-stu-id="4143b-126">Edit sessionStorage keys or values</span></span>  

1.  <span data-ttu-id="4143b-127">[ドメインの sessionStorage キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="4143b-127">[View the sessionStorage key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="4143b-128">[キー] 列または [値] 列の**セル\*\*\*\*をダブルクリック**して、そのキーまたは値を編集します。</span><span class="sxs-lookup"><span data-stu-id="4143b-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png" alt-text="sessionStorage キーの編集" lightbox="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png":::
       <span data-ttu-id="4143b-130">キーの `sessionStorage` 編集</span><span class="sxs-lookup"><span data-stu-id="4143b-130">Edit a `sessionStorage` key</span></span>  
    :::image-end:::  
    
## <a name="delete-sessionstorage-key-value-pairs"></a><span data-ttu-id="4143b-131">sessionStorage キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="4143b-131">Delete sessionStorage key-value pairs</span></span>  

1.  <span data-ttu-id="4143b-132">[ドメインの `sessionStorage` キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="4143b-132">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="4143b-133">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="4143b-133">Choose the key-value pair that you want to delete.</span></span>  <span data-ttu-id="4143b-134">DevTools は青色で強調表示され、選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4143b-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="4143b-135">キーを `Delete` 選択するか、[ **選択した \(** Delete ![ Selected \) を削除する] ][ImageDeleteIcon] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4143b-135">Select the `Delete` key or choose **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <a name="delete-all-sessionstorage-key-value-pairs-for-a-domain"></a><span data-ttu-id="4143b-136">ドメインのすべての sessionStorage キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="4143b-136">Delete all sessionStorage key-value pairs for a domain</span></span>  

1.  <span data-ttu-id="4143b-137">[ドメインの `sessionStorage` キーと値のペアを表示します](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="4143b-137">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="4143b-138">[ **すべてクリア]** \( ![ Clear All ][ImageClearIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4143b-138">Choose **Clear All** \(![Clear All][ImageClearIcon]\).</span></span>  
    
## <a name="interact-with-sessionstorage-from-the-console"></a><span data-ttu-id="4143b-139">コンソールから sessionStorage を操作する</span><span class="sxs-lookup"><span data-stu-id="4143b-139">Interact with sessionStorage from the Console</span></span>  

<span data-ttu-id="4143b-140">コンソールで JavaScript を実行\*\*\*\* できます。また、コンソール\*\*\*\* はページの JavaScript コンテキストにアクセスできますので、コンソールから操作 `sessionStorage` **できます**。</span><span class="sxs-lookup"><span data-stu-id="4143b-140">Since you may run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `sessionStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="4143b-141">現在の**ページ以外**のドメインのキーと値のペアにアクセスする\*\*\*\* 場合は、JavaScript コンテキスト メニューを使用してコンソールの JavaScript コンテキスト `sessionStorage` を変更します。</span><span class="sxs-lookup"><span data-stu-id="4143b-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `sessionStorage` key-value pairs of a domain other than the page you are on.</span></span>  
    
    :::image type="complex" source="../media/storage-console-domain-selection.msft.png" alt-text="コンソールの JavaScript コンテキストを変更する" lightbox="../media/storage-console-domain-selection.msft.png":::
       <span data-ttu-id="4143b-143">コンソールの JavaScript コンテキストを変更 **する**</span><span class="sxs-lookup"><span data-stu-id="4143b-143">Change the JavaScript context of the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4143b-144">JavaScript `sessionStorage` と同\*\*\*\* じ条件式をコンソールで実行します。</span><span class="sxs-lookup"><span data-stu-id="4143b-144">Run your `sessionStorage` expressions in the **Console**, the same as your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-session-storage-keys.msft.png" alt-text="コンソールから sessionStorage を操作する" lightbox="../media/storage-console-session-storage-keys.msft.png":::
       <span data-ttu-id="4143b-146">コンソールからの `sessionStorage` **操作**</span><span class="sxs-lookup"><span data-stu-id="4143b-146">Interact with `sessionStorage` from the **Console**</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4143b-147">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="4143b-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (クロム) 開発者向け|Microsoft Docs"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "Window.sessionStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="4143b-150">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="4143b-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4143b-151">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="4143b-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="4143b-153">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="4143b-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
