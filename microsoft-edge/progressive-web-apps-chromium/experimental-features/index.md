---
description: Microsoft Edge for Web Apps の最新の実験的機能
title: 実験的な機能|プログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, 実験, プログレッシブ Web アプリ, Web アプリ, PWA, PWA
ms.openlocfilehash: 587797bc8577f1c1aaca42394eecb997d21e9955
ms.sourcegitcommit: f605e4e27fed88aca286f2ae236e27f9a396b517
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474975"
---
# <a name="experimental-features-in-progressive-web-apps-pwas"></a><span data-ttu-id="a514b-104">プログレッシブ Web アプリ (PWA) の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="a514b-104">Experimental features in Progressive Web Apps (PWAs)</span></span>  

<span data-ttu-id="a514b-105">Microsoft Edge では、開発中の実験的な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a514b-105">Microsoft Edge provides access to experimental features that are still in development.</span></span>  <span data-ttu-id="a514b-106">各機能が準備完了かどうかを確認し、各機能をリリースする場合は、フィードバックを [テストして提供します](#providing-feedback-on-experimental-features)。</span><span class="sxs-lookup"><span data-stu-id="a514b-106">To determine if each feature is ready and when to release each, test and [provide feedback](#providing-feedback-on-experimental-features).</span></span>  

<span data-ttu-id="a514b-107">実験的な機能は、Microsoft Edge のすべてのチャネルで利用できますが、最新の実験的機能は Microsoft Edge Canary チャネルでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-107">Experimental features are available in all channels of Microsoft Edge, but the latest experimental features are only available in the Microsoft Edge Canary channel.</span></span>  

## <a name="turn-on-experimental-features"></a><span data-ttu-id="a514b-108">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="a514b-108">Turn on experimental features</span></span>  

<span data-ttu-id="a514b-109">Microsoft Edge で \(or off\) 実験機能を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a514b-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  
  
