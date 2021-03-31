---
description: Microsoft Edge 拡張機能を作成するときに考慮するさまざまな設計側面と UI 動作について説明します。
title: 拡張機能 - 設計
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, javascript, デザイン, アイコン, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a32223f93baf44d2ca523e92cf9d7584ad9a8333
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234957"
---
# <span data-ttu-id="6746a-104">Microsoft Edge 拡張機能の設計ガイドライン</span><span class="sxs-lookup"><span data-stu-id="6746a-104">Design Guidelines For Microsoft Edge Extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="6746a-105">次のページには、Microsoft Edge 拡張機能を作成する際に考慮すべきさまざまな設計上の側面と UI の動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6746a-105">The following page contains various design aspects and UI behavior to consider when creating Microsoft Edge extensions.</span></span>  

## <span data-ttu-id="6746a-106">アイコン</span><span class="sxs-lookup"><span data-stu-id="6746a-106">Icons</span></span>  

<span data-ttu-id="6746a-107">ベクター グラフィックを使用して拡張機能のアイコンを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6746a-107">You should make the icons of your extension using a vector graphic.</span></span>  <span data-ttu-id="6746a-108">拡張機能をパッケージ化する場合は、拡張機能用にアイコンのいくつかの異なるサイズを作成し、さらに 3 つのサイズを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6746a-108">You must create a few different sizes of your icon for your extension, and three additional sizes if you want to package your extension.</span></span>  <span data-ttu-id="6746a-109">Microsoft Edge 拡張機能では、.svg アイコンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6746a-109">Microsoft Edge extensions do not support .svg icons.</span></span>  

<span data-ttu-id="6746a-110">拡張機能アイコンを作成する前に、アクセシビリティ ガイド[][ExtensionsGuidesAccessibility]を確認して、アイコンのコントラストが十分に高く、Microsoft Edge の淡色テーマと濃色テーマの両方に表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6746a-110">Before you create your extension icons, you should review the [accessibility][ExtensionsGuidesAccessibility] guide to ensure that your icons have high enough contrast and are visible in both the light and dark themes of Microsoft Edge.</span></span>  

<span data-ttu-id="6746a-111">Webkit 画像形式はサポートされていますが、透明度のサポートには .png アイコンをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6746a-111">While any webkit image format is supported, .png icons are recommended for transparency support.</span></span>  

### <span data-ttu-id="6746a-112">拡張機能のアイコン</span><span class="sxs-lookup"><span data-stu-id="6746a-112">Icons for your extension</span></span>  

<span data-ttu-id="6746a-113">拡張機能の場合は、ブラウザーのアクションまたはページ アクション用に 1 つのアイコン サイズを作成し、[拡張機能] ウィンドウ用に 1 つのアイコン **サイズを作成する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="6746a-113">For your extension, you must create one icon size for the browser action or page action, and one icon size for the **Extensions** pane.</span></span>  <span data-ttu-id="6746a-114">高解像度ディスプレイをサポートするために、それぞれ複数のサイズを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6746a-114">More than one size for each may be provided to support high resolution displays.</span></span>  

<span data-ttu-id="6746a-115">拡張機能には、ブラウザーアクションまたはページ アクション アイコンが必要です。</span><span class="sxs-lookup"><span data-stu-id="6746a-115">An extension should have a browser action or page action icon.</span></span>  <span data-ttu-id="6746a-116">ブラウザーアクションアイコンとページ アクション アイコンは、実行時に [browserAction.setIcon][MSDApiBrowseractionSeticon] メソッドまたは [pageAction.setIcon][MDNApiPageactionSeticon] メソッドを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="6746a-116">The browser action and page action icons may be changed at runtime using the [browserAction.setIcon][MSDApiBrowseractionSeticon] method or [pageAction.setIcon][MDNApiPageactionSeticon] method.</span></span>  

#### <span data-ttu-id="6746a-117">ブラウザーの操作</span><span class="sxs-lookup"><span data-stu-id="6746a-117">Browser action</span></span>  

