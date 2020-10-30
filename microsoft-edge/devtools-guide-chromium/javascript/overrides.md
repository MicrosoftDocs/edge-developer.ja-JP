---
description: 上書き機能は、Microsoft Edge DevTools のソースツール内の機能で、web ページのリソースをハードドライブにコピーすることができます。  Web ページを更新すると、DevTools でリソースが読み込まれることはありませんが、代わりにローカルコピーで置き換えられます。
title: Microsoft Edge DevTools を使用してローカルコピーで web ページのリソースを上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 579ebe92dc50571837e7e3caf8fb7c1a9989bc59
ms.sourcegitcommit: 9dcaf598f3930bcfab9f93ff63463beb98274de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145183"
---
# <span data-ttu-id="ed4cf-105">Microsoft Edge DevTools を使用してローカルコピーで web ページのリソースを上書きする</span><span class="sxs-lookup"><span data-stu-id="ed4cf-105">Override webpage resources with local copies using Microsoft Edge DevTools</span></span>  

<span data-ttu-id="ed4cf-106">アクセス権を持っていない web ページの問題を解決する必要があります。または、修復が複雑で複雑なビルドプロセスが含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-106">Sometimes you need to fix a problem on a webpage that you do not have access to or fixes involve a slow and complex build process.</span></span>  <span data-ttu-id="ed4cf-107">DevTools では、すべての種類の問題をデバッグして修正することができます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-107">You may debug and fix all kind of problems in DevTools.</span></span> <span data-ttu-id="ed4cf-108">ただし、この変更は保存されません。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-108">But the problem is the changes do not persist.</span></span>  <span data-ttu-id="ed4cf-109">ファイルを更新すると、すべての作業が失われます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-109">After you refresh the file, all your work is gone.</span></span>  

<span data-ttu-id="ed4cf-110">[ソース][DevToolsSourcesTool]ツールの上書き機能は、この問題を解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-110">The Overrides feature in the [Sources][DevToolsSourcesTool] tool helps you solve this problem.</span></span>  

<span data-ttu-id="ed4cf-111">現在の web ページのリソースを取得して、ローカルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-111">You may now take a resource of the current webpage and store it locally.</span></span>  <span data-ttu-id="ed4cf-112">Web ページを更新しても、ブラウザーによってサーバーからリソースが読み込まれることはありません。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-112">When you refresh the webpage, the browser does not load the resource from the server.</span></span>  <span data-ttu-id="ed4cf-113">代わりに、ブラウザーによってリソースのローカルコピーで置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-113">Instead the browser replaces it with your local copy of the resource.</span></span>  

## <span data-ttu-id="ed4cf-114">上書きを保存するためのローカルフォルダーの設定</span><span class="sxs-lookup"><span data-stu-id="ed4cf-114">Setting up your local folder to store Overrides</span></span>  

