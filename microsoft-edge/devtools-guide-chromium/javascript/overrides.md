---
description: オーバーライド機能は、Microsoft Edge DevTools の Sources ツール内の機能で、Web ページ リソースをハード ドライブにコピーできます。  Web ページを更新すると、DevTools はリソースを読み込むのではなく、ローカル コピーに置き換える必要があります。
title: Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 66c0686c166163f1640384d096288af0b530f135
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519437"
---
# <a name="override-webpage-resources-with-local-copies-using-microsoft-edge-devtools"></a><span data-ttu-id="4c1b5-105">Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする</span><span class="sxs-lookup"><span data-stu-id="4c1b5-105">Override webpage resources with local copies using Microsoft Edge DevTools</span></span>  

<span data-ttu-id="4c1b5-106">場合によっては、Web ページの修正プログラムを試す必要がありますが、ソース ファイルにアクセスできない場合や、ページを変更するには、低速で複雑なビルド プロセスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-106">Sometimes you need to try out some possible fixes for a webpage, but you don't have access to the source files, or changing the page requires a slow and complex build process.</span></span>  <span data-ttu-id="4c1b5-107">DevTools のすべての種類の問題をデバッグして修正できます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-107">You may debug and fix all kind of problems in DevTools.</span></span>  <span data-ttu-id="4c1b5-108">ただし、変更は保持されません。ローカル ファイルを更新すると、すべての作業が完了します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-108">But the changes do not persist; after you refresh the local file, all your work is gone.</span></span>  <span data-ttu-id="4c1b5-109">ソース ツールのオーバーライド機能 [を使用すると][DevToolsSourcesTool] 、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-109">The Overrides feature in the [Sources][DevToolsSourcesTool] tool helps you solve this problem.</span></span>  

<span data-ttu-id="4c1b5-110">現在の Web ページのリソースを取得し、ローカルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-110">You may now take a resource of the current webpage and store it locally.</span></span>  <span data-ttu-id="4c1b5-111">Web ページを更新しても、ブラウザーはサーバーからリソースを読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-111">When you refresh the webpage, the browser does not load the resource from the server.</span></span>  <span data-ttu-id="4c1b5-112">代わりに、ブラウザーは、リソースのローカル コピーに置き換える。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-112">Instead the browser replaces it with your local copy of the resource.</span></span>  

## <a name="setting-up-your-local-folder-to-store-overrides"></a><span data-ttu-id="4c1b5-113">上書きを保存するローカル フォルダーを設定する</span><span class="sxs-lookup"><span data-stu-id="4c1b5-113">Setting up your local folder to store Overrides</span></span>  