<span data-ttu-id="6746a-118">ブラウザーのアクションアイコンとページ アクション アイコンの推奨サイズは `20px` 、, `25px` and `30px` `40px` .</span><span class="sxs-lookup"><span data-stu-id="6746a-118">The preferred sizes for browser action and page action icons are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="6746a-119">サポートされているその他のサイズには `19px` 、 `35px` , , . `38px`</span><span class="sxs-lookup"><span data-stu-id="6746a-119">Other supported sizes include `19px`, `35px`, and `38px`.</span></span>  

<span data-ttu-id="6746a-120">ファイル スニペット [manifest.js次][ExtensionsApisupportManifestkeys] の例は、標準および高解像度のブラウザー アクション アイコンが、ファイル キーを使用して指定 [browser_action][MDNManifestjsonBrowserAction] しています。</span><span class="sxs-lookup"><span data-stu-id="6746a-120">The following [manifest.json][ExtensionsApisupportManifestkeys] file snippet shows a standard and high definition browser action icon being specified using the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="6746a-121">このキーには同じ構文 [page_action][MDNManifestjsonPageAction] されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-121">The same syntax applies for the [page_action][MDNManifestjsonPageAction] key.</span></span>  

```json
"browser_action": {
    "default_icon": {
        "20": "images/icon_20.png",
        "40": "images/icon_40.png"
    },
    "default_title": "Fetch page info",
    "default_popup": "popup.html"
}
```  

<span data-ttu-id="6746a-122">ブラウザーの操作が拡張機能によって設定されている場合は、[その他 ](...) を選択した後の [操作] メニューに表示され、アドレス バー の横にある [表示] ボタンがユーザーによってオンに切り替えらた場合は、アドレス バーの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-122">If the browser action has been set by the extension, it appears either in the Actions menu after selecting **More(...)**,  or to the right of the address bar if **Show button next to the address bar** has been toggled on by the user.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="操作メニューでのブラウザーの操作":::
         <span data-ttu-id="6746a-124">操作メニューでのブラウザーの操作</span><span class="sxs-lookup"><span data-stu-id="6746a-124">Browser action in action menu</span></span> :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="ブラウザーの操作":::
         <span data-ttu-id="6746a-126">ブラウザーの操作</span><span class="sxs-lookup"><span data-stu-id="6746a-126">Browser action</span></span> :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### <span data-ttu-id="6746a-127">ページ アクション</span><span class="sxs-lookup"><span data-stu-id="6746a-127">Page action</span></span>  

<span data-ttu-id="6746a-128">この [page_action][MDNManifestjsonPageAction] キーには、次のキーと同じ JSON [マニフェスト構文browser_action][MDNManifestjsonBrowserAction] があります。</span><span class="sxs-lookup"><span data-stu-id="6746a-128">The [page_action][MDNManifestjsonPageAction] key has the same JSON manifest syntax as the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="6746a-129">ページ アクションには、ブラウザーの操作と同じアイコン サイズの要件があります。</span><span class="sxs-lookup"><span data-stu-id="6746a-129">Page action also has the same icon size requirements as browser action.</span></span>  

<span data-ttu-id="6746a-130">ページアクションがファイルのmanifest.js[ で][ExtensionsApisupportManifestkeys] 指定されている場合は [、pageAction.show][MDNApiPageactionShow] メソッドが使用されるたびにアドレス バー内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-130">If page action is specified in the [manifest.json][ExtensionsApisupportManifestkeys] file, it appears within the address bar whenever the [pageAction.show][MDNApiPageactionShow] method is used.</span></span>  

:::image type="complex" source="../media/pageaction.png" alt-text="ページ アクション":::
   <span data-ttu-id="6746a-132">ページ アクション</span><span class="sxs-lookup"><span data-stu-id="6746a-132">Page action</span></span>
:::image-end:::

<!--![page action][ImagePageaction]  -->  

