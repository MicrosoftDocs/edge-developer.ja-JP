---
description: このガイドでは、Windows でプログレッシブ Web アプリ (Chromium) を構築するための PWA の基本とツールの概要を説明します。
title: プログレッシブ Web アプリ (Chromium) の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/16/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: プログレッシブ Web アプリ、PWA、Edge、Windows、PWABuilder、Web マニフェスト、サービス ワーカー、プッシュ
ms.openlocfilehash: 6a40742c1065dbc3b8aaeeeb469ab9154629a47a
ms.sourcegitcommit: f605e4e27fed88aca286f2ae236e27f9a396b517
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474917"
---
# <a name="get-started-with-progressive-web-apps-chromium"></a><span data-ttu-id="06726-104">プログレッシブ Web アプリ (Chromium) の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="06726-104">Get started with Progressive Web Apps (Chromium)</span></span>  

<span data-ttu-id="06726-105">プログレッシブ Web アプリ \(PWAs\) は、段階的に拡張される [Web アプリです][WikiProgressiveEnhancement]。</span><span class="sxs-lookup"><span data-stu-id="06726-105">Progressive Web Apps \(PWAs\) are web apps that are [progressively enhanced][WikiProgressiveEnhancement].</span></span>  <span data-ttu-id="06726-106">プログレッシブ機能拡張には、インストール、オフライン サポート、プッシュ通知などのアプリのような機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="06726-106">The progressive enhancements include app-like features, such as installation, offline support, and push notifications.</span></span>  <span data-ttu-id="06726-107">PWA をアプリ ストア用にパッケージ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="06726-107">You may also package your PWA for app stores.</span></span>  <span data-ttu-id="06726-108">可能なアプリ ストアには、Microsoft Store、Google Play、Mac App Store などがあります。</span><span class="sxs-lookup"><span data-stu-id="06726-108">Possible app stores include the Microsoft Store, Google Play, Mac App Store, and more.</span></span>  <span data-ttu-id="06726-109">Microsoft Store は、Windows 10 に組み込みの商用アプリ ストアです。</span><span class="sxs-lookup"><span data-stu-id="06726-109">The Microsoft Store is the commercial app store built into Windows 10.</span></span>  

<span data-ttu-id="06726-110">次のガイドでは、簡単な Web アプリを作成し、PWA として拡張することで、PWA の基本の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="06726-110">The following guide gives you an overview of PWA basics by creating a simple web app and extending it as a PWA.</span></span>  <span data-ttu-id="06726-111">完成したプロジェクトは、最新のブラウザーで動作します。</span><span class="sxs-lookup"><span data-stu-id="06726-111">The finished project works across modern browsers.</span></span>  

> [!TIP]
> <span data-ttu-id="06726-112">[PWABuilder を使用して][PwaBuilder]、新しい PWA の作成、既存の PWA の強化、またはアプリ ストア用の PWA のパッケージ化を行います。</span><span class="sxs-lookup"><span data-stu-id="06726-112">You may use [PWABuilder][PwaBuilder] to create a new PWA, enhance your existing PWA, or package your PWA for app stores.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="06726-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="06726-113">Prerequisites</span></span>  

*   <span data-ttu-id="06726-114">PWA [Visual Studioコード][VisualstudioCodeMain] を編集するには、[コード] を使用します。</span><span class="sxs-lookup"><span data-stu-id="06726-114">Use [Visual Studio Code][VisualstudioCodeMain] to edit your PWA source code.</span></span>  
*   <span data-ttu-id="06726-115">ローカル [Node.js][NodejsMain] サーバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="06726-115">Use [Node.js][NodejsMain] as your local web server.</span></span>  
    
## <a name="create-a-basic-web-app"></a><span data-ttu-id="06726-116">基本的な Web アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="06726-116">Create a basic web app</span></span>  

<span data-ttu-id="06726-117">空の Web アプリを作成するには [、「Node Express App Generator」][ExpressjsApplicationGenerator]の手順に従い、アプリの名前を指定します `MySamplePwa` 。</span><span class="sxs-lookup"><span data-stu-id="06726-117">To create an empty web app, follow the steps in [Node Express App Generator][ExpressjsApplicationGenerator], and name your app `MySamplePwa`.</span></span>  

<span data-ttu-id="06726-118">プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="06726-118">In the prompt, run the following commands.</span></span>  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

<span data-ttu-id="06726-119">コマンドは空の Web アプリを作成し、依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="06726-119">The commands create an empty web app and install any dependencies.</span></span>  

<span data-ttu-id="06726-120">これで、シンプルで機能的な Web アプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="06726-120">You now have a simple, functional web app.</span></span>  <span data-ttu-id="06726-121">Web アプリを起動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="06726-121">To start your web app, run the following command.</span></span>  

```shell
npm start
```  

<span data-ttu-id="06726-122">次に、新 `http://localhost:3000` しい Web アプリを参照して表示します。</span><span class="sxs-lookup"><span data-stu-id="06726-122">Now browse to `http://localhost:3000` to view your new web app.</span></span>  

