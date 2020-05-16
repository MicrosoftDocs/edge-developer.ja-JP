---
description: このガイドでは、Windows でプログレッシブ web アプリを構築するための PWA の基本とツールの概要について説明します。
title: プログレッシブ Web アプリ (Chromium) の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、PWABuilder、web マニフェスト、サービスワーカー、プッシュ
ms.openlocfilehash: 6c5fa5d6af8494f33e11a545d5dde1264604c787
ms.sourcegitcommit: 136642396bb8094a535e203067ee429e60d31d25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "10659210"
---
# <span data-ttu-id="9b80b-104">プログレッシブ Web アプリ (Chromium) の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="9b80b-104">Get started with Progressive Web Apps (Chromium)</span></span>  

<span data-ttu-id="9b80b-105">プログレッシブ Web アプリ \ (PWAs \) は、インストール、オフラインサポート、プッシュ通知などのアプリのような機能によって[段階的に拡張][WikiProgressiveEnhancement]された web アプリです。</span><span class="sxs-lookup"><span data-stu-id="9b80b-105">Progressive Web Apps \(PWAs\) are web apps that are [progressively enhanced][WikiProgressiveEnhancement] with app-like features, such as installation, offline support, and push notifications.</span></span>  <span data-ttu-id="9b80b-106">また、Microsoft ストアや Google Play、Mac App Store などのアプリストア用に PWA をパッケージ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-106">You may also packaged your PWA for app stores, including the Microsoft Store as well as Google Play, Mac App Store and more.</span></span>  <span data-ttu-id="9b80b-107">Microsoft Store は、Windows 10 に組み込まれた商用アプリストアです。</span><span class="sxs-lookup"><span data-stu-id="9b80b-107">The Microsoft Store is the commercial app store built into Windows 10.</span></span>  

<span data-ttu-id="9b80b-108">次のガイドでは、簡単な web アプリを作成し、それを PWA として拡張することで、PWA の基本的な概要を示します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-108">The following guide gives you an overview of PWA basics by creating a simple web app and extending it as a PWA.</span></span>  <span data-ttu-id="9b80b-109">完成したプロジェクトは、最新のブラウザーで動作します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-109">The finished project works across modern browsers.</span></span>  

> [!TIP]
> <span data-ttu-id="9b80b-110">[PWABuilder][PwaBuilder]を使用して、新しい pwa の作成、既存の pwa の強化、アプリストア用の pwa のパッケージ化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-110">You may use [PWABuilder][PwaBuilder] to create a new PWA, enhance your existing PWA, or package your PWA for app stores.</span></span>  

## <span data-ttu-id="9b80b-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="9b80b-111">Prerequisites</span></span>  

*   <span data-ttu-id="9b80b-112">PWA ソースコードを編集するには、 [VS コード][VisualstudioCodeMain]を使います。</span><span class="sxs-lookup"><span data-stu-id="9b80b-112">Use [VS Code][VisualstudioCodeMain] to edit your PWA source code.</span></span>  
*   <span data-ttu-id="9b80b-113">ローカル web サーバーとして[node.js][NodejsMain]を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-113">Use [Node.js][NodejsMain] as your local web server.</span></span>  

## <span data-ttu-id="9b80b-114">基本的な web アプリをセットアップする</span><span class="sxs-lookup"><span data-stu-id="9b80b-114">Set up a basic web app</span></span>  

<span data-ttu-id="9b80b-115">空の web アプリを作成するには、[ノードエクスプレスアプリジェネレーター][ExpressjsApplicationGenerator]の手順に従い、アプリの名前を指定し `MySamplePwa` ます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-115">To create an empty web app, follow the steps in [Node Express App Generator][ExpressjsApplicationGenerator], and name your app `MySamplePwa`.</span></span>  

<span data-ttu-id="9b80b-116">プロンプトが表示されたら、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-116">In the prompt, run the following commands.</span></span>  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

<span data-ttu-id="9b80b-117">このコマンドは、空の web アプリを作成して、依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9b80b-117">The commands creates an empty web app and install any dependencies.</span></span>  

