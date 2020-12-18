---
description: オーバーライド機能は、Microsoft Edge DevTools の Sources ツール内の機能で、Web ページのリソースをハード ドライブにコピーできます。  Web ページを更新すると、DevTools はリソースを読み込むのではなく、ローカル コピーに置き換える必要があります。
title: Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7f273f89708e0948e68cd2c7ba79cefb6d7e167c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230965"
---
# <span data-ttu-id="ae0a9-105">Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする</span><span class="sxs-lookup"><span data-stu-id="ae0a9-105">Override webpage resources with local copies using Microsoft Edge DevTools</span></span>  

<span data-ttu-id="ae0a9-106">アクセスできない Web ページや修正プログラムの問題を修正する必要がある場合は、ビルド プロセスが遅く複雑になります。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-106">Sometimes you need to fix a problem on a webpage that you do not have access to or fixes involve a slow and complex build process.</span></span>  <span data-ttu-id="ae0a9-107">DevTools では、すべての種類の問題をデバッグして修正できます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-107">You may debug and fix all kind of problems in DevTools.</span></span> <span data-ttu-id="ae0a9-108">ただし、問題は変更が保持されない点です。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-108">But the problem is the changes do not persist.</span></span>  <span data-ttu-id="ae0a9-109">ファイルを更新すると、すべての作業が完了します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-109">After you refresh the file, all your work is gone.</span></span>  

<span data-ttu-id="ae0a9-110">ソース ツールの上書き機能 [は、この][DevToolsSourcesTool] 問題の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-110">The Overrides feature in the [Sources][DevToolsSourcesTool] tool helps you solve this problem.</span></span>  

<span data-ttu-id="ae0a9-111">現在の Web ページのリソースを取得し、ローカルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-111">You may now take a resource of the current webpage and store it locally.</span></span>  <span data-ttu-id="ae0a9-112">Web ページを更新しても、ブラウザーはサーバーからリソースを読み込みしません。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-112">When you refresh the webpage, the browser does not load the resource from the server.</span></span>  <span data-ttu-id="ae0a9-113">代わりに、ブラウザーがリソースのローカル コピーに置き換わる。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-113">Instead the browser replaces it with your local copy of the resource.</span></span>  

## <span data-ttu-id="ae0a9-114">上書きを保存するローカル フォルダーの設定</span><span class="sxs-lookup"><span data-stu-id="ae0a9-114">Setting up your local folder to store Overrides</span></span>  

