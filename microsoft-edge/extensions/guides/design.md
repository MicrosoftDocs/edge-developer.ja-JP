---
description: Microsoft Edge 拡張機能を作成するときに考慮するさまざまな設計面と UI の動作について説明します。
title: 拡張機能-デザイン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、javascript、デザイン、アイコン、開発者
ms.openlocfilehash: 622d72453ea3ecd2897efcf8f67e1b2aa7a0937c
ms.sourcegitcommit: da768193c7ae7b611f4fbb1746f16d9818e42bac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684065"
---
# <span data-ttu-id="e7c8a-104">Microsoft Edge Extensions の設計ガイドライン</span><span class="sxs-lookup"><span data-stu-id="e7c8a-104">Design Guidelines For Microsoft Edge Extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="e7c8a-105">次のページでは、Microsoft Edge extensions の作成時に考慮する必要がある、さまざまな設計面と UI の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-105">The following page contains various design aspects and UI behavior to consider when creating Microsoft Edge extensions.</span></span>  

## <span data-ttu-id="e7c8a-106">アイコン</span><span class="sxs-lookup"><span data-stu-id="e7c8a-106">Icons</span></span>  

<span data-ttu-id="e7c8a-107">ベクターグラフィックスを使って、拡張機能のアイコンを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-107">You should make the icons of your extension using a vector graphic.</span></span>  <span data-ttu-id="e7c8a-108">内線番号には、さまざまなサイズのアイコンを作成し、拡張機能をパッケージ化する場合は、3つのサイズを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-108">You must create a few different sizes of your icon for your extension, and three additional sizes if you want to package your extension.</span></span>  <span data-ttu-id="e7c8a-109">Microsoft Edge extensions は、svg アイコンをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-109">Microsoft Edge extensions do not support .svg icons.</span></span>  

<span data-ttu-id="e7c8a-110">拡張機能のアイコンを作成する前に、[アクセシビリティ][ExtensionsGuidesAccessibility]ガイドを確認して、アイコンのコントラストが十分であり、Microsoft Edge の淡色表示と濃色テーマの両方で表示されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-110">Before you create your extension icons, you should review the [accessibility][ExtensionsGuidesAccessibility] guide to ensure that your icons have high enough contrast and are visible in both the light and dark themes of Microsoft Edge.</span></span>  

<span data-ttu-id="e7c8a-111">Webkit の画像形式はいずれもサポートされていますが、透明度のサポートには .png アイコンが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-111">While any webkit image format is supported, .png icons are recommended for transparency support.</span></span>  

### <span data-ttu-id="e7c8a-112">拡張機能のアイコン</span><span class="sxs-lookup"><span data-stu-id="e7c8a-112">Icons for your extension</span></span>  

<span data-ttu-id="e7c8a-113">拡張機能については、ブラウザーのアクションまたはページのアクションのアイコンサイズと、[**拡張機能**] ウィンドウのアイコンのサイズを1つ作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-113">For your extension, you must create one icon size for the browser action or page action, and one icon size for the **Extensions** pane.</span></span>  <span data-ttu-id="e7c8a-114">高解像度ディスプレイをサポートするために、それぞれに1つ以上のサイズが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-114">More than one size for each may be provided to support high resolution displays.</span></span>  

<span data-ttu-id="e7c8a-115">拡張子には、ブラウザーのアクションアイコンまたはページ操作アイコンが必要です。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-115">An extension should have a browser action or page action icon.</span></span>  <span data-ttu-id="e7c8a-116">ブラウザーのアクションアイコンとページ操作アイコンは、 [setIcon][MSDApiBrowseractionSeticon]メソッドまたは[setIcon][MDNApiPageactionSeticon]メソッドを使って、実行時に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-116">The browser action and page action icons may be changed at runtime using the [browserAction.setIcon][MSDApiBrowseractionSeticon] method or [pageAction.setIcon][MDNApiPageactionSeticon] method.</span></span>  

