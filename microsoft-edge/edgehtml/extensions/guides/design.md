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
# Microsoft Edge 拡張機能の設計ガイドライン  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

次のページには、Microsoft Edge 拡張機能を作成する際に考慮すべきさまざまな設計上の側面と UI の動作が含まれます。  

## アイコン  

ベクター グラフィックを使用して拡張機能のアイコンを作成する必要があります。  拡張機能をパッケージ化する場合は、拡張機能用にアイコンのいくつかの異なるサイズを作成し、さらに 3 つのサイズを作成する必要があります。  Microsoft Edge 拡張機能では、.svg アイコンはサポートされていません。  

拡張機能アイコンを作成する前に、アクセシビリティ ガイド[][ExtensionsGuidesAccessibility]を確認して、アイコンのコントラストが十分に高く、Microsoft Edge の淡色テーマと濃色テーマの両方に表示される必要があります。  

Webkit 画像形式はサポートされていますが、透明度のサポートには .png アイコンをお勧めします。  

### 拡張機能のアイコン  

拡張機能の場合は、ブラウザーのアクションまたはページ アクション用に 1 つのアイコン サイズを作成し、[拡張機能] ウィンドウ用に 1 つのアイコン **サイズを作成する必要** があります。  高解像度ディスプレイをサポートするために、それぞれ複数のサイズを指定できます。  

拡張機能には、ブラウザーアクションまたはページ アクション アイコンが必要です。  ブラウザーアクションアイコンとページ アクション アイコンは、実行時に [browserAction.setIcon][MSDApiBrowseractionSeticon] メソッドまたは [pageAction.setIcon][MDNApiPageactionSeticon] メソッドを使用して変更できます。  

#### ブラウザーの操作  

ブラウザーのアクションアイコンとページ アクション アイコンの推奨サイズは `20px` 、, `25px` and `30px` `40px` .  サポートされているその他のサイズには `19px` 、 `35px` , , . `38px`  

ファイル スニペット [manifest.js次][ExtensionsApisupportManifestkeys] の例は、標準および高解像度のブラウザー アクション アイコンが、ファイル キーを使用して指定 [browser_action][MDNManifestjsonBrowserAction] しています。  このキーには同じ構文 [page_action][MDNManifestjsonPageAction] されます。  

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

ブラウザーの操作が拡張機能によって設定されている場合は、[その他 **](...)** を選択した後の [操作] メニューに表示され、アドレス バー**** の横にある [表示] ボタンがユーザーによってオンに切り替えらた場合は、アドレス バーの右側に表示されます。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="操作メニューでのブラウザーの操作":::
         操作メニューでのブラウザーの操作 :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="ブラウザーの操作":::
         ブラウザーの操作 :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### ページ アクション  

この [page_action][MDNManifestjsonPageAction] キーには、次のキーと同じ JSON [マニフェスト構文browser_action][MDNManifestjsonBrowserAction] があります。  ページ アクションには、ブラウザーの操作と同じアイコン サイズの要件があります。  

ページアクションがファイルのmanifest.js[ で][ExtensionsApisupportManifestkeys] 指定されている場合は [、pageAction.show][MDNApiPageactionShow] メソッドが使用されるたびにアドレス バー内に表示されます。  

:::image type="complex" source="../media/pageaction.png" alt-text="ページ アクション":::
   ページ アクション
:::image-end:::

<!--![page action][ImagePageaction]  -->  

##### 管理 UI  

ユーザーが [その他 **](...)** メニューに移動して [拡張機能]**** を選択して拡張機能ウィンドウに移動すると、拡張機能の名前の横にアイコンが表示されます。  

次のアイコン サイズを指定する必要があります。  

| キー | 詳細 |  
|:--- |:--- |  
| `48px` | 標準解像度のアイコンが表示されます。 |  
| `128px` | 高解像度表示用のアイコン。 |  
| `176px` | さらに高い解像度のアイコンが表示されます。 |  


```json
"icons": {
    "48": "images/icon_48.png",
    "128": "images/icon_128.png",
    "176": "images/icon_176.png"
},
```  

:::image type="complex" source="../media/management-ui.png" alt-text="管理 UI":::
   管理 UI
:::image-end:::

<!--![management UI][ImageManagementUi]  -->  

### パッケージ化用のアイコン  

拡張機能をパッケージ化する準備ができたら、追加のアイコン サイズを 3 つ用意する必要があります。  

| Size | 詳細 |  
|:--- |:--- |  
| 44px | Windows UI \( App**List**, **Settings**  \>  **System**  \>  Apps & features \)**で使用**されます。 |  
| 50px | パッケージ化要件 \(どこにも表示されない\)。 |  
| 150px | Microsoft Store のアイコンとして使用されます。 |  


これらのアイコンが [配置されている場所を][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] 判断するには、手動パッケージ [ガイドまたは、1][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] つ以上のガイドを参照してください。  これは、選択するパッケージ化方法によって異なります。  

#### Microsoft Store アイコン  

Microsoft Store の 150 ピクセルのアイコンに背景が透明な場合、ユーザーのデバイスのアクセント カラーがアイコンの背景色として表示されます。  

たとえば、ユーザーがアクセント カラーとしてピンクを選択した場合、ストア アイコンの透明な背景はピンクとして表示されます。  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="Windows のアクセント カラー":::
          Windows のアクセント カラー :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="背景色の自動選択":::
         背景色の自動選択 :::image-end:::
      
      <!--![Background color auto selected][ImageStoreIconTransparencyBackground]  -->  
   :::column-end:::
:::row-end:::

Microsoft Store 用に独自の背景色を選ぶ場合は、背景を不透明にする必要があります。  

> [!NOTE]
> Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。  Microsoft [Store][AkaExtensionRequest]に関するリクエストをお問い合わせください。お問い合わせは今後の更新と見なされます。  

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
