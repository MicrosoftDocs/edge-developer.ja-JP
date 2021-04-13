---
description: Microsoft Edge for Web Apps の最新の実験的機能
title: 実験的な機能|プログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/09/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, 実験, プログレッシブ Web アプリ, Web アプリ, PWA, PWA
ms.openlocfilehash: 5ab2ab0a727d1eb52f61a01ea64b52bc1c09abce
ms.sourcegitcommit: f6a3ab7b13adf05dbe7a4bf65ee67c9b0f6fab95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11482158"
---
# <a name="experimental-features-in-progressive-web-apps-pwas"></a><span data-ttu-id="ebddd-104">プログレッシブ Web アプリ (PWA) の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="ebddd-104">Experimental features in Progressive Web Apps (PWAs)</span></span>  

<span data-ttu-id="ebddd-105">Microsoft Edge では、開発中の実験的な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-105">Microsoft Edge provides access to experimental features that are still in development.</span></span>  <span data-ttu-id="ebddd-106">各機能が準備完了かどうかを確認し、各機能をリリースする場合は、フィードバックを [テストして提供します](#providing-feedback-on-experimental-features)。</span><span class="sxs-lookup"><span data-stu-id="ebddd-106">To determine if each feature is ready and when to release each, test and [provide feedback](#providing-feedback-on-experimental-features).</span></span>  

<span data-ttu-id="ebddd-107">実験的な機能は、Microsoft Edge のすべてのチャネルで利用できますが、最新の実験的機能は Microsoft Edge Canary チャネルでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-107">Experimental features are available in all channels of Microsoft Edge, but the latest experimental features are only available in the Microsoft Edge Canary channel.</span></span>  

## <a name="turn-on-experimental-features"></a><span data-ttu-id="ebddd-108">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="ebddd-108">Turn on experimental features</span></span>  

<span data-ttu-id="ebddd-109">Microsoft Edge で \(or off\) 実験機能を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  
  