1.  <span data-ttu-id="ed4cf-115">**ソース**ツールで、左側にあるいくつかのセクションを検索します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-115">In the **Sources** tool, find several sections on the left-hand side.</span></span>  <span data-ttu-id="ed4cf-116">[ **上書き** ] オプションが表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="ed4cf-116">If the **Overrides** option is not displayed, choose the</span></span> <code>&#x0226B;</code><!--`≫`--> <span data-ttu-id="ed4cf-117">アイコンを選びます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-117">icon to get there.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             <span data-ttu-id="ed4cf-119">[上書き] オプションを表示するための十分な領域がない**ソース**ツール</span><span class="sxs-lookup"><span data-stu-id="ed4cf-119">**Sources** tool with not enough space to show the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="[上書き] オプションを選ぶ" lightbox="../media/javascript-overrides-menu.msft.png":::
             <span data-ttu-id="ed4cf-121">[上書き] オプションを選ぶ</span><span class="sxs-lookup"><span data-stu-id="ed4cf-121">Choose the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="ed4cf-122">[ **上書き** ] オプションを選んだら、置換するリソースファイルを保存するローカルコンピューター上のフォルダーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-122">After you choose the **Overrides** option, you must choose a folder on your local computer to store the resource files that you want to replace.</span></span>  <span data-ttu-id="ed4cf-123">フォルダーを検索するには、[ **上書き用の + 選択] フォルダー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-123">Choose the **+ Select folder for overrides** to search for a folder.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="上書きに使用するフォルダーを選択する" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       <span data-ttu-id="ed4cf-125">上書きに使用するフォルダーを選択する</span><span class="sxs-lookup"><span data-stu-id="ed4cf-125">Choose a folder to use for overrides</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ed4cf-126">DevTools は、フォルダーへのフルアクセス権が必要であることを警告し、機密情報を表示しないようにします。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-126">DevTools warns you that must have full access to the folder and that you should not reveal any sensitive information.</span></span>  <span data-ttu-id="ed4cf-127">警告バーで、[ **許可** ] を選択してアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-127">On the warning bar, choose **Allow** to grant access.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="フォルダーへの DevTools アクセスの許可" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       <span data-ttu-id="ed4cf-129">フォルダーへの DevTools アクセスの許可</span><span class="sxs-lookup"><span data-stu-id="ed4cf-129">Grant DevTools access to folder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ed4cf-130">[ **上書き** ] ウィンドウで、[] と [上書き] フォルダーの横に checkbox が表示され `Enable Local Overrides` ます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-130">In the **Overrides** pane, a checkbox should be displayed next to `Enable Local Overrides` and your overrides folder.</span></span>  <span data-ttu-id="ed4cf-131">横にアイコンが表示され、ローカルの上書き設定を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-131">An icon is displayed next to it that allows you to delete your local overrides settings.</span></span>  <span data-ttu-id="ed4cf-132">これで、フォルダーの設定が完了し、ライブリソースをローカルのリソースに置き換える準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-132">You are now done setting up your folder and ready to replace live resources with local ones.</span></span>
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="上書きフォルダーの設定が完了しました" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       <span data-ttu-id="ed4cf-134">上書きフォルダーの設定が完了しました</span><span class="sxs-lookup"><span data-stu-id="ed4cf-134">Successful set up of an overrides folder</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ed4cf-135">上書きフォルダーにファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="ed4cf-135">Adding files to your Overrides folder</span></span>  
  
<span data-ttu-id="ed4cf-136">上書きフォルダーにファイルを追加するには、 **要素** ツールを開いて、web ページを調べます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-136">To add files to your overrides folder, open the **Elements** tool and inspect the webpage.</span></span>  <span data-ttu-id="ed4cf-137">編集するには、 **スタイル** インスペクターで CSS ファイルの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-137">To edit, choose the name of the CSS file in the **Styles** inspector.</span></span>  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="[スタイルインスペクター] でファイルを選ぶ" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   <span data-ttu-id="ed4cf-139">[ **スタイル** インスペクター] でファイルを選ぶ</span><span class="sxs-lookup"><span data-stu-id="ed4cf-139">Choose a file in the **Styles** inspector</span></span>  
:::image-end:::  

