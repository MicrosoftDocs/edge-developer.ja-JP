---
title: Microsoft Edge DevTools を使ってセッションストレージを表示および編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d90d4bd7ec9b8927b713a744fb067cc5e96a1fe6
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612082"
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





# <span data-ttu-id="a0316-103">Microsoft Edge DevTools を使ってセッションストレージを表示および編集する</span><span class="sxs-lookup"><span data-stu-id="a0316-103">View And Edit Session Storage With Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="a0316-104">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って、キーと値のペアを表示、編集、削除する方法について説明し [`sessionStorage`][MDNSessionStorage] ます。</span><span class="sxs-lookup"><span data-stu-id="a0316-104">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [`sessionStorage`][MDNSessionStorage] key-value pairs.</span></span>  

## <span data-ttu-id="a0316-105">SessionStorage のキーと値の表示</span><span class="sxs-lookup"><span data-stu-id="a0316-105">View sessionStorage keys and values</span></span>   

1.  <span data-ttu-id="a0316-106">[**アプリケーション**] タブを選択して、[**アプリケーション**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a0316-106">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="a0316-107">**マニフェスト**ウィンドウは既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0316-107">The **Manifest** pane is shown by default.</span></span>  
    
    > ##### <span data-ttu-id="a0316-108">図 1</span><span class="sxs-lookup"><span data-stu-id="a0316-108">Figure 1</span></span>  
    > <span data-ttu-id="a0316-109">マニフェストウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a0316-109">The Manifest pane</span></span>  
    > ![マニフェストウィンドウ][ImageManifest]  

1.  <span data-ttu-id="a0316-111">[**セッションストレージ**] メニューを展開します。</span><span class="sxs-lookup"><span data-stu-id="a0316-111">Expand the **Session Storage** menu.</span></span>  
    
    > ##### <span data-ttu-id="a0316-112">図 2</span><span class="sxs-lookup"><span data-stu-id="a0316-112">Figure 2</span></span>  
    > <span data-ttu-id="a0316-113">[**セッション記憶域**] メニュー</span><span class="sxs-lookup"><span data-stu-id="a0316-113">The **Session Storage** Menu</span></span>  
    > ![[セッション記憶域] メニュー][ImageSessionStorageMenu]  

1.  <span data-ttu-id="a0316-115">ドメインを選択して、キーと値のペアを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0316-115">Select a domain to view the key-value pairs.</span></span>  
    
    > ##### <span data-ttu-id="a0316-116">図 3</span><span class="sxs-lookup"><span data-stu-id="a0316-116">Figure 3</span></span>  
    > <span data-ttu-id="a0316-117">セッションストレージのキーと値のペア</span><span class="sxs-lookup"><span data-stu-id="a0316-117">The sessionStorage key-value pairs</span></span>  
    > !["SessionStorage" キーと値のペア][ImageSessionStorage]  

1.  <span data-ttu-id="a0316-119">テーブルの行を選択して、テーブルの下に表示されているビューアーの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="a0316-119">Select a row of the table to view the value in the viewer below the table.</span></span>  
    
    > ##### <span data-ttu-id="a0316-120">図 4</span><span class="sxs-lookup"><span data-stu-id="a0316-120">Figure 4</span></span>  
    > <span data-ttu-id="a0316-121">キーの値を表示する `x-sid`</span><span class="sxs-lookup"><span data-stu-id="a0316-121">Viewing the value of the `x-sid` key</span></span>  
    > ![X sid キーの値を表示する][ImageSessionStorageViewer]  

## <span data-ttu-id="a0316-123">新しい sessionStorage のキーと値のペアを作成する</span><span class="sxs-lookup"><span data-stu-id="a0316-123">Create a new sessionStorage key-value pair</span></span>   

1.  <span data-ttu-id="a0316-124">[ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="a0316-124">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="a0316-125">表の空の部分をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0316-125">Double-click the empty part of the table.</span></span>  <span data-ttu-id="a0316-126">DevTools で新しい行を作成し、**キー**列にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="a0316-126">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    > ##### <span data-ttu-id="a0316-127">図 5</span><span class="sxs-lookup"><span data-stu-id="a0316-127">Figure 5</span></span>  
    > <span data-ttu-id="a0316-128">新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分</span><span class="sxs-lookup"><span data-stu-id="a0316-128">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    > ![新しいキーと値のペアを作成するためにダブルクリックするテーブルの空の部分][ImageSessionStorageCreate]  

## <span data-ttu-id="a0316-130">SessionStorage のキーまたは値を編集する</span><span class="sxs-lookup"><span data-stu-id="a0316-130">Edit sessionStorage keys or values</span></span>   

1.  <span data-ttu-id="a0316-131">[ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="a0316-131">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="a0316-132">キーまた**は値の列の**セルをダブルクリックし**て、その**キーまたは値を編集します。</span><span class="sxs-lookup"><span data-stu-id="a0316-132">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    > ##### <span data-ttu-id="a0316-133">図 6</span><span class="sxs-lookup"><span data-stu-id="a0316-133">Figure 6</span></span>  
    > <span data-ttu-id="a0316-134">キーを編集する `sessionStorage`</span><span class="sxs-lookup"><span data-stu-id="a0316-134">Editing a `sessionStorage` key</span></span>  
    > ![セッションストレージキーを編集する][ImageSessionStorageEdit]  

## <span data-ttu-id="a0316-136">セッションストレージのキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="a0316-136">Delete sessionStorage key-value pairs</span></span>   

1.  <span data-ttu-id="a0316-137">[ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="a0316-137">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="a0316-138">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0316-138">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="a0316-139">DevTools は、青色を強調表示して、選択されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a0316-139">DevTools highlights it blue to indicate that it is selected.</span></span>  

1.  <span data-ttu-id="a0316-140">キーを押すか、[選択した `Delete` 削除の削除] をクリックし**Delete Selected** ![ ][ImageDeleteIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="a0316-140">Press the `Delete` key or click **Delete Selected** ![Delete Selected][ImageDeleteIcon].</span></span>  

## <span data-ttu-id="a0316-141">ドメインのすべてのセッション記憶域のキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="a0316-141">Delete all sessionStorage key-value pairs for a domain</span></span>   

1.  <span data-ttu-id="a0316-142">[ `sessionStorage` ドメインのキーと値のペアを表示](#view-sessionstorage-keys-and-values)します。</span><span class="sxs-lookup"><span data-stu-id="a0316-142">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  

1.  <span data-ttu-id="a0316-143">[**すべて**クリア] を選択し ![ ][ImageClearIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="a0316-143">Select **Clear All** ![Clear All][ImageClearIcon].</span></span>  

## <span data-ttu-id="a0316-144">コンソールからセッションストレージを操作する</span><span class="sxs-lookup"><span data-stu-id="a0316-144">Interact with sessionStorage from the Console</span></span>   

<span data-ttu-id="a0316-145">JavaScript は**本体**で実行できるため、**本体**はページの javascript コンテキストにアクセスできるため、コンソールから操作することができ `sessionStorage` ます。 **Console**</span><span class="sxs-lookup"><span data-stu-id="a0316-145">Since you can run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `sessionStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="a0316-146">使用しているページ以外のドメインのキーと値のペアにアクセスする場合は、 **javascript のコンテキスト**メニューを使って**本体**の javascript コンテキストを変更し `sessionStorage` ます。</span><span class="sxs-lookup"><span data-stu-id="a0316-146">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `sessionStorage` key-value pairs of a domain other than the page you are on.</span></span>  
    
    > ##### <span data-ttu-id="a0316-147">図 7</span><span class="sxs-lookup"><span data-stu-id="a0316-147">Figure 7</span></span>  
    > <span data-ttu-id="a0316-148">**本体**の JavaScript コンテキストの変更</span><span class="sxs-lookup"><span data-stu-id="a0316-148">Changing the JavaScript context of the **Console**</span></span>  
    > ![本体の JavaScript コンテキストの変更][ImageJSContext]  

1.  <span data-ttu-id="a0316-150">`sessionStorage`JavaScript と同じように、コンソールで式を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0316-150">Run your `sessionStorage` expressions in the Console, the same as you would in your JavaScript.</span></span>  
    
    > ##### <span data-ttu-id="a0316-151">図 8</span><span class="sxs-lookup"><span data-stu-id="a0316-151">Figure 8</span></span>  
    > <span data-ttu-id="a0316-152">`sessionStorage`**コンソール**からの操作</span><span class="sxs-lookup"><span data-stu-id="a0316-152">Interacting with `sessionStorage` from the **Console**</span></span>  
    > ![セッションストレージと本体との対話][ImageSessionStorageConsole]  

   

  

<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageSessionStorageMenu]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-session-storage.msft.png "図 2: [セッションストレージ] メニュー"  
[ImageSessionStorage]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-session-storage-domain.msft.png "図 3: セッションストレージのキーと値のペア"  
[ImageSessionStorageViewer]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-session-storage-domain-key-value-selected.msft.png "図 4: x sid キーの値を表示する"  
[ImageSessionStorageCreate]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-session-storage-domain-key-value-new.msft.png "図 5: 新しいキーと値のペアを作成するために、表の空の部分をダブルクリックする"  
[ImageSessionStorageEdit]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-session-storage-domain-key-value-edit.msft.png "図 6: セッションストレージキーを編集する"  
[ImageJSContext]: /microsoft-edge/devtools-guide-chromium/media/storage-console-domain-selection.msft.png "図 7: 本体の JavaScript コンテキストの変更"  
[ImageSessionStorageConsole]: /microsoft-edge/devtools-guide-chromium/media/storage-console-session-storage-keys.msft.png "図 8: コンソールからのセッションストレージとの相互作用"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "セッションストレージ |MDN"  

> [!NOTE]
> <span data-ttu-id="a0316-164">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0316-164">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a0316-165">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="a0316-165">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a0316-167">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a0316-167">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
