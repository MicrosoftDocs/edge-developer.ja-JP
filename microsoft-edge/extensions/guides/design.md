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
# Microsoft Edge Extensions の設計ガイドライン  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

次のページでは、Microsoft Edge extensions の作成時に考慮する必要がある、さまざまな設計面と UI の動作について説明します。  

## アイコン  

ベクターグラフィックスを使って、拡張機能のアイコンを作成する必要があります。  内線番号には、さまざまなサイズのアイコンを作成し、拡張機能をパッケージ化する場合は、3つのサイズを追加する必要があります。  Microsoft Edge extensions は、svg アイコンをサポートしていません。  

拡張機能のアイコンを作成する前に、[アクセシビリティ][ExtensionsGuidesAccessibility]ガイドを確認して、アイコンのコントラストが十分であり、Microsoft Edge の淡色表示と濃色テーマの両方で表示されていることを確認する必要があります。  

Webkit の画像形式はいずれもサポートされていますが、透明度のサポートには .png アイコンが推奨されます。  

### 拡張機能のアイコン  

拡張機能については、ブラウザーのアクションまたはページのアクションのアイコンサイズと、[**拡張機能**] ウィンドウのアイコンのサイズを1つ作成する必要があります。  高解像度ディスプレイをサポートするために、それぞれに1つ以上のサイズが提供されます。  

拡張子には、ブラウザーのアクションアイコンまたはページ操作アイコンが必要です。  ブラウザーのアクションアイコンとページ操作アイコンは、 [setIcon][MSDApiBrowseractionSeticon]メソッドまたは[setIcon][MDNApiPageactionSeticon]メソッドを使って、実行時に変更される可能性があります。  

#### ブラウザーのアクション  

ブラウザーのアクションアイコンとページ操作アイコンには、、、、という優先サイズがあり `20px` `25px` `30px` `40px` ます。  サポートされているその他のサイズには、、、、があり `19px` `35px` `38px` ます。  

次の[manifest.xml][ExtensionsApisupportManifestkeys]ファイルスニペットは、 [browser_action][MDNManifestjsonBrowserAction]キーを使用して指定された、標準および high definition browser アクションアイコンを示しています。  [Page_action][MDNManifestjsonPageAction]キーにも同じ構文が適用されます。  

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

ブラウザーのアクションが拡張機能によって設定されている場合は、[詳細] **(...)** を選択した後に [操作] メニューに表示されるか、アドレスバーの横にある [**表示] ボタン**がユーザーによってオンにされた場合は、アドレスバーの右側に表示されます。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="アクションメニューのブラウザアクション":::
         アクションメニューのブラウザアクション :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="ブラウザーのアクション":::
         ブラウザーのアクション :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### ページのアクション  

[Page_action][MDNManifestjsonPageAction]キーの JSON マニフェスト構文は、 [browser_action][MDNManifestjsonBrowserAction]キーと同じです。  ページアクションには、ブラウザーアクションと同じアイコンサイズの要件もあります。  

[Manifest.xml][ExtensionsApisupportManifestkeys]ファイルでページのアクションが指定されている場合は、ページの[アクション][MDNApiPageactionShow]が使用されるたびに、アドレスバー内に表示されます。  

:::image type="complex" source="../media/pageaction.png" alt-text="ページのアクション":::
   ページのアクション
:::image-end:::

<!--![page action][ImagePageaction]  -->  

##### 管理 UI  

ユーザーが [**その他 (...)** ] メニューに移動し、[**拡張機能**] を選択して、[拡張機能] ウィンドウに移動すると、拡張機能の名前の横にアイコンが表示されます。  

次のアイコンのサイズを指定する必要があります。  

| Key | 詳細 |  
|:--- |:--- |  
| `48px` | 標準解像度のアイコンが表示されます。 |  
| `128px` | 高解像度のアイコンが表示されます。 |  
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

### パッケージ化のアイコン  

拡張機能をパッケージ化する準備ができたら、さらに3つのアイコンのサイズを用意する必要があります。  

| Size | 詳細 |  
|:--- |:--- |  
| 44 px | Windows UI \ (**アプリ一覧**、**設定**  \>  **システム**  \>  **アプリ & 機能**) で使われます。 |  
| 50px | パッケージ化の要件 \ (どこにも表示されません)。 |  
| 150px | Microsoft Store のアイコンとして使用されます。 |  


これらのアイコンが配置されている場所を確認するには、[マニュアルパッケージガイド][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder]または[ManifoldJS パッケージガイド][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs]を参照してください。  これは、どのパッケージ方法を選択するかによって異なります。  

#### Microsoft Store アイコン  

Microsoft Store の [150px] アイコンに透明の背景が設定されている場合は、ユーザーのデバイスのアクセントカラーがアイコンの背景色として表示されます。  

たとえば、ユーザーが色付きの色としてピンクを選択した場合、ストアアイコンの透明な背景はピンクとして表示されます。  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="Windows アクセントカラー":::
          Windows アクセントカラー :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="自動選択された背景色":::
         自動選択された背景色 :::image-end:::
      
      <!--![Background color auto selected][ImageStoreIconTransparencyBackground]  -->  
   :::column-end:::
:::row-end:::

Microsoft Store の独自の背景色を選ぶ場合は、背景を不透明にする必要があります。  

> [!NOTE]
> Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。  Microsoft ストアのリクエストについてお[問い合わせ][AkaExtensionRequest]ください。お客さまのご要望は、今後の更新プログラムであると見なされます。  

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