:::image type="complex" source="./media/visual-studio-nodejs-express-index.png" alt-text="localhost で新しい PWA を実行する" lightbox="./media/visual-studio-nodejs-express-index.png":::
   <span data-ttu-id="06726-124">localhost で新しい PWA を実行する</span><span class="sxs-lookup"><span data-stu-id="06726-124">Running your new PWA on localhost</span></span>  
:::image-end:::  

## <a name="get-started-building-a-pwa"></a><span data-ttu-id="06726-125">PWA の構築を開始する</span><span class="sxs-lookup"><span data-stu-id="06726-125">Get started building a PWA</span></span>  

<span data-ttu-id="06726-126">簡単な Web アプリが作成されたので、PWA として拡張するには、PWA の 3 つの要件を追加します。</span><span class="sxs-lookup"><span data-stu-id="06726-126">Now that you have a simple web app, extend it as a PWA by adding the three requirements for PWAs</span></span><!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]--><span data-ttu-id="06726-127">: [HTTPS](#step-1---use-https) [、Web アプリ マニフェスト、](#step-2---create-a-web-app-manifest)および [サービス ワーカー](#step-3---add-a-service-worker)。</span><span class="sxs-lookup"><span data-stu-id="06726-127">: [HTTPS](#step-1---use-https), a [Web App Manifest](#step-2---create-a-web-app-manifest), and a [Service Worker](#step-3---add-a-service-worker).</span></span>  

### <a name="step-1---use-https"></a><span data-ttu-id="06726-128">手順 1 - HTTPS を使用する</span><span class="sxs-lookup"><span data-stu-id="06726-128">Step 1 - Use HTTPS</span></span>  

<span data-ttu-id="06726-129">PWA プラットフォームの主要な部分 [(Service Workers][MDNServiceWorkerApi]など) では、HTTPS の使用が必要です。</span><span class="sxs-lookup"><span data-stu-id="06726-129">Key parts of the PWA platform, such as [Service Workers][MDNServiceWorkerApi], require the use of HTTPS.</span></span>  <span data-ttu-id="06726-130">PWA が公開された場合は、HTTPS URL に発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06726-130">When your PWA goes live, you must publish it to an HTTPS URL.</span></span>  

<span data-ttu-id="06726-131">デバッグの目的で、Microsoft Edge では `http://localhost` PWA API の使用も許可されています。</span><span class="sxs-lookup"><span data-stu-id="06726-131">For debugging purposes, Microsoft Edge also permits `http://localhost` to use the PWA APIs.</span></span>  

<span data-ttu-id="06726-132">[Web アプリをライブ サイトとして公開します][VisualStudioNodejsTutorialPublishAzureAppService]が、サーバーが HTTPS 用に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="06726-132">[Publish your web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService], but ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="06726-133">たとえば、Azure 無料アカウント [を作成できます][AzureCreateFreeAccount]。</span><span class="sxs-lookup"><span data-stu-id="06726-133">For example, you may create an [Azure free account][AzureCreateFreeAccount].</span></span>  <span data-ttu-id="06726-134">Microsoft Azure App Service で [サイトをホスト][AzureWebApps] すると、既定で HTTPS 経由で提供されます。</span><span class="sxs-lookup"><span data-stu-id="06726-134">Host your site on the [Microsoft Azure App Service][AzureWebApps] and it is served over HTTPS by default.</span></span>  

<span data-ttu-id="06726-135">次のガイドでは `http://localhost` 、PWA をビルドするために使用します。</span><span class="sxs-lookup"><span data-stu-id="06726-135">The following guide, use `http://localhost` to build your PWA.</span></span>  

### <a name="step-2---create-a-web-app-manifest"></a><span data-ttu-id="06726-136">手順 2 - Web アプリ マニフェストを作成する</span><span class="sxs-lookup"><span data-stu-id="06726-136">Step 2 - Create a Web App Manifest</span></span>  

<span data-ttu-id="06726-137">[Web アプリ マニフェストは][MDNWebAppManifest]、名前、説明、アイコンなど、アプリに関するメタデータを含む JSON ファイルです。</span><span class="sxs-lookup"><span data-stu-id="06726-137">A [Web App Manifest][MDNWebAppManifest] is a JSON file containing metadata about your app, such as name, description, icons, and more.</span></span>  

<span data-ttu-id="06726-138">アプリ マニフェストを Web アプリに追加するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="06726-138">To add an app manifest to the web app:</span></span>  

1.  <span data-ttu-id="06726-139">[Visual Studio] で、[**ファイル**を開くフォルダー]  >  **を**選択し、前に作成 `MySamplePwa` したディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="06726-139">In Visual Studio Code, choose **File** > **Open Folder** and choose the `MySamplePwa` directory you created earlier.</span></span>  
1.  <span data-ttu-id="06726-140">選択 `Ctrl` + `N` して新しいファイルを作成し、次のコード スニペットに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="06726-140">Select `Ctrl`+`N` to create a new file, and paste in the following code snippet.</span></span>  
    
    ```json
    {
        "lang": "en-us",
        "name": "My Sample PWA",
        "short_name": "SamplePWA",
        "description": "A sample PWA for testing purposes",
        "start_url": "/",
        "background_color": "#2f3d58",
        "theme_color": "#2f3d58",        
        "orientation": "any",
        "display": "standalone",
        "icons": [
            {
                "src": "/icon512.png",
                "sizes": "512x512"
            }
        ]
    }
    ```  
    
1.  <span data-ttu-id="06726-141">ファイルをとして保存します `/MySamplePwa/public/manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="06726-141">Save the file as `/MySamplePwa/public/manifest.json`.</span></span>  
1.  <span data-ttu-id="06726-142">にという名前の 512x512 アプリ アイコン イメージを追加 `icon512.png` します `/MySamplePwa/public/images` 。</span><span class="sxs-lookup"><span data-stu-id="06726-142">Add a 512x512 app icon image named `icon512.png` to `/MySamplePwa/public/images`.</span></span>  <span data-ttu-id="06726-143">サンプル イメージは、 [テストの目的](./media/progressive-web-app.png) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="06726-143">You may use the [sample image](./media/progressive-web-app.png) for testing purposes.</span></span>  
1.  <span data-ttu-id="06726-144">[コードVisual Studio開き `/public/index.html` 、タグ内に次のコード スニペットを追加 `<head>` します。</span><span class="sxs-lookup"><span data-stu-id="06726-144">In Visual Studio Code, open `/public/index.html`, and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### <a name="step-3---add-a-service-worker"></a><span data-ttu-id="06726-145">手順 3 - サービス ワーカーを追加する</span><span class="sxs-lookup"><span data-stu-id="06726-145">Step 3 - Add a Service Worker</span></span>  

<span data-ttu-id="06726-146">サービス ワーカーは、PWA の主要なテクノロジであり、オフライン サポート、高度なキャッシュ、以前はネイティブ アプリに限定されたバックグラウンド タスクの実行など、シナリオを可能にします。</span><span class="sxs-lookup"><span data-stu-id="06726-146">Service workers are the key technology behind PWAs, enabling scenarios like offline support, advanced caching, and running background tasks previously limited to native apps.</span></span>  

<span data-ttu-id="06726-147">サービス ワーカーは、Web アプリからネットワーク要求を傍受するバックグラウンド タスクです。</span><span class="sxs-lookup"><span data-stu-id="06726-147">Service workers are background tasks that intercept network requests from your web app.</span></span>  <span data-ttu-id="06726-148">サービス ワーカーは、PWA が実行されていない場合でもタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="06726-148">Service workers attempt to complete tasks, even when your PWA is not running.</span></span>  <span data-ttu-id="06726-149">タスクには、次のアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="06726-149">Tasks include the following actions.</span></span>  

*   <span data-ttu-id="06726-150">キャッシュから要求されたリソースを提供する</span><span class="sxs-lookup"><span data-stu-id="06726-150">Serving requested resources from a cache</span></span>  
*   <span data-ttu-id="06726-151">プッシュ通知の送信</span><span class="sxs-lookup"><span data-stu-id="06726-151">Sending push notifications</span></span>  
*   <span data-ttu-id="06726-152">バックグラウンド フェッチ タスクの実行</span><span class="sxs-lookup"><span data-stu-id="06726-152">Running background fetch tasks</span></span>  
*   <span data-ttu-id="06726-153">バッド アイコン</span><span class="sxs-lookup"><span data-stu-id="06726-153">Badging icons</span></span>  
*   <span data-ttu-id="06726-154">およびその他</span><span class="sxs-lookup"><span data-stu-id="06726-154">and more</span></span>  
    
<span data-ttu-id="06726-155">サービス ワーカーは特別な JavaScript ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="06726-155">Service workers are defined in a special JavaScript file.</span></span>  <span data-ttu-id="06726-156">詳細については、「サービス ワーカーとサービス ワーカー API[の使用][MDNUsingServiceWorkers][」に移動します][MDNServiceWorkerApi]。</span><span class="sxs-lookup"><span data-stu-id="06726-156">For more information, navigate to [Using Service Workers][MDNUsingServiceWorkers] and [Service Worker API][MDNServiceWorkerApi].</span></span>  

<span data-ttu-id="06726-157">プロジェクトでサービス ワーカーを構築するには、PWA Builder の **キャッシュファースト ネットワーク** サービス ワーカー レシピ [を使用します][PwaBuilderServiceWorker]。</span><span class="sxs-lookup"><span data-stu-id="06726-157">To build a service worker in your project, use the **Cache-first network** service worker recipe from [PWA Builder][PwaBuilderServiceWorker].</span></span>  

1.  <span data-ttu-id="06726-158">[キャッシュ] [pwabuilder.com/serviceworker、][PwaBuilderServiceWorker]キャッシュ ファースト ネットワーク サービス ワーカーを **選択** し、[ダウンロード] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="06726-158">Navigate to [pwabuilder.com/serviceworker][PwaBuilderServiceWorker], select the **Cache-first network** service worker, and select the **Download** button.</span></span>  <span data-ttu-id="06726-159">ダウンロードしたファイルには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="06726-159">The downloaded file contains the following files:</span></span>
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
        
1.  <span data-ttu-id="06726-160">ダウンロードしたファイルを Web アプリ `public` プロジェクトのフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="06726-160">Copy the downloaded files to the `public` folder in your web app project.</span></span>  
1.  <span data-ttu-id="06726-161">[Visual Studioコード] で、次のコード スニペットを開 `/public/index.html` いてタグ内に追加 `<head>` します。</span><span class="sxs-lookup"><span data-stu-id="06726-161">In Visual Studio Code, open `/public/index.html` and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
<span data-ttu-id="06726-162">これで、キャッシュファースト戦略を使用するサービス ワーカーが Web アプリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="06726-162">Your web app now has a service worker that uses the cache-first strategy.</span></span>  <span data-ttu-id="06726-163">新しいサービス ワーカーは、最初にキャッシュから、必要に応じてネットワークからリソースをフェッチします。</span><span class="sxs-lookup"><span data-stu-id="06726-163">You new service worker fetches resources from the cache first, and from the network only as needed.</span></span>  <span data-ttu-id="06726-164">キャッシュされたリソースには、イメージ、JavaScript、CSS、HTML が含まれます。</span><span class="sxs-lookup"><span data-stu-id="06726-164">Cached resources include images, JavaScript, CSS, and HTML.</span></span>

<span data-ttu-id="06726-165">サービス ワーカーが実行されるのを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="06726-165">Use the following steps to confirm that your service worker runs.</span></span>  

1.  <span data-ttu-id="06726-166">を使用して Web アプリに移動します `http://localhost:3000` 。</span><span class="sxs-lookup"><span data-stu-id="06726-166">Navigate to your web app using `http://localhost:3000`.</span></span>  <span data-ttu-id="06726-167">Web アプリが使用できない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="06726-167">If your web app is not available, run the following command.</span></span>   
    
    ```shell
    npm start
    ```
    
1.  <span data-ttu-id="06726-168">Microsoft Edge で、Microsoft Edge `F12` DevTools を開く場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="06726-168">In Microsoft Edge, select `F12` to open the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="06726-169">[ **アプリケーション]** を選択し **、[サービス ワーカー] を選択** してサービス ワーカーを表示します。</span><span class="sxs-lookup"><span data-stu-id="06726-169">Select **Application**, then **Service Workers** to view the service workers.</span></span>  <span data-ttu-id="06726-170">サービス ワーカーが表示されない場合は、ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="06726-170">If the service worker is not displayed, refresh the page.</span></span>  
    
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools Service Worker の概要" lightbox="./media/devtools-sw-overview.png":::
       <span data-ttu-id="06726-172">Microsoft Edge DevTools Service Worker の概要</span><span class="sxs-lookup"><span data-stu-id="06726-172">Microsoft Edge DevTools Service Worker overview</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="06726-173">[キャッシュ ストレージ] を展開してサービス ワーカー キャッシュを **表示** し **、[pwabuilder-precache] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="06726-173">View the service worker cache by expanding **Cache Storage** and select **pwabuilder-precache**.</span></span>  <span data-ttu-id="06726-174">サービス ワーカーによってキャッシュされたリソースはすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="06726-174">All of the resources cached by the service worker should be displayed.</span></span>  <span data-ttu-id="06726-175">サービス ワーカーによってキャッシュされるリソースには、アプリ アイコン、アプリ マニフェスト、CSS、および JavaScript ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="06726-175">The resources cached by the service worker include the app icon, app manifest, CSS, and JavaScript files.</span></span>  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools のサービス ワーカー キャッシュ" lightbox="./media/devtools-cache.png":::
       <span data-ttu-id="06726-177">Microsoft Edge DevTools \(F12\) のサービス ワーカー キャッシュ</span><span class="sxs-lookup"><span data-stu-id="06726-177">Service Worker cache in Microsoft Edge DevTools \(F12\)</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="06726-178">オフライン アプリとして PWA を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="06726-178">Try your PWA as an offline app.</span></span>  <span data-ttu-id="06726-179">Microsoft Edge DevTools \( `F12` \) で、[ **ネットワーク** ] を選択し、[オンライン] 状態 **を [オフライン** ] に **変更します**。</span><span class="sxs-lookup"><span data-stu-id="06726-179">In Microsoft Edge DevTools \(`F12`\), choose **Network** then change the **Online** status to **Offline**.</span></span>  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="Microsoft Edge DevTools でアプリをオフライン モードに設定する" lightbox="./media/devtools-offline.png":::
       <span data-ttu-id="06726-181">Microsoft Edge DevTools でアプリをオフライン モードに設定する</span><span class="sxs-lookup"><span data-stu-id="06726-181">Setting app to offline mode in Microsoft Edge DevTools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="06726-182">アプリを更新すると、キャッシュからアプリのリソースを提供するためのオフライン メカニズムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06726-182">Refresh your app and it should display the offline mechanism for serving the resources of your app from the cache.</span></span>  
    
    :::image type="complex" source="./media/visual-studio-nodejs-express-index.png" alt-text="オフラインで実行されている PWA" lightbox="./media/visual-studio-nodejs-express-index.png":::
       <span data-ttu-id="06726-184">オフラインで実行されている PWA</span><span class="sxs-lookup"><span data-stu-id="06726-184">PWA running offline</span></span>  
    :::image-end:::  
    
## <a name="add-push-notifications-to-your-pwa"></a><span data-ttu-id="06726-185">PWA にプッシュ通知を追加する</span><span class="sxs-lookup"><span data-stu-id="06726-185">Add push notifications to your PWA</span></span>  

<span data-ttu-id="06726-186">プッシュ通知をサポートする PWA を作成するには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="06726-186">You may create PWAs that support push notifications by completing the following tasks.</span></span>  

1.  <span data-ttu-id="06726-187">プッシュ API を使用してメッセージング サービスを [サブスクライブする][MDNPushApi]</span><span class="sxs-lookup"><span data-stu-id="06726-187">Subscribe to a messaging service using the [Push API][MDNPushApi]</span></span>  
1.  <span data-ttu-id="06726-188">通知 API を使用してサービスからメッセージを受信すると、トースト メッセージを [表示する][MDNNotificationsApi]</span><span class="sxs-lookup"><span data-stu-id="06726-188">Display a toast message when a message is received from the service using the [Notifications API][MDNNotificationsApi]</span></span>  
    
<span data-ttu-id="06726-189">Service Workers と同様に、プッシュ通知 API は標準ベースの API です。</span><span class="sxs-lookup"><span data-stu-id="06726-189">Just like with Service Workers, the push notification APIs are standards-based APIs.</span></span>  <span data-ttu-id="06726-190">プッシュ通知 API はブラウザー間で動作します。そのため、コードは、PWA がサポートされているあらゆる場所で動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06726-190">The push notification APIs work across browsers, so your code should work everywhere that PWAs are supported.</span></span>  <span data-ttu-id="06726-191">サーバー上の別のブラウザーにプッシュ メッセージを配信する方法の詳細については [、「Web-Push」に移動します][NPMWebPush]。</span><span class="sxs-lookup"><span data-stu-id="06726-191">For more information about delivering push messages to different browsers on your server, navigate to [Web-Push][NPMWebPush].</span></span>  

<span data-ttu-id="06726-192">次の手順は、Mozilla が提供する Service [Worker クック][ServiceWorkerCookbookPushRichDemo] ブックのプッシュ リッチ デモから適用されています。その他の便利な Web プッシュおよびサービス ワーカーのレシピが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="06726-192">The following steps have been adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which has a number of other useful Web Push and service worker recipes.</span></span>  

### <a name="step-1---generate-vapid-keys"></a><span data-ttu-id="06726-193">手順 1 - VAPID キーを生成する</span><span class="sxs-lookup"><span data-stu-id="06726-193">Step 1 - Generate VAPID keys</span></span>  

<span data-ttu-id="06726-194">PWA クライアントにプッシュ メッセージを送信するには、プッシュ通知に VAPID \(Voluntary Application Server IDENTIFICATION\) キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="06726-194">Push notifications require VAPID \(Voluntary Application Server Identification\) keys in order to send push messages to the PWA client.</span></span>  <span data-ttu-id="06726-195">オンラインで使用可能な VAPID キー ジェネレーターは複数あります[][VapidkeysMain](たとえば、\vapidkeys.com)。</span><span class="sxs-lookup"><span data-stu-id="06726-195">There are several VAPID key generators available online \(for example, [vapidkeys.com][VapidkeysMain]\).</span></span>  <span data-ttu-id="06726-196">生成後、公開キーとプライベート キーを含む JSON オブジェクトを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06726-196">After generation, you should get a JSON object containing a public and private key.</span></span>  <span data-ttu-id="06726-197">次のチュートリアルの後の手順のキーを保存します。</span><span class="sxs-lookup"><span data-stu-id="06726-197">Save the keys for later steps in the following tutorial.</span></span>  <span data-ttu-id="06726-198">VAPID と WebPush の詳細については、Mozilla Push Service を使用して識別された [WebPush 通知の送信に移動します][MozillaServicesSendingVapidWebPushNotificationsPush]。</span><span class="sxs-lookup"><span data-stu-id="06726-198">For information about VAPID and WebPush, navigate to [Sending VAPID identified WebPush Notifications using the Mozilla Push Service][MozillaServicesSendingVapidWebPushNotificationsPush].</span></span>  

### <a name="step-2---subscribe-to-push-notifications"></a><span data-ttu-id="06726-199">手順 2 - プッシュ通知をサブスクライブする</span><span class="sxs-lookup"><span data-stu-id="06726-199">Step 2 - Subscribe to push notifications</span></span>  

<span data-ttu-id="06726-200">サービス ワーカーは、PWA でプッシュ イベントとトースト通知のやり取りを処理します。</span><span class="sxs-lookup"><span data-stu-id="06726-200">Service workers handle push events and toast notification interactions in your PWA.</span></span>  <span data-ttu-id="06726-201">PWA をサーバープッシュ通知にサブスクライブするには、次の条件を満たしてください。</span><span class="sxs-lookup"><span data-stu-id="06726-201">To subscribe the PWA to server push notifications, ensure the following conditions are met.</span></span>  

*   <span data-ttu-id="06726-202">PWA がインストール、アクティブ、および登録されている</span><span class="sxs-lookup"><span data-stu-id="06726-202">Your PWA is installed, active, and registered</span></span>  
*   <span data-ttu-id="06726-203">サブスクリプション タスクを完了するコードは、PWA のメイン UI スレッド上にある</span><span class="sxs-lookup"><span data-stu-id="06726-203">Your code to complete the subscription task is on the main UI thread of the PWA</span></span>  
*   <span data-ttu-id="06726-204">ネットワーク接続がある</span><span class="sxs-lookup"><span data-stu-id="06726-204">You have network connectivity</span></span>  
    
<span data-ttu-id="06726-205">新しいプッシュ サブスクリプションを作成する前に、Microsoft Edge は、ユーザーが PWA に通知を受信するアクセス許可を与えたか確認します。</span><span class="sxs-lookup"><span data-stu-id="06726-205">Before a new push subscription is created, Microsoft Edge verifies if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="06726-206">表示されない場合は、ブラウザーからアクセス許可を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06726-206">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="06726-207">アクセス許可が拒否された場合、処理する必要 `registration.pushManager.subscribe` がある `DOMException` 、 をスローする要求。</span><span class="sxs-lookup"><span data-stu-id="06726-207">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, which must be handled.</span></span>  <span data-ttu-id="06726-208">アクセス許可の管理の詳細については [、Microsoft Edge の [プッシュ通知] に移動します][WindowsBlogsWebNotificationsEdge]。</span><span class="sxs-lookup"><span data-stu-id="06726-208">For more on permission management, navigate to [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="06726-209">ファイルで `pwabuilder-sw-register.js` 、次のコード スニペットを追加します。</span><span class="sxs-lookup"><span data-stu-id="06726-209">In your `pwabuilder-sw-register.js` file, append the following code snippet.</span></span>  

```javascript
// Ask the user for permission to send push notifications.
navigator.serviceWorker.ready
    .then(function (registration) {
        // Check if the user has an existing subscription
        return registration.pushManager.getSubscription()
            .then(function (subscription) {
                if (subscription) {
                    return subscription;
                }
                
                const vapidPublicKey = "PASTE YOUR PUBLIC VAPID KEY HERE";             
                return registration.pushManager.subscribe({
                    userVisibleOnly: true,
                    applicationServerKey: urlBase64ToUint8Array(vapidPublicKey)
                });
            });
    });

// Utility function for browser interoperability
function urlBase64ToUint8Array(base64String) {
    var padding = '='.repeat((4 - base64String.length % 4) % 4);
    var base64 = (base64String + padding)
        .replace(/\-/g, '+')
        .replace(/_/g, '/');
        
    var rawData = window.atob(base64);
    var outputArray = new Uint8Array(rawData.length);
    
    for (var i = 0; i < rawData.length; ++i) {
        outputArray[i] = rawData.charCodeAt(i);
    }
    return outputArray;
}
```  

<span data-ttu-id="06726-210">詳細については [、「PushManager」][MDNPushManager] および [「Web-Push」に移動します][NPMWebPushUsage]。</span><span class="sxs-lookup"><span data-stu-id="06726-210">For more information, navigate to [PushManager][MDNPushManager] and [Web-Push][NPMWebPushUsage].</span></span>  

### <a name="step-3---listen-for-push-notifications"></a><span data-ttu-id="06726-211">手順 3 - プッシュ通知をリッスンする</span><span class="sxs-lookup"><span data-stu-id="06726-211">Step 3 - Listen for push notifications</span></span>  

<span data-ttu-id="06726-212">PWA でサブスクリプションを作成したら、プッシュ イベントに応答するハンドラーをサービス ワーカーに追加します。</span><span class="sxs-lookup"><span data-stu-id="06726-212">After a subscription is created in your PWA, add handlers to the service worker to respond to push events.</span></span>  <span data-ttu-id="06726-213">プッシュ イベントは、トースト通知を表示するためにサーバーから送信されます。</span><span class="sxs-lookup"><span data-stu-id="06726-213">Push event are sent from the server to display toast notifications.</span></span>  <span data-ttu-id="06726-214">トースト通知には、受信したメッセージのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06726-214">Toast notifications display data for a received message.</span></span>  <span data-ttu-id="06726-215">次のタスクを完了するには、ハンドラーを追加する必要 `click` があります。</span><span class="sxs-lookup"><span data-stu-id="06726-215">To complete the following tasks, you must add a `click` handler.</span></span>  

*   <span data-ttu-id="06726-216">トースト通知を閉じる</span><span class="sxs-lookup"><span data-stu-id="06726-216">Dismiss the toast notification</span></span>  
*   <span data-ttu-id="06726-217">開いているウィンドウを開く、フォーカスする、または開く、フォーカスする</span><span class="sxs-lookup"><span data-stu-id="06726-217">Open, focus, or open and focus any open windows</span></span>  
*   <span data-ttu-id="06726-218">PWA クライアント ページを表示する新しいウィンドウを開いてフォーカスする</span><span class="sxs-lookup"><span data-stu-id="06726-218">Open and focus a new window to display a PWA client page</span></span>  
    
<span data-ttu-id="06726-219">ファイルに `pwabuilder-sw.js` 、次のハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="06726-219">In your `pwabuilder-sw.js` file, add the following handlers.</span></span>  

```javascript
// Respond to a server push with a user notification.
self.addEventListener('push', function (event) {
    if (Notification.permission === "granted") {
        const notificationText = event.data.text();
        const showNotification = self.registration.showNotification('Sample PWA', {
            body: notificationText,
            icon: 'images/icon512.png'
        });
        // Ensure the toast notification is displayed before exiting the function.
        event.waitUntil(showNotification);
    }
});

// Respond to the user selecting the toast notification.
self.addEventListener('notificationclick', function (event) {
    console.log('On notification click: ', event.notification.tag);
    event.notification.close();
    
    // This attempts to display the current notification if it is already open and then focuses on it.
    event.waitUntil(clients.matchAll({
        type: 'window'
    }).then(function (clientList) {
        for (var i = 0; i < clientList.length; i++) {
            var client = clientList[i];
            if (client.url == 'http://localhost:1337/' && 'focus' in client)
                return client.focus();
        }
        if (clients.openWindow)
            return clients.openWindow('/');
    }));
});
```  

### <a name="step-4---try-it-out"></a><span data-ttu-id="06726-220">手順 4 - 試してみる</span><span class="sxs-lookup"><span data-stu-id="06726-220">Step 4 - Try it out</span></span>  

<span data-ttu-id="06726-221">PWA のプッシュ通知をテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="06726-221">To test push notifications for your PWA, complete the following steps.</span></span>  

1.  <span data-ttu-id="06726-222">PWA に移動します `http://localhost:3000` 。</span><span class="sxs-lookup"><span data-stu-id="06726-222">Navigate to your PWA at `http://localhost:3000`.</span></span>  <span data-ttu-id="06726-223">サービス ワーカーが PWA をアクティブ化してプッシュ通知にサブスクライブしようとすると、PWA に通知の表示を許可するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06726-223">When your service worker activates and attempts to subscribe your PWA to push notifications, Microsoft Edge prompts you to allow your PWA to show notifications.</span></span>  <span data-ttu-id="06726-224">[許可 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="06726-224">Select **Allow**.</span></span>  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="通知を有効にするアクセス許可ダイアログ" lightbox="./media/notification-permission.png":::
       <span data-ttu-id="06726-226">通知を有効にするアクセス許可ダイアログ</span><span class="sxs-lookup"><span data-stu-id="06726-226">Permission dialog for enabling notifications</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="06726-227">サーバー側のプッシュ通知をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="06726-227">Simulate a server-side push notification.</span></span>  <span data-ttu-id="06726-228">ブラウザーで PWA を開 `http://localhost:3000` いた後、選択 `F12` して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="06726-228">With your PWA opened at `http://localhost:3000` in your browser, select `F12` to open the DevTools.</span></span>  <span data-ttu-id="06726-229">[**アプリケーション**  >  **サービス ワーカー プッシュ]**  >  **を選択**して、PWA にテスト プッシュ通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="06726-229">Choose **Application** > **Service Worker** > **Push** to send a test push notification to your PWA.</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="06726-230">プッシュ通知がタスク バーの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="06726-230">A push notification should display near the taskbar.</span></span>  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="DevTools から通知をプッシュする" lightbox="./media/devtools-push.png":::
             <span data-ttu-id="06726-232">DevTools から通知をプッシュする</span><span class="sxs-lookup"><span data-stu-id="06726-232">Push a notification from DevTools</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="06726-233">トースト通知を \(または activate\) を選択しない場合、システムは数秒後に自動的に通知を却下し、Windows アクション センターにキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="06726-233">If you do not select \(or activate\) a toast notification, the system automatically dismisses it after several seconds and queues it in your Windows Action Center.</span></span>  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows アクション センターの通知" lightbox="./media/windows-action-center.png":::
             <span data-ttu-id="06726-235">Windows アクション センターの通知</span><span class="sxs-lookup"><span data-stu-id="06726-235">Notifications in Windows Action Center</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="06726-236">次の手順</span><span class="sxs-lookup"><span data-stu-id="06726-236">Next steps</span></span>  

<span data-ttu-id="06726-237">次の手順には、実際の PWA の構築を理解するのに役立つ追加のタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="06726-237">The following steps include additional tasks to help you understand building real-world PWAs.</span></span>  

*   <span data-ttu-id="06726-238">プッシュ サブスクリプションの管理と保存</span><span class="sxs-lookup"><span data-stu-id="06726-238">Manage and store push subscriptions</span></span>  
*   <span data-ttu-id="06726-239">[ペイロード データ][NPMWebPushEncrypt] の暗号化</span><span class="sxs-lookup"><span data-stu-id="06726-239">[Encrypt][NPMWebPushEncrypt] payload data</span></span>  
*   <span data-ttu-id="06726-240">レスポンシブ デザイン</span><span class="sxs-lookup"><span data-stu-id="06726-240">Responsive design</span></span>  
*   <span data-ttu-id="06726-241">ディープリンク</span><span class="sxs-lookup"><span data-stu-id="06726-241">Deep-linking</span></span>  
*   [<span data-ttu-id="06726-242">ブラウザー間のテスト</span><span class="sxs-lookup"><span data-stu-id="06726-242">Cross-browser testing</span></span>][BrowserStackTestEdgeBrowser]  
*   <span data-ttu-id="06726-243">Webhint などの検証と [テストのプラクティスを実装する][Webhint]</span><span class="sxs-lookup"><span data-stu-id="06726-243">Implement validation and testing practices such as [Webhint][Webhint]</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="06726-244">関連項目</span><span class="sxs-lookup"><span data-stu-id="06726-244">See also</span></span>  

*   [<span data-ttu-id="06726-245">MDN Web ドキュメントのプログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="06726-245">Progressive Web Apps on MDN web docs</span></span>][MDNProgressiveWebApps]  
*   [<span data-ttu-id="06726-246">プログレッシブ Web Apps on web.dev</span><span class="sxs-lookup"><span data-stu-id="06726-246">Progressive Web Apps on web.dev</span></span>][WebDevProgressiveWebApps]  
*   <span data-ttu-id="06726-247">[プログレッシブ Web アプリとしてのハッカー][HackerNewsProgressiveWebApps] ニュース リーダー - サンプル \(Hacker News reader\) PWA を実装するためのさまざまなフレームワークとパフォーマンス パターンを比較します。</span><span class="sxs-lookup"><span data-stu-id="06726-247">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  
*   [<span data-ttu-id="06726-248">ミス バトリング PWA</span><span class="sxs-lookup"><span data-stu-id="06726-248">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="06726-249">プログレッシブ Web アプリのプログレッシブ ロードマップ</span><span class="sxs-lookup"><span data-stu-id="06726-249">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="06726-250">プログレッシブ Web アプリを使用したオフライン POST</span><span class="sxs-lookup"><span data-stu-id="06726-250">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="06726-251">PWA Q&A</span><span class="sxs-lookup"><span data-stu-id="06726-251">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="06726-252">Web でのベット</span><span class="sxs-lookup"><span data-stu-id="06726-252">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="06726-253">プログレッシブ Web アプリの名前付け</span><span class="sxs-lookup"><span data-stu-id="06726-253">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="06726-254">フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 1)</span><span class="sxs-lookup"><span data-stu-id="06726-254">Designing And Building A Progressive Web Application Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [<span data-ttu-id="06726-255">フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 2)</span><span class="sxs-lookup"><span data-stu-id="06726-255">Designing And Building A Progressive Web Application Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [<span data-ttu-id="06726-256">フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 3)</span><span class="sxs-lookup"><span data-stu-id="06726-256">Designing And Building A Progressive Web Application Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "コード コード Node.jsを使用して Azure にアプリをVisual Studioする|Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントを作成|Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web Apps |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge の Web 通知 |Windows ブログ"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio Code"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA Q&A"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 サーバーでの Microsoft Edge ブラウザーの無料|BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "プログレッシブ Web アプリのプログレッシブ ロードマップ"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "ミス バスターリング PWA – 新しいエッジ エディション"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "Express アプリケーション ジェネレーター |Express" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "プログレッシブ Web アプリの名前付け"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "プログレッシブ Web アプリとしてのハッカー ニュース リーダー"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web でのベット"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "プログレッシブ Web アプリ \(PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービス ワーカー の使用|MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "プログレッシブ Web アプリを使用したオフライン POST"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "VAPID を送信すると、Mozilla のプッシュ サービス サービス経由で WebPush 通知が識別|Mozilla Services"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-push |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt(userPublicKey, userAuth, payload, contentEncoding) - web プッシュ |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用法 - Web プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "プログレッシブ Web アプリ"  

[PwaBuilder]: https://www.pwabuilder.com "PWA ビルダー"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "Service Worker |PWA ビルダー"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "Push Rich Demo |ServiceWorker クックブック"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 1)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 2)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 3)"  

[VapidkeysMain]: https://vapidkeys.com "Secure VAPID Key Generator |VapidKeys" 

[Webhint]: https://webhint.io "webhint"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "プログレッシブ Web アプリ |web.dev"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "プログレッシブ拡張|Wikipedia"  