<span data-ttu-id="ed4cf-140">**ソース**エディターで、選択したファイルのファイル名にポインターを置いて、コンテキストメニュー \ (右クリック \) を開き、[**上書き用に保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-140">On the **Sources** editor, hover on the file name of your chosen file, open the contextual menu \(right-click\), and choose **Save for overrides**.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="ソースエディターで、上書きするファイルの名前を追加します。" lightbox="../media/javascript-overrides-file-name.msft.png":::
   <span data-ttu-id="ed4cf-142">**ソース**エディターで、上書きするファイルの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-142">In the **Sources** editor, add the name of the file to overrides</span></span>  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="コンテキストメニューで、[上書き用に保存] を選択します。" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   <span data-ttu-id="ed4cf-144">コンテキストメニューで、[**上書き用に保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-144">On the context menu, choose **Save for overrides**</span></span>  
:::image-end:::  

<span data-ttu-id="ed4cf-145">ファイルは [上書き] フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-145">The file is stored in your overrides folder.</span></span>  <span data-ttu-id="ed4cf-146">DevTools で、ディレクトリ構造が適切なファイルの URL を使用して名前が付けられたフォルダーを作成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-146">Verify that DevTools create a folder that is named using the URL of the file with the correct directory structure.</span></span>  <span data-ttu-id="ed4cf-147">ファイルは内部に保存されています。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-147">The file is stored inside.</span></span>  <span data-ttu-id="ed4cf-148">エディターのファイル名には、ファイルがローカルであり、ライブではないことを示す紫色のドットも表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-148">The file name in the editor now also shows a purple dot that indicates that the file is local and not a live one.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="上書きフォルダーにファイルが正常に保存されました" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   <span data-ttu-id="ed4cf-150">上書きフォルダーにファイルが正常に保存されました</span><span class="sxs-lookup"><span data-stu-id="ed4cf-150">Successfully stored the file in your overrides folder</span></span>  
:::image-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="ed4cf-151">次の例では、web ページのスタイルを変更できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-151">In the following example, you may now change the styles of the webpage.</span></span>  <span data-ttu-id="ed4cf-152">ファイルの周囲に赤い境界線を追加するには、[ **スタイル** エディター] で次のスタイルをコピーして本文要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-152">To add a red border around the file, on the **Styles** editor, copy the following style, and add it to the body element.</span></span>  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="ed4cf-153">ファイルはコンピューターに自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-153">The file is automatically saved on your computer.</span></span>  <span data-ttu-id="ed4cf-154">ファイルを更新すると、枠線が表示され、作業内容が失われることはありません。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-154">If you refresh the file, the border is displayed and none of your work is lost.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="上書きフォルダー内のファイルを編集して、web ページのスタイルを永続的に変更する" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         <span data-ttu-id="ed4cf-156">上書きフォルダー内のファイルを編集して、web ページのスタイルを永続的に変更する</span><span class="sxs-lookup"><span data-stu-id="ed4cf-156">Change webpage styles persistently by editing a file in your overrides folder</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="ed4cf-157">**ソース**ツールの [**ページ**] セクションで、任意のファイルをポイントし、コンテキストメニュー \ (右クリック \) を開き、[上書き] に追加します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-157">On the **Sources** tool, in the **Page** section, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="ed4cf-158">この場合も、[上書き] フォルダーに既にあるファイルのアイコンに紫色のドットが付いています。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-158">Again, files that are already in your overrides folder have a purple dot on the icon.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="上書き用のソースツールからファイルを選ぶ" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         <span data-ttu-id="ed4cf-160">上書き用の **ソース** ツールからファイルを選ぶ</span><span class="sxs-lookup"><span data-stu-id="ed4cf-160">Choose a file from the **Sources** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="ed4cf-161">または、 **ネットワーク** ツールで任意のファイルをポイントし、コンテキストメニューを開き (\ を右クリックし)、[上書き] に追加します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-161">Alternatively, on the **Network** tool, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="ed4cf-162">上書きが有効な場合は、実際の web ページではなく、コンピューター上にあるファイル。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-162">When overrides are in effect, files that are located on your computer and not from the live webpage.</span></span>  <span data-ttu-id="ed4cf-163">上書きが有効な場合は、 **ネットワーク** ツールで、ファイル名の横にある警告アイコンを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-163">When overrides are in effect, on the **Network** tool, locate a warning icon next to the file name.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="上書き用のネットワークツールからファイルを選ぶ" lightbox="../media/javascript-overrides-network.msft.png":::
         <span data-ttu-id="ed4cf-165">上書き用の **ネットワーク** ツールからファイルを選ぶ</span><span class="sxs-lookup"><span data-stu-id="ed4cf-165">Choose a file from the **Network** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="ed4cf-166">上書きの双方向の相互作用</span><span class="sxs-lookup"><span data-stu-id="ed4cf-166">Two-way interaction of overrides</span></span>  

<span data-ttu-id="ed4cf-167">DevTools の **ソース** ツール、またはファイルを変更するエディターで提供されるエディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-167">Use the editor provided with the **Sources** tool of DevTools or any editor you want to change the files.</span></span>  <span data-ttu-id="ed4cf-168">変更は、上書きフォルダー内のファイルにアクセスするすべての製品間で同期されます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-168">Changes are synced across all the products that access the files in the overrides folder.</span></span>  

## <span data-ttu-id="ed4cf-169">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="ed4cf-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources.md "ソースツールの概要 |Microsoft ドキュメント"  
