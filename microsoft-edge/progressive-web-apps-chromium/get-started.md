---
description: このガイドでは、Windows でプログレッシブ Web アプリ (Chromium) を構築するための PWA の基本とツールの概要について説明します。
title: プログレッシブ Web アプリ (Chromium) の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、PWABuilder、web マニフェスト、サービスワーカー、プッシュ
ms.openlocfilehash: 065ced3afa8ecd4165325fd4f10a673d86c72fa7
ms.sourcegitcommit: be76feed0d616a96c77ea2748a9f0d6c0c06284b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103925"
---
# <span data-ttu-id="a9d7b-104">プログレッシブ Web アプリ (Chromium) の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-104">Get started with Progressive Web Apps (Chromium)</span></span>  

<span data-ttu-id="a9d7b-105">プログレッシブ Web アプリ (PWAs \) は、 [段階的に拡張][WikiProgressiveEnhancement]されている web アプリです。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-105">Progressive Web Apps \(PWAs\) are web apps that are [progressively enhanced][WikiProgressiveEnhancement].</span></span>  <span data-ttu-id="a9d7b-106">プログレッシブ機能拡張には、インストール、オフラインサポート、プッシュ通知などのアプリのような機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-106">The progressive enhancements include app-like features, such as installation, offline support, and push notifications.</span></span>  <span data-ttu-id="a9d7b-107">アプリストア用の PWA をパッケージ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-107">You may also package your PWA for app stores.</span></span>  <span data-ttu-id="a9d7b-108">アプリストアには、Microsoft ストア、Google Play、Mac App Store などが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-108">Possible app stores include the Microsoft Store, Google Play, Mac App Store, and more.</span></span>  <span data-ttu-id="a9d7b-109">Microsoft Store は、Windows 10 に組み込まれた商用アプリストアです。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-109">The Microsoft Store is the commercial app store built into Windows 10.</span></span>  

<span data-ttu-id="a9d7b-110">次のガイドでは、簡単な web アプリを作成し、それを PWA として拡張することで、PWA の基本的な概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-110">The following guide gives you an overview of PWA basics by creating a simple web app and extending it as a PWA.</span></span>  <span data-ttu-id="a9d7b-111">完成したプロジェクトは、最新のブラウザーで動作します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-111">The finished project works across modern browsers.</span></span>  

> [!TIP]
> <span data-ttu-id="a9d7b-112">[PWABuilder][PwaBuilder]を使用して、新しい pwa の作成、既存の pwa の強化、アプリストア用の pwa のパッケージ化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-112">You may use [PWABuilder][PwaBuilder] to create a new PWA, enhance your existing PWA, or package your PWA for app stores.</span></span>  

## <span data-ttu-id="a9d7b-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="a9d7b-113">Prerequisites</span></span>  

*   <span data-ttu-id="a9d7b-114">[Visual Studio コード][VisualstudioCodeMain]を使って、PWA ソースコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-114">Use [Visual Studio Code][VisualstudioCodeMain] to edit your PWA source code.</span></span>  
*   <span data-ttu-id="a9d7b-115">[Node.js][NodejsMain]をローカル web サーバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-115">Use [Node.js][NodejsMain] as your local web server.</span></span>  

## <span data-ttu-id="a9d7b-116">基本的な web アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-116">Create a basic web app</span></span>  

<span data-ttu-id="a9d7b-117">空の web アプリを作成するには、 [ノードエクスプレスアプリジェネレーター][ExpressjsApplicationGenerator]の手順に従い、アプリの名前を指定し `MySamplePwa` ます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-117">To create an empty web app, follow the steps in [Node Express App Generator][ExpressjsApplicationGenerator], and name your app `MySamplePwa`.</span></span>  

<span data-ttu-id="a9d7b-118">プロンプトが表示されたら、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-118">In the prompt, run the following commands.</span></span>  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

<span data-ttu-id="a9d7b-119">このコマンドは、空の web アプリを作成して、依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-119">The commands create an empty web app and install any dependencies.</span></span>  

<span data-ttu-id="a9d7b-120">これで、簡単で実用的な web アプリを利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-120">You now have a simple, functional web app.</span></span>  <span data-ttu-id="a9d7b-121">Web アプリを起動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-121">To start your web app, run the following command.</span></span>  

