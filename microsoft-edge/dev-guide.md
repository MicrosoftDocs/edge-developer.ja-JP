---
title: EdgeHTML 18 の新機能
description: このガイドでは、Microsoft Edge に含まれている開発者向けの機能と標準の概要について説明します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/06/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: edge、web 開発、html、css、javascript、開発者、devtools
ms.custom: RS5
ms.openlocfilehash: b9285be7169f197a687e9f754a20cf67bbde160d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568840"
---
# Microsoft Edge 開発者向けガイド

> [!TIP]
> Microsoft は、現在および最新の標準ベースの web テクノロジについて、理解されていないブラウザーを使用したドキュメントの明確な場所として、 [MDN Web ドキュメント](https://developer.mozilla.org/)を採用して、他のブラウザーや web コミュニティと[提携](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/)しています。 EdgeHTML API のサポートについて詳しくは、 [MDN web リファレンスライブラリ](https://developer.mozilla.org/docs/Web)の各ページで直接参照できます。 Microsoft Edge でサポートされている最新機能については、Microsoft Edge の[プラットフォームの状態](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release)を参照してください。 


## EdgeHTML 18 の新機能

EdgeHTML 18 には、 [Windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)(10/2018、ビルド 17763) の時点で、Microsoft Edge プラットフォームの現在のリリースで出荷されている次の新しい機能と更新された機能が含まれています。 特定の[Windows Insider](https://insider.windows.com/) Preview ビルドでの変更については、 [Microsoft Edge の Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/)と[EdgeHTML の新機能](./dev-guide/whats-new.md)をご覧ください。

次の変更の固定リンクを示し [https://aka.ms/devguide_edgehtml_18](https://aka.ms/devguide_edgehtml_18) ます。

## 新機能と更新された機能

### 自動再生ポリシー

Windows 10 10 月の2018更新プログラムでは、Microsoft Edge は、web 上の集中を最小限に抑え、帯域幅を節約するために、メディアを自動再生する web サイトの閲覧設定をカスタマイズすることができます。 ユーザーは、グローバルおよびサイトごとの自動再生コントロールの両方でメディアの動作をカスタマイズできます。 また、Microsoft Edge では、バックグラウンドタブでのメディアの自動再生が自動的に抑制されます。

サイトでホストされているメディアを適切に操作するためのベストプラクティスについては、「[自動再生ポリシー](./dev-guide/browser-features/autoplay-policies.md)ガイド」をご覧ください。

### Chakra の改善

EdgeHTML 18 には、新しい ES と WASM の機能をサポートするための Chakra JavaScript エンジンの更新が含まれています。また、パフォーマンスと相互運用性が向上しています。 詳細については、 [ChakraCore 1.11 リリースノート](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111)を参照してください。

### CSS の更新

( *Css マスクを有効にする*) の実験的な[css マスク](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)の実装について、[マスク-コンポジット](https://developer.mozilla.org/docs/Web/CSS/mask-composite)、[マスク位置](https://developer.mozilla.org/docs/Web/CSS/mask-position)、[マスクの繰り返し](https://developer.mozilla.org/docs/Web/CSS/mask-repeat)のサポートが追加されました。 サイトの互換性を確保するために、Microsoft Edge では、次の*webkit*プロパティもサポートされています。-webkit、-webkit-mask、--mask、--mask-------------------------------------

さらに、Microsoft Edge では、[過度なスクロール動作](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior)(と値) の[オーバーフローラップ](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap
)と部分的なサポートがサポートされるようになりました `auto` `contain` 。


### 開発者ツール

Microsoft Edge DevTools の最新の更新プログラムでは、サービス作業者とストレージのための新しい専用パネル、デバッガーのソースファイル検索ツール、スタイル/レイアウトのデバッグとコンソール Api 用の新しいエッジツールプロトコルドメインが含まれています。

[最新の Windows 10 更新プログラム (EdgeHTML 18) の Devtools](./devtools-guide/whats-new.md)には、すべての詳細が含まれています。

### フィードバックを聞く

お客様のフィードバックを聞き、EdgeHTML 18 の要求された Api のサポートを実装してい [`DataTransfer.setDragImage()`](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) ます。これは、ドラッグアンドドロップ時にカスタムイメージを設定するために使われるメソッドや、 [`secureConnectionStart`](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart) ブラウザーで現在の接続をセキュリティで保護するために、すぐにタイムスタンプを返すために使うことができる、パフォーマンスリソースタイミング API のプロパティです。 

また、属性のコレクションを列挙するのはありません。そのため、要素の属性名を文字列の配列として返すためのサポートが追加されました [`Element.getAttributeNames`](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) [`Element.toggleAttribute`](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute) 。ブール型の属性 (存在する場合は削除し、存在しない場合は、追加しない場合は追加します)。

### プログレッシブ Web アプリ

#### 有効期間のバックグラウンドスクリプト

Windows 10 の JavaScript アプリ ( *Wwahost*プロセスで実行されている web アプリ) では、任意のビューをアクティブ化してプロセスの間に実行する、オプションのアプリケーションごとのバックグラウンドスクリプトをサポートできるようになりました。 これにより、ナビゲーションを監視して変更したり、ナビゲーションの状態を追跡したり、ナビゲーションエラーを監視したり、ビューをアクティブ化する前にコードを実行したりすることができます。 

[`StartPage`](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application)[アプリマニフェスト](/uwp/schemas/appxpackage/appx-package-manifest)でを指定すると、アプリの各ビュー (windows) は、新しいクラスのインスタンスとしてスクリプトに公開され [`WebUIView`](/uwp/api/windows.ui.webui.webuiview) 、同じイベント、プロパティ、メソッドを一般的な (Win32) [WebView](/uwp/api/windows.web.ui.iwebviewcontrol)として提供します。 スクリプトは、イベントをリッスンして、 [`NewWebUIViewCreated`](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) 新しいビューのナビゲーションの制御をインターセプトできます。

```JavaScript
Windows.UI.WebUI.WebUIApplication.addEventListener("newwebuiviewcreated", newWebUIViewCreatedEventHandler);
```

 バックグラウンドスクリプトを使ったアプリのアクティブ化 `StartPage` は、ナビゲーションのためにスクリプト自体に依存します。

#### テキストの拡大縮小

2018年10月の更新プログラムでは、エンドユーザーのアクセシビリティを向上させるために[*テキストを大きく*](https://review.docs.microsoft.com/windows/uwp/design/input/text-scaling?branch=master#user-experience)するための設定が導入されており、pwas WINDOWS (UWP とほとんどのデスクトップアプリに追加) で、この機能が自動的にサポートされるようになりました。 PWAs コントロールと WebView コントロールの場合、テキスト縮尺は DPI スケーリングと同じように動作します。 ユーザーがテキストスケールと DPI スケールの両方を変更した場合、結果は2つの製品になります。

 デザインガイダンスについては、「 *Windows デベロッパーセンター*の[テキストスケーリング](/windows/uwp/design/input/text-scaling)UWP ガイド」をご覧ください。

### Service Worker の更新プログラム 

サービスワーカーの概要とその機能については、「MDN でのパートナーによって作成された[サービスワーカー API]( https://developer.mozilla.org/docs/Web/API/Service_Worker_API)の概要」を参照してください。  EdgeHTML 18 では、Microsoft Edge にサポートされているサービスワーカーにいくつかの更新がありました。 を `fetchEvent` 使うと、サービスワーカーは [`preloadResponse`]( https://developer.mozilla.org/docs/Web/API/FetchEvent) 応答を確約することができ、では、 [`resultingClientId`]( https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId) 現在のサービスワーカーが制御しているクライアントの ID を返します。  
[`NavigationPreloadManager`]( https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager)インターフェイスには、リソースのプリロードを管理するためのメソッドが用意されています。これにより、サービスワーカーの起動中に要求を並列で行うことができ、時間の遅延を避けることができます。 サービスワーカーのプリロードメソッドとプロパティのリストについては、[新しくサポートされている API プロパティ](#new-apis-in-edgehtml-18)を確認してください。 

### Web 認証

Microsoft Edge[に、新しい Web 認証 API](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge/) ( [WebAuthN](https://w3c.github.io/webauthn/)) のプレフィックスが付いていないサポートが追加されました。 Web 認証は、認証を簡素化するためのオープンでスケーラブルで相互運用可能なソリューションを提供します。これにより、より強力なハードウェアバインド資格情報を使用してパスワードを置き換えることができます。 Microsoft Edge の実装では、 [Windows Hello](https://www.microsoft.com/windows/windows-hello)を使用することで、ユーザーは、FIDO2 セキュリティキーや FIDO U2F セキュリティキーなどの[外部認証](https://fidoalliance.org)に加えて、web サイトに対して安全に認証することができます。

詳細については、「 [Microsoft Edge での Web 認証の概要」](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge)を参照してください。

### WebDriver

WebDriver は、 [Windows のオンデマンド機能](https://docs.microsoft.com/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities)として提供されています。これにより、Microsoft Edge でのテストを自動化し、お使いのデバイスに適したバージョンを入手することができます。 Web ドライバーをインストールするときに、ビルド/分岐/フレーバーを手動で一致させる必要がなくなりました。 [webdriver](https://www.w3.org/TR/webdriver)は、新しい Windows 10 の更新と一致するように自動的に更新されます。 

WebDriver をインストールするには、開発者モードを有効にするか、[設定] に移動して [アプリ > アプリ & 機能を > し > オプションの機能を管理します。 詳細については、「 [Windows ブログサイトの Web ドライバーのお知らせ](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand)」を参照してください。

### Web 通知のプロパティ
Web 通知の4つの新しいプロパティがサポートされるようになりました。また、とは、 [`actions`](https://developer.mozilla.org/docs/Web/API/notification/actions) [`badge`](https://developer.mozilla.org/docs/Web/API/notification/badge) 既存の [`image`](https://developer.mozilla.org/docs/Web/API/notification/image) `maxActions` 通知システムと互換性があるが、プラットフォームに依存しない状態で、web 上で通知を作成する機能を改善しました。

### WebView

#### サービス員
[サービスワーカー](https://developer.mozilla.org/docs/Web/API/Service_Worker_API)が WebView コントロールでサポートされるようになりました。 Microsoft Edge ブラウザーと Windows 10 JavaScript アプリに加えています。 すべての種類の Microsoft Edge webview ([PWA](/microsoft-edge/hosting/webview)、 [UWP](/uwp/api/Windows.UI.Xaml.Controls.WebView)、 [Win32](/windows/communitytoolkit/controls/wpf-winforms/webview)) でのサービスワーカーのサポートただし、[プッシュ API](https://developer.mozilla.org/docs/Web/API/Push_API)は、UWP と Win32 のバージョンではまだ利用できないことにご注意ください。

x64 アプリアーキテクチャでは、サービスワーカーは WoW64 プロセスでサポートされていないため、*ニュートラル*(任意の CPU) または*x64*パッケージが必要です。 (ディスク領域を節約するために、必須の Dll の WoW バージョンは、Windows にはネイティブでは含まれていません)。

#### Win32 WebView の更新プログラム

Windows デスクトップ (Win32) アプリ用の EdgeHTML [Webviewcontrol](/windows/communitytoolkit/controls/wpf-winforms/webview)は、ページ上の他のスクリプトが実行される前に、ページの読み込み時にスクリプトを挿入する機能や、 [`AddInitializeScript`](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript) 特定の webviewcontrol がフォーカスを取得または切断するタイミング () を通知する機能など、いくつかの新機能によって更新されてい [`GotFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus) / [`LostFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus) ます。

さらに、開いたウィンドウとして新しい WebViewControl を作成できるようになりました [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) 。 [`NewWindowRequested`](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested)このイベントは、webviewcontrol 通話ウィンドウ内でスクリプトが実行されているときに、アプリに対して常に通知します。ただし、EdgeHTML 18 には、 [`NewWindowRequestedEventArgs`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs) [`GetDeferral`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral) 新しい webviewcontrol ( [`NewWindow`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow) ) をウィンドウのターゲットとして設定するために、遅延 () を取得する機能が含まれています。開く:

```C#
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

最後に、power users は、次の場所で*デスクトップアプリ Web ビューアー* (以前は*Win32WebViewHost*) の apppearance に気付くことがあります。これは、Win32 WebView を表す内部システムアプリです。
- *Windows 10 のアクションセンター*。 これらの通知のソースは、Win32 アプリからホストされている WebView から認識される必要があります。
- [デバイスアクセスの設定] UI (*設定 >プライバシー->カメラ/位置/マイク*) これらの設定を無効にすると、Win32 アプリでホストされているすべての WebViews からのアクセスが拒否されます。

![デスクトップアプリの Web ビューアーデバイスアクセスの設定](./dev-guide/media/desktop-app-web-viewer.png)


## 廃止された機能

### XSS フィルターが廃止されるようになりました

EdgeHTML 18 では、Microsoft Edge で XSS フィルターを廃止しています。 お客様は、[コンテンツのセキュリティポリシー (CSP)](https://developer.mozilla.org/docs/Web/HTTP/CSP)のような最新の規格により保護されています。これにより、優れたパフォーマンスと安全なメカニズムが提供されます。これにより、最新のブラウザーとの互換性が高くなります。

## EdgeHTML 18 の新しい Api

EdgeHTML 18 の新しい Api の完全な一覧を確認してください。 [Interface name] の形式で一覧表示されます。[api name]。

> [!NOTE] 
> 次の Api は DOM に公開されていますが、一部はまだ開発中であり、実験的フラグの背後に隠れている可能性があります。 機能のサポートに関するオフィシャル単語については、 [Microsoft Edge プラットフォームの状態](https://developer.microsoft.com/microsoft-edge/platform/status/)を参照してください。

<iframe height='580' scrolling='no' title='EdgeHTML 18 の新しい Api' src='//codepen.io/MSEdgeDev/embed/5d7be9404d82575162b486e79d0dd58f
/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'>EdgeHTML 18 </a> by MSEdgeDev ( <a href='https://codepen.io/MSEdgeDev'> @MSEdgeDev) で、 </a> CodePen の Pen <a href='https://codepen.io'> New api を参照してください </a> 。</iframe>

## 以前の EdgeHTML リリース

[EdgeHTML 13/Windows ビルド 10586 (11/2015)](https://aka.ms/devguide_edgehtml_13)

[EdgeHTML 14/Windows ビルド 14393 (8/2016)](https://aka.ms/devguide_edgehtml_14)

[EdgeHTML 15/Windows ビルド 15063 (4/2017)](https://aka.ms/devguide_edgehtml_15)

[EdgeHTML 16/Windows ビルド 16299 (10/2017)](https://aka.ms/devguide_edgehtml_16)

[EdgeHTML 17/Windows ビルド 17134 (04/2018)](https://aka.ms/devguide_edgehtml_17)