<span data-ttu-id="9b80b-118">簡単で実用的な web アプリを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9b80b-118">Now you have a simple, functional web app.</span></span>  <span data-ttu-id="9b80b-119">開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-119">To start it, run the following command.</span></span>  

```shell
npm start
```  

<span data-ttu-id="9b80b-120">次に、を参照し `http://localhost:3000` て新しい web アプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-120">Now browse to `http://localhost:3000` to view your new web app.</span></span>  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="新しい PWA を localhost で実行する":::
   <span data-ttu-id="9b80b-122">新しい PWA を localhost で実行する</span><span class="sxs-lookup"><span data-stu-id="9b80b-122">Running your new PWA on localhost</span></span>
:::image-end:::

## <span data-ttu-id="9b80b-123">PWA の構築を開始する</span><span class="sxs-lookup"><span data-stu-id="9b80b-123">Get started building a PWA</span></span>  

<span data-ttu-id="9b80b-124">シンプルな web アプリを作成したので、PWAs の3つの要件を追加して、それを PWA として拡張します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-124">Now that you have a simple web app, extend it as a PWA by adding the 3 requirements for PWAs</span></span><!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]--><span data-ttu-id="9b80b-125">: [HTTPS](#step-1---use-https)、 [Web アプリマニフェスト](#step-2---create-a-web-app-manifest)、[サービスワーカー](#step-3---add-a-service-worker)。</span><span class="sxs-lookup"><span data-stu-id="9b80b-125">: [HTTPS](#step-1---use-https), a [Web App Manifest](#step-2---create-a-web-app-manifest), and a [Service Worker](#step-3---add-a-service-worker).</span></span>  

### <span data-ttu-id="9b80b-126">手順 1-HTTPS を使用する</span><span class="sxs-lookup"><span data-stu-id="9b80b-126">Step 1 - Use HTTPS</span></span>  

<span data-ttu-id="9b80b-127">[サービスワーカー][MDNServiceWorkerApi]などの PWA プラットフォームの重要な部分には、HTTPS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b80b-127">Key parts of the PWA platform, such as [Service Workers][MDNServiceWorkerApi], require the use of HTTPS.</span></span>  <span data-ttu-id="9b80b-128">PWA が有効になったら、HTTPS URL に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b80b-128">When your PWA goes live, you must publish it to an HTTPS URL.</span></span>  

<span data-ttu-id="9b80b-129">デバッグ目的で、Microsoft Edge でも `http://localhost` PWA api の使用が許可されています。</span><span class="sxs-lookup"><span data-stu-id="9b80b-129">For debugging purposes, Microsoft Edge also permits `http://localhost` to use the PWA APIs.</span></span>  

<span data-ttu-id="9b80b-130">[Web アプリをライブサイトとして発行][VisualStudioNodejsTutorialPublishAzureAppService]する場合 (たとえば、 [Azure free アカウント][AzureCreateFreeAccount]をセットアップして)、サーバーが HTTPS 用に構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b80b-130">If you [publish your web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService] \(for example, by setting up an [Azure free account][AzureCreateFreeAccount]\), you must ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="9b80b-131">[Microsoft Azure App Service][AzureWebApps]を使ってサイトをホストしている場合、既定では HTTPS 経由で提供されます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-131">If you use the [Microsoft Azure App Service][AzureWebApps] to host your site, it is served over HTTPS by default.</span></span>  

<span data-ttu-id="9b80b-132">次のガイドを使用し `http://localhost` て、PWA を構築します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-132">The following guide, use `http://localhost` to build your PWA.</span></span>  

### <span data-ttu-id="9b80b-133">手順 2-Web アプリマニフェストを作成する</span><span class="sxs-lookup"><span data-stu-id="9b80b-133">Step 2 - Create a Web App Manifest</span></span>  