```shell
npm start
```  

<span data-ttu-id="a9d7b-122">次に、を参照し `http://localhost:3000` て新しい web アプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-122">Now browse to `http://localhost:3000` to view your new web app.</span></span>  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/vs-nodejs-express-index.png":::
   <span data-ttu-id="a9d7b-124">新しい PWA を localhost で実行する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-124">Running your new PWA on localhost</span></span>
:::image-end:::

## <span data-ttu-id="a9d7b-125">PWA の構築を開始する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-125">Get started building a PWA</span></span>  

<span data-ttu-id="a9d7b-126">シンプルな web アプリを作成したので、PWAs の3つの要件を追加して、それを PWA として拡張します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-126">Now that you have a simple web app, extend it as a PWA by adding the three requirements for PWAs</span></span><!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]--><span data-ttu-id="a9d7b-127">: [HTTPS](#step-1---use-https)、 [Web アプリマニフェスト](#step-2---create-a-web-app-manifest)、 [サービスワーカー](#step-3---add-a-service-worker)。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-127">: [HTTPS](#step-1---use-https), a [Web App Manifest](#step-2---create-a-web-app-manifest), and a [Service Worker](#step-3---add-a-service-worker).</span></span>  

### <span data-ttu-id="a9d7b-128">手順 1-HTTPS を使用する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-128">Step 1 - Use HTTPS</span></span>  

<span data-ttu-id="a9d7b-129">[サービスワーカー][MDNServiceWorkerApi]などの PWA プラットフォームの重要な部分には、HTTPS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-129">Key parts of the PWA platform, such as [Service Workers][MDNServiceWorkerApi], require the use of HTTPS.</span></span>  <span data-ttu-id="a9d7b-130">PWA が有効になったら、HTTPS URL に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-130">When your PWA goes live, you must publish it to an HTTPS URL.</span></span>  

<span data-ttu-id="a9d7b-131">デバッグ目的で、Microsoft Edge でも `http://localhost` PWA api の使用が許可されています。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-131">For debugging purposes, Microsoft Edge also permits `http://localhost` to use the PWA APIs.</span></span>  

<span data-ttu-id="a9d7b-132">[Web アプリをライブサイトとして公開][VisualStudioNodejsTutorialPublishAzureAppService]しますが、サーバーが HTTPS 用に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-132">[Publish your web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService], but ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="a9d7b-133">たとえば、 [Azure 無料アカウント][AzureCreateFreeAccount]を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-133">For example, you may create an [Azure free account][AzureCreateFreeAccount].</span></span>  <span data-ttu-id="a9d7b-134">[Microsoft Azure App Service][AzureWebApps]でサイトをホストします。既定では HTTPS 経由で提供されます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-134">Host your site on the [Microsoft Azure App Service][AzureWebApps] and it is served over HTTPS by default.</span></span>  

<span data-ttu-id="a9d7b-135">次のガイドを使用し `http://localhost` て、PWA を構築します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-135">The following guide, use `http://localhost` to build your PWA.</span></span>  

### <span data-ttu-id="a9d7b-136">手順 2-Web アプリマニフェストを作成する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-136">Step 2 - Create a Web App Manifest</span></span>  

<span data-ttu-id="a9d7b-137">[Web アプリマニフェスト][MDNWebAppManifest]は、アプリに関するメタデータ (名前、説明、アイコンなど) を含む JSON ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-137">A [Web App Manifest][MDNWebAppManifest] is a JSON file containing metadata about your app, such as name, description, icons, and more.</span></span>  

<span data-ttu-id="a9d7b-138">Web アプリにアプリマニフェストを追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-138">To add an app manifest to the web app:</span></span>  

1.  <span data-ttu-id="a9d7b-139">Visual Studio のコードで、[**ファイル**を開くフォルダー] を選択し、前に作成した  >  **Open Folder**ディレクトリを選択し `MySamplePwa` ます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-139">In Visual Studio Code, choose **File** > **Open Folder** and choose the `MySamplePwa` directory you created earlier.</span></span>  
1.  <span data-ttu-id="a9d7b-140">`Ctrl` + `N` 新しいファイルを作成するには、次のコードスニペットを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-140">Select `Ctrl`+`N` to create a new file, and paste in the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="a9d7b-141">ファイルをとして保存 `/MySamplePwa/public/manifest.json` します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-141">Save the file as `/MySamplePwa/public/manifest.json`.</span></span>  
1.  <span data-ttu-id="a9d7b-142">という名前の 512 x 512 のアプリアイコンイメージを追加 `icon512.png` `/MySamplePwa/public/images` します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-142">Add a 512x512 app icon image named `icon512.png` to `/MySamplePwa/public/images`.</span></span>  <span data-ttu-id="a9d7b-143">テスト目的で [サンプルの画像][ImagePwa] を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-143">You may use the [sample image][ImagePwa] for testing purposes.</span></span>  
1.  <span data-ttu-id="a9d7b-144">Visual Studio のコードで `/public/index.html` 、を開き、次のコードスニペットをタグ内に追加し `<head>` ます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-144">In Visual Studio Code, open `/public/index.html`, and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### <span data-ttu-id="a9d7b-145">手順 3-サービスワーカーを追加する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-145">Step 3 - Add a Service Worker</span></span>  

<span data-ttu-id="a9d7b-146">サービスワーカーは、PWAs の主要なテクノロジであり、オフラインサポート、高度なキャッシュ、実行中のバックグラウンドタスクなどのシナリオを以前からネイティブアプリに限定することができます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-146">Service workers are the key technology behind PWAs, enabling scenarios like offline support, advanced caching, and running background tasks previously limited to native apps.</span></span>  

<span data-ttu-id="a9d7b-147">サービスワーカーは、web アプリからネットワーク要求を傍受するバックグラウンドタスクです。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-147">Service workers are background tasks that intercept network requests from your web app.</span></span>  <span data-ttu-id="a9d7b-148">サービス作業者が、PWA が実行されていない場合でも、タスクの実行を試みます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-148">Service workers attempt to complete tasks, even when your PWA is not running.</span></span>  <span data-ttu-id="a9d7b-149">タスクには次の操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-149">Tasks include the following actions.</span></span>  

*   <span data-ttu-id="a9d7b-150">キャッシュから要求されたリソースを提供する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-150">Serving requested resources from a cache</span></span>  
*   <span data-ttu-id="a9d7b-151">プッシュ通知の送信</span><span class="sxs-lookup"><span data-stu-id="a9d7b-151">Sending push notifications</span></span>  
*   <span data-ttu-id="a9d7b-152">バックグラウンドフェッチタスクの実行</span><span class="sxs-lookup"><span data-stu-id="a9d7b-152">Running background fetch tasks</span></span>  
*   <span data-ttu-id="a9d7b-153">バッジのアイコン</span><span class="sxs-lookup"><span data-stu-id="a9d7b-153">Badging icons</span></span>  
*   <span data-ttu-id="a9d7b-154">その他</span><span class="sxs-lookup"><span data-stu-id="a9d7b-154">and more</span></span>  

<span data-ttu-id="a9d7b-155">サービスワーカーは、特別な JavaScript ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-155">Service workers are defined in a special JavaScript file.</span></span>  <span data-ttu-id="a9d7b-156">詳細については、「Service Worker と[Service WORKER API][MDNServiceWorkerApi][を使用][MDNUsingServiceWorkers]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-156">For more information, navigate to [Using Service Workers][MDNUsingServiceWorkers] and [Service Worker API][MDNServiceWorkerApi].</span></span>  

<span data-ttu-id="a9d7b-157">プロジェクトでサービスワーカーを構築するには、 [PWA ビルダー][PwaBuilderServiceWorker]から**キャッシュの最初のネットワーク**サービスワーカーレシピを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-157">To build a service worker in your project, use the **Cache-first network** service worker recipe from [PWA Builder][PwaBuilderServiceWorker].</span></span>  

1.  <span data-ttu-id="a9d7b-158">[Pwabuilder.com/serviceworker][PwaBuilderServiceWorker]に移動して、[**キャッシュ-最初のネットワーク**サービス] ワーカーを選択し、[**ダウンロード**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-158">Navigate to [pwabuilder.com/serviceworker][PwaBuilderServiceWorker], select the **Cache-first network** service worker, and select the **Download** button.</span></span>  <span data-ttu-id="a9d7b-159">ダウンロードしたファイルには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-159">The downloaded file contains the following files:</span></span>
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
    
1.  <span data-ttu-id="a9d7b-160">ダウンロードしたファイルを `public` web アプリプロジェクトのフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-160">Copy the downloaded files to the `public` folder in your web app project.</span></span>  
    
1.  <span data-ttu-id="a9d7b-161">Visual Studio のコードで、 `/public/index.html` 次のコードスニペットを開いて、タグ内に追加し `<head>` ます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-161">In Visual Studio Code, open `/public/index.html` and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
<span data-ttu-id="a9d7b-162">これで、web アプリにキャッシュから最初の戦略を使用するサービスワーカーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-162">Your web app now has a service worker that uses the cache-first strategy.</span></span>  <span data-ttu-id="a9d7b-163">新しいサービスワーカーは、最初に、または必要に応じてネットワークからリソースをフェッチします。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-163">You new service worker fetches resources from the cache first, and from the network only as needed.</span></span>  <span data-ttu-id="a9d7b-164">キャッシュされたリソースには、画像、JavaScript、CSS、HTML が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-164">Cached resources include images, JavaScript, CSS, and HTML.</span></span>

<span data-ttu-id="a9d7b-165">次の手順を使用して、サービスワーカーが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-165">Use the following steps to confirm that your service worker runs.</span></span>  

1.  <span data-ttu-id="a9d7b-166">を使用して web アプリに移動し `http://localhost:3000` ます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-166">Navigate to your web app using `http://localhost:3000`.</span></span>  <span data-ttu-id="a9d7b-167">Web アプリを利用できない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-167">If your web app is not available, run the following command.</span></span>   
    
    ```shell
    npm start
    ```
    
1.  <span data-ttu-id="a9d7b-168">Microsoft Edge で、 `F12` Microsoft Edge DevTools を選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-168">In Microsoft Edge, select `F12` to open the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="a9d7b-169">[ **アプリケーション**] を選択し **てから、サービスワーカー** を表示します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-169">Select **Application**, then **Service Workers** to view the service workers.</span></span>  <span data-ttu-id="a9d7b-170">サービスワーカーが表示されない場合は、ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-170">If the service worker is not displayed, refresh the page.</span></span>  
     
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/devtools-sw-overview.png":::
       <span data-ttu-id="a9d7b-172">Microsoft Edge DevTools サービスワーカーの概要</span><span class="sxs-lookup"><span data-stu-id="a9d7b-172">Microsoft Edge DevTools Service Worker overview</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="a9d7b-173">**キャッシュストレージ**を展開してサービスワーカーキャッシュを表示し、[ **pwabuilder-precache**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-173">View the service worker cache by expanding **Cache Storage** and select **pwabuilder-precache**.</span></span>  <span data-ttu-id="a9d7b-174">サービスワーカーによってキャッシュされたすべてのリソースが表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-174">All of the resources cached by the service worker should be displayed.</span></span>  <span data-ttu-id="a9d7b-175">サービスワーカーによってキャッシュされたリソースには、アプリのアイコン、アプリマニフェスト、CSS、JavaScript ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-175">The resources cached by the service worker include the app icon, app manifest, CSS, and JavaScript files.</span></span>  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/devtools-cache.png":::
       <span data-ttu-id="a9d7b-177">Microsoft Edge DevTools でのサービスワーカーキャッシュ (F12)</span><span class="sxs-lookup"><span data-stu-id="a9d7b-177">Service Worker cache in Microsoft Edge DevTools (F12)</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="a9d7b-178">PWA をオフラインアプリとして試してみてください。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-178">Try your PWA as an offline app.</span></span>  <span data-ttu-id="a9d7b-179">Microsoft Edge DevTools \ ( `F12` \) で、[ **ネットワーク** ] を選択し、[ **オンライン** 状態] を [ **オフライン**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-179">In Microsoft Edge DevTools \(`F12`\), choose **Network** then change the **Online** status to **Offline**.</span></span>  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/devtools-offline.png":::
       <span data-ttu-id="a9d7b-181">Microsoft Edge DevTools でアプリをオフラインモードに設定する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-181">Setting app to offline mode in Microsoft Edge DevTools</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="a9d7b-182">アプリを更新すると、キャッシュからアプリのリソースを提供するためのオフラインメカニズムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-182">Refresh your app and it should display the offline mechanism for serving the resources of your app from the cache.</span></span>  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/vs-nodejs-express-index.png":::
       <span data-ttu-id="a9d7b-184">オフラインで実行されている PWA</span><span class="sxs-lookup"><span data-stu-id="a9d7b-184">PWA running offline</span></span>
    :::image-end:::
    
## <span data-ttu-id="a9d7b-185">PWA にプッシュ通知を追加する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-185">Add push notifications to your PWA</span></span>  

<span data-ttu-id="a9d7b-186">次のタスクを実行して、プッシュ通知をサポートする PWAs を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-186">You may create PWAs that support push notifications by completing the following tasks.</span></span>  

1.  <span data-ttu-id="a9d7b-187">[プッシュ API][MDNPushApi]を使用したメッセージサービスの購読</span><span class="sxs-lookup"><span data-stu-id="a9d7b-187">Subscribe to a messaging service using the [Push API][MDNPushApi]</span></span>  
1.  <span data-ttu-id="a9d7b-188">[通知 API][MDNNotificationsApi]を使用してサービスからメッセージを受信したときにトーストメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-188">Display a toast message when a message is received from the service using the [Notifications API][MDNNotificationsApi]</span></span>  
    
<span data-ttu-id="a9d7b-189">サービスワーカーの場合と同様に、プッシュ通知 Api は標準ベースの Api です。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-189">Just like with Service Workers, the push notification APIs are standards-based APIs.</span></span>  <span data-ttu-id="a9d7b-190">プッシュ通知 Api はブラウザー間で動作するため、コードはすべてがサポートされているすべての場所で動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-190">The push notification APIs work across browsers, so your code should work everywhere that PWAs are supported.</span></span>  <span data-ttu-id="a9d7b-191">サーバー上のさまざまなブラウザーへのプッシュメッセージの配信について詳しくは、[ [Web-プッシュ][NPMWebPush]] に移動してください。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-191">For more information about delivering push messages to different browsers on your server, navigate to [Web-Push][NPMWebPush].</span></span>  

<span data-ttu-id="a9d7b-192">以下の手順は、Mozilla が提供する [Service Worker][ServiceWorkerCookbookPushRichDemo] の Web サイトの「プッシュリッチデモ」で採用されています。これには、他にも多くの便利な Web プッシュとサービス worker のレシピが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-192">The following steps have been adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which has a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="a9d7b-193">手順 1-VAPID キーを生成する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-193">Step 1 - Generate VAPID keys</span></span>  

<span data-ttu-id="a9d7b-194">プッシュ通知には、PWA クライアントにプッシュメッセージを送信するために、VAPID \ (自主的なアプリケーションサーバー Id) キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-194">Push notifications require VAPID \(Voluntary Application Server Identification\) keys in order to send push messages to the PWA client.</span></span>  <span data-ttu-id="a9d7b-195">オンラインで利用できる VAPID キージェネレーターはいくつかあります ( [vapidkeys.com][VapidkeysMain]など)。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-195">There are several VAPID key generators available online \(for example, [vapidkeys.com][VapidkeysMain]\).</span></span>  <span data-ttu-id="a9d7b-196">生成後、公開キーと秘密キーを含む JSON オブジェクトを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-196">After generation, you should get a JSON object containing a public and private key.</span></span>  <span data-ttu-id="a9d7b-197">以降の手順については、次のチュートリアルのキーを保存します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-197">Save the keys for later steps in the following tutorial.</span></span>  <span data-ttu-id="a9d7b-198">VAPID と WebPush の詳細については、「 [VAPID による Web プッシュ通知の送信][MozillaServicesSendingVapidWebPushNotificationsPush]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-198">For information about VAPID and WebPush, navigate to [Sending VAPID identified WebPush Notifications using the Mozilla Push Service][MozillaServicesSendingVapidWebPushNotificationsPush].</span></span>  

### <span data-ttu-id="a9d7b-199">手順 2-プッシュ通知への登録</span><span class="sxs-lookup"><span data-stu-id="a9d7b-199">Step 2 - Subscribe to push notifications</span></span>  

<span data-ttu-id="a9d7b-200">サービスワーカーは、PWA でプッシュイベントとトースト通知のやり取りを処理します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-200">Service workers handle push events and toast notification interactions in your PWA.</span></span>  <span data-ttu-id="a9d7b-201">PWA をサーバープッシュ通知に登録するには、次の条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-201">To subscribe the PWA to server push notifications, ensure the following conditions are met.</span></span>  

*   <span data-ttu-id="a9d7b-202">PWA がインストール、アクティブ、登録されている</span><span class="sxs-lookup"><span data-stu-id="a9d7b-202">Your PWA is installed, active, and registered</span></span>  
*   <span data-ttu-id="a9d7b-203">サブスクリプションタスクを完了するコードは、PWA のメイン UI スレッドにあります。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-203">Your code to complete the subscription task is on the main UI thread of the PWA</span></span>  
*   <span data-ttu-id="a9d7b-204">ネットワーク接続がある場合</span><span class="sxs-lookup"><span data-stu-id="a9d7b-204">You have network connectivity</span></span>  
    
<span data-ttu-id="a9d7b-205">新しいプッシュサブスクリプションが作成される前に、Microsoft Edge は、ユーザーが通知を受信できるように PWA 権限を与えられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-205">Before a new push subscription is created, Microsoft Edge verifies if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="a9d7b-206">許可されていない場合は、ブラウザーからアクセス許可を求められます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-206">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="a9d7b-207">アクセス許可が拒否された場合は、を例外として `registration.pushManager.subscribe` `DOMException` 処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-207">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, which must be handled.</span></span>  <span data-ttu-id="a9d7b-208">権限管理の詳細については、「 [Microsoft Edge でのプッシュ通知」][WindowsBlogsWebNotificationsEdge]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-208">For more on permission management, navigate to [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="a9d7b-209">ファイルで `pwabuilder-sw-register.js` 、次のコードスニペットを追加します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-209">In your `pwabuilder-sw-register.js` file, append the following code snippet.</span></span>  

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

<span data-ttu-id="a9d7b-210">詳細については、「 [Pushmanager][MDNPushManager] と [Web-プッシュ][NPMWebPushUsage]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-210">For more information, navigate to [PushManager][MDNPushManager] and [Web-Push][NPMWebPushUsage].</span></span>  

### <span data-ttu-id="a9d7b-211">手順 3-プッシュ通知をリッスンする</span><span class="sxs-lookup"><span data-stu-id="a9d7b-211">Step 3 - Listen for push notifications</span></span>  

<span data-ttu-id="a9d7b-212">PWA でサブスクリプションを作成した後で、プッシュイベントに応答するように、サービスワーカーにハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-212">After a subscription is created in your PWA, add handlers to the service worker to respond to push events.</span></span>  <span data-ttu-id="a9d7b-213">プッシュイベントは、トースト通知を表示するためにサーバーから送信されます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-213">Push event are sent from the server to display toast notifications.</span></span>  <span data-ttu-id="a9d7b-214">トースト通知では、受信したメッセージのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-214">Toast notifications display data for a received message.</span></span>  <span data-ttu-id="a9d7b-215">次のタスクを実行するには、クリックハンドラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-215">To complete the following tasks, you must add a click handler.</span></span>  

*   <span data-ttu-id="a9d7b-216">トースト通知を無視する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-216">Dismiss the toast notification</span></span>  
*   <span data-ttu-id="a9d7b-217">開いているウィンドウを開く、フォーカスする、または開く</span><span class="sxs-lookup"><span data-stu-id="a9d7b-217">Open, focus, or open and focus any open windows</span></span>  
*   <span data-ttu-id="a9d7b-218">新しいウィンドウを開いてフォーカスを移動し、PWA クライアントページを表示する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-218">Open and focus a new window to display a PWA client page</span></span>  
    
<span data-ttu-id="a9d7b-219">ファイルで `pwabuilder-sw.js` 、次のハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-219">In your `pwabuilder-sw.js` file, add the following handlers.</span></span>  

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

### <span data-ttu-id="a9d7b-220">手順 4-試してみる</span><span class="sxs-lookup"><span data-stu-id="a9d7b-220">Step 4 - Try it out</span></span>  

<span data-ttu-id="a9d7b-221">PWA のプッシュ通知をテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-221">To test push notifications for your PWA, complete the following steps.</span></span>  

1.  <span data-ttu-id="a9d7b-222">PWA に移動 `http://localhost:3000` します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-222">Navigate to your PWA at `http://localhost:3000`.</span></span>  <span data-ttu-id="a9d7b-223">サービスワーカーがアクティブになって PWA のプッシュ通知をサブスクライブしようとすると、Microsoft Edge で、PWA に通知を表示することを許可するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-223">When your service worker activates and attempts to subscribe your PWA to push notifications, Microsoft Edge prompts you to allow your PWA to show notifications.</span></span>  <span data-ttu-id="a9d7b-224">[ **許可**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-224">Select **Allow**.</span></span>  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/notification-permission.png":::
       <span data-ttu-id="a9d7b-226">通知を有効にするためのアクセス許可ダイアログ</span><span class="sxs-lookup"><span data-stu-id="a9d7b-226">Permission dialog for enabling notifications</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="a9d7b-227">サーバー側のプッシュ通知をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-227">Simulate a server-side push notification.</span></span>  <span data-ttu-id="a9d7b-228">使用しているブラウザーで PWA が開いたら `http://localhost:3000` 、を選択して `F12` devtools を開きます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-228">With your PWA opened at `http://localhost:3000` in your browser, select `F12` to open the DevTools.</span></span>  <span data-ttu-id="a9d7b-229">[**アプリケーション**  >  **サービスワーカー**プッシュ] を選択し  >  **Push**て、PWA にテストプッシュ通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-229">Choose **Application** > **Service Worker** > **Push** to send a test push notification to your PWA.</span></span>  
    :::row:::
       :::column span="":::
          <span data-ttu-id="a9d7b-230">プッシュ通知は、タスクバーの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-230">A push notification should display near the taskbar.</span></span>  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/devtools-push.png":::
             <span data-ttu-id="a9d7b-232">DevTools から通知をプッシュする</span><span class="sxs-lookup"><span data-stu-id="a9d7b-232">Push a notification from DevTools</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="a9d7b-233">トースト通知を選択しない場合、またはトースト通知を有効にしない場合は、数秒後に自動的に消去され、Windows アクションセンターでキューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-233">If you do not select \(or activate\) a toast notification, the system automatically dismisses it after several seconds and queues it in your Windows Action Center.</span></span>  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/windows-action-center.png":::
             <span data-ttu-id="a9d7b-235">Windows アクションセンターでの通知</span><span class="sxs-lookup"><span data-stu-id="a9d7b-235">Notifications in Windows Action Center</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="a9d7b-236">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a9d7b-236">Next steps</span></span>  

<span data-ttu-id="a9d7b-237">次の手順には、実際の PWAs の構築を理解するのに役立つ追加のタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-237">The following steps include additional tasks to help you understand building real-world PWAs.</span></span>  

*   <span data-ttu-id="a9d7b-238">プッシュサブスクリプションの管理と保存</span><span class="sxs-lookup"><span data-stu-id="a9d7b-238">Manage and store push subscriptions</span></span>  
*   <span data-ttu-id="a9d7b-239">ペイロードデータを[暗号化][NPMWebPushEncrypt]する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-239">[Encrypt][NPMWebPushEncrypt] payload data</span></span>  
*   <span data-ttu-id="a9d7b-240">レスポンシブ デザイン</span><span class="sxs-lookup"><span data-stu-id="a9d7b-240">Responsive design</span></span>  
*   <span data-ttu-id="a9d7b-241">ディープリンク</span><span class="sxs-lookup"><span data-stu-id="a9d7b-241">Deep-linking</span></span>  
*   [<span data-ttu-id="a9d7b-242">ブラウザ間のテスト</span><span class="sxs-lookup"><span data-stu-id="a9d7b-242">Cross-browser testing</span></span>][BrowserStackTestEdgeBrowser]  
*   <span data-ttu-id="a9d7b-243">[Web ヒント][Webhint]などの検証およびテストの実施方法を実装する</span><span class="sxs-lookup"><span data-stu-id="a9d7b-243">Implement validation and testing practices such as [Webhint][Webhint]</span></span>  
   
## <span data-ttu-id="a9d7b-244">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9d7b-244">See also</span></span>  

*   [<span data-ttu-id="a9d7b-245">MDN web ドキュメントのプログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="a9d7b-245">Progressive Web Apps on MDN web docs</span></span>][MDNProgressiveWebApps]  
*   [<span data-ttu-id="a9d7b-246">Dev でのプログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="a9d7b-246">Progressive Web Apps on web.dev</span></span>][WebDevProgressiveWebApps]  
*   <span data-ttu-id="a9d7b-247">[[プログレッシブ Web アプリとしてのハッカーニュースリーダー][HackerNewsProgressiveWebApps] ]: サンプル \ (ハッカーたち News READER) PWA を実装するためのさまざまなフレームワークとパフォーマンスパターンを比較します。</span><span class="sxs-lookup"><span data-stu-id="a9d7b-247">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  
*   [<span data-ttu-id="a9d7b-248">神話の場合</span><span class="sxs-lookup"><span data-stu-id="a9d7b-248">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="a9d7b-249">プログレッシブ Web アプリのためのプログレッシブロードマップ</span><span class="sxs-lookup"><span data-stu-id="a9d7b-249">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="a9d7b-250">プログレッシブ Web アプリでのオフライン投稿</span><span class="sxs-lookup"><span data-stu-id="a9d7b-250">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="a9d7b-251">PWA&</span><span class="sxs-lookup"><span data-stu-id="a9d7b-251">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="a9d7b-252">Web でのお賭け</span><span class="sxs-lookup"><span data-stu-id="a9d7b-252">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="a9d7b-253">プログレッシブ Web アプリに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="a9d7b-253">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="a9d7b-254">フレームワークなしでプログレッシブ Web アプリケーションを設計して構築する (パート 1)</span><span class="sxs-lookup"><span data-stu-id="a9d7b-254">Designing And Building A Progressive Web Application Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [<span data-ttu-id="a9d7b-255">フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 2)</span><span class="sxs-lookup"><span data-stu-id="a9d7b-255">Designing And Building A Progressive Web Application Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [<span data-ttu-id="a9d7b-256">フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 3)</span><span class="sxs-lookup"><span data-stu-id="a9d7b-256">Designing And Building A Progressive Web Application Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "Visual Studio コードを使って Azure に Node.js アプリを展開する |Microsoft ドキュメント"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントの作成 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio コード"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA&"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "プログレッシブ Web アプリのためのプログレッシブロードマップ"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "神話のお客は新しい Edge エディション"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "エクスプレスアプリケーションジェネレーター |高速" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "プログレッシブ Web アプリに名前を付ける"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "プログレッシブ Web アプリとしてのハッカーニュースリーダー"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web でのお賭け"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "プログレッシブ web アプリ \ (PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービスワーカーを使用する |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "プログレッシブ Web アプリでのオフライン投稿"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "VAPID を Mozilla のプッシュサービス経由で識別された Web プッシュ通知を送信しています。 |Mozilla サービス"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-プッシュ |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "暗号化 (userPublicKey、Userpublickey、payload、contentEncoding)-web-プッシュ |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用状況-web-プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "プログレッシブ Web アプリ"  

[PwaBuilder]: https://www.pwabuilder.com "PWA ビルダー"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービスワーカー |PWA ビルダー"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "充実したデモのプッシュ |ServiceWorker の料理"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "フレームワークなしでプログレッシブ Web アプリケーションを設計して構築する (パート 1)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 2)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 3)"  

[VapidkeysMain]: https://vapidkeys.com "Secure VAPID Key Generator |VapidKeys" 

[Webhint]: https://webhint.io "web ヒント"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "プログレッシブ Web アプリ |web.xml"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "プログレッシブエンハンスメント |Wikipedia"  
