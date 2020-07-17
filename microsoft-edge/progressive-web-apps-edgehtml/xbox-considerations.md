---
description: PWA が Xbox の優れたエクスペリエンスを提供することを確認する
title: Xbox One 向けのプログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、UWP、Xbox、Xbox One、TVJS
ms.openlocfilehash: dfa2b2d252bb788c0010017de57ab147d407c5f7
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882854"
---
# <span data-ttu-id="82e83-104">Xbox One 向けのプログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="82e83-104">Progressive Web Apps for Xbox One</span></span>  

<span data-ttu-id="82e83-105">既存のフレームワーク、CDN、サーバーバックエンドの使用を継続しながら、web アプリケーションを拡張し、Microsoft Store 経由で Xbox One アプリとして利用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="82e83-105">You can extend a web application and make it available as an Xbox One app via Microsoft Store while still continuing to use your existing frameworks, CDN and server backend.</span></span>  <span data-ttu-id="82e83-106">また、すべてのユニバーサル Windows プラットフォーム (UWP) アプリと同様に、Xbox One で実行されているプログレッシブ Web アプリ (PWAs) は、ネイティブ Windows 10 Api を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="82e83-106">And like all Universal Windows Platform (UWP) apps, Progressive Web Apps (PWAs) running on Xbox One can also call native Windows 10 APIs.</span></span>  <span data-ttu-id="82e83-107">Xbox One では、特に[メディア再生アプリ](#media-pwas-on-xbox)のカテゴリにいくつかの pwas が用意されています。</span><span class="sxs-lookup"><span data-stu-id="82e83-107">There are already a number of PWAs available for the Xbox One, particularly in the category of [media playback apps](#media-pwas-on-xbox).</span></span>  

<span data-ttu-id="82e83-108">ほとんどの場合、 [Windows と同じよう](./windows-features.md)に、Pwa を Windows と同じ方法でパッケージ化することができます。 pwa[ビルダー](https://www.pwabuilder.com/)ツールまたは[Visual Studio](https://visualstudio.microsoft.com/vs/) IDE を使用して、pwa を UWP アプリとして実行するために必要な*package.appxmanifest*ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="82e83-108">For the most part, you can package your PWA for Xbox One in the [same way you would for Windows](./windows-features.md), using the [PWA Builder](https://www.pwabuilder.com/) tools or [Visual Studio](https://visualstudio.microsoft.com/vs/) IDE to generate the *appxmanifest* file required to run your PWA as a UWP app.</span></span> <span data-ttu-id="82e83-109">ただし、このガイドでは、いくつかの重要な相違点について説明します。</span><span class="sxs-lookup"><span data-stu-id="82e83-109">However, there are several key differences this guide will walk you through.</span></span>

## <span data-ttu-id="82e83-110">Xbox での PWAs の展開とテスト</span><span class="sxs-lookup"><span data-stu-id="82e83-110">Deploying and testing PWAs on Xbox</span></span>

<span data-ttu-id="82e83-111">始めるには、次の手順に従って、 [ *Xbox One 開発者モード*をアクティブに](/windows/uwp/xbox-apps/devkit-activation)します。</span><span class="sxs-lookup"><span data-stu-id="82e83-111">To get started, follow these [steps to activate *Xbox One Developer Mode*](/windows/uwp/xbox-apps/devkit-activation) .</span></span> <span data-ttu-id="82e83-112">開発者モードが有効になっている場合、 [ *Xbox 用 Device Portal* ](/windows/uwp/debug-test-perf/device-portal-xbox)をセットアップして、開発環境のブラウザーから xbox にリモートアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="82e83-112">With Developer Mode activated, [set up *Device Portal for Xbox*](/windows/uwp/debug-test-perf/device-portal-xbox) to gain remote access to your Xbox from the browser in your dev environment.</span></span>

<span data-ttu-id="82e83-113">これで、 *PWA ビルダー*または*Visual Studio*を使ってテスト用のアプリを展開する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="82e83-113">Now you're ready to deploy your app for testing using either *PWA Builder* or *Visual Studio*.</span></span>

### <span data-ttu-id="82e83-114">オプション 1: PWA ビルダー</span><span class="sxs-lookup"><span data-stu-id="82e83-114">Option 1: PWA Builder</span></span>

<span data-ttu-id="82e83-115">[PWA ビルダー](https://www.pwabuilder.com/)は、ノードパッケージマネージャー (npm) からインストールできる Node.js アプリです。</span><span class="sxs-lookup"><span data-stu-id="82e83-115">[PWA Builder](https://www.pwabuilder.com/) is a Node.js app you can install from Node Package Manager (NPM).</span></span> <span data-ttu-id="82e83-116">Android、iOS、Windows でネイティブにホストされるアプリを生成するために、web サイトのメタデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="82e83-116">It uses the metadata of your website to generate native hosted apps across Android, iOS and Windows.</span></span> <span data-ttu-id="82e83-117">サイトに既に[web アプリマニフェスト](https://developer.mozilla.org/docs/Web/Manifest)が含まれている場合、PWA ビルダーは、プラットフォーム固有のインストールパッケージを生成するためにそれを使います。</span><span class="sxs-lookup"><span data-stu-id="82e83-117">If your site already has a [web app manifest](https://developer.mozilla.org/docs/Web/Manifest), PWA Builder will use it to generate platform-specific installation packages.</span></span> <span data-ttu-id="82e83-118">そうしないと、PWA ビルダーは、サイトの特性に基づいて、ファイルに基本的な*manifest.js*を生成します。</span><span class="sxs-lookup"><span data-stu-id="82e83-118">Otherwise, PWA Builder will generate a basic *manifest.json* file based on the characteristics of your site.</span></span>

#### <span data-ttu-id="82e83-119">要件</span><span class="sxs-lookup"><span data-stu-id="82e83-119">Requirements</span></span>
 - <span data-ttu-id="82e83-120">[Node.js](https://nodejs.org/en/)。 npm が含まれます。</span><span class="sxs-lookup"><span data-stu-id="82e83-120">[Node.js](https://nodejs.org/en/), which includes NPM.</span></span>

#### <span data-ttu-id="82e83-121">セットアップ</span><span class="sxs-lookup"><span data-stu-id="82e83-121">Setup</span></span>

1. <span data-ttu-id="82e83-122">ノードコマンドプロンプトを開いて、PWA ビルダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="82e83-122">Open a Node command prompt to install PWA Builder:</span></span>

    ```
    npm install pwabuilder --global
    ```

2. <span data-ttu-id="82e83-123">自分の web サイトの URL で PWA ビルダーを実行します。</span><span class="sxs-lookup"><span data-stu-id="82e83-123">Run PWA Builder on your website URL:</span></span>

    ```
    pwabuilder https://example.com/ -windows10
    ```

    <span data-ttu-id="82e83-124">*-Windows 10*フラグは、パッケージの生成を Windows 10 (UWP) に制限します。</span><span class="sxs-lookup"><span data-stu-id="82e83-124">The *-windows10* flag limits package generation to Windows 10 (UWP).</span></span> <span data-ttu-id="82e83-125">これを省略して、iOS や Android など、サポートされているすべてのプラットフォームでパッケージを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="82e83-125">You can omit it to generate packages across all supported platforms, including iOS and Android.</span></span> <span data-ttu-id="82e83-126">詳しい情報については、「 [PWA ビルダーのドキュメント](https://docs.pwabuilder.com/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-126">See the [PWA Builder docs](https://docs.pwabuilder.com/) for more info.</span></span>

3. <span data-ttu-id="82e83-127">[Xbox の Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox)で、[**ホーム**]、& [アプリの追加] の順に移動し、  >  **My games & apps**  >  **Add**圧縮していない*ファイルをアップロード*するオプションを選択して、PWA ビルダーによって生成された Windows 10 アプリのマニフェストフォルダーを現在のディレクトリで選択します。</span><span class="sxs-lookup"><span data-stu-id="82e83-127">From the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox), go to **Home** > **My games & apps** > **Add**, choose the option to *upload loose files*, and select the Windows 10 app manifest folder generated by PWA Builder in the current directory.</span></span>

4. <span data-ttu-id="82e83-128">ウィザードの手順に従って、インストール処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="82e83-128">Step through the wizard to complete the installation process.</span></span> <span data-ttu-id="82e83-129">インストールが完了したら、</span><span class="sxs-lookup"><span data-stu-id="82e83-129">Once installed.</span></span> <span data-ttu-id="82e83-130">Xbox One ダッシュボードから PWA を表示して起動することができます。</span><span class="sxs-lookup"><span data-stu-id="82e83-130">you'll be able to see and launch your PWA from the Xbox One dashboard.</span></span>


### <span data-ttu-id="82e83-131">オプション 2: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="82e83-131">Option 2: Visual Studio</span></span>

<span data-ttu-id="82e83-132">無料のフル機能の[Visual Studio コミュニティ 2017](https://visualstudio.microsoft.com/vs/community/)には、windows 10 開発者ツール、ユニバーサルアプリテンプレート、コードエディター、強力なデバッガー、Windows Mobile エミュレーター、豊富な言語のサポートなどが用意されています。これらはすべて実稼働環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="82e83-132">The free, full-featured [Visual Studio Community 2017](https://visualstudio.microsoft.com/vs/community/) includes Windows 10 developer tools, universal app templates, a code editor, a powerful debugger, Windows Mobile emulators, rich language support and much more—all ready to use in production.</span></span> <span data-ttu-id="82e83-133">[*プロフェッショナル*と*エンタープライズ*](https://visualstudio.microsoft.com/vs/compare/)のバージョンには、さらに多くの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="82e83-133">The [*Professional* and *Enterprise*](https://visualstudio.microsoft.com/vs/compare/) versions provide even more features.</span></span>

#### <span data-ttu-id="82e83-134">要件</span><span class="sxs-lookup"><span data-stu-id="82e83-134">Requirements</span></span>

 - <span data-ttu-id="82e83-135">[**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
): 無料の*コミュニティ*エディションを含む任意のバージョン。</span><span class="sxs-lookup"><span data-stu-id="82e83-135">[**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
): any version, including the free *Community* edition.</span></span>
 - <span data-ttu-id="82e83-136">[**Windows 10 SDK**](/windows/uwp/xbox-apps/development-environment-setup): *Visual Studio 2017 インストーラー*でこのオプションコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="82e83-136">[**Windows 10 SDK**](/windows/uwp/xbox-apps/development-environment-setup): Select this optional component in the *Visual Studio 2017 Installer*.</span></span>

#### <span data-ttu-id="82e83-137">セットアップ</span><span class="sxs-lookup"><span data-stu-id="82e83-137">Setup</span></span>

1. <span data-ttu-id="82e83-138">手順に従って、 [PWA をユニバーサル Windows アプリとしてセットアップし、実行](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app)します。</span><span class="sxs-lookup"><span data-stu-id="82e83-138">Follow the steps to [set up and run your PWA as a Universal Windows app](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app).</span></span> <span data-ttu-id="82e83-139">これにより、ユニバーサル Windows Api にアクセスできる、完全に機能する Windows 10 アプリが完成します。</span><span class="sxs-lookup"><span data-stu-id="82e83-139">With this, you'll have a fully functioning Windows 10 app capable of accessing Universal Windows APIs.</span></span>

2. <span data-ttu-id="82e83-140">[Visual Studio リモートデバッガー](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017
)を使って、(他の Windows 10 リモートデバイスと同じように) Xbox ONE に PWA (UWP アプリとして) を展開してデバッグできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="82e83-140">You can now deploy and debug your PWA (as a UWP app) on the Xbox One (as with any other Windows 10 remote device) using the [Visual Studio remote debugger](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017
).</span></span> <span data-ttu-id="82e83-141">または、次の手順を使用して、 [Xbox 用 Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox)を使用して PWA をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="82e83-141">Alternately, you can install your PWA using the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox) using the following steps.</span></span>

3. <span data-ttu-id="82e83-142">Xbox の Device Portal で、[ホーム] > [& アプリ > 追加] に移動して、*アプリパッケージと依存関係*をアップロードするオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="82e83-142">From the Device Portal for Xbox, go to Home > My games & apps > Add, choose the option to upload *App Package and Dependencies*.</span></span>

4. <span data-ttu-id="82e83-143">手順1でアプリ用に生成したパッケージフォルダーに移動し、アップロードする *.appx*ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="82e83-143">Navigate to the package folder you generated for your app in Step 1 and select the *.appx* file for upload.</span></span> <span data-ttu-id="82e83-144">[ *.Appx*ファイル](/windows/uwp/packaging/packaging-uwp-apps)は UWP アプリパッケージファイルであり、テスト目的で任意のデバイスでサイドローディングできます。</span><span class="sxs-lookup"><span data-stu-id="82e83-144">The [*.appx* file](/windows/uwp/packaging/packaging-uwp-apps) is a UWP app package file that can be sideloaded on any device for testing purposes.</span></span>

5. <span data-ttu-id="82e83-145">次に、[**依存関係**] ボタンをタップして、アプリの [*依存関係*] サブフォルダーを選び、それぞれアップロードします。</span><span class="sxs-lookup"><span data-stu-id="82e83-145">Next tap the **Dependencies** button and select the *dependencies* sub-folder for your app and upload each one.</span></span> <span data-ttu-id="82e83-146">この手順は、Xbox 用 Device Portal からアプリを展開する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="82e83-146">This step is only required for deploying apps from the Device Portal for Xbox.</span></span> <span data-ttu-id="82e83-147">Visual Studio では、リモートデバッグとエンドユーザーのコンピューターが、Microsoft Store から配信されたときに、これらの依存関係を既にインストールしている場合に依存関係が提供されます。</span><span class="sxs-lookup"><span data-stu-id="82e83-147">Visual Studio delivers dependencies when remote debugging and the end user's machine will already have these installed when delivered from the Microsoft Store.</span></span>

6. <span data-ttu-id="82e83-148">アプリパッケージと依存関係がアップロードされた状態で、[*展開*] セクションの下にある [**移動**] ボタンをクリックすると、アプリがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="82e83-148">With the app package and the dependencies uploaded, click the **Go** button under the *Deploy* section and the app will be installed.</span></span> <span data-ttu-id="82e83-149">Xbox からアプリを起動する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="82e83-149">You're ready to launch your app from Xbox!</span></span>

## <span data-ttu-id="82e83-150">「PWAs for Xbox」の UX の考慮事項</span><span class="sxs-lookup"><span data-stu-id="82e83-150">UX considerations for PWAs on Xbox</span></span>

### <span data-ttu-id="82e83-151">"10 フィートエクスペリエンス" の設計</span><span class="sxs-lookup"><span data-stu-id="82e83-151">Design for the "10-Foot Experience"</span></span>

<span data-ttu-id="82e83-152">Xbox One は "10 フィートエクスペリエンス" と見なされます。つまり、ユーザーは画面から少なくとも10フィート離れていることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="82e83-152">Xbox One is considered a "10-foot experience", meaning that your users will likely be sitting a minimum of 10 feet away from the screen.</span></span> <span data-ttu-id="82e83-153">そのため、マウスとキーボードを使用した従来のデスクトップ web ブラウザー操作と比べて、その距離でアプリを使う方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-153">As such, consider how your app might be used at that distance as opposed to the traditional desktop web browser experience with a mouse and keyboard.</span></span> <span data-ttu-id="82e83-154">デザインと UX のガイダンスについては、「 [Xbox およびテレビ向け設計](/windows/uwp/design/devices/designing-for-tv)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="82e83-154">For design and UX guidance, check out [Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv).</span></span>

### <span data-ttu-id="82e83-155">"TV SafeZone" について理解する</span><span class="sxs-lookup"><span data-stu-id="82e83-155">Understand the "TV SafeZone"</span></span>

<span data-ttu-id="82e83-156">テレビの製造元は、アプリをクリップできるコンテンツの周りに["セーフゾーン"](/windows/uwp/design/devices/designing-for-tv#tv-safe-area)を適用します。</span><span class="sxs-lookup"><span data-stu-id="82e83-156">Television manufacturers will apply a ["safe-zone"](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) around the content that can clip your app.</span></span> <span data-ttu-id="82e83-157">既定では、アプリの周囲に安全な境界線が適用されますが、このためには、アプリが次のように呼び出してすべての画面サイズを使用できるようにする必要が [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode) あります。</span><span class="sxs-lookup"><span data-stu-id="82e83-157">By default, we apply a safe border around your app to account for this, however you can ensure that your app takes the full screen size by calling [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) and specifying [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode):</span></span>

```JavaScript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```

<span data-ttu-id="82e83-158">詳しくは、「名前空間のドキュメント」をご覧 [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) ください。</span><span class="sxs-lookup"><span data-stu-id="82e83-158">For more, check out the [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) namespace documentation.</span></span>

### <span data-ttu-id="82e83-159">XY フォーカスとナビゲーションを管理する</span><span class="sxs-lookup"><span data-stu-id="82e83-159">Manage XY focus and navigation</span></span>

<span data-ttu-id="82e83-160">Xbox のユーザー入力方式は、ゲームパッドまたはリモートコントロールであり、 [XY ナビゲーションシステム](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)を使用しているため、ユーザーはフォーカスを ctrl キーを押しながら上下左右に移動してコントロールに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="82e83-160">User input methods for Xbox are gamepad or remote control, which use a [XY navigation system](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction), allowing the user to shift the focus from control to control by moving up, down, left, and right.</span></span>

<span data-ttu-id="82e83-161">したがって、XY ナビゲーションでアプリが適切に動作することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-161">As such, you'll want to make sure your app works well with XY navigation.</span></span> <span data-ttu-id="82e83-162">また、UWP アプリでは既定でオンになっている[*マウスモード*を無効](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)にします (アプリの Xbox エクスペリエンスには適用されない場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="82e83-162">Also, be sure to [disable *mouse mode*](/windows/uwp/xbox-apps/how-to-disable-mouse-mode), which is on by default for UWP apps (and probably not applicable to your app's Xbox experience).</span></span>

<span data-ttu-id="82e83-163">次のコードは、 `mouse` モードをオフにして、ゲームパッド入力を有効にして、DOM キーボードイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="82e83-163">The following code turns off `mouse` mode and enables gamepad input to generate DOM keyboard events:</span></span>

```JavaScript
navigator.gamepadInputEmulation = "keyboard";
```

<span data-ttu-id="82e83-164">または、 `gamepad` マウスをオフにして、DOM キーボードイベントを生成せず、標準の web または WinRT のゲームパッド api を使用できるように指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="82e83-164">Alternately, you can specify `gamepad`, which also turns off mouse, does not generate DOM keyboard events, and allows you to use the standard web and/or WinRT gamepad APIs.</span></span>

<span data-ttu-id="82e83-165">方向ナビゲーションを有効にするには、 [TVJS ライブラリ](#tvjs)について、次の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-165">To enable directional navigation, check out the [TVJS library](#tvjs), discussed next.</span></span>

### <span data-ttu-id="82e83-166">TVJS</span><span class="sxs-lookup"><span data-stu-id="82e83-166">TVJS</span></span>

<span data-ttu-id="82e83-167">TVJS は、テレビ用の web アプリケーションを簡単に構築できるようにする[ヘルパーライブラリのコレクション](https://github.com/Microsoft/TVHelpers)です。</span><span class="sxs-lookup"><span data-stu-id="82e83-167">[TVJS is a collection of helper libraries](https://github.com/Microsoft/TVHelpers) that make it easier to build web applications for the TV.</span></span> <span data-ttu-id="82e83-168">Xbox でも実行されるホストされた web アプリを作成している場合、TVJS は*方向ナビゲーション*のサポートを追加するのに役立ちます。また、テレビ上のコンテンツを簡単に操作するためのいくつかのコントロールも用意されています。</span><span class="sxs-lookup"><span data-stu-id="82e83-168">If you are building a hosted web app that will also run on the Xbox, TVJS can help add support for *directional navigation*, as well as provide several controls that make it easier to interact with content on the TV.</span></span>

<span data-ttu-id="82e83-169">[方向ナビゲーション](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)は、テレビアプリのページ内での自動2次元のナビゲーションを提供する TVJS 機能です。</span><span class="sxs-lookup"><span data-stu-id="82e83-169">[Directional navigation](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) is a TVJS feature that provides automatic two-dimensional navigation within the pages of your TV app.</span></span> <span data-ttu-id="82e83-170">この機能を使うと、アプリのページ内でのナビゲーションをトラップして処理する必要がなくなります。また、UI の各要素のすべての有効なフォーカスターゲットを明示的に指定する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="82e83-170">With it, there's no need to trap and handle navigation within the pages of your app, or to explicitly specify all the valid focus targets for each element in the UI.</span></span> <span data-ttu-id="82e83-171">自動フォーカス処理により、ユーザーは直感的で確実な方法で移動できます。</span><span class="sxs-lookup"><span data-stu-id="82e83-171">Automatic focus handling enables users can navigate around in an intuitive and robust way.</span></span>

<span data-ttu-id="82e83-172">ユーザーがコントローラーの方向ボタンを使ってアプリの UI に移動すると、自動フォーカスアルゴリズムは、一連の潜在的なフォーカスターゲットを確認し、移動先の次の要素を特定し、自動的にフォーカスをその要素に設定します。</span><span class="sxs-lookup"><span data-stu-id="82e83-172">As your user navigates the app UI with the controller direction buttons, the automatic focus algorithm looks at the set of potential focus targets, determines the next element to move to and then automatically sets focus to that element.</span></span> <span data-ttu-id="82e83-173">次の要素を決定するために、アルゴリズムは、方向入力、過去のフォーカス履歴、およびページ上の UI 要素の物理レイアウトを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="82e83-173">To determine the next element, the algorithm combines directional input, past focus history, and the physical layout of UI elements on the page.</span></span>

<span data-ttu-id="82e83-174">方向ナビゲーションを有効にするには、次のスクリプト参照を含めます。</span><span class="sxs-lookup"><span data-stu-id="82e83-174">To enable directional navigation, include the following script reference:</span></span>

```HTML
<script src="directionalnavigation-1.0.0.0.js"></script>
```

<span data-ttu-id="82e83-175">既定では、、、、、 `<a>` `<button>` `<input>` `<select>` および `<textarea>` 要素のみがフォーカス可能になります。</span><span class="sxs-lookup"><span data-stu-id="82e83-175">By default, only `<a>`, `<button>`, `<input>`, `<select>`, and `<textarea>` elements are focusable.</span></span> <span data-ttu-id="82e83-176">他の要素にフォーカスを設定するには、有効な[tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="82e83-176">To enable focus on other elements, assign them a valid [tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex).</span></span>

```HTML
<div tabindex="0″>This div is eligible for focus</div>
```

ルート要素の変更、初期フォーカスの設定、次のフォーカスの上書き、フォーカス用コントロールの最適化、入力のカスタマイズ方法については、「 [direction」ナビゲーション](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation)ドキュメントをご覧ください。 <span data-ttu-id="82e83-178">さらに多くの便利なサンプルも用意されています。</span><span class="sxs-lookup"><span data-stu-id="82e83-178">There's also a number of other useful samples.</span></span>

## <span data-ttu-id="82e83-179">メディア p が Xbox にありました</span><span class="sxs-lookup"><span data-stu-id="82e83-179">Media PWAs on Xbox</span></span>

<span data-ttu-id="82e83-180">Xbox One 向けに PWA 再生メディアを作成している場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-180">If you're building a media playback PWA for Xbox One, be aware of the following considerations.</span></span>

### <span data-ttu-id="82e83-181">ブラウザーの暗号化されたメディア拡張機能 (EME)</span><span class="sxs-lookup"><span data-stu-id="82e83-181">Encrypted Media Extensions (EME) in the browser</span></span>

<span data-ttu-id="82e83-182">Xbox One の Microsoft Edge ブラウザーは、[暗号化されたメディア拡張機能](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)(EME) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="82e83-182">The Microsoft Edge browser on Xbox One does not support [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API) (EME).</span></span> <span data-ttu-id="82e83-183">メディア PWA でデジタル著作権管理 (DRM) に使用されている場合は、Xbox のブラウザーから実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="82e83-183">If your media PWA uses it for digital rights management (DRM), you won't be able to run it from the browser on your Xbox.</span></span> <span data-ttu-id="82e83-184">代わりに、前に説明したように、 [PWABuilder または Visual Studio を使って Xbox One アプリ](#deploying-and-testing-pwas-on-xbox)としてプロトタイプし、テストします。</span><span class="sxs-lookup"><span data-stu-id="82e83-184">Instead, prototype and test it as a [Xbox One app using PWABuilder or Visual Studio](#deploying-and-testing-pwas-on-xbox), as described above.</span></span> <span data-ttu-id="82e83-185">また、Windows の Microsoft Edge ブラウザーで EME が完全にサポートされている場合にも実行できます。</span><span class="sxs-lookup"><span data-stu-id="82e83-185">You can also run it on the Microsoft Edge browser on Windows, where EME is fully supported.</span></span>

### <span data-ttu-id="82e83-186">システムメディアトランスポートコントロールとの統合</span><span class="sxs-lookup"><span data-stu-id="82e83-186">Integrating with System Media Transport Controls</span></span>

<span data-ttu-id="82e83-187">アプリがメディアアプリの場合、アプリは、ユーザーが開始したメディアコントロールに対して、画面上のボタン、 [Cortana の音声コマンド](https://support.xbox.com/xbox-one/console/cortana-voice-commands)、ナビゲーションウィンドウの[システムメディアトランスポートコントロール](/windows/uwp/audio-video-camera/system-media-transport-controls)、またはその他のデバイス上にある[Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
)と[xbox One smartglass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2)アプリを使って応答することが重要です。</span><span class="sxs-lookup"><span data-stu-id="82e83-187">If your app is a media app, it is important that your app responds to the media controls initiated by the user via on-screen buttons, [Cortana voice commands](https://support.xbox.com/xbox-one/console/cortana-voice-commands), the [System Media Transport Controls](/windows/uwp/audio-video-camera/system-media-transport-controls) in the nav pane, or the [Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) and [Xbox One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2) apps on other devices.</span></span> <span data-ttu-id="82e83-188">これらのコントロールと自動的に統合される、 [TVJS ライブラリ](#tvjs)の[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)コントロールを見てみます。</span><span class="sxs-lookup"><span data-stu-id="82e83-188">Take a look at the [MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview) control from the [TVJS library](#tvjs), which automatically integrates with these controls.</span></span> <span data-ttu-id="82e83-189">または、手動で[システムメディアトランスポートコントロールと統合](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls)することもできます。</span><span class="sxs-lookup"><span data-stu-id="82e83-189">Alternately, you can manually [integrate with the System Media Transport Controls](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls).</span></span>

### <span data-ttu-id="82e83-190">PlayReady コンテンツの暗号化</span><span class="sxs-lookup"><span data-stu-id="82e83-190">PlayReady content encryption</span></span>

<span data-ttu-id="82e83-191">このドキュメントを作成した時点では、エンコードのサポートは XBox One の PlayReady クライアント (バージョン1709以上) に[ `cbcs` 制限され](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme)ています。</span><span class="sxs-lookup"><span data-stu-id="82e83-191">At the time of this writing, [`cbcs` encoding support is limited](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme) to the PlayReady client for XBox One (version 1709 or higher).</span></span> <span data-ttu-id="82e83-192">PWA のメディアが*cbcs*暗号化のみをサポートしている場合は、Windows でアプリの機能が制限される (または完全に利用できない) 可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-192">If the media for your PWA only supports *cbcs* encryption, be aware that your app's functionality will be likely be limited (or completely unavailable) on Windows.</span></span>



## <span data-ttu-id="82e83-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="82e83-193">See also</span></span>
<span data-ttu-id="82e83-194">[サウス Ridge video](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): web サーバーで React.js とホストされている Xbox 用のサンプルビデオアプリ。</span><span class="sxs-lookup"><span data-stu-id="82e83-194">[South Ridge Video](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): A sample video app for Xbox built with React.js and hosted on a web server.</span></span>

<span data-ttu-id="82e83-195">[Xbox およびテレビ向け設計](/windows/uwp/design/devices/designing-for-tv): xbox One とテレビ画面で適切に動作するように、ユニバーサル Windows プラットフォーム (UWP) アプリを設計します。</span><span class="sxs-lookup"><span data-stu-id="82e83-195">[Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv): Design your Universal Windows Platform (UWP) app so that it looks good and functions well on Xbox One and television screens.</span></span>

<span data-ttu-id="82e83-196">[Xbox のベストプラクティス](/windows/uwp/xbox-apps/tailoring-for-xbox): 以下のベストプラクティスに従って、xbox One 用にアプリを調整してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-196">[Xbox best practices](/windows/uwp/xbox-apps/tailoring-for-xbox): Follow these best practices to tailor your app for Xbox One.</span></span>

<span data-ttu-id="82e83-197">[Microsoft store で](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store)動作しています。ここでは、microsoft ストアに PWA を提出する方法 (およびその理由) について説明します。</span><span class="sxs-lookup"><span data-stu-id="82e83-197">[PWAs in the Microsoft Store](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store): Here's how (and why!) to Submit your PWA to the Microsoft Store.</span></span>

<span data-ttu-id="82e83-198">[Xbox one の uwp](/windows/uwp/xbox-apps/): xbox one の uwp アプリ開発の包括的なガイドです。</span><span class="sxs-lookup"><span data-stu-id="82e83-198">[UWP on Xbox One](/windows/uwp/xbox-apps/): A complete guide to UWP app development for Xbox One.</span></span>