1.  <span data-ttu-id="a514b-110">Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="a514b-110">Open Microsoft Edge.</span></span>   
    
    > [!NOTE]
    > <span data-ttu-id="a514b-111">この記事に記載されている実験を含む Microsoft Edge バージョンを使用してください。</span><span class="sxs-lookup"><span data-stu-id="a514b-111">Ensure you use a Microsoft Edge version that has the Experiment listed in this article.</span></span>  <span data-ttu-id="a514b-112">[実験機能 [] に移動します](#features-that-are-available-to-test)。</span><span class="sxs-lookup"><span data-stu-id="a514b-112">Navigate to [Experimental features](#features-that-are-available-to-test).</span></span>  
    
1.  <span data-ttu-id="a514b-113">に移動します `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="a514b-113">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="a514b-114">関連する実験に移動します。</span><span class="sxs-lookup"><span data-stu-id="a514b-114">Navigate to the relevant experiment.</span></span>  
1.  <span data-ttu-id="a514b-115">実験の説明の横にあるドロップダウン メニューを選択し、[. `Enabled`</span><span class="sxs-lookup"><span data-stu-id="a514b-115">Choose the dropdown menu next to the experiment description and choose `Enabled`.</span></span>  
    
    :::image type="complex" source="../media/turn-on-experimental-flag.png" alt-text="[有効] を選択して実験を有効にする" lightbox="../media/turn-on-experimental-flag.png":::
       <span data-ttu-id="a514b-117">[ **有効] を** 選択して実験を有効にする</span><span class="sxs-lookup"><span data-stu-id="a514b-117">Choose **Enabled** to turn on an experiment</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="a514b-118">各実験には、通常、次の値を選択するドロップダウン メニューがあります。</span><span class="sxs-lookup"><span data-stu-id="a514b-118">Each experiment usually has a dropdown menu to choose the following values.</span></span>  <span data-ttu-id="a514b-119">実験機能に実験用のエントリが含めなかった\*\*\*\* 場合は、コマンド ラインを使用してその機能を使用して Microsoft Edge を起動する手順が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a514b-119">If an experimental feature doesn't have an entry on **Experiments**, instructions are provided to start Microsoft Edge with that feature using the command-line.</span></span>
    > 
    > *   `Default`  
    > *   `Disabled`  
    > *   `Enabled`  
    
1.  <span data-ttu-id="a514b-120">[Microsoft Edge を再起動]。</span><span class="sxs-lookup"><span data-stu-id="a514b-120">Restart Microsoft Edge.</span></span>  
    
### <a name="origin-trials"></a><span data-ttu-id="a514b-121">元の試用版</span><span class="sxs-lookup"><span data-stu-id="a514b-121">Origin Trials</span></span>  

<span data-ttu-id="a514b-122">Microsoft Edge では、特定のドメインまたは Web サイトの機能をテストするためにオリジン試用版を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a514b-122">Microsoft Edge sometimes uses origin trials to test features for specific domains or websites.</span></span>  <span data-ttu-id="a514b-123">特定の機能を適用するには、Web サイトにオリジン試用版を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-123">You may want to use an origin trial for your website to apply a specific feature.</span></span>  <span data-ttu-id="a514b-124">Web サイトの所有者の場合は、オリジン試用版に登録できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-124">If you're a website owner, you may enroll in an origin trial.</span></span>  <span data-ttu-id="a514b-125">オリジン試用版は、Web サイトにアクセスする Microsoft Edge ユーザーの割合に機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a514b-125">An origin trial provides features to a percentage of Microsoft Edge users who visit your website.</span></span>

<span data-ttu-id="a514b-126">Origin Trials の詳細については [、「Microsoft Edge Origin Trials Developer Console」に移動します][MicrosoftDeveloperMicrosoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="a514b-126">For more information about Origin Trials, navigate to [Microsoft Edge Origin Trials Developer Console][MicrosoftDeveloperMicrosoftEdgeOriginTrials].</span></span>  
    
> [!NOTE]
> <span data-ttu-id="a514b-127">実験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a514b-127">Experimental features are constantly updated and may cause performance issues.</span></span>  <span data-ttu-id="a514b-128">実験機能をオフにする場合は、[実験[](#turn-on-experimental-features)機能を有効にする] に移動し、実験に移動し、[] を選択します `Disabled` 。</span><span class="sxs-lookup"><span data-stu-id="a514b-128">To turn off an experimental feature, navigate to [Turn on experimental features](#turn-on-experimental-features), navigate to the experiment, and then choose `Disabled`.</span></span>  

## <a name="features-that-are-available-to-test"></a><span data-ttu-id="a514b-129">テストに使用できる機能</span><span class="sxs-lookup"><span data-stu-id="a514b-129">Features that are available to test</span></span>  

<span data-ttu-id="a514b-130">次の一覧では、Microsoft Edge でテストおよび検証できる新しい実験的な Web アプリ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a514b-130">The following list describes the new experimental web app features that are available to test and validate on Microsoft Edge.</span></span>  

| <span data-ttu-id="a514b-131">機能</span><span class="sxs-lookup"><span data-stu-id="a514b-131">Feature</span></span> | <span data-ttu-id="a514b-132">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="a514b-132">Microsoft Edge version</span></span> | <span data-ttu-id="a514b-133">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="a514b-133">Platform</span></span> |  
|:--- |:--- |:--- |  
| [<span data-ttu-id="a514b-134">URI プロトコルの処理</span><span class="sxs-lookup"><span data-stu-id="a514b-134">URI Protocol Handling</span></span>](#uri-protocol-handling) | <span data-ttu-id="a514b-135">91 以降</span><span class="sxs-lookup"><span data-stu-id="a514b-135">91 or later</span></span> | <span data-ttu-id="a514b-136">Windows</span><span class="sxs-lookup"><span data-stu-id="a514b-136">Windows</span></span> |    
| [<span data-ttu-id="a514b-137">URL リンクの処理</span><span class="sxs-lookup"><span data-stu-id="a514b-137">URL Link Handling</span></span>](#url-link-handling) | <span data-ttu-id="a514b-138">91 以降</span><span class="sxs-lookup"><span data-stu-id="a514b-138">91 or later</span></span> | <span data-ttu-id="a514b-139">Windows</span><span class="sxs-lookup"><span data-stu-id="a514b-139">Windows</span></span>|  
| [<span data-ttu-id="a514b-140">OS ログインで実行する</span><span class="sxs-lookup"><span data-stu-id="a514b-140">Run on OS Login</span></span>](#run-on-os-login) | <span data-ttu-id="a514b-141">88 以降</span><span class="sxs-lookup"><span data-stu-id="a514b-141">88 or later</span></span> | <span data-ttu-id="a514b-142">すべて</span><span class="sxs-lookup"><span data-stu-id="a514b-142">All</span></span> |  
| [<span data-ttu-id="a514b-143">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a514b-143">Shortcuts</span></span>](#shortcuts) | <span data-ttu-id="a514b-144">87 以降</span><span class="sxs-lookup"><span data-stu-id="a514b-144">87 or later</span></span> | <span data-ttu-id="a514b-145">すべて</span><span class="sxs-lookup"><span data-stu-id="a514b-145">All</span></span> |  
| [<span data-ttu-id="a514b-146">ファイル処理</span><span class="sxs-lookup"><span data-stu-id="a514b-146">File Handling</span></span>](#file-handling) | <span data-ttu-id="a514b-147">83 以降</span><span class="sxs-lookup"><span data-stu-id="a514b-147">83 or later</span></span> | <span data-ttu-id="a514b-148">すべてのデスクトップ</span><span class="sxs-lookup"><span data-stu-id="a514b-148">All Desktop</span></span> |  


## <a name="uri-protocol-handling"></a><span data-ttu-id="a514b-149">URI プロトコルの処理</span><span class="sxs-lookup"><span data-stu-id="a514b-149">URI Protocol Handling</span></span>  

<span data-ttu-id="a514b-150">HTTP または FTP プロトコルを使用して Web ページや Web コンテンツへのリンクを定義するために、統一されたリソース識別子 \(URI\) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-150">A uniform resource identifier \(URI\) may be used to define more than just links to webpages and web content using the HTTP or FTP protocol.</span></span>  <span data-ttu-id="a514b-151">URI を使用して、スキーマにコード化するリンクを記述できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-151">URIs may be used to describe links to anything that you codify into a schema.</span></span>  <span data-ttu-id="a514b-152">たとえば、プロトコルを使用して電子メール リンクを記述し、オペレーティング システム \(OS\) またはブラウザーが、そのプロトコルを処理する Web ページまたはアプリ `mailto://` を決定します。</span><span class="sxs-lookup"><span data-stu-id="a514b-152">For example, the `mailto://` protocol is used to describe an email link and the operating system \(OS\) or browser decides which webpage or app should handle that protocol.</span></span>  

<span data-ttu-id="a514b-153">既存のブラウザー ベースのサポートの詳細については [、Web ベースのプロトコル ハンドラーに移動します][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]。</span><span class="sxs-lookup"><span data-stu-id="a514b-153">For more information about existing browser-based support, navigate to [Web-based protocol handlers][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers].</span></span>  

<span data-ttu-id="a514b-154">この機能を使用すると、次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-154">This feature allows you to complete the following actions.</span></span>  

*   <span data-ttu-id="a514b-155">Web アプリのマニフェストを使用して PWA をホスト OS に登録する</span><span class="sxs-lookup"><span data-stu-id="a514b-155">Register your PWA with the host OS using the manifest of your web app</span></span>
*   <span data-ttu-id="a514b-156">PWA が特定の URI プロトコルを処理すると宣言する</span><span class="sxs-lookup"><span data-stu-id="a514b-156">Declare that a PWA handles a specific URI protocol</span></span>  
     
<span data-ttu-id="a514b-157">プロトコル ハンドラーとして PWA を登録した後、ブラウザーやネイティブ アプリなどの特定のスキームを使用してハイパーリンクを選択すると、登録済みの PWA は OS によってアクティブ化され `mailto://` 、URI を受信します。 `web+music://`</span><span class="sxs-lookup"><span data-stu-id="a514b-157">After you register a PWA as a protocol handler, when a user chooses a hyperlink with a specific scheme such as `mailto://` or `web+music://` from a browser or a native app, the registered PWA is activated by the OS and receives the URI.</span></span>  

<span data-ttu-id="a514b-158">この機能では、2 つのフィールドを指定する必要がある配列に配列を含める Web アプリ マニフェスト `protocol_handlers` を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a514b-158">This feature requires you to update the web app manifest to include a `protocol_handlers` array, in the array you need to specify two fields:</span></span>  

*   `protocol`<span data-ttu-id="a514b-159">: 要求を処理するプロトコル (たとえば `mailto` `web+jngl` 、または.</span><span class="sxs-lookup"><span data-stu-id="a514b-159">:  The protocol to handle the request, for example `mailto` or `web+jngl`.</span></span>  
*   `url`<span data-ttu-id="a514b-160">: プロトコルを処理するアプリ スコープ内の HTTPS URI。</span><span class="sxs-lookup"><span data-stu-id="a514b-160">: The HTTPS URI in the app scope that handles the protocol.</span></span>  <span data-ttu-id="a514b-161">今後、プロトコル ハンドラー スキームで始まる URI は、トークンを置き換える予定 `%s` です。</span><span class="sxs-lookup"><span data-stu-id="a514b-161">In the future, the URI starting with the protocol handlers scheme is planned to replace the `%s` token.</span></span>  
    
<span data-ttu-id="a514b-162">登録するプロトコルをサポートするためにマニフェストを更新します。</span><span class="sxs-lookup"><span data-stu-id="a514b-162">Update your manifest to support the protocol that you want to register.</span></span>  <span data-ttu-id="a514b-163">この機能を有効にした後、Microsoft Edge は次のアクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="a514b-163">After you turn on this feature, Microsoft Edge completes the following actions.</span></span>  

1.  <span data-ttu-id="a514b-164">マニフェストの変更を検出する</span><span class="sxs-lookup"><span data-stu-id="a514b-164">Detects changes in the manifest</span></span>  
1.  <span data-ttu-id="a514b-165">プロトコルのアプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="a514b-165">Registers the app for the protocol</span></span>  
    
<span data-ttu-id="a514b-166">複数のアプリがプロトコルを登録すると、ユーザーにプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a514b-166">If more than one app registers a protocol, the user is presented with a prompt.</span></span>  <span data-ttu-id="a514b-167">ユーザーは、OS またはブラウザーによって表示されるリストから適切なアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="a514b-167">The user chooses the appropriate app from the list presented by the OS or browser.</span></span>  

<span data-ttu-id="a514b-168">Windows の Microsoft Edge でプロトコル処理を[](#turn-on-experimental-features)プレビューするには、[実験的な機能を有効にする] に移動し、[デスクトップ Web アプリのプロトコル ハンドラーのサポート **] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="a514b-168">To preview protocol handling in Microsoft Edge on Windows, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop Web Apps support Protocol Handlers**.</span></span>  

<span data-ttu-id="a514b-169">プロトコル ハンドラーでオリジン試用版が実行されている場合の詳細については [、「Register for Web App Protocol Handler Registration」に移動します][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]。</span><span class="sxs-lookup"><span data-stu-id="a514b-169">For more information about origin trial is running for protocol handlers, navigate to [Register for Web App Protocol Handler Registration][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration].</span></span>  

### <a name="example-manifest"></a><span data-ttu-id="a514b-170">マニフェストの例</span><span class="sxs-lookup"><span data-stu-id="a514b-170">Example Manifest</span></span>

<span data-ttu-id="a514b-171">この例では、Web アプリ マニフェストは、プロトコルを処理するためにアプリを登録する必要があります `web+jngl` `web+jnglstore` 。</span><span class="sxs-lookup"><span data-stu-id="a514b-171">In this example, a web app manifest declares that the app should be registered to handle the protocols `web+jngl` and `web+jnglstore`.</span></span>

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
 
## <a name="url-link-handling"></a><span data-ttu-id="a514b-172">URL リンクの処理</span><span class="sxs-lookup"><span data-stu-id="a514b-172">URL Link Handling</span></span>  

<span data-ttu-id="a514b-173">統一リソース ロケーター \(URL\) は URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="a514b-173">A uniform resource locator \(URL\) is a type of URI.</span></span>  <span data-ttu-id="a514b-174">プログレッシブ Web Apps \(PWAs\) が https URI のハンドラーとして登録するときに、より魅力的なエクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a514b-174">Create a more engaging experience when Progressive Web Apps \(PWAs\) register as handlers for https URIs.</span></span>  <span data-ttu-id="a514b-175">関連付けられた URI がアクティブ化されると、PWA が起動を要求する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a514b-175">PWAs may request to launch when associated URIs are activated.</span></span>  <span data-ttu-id="a514b-176">たとえば、ユーザーが電子メール メッセージからニュース ストーリーへのリンクを選択した場合です。</span><span class="sxs-lookup"><span data-stu-id="a514b-176">For example, if a user chooses a link to a news story from an email message.</span></span>  <span data-ttu-id="a514b-177">リンクのアクティブ化を処理するために、ニュース 記事を表示する関連付けられた PWA が自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="a514b-177">An associated PWA to display news stories is automatically launched to handle the activation of the link.</span></span>  

<span data-ttu-id="a514b-178">この機能を使用すると、Web アプリ マニフェストを使用してブラウザーに PWA を登録し、ブラウザーが特定のリンクを処理すると宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-178">This feature allows you to register a PWA with the browser using the web app manifest and declare that the browser handles specific links.</span></span>  <span data-ttu-id="a514b-179">ブラウザーに PWA を登録するには、省略可能なメンバーを `url_handlers` マニフェスト ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="a514b-179">To register a PWA with the browser, add the optional `url_handlers` member to the manifest file.</span></span>  <span data-ttu-id="a514b-180">メンバー `url_handlers` は、アプリが処理する `object[]` URI の原点をグループ分けするメンバーです。</span><span class="sxs-lookup"><span data-stu-id="a514b-180">The `url_handlers` member is an `object[]` that groups the origins of URIs that the app wishes to handle.</span></span>  

<span data-ttu-id="a514b-181">リンク処理は、原点にある JSON ファイルを使用してブラウザー `web-app-origin-association` によって検証されます。</span><span class="sxs-lookup"><span data-stu-id="a514b-181">Link handling is validated by the browser using a `web-app-origin-association` JSON file that is located on the origin.</span></span>  <span data-ttu-id="a514b-182">オリジン ファイルは、オリジンの含まれるパスまたは除外されたパスをさらに微調整します。</span><span class="sxs-lookup"><span data-stu-id="a514b-182">The origin file further fine-tunes the included or excluded paths at the origin.</span></span>  <span data-ttu-id="a514b-183">URL ハンドラーのテストに関する詳細な手順については、URL [ハンドラーとして PWA に移動します][GithubWicgPwaUrlHandlerBlobMainExplainerMd]。</span><span class="sxs-lookup"><span data-stu-id="a514b-183">For detailed instructions about testing the URL handler, navigate to [PWAs as URL Handlers][GithubWicgPwaUrlHandlerBlobMainExplainerMd].</span></span>  

<span data-ttu-id="a514b-184">Windows の Microsoft Edge で URL リンク[](#turn-on-experimental-features)処理をプレビューするには、[実験的な機能を有効にする] に移動し、[デスクトップ PWA URL の処理 **] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="a514b-184">To preview URL link handling in Microsoft Edge on Windows, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop PWA URL  Handling**.</span></span>  

### <a name="example-of-the-url_handlers-in-the-manifest"></a><span data-ttu-id="a514b-185">マニフェスト内のurl_handlersの例</span><span class="sxs-lookup"><span data-stu-id="a514b-185">Example of the url_handlers in the manifest</span></span>  

<span data-ttu-id="a514b-186">次のコード スニペットは、メンバーを持つ Web アプリ マニフェストの例 `url_handlers` です。</span><span class="sxs-lookup"><span data-stu-id="a514b-186">The following code snippet is an example web app manifest with the `url_handlers` member.</span></span>  

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

<span data-ttu-id="a514b-187">PWA は、URI が元の文字列の 1 つと一致する場合に URL 処理の URI と一致し、ブラウザーは、このアプリがそのような URI を処理することに基が同意したと検証します `url_handlers` 。</span><span class="sxs-lookup"><span data-stu-id="a514b-187">A PWA matches a URI for URL handling if the URI matches one of the origin strings in `url_handlers` and the browser validates that the origin agrees to allow this app handle such a URI.</span></span>  

<span data-ttu-id="a514b-188">メンバーには、要求する PWA の範囲と他の無関係な起点を含むオ `url_handlers` リジンが含まれる。</span><span class="sxs-lookup"><span data-stu-id="a514b-188">The `url_handlers` member contains an origin that encompasses the scope and also other unrelated origins of the requesting PWA.</span></span>  <span data-ttu-id="a514b-189">URI を要求する PWA と同じスコープまたはドメインに制限しない場合、同じコンテンツに異なるドメイン名を使用できますが、同じ PWA で処理できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-189">Not restricting URIs to the same scope or domain as the requesting PWA allows you to use different domain names for the same content but handle them with the same PWA.</span></span>  

#### <a name="wildcard-matching"></a><span data-ttu-id="a514b-190">ワイルドカードの一致</span><span class="sxs-lookup"><span data-stu-id="a514b-190">Wildcard matching</span></span>  

<span data-ttu-id="a514b-191">1 つ以上の文字に `*` 一致するには、ワイルドカード文字 \( \) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a514b-191">Use the wildcard character \(`*`\) to match one or more characters.</span></span>  

<span data-ttu-id="a514b-192">異なるサブドメインに一致するために、メンバーのオリジン文字列でワイルドカード `url_handlers` プレフィックスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a514b-192">A wildcard prefix is used in origin strings of the `url_handlers` member to match for different subdomains.</span></span>  <span data-ttu-id="a514b-193">プレフィックスは、この使用法 `*.` 用である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a514b-193">The prefix must be `*.` for this usage.</span></span>  <span data-ttu-id="a514b-194">ワイルドカード `https` プレフィックスを使用する場合、スキームは想定されます。</span><span class="sxs-lookup"><span data-stu-id="a514b-194">The `https` scheme is assumed when you use a wildcard prefix.</span></span>  

<span data-ttu-id="a514b-195">たとえば、メンバーの `url_handlers` 値は一致する値に `*.contoso.com` 設定 `tenant.contoso.com` されますが、 `www.tenant.contoso.com` 一致しません `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="a514b-195">For example, the `url_handlers` member value is set to `*.contoso.com` matches `tenant.contoso.com` and `www.tenant.contoso.com`, but doesn't match `contoso.com`.</span></span>  

<!-- Hold for future release -->  
<!--  ## Window Controls Overlay for installed desktop web apps  

To create an immersive title bar similar to a native app for your desktop installed web app.  The **Window Controls Overlay** feature  completes the following actions.  
    
1.  Removes the system reserved title bar.  It usually spans the width of the client frame.  
1.  Replaces it with an overlay.  It contains just the critical system required window controls necessary for a user to control the window itself.  
    
After it provides an overlay, the entire web client area is available for you to use.  This feature includes a manifest update.  It provides ways for you to determine the size and position of the overlay to help you arrange content.  
    
### Examples of title bar area customization  

This feature is based on the ability in native apps to customize the title bar.  You may customize a title bar for important app actions or notifications.  Review the following examples for Microsoft Visual Studio Code and Microsoft Teams.  

#### Visual Studio Code  

Microsoft Visual Studio Code is a popular editor built on Electron that ships on multiple desktop platforms.  

The following example displays how Visual Studio Code uses the title bar to maximize available screen real estate to include the current file name and top-level menu structure in the title bar.  

:::image type="complex" source="../media/visual-studio-code-title-customization.png" alt-text="An example of the title bar in Visual Studio Code" lightbox="../media/visual-studio-code-title-customization.png":::
   An example of the title bar in Visual Studio Code  
:::image-end:::  

#### Microsoft Teams  

Workplace collaboration and communication tool Microsoft Teams is also built with Electron and available on multiple desktop platforms.  In the following example, Microsoft Teams displays `back` and `forward` navigation buttons, a search box, and user profile controls.  

:::image type="complex" source="../media/teams-title-customization.png" alt-text="An example of the title bar in Microsoft Teams" lightbox="../media/teams-title-customization.png":::
   An example of the title bar in Microsoft Teams  
:::image-end:::  

### Overlay Window Controls on a Frameless Window  

To provide the maximum addressable area for web content, the browser creates a frameless window, removing all browser UI except for the window controls provided as an overlay.  
The window controls overlay ensures users still minimize, maximize, restore, and close the app.  It also provides access to relevant browser controls using the web app menu.  For Chromium-based browsers, the controls in the overlay.

*   A draggable region the same width and height of each of the window control buttons  
*   The **Settings and more** \(...\) button  
*   The window control buttons minimize, maximize, restore, and close  
    
The following scenarios include when browser displays other content in the controls overlay.  

*   When an installed web app is launched, the origin of the webpage displays to the left of the **Settings and more** \(...\) menu for a few seconds and then disappears.  
*   If a user interacts with an extension using the **Settings and more** \(...\) menu, the icon of the extension displays in the overlay to the left of the three-dot menu.  After you exit any extension dialog, the icon is removed from the overlay.  
    
| Language direction | Overlay location | Details |  
|:--- |:--- |:--- |  
| Left-to-right \(LTR\) | Upper left of the client area | The controls are flipped |  
| Right-to-left \(RTL\) | Upper right corner of the client area |  |  

>[!IMPORTANT]
> The overlay is always on top of the Z-index of the web content and accepts all user input without flowing it through to the web content.  

### Working around the Window Controls Overlay  

Your web content must be aware of the reserved area for the controls overlay.  Ensure the reserved area doesn't expect user interaction.  Query the browser for the bounding rectangle and visibility of the controls overlay.  The information is provided to you through JavaScript APIs and CSS environment variables.  

#### JavaScript APIs  

A new `windowControlsOverlay` object on the `window.navigator` property allows you to query the bounding rectangle of the controls overlay.  

The `windowControlsOverlay` object has the following two objects.  

*   `getBoundingClientRect()` returns a `DOMRect` object.  The `DOMRect` object represents the area under the window controls overlay.  
*   `visible` is a boolean that indicates that the controls overlay is rendered and displayed.  
    
> [!IMPORTANT]
> For privacy reasons, the `windowControlsOverlay` isn't accessible to `iframe` elements in the web content.  

Whenever the overlay is resized, a `geometrychange` event runs on the `navigator.windowControlsOverlay` object to notify the client to recalculate the content layout.  The recalculated content layout is based on the new bounding rectangle of the overlay.  

#### CSS Environment Variables  

Besides the JavaScript API, you may use CSS to query the bounding rectangle of the controls overlay.  Use the following four new CSS environment variables to accomplish to query.  

*   `titlebar-area-x`  
*   `titlebar-area-y`  
*   `titlebar-area-width`  
*   `titlebar-area-height`  
    
### Define Draggable Regions in Web Content  

Users expect to grab and drag the upper region of a window.  To accommodate the expectation, declare specific parts of the web content as draggable.  
To specify an element is draggable, use the webkit proprietary `-webkit-app-region` CSS property.  The CSS working group continues efforts to standardize the `app-region` property.  

To preview this feature in Microsoft Edge for desktop OSs, navigate to [Turn on experimental features](#turn-on-experimental-features) and navigate to **Desktop PWA Window Controls Overlay**.   

### Custom title bar example  

The following example displays how the new features create a web app with a custom title bar.  

:::image type="complex" source="../media/teams-title-customization-example.png" alt-text="Example of a custom title bar in Microsoft Teams" lightbox="../media/teams-title-customization-example.png":::
   Example of a custom title bar in Microsoft Teams  
:::image-end:::  

#### manifest.webmanifest  

In the manifest, set `display_override` array to  `window-controls-overlay`.  Set the `theme_color` to your choice of color for the title bar.  Set the display mode to an appropriate fallback for when either `display_override` or `window-controls-overlay` isn't supported.  

The following code snippet includes the recommended manifest updates.  

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

### index.html  

The following IDs represent the two main regions of the webpage.  

*   `titleBarContainer`  
*   `mainContent`  
    
The `div` element with the `titleBar` ID is set to `draggable` and the search box `input` child element is set to `nonDraggable`.  

```html
<div id="titleBar" class=" draggable">
    <span class="draggable">Example PWA</span>
    <input class="nonDraggable" type="text" placeholder="Search"></input>
</div>
```

In the `div` element with the `titleBarContainer` ID, the `div` with the `titleBar` ID represents the visible portion of the title bar area.  

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
    <div id="mainContent">The rest of the webpage</div>
  </body>
</html>
```  

### style.css  

The draggable and non-draggable regions are set using `-webkit-app-region: drag` and `-webkit-app-region: no-drag`.  

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

For the `body` element, margins are set to `0` to ensure the title bar reaches to the edges of the window.  

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
}
```  

The `titleBarContainer` ID uses `position: absolute` and sets the `top` to `titlebar-area-inset-top`, which attaches the container to the top of the webpage.  The `bottom` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-title-bar-height)` if the window controls overlay isn't visible.  The background color of the `titleBarContainer` ID is the same as the `theme_color`.  The width is set to `100%`, so that the `div` element fills the width of the webpage and flows under the overlay when it's visible for a contiguous appearance.  

```css
#titleBarContainer {
    position: absolute;
    top: env(titlebar-area-y, 0);
    bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    width: 100%;
    background-color:#254B85;
}
```  

The `titleBar` ID also uses `position: absolute` and `top: titlebar-area-inset-top` to attaches it to the top of the window.  By default, it consumes the full width of the window.  The `left` and `right` edges are set to `titlebar-area-inset-left` and `titlebar-area-inset-right` respectively, both fall back to `0` when the values aren't set.  It also sets `user-select: none` to prevent any attempts to drag the window consumed instead it highlights text in the `div` element.  

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

The container for the `mainContent` ID is also fixed in place with `position: absolute` and is attached to the bottom of the webpage.  The `height` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-titlebar-height)` to fill the remaining space below the title bar.  It sets `overflow-y: scroll` to allow the contents to scroll vertically in the container.  

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

For cases where the browser doesn't support the window controls overlay, a CSS variable is added to set a default height for the title bar.  The bounds of the `titleBarContainer` and `mainContent` IDs are initially set to fill the entire client area, and you don't need to change it if the overlay isn't supported.  

The following code snippet includes all of the recommended css updates.

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
-->  

## <a name="run-on-os-login"></a><span data-ttu-id="a514b-196">[OS ログイン時に実行]</span><span class="sxs-lookup"><span data-stu-id="a514b-196">Run On OS Login</span></span>  

<span data-ttu-id="a514b-197">この機能を使用すると、ユーザーが Microsoft Windows にログインするときに自動的に起動するアプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-197">This feature allows you to configure your app to automatically launch when the user logs into Microsoft Windows.</span></span>  <span data-ttu-id="a514b-198">いくつかのクラスのアプリは、この機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="a514b-198">Several classes of apps take advantage of the capability.</span></span>  <span data-ttu-id="a514b-199">アプリのクラスには、メール、チャット、監視ダッシュボード、リアルタイムデータ表示アプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a514b-199">The classes of apps include email, chat, monitoring dashboard, and real-time data display apps.</span></span>  <span data-ttu-id="a514b-200">この機能を使用すると、ユーザーが OS にログインするとすぐにアプリに参加できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-200">The capability allows a user to engage with the apps as soon as the user logs into the OS.</span></span>  <span data-ttu-id="a514b-201">この機能は、手動で起動するのと同じ方法で PWA を自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="a514b-201">This feature automatically starts the PWA the same way it's launched manually.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="a514b-202">**[OS ログインで実行] は** 強力 [な機能です][GithubW3cPermissionsPowerfulFeature]。</span><span class="sxs-lookup"><span data-stu-id="a514b-202">**Run on OS Login** is a [powerful feature][GithubW3cPermissionsPowerfulFeature].</span></span>  <span data-ttu-id="a514b-203">ユーザーは、インストールされている Web アプリの機能を有効にするかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a514b-203">Users should decide whether to turn on the capability for the installed web app.</span></span>  

### <a name="turn-on-run-on-os-login"></a><span data-ttu-id="a514b-204">[OS ログイン時に実行] をオンにする</span><span class="sxs-lookup"><span data-stu-id="a514b-204">Turn on Run On OS Login</span></span>  

<span data-ttu-id="a514b-205">PWA の**Run On OS Login 機能**を有効[](#turn-on-experimental-features)にする場合は、[実験的な機能を有効にする] に移動し、OS ログイン時にデスクトップ**PWA を実行します**。</span><span class="sxs-lookup"><span data-stu-id="a514b-205">To turn on **Run On OS Login** capabilities for your PWA, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop PWAs run on OS login**.</span></span>  

:::image type="complex" source="../media/desktop-pwas-run-on-os-login-flag.png" alt-text="OS Login 実験で実行するデスクトップ PWA を有効にする" lightbox="../media/desktop-pwas-run-on-os-login-flag.png":::
   <span data-ttu-id="a514b-207">OS ログイン実験 **でデスクトップ PWA の実行を有効** にする</span><span class="sxs-lookup"><span data-stu-id="a514b-207">Turn on the **Desktop PWAs run on OS login** experiment</span></span>  
:::image-end:::  

### <a name="turn-on-the-feature-for-the-installed-web-app"></a><span data-ttu-id="a514b-208">インストールされている Web アプリの機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="a514b-208">Turn on the feature for the installed web app</span></span>  

<span data-ttu-id="a514b-209">インストールされている `Start app when you sign in` PWA の機能を有効にするには、</span><span class="sxs-lookup"><span data-stu-id="a514b-209">To turn on the `Start app when you sign in` feature for an installed PWA,</span></span> 

1.  <span data-ttu-id="a514b-210">Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="a514b-210">Open Microsoft Edge.</span></span>   
1.  <span data-ttu-id="a514b-211">に移動します `edge://apps` 。</span><span class="sxs-lookup"><span data-stu-id="a514b-211">Navigate to `edge://apps`.</span></span>  
1.  <span data-ttu-id="a514b-212">アプリにカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="a514b-212">Hover on your app.</span></span>  
1.  <span data-ttu-id="a514b-213">コンテキスト メニュー \(右クリック\) を開き、サインイン時に [アプリの起動 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a514b-213">Open the contextual menu \(right-click\) and then choose **Start app when you sign in**.</span></span>  
    
    :::image type="complex" source="../media/turn-on-run-on-os-login-flag.png" alt-text="Microsoft Edge の機能にサインインするときに、コンテキスト メニューを使用してスタート アプリを有効にする" lightbox="../media/turn-on-run-on-os-login-flag.png":::
       <span data-ttu-id="a514b-215">Microsoft Edge の機能にサインインするときに、コンテキスト メニューを使用してスタート **アプリを** 有効にする</span><span class="sxs-lookup"><span data-stu-id="a514b-215">Use the contextual menu to turn on the **Start app when you sign in** feature in Microsoft Edge</span></span>  
    :::image-end:::  
    
## <a name="shortcuts"></a><span data-ttu-id="a514b-216">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a514b-216">Shortcuts</span></span>  

`Shortcuts` <span data-ttu-id="a514b-217">はマニフェスト ファイルの新しいメンバーです。</span><span class="sxs-lookup"><span data-stu-id="a514b-217">is a new member of the manifest file.</span></span>  <span data-ttu-id="a514b-218">これにより、Web アプリ内のパーツ、キー Web ページ、またはアクションへのリンクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-218">It allows you to define links to parts, key webpages, or actions in your web app.</span></span>  <span data-ttu-id="a514b-219">Microsoft Windows は、ジャンプリスト **として統合します**。</span><span class="sxs-lookup"><span data-stu-id="a514b-219">Microsoft Windows integrates it as **Jumplists**.</span></span>  <span data-ttu-id="a514b-220">**ジャンプリストは、** 次のいずれかの UI 要素で表示されるポップアップ メニューを定義し、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a514b-220">**Jumplists** define popup menus that appear when you on one of the following UI elements and open a contextual menu \(right-click\).</span></span>  

*   <span data-ttu-id="a514b-221">スタート メニューのタイル</span><span class="sxs-lookup"><span data-stu-id="a514b-221">A tile on the Start Menu</span></span>  
*   <span data-ttu-id="a514b-222">タスク バーのアイコン</span><span class="sxs-lookup"><span data-stu-id="a514b-222">An icon on the Taskbar</span></span>  
    
<span data-ttu-id="a514b-223">ユーザーがショートカットを呼び出すと、ユーザーはショートカットのメンバーによって指定された `url` アドレスに移動します。</span><span class="sxs-lookup"><span data-stu-id="a514b-223">When a user invokes a shortcut, the user navigates to the address specified by the `url` member of the shortcut.</span></span>  
  
:::image type="complex" source="../media/jumplists-on-windows-10.png" alt-text="Windows 10 のジャンプリストの例" lightbox="../media/jumplists-on-windows-10.png":::
   <span data-ttu-id="a514b-225">Windows 10 **のジャンプリスト** の例</span><span class="sxs-lookup"><span data-stu-id="a514b-225">An example of **Jumplists** on Windows 10</span></span>  
:::image-end:::  

### <a name="shortcuts-in-the-manifest-file"></a><span data-ttu-id="a514b-226">マニフェスト ファイルのショートカット</span><span class="sxs-lookup"><span data-stu-id="a514b-226">Shortcuts in the Manifest file</span></span>  

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

#### <a name="properties-of-shortcuts"></a><span data-ttu-id="a514b-227">ショートカットのプロパティ</span><span class="sxs-lookup"><span data-stu-id="a514b-227">Properties of shortcuts</span></span>  

<span data-ttu-id="a514b-228">次のプロパティは、各ショートカットを定義します。</span><span class="sxs-lookup"><span data-stu-id="a514b-228">The following properties define each shortcut.</span></span>  

| <span data-ttu-id="a514b-229">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a514b-229">Property</span></span> | <span data-ttu-id="a514b-230">詳細</span><span class="sxs-lookup"><span data-stu-id="a514b-230">Details</span></span> |  
|:--- |:--- |  
| `name` | <span data-ttu-id="a514b-231">**Jumplists**またはコンテキスト メニューでユーザーに表示される文字列。</span><span class="sxs-lookup"><span data-stu-id="a514b-231">A string that is displayed to the user on **Jumplists** or the contextual menu.</span></span> |  
| `short_name` | <span data-ttu-id="a514b-232">ショートカットの完全な名前を表示する領域が不足している場合に表示される文字列。</span><span class="sxs-lookup"><span data-stu-id="a514b-232">A string that is displayed when insufficient space exists to display the full name of the shortcut.</span></span> |  
| `description` | <span data-ttu-id="a514b-233">ショートカットの目的を説明する文字列。</span><span class="sxs-lookup"><span data-stu-id="a514b-233">A string that describes the purpose of the shortcut.</span></span>  <span data-ttu-id="a514b-234">支援技術によってアクセスされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a514b-234">It may be accessed by assistive technology.</span></span> |  
| `url` | <span data-ttu-id="a514b-235">ショートカットがアクティブ化されると開く Web アプリの URI。</span><span class="sxs-lookup"><span data-stu-id="a514b-235">The URI in the web app that opens when the shortcut is activated.</span></span> |  
| `icons` | <span data-ttu-id="a514b-236">ショートカットを表す一連のアイコン。</span><span class="sxs-lookup"><span data-stu-id="a514b-236">A set of icons that represents the shortcut.</span></span> |  

## <a name="file-handling"></a><span data-ttu-id="a514b-237">ファイル処理</span><span class="sxs-lookup"><span data-stu-id="a514b-237">File Handling</span></span>  

<span data-ttu-id="a514b-238">ファイルの種類ハンドラーとして登録する機能は、実験段階です。</span><span class="sxs-lookup"><span data-stu-id="a514b-238">The ability to register as a file type handler is in the experimentation phase.</span></span>  <span data-ttu-id="a514b-239">マニフェスト エントリでアプリが処理するファイルの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a514b-239">You may specify the file types that your app handles in a manifest entry.</span></span>  <span data-ttu-id="a514b-240">インストール中に、ユーザーのホスト OS は、アプリをリストされたファイルの種類のファイル ハンドラーとして登録します。</span><span class="sxs-lookup"><span data-stu-id="a514b-240">During installation, the user's host OS registers your app as a file handler for the listed file types.</span></span>  <span data-ttu-id="a514b-241">アプリのスタートアップ コードに機能が存在し、その機能が `launchQueue` ファイルを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a514b-241">Ensure the existence of the feature `launchQueue` in your apps startup code and that it handles the file.</span></span>  

<span data-ttu-id="a514b-242">クロム ベースのブラウザーでは、この機能のテストと整形を行っています。</span><span class="sxs-lookup"><span data-stu-id="a514b-242">Chromium-based browsers are testing and shaping this feature.</span></span>  <span data-ttu-id="a514b-243">コード例を含む詳細については、「Web アプリケーションをファイル ハンドラー [に設定する」に移動します][WebDevFileHandling]。</span><span class="sxs-lookup"><span data-stu-id="a514b-243">For more information including code examples, navigate to [Let web applications be file handlers][WebDevFileHandling].</span></span>  

<span data-ttu-id="a514b-244">デスクトップ OS 用 Microsoft Edge でファイル処理を[](#turn-on-experimental-features)プレビューするには、[実験機能を有効にする] に移動し、[ファイル処理**API] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="a514b-244">To preview file handling in Microsoft Edge for desktop OSs, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **File Handling API**.</span></span>  
    
## <a name="providing-feedback-on-experimental-features"></a><span data-ttu-id="a514b-245">実験的な機能に関するフィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="a514b-245">Providing feedback on experimental features</span></span>  

<span data-ttu-id="a514b-246">Microsoft Edge Web アプリの実験に関するフィードバックを提供する。</span><span class="sxs-lookup"><span data-stu-id="a514b-246">To provide feedback on Microsoft Edge web app experiments.</span></span>  

*   <span data-ttu-id="a514b-247">[設定] および [ **その他]** \( \) を使用してフィードバックを送信 `...` >フィードバックを **Microsoft に送信します**。</span><span class="sxs-lookup"><span data-stu-id="a514b-247">Send your feedback using **Settings and More** \(`...`\) > **Send Feedback to Microsoft**.</span></span>  
*   <span data-ttu-id="a514b-248">を選択します `Alt` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="a514b-248">Select `Alt`+`Shift`+`I`.</span></span>  
    
:::image type="complex" source="../media/send-feedback-from-progressive-web-app.png" alt-text="PWA からフィードバックを送信する" lightbox="../media/send-feedback-from-progressive-web-app.png":::
   <span data-ttu-id="a514b-250">PWA からフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="a514b-250">Send Feedback from your PWA</span></span>  
:::image-end:::  

<!-- links -->  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[MicrosoftDeveloperMicrosoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Origin Trials |Microsoft Edge 開発者"  
[MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]: https://developer.microsoft.com/microsoft-edge/origin-trials/web-app-protocol-handler-registration/registration "Web アプリ プロトコル ハンドラー登録の登録|Microsoft 開発者"  

[MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]: https://developer.mozilla.org/docs/Web/API/Navigator/registerProtocolHandler/Web-based_protocol_handlers "Web ベースのプロトコル ハンドラー|MDN"  

[GithubW3cPermissionsPowerfulFeature]: https://w3c.github.io/permissions#powerful-feature "強力な機能 - アクセス許可|GitHub"  

[GithubWicgPwaUrlHandlerBlobMainExplainerMd]: https://github.com/WICG/pwa-url-handler/blob/main/explainer.md "URL ハンドラーとしての PWA |GitHub"  

[WebDevFileHandling]: https://web.dev/file-handling "Web アプリケーションをファイル ハンドラーに|web.dev"  
