---
description: オーバーライド機能は、Microsoft Edge DevTools の Sources ツール内の機能で、Web ページ リソースをハード ドライブにコピーできます。  Web ページを更新すると、DevTools はリソースを読み込むのではなく、ローカル コピーに置き換える必要があります。
title: Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7f273f89708e0948e68cd2c7ba79cefb6d7e167c
ms.sourcegitcommit: 2ddfd98d1e871be9c61380a8ca57da398d38bd54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "11230965"
---
# <a name="override-webpage-resources-with-local-copies-using-microsoft-edge-devtools"></a><span data-ttu-id="3195d-105">Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする</span><span class="sxs-lookup"><span data-stu-id="3195d-105">Override webpage resources with local copies using Microsoft Edge DevTools</span></span>  

<span data-ttu-id="3195d-106">アクセスできない Web ページや修正プログラムで問題を修正する必要がある場合は、ビルド プロセスが遅く複雑な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3195d-106">Sometimes you need to fix a problem on a webpage that you do not have access to or fixes involve a slow and complex build process.</span></span>  <span data-ttu-id="3195d-107">DevTools のすべての種類の問題をデバッグして修正できます。</span><span class="sxs-lookup"><span data-stu-id="3195d-107">You may debug and fix all kind of problems in DevTools.</span></span> <span data-ttu-id="3195d-108">しかし、問題は変更が持続しない点です。</span><span class="sxs-lookup"><span data-stu-id="3195d-108">But the problem is the changes do not persist.</span></span>  <span data-ttu-id="3195d-109">ファイルを更新すると、すべての作業が完了します。</span><span class="sxs-lookup"><span data-stu-id="3195d-109">After you refresh the file, all your work is gone.</span></span>  

<span data-ttu-id="3195d-110">ソース ツールのオーバーライド機能 [を使用すると][DevToolsSourcesTool] 、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="3195d-110">The Overrides feature in the [Sources][DevToolsSourcesTool] tool helps you solve this problem.</span></span>  

<span data-ttu-id="3195d-111">現在の Web ページのリソースを取得し、ローカルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="3195d-111">You may now take a resource of the current webpage and store it locally.</span></span>  <span data-ttu-id="3195d-112">Web ページを更新しても、ブラウザーはサーバーからリソースを読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="3195d-112">When you refresh the webpage, the browser does not load the resource from the server.</span></span>  <span data-ttu-id="3195d-113">代わりに、ブラウザーは、リソースのローカル コピーに置き換える。</span><span class="sxs-lookup"><span data-stu-id="3195d-113">Instead the browser replaces it with your local copy of the resource.</span></span>  

## <a name="setting-up-your-local-folder-to-store-overrides"></a><span data-ttu-id="3195d-114">上書きを保存するローカル フォルダーを設定する</span><span class="sxs-lookup"><span data-stu-id="3195d-114">Setting up your local folder to store Overrides</span></span>  

