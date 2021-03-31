---
description: PWA が Xbox に優れたエクスペリエンスを提供するようにする
title: Xbox One 用プログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ Web アプリ、PWA、Edge、Windows、UWP、Xbox、Xbox One、TVJS
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3ac4174c821f221d6d666a25880867275ca5cbd5
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397672"
---
# <a name="progressive-web-apps-for-xbox-one"></a><span data-ttu-id="9db5f-104">Xbox One 用プログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="9db5f-104">Progressive Web Apps for Xbox One</span></span>  

<span data-ttu-id="9db5f-105">既存のフレームワーク、CDN、サーバー バックエンドを引き続き使用しながら、Web アプリケーションを拡張し、Microsoft Store 経由で Xbox One アプリとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-105">You can extend a web application and make it available as an Xbox One app via Microsoft Store while still continuing to use your existing frameworks, CDN and server backend.</span></span>  <span data-ttu-id="9db5f-106">また、すべてのユニバーサル Windows プラットフォーム \(UWP\) アプリと同様に、Xbox One で実行されているプログレッシブ Web アプリ \(PWAs\) もネイティブ Windows 10 API を呼び出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9db5f-106">And like all Universal Windows Platform \(UWP\) apps, Progressive Web Apps \(PWAs\) running on Xbox One can also call native Windows 10 APIs.</span></span>  <span data-ttu-id="9db5f-107">特にメディア再生アプリのカテゴリでは、Xbox One で使用可能な PWA [が既に多数存在します](#media-pwas-on-xbox)。</span><span class="sxs-lookup"><span data-stu-id="9db5f-107">There are already a number of PWAs available for the Xbox One, particularly in the category of [media playback apps](#media-pwas-on-xbox).</span></span>  

<span data-ttu-id="9db5f-108">ほとんどの場合[、PWA](https://www.pwabuilder.com)ビルダー ツールまたは Visual Studio IDE を使用して PWA を[UWP](https://visualstudio.microsoft.com/vs)アプリとして実行するために必要なファイルを生成して[、Windows](./windows-features.md)と同じ方法で Xbox One 用の PWA をパッケージ化できます。 `appxmanifest`</span><span class="sxs-lookup"><span data-stu-id="9db5f-108">For the most part, you can package your PWA for Xbox One in the [same way you would for Windows](./windows-features.md), using the [PWA Builder](https://www.pwabuilder.com) tools or [Visual Studio](https://visualstudio.microsoft.com/vs) IDE to generate the `appxmanifest` file required to run your PWA as a UWP app.</span></span>  <span data-ttu-id="9db5f-109">ただし、このガイドではいくつかの重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="9db5f-109">However, there are several key differences this guide will walk you through.</span></span>  

## <a name="deploying-and-testing-pwas-on-xbox"></a><span data-ttu-id="9db5f-110">Xbox での PWA の展開とテスト</span><span class="sxs-lookup"><span data-stu-id="9db5f-110">Deploying and testing PWAs on Xbox</span></span>  

<span data-ttu-id="9db5f-111">開始するには、次の手順に [従って *Xbox One 開発者モードをアクティブにします*](/windows/uwp/xbox-apps/devkit-activation)。</span><span class="sxs-lookup"><span data-stu-id="9db5f-111">To get started, follow these [steps to activate *Xbox One Developer Mode*](/windows/uwp/xbox-apps/devkit-activation).</span></span>  <span data-ttu-id="9db5f-112">開発者モードをアクティブ化した状態 [で *、Xbox*](/windows/uwp/debug-test-perf/device-portal-xbox) 用デバイス ポータルをセットアップして、開発環境のブラウザーから Xbox にリモート アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-112">With Developer Mode activated, [set up *Device Portal for Xbox*](/windows/uwp/debug-test-perf/device-portal-xbox) to gain remote access to your Xbox from the browser in your dev environment.</span></span>  

<span data-ttu-id="9db5f-113">これで、PWA ビルダーまたはアプリを使用してテスト用にアプリを展開するVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="9db5f-113">Now you're ready to deploy your app for testing using either PWA Builder or Visual Studio.</span></span>  

### <a name="option-1--pwa-builder"></a><span data-ttu-id="9db5f-114">オプション 1: PWA ビルダー</span><span class="sxs-lookup"><span data-stu-id="9db5f-114">Option 1:  PWA Builder</span></span>  

<span data-ttu-id="9db5f-115">[PWA Builder](https://www.pwabuilder.com) は、ノード Node.js \(NPM\) からインストールパッケージ マネージャーアプリです。</span><span class="sxs-lookup"><span data-stu-id="9db5f-115">[PWA Builder](https://www.pwabuilder.com) is a Node.js app you can install from Node Package Manager \(NPM\).</span></span>  <span data-ttu-id="9db5f-116">Web サイトのメタデータを使用して、Android、iOS、Windows 全体でネイティブホスト型アプリを生成します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-116">It uses the metadata of your website to generate native hosted apps across Android, iOS and Windows.</span></span>  <span data-ttu-id="9db5f-117">サイトに既に [Web](https://developer.mozilla.org/docs/Web/Manifest)アプリ マニフェストがある場合、PWA ビルダーは Web アプリ マニフェストを使用してプラットフォーム固有のインストール パッケージを生成します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-117">If your site already has a [web app manifest](https://developer.mozilla.org/docs/Web/Manifest), PWA Builder will use it to generate platform-specific installation packages.</span></span>  <span data-ttu-id="9db5f-118">それ以外の場合、PWA ビルダーはサイトの特性に `manifest.json` 基づいて基本的なファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-118">Otherwise, PWA Builder will generate a basic `manifest.json` file based on the characteristics of your site.</span></span>  

#### <a name="requirements"></a><span data-ttu-id="9db5f-119">要件</span><span class="sxs-lookup"><span data-stu-id="9db5f-119">Requirements</span></span>  

*   <span data-ttu-id="9db5f-120">[Node.js](https://nodejs.org)NPM を含む。</span><span class="sxs-lookup"><span data-stu-id="9db5f-120">[Node.js](https://nodejs.org), which includes NPM.</span></span>  

#### <a name="setup"></a><span data-ttu-id="9db5f-121">セットアップ</span><span class="sxs-lookup"><span data-stu-id="9db5f-121">Setup</span></span>  

1.  <span data-ttu-id="9db5f-122">ノード コマンド プロンプトを開き、PWA ビルダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9db5f-122">Open a Node command prompt to install PWA Builder:</span></span>  
    
    ```shell
    npm install pwabuilder --global
    ```  
    
1.  <span data-ttu-id="9db5f-123">Web サイトの URL で PWA ビルダーを実行します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-123">Run PWA Builder on your website URL:</span></span>  
    
    ```shell
    pwabuilder https://example.com/ -windows10
    ```  
    
    <span data-ttu-id="9db5f-124">*-windows10 フラグは*、パッケージの生成を Windows 10 \(UWP\) に制限します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-124">The *-windows10* flag limits package generation to Windows 10 \(UWP\).</span></span>  <span data-ttu-id="9db5f-125">iOS や Android を含む、サポートされているプラットフォーム全体でパッケージを生成するには、パッケージを省略できます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-125">You can omit it to generate packages across all supported platforms, including iOS and Android.</span></span>  <span data-ttu-id="9db5f-126">詳細については [、PWA Builder ドキュメント](https://docs.pwabuilder.com) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9db5f-126">See the [PWA Builder docs](https://docs.pwabuilder.com) for more info.</span></span>  
    
1.  <span data-ttu-id="9db5f-127">Xbox 用デバイス[ポータル](/windows/uwp/debug-test-perf/device-portal-xbox)で、[ホーム マイ ゲーム & アプリの追加] に移動し、緩いファイルをアップロードするオプションを選択し、現在のディレクトリで PWA ビルダーによって生成された  >    >   Windows 10 アプリ マニフェスト フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-127">From the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox), go to **Home** > **My games & apps** > **Add**, choose the option to **upload loose files**, and select the Windows 10 app manifest folder generated by PWA Builder in the current directory.</span></span>  
1.  <span data-ttu-id="9db5f-128">ウィザードの手順を実行して、インストール プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-128">Step through the wizard to complete the installation process.</span></span>  <span data-ttu-id="9db5f-129">一度インストールします。</span><span class="sxs-lookup"><span data-stu-id="9db5f-129">Once installed.</span></span>  <span data-ttu-id="9db5f-130">Xbox One ダッシュボードから PWA を表示および起動できます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-130">you'll be able to see and launch your PWA from the Xbox One dashboard.</span></span>  
    
### <a name="option-2--visual-studio"></a><span data-ttu-id="9db5f-131">オプション 2: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9db5f-131">Option 2:  Visual Studio</span></span>  

<span data-ttu-id="9db5f-132">無料のフル機能の [Visual Studio コミュニティ 2017](https://visualstudio.microsoft.com/vs/community) には、Windows 10 開発者ツール、ユニバーサル アプリ テンプレート、コード エディター、強力なデバッガー、Windows Mobile エミュレーター、豊富な言語サポートなど、すべてが実稼働環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-132">The free, full-featured [Visual Studio Community 2017](https://visualstudio.microsoft.com/vs/community) includes Windows 10 developer tools, universal app templates, a code editor, a powerful debugger, Windows Mobile emulators, rich language support and much more—all ready to use in production.</span></span>  <span data-ttu-id="9db5f-133">プロフェッショナル [バージョンとエンタープライズ バージョンでは](https://visualstudio.microsoft.com/vs/compare) 、さらに多くの機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-133">The [Professional and Enterprise](https://visualstudio.microsoft.com/vs/compare) versions provide even more features.</span></span>  

#### <a name="requirements"></a><span data-ttu-id="9db5f-134">要件</span><span class="sxs-lookup"><span data-stu-id="9db5f-134">Requirements</span></span>  

*   <span data-ttu-id="9db5f-135">[Visual Studio 2017:](https://visualstudio.microsoft.com/vs)無料のコミュニティ エディションを含む任意のバージョン。</span><span class="sxs-lookup"><span data-stu-id="9db5f-135">[Visual Studio 2017](https://visualstudio.microsoft.com/vs):  Any version, including the free Community edition.</span></span>  
*   <span data-ttu-id="9db5f-136">[Windows 10 SDK](/windows/uwp/xbox-apps/development-environment-setup): 2017 インストーラーでこのオプション コンポーネントVisual Studio選択します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-136">[Windows 10 SDK](/windows/uwp/xbox-apps/development-environment-setup):  Select this optional component in the Visual Studio 2017 Installer.</span></span>  

#### <a name="setup"></a><span data-ttu-id="9db5f-137">セットアップ</span><span class="sxs-lookup"><span data-stu-id="9db5f-137">Setup</span></span>  

1.  <span data-ttu-id="9db5f-138">手順に従って [、ユニバーサル Windows アプリとして PWA をセットアップして実行します](./windows-features.md#set-up-and-run-your-universal-windows-app)。</span><span class="sxs-lookup"><span data-stu-id="9db5f-138">Follow the steps to [set up and run your PWA as a Universal Windows app](./windows-features.md#set-up-and-run-your-universal-windows-app).</span></span>  <span data-ttu-id="9db5f-139">これにより、ユニバーサル Windows API にアクセスできる完全に機能する Windows 10 アプリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9db5f-139">With this, you'll have a fully functioning Windows 10 app capable of accessing Universal Windows APIs.</span></span>  
1.  <span data-ttu-id="9db5f-140">これで、Windows リモート デバッガーを使用して、Xbox One \(他の Windows 10 リモート デバイス\と同様に [Visual Studio)](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017&preserve-view=true
)で PWA \(UWP アプリ\) を展開およびデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-140">You can now deploy and debug your PWA \(as a UWP app\) on the Xbox One \(as with any other Windows 10 remote device\) using the [Visual Studio remote debugger](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017&preserve-view=true
).</span></span>  <span data-ttu-id="9db5f-141">または、次の手順を使用して Xbox 用デバイス ポータルを使用して [PWA](/windows/uwp/debug-test-perf/device-portal-xbox) をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-141">Alternately, you can install your PWA using the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox) using the following steps.</span></span>  
1.  <span data-ttu-id="9db5f-142">Xbox のデバイス ポータルで、[ホーム マイ ゲーム] \& [アプリの追加] に移動し、[アプリ パッケージと依存関係] をアップロードするオプション  >    >  を選択します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-142">From the Device Portal for Xbox, go to **Home** > **My games \& apps** > **Add**, choose the option to upload **App Package and Dependencies**.</span></span>  
1.  <span data-ttu-id="9db5f-143">手順 1 でアプリ用に生成したパッケージ フォルダーに移動し、アップロードする `.appx` ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-143">Navigate to the package folder you generated for your app in Step 1 and select the `.appx` file for upload.</span></span>  <span data-ttu-id="9db5f-144">[.appx ファイルは](/windows/uwp/packaging/packaging-uwp-apps)、テスト目的で任意のデバイスにサイドロードできる UWP アプリ パッケージ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="9db5f-144">The [.appx file](/windows/uwp/packaging/packaging-uwp-apps) is a UWP app package file that can be sideloaded on any device for testing purposes.</span></span>  
1.  <span data-ttu-id="9db5f-145">次に、[ **依存関係] ボタンを** タップし、アプリのサブフォルダーを選択し `dependencies` 、それぞれをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9db5f-145">Next tap the **Dependencies** button and select the `dependencies` sub-folder for your app and upload each one.</span></span>  <span data-ttu-id="9db5f-146">この手順は、Xbox 用デバイス ポータルからアプリを展開する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="9db5f-146">This step is only required for deploying apps from the Device Portal for Xbox.</span></span>  <span data-ttu-id="9db5f-147">Visual Studio、リモート デバッグ時に依存関係が提供され、エンド ユーザーのコンピューターは Microsoft Store から配信された場合に既にこれらの依存関係がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-147">Visual Studio delivers dependencies when remote debugging and the end user's machine will already have these installed when delivered from the Microsoft Store.</span></span>  
1.  <span data-ttu-id="9db5f-148">アプリ パッケージと依存関係がアップロードされた場合は、[展開] セクションの**[**移動] ボタンをクリックすると、アプリがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-148">With the app package and the dependencies uploaded, click the **Go** button under the *Deploy* section and the app will be installed.</span></span>  <span data-ttu-id="9db5f-149">Xbox からアプリを起動する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="9db5f-149">You're ready to launch your app from Xbox!</span></span>  

## <a name="ux-considerations-for-pwas-on-xbox"></a><span data-ttu-id="9db5f-150">Xbox の PWA の UX に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="9db5f-150">UX considerations for PWAs on Xbox</span></span>  

### <a name="design-for-the-10-foot-experience"></a><span data-ttu-id="9db5f-151">"10-Foot Experience" の設計</span><span class="sxs-lookup"><span data-stu-id="9db5f-151">Design for the "10-Foot Experience"</span></span>  

<span data-ttu-id="9db5f-152">Xbox One は"10 フィートのエクスペリエンス" と見なされます。つまり、ユーザーは画面から少なくとも 10 フィート離れた場所に座っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9db5f-152">Xbox One is considered a "10-foot experience", meaning that your users will likely be sitting a minimum of 10 feet away from the screen.</span></span>  <span data-ttu-id="9db5f-153">そのため、マウスとキーボードを使用した従来のデスクトップ Web ブラウザーエクスペリエンスとは対照的に、アプリをその距離でどのように使用する可能性があるのか検討してください。</span><span class="sxs-lookup"><span data-stu-id="9db5f-153">As such, consider how your app might be used at that distance as opposed to the traditional desktop web browser experience with a mouse and keyboard.</span></span>  <span data-ttu-id="9db5f-154">デザインと UX のガイダンスについては [、「Xbox とテレビのデザイン」を参照してください](/windows/uwp/design/devices/designing-for-tv)。</span><span class="sxs-lookup"><span data-stu-id="9db5f-154">For design and UX guidance, check out [Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv).</span></span>  

### <a name="understand-the-tv-safezone"></a><span data-ttu-id="9db5f-155">"TV SafeZone" を理解する</span><span class="sxs-lookup"><span data-stu-id="9db5f-155">Understand the "TV SafeZone"</span></span>  

<span data-ttu-id="9db5f-156">テレビメーカーは、アプリを [クリップできる](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) コンテンツの周囲にセーフ ゾーンを適用します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-156">Television manufacturers will apply a [safe-zone](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) around the content that can clip your app.</span></span>  <span data-ttu-id="9db5f-157">既定では、これを考慮するためにアプリの周囲に安全な枠線を適用しますが [、setDesiredBoundsMode](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) を呼び出して [useCoreWindow](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode)を指定することで、アプリが画面全体のサイズを取得できます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-157">By default, we apply a safe border around your app to account for this, however you can ensure that your app takes the full screen size by calling [setDesiredBoundsMode](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) and specifying [useCoreWindow](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode):</span></span>  

```javascript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```  

<span data-ttu-id="9db5f-158">詳細については [、Windows.UI.ViewManagement 名前空間のドキュメントを](/uwp/api/windows.ui.viewmanagement) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="9db5f-158">For more, check out the [Windows.UI.ViewManagement](/uwp/api/windows.ui.viewmanagement) namespace documentation.</span></span>  

### <a name="manage-xy-focus-and-navigation"></a><span data-ttu-id="9db5f-159">XY フォーカスとナビゲーションの管理</span><span class="sxs-lookup"><span data-stu-id="9db5f-159">Manage XY focus and navigation</span></span>  

<span data-ttu-id="9db5f-160">Xbox のユーザー入力方法はゲームパッドまたはリモート コントロールであり [、XY](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)ナビゲーション システムを使用して、ユーザーは上、下、左、右に移動して、コントロールからコントロールにフォーカスを移動できます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-160">User input methods for Xbox are gamepad or remote control, which use a [XY navigation system](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction), allowing the user to shift the focus from control to control by moving up, down, left, and right.</span></span>  

<span data-ttu-id="9db5f-161">そのため、アプリが XY ナビゲーションとうまく機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9db5f-161">As such, you'll want to make sure your app works well with XY navigation.</span></span>  <span data-ttu-id="9db5f-162">また、マウス モードを無効に [してください。これは](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)、UWP アプリの既定でオンになっています 。また、アプリの Xbox エクスペリエンス\には当てはめられない可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="9db5f-162">Also, be sure to [disable mouse mode](/windows/uwp/xbox-apps/how-to-disable-mouse-mode), which is on by default for UWP apps \(and probably not applicable to your app's Xbox experience\).</span></span>  

<span data-ttu-id="9db5f-163">次のコードはモードをオフ `mouse` にし、ゲームパッド入力で DOM キーボード イベントを生成できます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-163">The following code turns off `mouse` mode and enables gamepad input to generate DOM keyboard events:</span></span>  

```javascript
navigator.gamepadInputEmulation = "keyboard";
```  

<span data-ttu-id="9db5f-164">または、マウスをオフにし、DOM キーボード イベントを生成しない、標準の Web または WinRT ゲームパッド API を使用することもできます `gamepad` 。</span><span class="sxs-lookup"><span data-stu-id="9db5f-164">Alternately, you can specify `gamepad`, which also turns off mouse, does not generate DOM keyboard events, and allows you to use the standard web and/or WinRT gamepad APIs.</span></span>  

<span data-ttu-id="9db5f-165">方向ナビゲーションを有効にするには、次に説明する [TVJS ライブラリ](#tvjs)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9db5f-165">To enable directional navigation, check out the [TVJS library](#tvjs), discussed next.</span></span>  

### <a name="tvjs"></a><span data-ttu-id="9db5f-166">TVJS</span><span class="sxs-lookup"><span data-stu-id="9db5f-166">TVJS</span></span>  

<span data-ttu-id="9db5f-167">[TVJS は、テレビ用](https://github.com/Microsoft/TVHelpers) の Web アプリケーションを簡単に構築できるヘルパー ライブラリのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="9db5f-167">[TVJS is a collection of helper libraries](https://github.com/Microsoft/TVHelpers) that make it easier to build web applications for the TV.</span></span>  <span data-ttu-id="9db5f-168">Xbox でも実行されるホスト型 Web アプリを構築する場合、TVJS は方向ナビゲーションの サポートを追加したり、テレビ上のコンテンツを操作しやすくするための複数のコントロールを提供したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-168">If you are building a hosted web app that will also run on the Xbox, TVJS can help add support for *directional navigation*, as well as provide several controls that make it easier to interact with content on the TV.</span></span>  

<span data-ttu-id="9db5f-169">[方向ナビゲーション](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) は、テレビ アプリのページ内で自動 2 次元ナビゲーションを提供する TVJS 機能です。</span><span class="sxs-lookup"><span data-stu-id="9db5f-169">[Directional navigation](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) is a TVJS feature that provides automatic two-dimensional navigation within the pages of your TV app.</span></span>  <span data-ttu-id="9db5f-170">この機能を使用すると、アプリのページ内のナビゲーションをトラップして処理したり、UI 内の各要素の有効なフォーカス ターゲットを明示的に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9db5f-170">With it, there's no need to trap and handle navigation within the pages of your app, or to explicitly specify all the valid focus targets for each element in the UI.</span></span>  <span data-ttu-id="9db5f-171">自動フォーカス処理により、ユーザーは直感的で堅牢な方法で移動できます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-171">Automatic focus handling enables users can navigate around in an intuitive and robust way.</span></span>  

<span data-ttu-id="9db5f-172">ユーザーがコントローラーの方向ボタンを使用してアプリ UI を移動すると、自動フォーカス アルゴリズムは、一連の潜在的なフォーカス ターゲットを確認し、移動する次の要素を決定し、その要素にフォーカスを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-172">As your user navigates the app UI with the controller direction buttons, the automatic focus algorithm looks at the set of potential focus targets, determines the next element to move to and then automatically sets focus to that element.</span></span>  <span data-ttu-id="9db5f-173">次の要素を決定するために、アルゴリズムは、方向入力、過去のフォーカス履歴、ページ上の UI 要素の物理的なレイアウトを組み合わせたものになります。</span><span class="sxs-lookup"><span data-stu-id="9db5f-173">To determine the next element, the algorithm combines directional input, past focus history, and the physical layout of UI elements on the page.</span></span>  

<span data-ttu-id="9db5f-174">方向ナビゲーションを有効にするには、次のスクリプト参照を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9db5f-174">To enable directional navigation, include the following script reference:</span></span>  

```html
<script src="directionalnavigation-1.0.0.0.js"></script>
```  

<span data-ttu-id="9db5f-175">既定では、、 `<a>` 、 `<button>` 、 `<input>` `<select>` 、、および要素 `<textarea>` だけがフォーカス可能です。</span><span class="sxs-lookup"><span data-stu-id="9db5f-175">By default, only `<a>`, `<button>`, `<input>`, `<select>`, and `<textarea>` elements are focusable.</span></span>  <span data-ttu-id="9db5f-176">他の要素にフォーカスを設定するには、有効な [tabindex を割り当てる必要があります](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)。</span><span class="sxs-lookup"><span data-stu-id="9db5f-176">To enable focus on other elements, assign them a valid [tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex).</span></span>  

```html
<div tabindex="0″>This div is eligible for focus</div>
```  

ルート要素の変更、初期フォーカスの設定、次のフォーカスの上書き、フォーカスのコントロールの最適化、入力のカスタマイズ方法については [、DirectionalNavigation](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation) のドキュメントを参照してください。  <span data-ttu-id="9db5f-178">他にも役立つサンプルも多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="9db5f-178">There's also a number of other useful samples.</span></span>

## <a name="media-pwas-on-xbox"></a><span data-ttu-id="9db5f-179">Xbox のメディア PWA</span><span class="sxs-lookup"><span data-stu-id="9db5f-179">Media PWAs on Xbox</span></span>  

<span data-ttu-id="9db5f-180">Xbox One 用のメディア再生 PWA を作成する場合は、次の考慮事項に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9db5f-180">If you're building a media playback PWA for Xbox One, be aware of the following considerations.</span></span>  

### <a name="encrypted-media-extensions-eme-in-the-browser"></a><span data-ttu-id="9db5f-181">ブラウザーの暗号化されたメディア拡張機能 (EME)</span><span class="sxs-lookup"><span data-stu-id="9db5f-181">Encrypted Media Extensions (EME) in the browser</span></span>  

<span data-ttu-id="9db5f-182">Xbox One の Microsoft Edge[](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)ブラウザーでは、暗号化メディア拡張機能 \(EME\) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9db5f-182">The Microsoft Edge browser on Xbox One does not support [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API) \(EME\).</span></span>  <span data-ttu-id="9db5f-183">メディア PWA がデジタル著作権管理 \(DRM\) に使用している場合、Xbox のブラウザーからメディアを実行できません。</span><span class="sxs-lookup"><span data-stu-id="9db5f-183">If your media PWA uses it for digital rights management \(DRM\), you won't be able to run it from the browser on your Xbox.</span></span>  <span data-ttu-id="9db5f-184">代わりに、前述のように [、PWABuilder](#deploying-and-testing-pwas-on-xbox)またはアプリを使用して Xbox One アプリVisual Studioテストします。</span><span class="sxs-lookup"><span data-stu-id="9db5f-184">Instead, prototype and test it as a [Xbox One app using PWABuilder or Visual Studio](#deploying-and-testing-pwas-on-xbox), as described above.</span></span>  <span data-ttu-id="9db5f-185">EME が完全にサポートされている Windows の Microsoft Edge ブラウザーでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="9db5f-185">You can also run it on the Microsoft Edge browser on Windows, where EME is fully supported.</span></span>  

### <a name="integrating-with-system-media-transport-controls"></a><span data-ttu-id="9db5f-186">システム メディア トランスポート コントロールとの統合</span><span class="sxs-lookup"><span data-stu-id="9db5f-186">Integrating with System Media Transport Controls</span></span>  

<span data-ttu-id="9db5f-187">アプリがメディア アプリの場合は、アプリが画面のボタン [、Cortana](https://support.xbox.com/xbox-one/console/cortana-voice-commands)音声コマンド、ナビゲーション ウィンドウの System [Media Transport Controls、](/windows/uwp/audio-video-camera/system-media-transport-controls) または他のデバイスの [Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) と [Xbox One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2) アプリを介してユーザーによって開始されたメディア コントロールに応答することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9db5f-187">If your app is a media app, it is important that your app responds to the media controls initiated by the user via on-screen buttons, [Cortana voice commands](https://support.xbox.com/xbox-one/console/cortana-voice-commands), the [System Media Transport Controls](/windows/uwp/audio-video-camera/system-media-transport-controls) in the nav pane, or the [Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) and [Xbox One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2) apps on other devices.</span></span>  <span data-ttu-id="9db5f-188">これらのコントロールと自動的に統合される[TVJS](#tvjs)ライブラリから[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)コントロールを確認します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-188">Take a look at the [MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview) control from the [TVJS library](#tvjs), which automatically integrates with these controls.</span></span>  <span data-ttu-id="9db5f-189">または、システム メディア トランスポート コントロール [と手動で統合することもできます](/windows/uwp/audio-video-camera/system-media-transport-controls)。</span><span class="sxs-lookup"><span data-stu-id="9db5f-189">Alternately, you can manually [integrate with the System Media Transport Controls](/windows/uwp/audio-video-camera/system-media-transport-controls).</span></span>  

### <a name="playready-content-encryption"></a><span data-ttu-id="9db5f-190">PlayReady コンテンツの暗号化</span><span class="sxs-lookup"><span data-stu-id="9db5f-190">PlayReady content encryption</span></span>  

<span data-ttu-id="9db5f-191">この記事の執筆時点では [、cbcs エンコード](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme) サポートは XBox One 用の PlayReady クライアント \(バージョン 1709 以上\) に制限されています。</span><span class="sxs-lookup"><span data-stu-id="9db5f-191">At the time of this writing, [cbcs encoding support is limited](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme) to the PlayReady client for XBox One \(version 1709 or higher\).</span></span>  <span data-ttu-id="9db5f-192">PWA のメディアが **cbcs** 暗号化のみをサポートしている場合は、Windows でアプリの機能が制限される可能性が高い \(または完全に使用できない\) に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9db5f-192">If the media for your PWA only supports **cbcs** encryption, be aware that your app's functionality will be likely be limited \(or completely unavailable\) on Windows.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9db5f-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="9db5f-193">See also</span></span>  

<span data-ttu-id="9db5f-194">[サウス リッジ ビデオ](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): Web サーバー上でホストされている、React.js Xbox 用のサンプル ビデオ アプリ。</span><span class="sxs-lookup"><span data-stu-id="9db5f-194">[South Ridge Video](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video):  A sample video app for Xbox built with React.js and hosted on a web server.</span></span>  

<span data-ttu-id="9db5f-195">[Xbox とテレビ](/windows/uwp/design/devices/designing-for-tv)向けデザイン : ユニバーサル Windows プラットフォーム \(UWP\) アプリを設計して、Xbox One とテレビ画面でうまく機能するようにします。</span><span class="sxs-lookup"><span data-stu-id="9db5f-195">[Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv):  Design your Universal Windows Platform \(UWP\) app so that it looks good and functions well on Xbox One and television screens.</span></span>  

<span data-ttu-id="9db5f-196">[Xbox のベスト プラクティス](/windows/uwp/xbox-apps/tailoring-for-xbox): Xbox One 用にアプリを調整するには、次のベスト プラクティスに従います。</span><span class="sxs-lookup"><span data-stu-id="9db5f-196">[Xbox best practices](/windows/uwp/xbox-apps/tailoring-for-xbox):  Follow these best practices to tailor your app for Xbox One.</span></span>  

<span data-ttu-id="9db5f-197">[Microsoft ストアの PWA](./microsoft-store.md): PWA を Microsoft ストアに送信する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9db5f-197">[PWAs in the Microsoft Store](./microsoft-store.md):  Here's how \(and why?\) to Submit your PWA to the Microsoft Store.</span></span>  

<span data-ttu-id="9db5f-198">[Xbox One の UWP: Xbox](/windows/uwp/xbox-apps/index)One 用の UWP アプリ開発の完全なガイド。</span><span class="sxs-lookup"><span data-stu-id="9db5f-198">[UWP on Xbox One](/windows/uwp/xbox-apps/index):  A complete guide to UWP app development for Xbox One.</span></span>  
