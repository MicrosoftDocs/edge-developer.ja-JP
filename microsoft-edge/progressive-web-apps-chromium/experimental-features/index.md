---
description: Microsoft Edge for Web Apps の最新の実験的機能
title: 実験的な機能|プログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, 実験, プログレッシブ Web アプリ, Web アプリ, PWA, PWA
ms.openlocfilehash: 587797bc8577f1c1aaca42394eecb997d21e9955
ms.sourcegitcommit: f605e4e27fed88aca286f2ae236e27f9a396b517
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474975"
---
# <a name="experimental-features-in-progressive-web-apps-pwas"></a>プログレッシブ Web アプリ (PWA) の実験的な機能  

Microsoft Edge では、開発中の実験的な機能にアクセスできます。  各機能が準備完了かどうかを確認し、各機能をリリースする場合は、フィードバックを [テストして提供します](#providing-feedback-on-experimental-features)。  

実験的な機能は、Microsoft Edge のすべてのチャネルで利用できますが、最新の実験的機能は Microsoft Edge Canary チャネルでのみ利用できます。  

## <a name="turn-on-experimental-features"></a>実験的な機能を有効にする  

Microsoft Edge で \(or off\) 実験機能を有効にするには、次の手順を実行します。  
  
1.  Microsoft Edge を開きます。   
    
    > [!NOTE]
    > この記事に記載されている実験を含む Microsoft Edge バージョンを使用してください。  [実験機能 [] に移動します](#features-that-are-available-to-test)。  
    
1.  に移動します `edge://flags` 。  
1.  関連する実験に移動します。  
1.  実験の説明の横にあるドロップダウン メニューを選択し、[. `Enabled`  
    
    :::image type="complex" source="../media/turn-on-experimental-flag.png" alt-text="[有効] を選択して実験を有効にする" lightbox="../media/turn-on-experimental-flag.png":::
       [ **有効] を** 選択して実験を有効にする  
    :::image-end:::  
    
    > [!NOTE]
    > 各実験には、通常、次の値を選択するドロップダウン メニューがあります。  実験機能に実験用のエントリが含めなかった**** 場合は、コマンド ラインを使用してその機能を使用して Microsoft Edge を起動する手順が提供されます。
    > 
    > *   `Default`  
    > *   `Disabled`  
    > *   `Enabled`  
    
1.  [Microsoft Edge を再起動]。  
    
### <a name="origin-trials"></a>元の試用版  

Microsoft Edge では、特定のドメインまたは Web サイトの機能をテストするためにオリジン試用版を使用する場合があります。  特定の機能を適用するには、Web サイトにオリジン試用版を使用できます。  Web サイトの所有者の場合は、オリジン試用版に登録できます。  オリジン試用版は、Web サイトにアクセスする Microsoft Edge ユーザーの割合に機能を提供します。

Origin Trials の詳細については [、「Microsoft Edge Origin Trials Developer Console」に移動します][MicrosoftDeveloperMicrosoftEdgeOriginTrials]。  
    
> [!NOTE]
> 実験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。  実験機能をオフにする場合は、[実験[](#turn-on-experimental-features)機能を有効にする] に移動し、実験に移動し、[] を選択します `Disabled` 。  

## <a name="features-that-are-available-to-test"></a>テストに使用できる機能  

次の一覧では、Microsoft Edge でテストおよび検証できる新しい実験的な Web アプリ機能について説明します。  

| 機能 | Microsoft Edge バージョン | プラットフォーム |  
|:--- |:--- |:--- |  
| [URI プロトコルの処理](#uri-protocol-handling) | 91 以降 | Windows |    
| [URL リンクの処理](#url-link-handling) | 91 以降 | Windows|  
| [OS ログインで実行する](#run-on-os-login) | 88 以降 | すべて |  
| [ショートカット](#shortcuts) | 87 以降 | すべて |  
| [ファイル処理](#file-handling) | 83 以降 | すべてのデスクトップ |  


## <a name="uri-protocol-handling"></a>URI プロトコルの処理  

HTTP または FTP プロトコルを使用して Web ページや Web コンテンツへのリンクを定義するために、統一されたリソース識別子 \(URI\) を使用できます。  URI を使用して、スキーマにコード化するリンクを記述できます。  たとえば、プロトコルを使用して電子メール リンクを記述し、オペレーティング システム \(OS\) またはブラウザーが、そのプロトコルを処理する Web ページまたはアプリ `mailto://` を決定します。  

既存のブラウザー ベースのサポートの詳細については [、Web ベースのプロトコル ハンドラーに移動します][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]。  

この機能を使用すると、次のアクションを実行できます。  

*   Web アプリのマニフェストを使用して PWA をホスト OS に登録する
*   PWA が特定の URI プロトコルを処理すると宣言する  
     
プロトコル ハンドラーとして PWA を登録した後、ブラウザーやネイティブ アプリなどの特定のスキームを使用してハイパーリンクを選択すると、登録済みの PWA は OS によってアクティブ化され `mailto://` 、URI を受信します。 `web+music://`  

この機能では、2 つのフィールドを指定する必要がある配列に配列を含める Web アプリ マニフェスト `protocol_handlers` を更新する必要があります。  

*   `protocol`: 要求を処理するプロトコル (たとえば `mailto` `web+jngl` 、または.  
*   `url`: プロトコルを処理するアプリ スコープ内の HTTPS URI。  今後、プロトコル ハンドラー スキームで始まる URI は、トークンを置き換える予定 `%s` です。  
    
登録するプロトコルをサポートするためにマニフェストを更新します。  この機能を有効にした後、Microsoft Edge は次のアクションを完了します。  

1.  マニフェストの変更を検出する  
1.  プロトコルのアプリを登録します。  
    
複数のアプリがプロトコルを登録すると、ユーザーにプロンプトが表示されます。  ユーザーは、OS またはブラウザーによって表示されるリストから適切なアプリを選択します。  

Windows の Microsoft Edge でプロトコル処理を[](#turn-on-experimental-features)プレビューするには、[実験的な機能を有効にする] に移動し、[デスクトップ Web アプリのプロトコル ハンドラーのサポート **] をオンにします**。  

プロトコル ハンドラーでオリジン試用版が実行されている場合の詳細については [、「Register for Web App Protocol Handler Registration」に移動します][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]。  

### <a name="example-manifest"></a>マニフェストの例

この例では、Web アプリ マニフェストは、プロトコルを処理するためにアプリを登録する必要があります `web+jngl` `web+jnglstore` 。

```json
{
  "name": "Jungle",
  "description": "A plant encyclopedia",
  "protocol_handlers": [
    {
      "protocol": "web+jngl",
      "url": "/lookup?type=%s"
    },
    {
      "protocol": "web+jnglstore",
      "url": "/shop?for=%s"
    }
  ],
  "icons": [
    {
      "src": "images/icons-192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
  ],
  "background_color": "#007f87",

  "display": "standalone",
  "start_url": "/",
}
```  
 
## <a name="url-link-handling"></a>URL リンクの処理  

統一リソース ロケーター \(URL\) は URI の種類です。  プログレッシブ Web Apps \(PWAs\) が https URI のハンドラーとして登録するときに、より魅力的なエクスペリエンスを作成します。  関連付けられた URI がアクティブ化されると、PWA が起動を要求する場合があります。  たとえば、ユーザーが電子メール メッセージからニュース ストーリーへのリンクを選択した場合です。  リンクのアクティブ化を処理するために、ニュース 記事を表示する関連付けられた PWA が自動的に起動されます。  

この機能を使用すると、Web アプリ マニフェストを使用してブラウザーに PWA を登録し、ブラウザーが特定のリンクを処理すると宣言できます。  ブラウザーに PWA を登録するには、省略可能なメンバーを `url_handlers` マニフェスト ファイルに追加します。  メンバー `url_handlers` は、アプリが処理する `object[]` URI の原点をグループ分けするメンバーです。  

リンク処理は、原点にある JSON ファイルを使用してブラウザー `web-app-origin-association` によって検証されます。  オリジン ファイルは、オリジンの含まれるパスまたは除外されたパスをさらに微調整します。  URL ハンドラーのテストに関する詳細な手順については、URL [ハンドラーとして PWA に移動します][GithubWicgPwaUrlHandlerBlobMainExplainerMd]。  

Windows の Microsoft Edge で URL リンク[](#turn-on-experimental-features)処理をプレビューするには、[実験的な機能を有効にする] に移動し、[デスクトップ PWA URL の処理 **] をオンにします**。  

### <a name="example-of-the-url_handlers-in-the-manifest"></a>マニフェスト内のurl_handlersの例  

次のコード スニペットは、メンバーを持つ Web アプリ マニフェストの例 `url_handlers` です。  

```json 
{
    "name": "Contoso Business App",
    "display": "standalone",
    "icons": [
        {
            "src": "images/icons-144.png",
            "type": "image/png",
            "sizes": "144x144"
        }
    ],
    "capture_links": "existing_client_event",
    "url_handlers" : [
        {
            "origin": "https://contoso.com"
        },
        {
            "origin": "https://conto.so"
        },
        {
            "origin": "https://*.contoso.com"
        }
    ]
}
```  

PWA は、URI が元の文字列の 1 つと一致する場合に URL 処理の URI と一致し、ブラウザーは、このアプリがそのような URI を処理することに基が同意したと検証します `url_handlers` 。  

メンバーには、要求する PWA の範囲と他の無関係な起点を含むオ `url_handlers` リジンが含まれる。  URI を要求する PWA と同じスコープまたはドメインに制限しない場合、同じコンテンツに異なるドメイン名を使用できますが、同じ PWA で処理できます。  

#### <a name="wildcard-matching"></a>ワイルドカードの一致  

1 つ以上の文字に `*` 一致するには、ワイルドカード文字 \( \) を使用します。  

異なるサブドメインに一致するために、メンバーのオリジン文字列でワイルドカード `url_handlers` プレフィックスが使用されます。  プレフィックスは、この使用法 `*.` 用である必要があります。  ワイルドカード `https` プレフィックスを使用する場合、スキームは想定されます。  

たとえば、メンバーの `url_handlers` 値は一致する値に `*.contoso.com` 設定 `tenant.contoso.com` されますが、 `www.tenant.contoso.com` 一致しません `contoso.com` 。  

<!-- Hold for future release -->  
<!--  ## Window Controls Overlay for installed desktop web apps  

To create an immersive title bar similar to a native app for your desktop installed web app.  The **Window Controls Overlay** feature  completes the following actions.  
    
1.  Removes the system reserved title bar.  It usually spans the width of the client frame.  
1.  Replaces it with an overlay.  It contains just the critical system required window controls necessary for a user to control the window itself.  
    
After it provides an overlay, the entire web client area is available for you to use.  This feature includes a manifest update.  It provides ways for you to determine the size and position of the overlay to help you arrange content.  
    
### Examples of title bar area customization  

This feature is based on the ability in native apps to customize the title bar.  You may customize a title bar for important app actions or notifications.  Review the following examples for Microsoft Visual Studio Code and Microsoft Teams.  

#### Visual Studio Code  

Microsoft Visual Studio Code is a popular editor built on Electron that ships on multiple desktop platforms.  

The following example displays how Visual Studio Code uses the title bar to maximize available screen real estate to include the current file name and top-level menu structure in the title bar.  

:::image type="complex" source="../media/visual-studio-code-title-customization.png" alt-text="An example of the title bar in Visual Studio Code" lightbox="../media/visual-studio-code-title-customization.png":::
   An example of the title bar in Visual Studio Code  
:::image-end:::  

#### Microsoft Teams  

Workplace collaboration and communication tool Microsoft Teams is also built with Electron and available on multiple desktop platforms.  In the following example, Microsoft Teams displays `back` and `forward` navigation buttons, a search box, and user profile controls.  

:::image type="complex" source="../media/teams-title-customization.png" alt-text="An example of the title bar in Microsoft Teams" lightbox="../media/teams-title-customization.png":::
   An example of the title bar in Microsoft Teams  
:::image-end:::  

### Overlay Window Controls on a Frameless Window  

To provide the maximum addressable area for web content, the browser creates a frameless window, removing all browser UI except for the window controls provided as an overlay.  
The window controls overlay ensures users still minimize, maximize, restore, and close the app.  It also provides access to relevant browser controls using the web app menu.  For Chromium-based browsers, the controls in the overlay.

*   A draggable region the same width and height of each of the window control buttons  
*   The **Settings and more** \(...\) button  
*   The window control buttons minimize, maximize, restore, and close  
    
The following scenarios include when browser displays other content in the controls overlay.  

*   When an installed web app is launched, the origin of the webpage displays to the left of the **Settings and more** \(...\) menu for a few seconds and then disappears.  
*   If a user interacts with an extension using the **Settings and more** \(...\) menu, the icon of the extension displays in the overlay to the left of the three-dot menu.  After you exit any extension dialog, the icon is removed from the overlay.  
    
| Language direction | Overlay location | Details |  
|:--- |:--- |:--- |  
| Left-to-right \(LTR\) | Upper left of the client area | The controls are flipped |  
| Right-to-left \(RTL\) | Upper right corner of the client area |  |  

>[!IMPORTANT]
> The overlay is always on top of the Z-index of the web content and accepts all user input without flowing it through to the web content.  

### Working around the Window Controls Overlay  

Your web content must be aware of the reserved area for the controls overlay.  Ensure the reserved area doesn't expect user interaction.  Query the browser for the bounding rectangle and visibility of the controls overlay.  The information is provided to you through JavaScript APIs and CSS environment variables.  

#### JavaScript APIs  

A new `windowControlsOverlay` object on the `window.navigator` property allows you to query the bounding rectangle of the controls overlay.  

The `windowControlsOverlay` object has the following two objects.  

*   `getBoundingClientRect()` returns a `DOMRect` object.  The `DOMRect` object represents the area under the window controls overlay.  
*   `visible` is a boolean that indicates that the controls overlay is rendered and displayed.  
    
> [!IMPORTANT]
> For privacy reasons, the `windowControlsOverlay` isn't accessible to `iframe` elements in the web content.  

Whenever the overlay is resized, a `geometrychange` event runs on the `navigator.windowControlsOverlay` object to notify the client to recalculate the content layout.  The recalculated content layout is based on the new bounding rectangle of the overlay.  

#### CSS Environment Variables  

Besides the JavaScript API, you may use CSS to query the bounding rectangle of the controls overlay.  Use the following four new CSS environment variables to accomplish to query.  

*   `titlebar-area-x`  
*   `titlebar-area-y`  
*   `titlebar-area-width`  
*   `titlebar-area-height`  
    
### Define Draggable Regions in Web Content  

Users expect to grab and drag the upper region of a window.  To accommodate the expectation, declare specific parts of the web content as draggable.  
To specify an element is draggable, use the webkit proprietary `-webkit-app-region` CSS property.  The CSS working group continues efforts to standardize the `app-region` property.  

To preview this feature in Microsoft Edge for desktop OSs, navigate to [Turn on experimental features](#turn-on-experimental-features) and navigate to **Desktop PWA Window Controls Overlay**.   

### Custom title bar example  

The following example displays how the new features create a web app with a custom title bar.  

:::image type="complex" source="../media/teams-title-customization-example.png" alt-text="Example of a custom title bar in Microsoft Teams" lightbox="../media/teams-title-customization-example.png":::
   Example of a custom title bar in Microsoft Teams  
:::image-end:::  

#### manifest.webmanifest  

In the manifest, set `display_override` array to  `window-controls-overlay`.  Set the `theme_color` to your choice of color for the title bar.  Set the display mode to an appropriate fallback for when either `display_override` or `window-controls-overlay` isn't supported.  

The following code snippet includes the recommended manifest updates.  

```json
{
  "name": "Example PWA",
  "display": "standalone",
  "display_override": [ 
    "window-controls-overlay" 
  ],
  "theme_color": "#254B85"
}
```  

### index.html  

The following IDs represent the two main regions of the webpage.  

*   `titleBarContainer`  
*   `mainContent`  
    
The `div` element with the `titleBar` ID is set to `draggable` and the search box `input` child element is set to `nonDraggable`.  

```html
<div id="titleBar" class=" draggable">
    <span class="draggable">Example PWA</span>
    <input class="nonDraggable" type="text" placeholder="Search"></input>
</div>
```

In the `div` element with the `titleBarContainer` ID, the `div` with the `titleBar` ID represents the visible portion of the title bar area.  

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Example PWA</title>
    <link rel="stylesheet" href="style.css">
    <link rel="manifest" href="./manifest.webmanifest">
  </head>
  <body>
    <div id="titleBarContainer">
      <div id="titleBar" class=" draggable">
        <span class="draggable">Example PWA</span>
        <input class="nonDraggable" type="text" placeholder="Search"></input>
      </div>
    </div>
    <div id="mainContent">The rest of the webpage</div>
  </body>
</html>
```  

### style.css  

The draggable and non-draggable regions are set using `-webkit-app-region: drag` and `-webkit-app-region: no-drag`.  

```css
.draggable {
    app-region: drag;
    /* Pre-fix app-region during standardization process */
    -webkit-app-region: drag;
}

.nonDraggable {
    app-region: no-drag;
    /* Pre-fix app-region during standardization process */
    -webkit-app-region: no-drag;
}
```  

For the `body` element, margins are set to `0` to ensure the title bar reaches to the edges of the window.  

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
}
```  

The `titleBarContainer` ID uses `position: absolute` and sets the `top` to `titlebar-area-inset-top`, which attaches the container to the top of the webpage.  The `bottom` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-title-bar-height)` if the window controls overlay isn't visible.  The background color of the `titleBarContainer` ID is the same as the `theme_color`.  The width is set to `100%`, so that the `div` element fills the width of the webpage and flows under the overlay when it's visible for a contiguous appearance.  

```css
#titleBarContainer {
    position: absolute;
    top: env(titlebar-area-y, 0);
    bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    width: 100%;
    background-color:#254B85;
}
```  

The `titleBar` ID also uses `position: absolute` and `top: titlebar-area-inset-top` to attaches it to the top of the window.  By default, it consumes the full width of the window.  The `left` and `right` edges are set to `titlebar-area-inset-left` and `titlebar-area-inset-right` respectively, both fall back to `0` when the values aren't set.  It also sets `user-select: none` to prevent any attempts to drag the window consumed instead it highlights text in the `div` element.  

```css
#titleBar {
    position: absolute;
    top: 0;
    display: flex;
    user-select: none;
    height: 100%;
    left: env(titlebar-area-x, 0);
    right: env(titlebar-area-width, 0);
    color: #FFFFFF;
    font-weight: bold;
    text-align: center;
}

#titleBar > span {
    margin: auto;
    padding: 0px 16px 0px 16px;
}

#titleBar > input {
    flex: 1;
    margin: 8px;
    border-radius: 5px;
    border: none;
    padding: 8px;
}
```

The container for the `mainContent` ID is also fixed in place with `position: absolute` and is attached to the bottom of the webpage.  The `height` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-titlebar-height)` to fill the remaining space below the title bar.  It sets `overflow-y: scroll` to allow the contents to scroll vertically in the container.  

```css
#mainContent {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    height: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    overflow-y: scroll;
}
```

For cases where the browser doesn't support the window controls overlay, a CSS variable is added to set a default height for the title bar.  The bounds of the `titleBarContainer` and `mainContent` IDs are initially set to fill the entire client area, and you don't need to change it if the overlay isn't supported.  

The following code snippet includes all of the recommended css updates.

```css
:root {
  --fallback-title-bar-height: 40px;
}

.draggable {
  app-region: drag;
  /* Pre-fix app-region during standardization process */
  -webkit-app-region: drag;
}

.nonDraggable {
  app-region: no-drag;
  /* Pre-fix app-region during standardization process */
  -webkit-app-region: no-drag;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  margin: 0;
}

#titleBarContainer {
  position: absolute;
  top: env(titlebar-area-y, 0);
  bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
  width: 100%;
  background-color:#254B85;
}

#titleBar {
  position: absolute;
  top: 0;
  display: flex;
  user-select: none;
  height: 100%;
  left: env(titlebar-area-x, 0);
  right: env(titlebar-area-width, 0);
  color: #FFFFFF;
  font-weight: bold;
  text-align: center;
}

#titleBar > span {
  margin: auto;
  padding: 0px 16px 0px 16px;
}

#titleBar > input {
  flex: 1;
  margin: 8px;
  border-radius: 5px;
  border: none;
  padding: 8px;
}

#mainContent {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
  overflow-y: scroll;
}
```  
-->  

## <a name="run-on-os-login"></a>[OS ログイン時に実行]  

この機能を使用すると、ユーザーが Microsoft Windows にログインするときに自動的に起動するアプリを構成できます。  いくつかのクラスのアプリは、この機能を利用します。  アプリのクラスには、メール、チャット、監視ダッシュボード、リアルタイムデータ表示アプリが含まれます。  この機能を使用すると、ユーザーが OS にログインするとすぐにアプリに参加できます。  この機能は、手動で起動するのと同じ方法で PWA を自動的に開始します。  

> [!IMPORTANT]
> **[OS ログインで実行] は** 強力 [な機能です][GithubW3cPermissionsPowerfulFeature]。  ユーザーは、インストールされている Web アプリの機能を有効にするかどうかを決定する必要があります。  

### <a name="turn-on-run-on-os-login"></a>[OS ログイン時に実行] をオンにする  

PWA の**Run On OS Login 機能**を有効[](#turn-on-experimental-features)にする場合は、[実験的な機能を有効にする] に移動し、OS ログイン時にデスクトップ**PWA を実行します**。  

:::image type="complex" source="../media/desktop-pwas-run-on-os-login-flag.png" alt-text="OS Login 実験で実行するデスクトップ PWA を有効にする" lightbox="../media/desktop-pwas-run-on-os-login-flag.png":::
   OS ログイン実験 **でデスクトップ PWA の実行を有効** にする  
:::image-end:::  

### <a name="turn-on-the-feature-for-the-installed-web-app"></a>インストールされている Web アプリの機能を有効にする  

インストールされている `Start app when you sign in` PWA の機能を有効にするには、 

1.  Microsoft Edge を開きます。   
1.  に移動します `edge://apps` 。  
1.  アプリにカーソルを合わせる。  
1.  コンテキスト メニュー \(右クリック\) を開き、サインイン時に [アプリの起動 **] を選択します**。  
    
    :::image type="complex" source="../media/turn-on-run-on-os-login-flag.png" alt-text="Microsoft Edge の機能にサインインするときに、コンテキスト メニューを使用してスタート アプリを有効にする" lightbox="../media/turn-on-run-on-os-login-flag.png":::
       Microsoft Edge の機能にサインインするときに、コンテキスト メニューを使用してスタート **アプリを** 有効にする  
    :::image-end:::  
    
## <a name="shortcuts"></a>ショートカット  

`Shortcuts` はマニフェスト ファイルの新しいメンバーです。  これにより、Web アプリ内のパーツ、キー Web ページ、またはアクションへのリンクを定義できます。  Microsoft Windows は、ジャンプリスト **として統合します**。  **ジャンプリストは、** 次のいずれかの UI 要素で表示されるポップアップ メニューを定義し、コンテキスト メニュー \(右クリック\) を開きます。  

*   スタート メニューのタイル  
*   タスク バーのアイコン  
    
ユーザーがショートカットを呼び出すと、ユーザーはショートカットのメンバーによって指定された `url` アドレスに移動します。  
  
:::image type="complex" source="../media/jumplists-on-windows-10.png" alt-text="Windows 10 のジャンプリストの例" lightbox="../media/jumplists-on-windows-10.png":::
   Windows 10 **のジャンプリスト** の例  
:::image-end:::  

### <a name="shortcuts-in-the-manifest-file"></a>マニフェスト ファイルのショートカット  

```json
"shortcuts" : [
  {
    "name": "Today's agenda",
    "url": "/today",
    "description": "List of events planned for today"
  },
  {
    "name": "New event",
    "url": "/create/event"
  },
  {
    "name": "New reminder",
    "url": "/create/reminder"
  }
]
```  

#### <a name="properties-of-shortcuts"></a>ショートカットのプロパティ  

次のプロパティは、各ショートカットを定義します。  

| プロパティ | 詳細 |  
|:--- |:--- |  
| `name` | **Jumplists**またはコンテキスト メニューでユーザーに表示される文字列。 |  
| `short_name` | ショートカットの完全な名前を表示する領域が不足している場合に表示される文字列。 |  
| `description` | ショートカットの目的を説明する文字列。  支援技術によってアクセスされる場合があります。 |  
| `url` | ショートカットがアクティブ化されると開く Web アプリの URI。 |  
| `icons` | ショートカットを表す一連のアイコン。 |  

## <a name="file-handling"></a>ファイル処理  

ファイルの種類ハンドラーとして登録する機能は、実験段階です。  マニフェスト エントリでアプリが処理するファイルの種類を指定できます。  インストール中に、ユーザーのホスト OS は、アプリをリストされたファイルの種類のファイル ハンドラーとして登録します。  アプリのスタートアップ コードに機能が存在し、その機能が `launchQueue` ファイルを処理する必要があります。  

クロム ベースのブラウザーでは、この機能のテストと整形を行っています。  コード例を含む詳細については、「Web アプリケーションをファイル ハンドラー [に設定する」に移動します][WebDevFileHandling]。  

デスクトップ OS 用 Microsoft Edge でファイル処理を[](#turn-on-experimental-features)プレビューするには、[実験機能を有効にする] に移動し、[ファイル処理**API] をオンにします**。  
    
## <a name="providing-feedback-on-experimental-features"></a>実験的な機能に関するフィードバックの提供  

Microsoft Edge Web アプリの実験に関するフィードバックを提供する。  

*   [設定] および [ **その他]** \( \) を使用してフィードバックを送信 `...` >フィードバックを **Microsoft に送信します**。  
*   を選択します `Alt` + `Shift` + `I` 。  
    
:::image type="complex" source="../media/send-feedback-from-progressive-web-app.png" alt-text="PWA からフィードバックを送信する" lightbox="../media/send-feedback-from-progressive-web-app.png":::
   PWA からフィードバックを送信する  
:::image-end:::  

<!-- links -->  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[MicrosoftDeveloperMicrosoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Origin Trials |Microsoft Edge 開発者"  
[MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]: https://developer.microsoft.com/microsoft-edge/origin-trials/web-app-protocol-handler-registration/registration "Web アプリ プロトコル ハンドラー登録の登録|Microsoft 開発者"  

[MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]: https://developer.mozilla.org/docs/Web/API/Navigator/registerProtocolHandler/Web-based_protocol_handlers "Web ベースのプロトコル ハンドラー|MDN"  

[GithubW3cPermissionsPowerfulFeature]: https://w3c.github.io/permissions#powerful-feature "強力な機能 - アクセス許可|GitHub"  

[GithubWicgPwaUrlHandlerBlobMainExplainerMd]: https://github.com/WICG/pwa-url-handler/blob/main/explainer.md "URL ハンドラーとしての PWA |GitHub"  

[WebDevFileHandling]: https://web.dev/file-handling "Web アプリケーションをファイル ハンドラーに|web.dev"  