1.  <span data-ttu-id="ae0a9-115">ソース ツール **で** 、左側に複数のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-115">In the **Sources** tool, find several sections on the left-hand side.</span></span>  <span data-ttu-id="ae0a9-116">[ **上書き] オプション** が表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="ae0a9-116">If the **Overrides** option is not displayed, choose the</span></span> <code>&#x0226B;</code><!--`≫`--> <span data-ttu-id="ae0a9-117">アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-117">icon to get there.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="上書きオプションを表示するのに十分な領域を持たなかったソース ツール" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             <span data-ttu-id="ae0a9-119">**上書き** オプションを表示するのに十分な領域を持たなかったソース ツール</span><span class="sxs-lookup"><span data-stu-id="ae0a9-119">**Sources** tool with not enough space to show the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="上書きオプションを選択する" lightbox="../media/javascript-overrides-menu.msft.png":::
             <span data-ttu-id="ae0a9-121">上書きオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="ae0a9-121">Choose the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="ae0a9-122">上書きオプションを **選択** した後、ローカル コンピューター上のフォルダーを選択して、置換するリソース ファイルを格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-122">After you choose the **Overrides** option, you must choose a folder on your local computer to store the resource files that you want to replace.</span></span>  <span data-ttu-id="ae0a9-123">Choose the **+ Select folder for overrides** to search for a folder.</span><span class="sxs-lookup"><span data-stu-id="ae0a9-123">Choose the **+ Select folder for overrides** to search for a folder.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="上書きに使用するフォルダーを選択する" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       <span data-ttu-id="ae0a9-125">上書きに使用するフォルダーを選択する</span><span class="sxs-lookup"><span data-stu-id="ae0a9-125">Choose a folder to use for overrides</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0a9-126">DevTools は、フォルダーへのフル アクセスが必要であり、機密情報を公開しなけなければならないという警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-126">DevTools warns you that must have full access to the folder and that you should not reveal any sensitive information.</span></span>  <span data-ttu-id="ae0a9-127">警告バーで、[アクセスを許可 **する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-127">On the warning bar, choose **Allow** to grant access.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="DevTools にフォルダーへのアクセス権を付与する" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       <span data-ttu-id="ae0a9-129">DevTools にフォルダーへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="ae0a9-129">Grant DevTools access to folder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0a9-130">[上書 **き] ウィンドウ** で、チェック ボックスが横に表示され、上書 `Enable Local Overrides` きフォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-130">In the **Overrides** pane, a checkbox should be displayed next to `Enable Local Overrides` and your overrides folder.</span></span>  <span data-ttu-id="ae0a9-131">アイコンが横に表示され、ローカルの上書き設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-131">An icon is displayed next to it that allows you to delete your local overrides settings.</span></span>  <span data-ttu-id="ae0a9-132">これで、フォルダーのセットアップが完了し、ライブ リソースをローカル リソースに置き換える準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-132">You are now done setting up your folder and ready to replace live resources with local ones.</span></span>
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="オーバーライド フォルダーの正常なセットアップ" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       <span data-ttu-id="ae0a9-134">オーバーライド フォルダーの正常なセットアップ</span><span class="sxs-lookup"><span data-stu-id="ae0a9-134">Successful set up of an overrides folder</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ae0a9-135">Overrides フォルダーへのファイルの追加</span><span class="sxs-lookup"><span data-stu-id="ae0a9-135">Adding files to your Overrides folder</span></span>  
  
<span data-ttu-id="ae0a9-136">オーバーライド フォルダーにファイルを追加するには **、Elements** ツールを開き、Web ページを検査します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-136">To add files to your overrides folder, open the **Elements** tool and inspect the webpage.</span></span>  <span data-ttu-id="ae0a9-137">編集するには、[スタイル] インスペクターで CSS ファイルの名前 **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-137">To edit, choose the name of the CSS file in the **Styles** inspector.</span></span>  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="スタイルインスペクターでファイルを選択する" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   <span data-ttu-id="ae0a9-139">スタイルインスペクターでファイル **を選択** する</span><span class="sxs-lookup"><span data-stu-id="ae0a9-139">Choose a file in the **Styles** inspector</span></span>  
:::image-end:::  