<span data-ttu-id="9b80b-134">[Web アプリマニフェスト][MDNWebAppManifest]は、アプリに関するメタデータ (名前、説明、アイコンなど) を含む JSON ファイルです。</span><span class="sxs-lookup"><span data-stu-id="9b80b-134">A [Web App Manifest][MDNWebAppManifest] is a JSON file containing metadata about your app, such as name, description, icons, and more.</span></span>  

<span data-ttu-id="9b80b-135">Web アプリにアプリマニフェストを追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9b80b-135">To add an app manifest to the web app:</span></span>  

1.  <span data-ttu-id="9b80b-136">VS コードで、[**ファイル**を  >  **開く] フォルダーを開い**て、前に作成したディレクトリを選択し `MySamplePwa` ます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-136">In VS Code, go **File** > **Open Folder** and choose the `MySamplePwa` directory you created earlier.</span></span>  
1.  <span data-ttu-id="9b80b-137">を押して `Ctrl` + `N` 新しいファイルを作成し、次のコードスニペットに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-137">Press `Ctrl`+`N` to create a new file, and paste in the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="9b80b-138">ファイルをとして保存 `/MySamplePwa/public/manifest.json` します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-138">Save the file as `/MySamplePwa/public/manifest.json`.</span></span>  
1.  <span data-ttu-id="9b80b-139">という名前の 512 x 512 のアプリアイコンイメージを追加 `icon512.png` `/MySamplePwa/public/images` します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-139">Add a 512x512 app icon image named `icon512.png` to `/MySamplePwa/public/images`.</span></span>  <span data-ttu-id="9b80b-140">テスト目的で[サンプルの画像][ImagePwa]を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-140">You may use the [sample image][ImagePwa] for testing purposes.</span></span>  
1.  <span data-ttu-id="9b80b-141">VS コードで、 `/public/index.html` を開き、次のコードスニペットをタグ内に追加し `<head>` ます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-141">In VS Code, open `/public/index.html`, and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### <span data-ttu-id="9b80b-142">手順 3-サービスワーカーを追加する</span><span class="sxs-lookup"><span data-stu-id="9b80b-142">Step 3 - Add a Service Worker</span></span>  

<span data-ttu-id="9b80b-143">サービスワーカーは、PWAs の主要なテクノロジであり、オフラインサポート、高度なキャッシュ、実行中のバックグラウンドタスクなどのシナリオを以前からネイティブアプリに限定することができます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-143">Service workers are the key technology behind PWAs, enabling scenarios like offline support, advanced caching, and running background tasks previously limited to native apps.</span></span>  

<span data-ttu-id="9b80b-144">サービスワーカーは、web アプリからネットワーク要求を傍受するバックグラウンドタスクです。</span><span class="sxs-lookup"><span data-stu-id="9b80b-144">Service workers are background tasks that intercept network requests from your web app.</span></span>  <span data-ttu-id="9b80b-145">ユーザーは、PWA が実行されていない場合でも、キャッシュからの要求されたリソースの提供、プッシュ通知の送信、バックグラウンドフェッチタスクの実行、バッジのアイコンの実行など、タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-145">They perform tasks, even when your PWA is not running, such as serving requested resources from a cache, sending push notifications, running background fetch tasks, badging icons, and so on.</span></span>  <span data-ttu-id="9b80b-146">サービスワーカーは、特別な JavaScript ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="9b80b-146">Service workers are defined in a special JavaScript file.</span></span>  <span data-ttu-id="9b80b-147">詳細については、「[サービスワーカー][MDNUsingServiceWorkers]と[サービスワーカー API][MDNServiceWorkerApi]の使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b80b-147">For more information, see [Using Service Workers][MDNUsingServiceWorkers] and [Service Worker API][MDNServiceWorkerApi].</span></span>  

<span data-ttu-id="9b80b-148">プロジェクトでサービスワーカーを構築するには、 [PWA ビルダー][PwaBuilderServiceWorker]から**キャッシュの最初のネットワーク**サービスワーカーレシピを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-148">To build a service worker in your project, use the **Cache-first network** service worker recipe from [PWA Builder][PwaBuilderServiceWorker].</span></span>  