#### <span data-ttu-id="e7c8a-117">ブラウザーのアクション</span><span class="sxs-lookup"><span data-stu-id="e7c8a-117">Browser action</span></span>  

<span data-ttu-id="e7c8a-118">ブラウザーのアクションアイコンとページ操作アイコンには、、、、という優先サイズがあり `20px` `25px` `30px` `40px` ます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-118">The preferred sizes for browser action and page action icons are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="e7c8a-119">サポートされているその他のサイズには、、、、があり `19px` `35px` `38px` ます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-119">Other supported sizes include `19px`, `35px`, and `38px`.</span></span>  

<span data-ttu-id="e7c8a-120">次の[manifest.xml][ExtensionsApisupportManifestkeys]ファイルスニペットは、 [browser_action][MDNManifestjsonBrowserAction]キーを使用して指定された、標準および high definition browser アクションアイコンを示しています。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-120">The following [manifest.json][ExtensionsApisupportManifestkeys] file snippet shows a standard and high definition browser action icon being specified using the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="e7c8a-121">[Page_action][MDNManifestjsonPageAction]キーにも同じ構文が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-121">The same syntax applies for the [page_action][MDNManifestjsonPageAction] key.</span></span>  

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

<span data-ttu-id="e7c8a-122">ブラウザーのアクションが拡張機能によって設定されている場合は、[詳細] **(...)** を選択した後に [操作] メニューに表示されるか、アドレスバーの横にある [**表示] ボタン**がユーザーによってオンにされた場合は、アドレスバーの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-122">If the browser action has been set by the extension, it appears either in the Actions menu after selecting **More(...)**,  or to the right of the address bar if **Show button next to the address bar** has been toggled on by the user.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="アクションメニューのブラウザアクション":::
         <span data-ttu-id="e7c8a-124">アクションメニューのブラウザアクション</span><span class="sxs-lookup"><span data-stu-id="e7c8a-124">Browser action in action menu</span></span> :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="ブラウザーのアクション":::
         <span data-ttu-id="e7c8a-126">ブラウザーのアクション</span><span class="sxs-lookup"><span data-stu-id="e7c8a-126">Browser action</span></span> :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### <span data-ttu-id="e7c8a-127">ページのアクション</span><span class="sxs-lookup"><span data-stu-id="e7c8a-127">Page action</span></span>  

<span data-ttu-id="e7c8a-128">[Page_action][MDNManifestjsonPageAction]キーの JSON マニフェスト構文は、 [browser_action][MDNManifestjsonBrowserAction]キーと同じです。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-128">The [page_action][MDNManifestjsonPageAction] key has the same JSON manifest syntax as the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="e7c8a-129">ページアクションには、ブラウザーアクションと同じアイコンサイズの要件もあります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-129">Page action also has the same icon size requirements as browser action.</span></span>  

<span data-ttu-id="e7c8a-130">[Manifest.xml][ExtensionsApisupportManifestkeys]ファイルでページのアクションが指定されている場合は、ページの[アクション][MDNApiPageactionShow]が使用されるたびに、アドレスバー内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-130">If page action is specified in the [manifest.json][ExtensionsApisupportManifestkeys] file, it appears within the address bar whenever the [pageAction.show][MDNApiPageactionShow] method is used.</span></span>  

:::image type="complex" source="../media/pageaction.png" alt-text="ページのアクション":::
   <span data-ttu-id="e7c8a-132">ページのアクション</span><span class="sxs-lookup"><span data-stu-id="e7c8a-132">Page action</span></span>
:::image-end:::

<!--![page action][ImagePageaction]  -->  

##### <span data-ttu-id="e7c8a-133">管理 UI</span><span class="sxs-lookup"><span data-stu-id="e7c8a-133">Management UI</span></span>  