1.  <span data-ttu-id="ebddd-110">Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-110">Open Microsoft Edge.</span></span>   
    
    > [!NOTE]
    > <span data-ttu-id="ebddd-111">この記事に記載されている実験を含む Microsoft Edge バージョンを使用してください。</span><span class="sxs-lookup"><span data-stu-id="ebddd-111">Ensure you use a Microsoft Edge version that has the Experiment listed in this article.</span></span>  <span data-ttu-id="ebddd-112">[実験機能 [] に移動します](#features-that-are-available-to-test)。</span><span class="sxs-lookup"><span data-stu-id="ebddd-112">Navigate to [Experimental features](#features-that-are-available-to-test).</span></span>  
    
1.  <span data-ttu-id="ebddd-113">に移動します `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-113">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="ebddd-114">関連する実験に移動します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-114">Navigate to the relevant experiment.</span></span>  
1.  <span data-ttu-id="ebddd-115">実験の説明の横にあるドロップダウン メニューを選択し、[. `Enabled`</span><span class="sxs-lookup"><span data-stu-id="ebddd-115">Choose the dropdown menu next to the experiment description and choose `Enabled`.</span></span>  
    
    :::image type="complex" source="../media/turn-on-experimental-flag.png" alt-text="[有効] を選択して実験を有効にする" lightbox="../media/turn-on-experimental-flag.png":::
       <span data-ttu-id="ebddd-117">[ **有効] を** 選択して実験を有効にする</span><span class="sxs-lookup"><span data-stu-id="ebddd-117">Choose **Enabled** to turn on an experiment</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="ebddd-118">各実験には、通常、次の値を選択するドロップダウン メニューがあります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-118">Each experiment usually has a dropdown menu to choose the following values.</span></span>  <span data-ttu-id="ebddd-119">実験機能に実験用のエントリが含めなかった\*\*\*\* 場合は、コマンド ラインを使用してその機能を使用して Microsoft Edge を起動する手順が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-119">If an experimental feature doesn't have an entry on **Experiments**, instructions are provided to start Microsoft Edge with that feature using the command-line.</span></span>
    > 
    > *   `Default`  
    > *   `Disabled`  
    > *   `Enabled`  
    
1.  <span data-ttu-id="ebddd-120">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="ebddd-120">Restart Microsoft Edge.</span></span>  
    
### <a name="origin-trials"></a><span data-ttu-id="ebddd-121">元の試用版</span><span class="sxs-lookup"><span data-stu-id="ebddd-121">Origin Trials</span></span>  

<span data-ttu-id="ebddd-122">Microsoft Edge では、特定のドメインまたは Web サイトの機能をテストするためにオリジン試用版を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-122">Microsoft Edge sometimes uses origin trials to test features for specific domains or websites.</span></span>  <span data-ttu-id="ebddd-123">特定の機能を適用するには、Web サイトにオリジン試用版を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-123">You may want to use an origin trial for your website to apply a specific feature.</span></span>  <span data-ttu-id="ebddd-124">Web サイトの所有者の場合は、オリジン試用版に登録できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-124">If you're a website owner, you may enroll in an origin trial.</span></span>  <span data-ttu-id="ebddd-125">オリジン試用版は、Web サイトにアクセスする Microsoft Edge ユーザーの割合に機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-125">An origin trial provides features to a percentage of Microsoft Edge users who visit your website.</span></span>

<span data-ttu-id="ebddd-126">Origin Trials の詳細については [、「Microsoft Edge Origin Trials Developer Console」に移動します][MicrosoftDeveloperMicrosoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="ebddd-126">For more information about Origin Trials, navigate to [Microsoft Edge Origin Trials Developer Console][MicrosoftDeveloperMicrosoftEdgeOriginTrials].</span></span>  
    
> [!NOTE]
> <span data-ttu-id="ebddd-127">実験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-127">Experimental features are constantly updated and may cause performance issues.</span></span>  <span data-ttu-id="ebddd-128">実験機能をオフにする場合は、[実験[](#turn-on-experimental-features)機能を有効にする] に移動し、実験に移動し、[] を選択します `Disabled` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-128">To turn off an experimental feature, navigate to [Turn on experimental features](#turn-on-experimental-features), navigate to the experiment, and then choose `Disabled`.</span></span>  

## <a name="features-that-are-available-to-test"></a><span data-ttu-id="ebddd-129">テストに使用できる機能</span><span class="sxs-lookup"><span data-stu-id="ebddd-129">Features that are available to test</span></span>  

<span data-ttu-id="ebddd-130">次の一覧では、Microsoft Edge でテストおよび検証できる新しい実験的な Web アプリ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-130">The following list describes the new experimental web app features that are available to test and validate on Microsoft Edge.</span></span>  

| <span data-ttu-id="ebddd-131">機能</span><span class="sxs-lookup"><span data-stu-id="ebddd-131">Feature</span></span> | <span data-ttu-id="ebddd-132">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="ebddd-132">Microsoft Edge version</span></span> | <span data-ttu-id="ebddd-133">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="ebddd-133">Platform</span></span> |  
|:--- |:--- |:--- |  
| [<span data-ttu-id="ebddd-134">URI プロトコルの処理</span><span class="sxs-lookup"><span data-stu-id="ebddd-134">URI Protocol Handling</span></span>](#uri-protocol-handling) | <span data-ttu-id="ebddd-135">91 以降</span><span class="sxs-lookup"><span data-stu-id="ebddd-135">91 or later</span></span> | <span data-ttu-id="ebddd-136">Windows</span><span class="sxs-lookup"><span data-stu-id="ebddd-136">Windows</span></span> |    
| [<span data-ttu-id="ebddd-137">URL リンクの処理</span><span class="sxs-lookup"><span data-stu-id="ebddd-137">URL Link Handling</span></span>](#url-link-handling) | <span data-ttu-id="ebddd-138">91 以降</span><span class="sxs-lookup"><span data-stu-id="ebddd-138">91 or later</span></span> | <span data-ttu-id="ebddd-139">Windows</span><span class="sxs-lookup"><span data-stu-id="ebddd-139">Windows</span></span>|
| [<span data-ttu-id="ebddd-140">デスクトップ アプリのウィンドウ コントロール オーバーレイ</span><span class="sxs-lookup"><span data-stu-id="ebddd-140">Window Controls Overlay for Desktop Apps</span></span>](#window-controls-overlay-for-installed-desktop-web-apps) | <span data-ttu-id="ebddd-141">91 以降</span><span class="sxs-lookup"><span data-stu-id="ebddd-141">91 or later</span></span> | <span data-ttu-id="ebddd-142">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ebddd-142">Windows 10</span></span>|   
| [<span data-ttu-id="ebddd-143">OS ログインで実行する</span><span class="sxs-lookup"><span data-stu-id="ebddd-143">Run on OS Login</span></span>](#run-on-os-login) | <span data-ttu-id="ebddd-144">88 以降</span><span class="sxs-lookup"><span data-stu-id="ebddd-144">88 or later</span></span> | <span data-ttu-id="ebddd-145">すべて</span><span class="sxs-lookup"><span data-stu-id="ebddd-145">All</span></span> |  
| [<span data-ttu-id="ebddd-146">ショートカット</span><span class="sxs-lookup"><span data-stu-id="ebddd-146">Shortcuts</span></span>](#shortcuts) | <span data-ttu-id="ebddd-147">87 以降</span><span class="sxs-lookup"><span data-stu-id="ebddd-147">87 or later</span></span> | <span data-ttu-id="ebddd-148">すべて</span><span class="sxs-lookup"><span data-stu-id="ebddd-148">All</span></span> |  
| [<span data-ttu-id="ebddd-149">ファイル処理</span><span class="sxs-lookup"><span data-stu-id="ebddd-149">File Handling</span></span>](#file-handling) | <span data-ttu-id="ebddd-150">83 以降</span><span class="sxs-lookup"><span data-stu-id="ebddd-150">83 or later</span></span> | <span data-ttu-id="ebddd-151">すべてのデスクトップ</span><span class="sxs-lookup"><span data-stu-id="ebddd-151">All Desktop</span></span> |  


## <a name="uri-protocol-handling"></a><span data-ttu-id="ebddd-152">URI プロトコルの処理</span><span class="sxs-lookup"><span data-stu-id="ebddd-152">URI Protocol Handling</span></span>  

<span data-ttu-id="ebddd-153">HTTP または FTP プロトコルを使用して Web ページや Web コンテンツへのリンクを定義するために、統一されたリソース識別子 \(URI\) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-153">A uniform resource identifier \(URI\) may be used to define more than just links to webpages and web content using the HTTP or FTP protocol.</span></span>  <span data-ttu-id="ebddd-154">URI を使用して、スキーマにコード化するリンクを記述できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-154">URIs may be used to describe links to anything that you codify into a schema.</span></span>  <span data-ttu-id="ebddd-155">たとえば、プロトコルを使用して電子メール リンクを記述し、オペレーティング システム \(OS\) またはブラウザーが、そのプロトコルを処理する Web ページまたはアプリ `mailto://` を決定します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-155">For example, the `mailto://` protocol is used to describe an email link and the operating system \(OS\) or browser decides which webpage or app should handle that protocol.</span></span>  

<span data-ttu-id="ebddd-156">既存のブラウザー ベースのサポートの詳細については [、Web ベースのプロトコル ハンドラーに移動します][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]。</span><span class="sxs-lookup"><span data-stu-id="ebddd-156">For more information about existing browser-based support, navigate to [Web-based protocol handlers][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers].</span></span>  

<span data-ttu-id="ebddd-157">この機能を使用すると、次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-157">This feature allows you to complete the following actions.</span></span>  

*   <span data-ttu-id="ebddd-158">Web アプリのマニフェストを使用して PWA をホスト OS に登録する</span><span class="sxs-lookup"><span data-stu-id="ebddd-158">Register your PWA with the host OS using the manifest of your web app</span></span>
*   <span data-ttu-id="ebddd-159">PWA が特定の URI プロトコルを処理すると宣言する</span><span class="sxs-lookup"><span data-stu-id="ebddd-159">Declare that a PWA handles a specific URI protocol</span></span>  
     
<span data-ttu-id="ebddd-160">プロトコル ハンドラーとして PWA を登録した後、ブラウザーやネイティブ アプリなどの特定のスキームを使用してハイパーリンクを選択すると、登録済みの PWA は OS によってアクティブ化され `mailto://` 、URI を受信します。 `web+music://`</span><span class="sxs-lookup"><span data-stu-id="ebddd-160">After you register a PWA as a protocol handler, when a user chooses a hyperlink with a specific scheme such as `mailto://` or `web+music://` from a browser or a native app, the registered PWA is activated by the OS and receives the URI.</span></span>  

<span data-ttu-id="ebddd-161">この機能では、2 つのフィールドを指定する必要がある配列に配列を含める Web アプリ マニフェスト `protocol_handlers` を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-161">This feature requires you to update the web app manifest to include a `protocol_handlers` array, in the array you need to specify two fields:</span></span>  

*   `protocol`<span data-ttu-id="ebddd-162">: 要求を処理するプロトコル (たとえば `mailto` `web+jngl` 、または.</span><span class="sxs-lookup"><span data-stu-id="ebddd-162">:  The protocol to handle the request, for example `mailto` or `web+jngl`.</span></span>  
*   `url`<span data-ttu-id="ebddd-163">: プロトコルを処理するアプリ スコープ内の HTTPS URI。</span><span class="sxs-lookup"><span data-stu-id="ebddd-163">: The HTTPS URI in the app scope that handles the protocol.</span></span>  <span data-ttu-id="ebddd-164">今後、プロトコル ハンドラー スキームで始まる URI は、トークンを置き換える予定 `%s` です。</span><span class="sxs-lookup"><span data-stu-id="ebddd-164">In the future, the URI starting with the protocol handlers scheme is planned to replace the `%s` token.</span></span>  
    
<span data-ttu-id="ebddd-165">登録するプロトコルをサポートするためにマニフェストを更新します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-165">Update your manifest to support the protocol that you want to register.</span></span>  <span data-ttu-id="ebddd-166">この機能を有効にした後、Microsoft Edge は次のアクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-166">After you turn on this feature, Microsoft Edge completes the following actions.</span></span>  

1.  <span data-ttu-id="ebddd-167">マニフェストの変更を検出する</span><span class="sxs-lookup"><span data-stu-id="ebddd-167">Detects changes in the manifest</span></span>  
1.  <span data-ttu-id="ebddd-168">プロトコルのアプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-168">Registers the app for the protocol</span></span>  
    
<span data-ttu-id="ebddd-169">複数のアプリがプロトコルを登録すると、ユーザーにプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-169">If more than one app registers a protocol, the user is presented with a prompt.</span></span>  <span data-ttu-id="ebddd-170">ユーザーは、OS またはブラウザーによって表示されるリストから適切なアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-170">The user chooses the appropriate app from the list presented by the OS or browser.</span></span>  

<span data-ttu-id="ebddd-171">Windows の Microsoft Edge でプロトコル処理を[](#turn-on-experimental-features)プレビューするには、[実験的な機能を有効にする] に移動し、[デスクトップ Web アプリのプロトコル ハンドラーのサポート **] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="ebddd-171">To preview protocol handling in Microsoft Edge on Windows, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop Web Apps support Protocol Handlers**.</span></span>  

<span data-ttu-id="ebddd-172">プロトコル ハンドラーでオリジン試用版が実行されている場合の詳細については [、「Register for Web App Protocol Handler Registration」に移動します][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]。</span><span class="sxs-lookup"><span data-stu-id="ebddd-172">For more information about origin trial is running for protocol handlers, navigate to [Register for Web App Protocol Handler Registration][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration].</span></span>  

### <a name="example-manifest"></a><span data-ttu-id="ebddd-173">マニフェストの例</span><span class="sxs-lookup"><span data-stu-id="ebddd-173">Example Manifest</span></span>

<span data-ttu-id="ebddd-174">この例では、Web アプリ マニフェストは、プロトコルを処理するためにアプリを登録する必要があります `web+jngl` `web+jnglstore` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-174">In this example, a web app manifest declares that the app should be registered to handle the protocols `web+jngl` and `web+jnglstore`.</span></span>

```json
{
  "name": "Jungle",
  "description": "A plant encyclopedia",
  "protocol_handlers": [
    {
      "protocol": "web+jngl",
      "url": "/lookup?type=%s"
    },
    {
      "protocol": "web+jnglstore",
      "url": "/shop?for=%s"
    }
  ],
  "icons": [
    {
      "src": "images/icons-192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
  ],
  "background_color": "#007f87",

  "display": "standalone",
  "start_url": "/",
}
```  
 
## <a name="url-link-handling"></a><span data-ttu-id="ebddd-175">URL リンクの処理</span><span class="sxs-lookup"><span data-stu-id="ebddd-175">URL Link Handling</span></span>  

<span data-ttu-id="ebddd-176">統一リソース ロケーター \(URL\) は URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="ebddd-176">A uniform resource locator \(URL\) is a type of URI.</span></span>  <span data-ttu-id="ebddd-177">プログレッシブ Web Apps \(PWAs\) が https URI のハンドラーとして登録するときに、より魅力的なエクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-177">Create a more engaging experience when Progressive Web Apps \(PWAs\) register as handlers for https URIs.</span></span>  <span data-ttu-id="ebddd-178">関連付けられた URI がアクティブ化されると、PWA が起動を要求する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-178">PWAs may request to launch when associated URIs are activated.</span></span>  <span data-ttu-id="ebddd-179">たとえば、ユーザーが電子メール メッセージからニュース ストーリーへのリンクを選択した場合です。</span><span class="sxs-lookup"><span data-stu-id="ebddd-179">For example, if a user chooses a link to a news story from an email message.</span></span>  <span data-ttu-id="ebddd-180">リンクのアクティブ化を処理するために、ニュース 記事を表示する関連付けられた PWA が自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-180">An associated PWA to display news stories is automatically launched to handle the activation of the link.</span></span>  

<span data-ttu-id="ebddd-181">この機能を使用すると、Web アプリ マニフェストを使用してブラウザーに PWA を登録し、ブラウザーが特定のリンクを処理すると宣言できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-181">This feature allows you to register a PWA with the browser using the web app manifest and declare that the browser handles specific links.</span></span>  <span data-ttu-id="ebddd-182">ブラウザーに PWA を登録するには、省略可能なメンバーを `url_handlers` マニフェスト ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-182">To register a PWA with the browser, add the optional `url_handlers` member to the manifest file.</span></span>  <span data-ttu-id="ebddd-183">メンバー `url_handlers` は、アプリが処理する `object[]` URI の原点をグループ分けするメンバーです。</span><span class="sxs-lookup"><span data-stu-id="ebddd-183">The `url_handlers` member is an `object[]` that groups the origins of URIs that the app wishes to handle.</span></span>  

<span data-ttu-id="ebddd-184">リンク処理は、原点にある JSON ファイルを使用してブラウザー `web-app-origin-association` によって検証されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-184">Link handling is validated by the browser using a `web-app-origin-association` JSON file that is located on the origin.</span></span>  <span data-ttu-id="ebddd-185">オリジン ファイルは、オリジンの含まれるパスまたは除外されたパスをさらに微調整します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-185">The origin file further fine-tunes the included or excluded paths at the origin.</span></span>  <span data-ttu-id="ebddd-186">URL ハンドラーのテストに関する詳細な手順については、URL [ハンドラーとして PWA に移動します][GithubWicgPwaUrlHandlerBlobMainExplainerMd]。</span><span class="sxs-lookup"><span data-stu-id="ebddd-186">For detailed instructions about testing the URL handler, navigate to [PWAs as URL Handlers][GithubWicgPwaUrlHandlerBlobMainExplainerMd].</span></span>  

<span data-ttu-id="ebddd-187">Windows の Microsoft Edge で URL リンク[](#turn-on-experimental-features)処理をプレビューするには、[実験的な機能を有効にする] に移動し、[デスクトップ PWA URL の処理 **] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="ebddd-187">To preview URL link handling in Microsoft Edge on Windows, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop PWA URL  Handling**.</span></span>  

### <a name="example-of-the-url_handlers-in-the-manifest"></a><span data-ttu-id="ebddd-188">マニフェスト内のurl_handlersの例</span><span class="sxs-lookup"><span data-stu-id="ebddd-188">Example of the url_handlers in the manifest</span></span>  

<span data-ttu-id="ebddd-189">次のコード スニペットは、メンバーを持つ Web アプリ マニフェストの例 `url_handlers` です。</span><span class="sxs-lookup"><span data-stu-id="ebddd-189">The following code snippet is an example web app manifest with the `url_handlers` member.</span></span>  

```json 
{
    "name": "Contoso Business App",
    "display": "standalone",
    "icons": [
        {
            "src": "images/icons-144.png",
            "type": "image/png",
            "sizes": "144x144"
        }
    ],
    "capture_links": "existing_client_event",
    "url_handlers" : [
        {
            "origin": "https://contoso.com"
        },
        {
            "origin": "https://conto.so"
        },
        {
            "origin": "https://*.contoso.com"
        }
    ]
}
```  

<span data-ttu-id="ebddd-190">PWA は、URI が元の文字列の 1 つと一致する場合に URL 処理の URI と一致し、ブラウザーは、このアプリがそのような URI を処理することに基が同意したと検証します `url_handlers` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-190">A PWA matches a URI for URL handling if the URI matches one of the origin strings in `url_handlers` and the browser validates that the origin agrees to allow this app handle such a URI.</span></span>  

<span data-ttu-id="ebddd-191">メンバーには、要求元 PWA の範囲と他の無関係な起点を含むオ `url_handlers` リジンが含まれる。</span><span class="sxs-lookup"><span data-stu-id="ebddd-191">The `url_handlers` member contains an origin that encompasses the scope and other unrelated origins of the requesting PWA.</span></span>  <span data-ttu-id="ebddd-192">URI を要求する PWA と同じスコープまたはドメインに制限しない場合、同じコンテンツに異なるドメイン名を使用できますが、同じ PWA で処理できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-192">Not restricting URIs to the same scope or domain as the requesting PWA allows you to use different domain names for the same content but handle them with the same PWA.</span></span>  

#### <a name="wildcard-matching"></a><span data-ttu-id="ebddd-193">ワイルドカードの一致</span><span class="sxs-lookup"><span data-stu-id="ebddd-193">Wildcard matching</span></span>  

<span data-ttu-id="ebddd-194">1 つ以上の文字に `*` 一致するには、ワイルドカード文字 \( \) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-194">Use the wildcard character \(`*`\) to match one or more characters.</span></span>  

<span data-ttu-id="ebddd-195">異なるサブドメインに一致するために、メンバーのオリジン文字列でワイルドカード `url_handlers` プレフィックスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-195">A wildcard prefix is used in origin strings of the `url_handlers` member to match for different subdomains.</span></span>  <span data-ttu-id="ebddd-196">プレフィックスは、この使用法 `*.` 用である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-196">The prefix must be `*.` for this usage.</span></span>  <span data-ttu-id="ebddd-197">ワイルドカード `https` プレフィックスを使用する場合、スキームは想定されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-197">The `https` scheme is assumed when you use a wildcard prefix.</span></span>  

<span data-ttu-id="ebddd-198">たとえば、メンバーの `url_handlers` 値は一致する値に `*.contoso.com` 設定 `tenant.contoso.com` されますが、 `www.tenant.contoso.com` 一致しません `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-198">For example, the `url_handlers` member value is set to `*.contoso.com` matches `tenant.contoso.com` and `www.tenant.contoso.com`, but doesn't match `contoso.com`.</span></span>  

## <a name="window-controls-overlay-for-installed-desktop-web-apps"></a><span data-ttu-id="ebddd-199">インストールされているデスクトップ Web アプリのウィンドウ コントロール オーバーレイ</span><span class="sxs-lookup"><span data-stu-id="ebddd-199">Window Controls Overlay for installed desktop web apps</span></span>  

<span data-ttu-id="ebddd-200">デスクトップにインストールされた Web アプリ用のネイティブ アプリのようなイマーシブ タイトル バーを作成するには **、Window Controls Overlay** 機能によって次のアクションが完了します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-200">To create an immersive title bar like a native app for your desktop installed web app, the **Window Controls Overlay** feature completes the following actions.</span></span>  
    
1.  <span data-ttu-id="ebddd-201">システム予約のタイトル バーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-201">Removes the system reserved title bar.</span></span>  <span data-ttu-id="ebddd-202">通常、クライアント フレームの幅にまたがっています。</span><span class="sxs-lookup"><span data-stu-id="ebddd-202">It usually spans the width of the client frame.</span></span>  
1.  <span data-ttu-id="ebddd-203">オーバーレイに置き換える。</span><span class="sxs-lookup"><span data-stu-id="ebddd-203">Replaces it with an overlay.</span></span>  <span data-ttu-id="ebddd-204">このコントロールには、ユーザーがウィンドウ自体を制御するために必要な重要なシステムに必要なウィンドウ コントロールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebddd-204">It contains just the critical system required window controls necessary for a user to control the window itself.</span></span>  
    
<span data-ttu-id="ebddd-205">オーバーレイを提供すると、Web クライアント領域全体を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-205">After it provides an overlay, the entire web client area is available for you to use.</span></span>  <span data-ttu-id="ebddd-206">この機能には、マニフェスト更新プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebddd-206">This feature includes a manifest update.</span></span>  <span data-ttu-id="ebddd-207">コンテンツの配置に役立つオーバーレイのサイズと位置を決定する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-207">It provides ways for you to determine the size and position of the overlay to help you arrange content.</span></span>  

<span data-ttu-id="ebddd-208">Microsoft Edge for Windows 10 のウィンドウ コントロール オーバーレイ[](#turn-on-experimental-features)をプレビューするには、[実験機能を有効にする] に移動し、[デスクトップ PWA ウィンドウ コントロール オーバーレイ]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ebddd-208">To preview the Window Controls Overlays in Microsoft Edge for Windows 10, navigate to [Turn on experimental features](#turn-on-experimental-features) and navigate to **Desktop PWA Window Controls Overlay**.</span></span>   

### <a name="examples-of-title-bar-area-customization"></a><span data-ttu-id="ebddd-209">タイトル バー領域のカスタマイズの例</span><span class="sxs-lookup"><span data-stu-id="ebddd-209">Examples of title bar area customization</span></span>  

<span data-ttu-id="ebddd-210">この機能は、ネイティブ アプリでタイトル バーをカスタマイズする機能に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="ebddd-210">This feature is based on the ability in native apps to customize the title bar.</span></span>  <span data-ttu-id="ebddd-211">重要なアプリのアクションや通知用にタイトル バーをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-211">You may customize a title bar for important app actions or notifications.</span></span>  <span data-ttu-id="ebddd-212">Microsoft Visual Studioおよび Microsoft Teams の次の例を確認します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-212">Review the following examples for Microsoft Visual Studio Code and Microsoft Teams.</span></span>  

#### <a name="visual-studio-code"></a><span data-ttu-id="ebddd-213">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ebddd-213">Visual Studio Code</span></span>  

<span data-ttu-id="ebddd-214">Microsoft Visual Studio コードは、複数のデスクトップ プラットフォームに組み込む、電子で構築された一般的なエディターです。</span><span class="sxs-lookup"><span data-stu-id="ebddd-214">Microsoft Visual Studio Code is a popular editor built on Electron that ships on multiple desktop platforms.</span></span>  

<span data-ttu-id="ebddd-215">次の使用例は、Visual Studio コードがタイトル バーを使用して使用可能な画面の不動産を最大化して、現在のファイル名とトップ レベルのメニュー構造をタイトル バーに含める方法を表示します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-215">The following example displays how Visual Studio Code uses the title bar to maximize available screen real estate to include the current file name and top-level menu structure in the title bar.</span></span>  

:::image type="complex" source="../media/visual-studio-code-title-customization.png" alt-text="コード内のタイトル バー Visual Studio例" lightbox="../media/visual-studio-code-title-customization.png":::
   <span data-ttu-id="ebddd-217">コード内のタイトル バー Visual Studio例</span><span class="sxs-lookup"><span data-stu-id="ebddd-217">An example of the title bar in Visual Studio Code</span></span>  
:::image-end:::  

#### <a name="microsoft-teams"></a><span data-ttu-id="ebddd-218">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ebddd-218">Microsoft Teams</span></span>  

<span data-ttu-id="ebddd-219">Workplace のコラボレーションとコミュニケーション ツール Microsoft Teams も、電子を使用して構築され、複数のデスクトップ プラットフォームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-219">Workplace collaboration and communication tool Microsoft Teams is also built with Electron and available on multiple desktop platforms.</span></span>  <span data-ttu-id="ebddd-220">次の例では、Microsoft Teams が表示 `back` `forward` され、ナビゲーション ボタン、検索ボックス、およびユーザー プロファイル コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-220">In the following example, Microsoft Teams displays `back` and `forward` navigation buttons, a search box, and user profile controls.</span></span>  

:::image type="complex" source="../media/teams-title-customization.png" alt-text="Microsoft Teams のタイトル バーの例" lightbox="../media/teams-title-customization.png":::
   <span data-ttu-id="ebddd-222">Microsoft Teams のタイトル バーの例</span><span class="sxs-lookup"><span data-stu-id="ebddd-222">An example of the title bar in Microsoft Teams</span></span>  
:::image-end:::  

### <a name="overlay-window-controls-on-a-frameless-window"></a><span data-ttu-id="ebddd-223">フレームレス ウィンドウのオーバーレイ ウィンドウ コントロール</span><span class="sxs-lookup"><span data-stu-id="ebddd-223">Overlay Window Controls on a Frameless Window</span></span>  

<span data-ttu-id="ebddd-224">Web コンテンツのアドレス指定可能領域を最大化するために、ブラウザーはフレームレス ウィンドウを作成します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-224">To maximize the addressable area for web content, the browser creates a frameless window.</span></span>  <span data-ttu-id="ebddd-225">フレームレス ウィンドウは、オーバーレイとして提供されるウィンドウ コントロールを除き、すべてのブラウザー UI を削除します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-225">A frameless window removes all browser UI, except for the window controls provided as an overlay.</span></span>  <span data-ttu-id="ebddd-226">ウィンドウ コントロールのオーバーレイを使用すると、ユーザーはアプリを最小化、最大化、復元、閉じ続けます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-226">The window controls overlay allows users to still minimize, maximize, restore, and close the app.</span></span>  <span data-ttu-id="ebddd-227">また、Web アプリ メニューを使用して関連するブラウザー コントロールにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-227">It also provides access to relevant browser controls using the web app menu.</span></span>  <span data-ttu-id="ebddd-228">クロム ベースのブラウザーの場合、オーバーレイには次のコントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-228">For Chromium-based browsers, the overlay includes the following controls.</span></span>  

*   <span data-ttu-id="ebddd-229">ドラッグ可能な領域の各ウィンドウ コントロール ボタンの幅と高さが同じ</span><span class="sxs-lookup"><span data-stu-id="ebddd-229">A draggable region the same width and height of each of the window control buttons</span></span>  
*   <span data-ttu-id="ebddd-230">[ **設定] および [その他** ] \(...\) ボタン</span><span class="sxs-lookup"><span data-stu-id="ebddd-230">The **Settings and more** \(...\) button</span></span>  
*   <span data-ttu-id="ebddd-231">ウィンドウ コントロール ボタンを最小化、最大化、復元、閉じる</span><span class="sxs-lookup"><span data-stu-id="ebddd-231">The window control buttons minimize, maximize, restore, and close</span></span>  
    
<span data-ttu-id="ebddd-232">前に示したコントロールに加え、オーバーレイに表示される UI は、次のシナリオで動的にサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-232">Besides the previously listed controls, the UI displayed in the overlay is dynamically resized in the following scenarios.</span></span>  

*   <span data-ttu-id="ebddd-233">インストールされている Web アプリが起動すると、Web ページの原点が [設定]\*\*\*\* メニューの左側に表示され、さらに \(...\) メニューが数秒表示され、その後消えます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-233">When an installed web app is launched, the origin of the webpage displays to the left of the **Settings and more** \(...\) menu for a few seconds and then disappears.</span></span>  
*   <span data-ttu-id="ebddd-234">ユーザーが [設定] メニューおよび **[その** 他の \(...\)] メニューを使用して拡張機能を操作すると、拡張機能のアイコンが 3 ドット メニューの左側のオーバーレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-234">If a user interacts with an extension using the **Settings and more** \(...\) menu, the icon of the extension displays in the overlay to the left of the three-dot menu.</span></span>  <span data-ttu-id="ebddd-235">拡張機能ダイアログを終了すると、アイコンはオーバーレイから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-235">After you exit any extension dialog, the icon is removed from the overlay.</span></span>  
    
| <span data-ttu-id="ebddd-236">言語の方向</span><span class="sxs-lookup"><span data-stu-id="ebddd-236">Language direction</span></span> | <span data-ttu-id="ebddd-237">オーバーレイの場所</span><span class="sxs-lookup"><span data-stu-id="ebddd-237">Overlay location</span></span> | <span data-ttu-id="ebddd-238">詳細</span><span class="sxs-lookup"><span data-stu-id="ebddd-238">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="ebddd-239">左から右 \(LTR\)</span><span class="sxs-lookup"><span data-stu-id="ebddd-239">Left-to-right \(LTR\)</span></span> | <span data-ttu-id="ebddd-240">クライアント領域の左上</span><span class="sxs-lookup"><span data-stu-id="ebddd-240">Upper left of the client area</span></span> | <span data-ttu-id="ebddd-241">コントロールが反転する</span><span class="sxs-lookup"><span data-stu-id="ebddd-241">The controls are flipped</span></span> |  
| <span data-ttu-id="ebddd-242">右から左 \(RTL\)</span><span class="sxs-lookup"><span data-stu-id="ebddd-242">Right-to-left \(RTL\)</span></span> | <span data-ttu-id="ebddd-243">クライアント領域の右上隅</span><span class="sxs-lookup"><span data-stu-id="ebddd-243">Upper right corner of the client area</span></span> |  |  

> [!IMPORTANT]
> <span data-ttu-id="ebddd-244">オーバーレイは常に Web コンテンツの Z インデックスの上に表示され、Web コンテンツにフローせずにすべてのユーザー入力を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="ebddd-244">The overlay is always on top of the Z-index of the web content and accepts all user input without flowing it through to the web content.</span></span>  

### <a name="working-around-the-window-controls-overlay"></a><span data-ttu-id="ebddd-245">ウィンドウ コントロール オーバーレイの操作</span><span class="sxs-lookup"><span data-stu-id="ebddd-245">Working around the Window Controls Overlay</span></span>  

<span data-ttu-id="ebddd-246">Web コンテンツは、コントロール オーバーレイの予約領域を認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-246">Your web content must be aware of the reserved area for the controls overlay.</span></span>  <span data-ttu-id="ebddd-247">予約領域がユーザーの操作を期待しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-247">Ensure the reserved area doesn't expect user interaction.</span></span>  <span data-ttu-id="ebddd-248">境界を設定する四角形とコントロール オーバーレイの表示をブラウザーに照会します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-248">Query the browser for the bounding rectangle and visibility of the controls overlay.</span></span>  <span data-ttu-id="ebddd-249">この情報は、JavaScript API と CSS 環境変数を使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-249">The information is provided to you through JavaScript APIs and CSS environment variables.</span></span>  

#### <a name="javascript-apis"></a><span data-ttu-id="ebddd-250">JavaScript API</span><span class="sxs-lookup"><span data-stu-id="ebddd-250">JavaScript APIs</span></span>  

<span data-ttu-id="ebddd-251">プロパティの `windowControlsOverlay` 新しいオブジェクト `window.navigator` を使用すると、コントロール オーバーレイの境界の四角形に対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-251">A new `windowControlsOverlay` object on the `window.navigator` property allows you to query the bounding rectangle of the controls overlay.</span></span>  

<span data-ttu-id="ebddd-252">オブジェクト `windowControlsOverlay` には、次の 2 つのオブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-252">The `windowControlsOverlay` object has the following two objects.</span></span>  

*   `getBoundingClientRect()` <span data-ttu-id="ebddd-253">オブジェクトを返 `DOMRect` します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-253">returns a `DOMRect` object.</span></span>  <span data-ttu-id="ebddd-254">オブジェクト `DOMRect` は、ウィンドウ コントロールオーバーレイの下の領域を表します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-254">The `DOMRect` object represents the area under the window controls overlay.</span></span>  
*   `visible` <span data-ttu-id="ebddd-255">は、コントロールのオーバーレイがレンダリングおよび表示されるブール値です。</span><span class="sxs-lookup"><span data-stu-id="ebddd-255">is a boolean that indicates that the controls overlay is rendered and displayed.</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="ebddd-256">プライバシー上の理由から `windowControlsOverlay` 、Web コンテンツ内の `iframe` 要素にアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="ebddd-256">For privacy reasons, the `windowControlsOverlay` isn't accessible to `iframe` elements in the web content.</span></span>  

<span data-ttu-id="ebddd-257">オーバーレイのサイズが変更されるたびに、オブジェクト上でイベントが実行され、コンテンツ レイアウトの再計算をクライアント `geometrychange` `navigator.windowControlsOverlay` に通知します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-257">Whenever the overlay is resized, a `geometrychange` event runs on the `navigator.windowControlsOverlay` object to notify the client to recalculate the content layout.</span></span>  <span data-ttu-id="ebddd-258">再計算されたコンテンツ レイアウトは、オーバーレイの新しい境界四角形に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-258">The recalculated content layout is based on the new bounding rectangle of the overlay.</span></span>  

#### <a name="css-environment-variables"></a><span data-ttu-id="ebddd-259">CSS 環境変数</span><span class="sxs-lookup"><span data-stu-id="ebddd-259">CSS Environment Variables</span></span>  

<span data-ttu-id="ebddd-260">JavaScript API の他に、CSS を使用してコントロール オーバーレイの外接する四角形にクエリを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-260">Besides the JavaScript API, you may use CSS to query the bounding rectangle of the controls overlay.</span></span>  <span data-ttu-id="ebddd-261">クエリを実行するには、次の 4 つの新しい CSS 環境変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-261">Use the following four new CSS environment variables to accomplish to query.</span></span>  

*   `titlebar-area-x`  
*   `titlebar-area-y`  
*   `titlebar-area-width`  
*   `titlebar-area-height`  
    
### <a name="define-draggable-regions-in-web-content"></a><span data-ttu-id="ebddd-262">Web コンテンツでドラッグ可能な領域を定義する</span><span class="sxs-lookup"><span data-stu-id="ebddd-262">Define Draggable Regions in Web Content</span></span>  

<span data-ttu-id="ebddd-263">ユーザーは、ウィンドウの上部領域をつかんでドラッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-263">Users expect to grab and drag the upper region of a window.</span></span>  <span data-ttu-id="ebddd-264">期待に合わせて、Web コンテンツの特定の部分をドラッグ可能として宣言します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-264">To accommodate the expectation, declare specific parts of the web content as draggable.</span></span>  
<span data-ttu-id="ebddd-265">要素をドラッグ可能に指定するには、WebKit 独自の `-webkit-app-region` CSS プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-265">To specify an element is draggable, use the WebKit-proprietary `-webkit-app-region` CSS property.</span></span>  <span data-ttu-id="ebddd-266">CSS 作業グループは、プロパティの標準化に取り組 `app-region` み続けます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-266">The CSS working group continues efforts to standardize the `app-region` property.</span></span>  

### <a name="custom-title-bar-example"></a><span data-ttu-id="ebddd-267">カスタム タイトル バーの例</span><span class="sxs-lookup"><span data-stu-id="ebddd-267">Custom title bar example</span></span>  

<span data-ttu-id="ebddd-268">次の使用例は、新しい機能がカスタム タイトル バーを持つ Web アプリを作成する方法を表示します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-268">The following example displays how the new features create a web app with a custom title bar.</span></span>  

:::image type="complex" source="../media/teams-title-customization-example.png" alt-text="Microsoft Teams のカスタム タイトル バーの例" lightbox="../media/teams-title-customization-example.png":::
   <span data-ttu-id="ebddd-270">Microsoft Teams のカスタム タイトル バーの例</span><span class="sxs-lookup"><span data-stu-id="ebddd-270">Example of a custom title bar in Microsoft Teams</span></span>  
:::image-end:::  

#### <a name="manifestwebmanifest"></a><span data-ttu-id="ebddd-271">manifest.webmanifest</span><span class="sxs-lookup"><span data-stu-id="ebddd-271">manifest.webmanifest</span></span>  

<span data-ttu-id="ebddd-272">マニフェストで、配列を `display_override` に設定します  `window-controls-overlay` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-272">In the manifest, set `display_override` array to  `window-controls-overlay`.</span></span>  <span data-ttu-id="ebddd-273">タイトル バー `theme_color` の色の選択に設定します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-273">Set the `theme_color` to your choice of color for the title bar.</span></span>  <span data-ttu-id="ebddd-274">サポートされていない場合に、表示モードを適切なフォールバック `display_override` `window-controls-overlay` に設定します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-274">Set the display mode to an appropriate fallback for when either `display_override` or `window-controls-overlay` isn't supported.</span></span>  

<span data-ttu-id="ebddd-275">次のコード スニペットには、推奨されるマニフェスト更新プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebddd-275">The following code snippet includes the recommended manifest updates.</span></span>  

```json
{
  "name": "Example PWA",
  "display": "standalone",
  "display_override": [ 
    "window-controls-overlay" 
  ],
  "theme_color": "#254B85"
}
```  

### <a name="indexhtml"></a><span data-ttu-id="ebddd-276">index.html</span><span class="sxs-lookup"><span data-stu-id="ebddd-276">index.html</span></span>  

<span data-ttu-id="ebddd-277">次の ID は、Web ページの 2 つの主要な領域を表します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-277">The following IDs represent the two main regions of the webpage.</span></span>  

*   `titleBarContainer`  
*   `mainContent`  
    
<span data-ttu-id="ebddd-278">`div`ID を持つ `titleBar` 要素がに設定され `draggable` 、検索ボックス `input` の子要素がに設定されます `nonDraggable` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-278">The `div` element with the `titleBar` ID is set to `draggable` and the search box `input` child element is set to `nonDraggable`.</span></span>  

```html
<div id="titleBar" class=" draggable">
    <span class="draggable">Example PWA</span>
    <input class="nonDraggable" type="text" placeholder="Search"></input>
</div>
```

<span data-ttu-id="ebddd-279">ID を `div` 持つ `titleBarContainer` 要素では `div` 、ID を持 `titleBar` つ要素はタイトル バー領域の表示部分を表します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-279">In the `div` element with the `titleBarContainer` ID, the `div` with the `titleBar` ID represents the visible portion of the title bar area.</span></span>  

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Example PWA</title>
    <link rel="stylesheet" href="style.css">
    <link rel="manifest" href="./manifest.webmanifest">
  </head>
  <body>
    <div id="titleBarContainer">
      <div id="titleBar" class=" draggable">
        <span class="draggable">Example PWA</span>
        <input class="nonDraggable" type="text" placeholder="Search"></input>
      </div>
    </div>
    <div id="mainContent"><!-- The rest of the webpage --></div>
  </body>
</html>
```  

### <a name="stylecss"></a><span data-ttu-id="ebddd-280">style.css</span><span class="sxs-lookup"><span data-stu-id="ebddd-280">style.css</span></span>  

<span data-ttu-id="ebddd-281">ドラッグ可能領域とドラッグ不可領域は、 を使用して `-webkit-app-region: drag` 設定されます `-webkit-app-region: no-drag` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-281">The draggable and non-draggable regions are set using `-webkit-app-region: drag` and `-webkit-app-region: no-drag`.</span></span>  

```css
.draggable {
    app-region: drag;
    /* Pre-fix app-region during standardization process */
    -webkit-app-region: drag;
}

.nonDraggable {
    app-region: no-drag;
    /* Pre-fix app-region during standardization process */
    -webkit-app-region: no-drag;
}
```  

<span data-ttu-id="ebddd-282">要素の場合、タイトル バーがウィンドウの端に達するまで余白 `body` `0` が設定されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-282">For the `body` element, margins are set to `0` to ensure the title bar reaches to the edges of the window.</span></span>  

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
}
```  

<span data-ttu-id="ebddd-283">ID は、コンテナーを Web ページの上部に接続する 、 `titleBarContainer` `position: absolute` `top` `titlebar-area-inset-top` を使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-283">The `titleBarContainer` ID uses `position: absolute` and sets the `top` to `titlebar-area-inset-top`, which attaches the container to the top of the webpage.</span></span>  <span data-ttu-id="ebddd-284">ウィンドウ `bottom` コントロールのオーバーレイが表示されない場合は、に設定され、戻 `titlebar-area-inset-bottom` `100% - var(--fallback-title-bar-height)` ります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-284">The `bottom` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-title-bar-height)` if the window controls overlay isn't visible.</span></span>  <span data-ttu-id="ebddd-285">ID の背景色は `titleBarContainer` 、 と同じです `theme_color` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-285">The background color of the `titleBarContainer` ID is the same as the `theme_color`.</span></span>  <span data-ttu-id="ebddd-286">幅は 、要素が Web ページの幅を塗りつぶし、隣接する外観で表示されているときにオーバーレイの下 `100%` `div` を流れるので、に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-286">The width is set to `100%`, so that the `div` element fills the width of the webpage and flows under the overlay when it's visible for a contiguous appearance.</span></span>  

```css
#titleBarContainer {
    position: absolute;
    top: env(titlebar-area-y, 0);
    bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    width: 100%;
    background-color:#254B85;
}
```  

<span data-ttu-id="ebddd-287">ID `titleBar` も使用 `position: absolute` し `top: titlebar-area-inset-top` 、ウィンドウの上部に添付します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-287">The `titleBar` ID also uses `position: absolute` and `top: titlebar-area-inset-top` to attaches it to the top of the window.</span></span>  <span data-ttu-id="ebddd-288">既定では、ウィンドウの全幅が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-288">By default, it consumes the full width of the window.</span></span>  <span data-ttu-id="ebddd-289">エッジ `left` と `right` エッジはそれぞれに設定され、両方とも値が設定されていない `titlebar-area-inset-left` `titlebar-area-inset-right` `0` 場合に戻されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-289">The `left` and `right` edges are set to `titlebar-area-inset-left` and `titlebar-area-inset-right` respectively, both fall back to `0` when the values aren't set.</span></span>  <span data-ttu-id="ebddd-290">また、代わりに使用されるウィンドウをドラッグしようとして、要素内のテキストが強調表示 `user-select: none` されるのを防ぐ設定 `div` も行います。</span><span class="sxs-lookup"><span data-stu-id="ebddd-290">It also sets `user-select: none` to prevent any attempts to drag the window consumed instead it highlights text in the `div` element.</span></span>  

```css
#titleBar {
    position: absolute;
    top: 0;
    display: flex;
    user-select: none;
    height: 100%;
    left: env(titlebar-area-x, 0);
    right: env(titlebar-area-width, 0);
    color: #FFFFFF;
    font-weight: bold;
    text-align: center;
}

#titleBar > span {
    margin: auto;
    padding: 0px 16px 0px 16px;
}

#titleBar > input {
    flex: 1;
    margin: 8px;
    border-radius: 5px;
    border: none;
    padding: 8px;
}
```

<span data-ttu-id="ebddd-291">ID のコンテナーも固定され、Web ページの下部 `mainContent` `position: absolute` に添付されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-291">The container for the `mainContent` ID is also fixed in place with `position: absolute` and is attached to the bottom of the webpage.</span></span>  <span data-ttu-id="ebddd-292">に `height` 設定され、タイトル バーの下の残りの領域を埋めるに `titlebar-area-inset-bottom` `100% - var(--fallback-titlebar-height)` 戻ります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-292">The `height` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-titlebar-height)` to fill the remaining space below the title bar.</span></span>  <span data-ttu-id="ebddd-293">コンテナー内 `overflow-y: scroll` でコンテンツを垂直方向にスクロールできる設定です。</span><span class="sxs-lookup"><span data-stu-id="ebddd-293">It sets `overflow-y: scroll` to allow the contents to scroll vertically in the container.</span></span>  

```css
#mainContent {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    height: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    overflow-y: scroll;
}
```

<span data-ttu-id="ebddd-294">ブラウザーがウィンドウ コントロールオーバーレイをサポートしない場合は、タイトル バーの既定の高さを設定するために CSS 変数が追加されます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-294">For cases where the browser doesn't support the window controls overlay, a CSS variable is added to set a default height for the title bar.</span></span>  <span data-ttu-id="ebddd-295">最初は、クライアント領域全体を埋める境界と ID が設定され、オーバーレイがサポートされていない場合は変更 `titleBarContainer` `mainContent` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-295">The bounds of the `titleBarContainer` and `mainContent` IDs are initially set to fill the entire client area, and you don't need to change it if the overlay isn't supported.</span></span>  

<span data-ttu-id="ebddd-296">次のコード スニペットには、すべての推奨される CSS 更新プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebddd-296">The following code snippet includes all the recommended CSS updates.</span></span>

```css
:root {
  --fallback-title-bar-height: 40px;
}

.draggable {
  app-region: drag;
  /* Pre-fix app-region during standardization process */
  -webkit-app-region: drag;
}

.nonDraggable {
  app-region: no-drag;
  /* Pre-fix app-region during standardization process */
  -webkit-app-region: no-drag;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  margin: 0;
}

#titleBarContainer {
  position: absolute;
  top: env(titlebar-area-y, 0);
  bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
  width: 100%;
  background-color:#254B85;
}