1.  <span data-ttu-id="9b80b-149">[Pwabuilder.com/serviceworker][PwaBuilderServiceWorker]に移動して、[**キャッシュ-最初のネットワーク**サービス] ワーカーを選択し、[**ダウンロード**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-149">Navigate to [pwabuilder.com/serviceworker][PwaBuilderServiceWorker], select the **Cache-first network** service worker, and select the **Download** button.</span></span>  <span data-ttu-id="9b80b-150">ダウンロードしたファイルには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-150">The downloaded file contains the following files:</span></span>
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
    
1.  <span data-ttu-id="9b80b-151">ダウンロードしたファイルを `public` web アプリプロジェクトのフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9b80b-151">Copy the downloaded files to the `public` folder in your web app project.</span></span>  
    
1.  <span data-ttu-id="9b80b-152">VS コードで、 `/public/index.html` 次のコードスニペットを開いて、タグ内に追加し `<head>` ます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-152">In VS Code, open `/public/index.html` and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <script src="/pwabuilder-sw-register.js"></script>
    ```  
    
<span data-ttu-id="9b80b-153">これで、web アプリには、最初にキャッシュからのリソース、JS、CSS、HTML などのリソースを取得し、必要に応じてネットワークにフォールバックする、キャッシュ方式を使うサービスワーカーが用意されました。</span><span class="sxs-lookup"><span data-stu-id="9b80b-153">Your web app now has a service worker that uses the cache-first strategy, which fetches resources like images, JS, CSS, and HTML from the cache first, and falls back to the network as needed.</span></span>  

<span data-ttu-id="9b80b-154">次の手順を使用して、サービスワーカーが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-154">Use the following steps to confirm that your service worker runs.</span></span>  

1.  <span data-ttu-id="9b80b-155">を使用して web アプリに移動し `http://localhost:3000` ます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-155">Navigate to your web app using `http://localhost:3000`.</span></span>  <span data-ttu-id="9b80b-156">Web アプリを利用できない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-156">If your web app is not available, run the following command.</span></span>   
    
    ```shell
    npm start
    ```
    
1.  <span data-ttu-id="9b80b-157">Microsoft Edge で、 `F12` Microsoft Edge DevTools を選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-157">In Microsoft Edge, select `F12` to open the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="9b80b-158">[**アプリケーション**] を選択し**てから、サービスワーカー**を表示します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-158">Select **Application**, then **Service Workers** to view the service workers.</span></span>  <span data-ttu-id="9b80b-159">サービスワーカーが表示されない場合は、ページの更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9b80b-159">If you do not see the service worker, you may need to refresh the page.</span></span>  
     
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools サービスワーカーの概要":::
       <span data-ttu-id="9b80b-161">Microsoft Edge DevTools サービスワーカーの概要</span><span class="sxs-lookup"><span data-stu-id="9b80b-161">Microsoft Edge DevTools Service Worker overview</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="9b80b-162">**キャッシュストレージ**を展開してサービスワーカーキャッシュを表示し、[ **pwabuilder-precache**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-162">View the service worker cache by expanding **Cache Storage** and select **pwabuilder-precache**.</span></span>  <span data-ttu-id="9b80b-163">アプリのアイコン、アプリマニフェスト、CSS、JavaScript ファイルなど、サービスワーカーによってキャッシュされたすべてのリソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-163">You should see all the resources cached by the service worker, such as the app icon, app manifest, CSS and JavaScript files.</span></span>  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools の Service Worker キャッシュ":::
       <span data-ttu-id="9b80b-165">Microsoft Edge DevTools でのサービスワーカーキャッシュ (F12)</span><span class="sxs-lookup"><span data-stu-id="9b80b-165">Service Worker cache in Microsoft Edge DevTools (F12)</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="9b80b-166">PWA をオフラインアプリとして試してみてください。</span><span class="sxs-lookup"><span data-stu-id="9b80b-166">Try your PWA as an offline app.</span></span>  <span data-ttu-id="9b80b-167">Microsoft Edge DevTools \ ( `F12` \) で、[**ネットワーク**] を選択し、[**オンライン**状態] を [**オフライン**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-167">In Microsoft Edge DevTools \(`F12`\), choose **Network** then change the **Online** status to **Offline**.</span></span>  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="Microsoft Edge DevTools でアプリをオフラインモードに設定する":::
       <span data-ttu-id="9b80b-169">Microsoft Edge DevTools でアプリをオフラインモードに設定する</span><span class="sxs-lookup"><span data-stu-id="9b80b-169">Setting app to offline mode in Microsoft Edge DevTools</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="9b80b-170">アプリを最新の状態に更新すると、アプリのリソースがキャッシュから提供されるため、オフラインで作業していることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9b80b-170">Refresh your app and you should see it working offline by serving the resources of your app from the cache.</span></span>  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="オフラインで実行されている PWA":::
       <span data-ttu-id="9b80b-172">オフラインで実行されている PWA</span><span class="sxs-lookup"><span data-stu-id="9b80b-172">PWA running offline</span></span>
    :::image-end:::
    
## <span data-ttu-id="9b80b-173">PWA にプッシュ通知を追加する</span><span class="sxs-lookup"><span data-stu-id="9b80b-173">Add push notifications to your PWA</span></span>  

<span data-ttu-id="9b80b-174">次のタスクを実行して、プッシュ通知をサポートする PWAs を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-174">You may create PWAs that support push notifications by completing the following tasks.</span></span>  

1.  <span data-ttu-id="9b80b-175">[プッシュ API][MDNPushApi]を使用したメッセージサービスの購読</span><span class="sxs-lookup"><span data-stu-id="9b80b-175">Subscribe to a messaging service using the [Push API][MDNPushApi]</span></span>  
1.  <span data-ttu-id="9b80b-176">[通知 API][MDNNotificationsApi]を使用して、サービスからメッセージが受信されたときにトーストメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="9b80b-176">Display a toast messages when a message is received from the service using the [Notifications API][MDNNotificationsApi]</span></span>  

<span data-ttu-id="9b80b-177">サービスワーカーの場合と同様に、これらはブラウザー間で動作する標準ベースの Api であるため、このコードを1回記述するだけで、PWAs がサポートされているすべての場所で動作させることができます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-177">As with Service Workers, these are standards-based APIs that work across browsers, so you only have to write the code once for it to work everywhere that PWAs are supported.</span></span>  <span data-ttu-id="9b80b-178">サーバー上のさまざまなブラウザーへのプッシュメッセージの配信の詳細については、 [「Web-プッシュ][NPMWebPush]ソースライブラリ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b80b-178">For more information on delivering push messages to different browsers on your server, use the [Web-Push][NPMWebPush] open-source library.</span></span>  

<span data-ttu-id="9b80b-179">以下の手順は、Mozilla が提供する[Service Worker][ServiceWorkerCookbookPushRichDemo]の Web サイトの「プッシュリッチデモ」で採用されています。これには、他にも多くの便利な Web プッシュとサービス worker のレシピが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9b80b-179">The following steps have been adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which has a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="9b80b-180">手順 1-VAPID キーを生成する</span><span class="sxs-lookup"><span data-stu-id="9b80b-180">Step 1 - Generate VAPID keys</span></span>  

<span data-ttu-id="9b80b-181">プッシュ通知には、PWA クライアントにプッシュメッセージを送信するために、VAPID \ (自主的なアプリケーションサーバー Id) キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="9b80b-181">Push notifications require VAPID \(Voluntary Application Server Identification\) keys in order to send push messages to the PWA client.</span></span>  <span data-ttu-id="9b80b-182">オンラインで利用できる VAPID キージェネレーターはいくつかあります ( [vapidkeys.com][VapidkeysMain]など)。</span><span class="sxs-lookup"><span data-stu-id="9b80b-182">There are several VAPID key generators available online \(for example, [vapidkeys.com][VapidkeysMain]\).</span></span>  <span data-ttu-id="9b80b-183">生成後、公開キーと秘密キーを含む JSON オブジェクトを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b80b-183">After generation, you should get a JSON object containing a public and private key.</span></span>  <span data-ttu-id="9b80b-184">以降の手順に従ってキーを保存します。次のチュートリアルを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-184">Save the keys for subsequent steps in the following tutorial.</span></span>  <span data-ttu-id="9b80b-185">VAPID と WebPush のしくみの詳細については、「 [Mozilla のプッシュサービス経由で VAPID 識別された Web プッシュ通知を送信][MozillaServicesSendingVapidWebPushNotificationsPush]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b80b-185">For information on how VAPID and WebPush works, see [Sending VAPID identified WebPush Notifications via Mozilla's Push Service][MozillaServicesSendingVapidWebPushNotificationsPush].</span></span>  

### <span data-ttu-id="9b80b-186">手順 2-プッシュ通知への登録</span><span class="sxs-lookup"><span data-stu-id="9b80b-186">Step 2 - Subscribe to push notifications</span></span>  

<span data-ttu-id="9b80b-187">サービスワーカーは、PWA でプッシュイベントとトースト通知のやり取りを処理します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-187">Service workers handle push events and toast notification interactions in your PWA.</span></span>  <span data-ttu-id="9b80b-188">PWA をサーバープッシュ通知に登録するには、次の条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-188">To subscribe the PWA to server push notifications, ensure the following conditions are met.</span></span>  

*   <span data-ttu-id="9b80b-189">PWA がインストールされ、アクティブで登録されている</span><span class="sxs-lookup"><span data-stu-id="9b80b-189">Your PWA is installed, active and registered</span></span>  
*   <span data-ttu-id="9b80b-190">サブスクリプションタスクを実行するコードは、PWA のメイン UI スレッドにあります。</span><span class="sxs-lookup"><span data-stu-id="9b80b-190">Your code that performs the subscription task is on the main UI thread of the PWA</span></span>  
*   <span data-ttu-id="9b80b-191">ネットワーク接続がある場合</span><span class="sxs-lookup"><span data-stu-id="9b80b-191">You have network connectivity</span></span>  

<span data-ttu-id="9b80b-192">新しいプッシュサブスクリプションが作成される前に、Microsoft Edge は、ユーザーが通知を受信できるように PWA 権限を与えられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-192">Before a new push subscription is created, Microsoft Edge checks if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="9b80b-193">許可されていない場合は、ブラウザーからアクセス許可を求められます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-193">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="9b80b-194">アクセス許可が拒否された場合は、を例外として `registration.pushManager.subscribe` `DOMException` 処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b80b-194">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, which must be handled.</span></span>  <span data-ttu-id="9b80b-195">権限の管理について詳しくは、「 [Microsoft Edge でのプッシュ通知][WindowsBlogsWebNotificationsEdge]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9b80b-195">For more on permission management, see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="9b80b-196">ファイルで `pwabuilder-sw-register.js` 、次のコードスニペットを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-196">In your `pwabuilder-sw-register.js` file, append the following code snippet.</span></span>  

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

<span data-ttu-id="9b80b-197">詳細については、「 [Pushmanager][MDNPushManager]と[Web (プッシュ)][NPMWebPushUsage]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9b80b-197">For more information, see [PushManager][MDNPushManager] and [Web-Push][NPMWebPushUsage].</span></span>  

### <span data-ttu-id="9b80b-198">手順 3-プッシュ通知をリッスンする</span><span class="sxs-lookup"><span data-stu-id="9b80b-198">Step 3 - Listen for push notifications</span></span>  

<span data-ttu-id="9b80b-199">これでサブスクリプションが PWA で設定されたので、プッシュイベント (サーバーから送信) に応答するためのハンドラーをサービスワーカーに追加して、受信メッセージのデータを使ってトースト通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-199">Now that a subscription is set up in your PWA, add handlers to the service worker to respond to push events \(sent from the server\) to display toast notifications with the data of a received message.</span></span>  <span data-ttu-id="9b80b-200">次のいずれかのタスクを実行するには、クリックハンドラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b80b-200">You must add a click handler to perform the any of the following tasks.</span></span>  
*   <span data-ttu-id="9b80b-201">トースト通知を無視する</span><span class="sxs-lookup"><span data-stu-id="9b80b-201">dismiss the toast notification</span></span>  
*   <span data-ttu-id="9b80b-202">開いているウィンドウを開く、フォーカスする、または開く</span><span class="sxs-lookup"><span data-stu-id="9b80b-202">open, focus, or open and focus any open windows</span></span>  
*   <span data-ttu-id="9b80b-203">新しいウィンドウを開いてフォーカスを移動し、PWA クライアントページを表示する</span><span class="sxs-lookup"><span data-stu-id="9b80b-203">open and focus a new window to display a PWA client page</span></span>  

<span data-ttu-id="9b80b-204">ファイルで `pwabuilder-sw.js` 、次のハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-204">In your `pwabuilder-sw.js` file, add the following handlers.</span></span>  

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
    
    // This looks to see if the current notification is already open and focuses it.
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

### <span data-ttu-id="9b80b-205">手順 4-試してみる</span><span class="sxs-lookup"><span data-stu-id="9b80b-205">Step 4 - Try it out</span></span>  

<span data-ttu-id="9b80b-206">PWA でプッシュ通知をテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-206">Perform the following steps to test push notifications in your PWA.</span></span>  

1.  <span data-ttu-id="9b80b-207">PWA に移動 `http://localhost:3000` します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-207">Navigate to your PWA at `http://localhost:3000`.</span></span>  <span data-ttu-id="9b80b-208">サービスワーカーがアクティブになって PWA のプッシュ通知をサブスクライブしようとすると、Microsoft Edge で、PWA に通知を表示することを許可するように求められます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-208">When your service worker activates and attempts to subscribe your PWA to push notifications, Microsoft Edge prompts you to allow your PWA to show notifications.</span></span>  <span data-ttu-id="9b80b-209">[**許可**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-209">Select **Allow**.</span></span>  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="通知を有効にするためのアクセス許可ダイアログ":::
       <span data-ttu-id="9b80b-211">通知を有効にするためのアクセス許可ダイアログ</span><span class="sxs-lookup"><span data-stu-id="9b80b-211">Permission dialog for enabling notifications</span></span>
    :::image-end:::
    
    
1.  <span data-ttu-id="9b80b-212">サーバー側のプッシュ通知をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="9b80b-212">Simulate a server-side push notification.</span></span>  <span data-ttu-id="9b80b-213">使用しているブラウザーで PWA が開いたら `http://localhost:3000` 、を選択して `F12` devtools を開きます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-213">With your PWA opened at `http://localhost:3000` in your browser, select `F12` to open the DevTools.</span></span>  <span data-ttu-id="9b80b-214">[**アプリケーション**  >  **サービスワーカー**プッシュ] を選択し  >  **Push**て、PWA にテストプッシュ通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-214">Choose **Application** > **Service Worker** > **Push** to send a test push notification to your PWA.</span></span>  <span data-ttu-id="9b80b-215">プッシュ通知はタスクバーの近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-215">You should see a push notification appear near the taskbar.</span></span>  
    
    :::image type="complex" source="./media/devtools-push.png" alt-text="DevTools から通知をプッシュする":::
       <span data-ttu-id="9b80b-217">DevTools から通知をプッシュする</span><span class="sxs-lookup"><span data-stu-id="9b80b-217">Push a notification from DevTools</span></span>
    :::image-end:::
     
    <span data-ttu-id="9b80b-218">トースト通知を選択しない場合は、数秒後に表示されなくなり、Windows アクションセンターでキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="9b80b-218">If you do not select \(or activate\) a toast notification, it is dismissed after several seconds and queues up in your Windows Action Center.</span></span>  
    
    :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows アクションセンターでの通知":::
       <span data-ttu-id="9b80b-220">Windows アクションセンターでの通知</span><span class="sxs-lookup"><span data-stu-id="9b80b-220">Notifications in Windows Action Center</span></span>
    :::image-end:::
    
    
## <span data-ttu-id="9b80b-221">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9b80b-221">Next steps</span></span>  

<span data-ttu-id="9b80b-222">次に、現実世界での構築時に学習する追加のタスクを示します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-222">The following is a list of additional tasks to learn when building real-world PWAs:</span></span>  

*  <span data-ttu-id="9b80b-223">プッシュサブスクリプションの管理と保存</span><span class="sxs-lookup"><span data-stu-id="9b80b-223">Manage and store push subscriptions</span></span>  
*  <span data-ttu-id="9b80b-224">ペイロードデータを[暗号化][NPMWebPushEncrypt]する</span><span class="sxs-lookup"><span data-stu-id="9b80b-224">[Encrypt][NPMWebPushEncrypt] payload data</span></span>  
*  <span data-ttu-id="9b80b-225">レスポンシブ デザイン</span><span class="sxs-lookup"><span data-stu-id="9b80b-225">Responsive design</span></span>  
*  <span data-ttu-id="9b80b-226">ディープリンク</span><span class="sxs-lookup"><span data-stu-id="9b80b-226">Deep-linking</span></span>  
*  [<span data-ttu-id="9b80b-227">ブラウザ間のテスト</span><span class="sxs-lookup"><span data-stu-id="9b80b-227">Cross-browser testing</span></span>][BrowserStackTestEdgeBrowser]  
*  <span data-ttu-id="9b80b-228">[Webhint][Webhint]などのベストプラクティスを実装する</span><span class="sxs-lookup"><span data-stu-id="9b80b-228">Implement best practices such as [Webhint][Webhint]</span></span>  

## <span data-ttu-id="9b80b-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b80b-229">See also</span></span>  

*   <span data-ttu-id="9b80b-230">[MDN web ドキュメントのプログレッシブ Web アプリ][MDNProgressiveWebApps]。</span><span class="sxs-lookup"><span data-stu-id="9b80b-230">[Progressive Web Apps on MDN web docs][MDNProgressiveWebApps].</span></span>  
*   <span data-ttu-id="9b80b-231">[Web.config でのプログレッシブ Web アプリ][WebDevProgressiveWebApps]。</span><span class="sxs-lookup"><span data-stu-id="9b80b-231">[Progressive Web Apps on web.dev][WebDevProgressiveWebApps].</span></span>  
*   <span data-ttu-id="9b80b-232">[[プログレッシブ Web アプリとしてのハッカーニュースリーダー][HackerNewsProgressiveWebApps] ]: サンプル \ (ハッカーたち News READER) PWA を実装するためのさまざまなフレームワークとパフォーマンスパターンを比較します。</span><span class="sxs-lookup"><span data-stu-id="9b80b-232">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  

<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "Azure App Service に発行する-Visual Studio でノード .js と Express アプリを作成する |Microsoft ドキュメント"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントの作成 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio コード"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "エクスプレスアプリケーションジェネレーター |高速" 

[HackerNewsProgressiveWebApps]: https://hnpwa.com "プログレッシブ Web アプリとしてのハッカーニュースリーダー"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "プログレッシブ web アプリ \ (PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービスワーカーを使用する |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "VAPID を Mozilla のプッシュサービス経由で識別された Web プッシュ通知を送信しています。 |Mozilla サービス"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-プッシュ |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "暗号化 (userPublicKey、Userpublickey、payload、contentEncoding)-web-プッシュ |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用状況-web-プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "プログレッシブ Web アプリ"  

[PwaBuilder]: https://www.pwabuilder.com "PWA ビルダー"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービスワーカー |PWA ビルダー"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "充実したデモのプッシュ |ServiceWorker の料理"  

[VapidkeysMain]: https://vapidkeys.com "Secure VAPID Key Generator |VapidKeys" 

[Webhint]: https://sonarwhal.com "web ベストプラクティスのヒントエンジンの web ヒント"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "プログレッシブ Web アプリ |web.xml"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "プログレッシブエンハンスメント |Wikipedia"  
