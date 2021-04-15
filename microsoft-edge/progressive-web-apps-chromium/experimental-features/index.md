---
description: Microsoft Edge for Web Apps の最新の実験的機能
title: 実験的な機能|プログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/09/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, 実験, プログレッシブ Web アプリ, Web アプリ, PWA, PWA
ms.openlocfilehash: 20bc4c90c1fe30be360b44294966415823f9b3a6
ms.sourcegitcommit: 4c6b74b9cdfca73c410d9eba9b42d229b695ee4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11482444"
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
| [デスクトップ アプリのウィンドウ コントロール オーバーレイ](#window-controls-overlay-for-installed-desktop-web-apps) | 91 以降 | Windows 10|   
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

Windows の Microsoft Edge でのプロトコル処理を[](#turn-on-experimental-features)プレビューするには、[実験的な機能を有効にする] に移動し、[**デスクトップ PWA プロトコルの処理] をオンにします**。  

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

メンバーには、要求元 PWA の範囲と他の無関係な起点を含むオ `url_handlers` リジンが含まれる。  URI を要求する PWA と同じスコープまたはドメインに制限しない場合、同じコンテンツに異なるドメイン名を使用できますが、同じ PWA で処理できます。  

#### <a name="wildcard-matching"></a>ワイルドカードの一致  

1 つ以上の文字に `*` 一致するには、ワイルドカード文字 \( \) を使用します。  

異なるサブドメインに一致するために、メンバーのオリジン文字列でワイルドカード `url_handlers` プレフィックスが使用されます。  プレフィックスは、この使用法 `*.` 用である必要があります。  ワイルドカード `https` プレフィックスを使用する場合、スキームは想定されます。  

たとえば、メンバーの `url_handlers` 値は一致する値に `*.contoso.com` 設定 `tenant.contoso.com` されますが、 `www.tenant.contoso.com` 一致しません `contoso.com` 。  

## <a name="window-controls-overlay-for-installed-desktop-web-apps"></a>インストールされているデスクトップ Web アプリのウィンドウ コントロール オーバーレイ  

デスクトップにインストールされた Web アプリ用のネイティブ アプリのようなイマーシブ タイトル バーを作成するには **、Window Controls Overlay** 機能によって次のアクションが完了します。  
    
1.  システム予約のタイトル バーを削除します。  通常、クライアント フレームの幅にまたがっています。  
1.  オーバーレイに置き換える。  このコントロールには、ユーザーがウィンドウ自体を制御するために必要な重要なシステムに必要なウィンドウ コントロールが含まれています。  
    
オーバーレイを提供すると、Web クライアント領域全体を使用できます。  この機能には、マニフェスト更新プログラムが含まれています。  コンテンツの配置に役立つオーバーレイのサイズと位置を決定する方法を提供します。  

Microsoft Edge for Windows 10 のウィンドウ コントロール オーバーレイ[](#turn-on-experimental-features)をプレビューするには、[実験機能を有効にする] に移動し、[デスクトップ PWA ウィンドウ コントロール オーバーレイ]**に移動します**。   

### <a name="examples-of-title-bar-area-customization"></a>タイトル バー領域のカスタマイズの例  

この機能は、ネイティブ アプリでタイトル バーをカスタマイズする機能に基づいて行います。  重要なアプリのアクションや通知用にタイトル バーをカスタマイズできます。  Microsoft Visual Studioおよび Microsoft Teams の次の例を確認します。  

#### <a name="visual-studio-code"></a>Visual Studio Code  

Microsoft Visual Studio コードは、複数のデスクトップ プラットフォームに組み込む、電子で構築された一般的なエディターです。  

次の使用例は、Visual Studio コードがタイトル バーを使用して使用可能な画面の不動産を最大化して、現在のファイル名とトップ レベルのメニュー構造をタイトル バーに含める方法を表示します。  

:::image type="complex" source="../media/visual-studio-code-title-customization.png" alt-text="コード内のタイトル バー Visual Studio例" lightbox="../media/visual-studio-code-title-customization.png":::
   コード内のタイトル バー Visual Studio例  
:::image-end:::  

#### <a name="microsoft-teams"></a>Microsoft Teams  

Workplace のコラボレーションとコミュニケーション ツール Microsoft Teams も、電子を使用して構築され、複数のデスクトップ プラットフォームで利用できます。  次の例では、Microsoft Teams が表示 `back` `forward` され、ナビゲーション ボタン、検索ボックス、およびユーザー プロファイル コントロールが表示されます。  

:::image type="complex" source="../media/teams-title-customization.png" alt-text="Microsoft Teams のタイトル バーの例" lightbox="../media/teams-title-customization.png":::
   Microsoft Teams のタイトル バーの例  
:::image-end:::  

### <a name="overlay-window-controls-on-a-frameless-window"></a>フレームレス ウィンドウのオーバーレイ ウィンドウ コントロール  

Web コンテンツのアドレス指定可能領域を最大化するために、ブラウザーはフレームレス ウィンドウを作成します。  フレームレス ウィンドウは、オーバーレイとして提供されるウィンドウ コントロールを除き、すべてのブラウザー UI を削除します。  ウィンドウ コントロールのオーバーレイを使用すると、ユーザーはアプリを最小化、最大化、復元、閉じ続けます。  また、Web アプリ メニューを使用して関連するブラウザー コントロールにアクセスすることもできます。  クロム ベースのブラウザーの場合、オーバーレイには次のコントロールが含まれます。  

*   ドラッグ可能な領域の各ウィンドウ コントロール ボタンの幅と高さが同じ  
*   [ **設定] および [その他** ] \(...\) ボタン  
*   ウィンドウ コントロール ボタンを最小化、最大化、復元、閉じる  
    
前に示したコントロールに加え、オーバーレイに表示される UI は、次のシナリオで動的にサイズ変更されます。  

*   インストールされている Web アプリが起動すると、Web ページの原点が [設定]**** メニューの左側に表示され、さらに \(...\) メニューが数秒表示され、その後消えます。  
*   ユーザーが [設定] メニューおよび **[その** 他の \(...\)] メニューを使用して拡張機能を操作すると、拡張機能のアイコンが 3 ドット メニューの左側のオーバーレイに表示されます。  拡張機能ダイアログを終了すると、アイコンはオーバーレイから削除されます。  
    
| 言語の方向 | オーバーレイの場所 | 詳細 |  
|:--- |:--- |:--- |  
| 左から右 \(LTR\) | クライアント領域の左上 | コントロールが反転する |  
| 右から左 \(RTL\) | クライアント領域の右上隅 |  |  

> [!IMPORTANT]
> オーバーレイは常に Web コンテンツの Z インデックスの上に表示され、Web コンテンツにフローせずにすべてのユーザー入力を受け入れる。  

### <a name="working-around-the-window-controls-overlay"></a>ウィンドウ コントロール オーバーレイの操作  

Web コンテンツは、コントロール オーバーレイの予約領域を認識している必要があります。  予約領域がユーザーの操作を期待しないことを確認します。  境界を設定する四角形とコントロール オーバーレイの表示をブラウザーに照会します。  この情報は、JavaScript API と CSS 環境変数を使用して提供されます。  

#### <a name="javascript-apis"></a>JavaScript API  

プロパティの `windowControlsOverlay` 新しいオブジェクト `window.navigator` を使用すると、コントロール オーバーレイの境界の四角形に対してクエリを実行できます。  

オブジェクト `windowControlsOverlay` には、次の 2 つのオブジェクトがあります。  

*   `getBoundingClientRect()` オブジェクトを返 `DOMRect` します。  オブジェクト `DOMRect` は、ウィンドウ コントロールオーバーレイの下の領域を表します。  
*   `visible` は、コントロールのオーバーレイがレンダリングおよび表示されるブール値です。  
    
> [!IMPORTANT]
> プライバシー上の理由から `windowControlsOverlay` 、Web コンテンツ内の `iframe` 要素にアクセスできない。  

オーバーレイのサイズが変更されるたびに、オブジェクト上でイベントが実行され、コンテンツ レイアウトの再計算をクライアント `geometrychange` `navigator.windowControlsOverlay` に通知します。  再計算されたコンテンツ レイアウトは、オーバーレイの新しい境界四角形に基づいて作成されます。  

#### <a name="css-environment-variables"></a>CSS 環境変数  

JavaScript API の他に、CSS を使用してコントロール オーバーレイの外接する四角形にクエリを実行することもできます。  クエリを実行するには、次の 4 つの新しい CSS 環境変数を使用します。  

*   `titlebar-area-x`  
*   `titlebar-area-y`  
*   `titlebar-area-width`  
*   `titlebar-area-height`  
    
### <a name="define-draggable-regions-in-web-content"></a>Web コンテンツでドラッグ可能な領域を定義する  

ユーザーは、ウィンドウの上部領域をつかんでドラッグする必要があります。  期待に合わせて、Web コンテンツの特定の部分をドラッグ可能として宣言します。  
要素をドラッグ可能に指定するには、WebKit 独自の `-webkit-app-region` CSS プロパティを使用します。  CSS 作業グループは、プロパティの標準化に取り組 `app-region` み続けます。  

### <a name="custom-title-bar-example"></a>カスタム タイトル バーの例  

次の使用例は、新しい機能がカスタム タイトル バーを持つ Web アプリを作成する方法を表示します。  

:::image type="complex" source="../media/teams-title-customization-example.png" alt-text="Microsoft Teams のカスタム タイトル バーの例" lightbox="../media/teams-title-customization-example.png":::
   Microsoft Teams のカスタム タイトル バーの例  
:::image-end:::  

#### <a name="manifestwebmanifest"></a>manifest.webmanifest  

マニフェストで、配列を `display_override` に設定します  `window-controls-overlay` 。  タイトル バー `theme_color` の色の選択に設定します。  サポートされていない場合に、表示モードを適切なフォールバック `display_override` `window-controls-overlay` に設定します。  

次のコード スニペットには、推奨されるマニフェスト更新プログラムが含まれています。  

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

### <a name="indexhtml"></a>index.html  

次の ID は、Web ページの 2 つの主要な領域を表します。  

*   `titleBarContainer`  
*   `mainContent`  
    
`div`ID を持つ `titleBar` 要素がに設定され `draggable` 、検索ボックス `input` の子要素がに設定されます `nonDraggable` 。  

```html
<div id="titleBar" class=" draggable">
    <span class="draggable">Example PWA</span>
    <input class="nonDraggable" type="text" placeholder="Search"></input>
</div>
```

ID を `div` 持つ `titleBarContainer` 要素では `div` 、ID を持 `titleBar` つ要素はタイトル バー領域の表示部分を表します。  

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
    <div id="mainContent"><!-- The rest of the webpage --></div>
  </body>
</html>
```  

### <a name="stylecss"></a>style.css  

ドラッグ可能領域とドラッグ不可領域は、 を使用して `-webkit-app-region: drag` 設定されます `-webkit-app-region: no-drag` 。  

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

要素の場合、タイトル バーがウィンドウの端に達するまで余白 `body` `0` が設定されます。  

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
}
```  

ID は、コンテナーを Web ページの上部に接続する 、 `titleBarContainer` `position: absolute` `top` `titlebar-area-inset-top` を使用して設定します。  ウィンドウ `bottom` コントロールのオーバーレイが表示されない場合は、に設定され、戻 `titlebar-area-inset-bottom` `100% - var(--fallback-title-bar-height)` ります。  ID の背景色は `titleBarContainer` 、 と同じです `theme_color` 。  幅は 、要素が Web ページの幅を塗りつぶし、隣接する外観で表示されているときにオーバーレイの下 `100%` `div` を流れるので、に設定されます。  

```css
#titleBarContainer {
    position: absolute;
    top: env(titlebar-area-y, 0);
    bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    width: 100%;
    background-color:#254B85;
}
```  

ID `titleBar` も使用 `position: absolute` し `top: titlebar-area-inset-top` 、ウィンドウの上部に添付します。  既定では、ウィンドウの全幅が使用されます。  エッジ `left` と `right` エッジはそれぞれに設定され、両方とも値が設定されていない `titlebar-area-inset-left` `titlebar-area-inset-right` `0` 場合に戻されます。  また、代わりに使用されるウィンドウをドラッグしようとして、要素内のテキストが強調表示 `user-select: none` されるのを防ぐ設定 `div` も行います。  

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

ID のコンテナーも固定され、Web ページの下部 `mainContent` `position: absolute` に添付されます。  に `height` 設定され、タイトル バーの下の残りの領域を埋めるに `titlebar-area-inset-bottom` `100% - var(--fallback-titlebar-height)` 戻ります。  コンテナー内 `overflow-y: scroll` でコンテンツを垂直方向にスクロールできる設定です。  

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

ブラウザーがウィンドウ コントロールオーバーレイをサポートしない場合は、タイトル バーの既定の高さを設定するために CSS 変数が追加されます。  最初は、クライアント領域全体を埋める境界と ID が設定され、オーバーレイがサポートされていない場合は変更 `titleBarContainer` `mainContent` する必要があります。  

次のコード スニペットには、すべての推奨される CSS 更新プログラムが含まれています。

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

## <a name="run-on-os-login"></a>[OS ログイン時に実行]  

この機能を使用すると、ユーザーが Microsoft Windows にログインするときに自動的に起動するアプリを構成できます。  いくつかのクラスのアプリは、この機能を利用します。  アプリのクラスには、メール、チャット、監視ダッシュボード、リアルタイムデータ表示アプリが含まれます。  この機能を使用すると、ユーザーが OS にログインするとすぐにアプリに参加できます。  この機能は、手動で起動するのと同じ方法で PWA を自動的に開始します。  

> [!IMPORTANT]
> **[OS ログインで実行] は** 強力 [な機能です][GithubW3cPermissionsPowerfulFeature]。  ユーザーは、インストールされている Web アプリの機能を有効にするかどうかを決定する必要があります。  

### <a name="turn-on-run-on-os-login"></a>[OS ログイン時に実行] をオンにする  

PWA の**Run On OS Login**機能をプレビュー[](#turn-on-experimental-features)するには、[実験的な機能を有効にする] に移動し、OS ログインでデスクトップ**PWA を実行します**。  

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

Microsoft Edge for Windows 10 でファイル処理[](#turn-on-experimental-features)をプレビューするには、[実験的な機能を有効にする] に移動し、[ファイル処理**API] をオンにします**。  
    
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