<span data-ttu-id="e7c8a-134">ユーザーが [**その他 (...)** ] メニューに移動し、[**拡張機能**] を選択して、[拡張機能] ウィンドウに移動すると、拡張機能の名前の横にアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-134">When users navigate to the extensions pane by going to the **More(...)** menu and selecting **Extensions**, an icon is displayed next to the name of the extension.</span></span>  

<span data-ttu-id="e7c8a-135">次のアイコンのサイズを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-135">You should specify the following icon sizes.</span></span>  

| <span data-ttu-id="e7c8a-136">Key</span><span class="sxs-lookup"><span data-stu-id="e7c8a-136">Key</span></span> | <span data-ttu-id="e7c8a-137">詳細</span><span class="sxs-lookup"><span data-stu-id="e7c8a-137">Details</span></span> |  
|:--- |:--- |  
| `48px` | <span data-ttu-id="e7c8a-138">標準解像度のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-138">Icon for standard resolution displays.</span></span> |  
| `128px` | <span data-ttu-id="e7c8a-139">高解像度のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-139">Icon for high resolution displays.</span></span> |  
| `176px` | <span data-ttu-id="e7c8a-140">さらに高い解像度のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-140">Icon for even higher resolution displays.</span></span> |  


```json
"icons": {
    "48": "images/icon_48.png",
    "128": "images/icon_128.png",
    "176": "images/icon_176.png"
},
```  

:::image type="complex" source="../media/management-ui.png" alt-text="管理 UI":::
   <span data-ttu-id="e7c8a-142">管理 UI</span><span class="sxs-lookup"><span data-stu-id="e7c8a-142">Management UI</span></span>
:::image-end:::

<!--![management UI][ImageManagementUi]  -->  

### <span data-ttu-id="e7c8a-143">パッケージ化のアイコン</span><span class="sxs-lookup"><span data-stu-id="e7c8a-143">Icons for packaging</span></span>  

<span data-ttu-id="e7c8a-144">拡張機能をパッケージ化する準備ができたら、さらに3つのアイコンのサイズを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-144">Once your extension is ready for packaging, you must have three additional icon sizes ready.</span></span>  

| <span data-ttu-id="e7c8a-145">Size</span><span class="sxs-lookup"><span data-stu-id="e7c8a-145">Size</span></span> | <span data-ttu-id="e7c8a-146">詳細</span><span class="sxs-lookup"><span data-stu-id="e7c8a-146">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="e7c8a-147">44 px</span><span class="sxs-lookup"><span data-stu-id="e7c8a-147">44px</span></span> | <span data-ttu-id="e7c8a-148">Windows UI \ (**アプリ一覧**、**設定**  \>  **システム**  \>  **アプリ & 機能**) で使われます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-148">Used in the Windows UI \(**App List**, **Settings** \> **System** \> **Apps & features**\).</span></span> |  
| <span data-ttu-id="e7c8a-149">50px</span><span class="sxs-lookup"><span data-stu-id="e7c8a-149">50px</span></span> | <span data-ttu-id="e7c8a-150">パッケージ化の要件 \ (どこにも表示されません)。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-150">Packaging requirement \(not visible anywhere\).</span></span> |  
| <span data-ttu-id="e7c8a-151">150px</span><span class="sxs-lookup"><span data-stu-id="e7c8a-151">150px</span></span> | <span data-ttu-id="e7c8a-152">Microsoft Store のアイコンとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-152">Used as the icon for the Microsoft Store.</span></span> |  