1.  <span data-ttu-id="3195d-115">[ソース **] ツール** で、左側に複数のセクションを検索します。</span><span class="sxs-lookup"><span data-stu-id="3195d-115">In the **Sources** tool, find several sections on the left-hand side.</span></span>  <span data-ttu-id="3195d-116">[ **上書き] オプション** が表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="3195d-116">If the **Overrides** option is not displayed, choose the</span></span> <code>&#x0226B;</code><!--`≫`--> <span data-ttu-id="3195d-117">アイコンをクリックしてそこにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3195d-117">icon to get there.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="オーバーライド オプションを表示するのに十分な領域を持つソース ツール" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             <span data-ttu-id="3195d-119">**オーバーライド オプション** を表示するのに十分な領域を持つソース ツール</span><span class="sxs-lookup"><span data-stu-id="3195d-119">**Sources** tool with not enough space to show the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="上書きオプションを選択する" lightbox="../media/javascript-overrides-menu.msft.png":::
             <span data-ttu-id="3195d-121">上書きオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="3195d-121">Choose the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="3195d-122">[上書き] オプション **を** 選択した後、ローカル コンピューター上のフォルダーを選択して、置き換えるリソース ファイルを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3195d-122">After you choose the **Overrides** option, you must choose a folder on your local computer to store the resource files that you want to replace.</span></span>  <span data-ttu-id="3195d-123">フォルダーを **検索するには、上書きする +** 選択フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3195d-123">Choose the **+ Select folder for overrides** to search for a folder.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="上書きに使用するフォルダーを選択する" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       <span data-ttu-id="3195d-125">上書きに使用するフォルダーを選択する</span><span class="sxs-lookup"><span data-stu-id="3195d-125">Choose a folder to use for overrides</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3195d-126">DevTools は、フォルダーへのフル アクセス権が必要であり、機密情報を明らかにしなける必要があるという警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="3195d-126">DevTools warns you that must have full access to the folder and that you should not reveal any sensitive information.</span></span>  <span data-ttu-id="3195d-127">警告バーで、[許可] を **選択してアクセス** を許可します。</span><span class="sxs-lookup"><span data-stu-id="3195d-127">On the warning bar, choose **Allow** to grant access.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="DevTools にフォルダーへのアクセス権を付与する" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       <span data-ttu-id="3195d-129">DevTools にフォルダーへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="3195d-129">Grant DevTools access to folder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3195d-130">[上書 **き]** ウィンドウの横にチェック ボックスが表示され、 `Enable Local Overrides` 上書きフォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3195d-130">In the **Overrides** pane, a checkbox should be displayed next to `Enable Local Overrides` and your overrides folder.</span></span>  <span data-ttu-id="3195d-131">アイコンが横に表示され、ローカルの上書き設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="3195d-131">An icon is displayed next to it that allows you to delete your local overrides settings.</span></span>  <span data-ttu-id="3195d-132">これで、フォルダーのセットアップが完了し、ライブ リソースをローカル リソースに置き換える準備ができました。</span><span class="sxs-lookup"><span data-stu-id="3195d-132">You are now done setting up your folder and ready to replace live resources with local ones.</span></span>
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="上書きフォルダーの正常なセットアップ" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       <span data-ttu-id="3195d-134">上書きフォルダーの正常なセットアップ</span><span class="sxs-lookup"><span data-stu-id="3195d-134">Successful set up of an overrides folder</span></span>  
    :::image-end:::  
    
## <a name="adding-files-to-your-overrides-folder"></a><span data-ttu-id="3195d-135">Overrides フォルダーへのファイルの追加</span><span class="sxs-lookup"><span data-stu-id="3195d-135">Adding files to your Overrides folder</span></span>  
  
<span data-ttu-id="3195d-136">上書きフォルダーにファイルを追加するには、[要素] ツール **を開** き、Web ページを調べる。</span><span class="sxs-lookup"><span data-stu-id="3195d-136">To add files to your overrides folder, open the **Elements** tool and inspect the webpage.</span></span>  <span data-ttu-id="3195d-137">編集するには、[スタイル] インスペクタで CSS ファイルの名前 **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="3195d-137">To edit, choose the name of the CSS file in the **Styles** inspector.</span></span>  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="[スタイル] インスペクタでファイルを選択する" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   <span data-ttu-id="3195d-139">[スタイル] インスペクタでファイル **を選択** する</span><span class="sxs-lookup"><span data-stu-id="3195d-139">Choose a file in the **Styles** inspector</span></span>  
:::image-end:::  

