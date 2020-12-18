---
description: PWA が Xbox に優れたエクスペリエンスを提供するようにする
title: Xbox One 用の段階的な Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 段階的な Web アプリ、PWA、Edge、Windows、UWP、Xbox、Xbox One、TVJS
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f1c46fe49f335373323de106b1b2a84418b97577
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235076"
---
# <span data-ttu-id="3de4b-104">Xbox One 用の段階的な Web アプリ</span><span class="sxs-lookup"><span data-stu-id="3de4b-104">Progressive Web Apps for Xbox One</span></span>  

<span data-ttu-id="3de4b-105">既存のフレームワーク、CDN、サーバー バックエンドを引き続き使用しながら、Web アプリケーションを拡張し、Microsoft Store 経由で Xbox One アプリとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-105">You can extend a web application and make it available as an Xbox One app via Microsoft Store while still continuing to use your existing frameworks, CDN and server backend.</span></span>  <span data-ttu-id="3de4b-106">また、すべてのユニバーサル Windows プラットフォーム (UWP) アプリと同様に、Xbox One で実行される段階的な Web アプリ (PAP) も、ネイティブの Windows 10 API を呼び出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3de4b-106">And like all Universal Windows Platform (UWP) apps, Progressive Web Apps (PWAs) running on Xbox One can also call native Windows 10 APIs.</span></span>  <span data-ttu-id="3de4b-107">Xbox One では、特にメディア再生アプリのカテゴリに多数の [PAS が既に用意されています](#media-pwas-on-xbox)。</span><span class="sxs-lookup"><span data-stu-id="3de4b-107">There are already a number of PWAs available for the Xbox One, particularly in the category of [media playback apps](#media-pwas-on-xbox).</span></span>  

<span data-ttu-id="3de4b-108">ほとんどの場合、Windows の場合と同じ方法で Xbox One[](./windows-features.md)用の PWA をパッケージ化できます。PWA [Builder](https://www.pwabuilder.com/)ツールまたは[Visual Studio](https://visualstudio.microsoft.com/vs/) IDE を使用して、PWA を UWP アプリとして実行するために必要な*appxmanifest*ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-108">For the most part, you can package your PWA for Xbox One in the [same way you would for Windows](./windows-features.md), using the [PWA Builder](https://www.pwabuilder.com/) tools or [Visual Studio](https://visualstudio.microsoft.com/vs/) IDE to generate the *appxmanifest* file required to run your PWA as a UWP app.</span></span> <span data-ttu-id="3de4b-109">ただし、このガイドではいくつかの重要な違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-109">However, there are several key differences this guide will walk you through.</span></span>

## <span data-ttu-id="3de4b-110">Xbox での PAS の展開とテスト</span><span class="sxs-lookup"><span data-stu-id="3de4b-110">Deploying and testing PWAs on Xbox</span></span>

<span data-ttu-id="3de4b-111">開始するには、次の手順に [従って *Xbox One 開発者モードをアクティブ化します*](/windows/uwp/xbox-apps/devkit-activation) 。</span><span class="sxs-lookup"><span data-stu-id="3de4b-111">To get started, follow these [steps to activate *Xbox One Developer Mode*](/windows/uwp/xbox-apps/devkit-activation) .</span></span> <span data-ttu-id="3de4b-112">開発者モードをアクティブ化した状態で[*、Xbox 用 Device Portal を*](/windows/uwp/debug-test-perf/device-portal-xbox)セットアップして、お使いの環境のブラウザーから Xbox にリモート アクセスします。</span><span class="sxs-lookup"><span data-stu-id="3de4b-112">With Developer Mode activated, [set up *Device Portal for Xbox*](/windows/uwp/debug-test-perf/device-portal-xbox) to gain remote access to your Xbox from the browser in your dev environment.</span></span>

<span data-ttu-id="3de4b-113">これで *、PWA* Builder または Visual Studio を使用して、テスト用にアプリを展開*する準備が整Visual Studio。*</span><span class="sxs-lookup"><span data-stu-id="3de4b-113">Now you're ready to deploy your app for testing using either *PWA Builder* or *Visual Studio*.</span></span>

### <span data-ttu-id="3de4b-114">オプション 1: PWA Builder</span><span class="sxs-lookup"><span data-stu-id="3de4b-114">Option 1: PWA Builder</span></span>

<span data-ttu-id="3de4b-115">[PWA Builder](https://www.pwabuilder.com/) は、node Node.js (NPM) からインストールできるパッケージ マネージャーアプリです。</span><span class="sxs-lookup"><span data-stu-id="3de4b-115">[PWA Builder](https://www.pwabuilder.com/) is a Node.js app you can install from Node Package Manager (NPM).</span></span> <span data-ttu-id="3de4b-116">Web サイトのメタデータを使用して、Android、iOS、Windows 全体でネイティブでホストされるアプリを生成します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-116">It uses the metadata of your website to generate native hosted apps across Android, iOS and Windows.</span></span> <span data-ttu-id="3de4b-117">サイトに既に [Web](https://developer.mozilla.org/docs/Web/Manifest)アプリ マニフェストがある場合、PWA Builder は Web アプリ マニフェストを使用してプラットフォーム固有のインストール パッケージを生成します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-117">If your site already has a [web app manifest](https://developer.mozilla.org/docs/Web/Manifest), PWA Builder will use it to generate platform-specific installation packages.</span></span> <span data-ttu-id="3de4b-118">それ以外の場合、PWA Builder は、サイト \* のmanifest.js\* に基づいてファイルに基づいて基本的なファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-118">Otherwise, PWA Builder will generate a basic *manifest.json* file based on the characteristics of your site.</span></span>

#### <span data-ttu-id="3de4b-119">要件</span><span class="sxs-lookup"><span data-stu-id="3de4b-119">Requirements</span></span>

 - <span data-ttu-id="3de4b-120">[Node.js](https://nodejs.org/en/)NPM を含む。</span><span class="sxs-lookup"><span data-stu-id="3de4b-120">[Node.js](https://nodejs.org/en/), which includes NPM.</span></span>

#### <span data-ttu-id="3de4b-121">セットアップ</span><span class="sxs-lookup"><span data-stu-id="3de4b-121">Setup</span></span>

1.  <span data-ttu-id="3de4b-122">Node コマンド プロンプトを開き、PWA ビルダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3de4b-122">Open a Node command prompt to install PWA Builder:</span></span>
    
    ```shell
    npm install pwabuilder --global
    ```  
    
2.  <span data-ttu-id="3de4b-123">Web サイトの URL で PWA Builder を実行します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-123">Run PWA Builder on your website URL:</span></span>
    
    ```shell
    pwabuilder https://example.com/ -windows10
    ```  
    
    <span data-ttu-id="3de4b-124">*-windows10 フラグは*、パッケージの生成を Windows 10 (UWP) に制限します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-124">The *-windows10* flag limits package generation to Windows 10 (UWP).</span></span> <span data-ttu-id="3de4b-125">iOS や Android を含む、サポートされているプラットフォーム全体でパッケージを生成する場合は省略できます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-125">You can omit it to generate packages across all supported platforms, including iOS and Android.</span></span> <span data-ttu-id="3de4b-126">詳細については [、PWA Builder のドキュメント](https://docs.pwabuilder.com/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3de4b-126">See the [PWA Builder docs](https://docs.pwabuilder.com/) for more info.</span></span>
    
3.  <span data-ttu-id="3de4b-127">Xbox[用 Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox)で\*\*\*\*、[ホーム マイ ゲーム] & アプリの [追加] に移動し、ルーズ ファイルをアップロードするオプションを選択し、現在のディレクトリで PWA Builder によって生成された  >  \*\*\*\*  >  \*\*\*\* Windows 10\*\* アプリ マニフェスト フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-127">From the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox), go to **Home** > **My games & apps** > **Add**, choose the option to *upload loose files*, and select the Windows 10 app manifest folder generated by PWA Builder in the current directory.</span></span>

4.  <span data-ttu-id="3de4b-128">ウィザードをステップ実行してインストール プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-128">Step through the wizard to complete the installation process.</span></span> <span data-ttu-id="3de4b-129">インストール後。</span><span class="sxs-lookup"><span data-stu-id="3de4b-129">Once installed.</span></span> <span data-ttu-id="3de4b-130">Xbox One ダッシュボードから PWA を表示して起動できます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-130">you'll be able to see and launch your PWA from the Xbox One dashboard.</span></span>
    
### <span data-ttu-id="3de4b-131">オプション 2: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3de4b-131">Option 2: Visual Studio</span></span>

<span data-ttu-id="3de4b-132">無料のフル機能を備える [Visual Studio Community 2017](https://visualstudio.microsoft.com/vs/community/) には、Windows 10 開発者ツール、ユニバーサル アプリ テンプレート、コード エディター、強力なデバッガー、Windows Mobile エミュレーター、豊富な言語サポートなど、すべて実稼働環境で使用できる状態が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3de4b-132">The free, full-featured [Visual Studio Community 2017](https://visualstudio.microsoft.com/vs/community/) includes Windows 10 developer tools, universal app templates, a code editor, a powerful debugger, Windows Mobile emulators, rich language support and much more—all ready to use in production.</span></span> <span data-ttu-id="3de4b-133">Professional [*および* *Enterprise のバージョンでは*](https://visualstudio.microsoft.com/vs/compare/) 、さらに多くの機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-133">The [*Professional* and *Enterprise*](https://visualstudio.microsoft.com/vs/compare/) versions provide even more features.</span></span>

#### <span data-ttu-id="3de4b-134">要件</span><span class="sxs-lookup"><span data-stu-id="3de4b-134">Requirements</span></span>

-   <span data-ttu-id="3de4b-135">[**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
    ): 無料の *Community* エディションを含む任意のバージョン。</span><span class="sxs-lookup"><span data-stu-id="3de4b-135">[**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
): any version, including the free *Community* edition.</span></span>
-   <span data-ttu-id="3de4b-136">[**Windows 10 SDK:**](/windows/uwp/xbox-apps/development-environment-setup)Visual Studio *2017 インストーラーでこのオプション コンポーネントを選択します*。</span><span class="sxs-lookup"><span data-stu-id="3de4b-136">[**Windows 10 SDK**](/windows/uwp/xbox-apps/development-environment-setup): Select this optional component in the *Visual Studio 2017 Installer*.</span></span>
    
#### <span data-ttu-id="3de4b-137">セットアップ</span><span class="sxs-lookup"><span data-stu-id="3de4b-137">Setup</span></span>

1.  <span data-ttu-id="3de4b-138">手順に従って [、PWA をユニバーサル Windows アプリとしてセットアップして実行します](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app)。</span><span class="sxs-lookup"><span data-stu-id="3de4b-138">Follow the steps to [set up and run your PWA as a Universal Windows app](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app).</span></span> <span data-ttu-id="3de4b-139">これにより、ユニバーサル Windows API にアクセスできる完全に機能する Windows 10 アプリが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-139">With this, you'll have a fully functioning Windows 10 app capable of accessing Universal Windows APIs.</span></span>
2.  <span data-ttu-id="3de4b-140">[Visual Studio リモート デバッガー](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017 &preserve-view=true) を使用して、(他の Windows 10 リモート デバイスと同様に) Xbox One で PWA を展開およびデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-140">You can now deploy and debug your PWA (as a UWP app) on the Xbox One (as with any other Windows 10 remote device) using the [Visual Studio remote debugger](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017 &preserve-view=true).</span></span> <span data-ttu-id="3de4b-141">または、次の手順を使用して [、Xbox 用 Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox) を使用して PWA をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-141">Alternately, you can install your PWA using the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox) using the following steps.</span></span>
3.  <span data-ttu-id="3de4b-142">Xbox 用 Device Portal で、[ホーム] > [マイ ゲーム] & [> 追加] に移動し、アプリ パッケージと依存関係をアップロードするオプション *を選択します*。</span><span class="sxs-lookup"><span data-stu-id="3de4b-142">From the Device Portal for Xbox, go to Home > My games & apps > Add, choose the option to upload *App Package and Dependencies*.</span></span>
4.  <span data-ttu-id="3de4b-143">手順 1 でアプリ用に生成したパッケージ フォルダーに移動し、アップロードする *.appx* ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-143">Navigate to the package folder you generated for your app in Step 1 and select the *.appx* file for upload.</span></span> <span data-ttu-id="3de4b-144">[ *.appx ファイルは*](/windows/uwp/packaging/packaging-uwp-apps)、テスト目的で任意のデバイスにサイドロードできる UWP アプリ パッケージ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="3de4b-144">The [*.appx* file](/windows/uwp/packaging/packaging-uwp-apps) is a UWP app package file that can be sideloaded on any device for testing purposes.</span></span>
5.  <span data-ttu-id="3de4b-145">次に、[**依存関係] ボタンを**タップ\*\* し、アプリの依存関係サブフォルダーを選択し、それぞれをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3de4b-145">Next tap the **Dependencies** button and select the *dependencies* sub-folder for your app and upload each one.</span></span> <span data-ttu-id="3de4b-146">この手順は、Xbox 用 Device Portal からアプリを展開する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="3de4b-146">This step is only required for deploying apps from the Device Portal for Xbox.</span></span> <span data-ttu-id="3de4b-147">Visual Studioデバッグとエンド ユーザーのコンピューターが Microsoft Store から配信される場合に、これらの依存関係が既にインストールされている場合に、依存関係が提供されます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-147">Visual Studio delivers dependencies when remote debugging and the end user's machine will already have these installed when delivered from the Microsoft Store.</span></span>
6.  <span data-ttu-id="3de4b-148">アプリ パッケージと依存関係がアップロードされた後、[展開] セクションの下\*\* の [**移動**] ボタンをクリックすると、アプリがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-148">With the app package and the dependencies uploaded, click the **Go** button under the *Deploy* section and the app will be installed.</span></span> <span data-ttu-id="3de4b-149">Xbox からアプリを起動する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="3de4b-149">You're ready to launch your app from Xbox!</span></span>
    
## <span data-ttu-id="3de4b-150">Xbox の PAS の UX に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3de4b-150">UX considerations for PWAs on Xbox</span></span>

### <span data-ttu-id="3de4b-151">"10 フィート エクスペリエンス" の設計</span><span class="sxs-lookup"><span data-stu-id="3de4b-151">Design for the "10-Foot Experience"</span></span>

<span data-ttu-id="3de4b-152">Xbox One は "10 フィート エクスペリエンス" と見なされます。つまり、ユーザーは画面から少なくとも 10 フィート離れた場所に座っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3de4b-152">Xbox One is considered a "10-foot experience", meaning that your users will likely be sitting a minimum of 10 feet away from the screen.</span></span> <span data-ttu-id="3de4b-153">そのため、マウスとキーボードを使った従来のデスクトップ Web ブラウザー エクスペリエンスとは対照的に、アプリをその距離でどのように使うのか検討します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-153">As such, consider how your app might be used at that distance as opposed to the traditional desktop web browser experience with a mouse and keyboard.</span></span> <span data-ttu-id="3de4b-154">設計と UX のガイダンスについては [、Xbox およびテレビ向け設計を参照してください](/windows/uwp/design/devices/designing-for-tv)。</span><span class="sxs-lookup"><span data-stu-id="3de4b-154">For design and UX guidance, check out [Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv).</span></span>

### <span data-ttu-id="3de4b-155">"TV SafeZone" について</span><span class="sxs-lookup"><span data-stu-id="3de4b-155">Understand the "TV SafeZone"</span></span>

<span data-ttu-id="3de4b-156">テレビの製造元は、アプリ [をクリップできるコンテンツ](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) の周囲に「セーフ ゾーン」を適用します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-156">Television manufacturers will apply a ["safe-zone"](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) around the content that can clip your app.</span></span> <span data-ttu-id="3de4b-157">既定では、アプリの周囲に安全な境界線が適用されます。ただし、次を呼び出して指定することで、アプリが全画面サイズを取る [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) 必要があります [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode) 。</span><span class="sxs-lookup"><span data-stu-id="3de4b-157">By default, we apply a safe border around your app to account for this, however you can ensure that your app takes the full screen size by calling [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) and specifying [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode):</span></span>

```javascript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```  

<span data-ttu-id="3de4b-158">詳細については、名前空間のドキュメント [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3de4b-158">For more, check out the [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) namespace documentation.</span></span>

### <span data-ttu-id="3de4b-159">XY フォーカスとナビゲーションを管理する</span><span class="sxs-lookup"><span data-stu-id="3de4b-159">Manage XY focus and navigation</span></span>

<span data-ttu-id="3de4b-160">Xbox のユーザー入力方法はゲームパッドまたはリモコンで [、XY](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)ナビゲーション システムを使います。ユーザーは、上、下、左、右に移動して、フォーカスをコントロールからコントロールに移動できます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-160">User input methods for Xbox are gamepad or remote control, which use a [XY navigation system](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction), allowing the user to shift the focus from control to control by moving up, down, left, and right.</span></span>

<span data-ttu-id="3de4b-161">そのため、アプリが XY ナビゲーションで正常に動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de4b-161">As such, you'll want to make sure your app works well with XY navigation.</span></span> <span data-ttu-id="3de4b-162">また、必ずマウス[\*\* モード](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)を無効にしてください。マウス モードは、UWP アプリに対して既定でオンになっています (アプリの Xbox エクスペリエンスには適用されない可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="3de4b-162">Also, be sure to [disable *mouse mode*](/windows/uwp/xbox-apps/how-to-disable-mouse-mode), which is on by default for UWP apps (and probably not applicable to your app's Xbox experience).</span></span>

<span data-ttu-id="3de4b-163">次のコードはモードをオフ `mouse` にし、ゲームパッド入力で DOM キーボード イベントを生成できます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-163">The following code turns off `mouse` mode and enables gamepad input to generate DOM keyboard events:</span></span>

```javascript
navigator.gamepadInputEmulation = "keyboard";
```  

<span data-ttu-id="3de4b-164">または、マウスをオフにしたり、DOM キーボード イベントを生成したり、標準の Web や WinRT ゲームパッド API を使用したりすることもできます `gamepad` 。</span><span class="sxs-lookup"><span data-stu-id="3de4b-164">Alternately, you can specify `gamepad`, which also turns off mouse, does not generate DOM keyboard events, and allows you to use the standard web and/or WinRT gamepad APIs.</span></span>

<span data-ttu-id="3de4b-165">方向ナビゲーションを有効にするには、次に説明 [する TVJS ライブラリ](#tvjs)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3de4b-165">To enable directional navigation, check out the [TVJS library](#tvjs), discussed next.</span></span>

### <span data-ttu-id="3de4b-166">TVJS</span><span class="sxs-lookup"><span data-stu-id="3de4b-166">TVJS</span></span>

<span data-ttu-id="3de4b-167">[TVJS は、テレビ用](https://github.com/Microsoft/TVHelpers) の Web アプリケーションを簡単に構築できるヘルパー ライブラリのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3de4b-167">[TVJS is a collection of helper libraries](https://github.com/Microsoft/TVHelpers) that make it easier to build web applications for the TV.</span></span> <span data-ttu-id="3de4b-168">Xbox でも実行されるホストされた Web アプリを構築している場合、TVJS は方向ナビゲーションの\*\* サポートを追加したり、テレビのコンテンツを操作しやすくするコントロールを提供したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-168">If you are building a hosted web app that will also run on the Xbox, TVJS can help add support for *directional navigation*, as well as provide several controls that make it easier to interact with content on the TV.</span></span>

<span data-ttu-id="3de4b-169">[方向ナビゲーション](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) は、テレビ アプリのページ内で自動 2 次元ナビゲーションを提供する TVJS 機能です。</span><span class="sxs-lookup"><span data-stu-id="3de4b-169">[Directional navigation](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) is a TVJS feature that provides automatic two-dimensional navigation within the pages of your TV app.</span></span> <span data-ttu-id="3de4b-170">アプリでは、アプリのページ内のナビゲーションをトラップして処理したり、UI の各要素の有効なフォーカス ターゲットを明示的に指定したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3de4b-170">With it, there's no need to trap and handle navigation within the pages of your app, or to explicitly specify all the valid focus targets for each element in the UI.</span></span> <span data-ttu-id="3de4b-171">自動フォーカス処理により、ユーザーは直感的で堅牢な方法で移動できます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-171">Automatic focus handling enables users can navigate around in an intuitive and robust way.</span></span>

<span data-ttu-id="3de4b-172">ユーザーがコントローラーの方向ボタンを使ってアプリ UI を移動すると、自動フォーカス アルゴリズムは潜在的なフォーカス ターゲットのセットを見て、移動先の次の要素を決定し、自動的にその要素にフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-172">As your user navigates the app UI with the controller direction buttons, the automatic focus algorithm looks at the set of potential focus targets, determines the next element to move to and then automatically sets focus to that element.</span></span> <span data-ttu-id="3de4b-173">次の要素を決定するために、このアルゴリズムは、方向入力、過去のフォーカス履歴、ページ上の UI 要素の物理的なレイアウトを組み合わせたものになります。</span><span class="sxs-lookup"><span data-stu-id="3de4b-173">To determine the next element, the algorithm combines directional input, past focus history, and the physical layout of UI elements on the page.</span></span>

<span data-ttu-id="3de4b-174">方向ナビゲーションを有効にするには、次のスクリプト リファレンスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de4b-174">To enable directional navigation, include the following script reference:</span></span>

```html
<script src="directionalnavigation-1.0.0.0.js"></script>
```  

<span data-ttu-id="3de4b-175">既定では、フォーカス可能な要素は 、 `<a>` `<button>` `<input>` `<select>` `<textarea>` 。</span><span class="sxs-lookup"><span data-stu-id="3de4b-175">By default, only `<a>`, `<button>`, `<input>`, `<select>`, and `<textarea>` elements are focusable.</span></span> <span data-ttu-id="3de4b-176">他の要素にフォーカスを設定するには、有効な [tabindex を割り当てる必要があります](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)。</span><span class="sxs-lookup"><span data-stu-id="3de4b-176">To enable focus on other elements, assign them a valid [tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex).</span></span>

```html
<div tabindex="0″>This div is eligible for focus</div>
```  

ルート要素の変更、初期フォーカスの設定、次のフォーカスの上書き、フォーカス用のコントロールの最適化、入力のカスタマイズを行う方法については [、DirectionalNavigation](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation) のドキュメントを参照してください。 <span data-ttu-id="3de4b-178">その他にも役立つサンプルが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="3de4b-178">There's also a number of other useful samples.</span></span>

## <span data-ttu-id="3de4b-179">Xbox のメディア PAS</span><span class="sxs-lookup"><span data-stu-id="3de4b-179">Media PWAs on Xbox</span></span>

<span data-ttu-id="3de4b-180">Xbox One 用のメディア再生 PWA を構築する場合は、次の考慮事項に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3de4b-180">If you're building a media playback PWA for Xbox One, be aware of the following considerations.</span></span>

### <span data-ttu-id="3de4b-181">ブラウザーでの暗号化されたメディア拡張機能 (EME)</span><span class="sxs-lookup"><span data-stu-id="3de4b-181">Encrypted Media Extensions (EME) in the browser</span></span>

<span data-ttu-id="3de4b-182">Xbox One の Microsoft Edge ブラウザーは、 [暗号化](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API) メディア拡張機能 (EME) をサポートしていない。</span><span class="sxs-lookup"><span data-stu-id="3de4b-182">The Microsoft Edge browser on Xbox One does not support [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API) (EME).</span></span> <span data-ttu-id="3de4b-183">メディア PWA がデジタル著作権管理 (DRM) にメディアを使用している場合、Xbox のブラウザーから実行できません。</span><span class="sxs-lookup"><span data-stu-id="3de4b-183">If your media PWA uses it for digital rights management (DRM), you won't be able to run it from the browser on your Xbox.</span></span> <span data-ttu-id="3de4b-184">代わりに、前述のように [、PWABuilder](#deploying-and-testing-pwas-on-xbox)または Visual Studioを使用して Xbox One アプリとしてプロトタイプを作成してテストします。</span><span class="sxs-lookup"><span data-stu-id="3de4b-184">Instead, prototype and test it as a [Xbox One app using PWABuilder or Visual Studio](#deploying-and-testing-pwas-on-xbox), as described above.</span></span> <span data-ttu-id="3de4b-185">EME が完全にサポートされている Windows の Microsoft Edge ブラウザーでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-185">You can also run it on the Microsoft Edge browser on Windows, where EME is fully supported.</span></span>

### <span data-ttu-id="3de4b-186">システム メディア トランスポート コントロールとの統合</span><span class="sxs-lookup"><span data-stu-id="3de4b-186">Integrating with System Media Transport Controls</span></span>

<span data-ttu-id="3de4b-187">アプリがメディア アプリの場合は、アプリが画面ボタン[、Cortana](https://support.xbox.com/xbox-one/console/cortana-voice-commands)音声コマンド、ナビゲーション ウィンドウのシステム メディア トランスポート コントロール、または他のデバイス上の[](/windows/uwp/audio-video-camera/system-media-transport-controls)Xbox および[Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) [One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2)アプリを介して、ユーザーによって開始されたメディア コントロールに応答することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3de4b-187">If your app is a media app, it is important that your app responds to the media controls initiated by the user via on-screen buttons, [Cortana voice commands](https://support.xbox.com/xbox-one/console/cortana-voice-commands), the [System Media Transport Controls](/windows/uwp/audio-video-camera/system-media-transport-controls) in the nav pane, or the [Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) and [Xbox One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2) apps on other devices.</span></span> <span data-ttu-id="3de4b-188">TVJS ライブラリから[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)コントロール[](#tvjs)を見て、これらのコントロールと自動的に統合されます。</span><span class="sxs-lookup"><span data-stu-id="3de4b-188">Take a look at the [MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview) control from the [TVJS library](#tvjs), which automatically integrates with these controls.</span></span> <span data-ttu-id="3de4b-189">または、システム メディア トランスポート [コントロールと手動で統合することもできます](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls)。</span><span class="sxs-lookup"><span data-stu-id="3de4b-189">Alternately, you can manually [integrate with the System Media Transport Controls](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls).</span></span>

### <span data-ttu-id="3de4b-190">PlayReady コンテンツの暗号化</span><span class="sxs-lookup"><span data-stu-id="3de4b-190">PlayReady content encryption</span></span>

<span data-ttu-id="3de4b-191">この記事の執筆時点では、[ `cbcs` ](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme)エンコードのサポートは XBox One (バージョン 1709 以上) の PlayReady クライアントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="3de4b-191">At the time of this writing, [`cbcs` encoding support is limited](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme) to the PlayReady client for XBox One (version 1709 or higher).</span></span> <span data-ttu-id="3de4b-192">PWA のメディアが *cbcs* 暗号化のみをサポートしている場合、Windows ではアプリの機能が制限されている (または完全に利用できない) 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3de4b-192">If the media for your PWA only supports *cbcs* encryption, be aware that your app's functionality will be likely be limited (or completely unavailable) on Windows.</span></span>

## <span data-ttu-id="3de4b-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="3de4b-193">See also</span></span>
<span data-ttu-id="3de4b-194">[South South South Video](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): React.js を使用して構築され、Web サーバーでホストされる Xbox 用のサンプル ビデオ アプリです。</span><span class="sxs-lookup"><span data-stu-id="3de4b-194">[South Ridge Video](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): A sample video app for Xbox built with React.js and hosted on a web server.</span></span>

<span data-ttu-id="3de4b-195">[Xbox とテレビ向け](/windows/uwp/design/devices/designing-for-tv)設計: ユニバーサル Windows プラットフォーム (UWP) アプリを設計して、Xbox One とテレビ画面で見栄えよく機能するようにします。</span><span class="sxs-lookup"><span data-stu-id="3de4b-195">[Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv): Design your Universal Windows Platform (UWP) app so that it looks good and functions well on Xbox One and television screens.</span></span>

<span data-ttu-id="3de4b-196">[Xbox のベスト プラクティス](/windows/uwp/xbox-apps/tailoring-for-xbox): 次のベスト プラクティスに従って、Xbox One 用にアプリを調整します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-196">[Xbox best practices](/windows/uwp/xbox-apps/tailoring-for-xbox): Follow these best practices to tailor your app for Xbox One.</span></span>

<span data-ttu-id="3de4b-197">[Microsoft Store の PWA](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store): PWA を Microsoft Store に提出する方法 (および理由) を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3de4b-197">[PWAs in the Microsoft Store](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store): Here's how (and why!) to Submit your PWA to the Microsoft Store.</span></span>

<span data-ttu-id="3de4b-198">[Xbox One の UWP: Xbox One](/windows/uwp/xbox-apps/)向け UWP アプリ開発の完全なガイド。</span><span class="sxs-lookup"><span data-stu-id="3de4b-198">[UWP on Xbox One](/windows/uwp/xbox-apps/): A complete guide to UWP app development for Xbox One.</span></span>