##### <span data-ttu-id="6746a-133">管理 UI</span><span class="sxs-lookup"><span data-stu-id="6746a-133">Management UI</span></span>  

<span data-ttu-id="6746a-134">ユーザーが [その他 ](...) メニューに移動して [拡張機能] を選択して拡張機能ウィンドウに移動すると、拡張機能の名前の横にアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-134">When users navigate to the extensions pane by going to the **More(...)** menu and selecting **Extensions**, an icon is displayed next to the name of the extension.</span></span>  

<span data-ttu-id="6746a-135">次のアイコン サイズを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6746a-135">You should specify the following icon sizes.</span></span>  

| <span data-ttu-id="6746a-136">キー</span><span class="sxs-lookup"><span data-stu-id="6746a-136">Key</span></span> | <span data-ttu-id="6746a-137">詳細</span><span class="sxs-lookup"><span data-stu-id="6746a-137">Details</span></span> |  
|:--- |:--- |  
| `48px` | <span data-ttu-id="6746a-138">標準解像度のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-138">Icon for standard resolution displays.</span></span> |  
| `128px` | <span data-ttu-id="6746a-139">高解像度表示用のアイコン。</span><span class="sxs-lookup"><span data-stu-id="6746a-139">Icon for high resolution displays.</span></span> |  
| `176px` | <span data-ttu-id="6746a-140">さらに高い解像度のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-140">Icon for even higher resolution displays.</span></span> |  


```json
"icons": {
    "48": "images/icon_48.png",
    "128": "images/icon_128.png",
    "176": "images/icon_176.png"
},
```  

:::image type="complex" source="../media/management-ui.png" alt-text="管理 UI":::
   <span data-ttu-id="6746a-142">管理 UI</span><span class="sxs-lookup"><span data-stu-id="6746a-142">Management UI</span></span>
:::image-end:::

<!--![management UI][ImageManagementUi]  -->  

### <span data-ttu-id="6746a-143">パッケージ化用のアイコン</span><span class="sxs-lookup"><span data-stu-id="6746a-143">Icons for packaging</span></span>  

<span data-ttu-id="6746a-144">拡張機能をパッケージ化する準備ができたら、追加のアイコン サイズを 3 つ用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6746a-144">Once your extension is ready for packaging, you must have three additional icon sizes ready.</span></span>  

| <span data-ttu-id="6746a-145">Size</span><span class="sxs-lookup"><span data-stu-id="6746a-145">Size</span></span> | <span data-ttu-id="6746a-146">詳細</span><span class="sxs-lookup"><span data-stu-id="6746a-146">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="6746a-147">44px</span><span class="sxs-lookup"><span data-stu-id="6746a-147">44px</span></span> | <span data-ttu-id="6746a-148">Windows UI \( App**List**, **Settings**  \>  **System**  \>  Apps & features \)**で使用**されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-148">Used in the Windows UI \(**App List**, **Settings** \> **System** \> **Apps & features**\).</span></span> |  
| <span data-ttu-id="6746a-149">50px</span><span class="sxs-lookup"><span data-stu-id="6746a-149">50px</span></span> | <span data-ttu-id="6746a-150">パッケージ化要件 \(どこにも表示されない\)。</span><span class="sxs-lookup"><span data-stu-id="6746a-150">Packaging requirement \(not visible anywhere\).</span></span> |  
| <span data-ttu-id="6746a-151">150px</span><span class="sxs-lookup"><span data-stu-id="6746a-151">150px</span></span> | <span data-ttu-id="6746a-152">Microsoft Store のアイコンとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-152">Used as the icon for the Microsoft Store.</span></span> |  


<span data-ttu-id="6746a-153">これらのアイコンが [配置されている場所を][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] 判断するには、手動パッケージ [ガイドまたは、1][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] つ以上のガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6746a-153">See either the [manual packaging guide][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] or the [ManifoldJS packaging guide][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] to determine where these icons is placed.</span></span>  <span data-ttu-id="6746a-154">これは、選択するパッケージ化方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6746a-154">This depends upon which packaging method you choose.</span></span>  

