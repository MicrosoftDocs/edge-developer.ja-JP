---
description: このガイドでは、Windows で段階的な Web アプリ (Chromium) を構築するための PWA の基本とツールの概要について説明します。
title: プログレッシブ Web アプリ (Chromium) の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 段階的な Web アプリ, PWA, Edge, Windows, PWABuilder, Web マニフェスト, サービス ワーカー, プッシュ
ms.openlocfilehash: 7ad13f98f54c52891681d7591b21503c9d5825ff
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231224"
---
# <span data-ttu-id="f5971-104">プログレッシブ Web アプリ (Chromium) の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="f5971-104">Get started with Progressive Web Apps (Chromium)</span></span>  

<span data-ttu-id="f5971-105">段階的な Web アプリ \(PWAs\) は、徐々に [拡張された Web アプリです][WikiProgressiveEnhancement]。</span><span class="sxs-lookup"><span data-stu-id="f5971-105">Progressive Web Apps \(PWAs\) are web apps that are [progressively enhanced][WikiProgressiveEnhancement].</span></span>  <span data-ttu-id="f5971-106">段階的な機能強化には、インストール、オフライン サポート、プッシュ通知など、アプリのような機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5971-106">The progressive enhancements include app-like features, such as installation, offline support, and push notifications.</span></span>  <span data-ttu-id="f5971-107">PWA をアプリ ストア用にパッケージ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5971-107">You may also package your PWA for app stores.</span></span>  <span data-ttu-id="f5971-108">可能なアプリ ストアには、Microsoft Store、Google Play、Mac App Store などです。</span><span class="sxs-lookup"><span data-stu-id="f5971-108">Possible app stores include the Microsoft Store, Google Play, Mac App Store, and more.</span></span>  <span data-ttu-id="f5971-109">Microsoft Store は、Windows 10 に組み込みの商用アプリ ストアです。</span><span class="sxs-lookup"><span data-stu-id="f5971-109">The Microsoft Store is the commercial app store built into Windows 10.</span></span>  

<span data-ttu-id="f5971-110">次のガイドでは、簡単な Web アプリを作成し、PWA として拡張することで、PWA の基本の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="f5971-110">The following guide gives you an overview of PWA basics by creating a simple web app and extending it as a PWA.</span></span>  <span data-ttu-id="f5971-111">完成したプロジェクトは、最新のブラウザー間で動作します。</span><span class="sxs-lookup"><span data-stu-id="f5971-111">The finished project works across modern browsers.</span></span>  

> [!TIP]
> <span data-ttu-id="f5971-112">[PWABuilder を使用して][PwaBuilder]、新しい PWA を作成したり、既存の PWA を拡張したり、アプリ ストア用に PWA をパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="f5971-112">You may use [PWABuilder][PwaBuilder] to create a new PWA, enhance your existing PWA, or package your PWA for app stores.</span></span>  

## <span data-ttu-id="f5971-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="f5971-113">Prerequisites</span></span>  

*   <span data-ttu-id="f5971-114">コード [Visual Studio使用][VisualstudioCodeMain] して、PWA ソース コードを編集します。</span><span class="sxs-lookup"><span data-stu-id="f5971-114">Use [Visual Studio Code][VisualstudioCodeMain] to edit your PWA source code.</span></span>  
*   <span data-ttu-id="f5971-115">ローカル [Node.js][NodejsMain] Web サーバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="f5971-115">Use [Node.js][NodejsMain] as your local web server.</span></span>  
    
## <span data-ttu-id="f5971-116">基本的な Web アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f5971-116">Create a basic web app</span></span>  

<span data-ttu-id="f5971-117">空の Web アプリを作成するには [、「Node Express App Generator」][ExpressjsApplicationGenerator]の手順に従って、アプリに名前を付します `MySamplePwa` 。</span><span class="sxs-lookup"><span data-stu-id="f5971-117">To create an empty web app, follow the steps in [Node Express App Generator][ExpressjsApplicationGenerator], and name your app `MySamplePwa`.</span></span>  

<span data-ttu-id="f5971-118">プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5971-118">In the prompt, run the following commands.</span></span>  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

<span data-ttu-id="f5971-119">コマンドは空の Web アプリを作成し、依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f5971-119">The commands create an empty web app and install any dependencies.</span></span>  

<span data-ttu-id="f5971-120">これで、シンプルで機能的な Web アプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f5971-120">You now have a simple, functional web app.</span></span>  <span data-ttu-id="f5971-121">Web アプリを起動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5971-121">To start your web app, run the following command.</span></span>  

```shell
npm start
```  