#titleBar {
  position: absolute;
  top: 0;
  display: flex;
  user-select: none;
  height: 100%;
  left: env(titlebar-area-x, 0);
  right: env(titlebar-area-width, 0);
  color: #FFFFFF;
  font-weight: bold;
  text-align: center;
}

#titleBar > span {
  margin: auto;
  padding: 0px 16px 0px 16px;
}

#titleBar > input {
  flex: 1;
  margin: 8px;
  border-radius: 5px;
  border: none;
  padding: 8px;
}

#mainContent {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
  overflow-y: scroll;
}
```  

## <a name="run-on-os-login"></a><span data-ttu-id="ebddd-297">[OS ログイン時に実行]</span><span class="sxs-lookup"><span data-stu-id="ebddd-297">Run On OS Login</span></span>  

<span data-ttu-id="ebddd-298">この機能を使用すると、ユーザーが Microsoft Windows にログインするときに自動的に起動するアプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-298">This feature allows you to configure your app to automatically launch when the user logs into Microsoft Windows.</span></span>  <span data-ttu-id="ebddd-299">いくつかのクラスのアプリは、この機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-299">Several classes of apps take advantage of the capability.</span></span>  <span data-ttu-id="ebddd-300">アプリのクラスには、メール、チャット、監視ダッシュボード、リアルタイムデータ表示アプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-300">The classes of apps include email, chat, monitoring dashboard, and real-time data display apps.</span></span>  <span data-ttu-id="ebddd-301">この機能を使用すると、ユーザーが OS にログインするとすぐにアプリに参加できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-301">The capability allows a user to engage with the apps as soon as the user logs into the OS.</span></span>  <span data-ttu-id="ebddd-302">この機能は、手動で起動するのと同じ方法で PWA を自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-302">This feature automatically starts the PWA the same way it's launched manually.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ebddd-303">**[OS ログインで実行] は** 強力 [な機能です][GithubW3cPermissionsPowerfulFeature]。</span><span class="sxs-lookup"><span data-stu-id="ebddd-303">**Run on OS Login** is a [powerful feature][GithubW3cPermissionsPowerfulFeature].</span></span>  <span data-ttu-id="ebddd-304">ユーザーは、インストールされている Web アプリの機能を有効にするかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-304">Users should decide whether to turn on the capability for the installed web app.</span></span>  

### <a name="turn-on-run-on-os-login"></a><span data-ttu-id="ebddd-305">[OS ログイン時に実行] をオンにする</span><span class="sxs-lookup"><span data-stu-id="ebddd-305">Turn on Run On OS Login</span></span>  

<span data-ttu-id="ebddd-306">PWA の**Run On OS Login**機能をプレビュー[](#turn-on-experimental-features)するには、[実験的な機能を有効にする] に移動し、OS ログインでデスクトップ**PWA を実行します**。</span><span class="sxs-lookup"><span data-stu-id="ebddd-306">To preview the **Run On OS Login** capabilities for your PWA, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop PWAs run on OS login**.</span></span>  

:::image type="complex" source="../media/desktop-pwas-run-on-os-login-flag.png" alt-text="OS Login 実験で実行するデスクトップ PWA を有効にする" lightbox="../media/desktop-pwas-run-on-os-login-flag.png":::
   <span data-ttu-id="ebddd-308">OS ログイン実験 **でデスクトップ PWA の実行を有効** にする</span><span class="sxs-lookup"><span data-stu-id="ebddd-308">Turn on the **Desktop PWAs run on OS login** experiment</span></span>  
:::image-end:::  

### <a name="turn-on-the-feature-for-the-installed-web-app"></a><span data-ttu-id="ebddd-309">インストールされている Web アプリの機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="ebddd-309">Turn on the feature for the installed web app</span></span>  

<span data-ttu-id="ebddd-310">インストールされている `Start app when you sign in` PWA の機能を有効にするには、</span><span class="sxs-lookup"><span data-stu-id="ebddd-310">To turn on the `Start app when you sign in` feature for an installed PWA,</span></span> 

1.  <span data-ttu-id="ebddd-311">Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-311">Open Microsoft Edge.</span></span>   
1.  <span data-ttu-id="ebddd-312">に移動します `edge://apps` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-312">Navigate to `edge://apps`.</span></span>  
1.  <span data-ttu-id="ebddd-313">アプリにカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="ebddd-313">Hover on your app.</span></span>  
1.  <span data-ttu-id="ebddd-314">コンテキスト メニュー \(右クリック\) を開き、サインイン時に [アプリの起動 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ebddd-314">Open the contextual menu \(right-click\) and then choose **Start app when you sign in**.</span></span>  
    
    :::image type="complex" source="../media/turn-on-run-on-os-login-flag.png" alt-text="Microsoft Edge の機能にサインインするときに、コンテキスト メニューを使用してスタート アプリを有効にする" lightbox="../media/turn-on-run-on-os-login-flag.png":::
       <span data-ttu-id="ebddd-316">Microsoft Edge の機能にサインインするときに、コンテキスト メニューを使用してスタート **アプリを** 有効にする</span><span class="sxs-lookup"><span data-stu-id="ebddd-316">Use the contextual menu to turn on the **Start app when you sign in** feature in Microsoft Edge</span></span>  
    :::image-end:::  
    
## <a name="shortcuts"></a><span data-ttu-id="ebddd-317">ショートカット</span><span class="sxs-lookup"><span data-stu-id="ebddd-317">Shortcuts</span></span>  

`Shortcuts` <span data-ttu-id="ebddd-318">はマニフェスト ファイルの新しいメンバーです。</span><span class="sxs-lookup"><span data-stu-id="ebddd-318">is a new member of the manifest file.</span></span>  <span data-ttu-id="ebddd-319">これにより、Web アプリ内のパーツ、キー Web ページ、またはアクションへのリンクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-319">It allows you to define links to parts, key webpages, or actions in your web app.</span></span>  <span data-ttu-id="ebddd-320">Microsoft Windows は、ジャンプリスト **として統合します**。</span><span class="sxs-lookup"><span data-stu-id="ebddd-320">Microsoft Windows integrates it as **Jumplists**.</span></span>  <span data-ttu-id="ebddd-321">**ジャンプリストは、** 次のいずれかの UI 要素で表示されるポップアップ メニューを定義し、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-321">**Jumplists** define popup menus that appear when you on one of the following UI elements and open a contextual menu \(right-click\).</span></span>  

*   <span data-ttu-id="ebddd-322">スタート メニューのタイル</span><span class="sxs-lookup"><span data-stu-id="ebddd-322">A tile on the Start Menu</span></span>  
*   <span data-ttu-id="ebddd-323">タスク バーのアイコン</span><span class="sxs-lookup"><span data-stu-id="ebddd-323">An icon on the Taskbar</span></span>  
    
<span data-ttu-id="ebddd-324">ユーザーがショートカットを呼び出すと、ユーザーはショートカットのメンバーによって指定された `url` アドレスに移動します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-324">When a user invokes a shortcut, the user navigates to the address specified by the `url` member of the shortcut.</span></span>  
  
:::image type="complex" source="../media/jumplists-on-windows-10.png" alt-text="Windows 10 のジャンプリストの例" lightbox="../media/jumplists-on-windows-10.png":::
   <span data-ttu-id="ebddd-326">Windows 10 **のジャンプリスト** の例</span><span class="sxs-lookup"><span data-stu-id="ebddd-326">An example of **Jumplists** on Windows 10</span></span>  
:::image-end:::  

### <a name="shortcuts-in-the-manifest-file"></a><span data-ttu-id="ebddd-327">マニフェスト ファイルのショートカット</span><span class="sxs-lookup"><span data-stu-id="ebddd-327">Shortcuts in the Manifest file</span></span>  

```json
"shortcuts" : [
  {
    "name": "Today's agenda",
    "url": "/today",
    "description": "List of events planned for today"
  },
  {
    "name": "New event",
    "url": "/create/event"
  },
  {
    "name": "New reminder",
    "url": "/create/reminder"
  }
]
```  

#### <a name="properties-of-shortcuts"></a><span data-ttu-id="ebddd-328">ショートカットのプロパティ</span><span class="sxs-lookup"><span data-stu-id="ebddd-328">Properties of shortcuts</span></span>  

<span data-ttu-id="ebddd-329">次のプロパティは、各ショートカットを定義します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-329">The following properties define each shortcut.</span></span>  

| <span data-ttu-id="ebddd-330">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ebddd-330">Property</span></span> | <span data-ttu-id="ebddd-331">詳細</span><span class="sxs-lookup"><span data-stu-id="ebddd-331">Details</span></span> |  
|:--- |:--- |  
| `name` | <span data-ttu-id="ebddd-332">**Jumplists**またはコンテキスト メニューでユーザーに表示される文字列。</span><span class="sxs-lookup"><span data-stu-id="ebddd-332">A string that is displayed to the user on **Jumplists** or the contextual menu.</span></span> |  
| `short_name` | <span data-ttu-id="ebddd-333">ショートカットの完全な名前を表示する領域が不足している場合に表示される文字列。</span><span class="sxs-lookup"><span data-stu-id="ebddd-333">A string that is displayed when insufficient space exists to display the full name of the shortcut.</span></span> |  
| `description` | <span data-ttu-id="ebddd-334">ショートカットの目的を説明する文字列。</span><span class="sxs-lookup"><span data-stu-id="ebddd-334">A string that describes the purpose of the shortcut.</span></span>  <span data-ttu-id="ebddd-335">支援技術によってアクセスされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-335">It may be accessed by assistive technology.</span></span> |  
| `url` | <span data-ttu-id="ebddd-336">ショートカットがアクティブ化されると開く Web アプリの URI。</span><span class="sxs-lookup"><span data-stu-id="ebddd-336">The URI in the web app that opens when the shortcut is activated.</span></span> |  
| `icons` | <span data-ttu-id="ebddd-337">ショートカットを表す一連のアイコン。</span><span class="sxs-lookup"><span data-stu-id="ebddd-337">A set of icons that represents the shortcut.</span></span> |  

## <a name="file-handling"></a><span data-ttu-id="ebddd-338">ファイル処理</span><span class="sxs-lookup"><span data-stu-id="ebddd-338">File Handling</span></span>  

<span data-ttu-id="ebddd-339">ファイルの種類ハンドラーとして登録する機能は、実験段階です。</span><span class="sxs-lookup"><span data-stu-id="ebddd-339">The ability to register as a file type handler is in the experimentation phase.</span></span>  <span data-ttu-id="ebddd-340">マニフェスト エントリでアプリが処理するファイルの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ebddd-340">You may specify the file types that your app handles in a manifest entry.</span></span>  <span data-ttu-id="ebddd-341">インストール中に、ユーザーのホスト OS は、アプリをリストされたファイルの種類のファイル ハンドラーとして登録します。</span><span class="sxs-lookup"><span data-stu-id="ebddd-341">During installation, the user's host OS registers your app as a file handler for the listed file types.</span></span>  <span data-ttu-id="ebddd-342">アプリのスタートアップ コードに機能が存在し、その機能が `launchQueue` ファイルを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebddd-342">Ensure the existence of the feature `launchQueue` in your apps startup code and that it handles the file.</span></span>  

<span data-ttu-id="ebddd-343">クロム ベースのブラウザーでは、この機能のテストと整形を行っています。</span><span class="sxs-lookup"><span data-stu-id="ebddd-343">Chromium-based browsers are testing and shaping this feature.</span></span>  <span data-ttu-id="ebddd-344">コード例を含む詳細については、「Web アプリケーションをファイル ハンドラー [に設定する」に移動します][WebDevFileHandling]。</span><span class="sxs-lookup"><span data-stu-id="ebddd-344">For more information including code examples, navigate to [Let web applications be file handlers][WebDevFileHandling].</span></span>  

<span data-ttu-id="ebddd-345">Microsoft Edge for Windows 10 でファイル処理[](#turn-on-experimental-features)をプレビューするには、[実験的な機能を有効にする] に移動し、[ファイル処理**API] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="ebddd-345">To preview file handling in Microsoft Edge for Windows 10, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **File Handling API**.</span></span>  
    
## <a name="providing-feedback-on-experimental-features"></a><span data-ttu-id="ebddd-346">実験的な機能に関するフィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="ebddd-346">Providing feedback on experimental features</span></span>  

<span data-ttu-id="ebddd-347">Microsoft Edge Web アプリの実験に関するフィードバックを提供する。</span><span class="sxs-lookup"><span data-stu-id="ebddd-347">To provide feedback on Microsoft Edge web app experiments.</span></span>  

*   <span data-ttu-id="ebddd-348">[設定] および [ **その他]** \( \) を使用してフィードバックを送信 `...` >フィードバックを **Microsoft に送信します**。</span><span class="sxs-lookup"><span data-stu-id="ebddd-348">Send your feedback using **Settings and More** \(`...`\) > **Send Feedback to Microsoft**.</span></span>  
*   <span data-ttu-id="ebddd-349">を選択します `Alt` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="ebddd-349">Select `Alt`+`Shift`+`I`.</span></span>  
    
:::image type="complex" source="../media/send-feedback-from-progressive-web-app.png" alt-text="PWA からフィードバックを送信する" lightbox="../media/send-feedback-from-progressive-web-app.png":::
   <span data-ttu-id="ebddd-351">PWA からフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="ebddd-351">Send Feedback from your PWA</span></span>  
:::image-end:::  

<!-- links -->  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[MicrosoftDeveloperMicrosoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Origin Trials |Microsoft Edge 開発者"  
[MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]: https://developer.microsoft.com/microsoft-edge/origin-trials/web-app-protocol-handler-registration/registration "Web アプリ プロトコル ハンドラー登録の登録|Microsoft 開発者"  

[MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]: https://developer.mozilla.org/docs/Web/API/Navigator/registerProtocolHandler/Web-based_protocol_handlers "Web ベースのプロトコル ハンドラー|MDN"  

[GithubW3cPermissionsPowerfulFeature]: https://w3c.github.io/permissions#powerful-feature "強力な機能 - アクセス許可|GitHub"  

[GithubWicgPwaUrlHandlerBlobMainExplainerMd]: https://github.com/WICG/pwa-url-handler/blob/main/explainer.md "URL ハンドラーとしての PWA |GitHub"  

[WebDevFileHandling]: https://web.dev/file-handling "Web アプリケーションをファイル ハンドラーに|web.dev"  