1.  <span data-ttu-id="4c1b5-114">[ソース] **ツールに移動** します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-114">Navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="4c1b5-115">左側の **[ナビゲーター]** ウィンドウで、[上書き] **タブを選択** します。 [上書 **き] タブが** 表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="4c1b5-115">In the **Navigator** pane (on the left), choose the **Overrides** tab.  If the **Overrides** tab is not displayed, choose the</span></span> <code>&#x0226B;</code><!--`≫`--> <span data-ttu-id="4c1b5-116"> アイコンを選びます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-116">icon.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="オーバーライド オプションを表示するのに十分な領域を持つソース ツール" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             <span data-ttu-id="4c1b5-118">**オーバーライド オプション** を表示するのに十分な領域を持つソース ツール</span><span class="sxs-lookup"><span data-stu-id="4c1b5-118">**Sources** tool with not enough space to show the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="上書きオプションを選択する" lightbox="../media/javascript-overrides-menu.msft.png":::
             <span data-ttu-id="4c1b5-120">上書きオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="4c1b5-120">Choose the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="4c1b5-121">置き換えるリソース ファイルを保存するフォルダーをローカル コンピューター上で選択します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-121">Choose a folder on your local computer to store the resource files that you want to replace.</span></span>  
     *   <span data-ttu-id="4c1b5-122">フォルダーを検索するには、[+ 上書き **フォルダーの選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-122">To search for a folder, choose **+ Select folder for overrides**.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="上書きに使用するフォルダーを選択する" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       <span data-ttu-id="4c1b5-124">上書きに使用するフォルダーを選択する</span><span class="sxs-lookup"><span data-stu-id="4c1b5-124">Choose a folder to use for overrides</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4c1b5-125">DevTools は、フォルダーへのフル アクセス権が必要であり、機密情報を明らかにしなける必要があるという警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-125">DevTools warns you that must have full access to the folder and that you should not reveal any sensitive information.</span></span>  <span data-ttu-id="4c1b5-126">警告バーで、[許可] を **選択してアクセス** を許可します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-126">On the warning bar, choose **Allow** to grant access.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="DevTools にフォルダーへのアクセス権を付与する" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       <span data-ttu-id="4c1b5-128">DevTools にフォルダーへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="4c1b5-128">Grant DevTools access to folder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4c1b5-129">[上書 **き] タブ** で、[ローカルオーバーライドを有効にする] の横 **にチェック ボックスが表示されます**。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-129">In the **Overrides** tab, a checkbox is shown next to **Enable Local Overrides**.</span></span>  <span data-ttu-id="4c1b5-130">[ローカル上書き**を有効にする]** の\*\*\*\* 右側には、ローカルの上書き設定を削除できる [構成のクリア] アイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-130">To the right of **Enable Local Overrides** is a **Clear configuration** icon that allows you to delete your local overrides settings.</span></span>  <span data-ttu-id="4c1b5-131">これで、フォルダーのセットアップが完了し、ライブ リソースをローカル リソースに置き換える準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-131">You are now done setting up your folder and are ready to replace live resources with local ones.</span></span>
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="上書きフォルダーの正常なセットアップ" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       <span data-ttu-id="4c1b5-133">上書きフォルダーの正常なセットアップ</span><span class="sxs-lookup"><span data-stu-id="4c1b5-133">Successful setup of an overrides folder</span></span>  
    :::image-end:::  
    
## <a name="adding-files-to-your-overrides-folder"></a><span data-ttu-id="4c1b5-134">Overrides フォルダーへのファイルの追加</span><span class="sxs-lookup"><span data-stu-id="4c1b5-134">Adding files to your Overrides folder</span></span>  
  
<span data-ttu-id="4c1b5-135">上書きフォルダーにファイルを追加するには、[要素] ツール **を開** き、Web ページを調べる。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-135">To add files to your overrides folder, open the **Elements** tool and inspect the webpage.</span></span>  <span data-ttu-id="4c1b5-136">編集するには、[スタイル] インスペクタで CSS ファイルの名前 **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-136">To edit, choose the name of the CSS file in the **Styles** inspector.</span></span>  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="[スタイル] インスペクタでファイルを選択する" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   <span data-ttu-id="4c1b5-138">[スタイル] インスペクタでファイル **を選択** する</span><span class="sxs-lookup"><span data-stu-id="4c1b5-138">Choose a file in the **Styles** inspector</span></span>  
:::image-end:::  

<span data-ttu-id="4c1b5-139">[ソース **] エディターで** 、選択したファイルのファイル名にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[上書き用に保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-139">On the **Sources** editor, hover on the file name of your chosen file, open the contextual menu \(right-click\), and choose **Save for overrides**.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="[ソース] エディターで、上書きするファイルの名前を追加します。" lightbox="../media/javascript-overrides-file-name.msft.png":::
   <span data-ttu-id="4c1b5-141">[ソース **] エディターで** 、上書きするファイルの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-141">In the **Sources** editor, add the name of the file to overrides</span></span>  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="コンテキスト メニューで、[上書き用に保存] を選択します。" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   <span data-ttu-id="4c1b5-143">コンテキスト メニューで、[上書き用 **に保存] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="4c1b5-143">On the context menu, choose **Save for overrides**</span></span>  
:::image-end:::  

<span data-ttu-id="4c1b5-144">ファイルは上書きフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-144">The file is stored in your overrides folder.</span></span>  <span data-ttu-id="4c1b5-145">DevTools が、正しいディレクトリ構造を持つファイルの URL を使用して名前が付けられたフォルダーを作成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-145">Verify that DevTools create a folder that is named using the URL of the file with the correct directory structure.</span></span>  <span data-ttu-id="4c1b5-146">ファイルは内部に格納されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-146">The file is stored inside.</span></span>  <span data-ttu-id="4c1b5-147">エディターのファイル名には、ファイルがローカルであり、ライブではないかどうかを示す紫色のドットも表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-147">The file name in the editor now also shows a purple dot that indicates that the file is local and not a live one.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="ファイルをオーバーライド フォルダーに正常に保存しました" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   <span data-ttu-id="4c1b5-149">ファイルをオーバーライド フォルダーに正常に保存しました</span><span class="sxs-lookup"><span data-stu-id="4c1b5-149">Successfully stored the file in your overrides folder</span></span>  
:::image-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="4c1b5-150">次の例では、Web ページのスタイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-150">In the following example, you may now change the styles of the webpage.</span></span>  <span data-ttu-id="4c1b5-151">ファイルの周囲に赤い枠線を追加するには\*\*\*\*、[スタイル] エディターで次のスタイルをコピーし、body 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-151">To add a red border around the file, on the **Styles** editor, copy the following style, and add it to the body element.</span></span>  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="4c1b5-152">ファイルはコンピューターに自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-152">The file is automatically saved on your computer.</span></span>  <span data-ttu-id="4c1b5-153">ファイルを更新すると、罫線が表示され、作業のどれも失われます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-153">If you refresh the file, the border is displayed and none of your work is lost.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="オーバーライド フォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         <span data-ttu-id="4c1b5-155">オーバーライド フォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する</span><span class="sxs-lookup"><span data-stu-id="4c1b5-155">Change webpage styles persistently by editing a file in your overrides folder</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="4c1b5-156">[ソース **] ツールの** [ **ページ** ] セクションで、任意のファイルにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-156">On the **Sources** tool, in the **Page** section, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="4c1b5-157">繰り返しますが、上書きフォルダーに既に存在するファイルには、アイコンに紫色のドットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-157">Again, files that are already in your overrides folder have a purple dot on the icon.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="上書きのために Sources ツールからファイルを選択する" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         <span data-ttu-id="4c1b5-159">上書きのために **Sources ツールから** ファイルを選択する</span><span class="sxs-lookup"><span data-stu-id="4c1b5-159">Choose a file from the **Sources** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="4c1b5-160">または、ネットワーク ツール\*\*\*\* で任意のファイルにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-160">Alternatively, on the **Network** tool, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="4c1b5-161">上書きが有効な場合、ライブ Web ページではなく、コンピューター上にあるファイル。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-161">When overrides are in effect, files that are located on your computer and not from the live webpage.</span></span>  <span data-ttu-id="4c1b5-162">上書きが有効な場合は、 **ネットワーク** ツールで、ファイル名の横にある警告アイコンを探します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-162">When overrides are in effect, on the **Network** tool, locate a warning icon next to the file name.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="ネットワーク ツールから上書き用のファイルを選択する" lightbox="../media/javascript-overrides-network.msft.png":::
         <span data-ttu-id="4c1b5-164">ネットワーク ツールから上書き **用の** ファイルを選択する</span><span class="sxs-lookup"><span data-stu-id="4c1b5-164">Choose a file from the **Network** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="two-way-interaction-of-overrides"></a><span data-ttu-id="4c1b5-165">オーバーライドの相互対話</span><span class="sxs-lookup"><span data-stu-id="4c1b5-165">Two-way interaction of overrides</span></span>  

<span data-ttu-id="4c1b5-166">DevTools の **Sources** ツールまたはファイルを変更する任意のエディターで提供されるエディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-166">Use the editor provided with the **Sources** tool of DevTools or any editor you want to change the files.</span></span>  <span data-ttu-id="4c1b5-167">変更は、オーバーライド フォルダー内のファイルにアクセスするすべての製品間で同期されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b5-167">Changes are synced across all the products that access the files in the overrides folder.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4c1b5-168">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="4c1b5-168">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources/index.md "ソース ツールの概要|Microsoft Docs"  