<span data-ttu-id="e7c8a-153">これらのアイコンが配置されている場所を確認するには、[マニュアルパッケージガイド][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder]または[ManifoldJS パッケージガイド][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-153">See either the [manual packaging guide][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] or the [ManifoldJS packaging guide][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] to determine where these icons is placed.</span></span>  <span data-ttu-id="e7c8a-154">これは、どのパッケージ方法を選択するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-154">This depends upon which packaging method you choose.</span></span>  

#### <span data-ttu-id="e7c8a-155">Microsoft Store アイコン</span><span class="sxs-lookup"><span data-stu-id="e7c8a-155">Microsoft Store icon</span></span>  

<span data-ttu-id="e7c8a-156">Microsoft Store の [150px] アイコンに透明の背景が設定されている場合は、ユーザーのデバイスのアクセントカラーがアイコンの背景色として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-156">If the 150px icon for the Microsoft Store has a transparent background, the accent color of the user's device appears as the background color of the icon.</span></span>  

<span data-ttu-id="e7c8a-157">たとえば、ユーザーが色付きの色としてピンクを選択した場合、ストアアイコンの透明な背景はピンクとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-157">For example, if a user has selected pink as the accent color, the transparent background of your store icon is displayed as pink.</span></span>  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="Windows アクセントカラー":::
          <span data-ttu-id="e7c8a-159">Windows アクセントカラー</span><span class="sxs-lookup"><span data-stu-id="e7c8a-159">Windows accent color</span></span> :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="自動選択された背景色":::
         <span data-ttu-id="e7c8a-161">自動選択された背景色</span><span class="sxs-lookup"><span data-stu-id="e7c8a-161">Background color auto selected</span></span> :::image-end:::
      
      <!--![Background color auto selected][ImageStoreIconTransparencyBackground]  -->  
   :::column-end:::
:::row-end:::

<span data-ttu-id="e7c8a-162">Microsoft Store の独自の背景色を選ぶ場合は、背景を不透明にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-162">If you want to pick your own background color for your Microsoft Store, you must make the background opaque.</span></span>  

> [!NOTE]
> <span data-ttu-id="e7c8a-163">Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-163">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="e7c8a-164">Microsoft ストアのリクエストについてお[問い合わせ][AkaExtensionRequest]ください。お客さまのご要望は、今後の更新プログラムであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="e7c8a-164">[Contact us][AkaExtensionRequest] with your requests for the Microsoft Store, and your request is considered for a future update.</span></span>  

<!-- image links -->  

<!--[ImageActionmenuBrowseraction]: ../media/actionmenu-browseraction.png "browser action in action menu"  -->  
<!--[ImageBrowserActionIcon]: ../media/browseractionicon.png "browser action"  -->  
<!--[ImagePageaction]: ../media/pageaction.png "page action"  -->  
<!--[ImageManagementUi]: ../media/management-ui.png "management UI"  -->  
<!--[ImageWindowsAccentColor]: ../media/windows-accent-color.png "Windows accent color"  -->  
<!--[ImageStoreIconTransparencyBackground]: ../media/store-icon-with-transparent-background.png "Background color auto selected"  -->  

<!-- links -->  

[ExtensionsGuidesAccessibility]: ./accessibility.md "アクセシビリティ |Microsoft ドキュメント"  
[ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder]: ./packaging/creating-and-testing-extension-packages.md#assets-folder "[アセット] フォルダー-Microsoft Edge 拡張機能 AppX パッケージの作成とテスト |Microsoft ドキュメント"  
[ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs]: ./packaging/using-manifoldjs-to-package-extensions.md#packaging-with-manifoldjs "ManifoldJS によるパッケージ化-ManifoldJS を使って拡張 AppX パッケージを作成する |Microsoft ドキュメント"  

[ExtensionsApisupportManifestkeys]: ../API-support/supported-manifest-keys.md "サポートされているマニフェストキー |Microsoft ドキュメント"  

[AkaExtensionRequest]: https://aka.ms/extension-request "Skype に連絡する"  

[MSDApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction ()-API |MDN"  
[MDNApiPageactionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/setIcon "pageAction ()-API |MDN"  
[MDNApiPageactionShow]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/show "pageAction. show ()-API |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action "browser_action-manifest |MDN"  
[MDNManifestjsonPageAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action "page_action-manifest |MDN"  