<span data-ttu-id="3195d-140">[ソース **] エディターで** 、選択したファイルのファイル名にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[上書き用に保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3195d-140">On the **Sources** editor, hover on the file name of your chosen file, open the contextual menu \(right-click\), and choose **Save for overrides**.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="[ソース] エディターで、上書きするファイルの名前を追加します。" lightbox="../media/javascript-overrides-file-name.msft.png":::
   <span data-ttu-id="3195d-142">[ソース **] エディターで** 、上書きするファイルの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="3195d-142">In the **Sources** editor, add the name of the file to overrides</span></span>  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="コンテキスト メニューで、[上書き用に保存] を選択します。" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   <span data-ttu-id="3195d-144">コンテキスト メニューで、[上書き用 **に保存] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="3195d-144">On the context menu, choose **Save for overrides**</span></span>  
:::image-end:::  

<span data-ttu-id="3195d-145">ファイルは上書きフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="3195d-145">The file is stored in your overrides folder.</span></span>  <span data-ttu-id="3195d-146">DevTools が、正しいディレクトリ構造を持つファイルの URL を使用して名前が付けられたフォルダーを作成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3195d-146">Verify that DevTools create a folder that is named using the URL of the file with the correct directory structure.</span></span>  <span data-ttu-id="3195d-147">ファイルは内部に格納されます。</span><span class="sxs-lookup"><span data-stu-id="3195d-147">The file is stored inside.</span></span>  <span data-ttu-id="3195d-148">エディターのファイル名には、ファイルがローカルであり、ライブではないかどうかを示す紫色のドットも表示されます。</span><span class="sxs-lookup"><span data-stu-id="3195d-148">The file name in the editor now also shows a purple dot that indicates that the file is local and not a live one.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="ファイルをオーバーライド フォルダーに正常に保存しました" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   <span data-ttu-id="3195d-150">ファイルをオーバーライド フォルダーに正常に保存しました</span><span class="sxs-lookup"><span data-stu-id="3195d-150">Successfully stored the file in your overrides folder</span></span>  
:::image-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="3195d-151">次の例では、Web ページのスタイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3195d-151">In the following example, you may now change the styles of the webpage.</span></span>  <span data-ttu-id="3195d-152">ファイルの周囲に赤い枠線を追加するには\*\*\*\*、[スタイル] エディターで次のスタイルをコピーし、body 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="3195d-152">To add a red border around the file, on the **Styles** editor, copy the following style, and add it to the body element.</span></span>  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="3195d-153">ファイルはコンピューターに自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="3195d-153">The file is automatically saved on your computer.</span></span>  <span data-ttu-id="3195d-154">ファイルを更新すると、罫線が表示され、作業のどれも失われます。</span><span class="sxs-lookup"><span data-stu-id="3195d-154">If you refresh the file, the border is displayed and none of your work is lost.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="オーバーライド フォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         <span data-ttu-id="3195d-156">オーバーライド フォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する</span><span class="sxs-lookup"><span data-stu-id="3195d-156">Change webpage styles persistently by editing a file in your overrides folder</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="3195d-157">[ソース **] ツールの** [ **ページ** ] セクションで、任意のファイルにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。</span><span class="sxs-lookup"><span data-stu-id="3195d-157">On the **Sources** tool, in the **Page** section, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="3195d-158">繰り返しますが、上書きフォルダーに既に存在するファイルには、アイコンに紫色のドットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3195d-158">Again, files that are already in your overrides folder have a purple dot on the icon.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="上書きのために Sources ツールからファイルを選択する" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         <span data-ttu-id="3195d-160">上書きのために **Sources ツールから** ファイルを選択する</span><span class="sxs-lookup"><span data-stu-id="3195d-160">Choose a file from the **Sources** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="3195d-161">または、ネットワーク ツール\*\*\*\* で任意のファイルにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。</span><span class="sxs-lookup"><span data-stu-id="3195d-161">Alternatively, on the **Network** tool, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="3195d-162">上書きが有効な場合、ライブ Web ページではなく、コンピューター上にあるファイル。</span><span class="sxs-lookup"><span data-stu-id="3195d-162">When overrides are in effect, files that are located on your computer and not from the live webpage.</span></span>  <span data-ttu-id="3195d-163">上書きが有効な場合は、 **ネットワーク** ツールで、ファイル名の横にある警告アイコンを探します。</span><span class="sxs-lookup"><span data-stu-id="3195d-163">When overrides are in effect, on the **Network** tool, locate a warning icon next to the file name.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="ネットワーク ツールから上書き用のファイルを選択する" lightbox="../media/javascript-overrides-network.msft.png":::
         <span data-ttu-id="3195d-165">ネットワーク ツールから上書き **用の** ファイルを選択する</span><span class="sxs-lookup"><span data-stu-id="3195d-165">Choose a file from the **Network** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="two-way-interaction-of-overrides"></a><span data-ttu-id="3195d-166">オーバーライドの相互対話</span><span class="sxs-lookup"><span data-stu-id="3195d-166">Two-way interaction of overrides</span></span>  

<span data-ttu-id="3195d-167">DevTools の **Sources** ツールまたはファイルを変更する任意のエディターで提供されるエディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3195d-167">Use the editor provided with the **Sources** tool of DevTools or any editor you want to change the files.</span></span>  <span data-ttu-id="3195d-168">変更は、オーバーライド フォルダー内のファイルにアクセスするすべての製品間で同期されます。</span><span class="sxs-lookup"><span data-stu-id="3195d-168">Changes are synced across all the products that access the files in the overrides folder.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="3195d-169">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="3195d-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources/index.md "ソース ツールの概要|Microsoft Docs"  
