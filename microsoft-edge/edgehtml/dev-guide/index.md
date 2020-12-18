---
description: このガイドでは、Microsoft Edge に含まれる開発者向けの機能と標準の概要について説明します。
title: EdgeHTML 18 の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: edge, Web 開発, html, css, javascript, 開発者, devtools
ms.custom: RS5
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 15d3321e05f8a307d8014696f1ab78a8967f7129
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234495"
---
# Microsoft Edge 開発者ガイド

> [!TIP]
> 他のブラウザー[](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/)や Web コミュニティと提携し[、MDN Web Docs](https://developer.mozilla.org/)を、現在および新たな標準ベースの Web テクノロジに関する有用で、未確定のブラウザーに依存しないドキュメントの決定的な場所として採用しています。 EdgeHTML API のサポートに関する詳細は、MDN Web リファレンス ライブラリの各ページ [で直接確認できます](https://developer.mozilla.org/docs/Web)。 Microsoft Edge でサポートされている最新 [の](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release) 機能については、Microsoft Edge のプラットフォームの状態にアクセスしてください。 

## EdgeHTML 18 の新機能

EdgeHTML 18 には [、Windows 10 October 2018 Update (10/2018、](/windows/uwp/whats-new/windows-10-build-17763) ビルド 17763) の現在のリリースでリリースされた次の新機能と更新された機能が含まれています。 特定の [Windows Insider](https://insider.windows.com/) Preview ビルドの変更については [、Microsoft Edge の変更ログ](https://developer.microsoft.com/microsoft-edge/platform/changelog/) と EdgeHTML の新機能に関するページ [をご覧ください](./whats-new.md)。

次の変更の一覧の permalink を次に示します [https://aka.ms/devguide_edgehtml_18](./whats-new.md) 。

## 新機能と更新された機能

### 自動再生のポリシー

Windows 10 October 2018 Update を使用すると、Microsoft Edge では、Web 上の気を散らさないようにし、帯域幅を節約するために、メディアをサウンドで自動再生する Web サイトの閲覧設定をカスタマイズできます。 ユーザーは、グローバル自動再生コントロールとサイトごとの自動再生コントロールの両方でメディアの動作をカスタマイズできます。 さらに、Microsoft Edge では、バックグラウンド タブでのメディアの自動再生が自動的に抑制されます。

サイトでホスト [されているメディアに](./browser-features/autoplay-policies.md) 関する優れたユーザー エクスペリエンスを確保するための詳細とベスト プラクティスについては、自動再生ポリシー ガイドを参照してください。

### チャクラの機能強化

EdgeHTML 18 には、パフォーマンスと相互運用性の向上に加えて、新しい ES および WASM 機能をサポートするために、Chakra JavaScript エンジンの更新プログラムが含まれています。 詳細については [、ChakraCore 1.11 リリース ノート](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111) を参照してください。

### CSS の更新

マスクコンポジット、マスク位置、マスク繰り返しのサポートが追加され、実験的[](https://developer.mozilla.org/docs/Web/CSS/mask-repeat)な[CSS](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)マスクの実装 *(ENABLE CSS Masking*フラグの背後) に関するさらなる進歩が行われた。 [](https://developer.mozilla.org/docs/Web/CSS/mask-composite) [](https://developer.mozilla.org/docs/Web/CSS/mask-position) サイト互換性のために、Microsoft Edge は次の *-webkit-* プロパティもサポートしています。-webkit-mask、-webkit-mask-composite、-webkit-mask-image、-webkit-mask-position、-webkit-mask-position-x、-webkit-mask-position-y、-webkit-mask-repeat、-webkit-mask-size。

さらに、Microsoft Edge では、オーバーフロー[](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap
)ラップとオーバースクロール動作[(および](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior)値) の部分的なサポートが `auto` サポート `contain` されています。

### 開発者ツール

Microsoft Edge DevTools の最新の更新プログラムでは、UI とセキュリティの両方に多くの利便性が追加されています。たとえば、サービス ワーカーとストレージ用の新しい専用パネル、デバッガーのソース ファイル検索ツール、スタイル/レイアウトのデバッグとコンソール API 用の新しい Edge DevTools プロトコル ドメインが含まれます。

[最新の Windows 10 更新プログラム (EdgeHTML 18) の DevTools](../devtools-guide/whats-new.md) には、すべての詳細があります。

### フィードバックの聞き取り

お客様からのフィードバックを受け取り、EdgeHTML 18 で要求された API のサポートを実装しました。たとえば、ドラッグ アンド ドロップ時にカスタム イメージを設定するために使用されるメソッドや、ブラウザーがハンドシェイク プロセスを開始する直前にタイムスタンプを返して現在の接続をセキュリティで保護するために使用できる Performance [`DataTransfer.setDragImage()`](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) Resource Timing API のプロパティが含まれます。 [`secureConnectionStart`](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart) 

また、属性コレクションの列挙を好む人はいないので、要素の属性名を文字列の配列として返すだけでなく、ブール属性を切り替えるサポートも追加しました (存在する場合は削除し、ない場合は追加します [`Element.getAttributeNames`](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) [`Element.toggleAttribute`](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute) )。

### プログレッシブ Web アプリ

#### 有効期間バックグラウンド スクリプト

Windows 10 JavaScript アプリ * (WWAHost.exe* プロセスで実行される Web アプリ) では、任意のビューがアクティブ化され、プロセスの期間中実行される前に開始される、アプリケーションごとのオプションのバックグラウンド スクリプトがサポートされます。 これにより、ナビゲーションの監視と変更、ナビゲーション全体の状態の追跡、ナビゲーション エラーの監視、およびビューがアクティブ化される前のコードの実行を行えます。 

アプリ マニフェストで指定すると、アプリの各ビュー (ウィンドウ) が新しいクラスのインスタンスとしてスクリプトに公開され、一般的な [`StartPage`](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application) [](/uwp/schemas/appxpackage/appx-package-manifest) [`WebUIView`](/uwp/api/windows.ui.webui.webuiview) (Win32) [WebView](/uwp/api/windows.web.ui.iwebviewcontrol)と同じイベント、プロパティ、およびメソッドが提供されます。 スクリプトは、新しいビュー [`NewWebUIViewCreated`](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) のナビゲーションの制御を傍受するイベントをリッスンできます。

```JavaScript
Windows.UI.WebUI.WebUIApplication.addEventListener("newwebuiviewcreated", newWebUIViewCreatedEventHandler);
```

 バックグラウンド スクリプトを使ったアプリのアクティブ化は、ナビゲーションの `StartPage` スクリプト自体に依存します。

#### テキストの拡大縮小

Windows 10 October 2018 Update[**](/windows/uwp/design/input/text-scaling#user-experience)では、エンド ユーザーのアクセシビリティを強化するためにテキストを大きくする設定が導入され、Windows (UWP とほとんどのデスクトップ アプリに加えて) にインストールされている PAS は、この機能を自動的にサポートします。 PAS コントロールと WebView コントロールの場合、テキストスケールは DPI スケーリングと同じように動作します。 ユーザーがテキスト スケールと DPI スケールの両方を変更すると、結果は 2 つの製品になります。

 設計ガイダンスについては、Windows デベロッパー センターの [テキストスケーリング](/windows/uwp/design/input/text-scaling) UWP ガイド *をご覧ください*。

### サービス ワーカーの更新プログラム 

サービス ワーカーの概要と動作の詳細については、パートナーが MDN で書いたサービス ワーカー [API]( https://developer.mozilla.org/docs/Web/API/Service_Worker_API) の概要を確認してください。  EdgeHTML 18 のサービス ワーカーをサポートする Microsoft Edge には、いくつかの更新プログラムが含まれています。 サービス ワーカーが応答を約束するために使用し、現在のサービス ワーカーが制御しているクライアントの `fetchEvent` [`preloadResponse`]( https://developer.mozilla.org/docs/Web/API/FetchEvent) ID [`resultingClientId`]( https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId) を返します。  
このインターフェイスは、リソースのプリロードを管理するためのメソッドを提供し、サービス ワーカーが起動している間に並行して要求を行い、時間遅延を回避 [`NavigationPreloadManager`]( https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager) できます。 Service Worker の [プリロード メソッド](#new-apis-in-edgehtml-18) とプロパティの一覧で、新しくサポートされている API プロパティを確認してください。 

### Web 認証

Microsoft Edge では、新しい Web 認証 API (別名[WebAuthN)](https://w3c.github.io/webauthn/)に対[する](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge/)固定されていないサポートが追加されました。 Web 認証は、オープンでスケーラブルで相互運用可能なソリューションを提供し、認証を簡素化し、パスワードをより強力なハードウェアにバインドされた資格情報に置き換え、より優れたセキュリティで保護されたユーザー エクスペリエンスを実現します。 Microsoft Edge の実装により、ユーザーは[Windows Hello](https://www.microsoft.com/windows/windows-hello)を使用して、FIDO2 セキュリティ キーや FIDO U2F セキュリティ キーのような外部認証システムに加えて、顔認証、指紋認証、PIN を使用して Web サイトに安全に認証できます。 [](https://fidoalliance.org)

詳細については、Microsoft Edge での Web 認証の紹介に [関するブログ投稿にアクセスしてください](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge)。

### WebDriver

WebDriver は [Windows](/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities) オンデマンド機能 (FoD) になったので、Microsoft Edge でのテストを自動化し、デバイスに適切なバージョンを取得する作業がこれまで以上に簡単になりました。 WebDriver のインストール時に手動でビルド/分岐/インストールを一致する必要がなくなりました [。WebDriver](https://www.w3.org/TR/webdriver) は、新しい Windows 10 の更新プログラムに合わせて自動的に更新されます。 

開発者モードを有効にすることで WebDriver をインストールするか、[設定] > Apps > Apps & 機能>オプション機能の管理に移動してスタンドアロンとしてインストールできます。 詳細については、Windows ブログ サイトの [WebDriver アナウンスを確認してください](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand)。

### Web 通知のプロパティ
Web 通知では、プラットフォームに依存しないまま、既存の通知システムと互換性のある Web 上で通知を作成する機能が強化され、4 つの新しいプロパティがサポートされます。 [`actions`](https://developer.mozilla.org/docs/Web/API/notification/actions) [`badge`](https://developer.mozilla.org/docs/Web/API/notification/badge) [`image`](https://developer.mozilla.org/docs/Web/API/notification/image) `maxActions`

### WebView

#### サービス ワーカー
[サービス ワーカーは](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) 、Microsoft Edge ブラウザーと Windows 10 JavaScript アプリに加えて、WebView コントロールでサポートされる予定です。 すべての種類の Microsoft Edge Webview ([PWA](../hosting/webview/index.md)、 [UWP](/uwp/api/Windows.UI.Xaml.Controls.WebView)、 [Win32](/windows/communitytoolkit/controls/wpf-winforms/webview)) はサービス ワーカーをサポートしますが、プッシュ [API](https://developer.mozilla.org/docs/Web/API/Push_API) はまだ UWP バージョンと Win32 バージョンで利用できない点に注意してください。

サービス ワーカーは WoW64 プロセスでサポートされていないので、x64 アプリ アーキテクチャにはニュートラル *(Any* CPU) パッケージまたは *x64* パッケージが必要です。 (ディスク領域を節約するために、必要な DLL の WoW バージョンは Windows にネイティブに含まれていません)。

#### Win32 WebView の更新プログラム

Windows デスクトップ (Win32) 用 EdgeHTML [WebViewControl](/windows/communitytoolkit/controls/wpf-winforms/webview)アプリは、ページ上の他のスクリプトが実行される前に、ページの読み込み時にスクリプトを挿入する機能 () や、特定の [`AddInitializeScript`](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript) WebViewControl がいつフォーカスを受け取ったのか失ったのか () を知る機能など、いくつかの新機能で更新されました。 [`GotFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus) / [`LostFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus)

さらに、開いているウィンドウとして新しい WebViewControl を作成できます [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) 。 WebViewControl 内のスクリプトが window.open を呼び出す場合でも、このイベントはアプリに通知します。ただし、EdgeHTML 18 では、ウィンドウのターゲットとして新しい WebViewControl ( ) を設定するために保留 ( ) を取る機能が含まれます [`NewWindowRequested`](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested) [`NewWindowRequestedEventArgs`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs) [`GetDeferral`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral) [`NewWindow`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow) 。open:

```csharp
WebViewControlProcess wvProc;
WebViewControl webView;

void OnWebViewControlNewWindowRequested(WebViewControl sender, WebViewControlNewWindowRequestedEventArgs args)
{

    if (args.Uri.Domain == "mydomain.com")
    {
        using deferral = args.GetDeferral();
        args.NewWindow = await wvProc.CreateWebViewControlAsync(
            parentWindow, targetWebViewBounds);
        deferral.Complete();
    }
    else
    {
        // Prevent WebView from launching in the default browser.
        args.Handled = true;
    }
}

String htmlContent = "<html><script>window.open('http://mydomain.com')</script><body></body></html>";

webView.NavigateToString(htmlContent);
```  

最後に、パワー ユーザーは、次の場所で、Win32 *WebView* を表す内部システム アプリである Desktop App Web Viewer (以前の *Win32WebViewHost)* の外観に気付く場合があります。
- In the *Windows 10 Action Center*. これらの通知のソースは、Win32 アプリからホストされている WebView からと見なされる必要があります。
- デバイス アクセス設定 UI (*Settings->Privacy->Camera/Location/Microphone*)。 これらの設定を無効にすると、Win32 アプリでホストされているすべての WebView からのアクセスが拒否されます。

![Desktop App Web Viewer デバイス アクセス設定](./media/desktop-app-web-viewer.png)

## 非推奨の機能

### XSS フィルターは廃止されました

EdgeHTML 18 では、Microsoft Edge で XSS フィルターを廃止します。 お客様は、コンテンツ インジェクション攻撃から保護する強力で高性能で安全なメカニズムを提供し、最新のブラウザー間で高い互換性を持つコンテンツ セキュリティ ポリシー [(CSP)](https://developer.mozilla.org/docs/Web/HTTP/CSP)などの最新の標準により、引き続き保護されています。

## EdgeHTML 18 の新しい API

EdgeHTML 18 の新しい API の完全な一覧をご覧ください。 これらは [インターフェイス名] の形式で表示されます。[api name].

> [!NOTE] 
> 次の API は DOM で公開されています。ただし、一部の API のエンドツーエンドの動作は、まだ開発中であり、試験的なフラグの背後に隠れている可能性があります。 機能の  [サポートに関する公式](https://developer.microsoft.com/microsoft-edge/platform/status/) の単語については、Microsoft Edge プラットフォームの状態を参照してください。

<iframe height='580' scrolling='no' title='EdgeHTML 18 の新しい API' src='//codepen.io/MSEdgeDev/embed/5d7be9404d82575162b486e79d0dd58f
/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>CodePen の <a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'> EdgeHTML 18 by MSEdgeDev ( @MSEdgeDev ) の Pen New API </a> <a href='https://codepen.io/MSEdgeDev'> </a> を <a href='https://codepen.io'> 参照してください </a> 。</iframe>

## 以前の EdgeHTML リリース

[EdgeHTML 13 / Windows ビルド 10586 (11/2015)](./whats-new/edgehtml-13.md)

[EdgeHTML 14 / Windows ビルド 14393 (8/2016)](./whats-new/edgehtml-14.md)

[EdgeHTML 15 / Windows ビルド 15063 (4/2017)](./whats-new/edgehtml-15.md)

[EdgeHTML 16 / Windows ビルド 16299 (10/2017)](./whats-new/edgehtml-16.md)

[EdgeHTML 17 / Windows ビルド 17134 (04/2018)](./whats-new/edgehtml-17.md)
