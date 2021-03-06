---
description: このガイドでは、Microsoft Edge に含まれる開発者の機能と標準の概要について説明します。
title: EdgeHTML 18 の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: edge, Web 開発, html, css, javascript, developer, devtools
ms.custom: RS5
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6b53163115ad7db8e5b792cadda0c59b93b6711b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399226"
---
# <a name="microsoft-edge-developer-guide"></a>Microsoft Edge 開発者ガイド  

> [!TIP]
> 他のブラウザー[](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/)や Web コミュニティと提携し[、MDN Web Docs](https://developer.mozilla.org/)を現在および新しい標準ベースの Web テクノロジの有用で偏りのないブラウザーに依存しないドキュメントの決定的な場所として採用しました。  EdgeHTML API サポートの詳細については、MDN Web リファレンス ライブラリの各ページ [で直接確認できます](https://developer.mozilla.org/docs/Web)。  Microsoft Edge でサポートされている最新 [の](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release) 機能については、「Microsoft Edge のプラットフォームの状態」をご覧ください。  

## <a name="whats-new-in-edgehtml-18"></a>EdgeHTML 18 の新機能  

EdgeHTML 18 には [、Windows 10 2018 Update \(10/2018,](/windows/uwp/whats-new/windows-10-build-17763) Build 17763\) の現在のリリースに含まれる次の新機能と更新された機能が含まれています。  特定の [Windows Insider Preview ビルド](https://insider.windows.com) の変更については [、「Microsoft Edge Changelog」および「What's](https://developer.microsoft.com/microsoft-edge/platform/changelog) [New in EdgeHTML」を参照してください](./whats-new.md)。  

次の変更の一覧の permalink を次に示します [https://docs.microsoft.com/microsoft-edge/dev-guide](#new-apis-in-edgehtml-18) 。  

## <a name="new-and-updated-features"></a>新機能と更新された機能  

### <a name="autoplay-policies"></a>自動再生のポリシー  

Windows 10 2018 年 10 月の更新プログラムにより、Microsoft Edge は、Web 上の気晴らしを最小限に抑え、帯域幅を節約するために、メディアを音声で自動再生する Web サイトで閲覧の好みをカスタマイズする機能を顧客に提供します。  ユーザーは、グローバル自動再生コントロールとサイトごとの自動再生コントロールの両方でメディアの動作をカスタマイズできます。  さらに、Microsoft Edge はバックグラウンド タブのメディアの自動再生を自動的に抑制します。  

サイトでホストされている [メディアに関](./browser-features/autoplay-policies.md) する優れたユーザー エクスペリエンスを確保するための詳細とベスト プラクティスについては、「自動再生ポリシー ガイド」を参照してください。  

### <a name="chakra-improvements"></a>チャクラの機能強化  

EdgeHTML 18 には、パフォーマンスと相互運用性の向上に加えて、新しい ES および WASM 機能をサポートする Chakra JavaScript エンジンの更新プログラムが含まれています。  詳細については [、「ChakraCore 1.11 リリース ノート」を](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111) 参照してください。  

### <a name="css-updates"></a>CSS の更新  

マスク合成、マスク位置、マスク繰り返しのサポートが追加され、実験的[](https://developer.mozilla.org/docs/Web/CSS/mask-position)な[CSS](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)マスキング実装 \(Enable [](https://developer.mozilla.org/docs/Web/CSS/mask-composite) *CSS Masking* flag\の背後) でさらに進歩[しました。](https://developer.mozilla.org/docs/Web/CSS/mask-repeat)  サイト互換性のために、Microsoft Edge では、-webkit-mask、-webkit-mask-composite、-webkit-mask-image、-webkit-mask-position、-webkit-mask-position-x、-webkit-mask-position-y、-webkit-mask-repeat、-webkit-mask-size もサポートしています。 **  

さらに、Microsoft Edge では、オーバーフロー[](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap)ラップおよび[overscroll-behavior](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior) \( と values\) の部分的なサポート `auto` が `contain` サポートされています。  

### <a name="developer-tools"></a>開発者ツール  

Microsoft Edge DevTools の最新の更新プログラムは、UI とボンネットの両方に便利な機能を追加します。この中には、Service Workers と Storage 用の新しい専用パネル、デバッガーのソース ファイル検索ツール、スタイル/レイアウトデバッグおよびコンソール API 用の新しい Edge DevTools プロトコル ドメインがあります。  

[最新の Windows 10 更新プログラム (EdgeHTML 18) の DevTools には、すべての](./whats-new.md) 詳細があります。  

### <a name="listening-to-your-feedback"></a>フィードバックを聞く  

フィードバックに耳を傾け、EdgeHTML 18 では、ドラッグ アンド ドロップ時にカスタム イメージを設定するために使用される [DataTransfer.setDragImage()](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) メソッドや、ブラウザーが現在の接続をセキュリティで保護するためのハンドシェイク プロセスを開始する直前にタイムスタンプを返す際に使用できる Performance Resource Timing API のプロパティ [secureConnectionStart](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart)など、いくつかの要求された API のサポートを実装しています。  

さらに、属性コレクションの列挙が好きな人はいないので [、Element.getAttributeNames](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) のサポートを追加して、要素の属性名を文字列の配列として返すだけでなく [、Element.toggleAttribute](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute) を使用してブール属性 \(存在する場合は削除し、\ではない場合は追加) を切り替えました。  

### <a name="progressive-web-apps"></a>プログレッシブ Web アプリ  

#### <a name="lifetime-background-script"></a>ライフタイム バックグラウンド スクリプト  

Windows 10 JavaScript アプリ \(プロセスで実行される Web アプリ\) は、ビューがアクティブ化され、プロセスの期間中実行される前に開始される、アプリケーションごとのオプションのバックグラウンド スクリプトをサポートします。 `WWAHost.exe`  これにより、ビューをアクティブ化する前に、ナビゲーションの監視と変更、ナビゲーション全体の状態の追跡、ナビゲーション エラーの監視、コードの実行を行えます。  

アプリ マニフェストで[StartPage](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application) [](/uwp/schemas/appxpackage/appx-package-manifest)として指定すると、アプリの各ビュー \(windows\) は、新しい[WebUIView](/uwp/api/windows.ui.webui.webuiview)クラスのインスタンスとしてスクリプトに公開され、一般的な \(Win32\) [WebView](/uwp/api/windows.web.ui.iwebviewcontrol)と同じイベント、プロパティ、およびメソッドを提供します。  スクリプトは [NewWebUIViewCreated](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) イベントをリッスンして、新しいビューのナビゲーションの制御を傍受できます。  

```javascript
Windows.UI.WebUI.WebUIApplication.addEventListener("newwebuiviewcreated", newWebUIViewCreatedEventHandler);
```  

 バックグラウンド スクリプトを使用したアプリのアクティブ化は、スクリプト自体のナビゲーション `StartPage` に依存します。  

#### <a name="text-scaling"></a>テキストの拡大縮小  

Windows 10 2018 年 10 月の更新プログラムでは、エンドユーザーのアクセシビリティを向上するために [テキストを大きくする] 設定が導入され、Windows \(さらに UWP とほとんどのデスクトップ アプリ\) にインストールされた PWA は、この機能を自動的にサポートします。 [](/windows/uwp/design/input/text-scaling#user-experience)  PWA コントロールと WebView コントロールの場合、テキストスケールは DPI スケーリングと同じ方法で動作します。  ユーザーがテキストスケールと DPI スケールの両方を変更した場合、結果は 2 つの製品になります。  

 デザイン ガイダンスについては、「Windows デベロッパー センターの [テキスト スケーリング](/windows/uwp/design/input/text-scaling) UWP ガイド *」を参照してください*。  

### <a name="service-worker-updates"></a>Service Worker の更新  

サービス ワーカーの概要と動作方法に関する更新プログラムについては、パートナーが [MDN](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) で作成した Service Worker API の概要を確認してください。  EdgeHTML 18 でサービス ワーカーをサポートする Microsoft Edge に対して、いくつかの更新プログラムが追加されました。  これにより `fetchEvent` 、サービス ワーカーは [preloadResponse](https://developer.mozilla.org/docs/Web/API/FetchEvent) を使用して応答を約束し、結果として生成される [ClientId](https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId) は、現在のサービス ワーカーが制御しているクライアントの ID を返します。  
[NavigationPreloadManager](https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager)インターフェイスは、リソースのプリロードを管理するためのメソッドを提供し、サービス ワーカーが起動中に並行して要求を行い、時間の遅延を回避できます。  Service Worker の [プリロード メソッド](#new-apis-in-edgehtml-18) とプロパティの一覧については、新しくサポートされている API プロパティを確認してください。  

### <a name="web-authentication"></a>Web 認証  

Microsoft Edge には、 [新しい Web 認証 API](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge) \(別名 WebAuthN\) の未修正 [のサポートが含](https://w3c.github.io/webauthn)まれています。  Web 認証は、オープンでスケーラブルで相互運用可能なソリューションを提供し、認証を簡素化し、パスワードをより強力なハードウェアバインド資格情報に置き換え、より安全で安全なユーザー エクスペリエンスを実現します。  Microsoft Edge の実装では[、Windows Hello](https://www.microsoft.com/windows/windows-hello)を使用すると、ユーザーは、FIDO2 セキュリティ キーや FIDO U2F セキュリティ キーのような外部認証機能に加えて、顔、指紋、または PIN でサインインして、Web サイトに安全に認証できます。 [](https://fidoalliance.org)  

詳細については、ブログ記事「Microsoft Edge での [Web 認証の導入」をご覧ください](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge)。  

### <a name="webdriver"></a>WebDriver  

WebDriver は [現在、Windows](https://docs.microsoft.com/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities) オンデマンド機能 \(FoD\) であり、Microsoft Edge でのテストを自動化し、デバイスに適切なバージョンを取得する方がこれまで以上に簡単になりました。  WebDriver をインストールするときにビルド/ブランチ/フレーバーを手動で一致する必要がなくなった場合 [、WebDriver](https://www.w3.org/TR/webdriver) は新しい Windows 10 更新プログラムに一致するために自動的に更新されます。  

WebDriver をインストールするには、開発者モードを有効にするか、オプション機能の管理を行**** う設定アプリ アプリ &スタンドアロン  >  ****  >  **として**  >  **インストールします**。  詳細については [、Windows ブログ サイトの WebDriver アナウンスを参照してください](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand)。  

### <a name="web-notification-properties"></a>Web 通知のプロパティ  

Web 通知には、アクション、バッジ、イメージ、および、[](https://developer.mozilla.org/docs/Web/API/notification/badge)プラットフォームに[](https://developer.mozilla.org/docs/Web/API/notification/image)依存しないまま、既存の通知システムと互換性のある Web 上で通知を作成する機能が向上する 4 つの新しいプロパティがサポートされています。 [](https://developer.mozilla.org/docs/Web/API/notification/actions) `maxActions`  

### <a name="webview"></a>WebView  

#### <a name="service-workers"></a>サービス ワーカー  

[サービス ワーカーは](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) 、Microsoft Edge ブラウザーと Windows 10 JavaScript アプリに加えて、WebView コントロールでサポートされています。  Microsoft Edge Webview \([PWA](/microsoft-edge/hosting/webview), [UWP](/uwp/api/Windows.UI.Xaml.Controls.WebView), [Win32](/windows/communitytoolkit/controls/wpf-winforms/webview)\) サポート サービス ワーカーのすべての機能が、プッシュ [API](https://developer.mozilla.org/docs/Web/API/Push_API) がまだ UWP および Win32 バージョンで利用できない点に注意してください。  

サービス ワーカーは WoW64 プロセスでサポートされていないので、x64 アプリアーキテクチャではニュートラル \(Any CPU\) または x64 パッケージが必要です。  \(ディスク領域を節約するために、必要な DLL の WoW バージョンは Windows にネイティブに含まれません。\)  

#### <a name="win32-webview-updates"></a>Win32 WebView の更新プログラム  

EdgeHTML [WebViewControl](/windows/communitytoolkit/controls/wpf-winforms/webview) for Windows デスクトップ \(Win32\) アプリは、ページ上の他のスクリプトが実行される前にページの読み込み時にスクリプトを挿入[](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript)する機能や、特定の WebViewControl がフォーカスを受け取った場合または失われた場合を知る機能など、いくつかの新機能で更新されました\([GotFocus](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus) / [LostFocus](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus)\)。  

さらに [、window.open](https://developer.mozilla.org/docs/Web/API/Window/open)から開いたウィンドウとして新しい WebViewControl を作成できます。  [NewWindowRequested](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested)イベントは、WebViewControl 内のスクリプトが window.open を常に呼び出したときにアプリに通知しますが、EdgeHTML 18 では[、NewWindowRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs)には、ウィンドウのターゲットとして新しい WebViewControl \([NewWindow](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow)\) を設定するために遅延 \([GetDeferral](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral)\) を取る機能が含まれます。  

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

最後に、Power ユーザーは、次の場所で、Win32 WebView を表す内部システム アプリであるデスクトップ アプリ Web ビューアー \(以前は Win32WebViewHost\という名前) の apppearance に気付く場合があります。  

*   Windows 10 アクション センターで。  これらの通知のソースは、Win32 アプリからホストされる WebView から理解する必要があります。  
*   デバイス アクセス設定 UI \( `Settings`  >  `Privacy`  >  `Camera/Location/Microphone` \) で。  これらの設定を無効にすると、Win32 アプリでホストされているすべての WebView からのアクセスが拒否されます。  

![デスクトップ アプリ Web ビューアーのデバイス アクセス設定](./media/desktop-app-web-viewer.png)  

## <a name="deprecated-features"></a>非推奨の機能  

### <a name="xss-filter-now-retired"></a>XSS フィルターが廃止されました  

EdgeHTML 18 では、Microsoft Edge の XSS フィルターを廃止します。  コンテンツ インジェクション攻撃から保護するためのより強力でパフォーマンスの高い安全なメカニズムを提供するコンテンツ セキュリティ ポリシー [(CSP)](https://developer.mozilla.org/docs/Web/HTTP/CSP)などの最新の標準により、お客様は引き続き保護され、最新のブラウザー間で高い互換性を保っています。  

## <a name="new-apis-in-edgehtml-18"></a>EdgeHTML 18 の新しい API  

EdgeHTML 18 の新しい API の完全な一覧を確認してください。  これらは [インターフェイス名] の形式で一覧表示されます。[api name]。  

> [!NOTE] 
> 次の API は DOM で公開されています。一部のエンドツーエンドの動作は開発中であり、実験的なフラグの背後に隠れている可能性があります。  機能の  [サポートに関する公式な単語については、「Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/status/) プラットフォームの状態」を参照してください。  

<iframe height='580' scrolling='no' title='EdgeHTML 18 の新しい API' src='//codepen.io/MSEdgeDev/embed/5d7be9404d82575162b486e79d0dd58f
/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>CodePen の <a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'> EdgeHTML 18 </a> by MSEdgeDev ( @MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> ) のペンの新しい API </a> を <a href='https://codepen.io'> 参照してください </a> 。</iframe>  

## <a name="previous-edgehtml-releases"></a>以前の EdgeHTML リリース  

[EdgeHTML 13 / Windows ビルド 10586 (2015/11)](./whats-new/edgehtml-13.md)  

[EdgeHTML 14 / Windows ビルド 14393 (2016/8)](./whats-new/edgehtml-14.md)  

[EdgeHTML 15 / Windows ビルド 15063 (2017/4)](./whats-new/edgehtml-15.md)  

[EdgeHTML 16 / Windows ビルド 16299 (2017/10)](./whats-new/edgehtml-16.md)  

[EdgeHTML 17 / Windows ビルド 17134 (2018/04)](https://aka.ms/devguide_edgehtml_17)  