<span data-ttu-id="f5971-122">次に、新 `http://localhost:3000` しい Web アプリを参照して表示します。</span><span class="sxs-lookup"><span data-stu-id="f5971-122">Now browse to `http://localhost:3000` to view your new web app.</span></span>  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="localhost での新しい PWA の実行" lightbox="./media/vs-nodejs-express-index.png":::
   <span data-ttu-id="f5971-124">localhost での新しい PWA の実行</span><span class="sxs-lookup"><span data-stu-id="f5971-124">Running your new PWA on localhost</span></span>
:::image-end:::

## <span data-ttu-id="f5971-125">PWA の構築を開始する</span><span class="sxs-lookup"><span data-stu-id="f5971-125">Get started building a PWA</span></span>  

<span data-ttu-id="f5971-126">簡単な Web アプリが作成されたので、PWA として PWA として拡張するには、PWA の 3 つの要件を追加します。</span><span class="sxs-lookup"><span data-stu-id="f5971-126">Now that you have a simple web app, extend it as a PWA by adding the three requirements for PWAs</span></span><!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]--><span data-ttu-id="f5971-127">: [HTTPS、Web](#step-1---use-https)[アプリ マニフェスト、](#step-2---create-a-web-app-manifest)および[サービス ワーカー](#step-3---add-a-service-worker)。</span><span class="sxs-lookup"><span data-stu-id="f5971-127">: [HTTPS](#step-1---use-https), a [Web App Manifest](#step-2---create-a-web-app-manifest), and a [Service Worker](#step-3---add-a-service-worker).</span></span>  

### <span data-ttu-id="f5971-128">手順 1 - HTTPS を使用する</span><span class="sxs-lookup"><span data-stu-id="f5971-128">Step 1 - Use HTTPS</span></span>  

<span data-ttu-id="f5971-129">サービス ワーカーなど、PWA プラットフォームの主要な部分 [では][MDNServiceWorkerApi]HTTPS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5971-129">Key parts of the PWA platform, such as [Service Workers][MDNServiceWorkerApi], require the use of HTTPS.</span></span>  <span data-ttu-id="f5971-130">PWA が有効な場合は、HTTPS URL に発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5971-130">When your PWA goes live, you must publish it to an HTTPS URL.</span></span>  

<span data-ttu-id="f5971-131">デバッグの目的で、Microsoft Edge は PWA API の `http://localhost` 使用も許可します。</span><span class="sxs-lookup"><span data-stu-id="f5971-131">For debugging purposes, Microsoft Edge also permits `http://localhost` to use the PWA APIs.</span></span>  

<span data-ttu-id="f5971-132">[Web アプリをライブ サイトとして発行しますが][VisualStudioNodejsTutorialPublishAzureAppService]、サーバーが HTTPS 用に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5971-132">[Publish your web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService], but ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="f5971-133">たとえば、Azure 無料アカウント [を作成できます][AzureCreateFreeAccount]。</span><span class="sxs-lookup"><span data-stu-id="f5971-133">For example, you may create an [Azure free account][AzureCreateFreeAccount].</span></span>  <span data-ttu-id="f5971-134">Microsoft Azure App Service で [サイトをホスト][AzureWebApps] すると、既定で HTTPS 経由で提供されます。</span><span class="sxs-lookup"><span data-stu-id="f5971-134">Host your site on the [Microsoft Azure App Service][AzureWebApps] and it is served over HTTPS by default.</span></span>  

<span data-ttu-id="f5971-135">次のガイドでは `http://localhost` 、PWA の構築に使用します。</span><span class="sxs-lookup"><span data-stu-id="f5971-135">The following guide, use `http://localhost` to build your PWA.</span></span>  

### <span data-ttu-id="f5971-136">手順 2 - Web アプリ マニフェストを作成する</span><span class="sxs-lookup"><span data-stu-id="f5971-136">Step 2 - Create a Web App Manifest</span></span>  

<span data-ttu-id="f5971-137">[Web アプリ マニフェストは][MDNWebAppManifest]、名前、説明、アイコンなど、アプリに関するメタデータを含む JSON ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f5971-137">A [Web App Manifest][MDNWebAppManifest] is a JSON file containing metadata about your app, such as name, description, icons, and more.</span></span>  

<span data-ttu-id="f5971-138">アプリ マニフェストを Web アプリに追加するには:</span><span class="sxs-lookup"><span data-stu-id="f5971-138">To add an app manifest to the web app:</span></span>  

1.  <span data-ttu-id="f5971-139">[Visual Studioコード] で、[**ファイル**を  >  **開くフォルダー] を**選択し、前に作成 `MySamplePwa` したディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5971-139">In Visual Studio Code, choose **File** > **Open Folder** and choose the `MySamplePwa` directory you created earlier.</span></span>  
1.  <span data-ttu-id="f5971-140">新 `Ctrl` + `N` しいファイルを作成するために選択し、次のコード スニペットに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f5971-140">Select `Ctrl`+`N` to create a new file, and paste in the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="f5971-141">ファイルを次のように保存します `/MySamplePwa/public/manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="f5971-141">Save the file as `/MySamplePwa/public/manifest.json`.</span></span>  
1.  <span data-ttu-id="f5971-142">Add a 512x512 app icon image named `icon512.png` to `/MySamplePwa/public/images` .</span><span class="sxs-lookup"><span data-stu-id="f5971-142">Add a 512x512 app icon image named `icon512.png` to `/MySamplePwa/public/images`.</span></span>  <span data-ttu-id="f5971-143">サンプル イメージは、 [テスト目的][ImagePwa] で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5971-143">You may use the [sample image][ImagePwa] for testing purposes.</span></span>  
1.  <span data-ttu-id="f5971-144">コードVisual Studio開き `/public/index.html` 、タグ内に次のコード スニペットを追加 `<head>` します。</span><span class="sxs-lookup"><span data-stu-id="f5971-144">In Visual Studio Code, open `/public/index.html`, and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### <span data-ttu-id="f5971-145">手順 3 - サービス ワーカーを追加する</span><span class="sxs-lookup"><span data-stu-id="f5971-145">Step 3 - Add a Service Worker</span></span>  

<span data-ttu-id="f5971-146">サービス ワーカーは PAS の主要なテクノロジであり、オフライン サポート、高度なキャッシュ、以前はネイティブ アプリに限定されたバックグラウンド タスクの実行のようなシナリオを実現します。</span><span class="sxs-lookup"><span data-stu-id="f5971-146">Service workers are the key technology behind PWAs, enabling scenarios like offline support, advanced caching, and running background tasks previously limited to native apps.</span></span>  

<span data-ttu-id="f5971-147">サービス ワーカーは、Web アプリからのネットワーク要求を傍受するバックグラウンド タスクです。</span><span class="sxs-lookup"><span data-stu-id="f5971-147">Service workers are background tasks that intercept network requests from your web app.</span></span>  <span data-ttu-id="f5971-148">サービス ワーカーは、PWA が実行されていない場合でもタスクの完了を試みる。</span><span class="sxs-lookup"><span data-stu-id="f5971-148">Service workers attempt to complete tasks, even when your PWA is not running.</span></span>  <span data-ttu-id="f5971-149">タスクには、次のアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5971-149">Tasks include the following actions.</span></span>  

*   <span data-ttu-id="f5971-150">キャッシュから要求されたリソースの提供</span><span class="sxs-lookup"><span data-stu-id="f5971-150">Serving requested resources from a cache</span></span>  
*   <span data-ttu-id="f5971-151">プッシュ通知の送信</span><span class="sxs-lookup"><span data-stu-id="f5971-151">Sending push notifications</span></span>  
*   <span data-ttu-id="f5971-152">バックグラウンド フェッチ タスクの実行</span><span class="sxs-lookup"><span data-stu-id="f5971-152">Running background fetch tasks</span></span>  
*   <span data-ttu-id="f5971-153">バグアイコン</span><span class="sxs-lookup"><span data-stu-id="f5971-153">Badging icons</span></span>  
*   <span data-ttu-id="f5971-154">その他</span><span class="sxs-lookup"><span data-stu-id="f5971-154">and more</span></span>  
    
<span data-ttu-id="f5971-155">サービス ワーカーは、特別な JavaScript ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="f5971-155">Service workers are defined in a special JavaScript file.</span></span>  <span data-ttu-id="f5971-156">詳細については、「サービス ワーカーと [サービス][MDNUsingServiceWorkers] ワーカー API を使用する [」に移動します][MDNServiceWorkerApi]。</span><span class="sxs-lookup"><span data-stu-id="f5971-156">For more information, navigate to [Using Service Workers][MDNUsingServiceWorkers] and [Service Worker API][MDNServiceWorkerApi].</span></span>  

<span data-ttu-id="f5971-157">プロジェクトでサービス ワーカーを作成するには[、PWA Builder][PwaBuilderServiceWorker]の**キャッシュ**ファースト ネットワーク サービス ワーカー レシピを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5971-157">To build a service worker in your project, use the **Cache-first network** service worker recipe from [PWA Builder][PwaBuilderServiceWorker].</span></span>  

1.  <span data-ttu-id="f5971-158">キャッシュ に [pwabuilder.com/serviceworker、][PwaBuilderServiceWorker]キャッシュファースト ネットワーク サービス ワーカー **を** 選択して、[ダウンロード] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="f5971-158">Navigate to [pwabuilder.com/serviceworker][PwaBuilderServiceWorker], select the **Cache-first network** service worker, and select the **Download** button.</span></span>  <span data-ttu-id="f5971-159">ダウンロードしたファイルには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5971-159">The downloaded file contains the following files:</span></span>
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
        
1.  <span data-ttu-id="f5971-160">ダウンロードしたファイルを Web アプリ `public` プロジェクトのフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f5971-160">Copy the downloaded files to the `public` folder in your web app project.</span></span>  
1.  <span data-ttu-id="f5971-161">[Visual Studioコード] で、タグ `/public/index.html` 内で次のコード スニペットを開いて追加 `<head>` します。</span><span class="sxs-lookup"><span data-stu-id="f5971-161">In Visual Studio Code, open `/public/index.html` and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
<span data-ttu-id="f5971-162">これで、Web アプリに、キャッシュファースト戦略を使用するサービス ワーカーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="f5971-162">Your web app now has a service worker that uses the cache-first strategy.</span></span>  <span data-ttu-id="f5971-163">新しいサービス ワーカーは、最初にキャッシュからリソースをフェッチし、必要に応じてネットワークからのみリソースをフェッチします。</span><span class="sxs-lookup"><span data-stu-id="f5971-163">You new service worker fetches resources from the cache first, and from the network only as needed.</span></span>  <span data-ttu-id="f5971-164">キャッシュされたリソースには、画像、JavaScript、CSS、HTML が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5971-164">Cached resources include images, JavaScript, CSS, and HTML.</span></span>

<span data-ttu-id="f5971-165">次の手順を使用して、サービス ワーカーが実行されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5971-165">Use the following steps to confirm that your service worker runs.</span></span>  

1.  <span data-ttu-id="f5971-166">使用して Web アプリに移動します `http://localhost:3000` 。</span><span class="sxs-lookup"><span data-stu-id="f5971-166">Navigate to your web app using `http://localhost:3000`.</span></span>  <span data-ttu-id="f5971-167">Web アプリが使用できない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5971-167">If your web app is not available, run the following command.</span></span>   
    
    ```shell
    npm start
    ```
    
1.  <span data-ttu-id="f5971-168">Microsoft Edge で `F12` 、Microsoft Edge DevTools を開くことを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5971-168">In Microsoft Edge, select `F12` to open the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="f5971-169">[ **アプリケーション]** を選択し、[ **サービス ワーカー] を** 選択してサービス ワーカーを表示します。</span><span class="sxs-lookup"><span data-stu-id="f5971-169">Select **Application**, then **Service Workers** to view the service workers.</span></span>  <span data-ttu-id="f5971-170">サービス ワーカーが表示されない場合は、ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="f5971-170">If the service worker is not displayed, refresh the page.</span></span>  
    
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools Service Worker の概要" lightbox="./media/devtools-sw-overview.png":::
       <span data-ttu-id="f5971-172">Microsoft Edge DevTools Service Worker の概要</span><span class="sxs-lookup"><span data-stu-id="f5971-172">Microsoft Edge DevTools Service Worker overview</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="f5971-173">[キャッシュ ストレージ] を展開\*\*\*\* し **、pwabuilder-precache**を選択して、サービス ワーカー キャッシュを表示します。</span><span class="sxs-lookup"><span data-stu-id="f5971-173">View the service worker cache by expanding **Cache Storage** and select **pwabuilder-precache**.</span></span>  <span data-ttu-id="f5971-174">サービス ワーカーによってキャッシュされたリソースすべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5971-174">All of the resources cached by the service worker should be displayed.</span></span>  <span data-ttu-id="f5971-175">サービス ワーカーによってキャッシュされるリソースには、アプリ アイコン、アプリ マニフェスト、CSS、JavaScript ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5971-175">The resources cached by the service worker include the app icon, app manifest, CSS, and JavaScript files.</span></span>  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools のサービス ワーカー キャッシュ" lightbox="./media/devtools-cache.png":::
       <span data-ttu-id="f5971-177">Microsoft Edge DevTools のサービス ワーカー キャッシュ (F12)</span><span class="sxs-lookup"><span data-stu-id="f5971-177">Service Worker cache in Microsoft Edge DevTools (F12)</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="f5971-178">オフライン アプリとして PWA を試してください。</span><span class="sxs-lookup"><span data-stu-id="f5971-178">Try your PWA as an offline app.</span></span>  <span data-ttu-id="f5971-179">Microsoft Edge DevTools \( \) で、[ネットワーク] を選択し、[オンライン] の状態を `F12` [**オフライン**] に**変更します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f5971-179">In Microsoft Edge DevTools \(`F12`\), choose **Network** then change the **Online** status to **Offline**.</span></span>  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="Microsoft Edge DevTools でアプリをオフライン モードに設定する" lightbox="./media/devtools-offline.png":::
       <span data-ttu-id="f5971-181">Microsoft Edge DevTools でアプリをオフライン モードに設定する</span><span class="sxs-lookup"><span data-stu-id="f5971-181">Setting app to offline mode in Microsoft Edge DevTools</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="f5971-182">アプリを更新すると、キャッシュからアプリのリソースを提供するためのオフライン メカニズムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5971-182">Refresh your app and it should display the offline mechanism for serving the resources of your app from the cache.</span></span>  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="オフラインで実行されている PWA" lightbox="./media/vs-nodejs-express-index.png":::
       <span data-ttu-id="f5971-184">オフラインで実行されている PWA</span><span class="sxs-lookup"><span data-stu-id="f5971-184">PWA running offline</span></span>
    :::image-end:::
    
## <span data-ttu-id="f5971-185">PWA にプッシュ通知を追加する</span><span class="sxs-lookup"><span data-stu-id="f5971-185">Add push notifications to your PWA</span></span>  

<span data-ttu-id="f5971-186">プッシュ通知をサポートする PAS を作成するには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5971-186">You may create PWAs that support push notifications by completing the following tasks.</span></span>  

1.  <span data-ttu-id="f5971-187">プッシュ API を使用してメッセージング サービスを [サブスクライブする][MDNPushApi]</span><span class="sxs-lookup"><span data-stu-id="f5971-187">Subscribe to a messaging service using the [Push API][MDNPushApi]</span></span>  
1.  <span data-ttu-id="f5971-188">Notifications API を使用してサービスからメッセージを受信するとトースト メッセージを [表示する][MDNNotificationsApi]</span><span class="sxs-lookup"><span data-stu-id="f5971-188">Display a toast message when a message is received from the service using the [Notifications API][MDNNotificationsApi]</span></span>  
    
<span data-ttu-id="f5971-189">サービス ワーカーと同様に、プッシュ通知 API は標準ベースの API です。</span><span class="sxs-lookup"><span data-stu-id="f5971-189">Just like with Service Workers, the push notification APIs are standards-based APIs.</span></span>  <span data-ttu-id="f5971-190">プッシュ通知 API はブラウザー間で機能します。したがって、コードは PAP がサポートされているあらゆる場所で動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5971-190">The push notification APIs work across browsers, so your code should work everywhere that PWAs are supported.</span></span>  <span data-ttu-id="f5971-191">サーバー上の異なるブラウザーにプッシュ メッセージを配信する方法の詳細については [、Web プッシュに移動します][NPMWebPush]。</span><span class="sxs-lookup"><span data-stu-id="f5971-191">For more information about delivering push messages to different browsers on your server, navigate to [Web-Push][NPMWebPush].</span></span>  

<span data-ttu-id="f5971-192">次の手順は、Mozilla が提供する Service [Worker Cookbook][ServiceWorkerCookbookPushRichDemo] の Push Rich Demo から作成された手順です。Mozilla には、他にも便利な Web プッシュとサービス ワーカーのレシピが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="f5971-192">The following steps have been adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which has a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="f5971-193">手順 1 - VAPID キーを生成する</span><span class="sxs-lookup"><span data-stu-id="f5971-193">Step 1 - Generate VAPID keys</span></span>  

<span data-ttu-id="f5971-194">プッシュ通知では、PWA クライアントにプッシュ メッセージを送信するために VAPID \(任意のアプリケーション サーバー識別\) キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="f5971-194">Push notifications require VAPID \(Voluntary Application Server Identification\) keys in order to send push messages to the PWA client.</span></span>  <span data-ttu-id="f5971-195">オンラインで利用可能な VAPID キー ジェネレーターは複数あります (たとえば、vapidkeys.com [\)。][VapidkeysMain]</span><span class="sxs-lookup"><span data-stu-id="f5971-195">There are several VAPID key generators available online \(for example, [vapidkeys.com][VapidkeysMain]\).</span></span>  <span data-ttu-id="f5971-196">生成後、公開キーとプライベート キーを含む JSON オブジェクトを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5971-196">After generation, you should get a JSON object containing a public and private key.</span></span>  <span data-ttu-id="f5971-197">次のチュートリアルの後の手順で使用するキーを保存します。</span><span class="sxs-lookup"><span data-stu-id="f5971-197">Save the keys for later steps in the following tutorial.</span></span>  <span data-ttu-id="f5971-198">VAPID と WebPush の詳細については [、Mozilla Push Service][MozillaServicesSendingVapidWebPushNotificationsPush]を使用して VAPID が識別した WebPush 通知の送信に移動します。</span><span class="sxs-lookup"><span data-stu-id="f5971-198">For information about VAPID and WebPush, navigate to [Sending VAPID identified WebPush Notifications using the Mozilla Push Service][MozillaServicesSendingVapidWebPushNotificationsPush].</span></span>  

### <span data-ttu-id="f5971-199">手順 2 - プッシュ通知をサブスクライブする</span><span class="sxs-lookup"><span data-stu-id="f5971-199">Step 2 - Subscribe to push notifications</span></span>  

<span data-ttu-id="f5971-200">サービス ワーカーは、PWA でプッシュ イベントとトースト通知の操作を処理します。</span><span class="sxs-lookup"><span data-stu-id="f5971-200">Service workers handle push events and toast notification interactions in your PWA.</span></span>  <span data-ttu-id="f5971-201">PWA をサーバー プッシュ通知にサブスクライブするには、次の条件が満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5971-201">To subscribe the PWA to server push notifications, ensure the following conditions are met.</span></span>  

*   <span data-ttu-id="f5971-202">PWA がインストール、アクティブ、および登録されている</span><span class="sxs-lookup"><span data-stu-id="f5971-202">Your PWA is installed, active, and registered</span></span>  
*   <span data-ttu-id="f5971-203">サブスクリプション タスクを完了するコードが PWA のメイン UI スレッドにある</span><span class="sxs-lookup"><span data-stu-id="f5971-203">Your code to complete the subscription task is on the main UI thread of the PWA</span></span>  
*   <span data-ttu-id="f5971-204">ネットワーク接続がある</span><span class="sxs-lookup"><span data-stu-id="f5971-204">You have network connectivity</span></span>  
    
<span data-ttu-id="f5971-205">新しいプッシュ サブスクリプションを作成する前に、Microsoft Edge は、ユーザーが通知を受信するための PWA アクセス許可を付与した場合に確認します。</span><span class="sxs-lookup"><span data-stu-id="f5971-205">Before a new push subscription is created, Microsoft Edge verifies if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="f5971-206">アクセス許可が設定されていない場合、ユーザーはブラウザーからアクセス許可を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5971-206">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="f5971-207">アクセス許可が拒否された場合、要求は処理 `registration.pushManager.subscribe` `DOMException` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5971-207">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, which must be handled.</span></span>  <span data-ttu-id="f5971-208">アクセス許可管理の詳細については [、Microsoft Edge のプッシュ通知に移動します][WindowsBlogsWebNotificationsEdge]。</span><span class="sxs-lookup"><span data-stu-id="f5971-208">For more on permission management, navigate to [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="f5971-209">ファイルに `pwabuilder-sw-register.js` 、次のコード スニペットを追加します。</span><span class="sxs-lookup"><span data-stu-id="f5971-209">In your `pwabuilder-sw-register.js` file, append the following code snippet.</span></span>  

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

<span data-ttu-id="f5971-210">詳細については [、PushManager][MDNPushManager] と [Web プッシュに移動します][NPMWebPushUsage]。</span><span class="sxs-lookup"><span data-stu-id="f5971-210">For more information, navigate to [PushManager][MDNPushManager] and [Web-Push][NPMWebPushUsage].</span></span>  

### <span data-ttu-id="f5971-211">手順 3 - プッシュ通知をリッスンする</span><span class="sxs-lookup"><span data-stu-id="f5971-211">Step 3 - Listen for push notifications</span></span>  

<span data-ttu-id="f5971-212">PWA でサブスクリプションを作成したら、プッシュ イベントに応答するハンドラーをサービス ワーカーに追加します。</span><span class="sxs-lookup"><span data-stu-id="f5971-212">After a subscription is created in your PWA, add handlers to the service worker to respond to push events.</span></span>  <span data-ttu-id="f5971-213">プッシュ イベントは、トースト通知を表示するためにサーバーから送信されます。</span><span class="sxs-lookup"><span data-stu-id="f5971-213">Push event are sent from the server to display toast notifications.</span></span>  <span data-ttu-id="f5971-214">トースト通知は、受信したメッセージのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="f5971-214">Toast notifications display data for a received message.</span></span>  <span data-ttu-id="f5971-215">次のタスクを完了するには、クリック ハンドラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5971-215">To complete the following tasks, you must add a click handler.</span></span>  

*   <span data-ttu-id="f5971-216">トースト通知を閉じる</span><span class="sxs-lookup"><span data-stu-id="f5971-216">Dismiss the toast notification</span></span>  
*   <span data-ttu-id="f5971-217">開く、フォーカスする、開く、フォーカスを設定する</span><span class="sxs-lookup"><span data-stu-id="f5971-217">Open, focus, or open and focus any open windows</span></span>  
*   <span data-ttu-id="f5971-218">PWA クライアント ページを表示するために新しいウィンドウを開いてフォーカスを設定する</span><span class="sxs-lookup"><span data-stu-id="f5971-218">Open and focus a new window to display a PWA client page</span></span>  
    
<span data-ttu-id="f5971-219">ファイルに `pwabuilder-sw.js` 、次のハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f5971-219">In your `pwabuilder-sw.js` file, add the following handlers.</span></span>  

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

### <span data-ttu-id="f5971-220">手順 4 - 試してみる</span><span class="sxs-lookup"><span data-stu-id="f5971-220">Step 4 - Try it out</span></span>  

<span data-ttu-id="f5971-221">PWA のプッシュ通知をテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f5971-221">To test push notifications for your PWA, complete the following steps.</span></span>  

1.  <span data-ttu-id="f5971-222">PWA に移動します `http://localhost:3000` 。</span><span class="sxs-lookup"><span data-stu-id="f5971-222">Navigate to your PWA at `http://localhost:3000`.</span></span>  <span data-ttu-id="f5971-223">サービス ワーカーがアクティブ化し、PWA をサブスクライブして通知をプッシュしようとすると、Microsoft Edge は PWA に通知の表示を許可するように求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="f5971-223">When your service worker activates and attempts to subscribe your PWA to push notifications, Microsoft Edge prompts you to allow your PWA to show notifications.</span></span>  <span data-ttu-id="f5971-224">[許可 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5971-224">Select **Allow**.</span></span>  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="通知を有効にするためのアクセス許可ダイアログ" lightbox="./media/notification-permission.png":::
       <span data-ttu-id="f5971-226">通知を有効にするためのアクセス許可ダイアログ</span><span class="sxs-lookup"><span data-stu-id="f5971-226">Permission dialog for enabling notifications</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="f5971-227">サーバー側プッシュ通知をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="f5971-227">Simulate a server-side push notification.</span></span>  <span data-ttu-id="f5971-228">ブラウザーで PWA を開 `http://localhost:3000` いた後 `F12` 、DevTools を開くことを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5971-228">With your PWA opened at `http://localhost:3000` in your browser, select `F12` to open the DevTools.</span></span>  <span data-ttu-id="f5971-229">[**アプリケーション**  >  **サービス ワーカー プッシュ]**  >  **を選択**して、テスト プッシュ通知を PWA に送信します。</span><span class="sxs-lookup"><span data-stu-id="f5971-229">Choose **Application** > **Service Worker** > **Push** to send a test push notification to your PWA.</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="f5971-230">プッシュ通知はタスク バーの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5971-230">A push notification should display near the taskbar.</span></span>  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="DevTools からの通知のプッシュ" lightbox="./media/devtools-push.png":::
             <span data-ttu-id="f5971-232">DevTools からの通知のプッシュ</span><span class="sxs-lookup"><span data-stu-id="f5971-232">Push a notification from DevTools</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="f5971-233">トースト通知を \(または activate\) 選択しない場合、システムは数秒後に自動的に通知を閉じ、Windows アクション センターでキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="f5971-233">If you do not select \(or activate\) a toast notification, the system automatically dismisses it after several seconds and queues it in your Windows Action Center.</span></span>  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows アクション センターでの通知" lightbox="./media/windows-action-center.png":::
             <span data-ttu-id="f5971-235">Windows アクション センターでの通知</span><span class="sxs-lookup"><span data-stu-id="f5971-235">Notifications in Windows Action Center</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="f5971-236">次のステップ</span><span class="sxs-lookup"><span data-stu-id="f5971-236">Next steps</span></span>  

<span data-ttu-id="f5971-237">以下の手順には、実際の PAS の構築を理解するのに役立つ追加のタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5971-237">The following steps include additional tasks to help you understand building real-world PWAs.</span></span>  

*   <span data-ttu-id="f5971-238">プッシュ サブスクリプションの管理と保存</span><span class="sxs-lookup"><span data-stu-id="f5971-238">Manage and store push subscriptions</span></span>  
*   <span data-ttu-id="f5971-239">[ペイロード データ][NPMWebPushEncrypt] を暗号化する</span><span class="sxs-lookup"><span data-stu-id="f5971-239">[Encrypt][NPMWebPushEncrypt] payload data</span></span>  
*   <span data-ttu-id="f5971-240">レスポンシブ デザイン</span><span class="sxs-lookup"><span data-stu-id="f5971-240">Responsive design</span></span>  
*   <span data-ttu-id="f5971-241">ディープ リンク</span><span class="sxs-lookup"><span data-stu-id="f5971-241">Deep-linking</span></span>  
*   [<span data-ttu-id="f5971-242">クロスブラウザー テスト</span><span class="sxs-lookup"><span data-stu-id="f5971-242">Cross-browser testing</span></span>][BrowserStackTestEdgeBrowser]  
*   <span data-ttu-id="f5971-243">Webhint などの検証とテストのプラクティス [を実装する][Webhint]</span><span class="sxs-lookup"><span data-stu-id="f5971-243">Implement validation and testing practices such as [Webhint][Webhint]</span></span>  
    
## <span data-ttu-id="f5971-244">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5971-244">See also</span></span>  

*   [<span data-ttu-id="f5971-245">MDN Web ドキュメント上の段階的な Web アプリ</span><span class="sxs-lookup"><span data-stu-id="f5971-245">Progressive Web Apps on MDN web docs</span></span>][MDNProgressiveWebApps]  
*   [<span data-ttu-id="f5971-246">Web.dev 上の段階的な Web アプリ</span><span class="sxs-lookup"><span data-stu-id="f5971-246">Progressive Web Apps on web.dev</span></span>][WebDevProgressiveWebApps]  
*   <span data-ttu-id="f5971-247">[段階的な Web][HackerNewsProgressiveWebApps] アプリとしてのハッカーニュース リーダー - サンプル \(Hacker News reader\) PWA を実装するためのさまざまなフレームワークとパフォーマンス パターンを比較します。</span><span class="sxs-lookup"><span data-stu-id="f5971-247">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  
*   [<span data-ttu-id="f5971-248">1000,000</span><span class="sxs-lookup"><span data-stu-id="f5971-248">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="f5971-249">段階的な Web アプリの段階的なロードマップ</span><span class="sxs-lookup"><span data-stu-id="f5971-249">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="f5971-250">段階的な Web アプリを使用したオフライン POS</span><span class="sxs-lookup"><span data-stu-id="f5971-250">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="f5971-251">PWA Q&A</span><span class="sxs-lookup"><span data-stu-id="f5971-251">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="f5971-252">Web 上で楽しむ</span><span class="sxs-lookup"><span data-stu-id="f5971-252">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="f5971-253">段階的な Web アプリの名前付け</span><span class="sxs-lookup"><span data-stu-id="f5971-253">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="f5971-254">フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 1)</span><span class="sxs-lookup"><span data-stu-id="f5971-254">Designing And Building A Progressive Web Application Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [<span data-ttu-id="f5971-255">フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 2)</span><span class="sxs-lookup"><span data-stu-id="f5971-255">Designing And Building A Progressive Web Application Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [<span data-ttu-id="f5971-256">フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 3)</span><span class="sxs-lookup"><span data-stu-id="f5971-256">Designing And Building A Progressive Web Application Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "コードをNode.jsして Azure にアプリをVisual Studioする |Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントを作成する |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio Code"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA Q&A"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "段階的な Web アプリの段階的なロードマップ"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "新しい Edge Edition の機能を提供する PAS"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "Express アプリケーション ジェネレーター |Express" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "段階的な Web アプリの名前付け"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "段階的な Web アプリとしてのハッカーニュースリーダー"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web 上で楽しむ"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "段階的な Web アプリ \(PAS) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "サービス ワーカー API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービス ワーカーの使用 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "段階的な Web アプリを使用したオフライン POS"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "Mozilla のプッシュ サービスを介して VAPID によって識別された WebPush 通知を送信する |Mozilla Services"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-push |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt(userPublicKey, userAuth, payload, contentEncoding) - web-push |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用法 - Web プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "段階的な Web アプリ"  

[PwaBuilder]: https://www.pwabuilder.com "PWA Builder"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービス ワーカー |PWA Builder"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "プッシュ リッチ デモ |ServiceWorker Cookbook"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 1)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 2)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 3)"  

[VapidkeysMain]: https://vapidkeys.com "Secure VAPID Key Generator |VapidKeys" 

[Webhint]: https://webhint.io "webhint"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "段階的な Web アプリ |web.dev"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "段階的な機能強化 |Wikipedia"  