<span data-ttu-id="ae0a9-140">ソース エディター **で、** 選択したファイルのファイル名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[上書きのために保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-140">On the **Sources** editor, hover on the file name of your chosen file, open the contextual menu \(right-click\), and choose **Save for overrides**.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="Sources エディターで、上書きするファイルの名前を追加します。" lightbox="../media/javascript-overrides-file-name.msft.png":::
   <span data-ttu-id="ae0a9-142">Sources **エディターで** 、上書きするファイルの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-142">In the **Sources** editor, add the name of the file to overrides</span></span>  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="コンテキスト メニューで、[上書き用に保存] を選択します。" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   <span data-ttu-id="ae0a9-144">コンテキスト メニューで、[上書き用に **保存] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="ae0a9-144">On the context menu, choose **Save for overrides**</span></span>  
:::image-end:::  

<span data-ttu-id="ae0a9-145">ファイルは上書きフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-145">The file is stored in your overrides folder.</span></span>  <span data-ttu-id="ae0a9-146">DevTools が、正しいディレクトリ構造を持つファイルの URL を使用して名前が付けられたフォルダーを作成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-146">Verify that DevTools create a folder that is named using the URL of the file with the correct directory structure.</span></span>  <span data-ttu-id="ae0a9-147">ファイルは内部に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-147">The file is stored inside.</span></span>  <span data-ttu-id="ae0a9-148">エディターのファイル名にも紫色のドットが表示され、ファイルがローカルであり、ライブファイルできなっています。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-148">The file name in the editor now also shows a purple dot that indicates that the file is local and not a live one.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="上書きフォルダーにファイルが正常に保存されました" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   <span data-ttu-id="ae0a9-150">上書きフォルダーにファイルが正常に保存されました</span><span class="sxs-lookup"><span data-stu-id="ae0a9-150">Successfully stored the file in your overrides folder</span></span>  
:::image-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="ae0a9-151">次の例では、Web ページのスタイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-151">In the following example, you may now change the styles of the webpage.</span></span>  <span data-ttu-id="ae0a9-152">ファイルの周囲に赤い罫線を追加するには、 **スタイル** エディターで次のスタイルをコピーし、body 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-152">To add a red border around the file, on the **Styles** editor, copy the following style, and add it to the body element.</span></span>  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="ae0a9-153">ファイルはコンピューターに自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-153">The file is automatically saved on your computer.</span></span>  <span data-ttu-id="ae0a9-154">ファイルを更新すると、境界線が表示され、作業は失われます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-154">If you refresh the file, the border is displayed and none of your work is lost.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="上書きフォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         <span data-ttu-id="ae0a9-156">上書きフォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する</span><span class="sxs-lookup"><span data-stu-id="ae0a9-156">Change webpage styles persistently by editing a file in your overrides folder</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="ae0a9-157">ソース ツール **の** [ **ページ** ] セクションで、任意のファイルをポイントし、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-157">On the **Sources** tool, in the **Page** section, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="ae0a9-158">繰り返しますが、上書きフォルダーに既に存在するファイルのアイコンには紫色のドットが付きます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-158">Again, files that are already in your overrides folder have a purple dot on the icon.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="上書きのためにソース ツールからファイルを選択する" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         <span data-ttu-id="ae0a9-160">上書きのためにソース ツール **からファイル** を選択する</span><span class="sxs-lookup"><span data-stu-id="ae0a9-160">Choose a file from the **Sources** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="ae0a9-161">または、ネットワーク ツール\*\*\*\* で任意のファイルをポイントし、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-161">Alternatively, on the **Network** tool, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="ae0a9-162">上書きが有効な場合、実際の Web ページではなくコンピューター上にあるファイル。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-162">When overrides are in effect, files that are located on your computer and not from the live webpage.</span></span>  <span data-ttu-id="ae0a9-163">上書きが有効な場合は、 **ネットワーク** ツールでファイル名の横にある警告アイコンを探します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-163">When overrides are in effect, on the **Network** tool, locate a warning icon next to the file name.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="ネットワーク ツールから上書き用のファイルを選択する" lightbox="../media/javascript-overrides-network.msft.png":::
         <span data-ttu-id="ae0a9-165">ネットワーク ツールから上書き **用の** ファイルを選択する</span><span class="sxs-lookup"><span data-stu-id="ae0a9-165">Choose a file from the **Network** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="ae0a9-166">オーバーライドの 2 つのやり取り</span><span class="sxs-lookup"><span data-stu-id="ae0a9-166">Two-way interaction of overrides</span></span>  

<span data-ttu-id="ae0a9-167">DevTools の **Sources** ツールに用意されているエディター、またはファイルを変更する任意のエディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-167">Use the editor provided with the **Sources** tool of DevTools or any editor you want to change the files.</span></span>  <span data-ttu-id="ae0a9-168">変更は、overrides フォルダー内のファイルにアクセスする製品すべてで同期されます。</span><span class="sxs-lookup"><span data-stu-id="ae0a9-168">Changes are synced across all the products that access the files in the overrides folder.</span></span>  

## <span data-ttu-id="ae0a9-169">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="ae0a9-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources/index.md "ソース ツールの概要 |Microsoft Docs"  