#### <span data-ttu-id="6746a-155">Microsoft Store アイコン</span><span class="sxs-lookup"><span data-stu-id="6746a-155">Microsoft Store icon</span></span>  

<span data-ttu-id="6746a-156">Microsoft Store の 150 ピクセルのアイコンに背景が透明な場合、ユーザーのデバイスのアクセント カラーがアイコンの背景色として表示されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-156">If the 150px icon for the Microsoft Store has a transparent background, the accent color of the user's device appears as the background color of the icon.</span></span>  

<span data-ttu-id="6746a-157">たとえば、ユーザーがアクセント カラーとしてピンクを選択した場合、ストア アイコンの透明な背景はピンクとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="6746a-157">For example, if a user has selected pink as the accent color, the transparent background of your store icon is displayed as pink.</span></span>  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="Windows のアクセント カラー":::
          <span data-ttu-id="6746a-159">Windows のアクセント カラー</span><span class="sxs-lookup"><span data-stu-id="6746a-159">Windows accent color</span></span> :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="背景色の自動選択":::
         <span data-ttu-id="6746a-161">背景色の自動選択</span><span class="sxs-lookup"><span data-stu-id="6746a-161">Background color auto selected</span></span> :::image-end:::
      
      <!--![Background color auto selected][ImageStoreIconTransparencyBackground]  -->  
   :::column-end:::
:::row-end:::

<span data-ttu-id="6746a-162">Microsoft Store 用に独自の背景色を選ぶ場合は、背景を不透明にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6746a-162">If you want to pick your own background color for your Microsoft Store, you must make the background opaque.</span></span>  

> [!NOTE]
> <span data-ttu-id="6746a-163">Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="6746a-163">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="6746a-164">Microsoft [Store][AkaExtensionRequest]に関するリクエストをお問い合わせください。お問い合わせは今後の更新と見なされます。</span><span class="sxs-lookup"><span data-stu-id="6746a-164">[Contact us][AkaExtensionRequest] with your requests for the Microsoft Store, and your request is considered for a future update.</span></span>  

<!-- image links -->  

<!--[ImageActionmenuBrowseraction]: ../media/actionmenu-browseraction.png "browser action in action menu"  -->  
<!--[ImageBrowserActionIcon]: ../media/browseractionicon.png "browser action"  -->  
<!--[ImagePageaction]: ../media/pageaction.png "page action"  -->  
<!--[ImageManagementUi]: ../media/management-ui.png "management UI"  -->  
<!--[ImageWindowsAccentColor]: ../media/windows-accent-color.png "Windows accent color"  -->  
<!--[ImageStoreIconTransparencyBackground]: ../media/store-icon-with-transparent-background.png "Background color auto selected"  -->  

<!-- links -->  

[ExtensionsGuidesAccessibility]: ./accessibility.md "アクセシビリティ |Microsoft Docs"  
[ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder]: ./packaging/creating-and-testing-extension-packages.md#assets-folder "Assets フォルダー - Microsoft Edge Extension AppX パッケージの作成とテスト |Microsoft Docs"  
[ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs]: ./packaging/using-manifoldjs-to-package-extensions.md#packaging-with-manifoldjs "Packaging with ManifoldJS - Using ManifoldJS to create Extension AppX Packages |Microsoft Docs"  

[ExtensionsApisupportManifestkeys]: ../API-support/supported-manifest-keys.md "サポートされているマニフェスト キー |Microsoft Docs"  

[AkaExtensionRequest]: https://aka.ms/extension-request "お問い合わせ"  

[MSDApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction.setIcon() - API |MDN"  
[MDNApiPageactionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/setIcon "pageAction.setIcon() - API |MDN"  
[MDNApiPageactionShow]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/show "pageAction.show() - API |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action "browser_action - manifest.json |MDN"  
[MDNManifestjsonPageAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action "page_action - manifest.json |MDN"  
