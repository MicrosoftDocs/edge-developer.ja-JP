---
<span data-ttu-id="3f60f-101">説明: Microsoft Edge タイトルと WebView2 タイトルの機能の違い: Microsoft Edge と WebView2 作成者の機能の違い: MSEdgeTeam ms.author: msedgedevrel ms.date: 05/06/2021 ms.topic: 概念 ms.prod: microsoft-edge ms.technology: webview キーワード: IWebView2, IWebView2WebView、WebView2、Webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html no-loc:</span><span class="sxs-lookup"><span data-stu-id="3f60f-101">description: Feature differences between Microsoft Edge and WebView2 title: Feature differences between Microsoft Edge and WebView2 author: MSEdgeTeam ms.author: msedgedevrel ms.date: 05/06/2021 ms.topic: conceptual ms.prod: microsoft-edge ms.technology: webview keywords: IWebView2, IWebView2WebView, WebView2, webview, wpf apps, wpf, edge, ICoreWebView2, ICoreWebView2Host, browser control, edge html no-loc:</span></span>
- <span data-ttu-id="3f60f-102">"Autofill for Addresses"</span><span class="sxs-lookup"><span data-stu-id="3f60f-102">"Autofill for Addresses"</span></span>
- <span data-ttu-id="3f60f-103">"Autofill for Passwords"</span><span class="sxs-lookup"><span data-stu-id="3f60f-103">"Autofill for Passwords"</span></span>
- <span data-ttu-id="3f60f-104">"Autofill for Payments""</span><span class="sxs-lookup"><span data-stu-id="3f60f-104">"Autofill for Payments""</span></span>
- <span data-ttu-id="3f60f-105">"Browser Extensions""</span><span class="sxs-lookup"><span data-stu-id="3f60f-105">"Browser Extensions""</span></span>
- <span data-ttu-id="3f60f-106">"Browser Task Manager"</span><span class="sxs-lookup"><span data-stu-id="3f60f-106">"Browser Task Manager"</span></span>
- <span data-ttu-id="3f60f-107">"Collections"</span><span class="sxs-lookup"><span data-stu-id="3f60f-107">"Collections"</span></span>
- <span data-ttu-id="3f60f-108">"Continue-where-I-left-off prompt"</span><span class="sxs-lookup"><span data-stu-id="3f60f-108">"Continue-where-I-left-off prompt"</span></span>
- <span data-ttu-id="3f60f-109">"Downloads"</span><span class="sxs-lookup"><span data-stu-id="3f60f-109">"Downloads"</span></span>
- <span data-ttu-id="3f60f-110">"Edge Shopping"</span><span class="sxs-lookup"><span data-stu-id="3f60f-110">"Edge Shopping"</span></span>
- <span data-ttu-id="3f60f-111">"Family Safety"</span><span class="sxs-lookup"><span data-stu-id="3f60f-111">"Family Safety"</span></span>
- <span data-ttu-id="3f60f-112">"Favorites"</span><span class="sxs-lookup"><span data-stu-id="3f60f-112">"Favorites"</span></span>
- <span data-ttu-id="3f60f-113">"Hotkeys"</span><span class="sxs-lookup"><span data-stu-id="3f60f-113">"Hotkeys"</span></span>
- <span data-ttu-id="3f60f-114">"IE Mode"</span><span class="sxs-lookup"><span data-stu-id="3f60f-114">"IE Mode"</span></span>
- <span data-ttu-id="3f60f-115">"Immersive Reader"</span><span class="sxs-lookup"><span data-stu-id="3f60f-115">"Immersive Reader"</span></span>
- <span data-ttu-id="3f60f-116">"Intrusive Ads"</span><span class="sxs-lookup"><span data-stu-id="3f60f-116">"Intrusive Ads"</span></span>
- <span data-ttu-id="3f60f-117">"Read Aloud"</span><span class="sxs-lookup"><span data-stu-id="3f60f-117">"Read Aloud"</span></span>
- <span data-ttu-id="3f60f-118">"Smart Screen"</span><span class="sxs-lookup"><span data-stu-id="3f60f-118">"Smart Screen"</span></span>
- <span data-ttu-id="3f60f-119">"Translate"</span><span class="sxs-lookup"><span data-stu-id="3f60f-119">"Translate"</span></span>
- <span data-ttu-id="3f60f-120">"Tracking Prevention"</span><span class="sxs-lookup"><span data-stu-id="3f60f-120">"Tracking Prevention"</span></span>
- <span data-ttu-id="3f60f-121">"Profile and Identity"</span><span class="sxs-lookup"><span data-stu-id="3f60f-121">"Profile and Identity"</span></span>
- <span data-ttu-id="3f60f-122">"Web Payment API"</span><span class="sxs-lookup"><span data-stu-id="3f60f-122">"Web Payment API"</span></span>
- <span data-ttu-id="3f60f-123">"Windows Defender Application Guard"</span><span class="sxs-lookup"><span data-stu-id="3f60f-123">"Windows Defender Application Guard"</span></span>
- <span data-ttu-id="3f60f-124">"edge:// URLs"</span><span class="sxs-lookup"><span data-stu-id="3f60f-124">"edge:// URLs"</span></span>

---
# <a name="browser-feature-differences-between-microsoft-edge-and-webview2"></a><span data-ttu-id="3f60f-125">ブラウザーの機能の違いMicrosoft Edge WebView2</span><span class="sxs-lookup"><span data-stu-id="3f60f-125">Browser feature differences between Microsoft Edge and WebView2</span></span>  

<span data-ttu-id="3f60f-126">WebView2 は、新しいブラウザー Microsoft Edgeです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-126">WebView2 is based on the new Microsoft Edge browser.</span></span>  <span data-ttu-id="3f60f-127">ブラウザーから WebView2 ベースのアプリに機能を拡張する機会があります。これは便利です。</span><span class="sxs-lookup"><span data-stu-id="3f60f-127">You have the opportunity to extend features from the browser to WebView2-based apps, which is useful.</span></span>  <span data-ttu-id="3f60f-128">ただし、WebView2 はブラウザーのようなアプリに限定されないので、変更または削除する必要があるブラウザー機能があります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-128">However, since WebView2 isn't limited to browser-like apps, there are some browser features that need to be modified or removed.</span></span>  <span data-ttu-id="3f60f-129">この記事では、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3f60f-129">This article provides the following information.</span></span>  

*   <span data-ttu-id="3f60f-130">変更されたブラウザー機能とサポート情報。</span><span class="sxs-lookup"><span data-stu-id="3f60f-130">The modified browser features and supporting information.</span></span>   
*   <span data-ttu-id="3f60f-131">機能のオンとオフを切り替える機能。</span><span class="sxs-lookup"><span data-stu-id="3f60f-131">The ability to turn on or off the feature.</span></span>  
*   <span data-ttu-id="3f60f-132">キーボード ショートカットに関するガイダンス。</span><span class="sxs-lookup"><span data-stu-id="3f60f-132">Guidance on keyboard shortcuts.</span></span>  
    
## <a name="design-guidelines"></a><span data-ttu-id="3f60f-133">設計ガイドライン</span><span class="sxs-lookup"><span data-stu-id="3f60f-133">Design guidelines</span></span>  

<span data-ttu-id="3f60f-134">WebView2 のコンテキストでは、ブラウザー機能は次の設計ガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="3f60f-134">In the context of WebView2, browser features adhere to the following design guidelines.</span></span>  

*   <span data-ttu-id="3f60f-135">ほとんどの機能は、WebView2 および WebView2 および webView2 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3f60f-135">Most features work the same in WebView2 and Microsoft Edge.</span></span>  <span data-ttu-id="3f60f-136">WebView2 のコンテキストや他の理由で機能が意味をなさない場合、機能は変更または無効になります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-136">If a feature doesn't make sense in the context of WebView2 or for other reasons, the feature is modified or turned off.</span></span> 
*   <span data-ttu-id="3f60f-137">WebView2 の機能には、ブランド化Microsoft Edge含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f60f-137">WebView2 features don't include Microsoft Edge branding.</span></span>  
    
## <a name="features"></a><span data-ttu-id="3f60f-138">機能</span><span class="sxs-lookup"><span data-stu-id="3f60f-138">Features</span></span>  

<span data-ttu-id="3f60f-139">次の表に、ブラウザーとは異なる WebView2 Microsoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="3f60f-139">The following table displays the WebView2 features that differ from the Microsoft Edge browser.</span></span>   

*   <span data-ttu-id="3f60f-140">**既定の** 状態は、機能が新しい WebView2 インスタンスの既定のエクスペリエンスの一部を示します。</span><span class="sxs-lookup"><span data-stu-id="3f60f-140">**Default state** indicates that the feature is part of the default experience on a new WebView2 instance.</span></span>  
*   <span data-ttu-id="3f60f-141">**[構成** 可能] は、WebView2 API またはコマンド ライン スイッチを使用して機能を有効またはオフにできる可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="3f60f-141">**Configurable** indicates that you may turn on or off the feature using WebView2 APIs or command-line switches.</span></span>  
    
> [!NOTE]  
> <span data-ttu-id="3f60f-142">この記事では、コマンド ライン スイッチを使用した機能の変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f60f-142">This article doesn't cover modifying features using command-line switches.</span></span>  <span data-ttu-id="3f60f-143">コマンド ライン スイッチを使用して機能のオンとオフを切り替える方法の詳細については、「コマンド ライン スイッチの一覧[」Chromiumを参照してください][PeterExperimentsChromiumCommandLineSwitches]。</span><span class="sxs-lookup"><span data-stu-id="3f60f-143">For more information about turning on and off features with command-line switches, navigate to [List of Chromium Command Line Switches][PeterExperimentsChromiumCommandLineSwitches].</span></span>  
    
| <span data-ttu-id="3f60f-144">機能</span><span class="sxs-lookup"><span data-stu-id="3f60f-144">Feature</span></span> | <span data-ttu-id="3f60f-145">既定の状態</span><span class="sxs-lookup"><span data-stu-id="3f60f-145">Default state</span></span> | <span data-ttu-id="3f60f-146">構成可能</span><span class="sxs-lookup"><span data-stu-id="3f60f-146">Configurable</span></span> | <span data-ttu-id="3f60f-147">詳細</span><span class="sxs-lookup"><span data-stu-id="3f60f-147">Details</span></span> |  
|:--- |:--- |:--- | :--- |  
| Autofill for Addresses | <span data-ttu-id="3f60f-148">オン</span><span class="sxs-lookup"><span data-stu-id="3f60f-148">On</span></span> | <span data-ttu-id="3f60f-149">あり</span><span class="sxs-lookup"><span data-stu-id="3f60f-149">Yes</span></span> | <span data-ttu-id="3f60f-150">この機能は既定でオンになっています。WebView2 オートフィル API を使用してオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="3f60f-150">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| Autofill for Passwords | <span data-ttu-id="3f60f-151">オン</span><span class="sxs-lookup"><span data-stu-id="3f60f-151">On</span></span> | <span data-ttu-id="3f60f-152">あり</span><span class="sxs-lookup"><span data-stu-id="3f60f-152">Yes</span></span> | <span data-ttu-id="3f60f-153">この機能は既定でオンになっています。WebView2 オートフィル API を使用してオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="3f60f-153">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| <span data-ttu-id="3f60f-154">支払いの自動入力</span><span class="sxs-lookup"><span data-stu-id="3f60f-154">Autofill for Payments</span></span> | <span data-ttu-id="3f60f-155">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-155">Off</span></span> | <span data-ttu-id="3f60f-156">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-156">No</span></span> | <span data-ttu-id="3f60f-157">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-157">This feature is turned off.</span></span>  |  
| <span data-ttu-id="3f60f-158">ブラウザー拡張機能</span><span class="sxs-lookup"><span data-stu-id="3f60f-158">Browser Extensions</span></span> | <span data-ttu-id="3f60f-159">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-159">Off</span></span> | <span data-ttu-id="3f60f-160">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-160">No</span></span> | <span data-ttu-id="3f60f-161">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-161">This feature is turned off.</span></span>  |  
| Browser Task Manager | <span data-ttu-id="3f60f-162">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-162">Off</span></span> | <span data-ttu-id="3f60f-163">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-163">No</span></span> | <span data-ttu-id="3f60f-164">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-164">This feature is turned off.</span></span>  |  
| Collections | <span data-ttu-id="3f60f-165">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-165">Off</span></span> | <span data-ttu-id="3f60f-166">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-166">No</span></span> | <span data-ttu-id="3f60f-167">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-167">This feature is turned off.</span></span>  |  
| Continue-where-I-left-off prompt | <span data-ttu-id="3f60f-168">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-168">Off</span></span> | <span data-ttu-id="3f60f-169">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-169">No</span></span> | <span data-ttu-id="3f60f-170">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-170">This feature is turned off.</span></span>  |  
| Downloads | <span data-ttu-id="3f60f-171">オン</span><span class="sxs-lookup"><span data-stu-id="3f60f-171">On</span></span> | <span data-ttu-id="3f60f-172">あり</span><span class="sxs-lookup"><span data-stu-id="3f60f-172">Yes</span></span> | <span data-ttu-id="3f60f-173">WebView2 には、ダウンロード UI をカスタマイズしてダウンロードを操作できる API が提供されています。</span><span class="sxs-lookup"><span data-stu-id="3f60f-173">WebView2 provides an API that allows you to customize the download UI to manipulate downloads.</span></span> <span data-ttu-id="3f60f-174">たとえば、ブロック、リダイレクト、保存、一時停止などです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-174">For example, you can block, redirect, save, pause, and so on.</span></span>  <!--For more information, navigate to [download API][Webview2ReferenceDownloadApi].--> |  
| Edge Shopping | <span data-ttu-id="3f60f-175">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-175">Off</span></span> | <span data-ttu-id="3f60f-176">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-176">No</span></span> | <span data-ttu-id="3f60f-177">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-177">This feature is turned off.</span></span>  |  
| Family Safety | <span data-ttu-id="3f60f-178">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-178">Off</span></span> | <span data-ttu-id="3f60f-179">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-179">No</span></span> | <span data-ttu-id="3f60f-180">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-180">This feature is turned off.</span></span>  |  
| Favorites | <span data-ttu-id="3f60f-181">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-181">Off</span></span> | <span data-ttu-id="3f60f-182">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-182">No</span></span> | <span data-ttu-id="3f60f-183">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-183">This feature is turned off.</span></span>  |  
| IE Mode | <span data-ttu-id="3f60f-184">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-184">Off</span></span> | <span data-ttu-id="3f60f-185">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-185">No</span></span> | <span data-ttu-id="3f60f-186">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-186">This feature is turned off.</span></span> <span data-ttu-id="3f60f-187">WebView2 は IE モードをサポートし、IE と比較して動作の違いがあります (MHT サポートなど)。</span><span class="sxs-lookup"><span data-stu-id="3f60f-187">WebView2 doesn't support IE mode and has differences in behavior compared to IE (such as MHT support).</span></span> |  
| Immersive Reader | <span data-ttu-id="3f60f-188">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-188">Off</span></span> | <span data-ttu-id="3f60f-189">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-189">No</span></span> | <span data-ttu-id="3f60f-190">この機能は、操作のブラウザー UI によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-190">This feature depends on the browser UI for interaction.</span></span>  <span data-ttu-id="3f60f-191">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-191">This feature is turned off.</span></span>  |  
| Intrusive Ads | <span data-ttu-id="3f60f-192">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-192">Off</span></span> | <span data-ttu-id="3f60f-193">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-193">No</span></span> | <span data-ttu-id="3f60f-194">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-194">This feature is turned off.</span></span>  |  
| <span data-ttu-id="3f60f-195">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="3f60f-195">Keyboard shortcuts</span></span> | <span data-ttu-id="3f60f-196">レビューの詳細</span><span class="sxs-lookup"><span data-stu-id="3f60f-196">Review Details</span></span> | <span data-ttu-id="3f60f-197">レビューの詳細</span><span class="sxs-lookup"><span data-stu-id="3f60f-197">Review Details</span></span> | <span data-ttu-id="3f60f-198">既定でオフになっているキーボード ショートカットは、意味をなさないか、WebView2 で問題を引き起こします。</span><span class="sxs-lookup"><span data-stu-id="3f60f-198">The keyboard shortcuts that are turned off by default either don't make sense or cause problems in WebView2.</span></span>  <span data-ttu-id="3f60f-199">これらのショートカットを有効またはオフにしない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-199">You may not turn on or off these shortcuts.</span></span>  <span data-ttu-id="3f60f-200">代わりに、イベントを使用してキーの組み合わせをリッスンし、必要に応じてカスタム `AcceleratorKeyPressed` 応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3f60f-200">Instead, you may listen for a key combination using the `AcceleratorKeyPressed` event and create a custom response if needed.</span></span>  <span data-ttu-id="3f60f-201">詳細については、「その他のキーボード [ショートカット情報」に移動します](#additional-keyboard-shortcuts-information)。</span><span class="sxs-lookup"><span data-stu-id="3f60f-201">For more information, navigate to [Additional keyboard shortcuts information](#additional-keyboard-shortcuts-information).</span></span> |  
| <span data-ttu-id="3f60f-202">プッシュ通知</span><span class="sxs-lookup"><span data-stu-id="3f60f-202">Push notifications</span></span> | <span data-ttu-id="3f60f-203">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-203">Off</span></span> | <span data-ttu-id="3f60f-204">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-204">No</span></span> | <span data-ttu-id="3f60f-205">この機能は WebView2 では実装されていません。</span><span class="sxs-lookup"><span data-stu-id="3f60f-205">This feature is not implemented in WebView2.</span></span>  <span data-ttu-id="3f60f-206">詳細については [、「HTML5 通知 API のサポートの追加 (#308) 」を参照してください][GithubMicrosoftedgeWebview2feedbackIssues308]。</span><span class="sxs-lookup"><span data-stu-id="3f60f-206">For more information, navigate to [Add support for HTML5 Notification API (#308)][GithubMicrosoftedgeWebview2feedbackIssues308].</span></span> |  
| Read Aloud | <span data-ttu-id="3f60f-207">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-207">Off</span></span> | <span data-ttu-id="3f60f-208">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-208">No</span></span> | <span data-ttu-id="3f60f-209">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-209">This feature is turned off.</span></span>  |  
| Smart Screen | <span data-ttu-id="3f60f-210">オン</span><span class="sxs-lookup"><span data-stu-id="3f60f-210">On</span></span>`*` | <span data-ttu-id="3f60f-211">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-211">No</span></span> | `*` <span data-ttu-id="3f60f-212">この機能の UI は削除されましたが、基になる機能は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f60f-212">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="3f60f-213">また、コマンド ライン スイッチを Smart Screen 使用してオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3f60f-213">Additionally, you may turn off Smart Screen using a command-line switch.</span></span>  |  
| Translate | <span data-ttu-id="3f60f-214">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-214">Off</span></span> | <span data-ttu-id="3f60f-215">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-215">No</span></span> | <span data-ttu-id="3f60f-216">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-216">This feature is turned off.</span></span>  |  
| Tracking Prevention | <span data-ttu-id="3f60f-217">オン</span><span class="sxs-lookup"><span data-stu-id="3f60f-217">On</span></span>`*` | <span data-ttu-id="3f60f-218">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-218">No</span></span> | `*` <span data-ttu-id="3f60f-219">この機能の UI は削除されましたが、基になる機能は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f60f-219">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="3f60f-220">追跡防止は常にバランスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f60f-220">Tracking prevention is always set to balanced.</span></span>|  
| Profile and Identity | <span data-ttu-id="3f60f-221">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-221">Off</span></span> | <span data-ttu-id="3f60f-222">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-222">No</span></span> | <span data-ttu-id="3f60f-223">お気に入り、Cookie などと同期する機能はオフになります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-223">The feature that syncs your favorites, cookies, and so on, is turned off.</span></span>  |  
| Web Payment API | <span data-ttu-id="3f60f-224">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-224">Off</span></span> | <span data-ttu-id="3f60f-225">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-225">No</span></span> | <span data-ttu-id="3f60f-226">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-226">This feature is turned off.</span></span>  | 
| Windows Defender Application Guard | <span data-ttu-id="3f60f-227">オフ</span><span class="sxs-lookup"><span data-stu-id="3f60f-227">Off</span></span> | <span data-ttu-id="3f60f-228">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-228">No</span></span> | <span data-ttu-id="3f60f-229">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="3f60f-229">This feature is turned off.</span></span>  |  
| edge:// URLs | <span data-ttu-id="3f60f-230">レビューの詳細</span><span class="sxs-lookup"><span data-stu-id="3f60f-230">Review Details</span></span> | <span data-ttu-id="3f60f-231">なし</span><span class="sxs-lookup"><span data-stu-id="3f60f-231">No</span></span> | <span data-ttu-id="3f60f-232">設定ブラウザーのMicrosoft Edge URL です `edge://` 。</span><span class="sxs-lookup"><span data-stu-id="3f60f-232">Settings for the Microsoft Edge browser are on `edge://` URLs.</span></span>  <span data-ttu-id="3f60f-233">これらの Web ページの多Microsoft Edge、WebView2 のコンテキスト内では意味をなさないので、これらの URL の一部は無効になります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-233">Because most of these webpages have Microsoft Edge branding or don't make sense within the context of WebView2, some of these URLs are turned off.</span></span>  <span data-ttu-id="3f60f-234">詳細については、「ブロックされた内部 [URL」に移動します](#blocked-internal-urls)。</span><span class="sxs-lookup"><span data-stu-id="3f60f-234">For more information, navigate to [Blocked internal URLs](#blocked-internal-urls).</span></span>  |  

## <a name="blocked-internal-urls"></a><span data-ttu-id="3f60f-235">ブロックされた内部 URL</span><span class="sxs-lookup"><span data-stu-id="3f60f-235">Blocked internal URLs</span></span>  

<span data-ttu-id="3f60f-236">次のMicrosoft Edge Google Chrome 設定の Web ページは WebView2 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="3f60f-236">The following Microsoft Edge and Google Chrome settings webpages aren't available in WebView2.</span></span>  

*   `chrome-search://local-ntp/local-ntp.html`  
*   `edge://application-guard-internals`  
*   `edge://apps`  
*   `edge://compat`  
*   `edge://extensions`  
*   `edge://favorites`  
*   `edge://help`  
*   `edge://management`  
*   `edge://network-error`  
*   `edge://new-tab-page`  
*   `edge://newtab`  
*   `edge://omnibox`  
*   `edge://settings`  
*   `edge://supervised-user-internals`  
*   `edge://version`  
    
## <a name="additional-keyboard-shortcuts-information"></a><span data-ttu-id="3f60f-237">その他のキーボード ショートカット情報</span><span class="sxs-lookup"><span data-stu-id="3f60f-237">Additional keyboard shortcuts information</span></span>  

<span data-ttu-id="3f60f-238">キーボード ショートカットまたはキー バインドは、WebView2 Microsoft Edgeサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3f60f-238">Keyboard shortcuts or key bindings are supported in Microsoft Edge and WebView2.</span></span>  <span data-ttu-id="3f60f-239">更新Microsoft Edge、既定のキー バインドが変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-239">When Microsoft Edge updates, the default key bindings may change.</span></span>  <span data-ttu-id="3f60f-240">さらに、WebView2 で機能がサポートされている場合は、既定で無効になっているキーボード ショートカットが有効になります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-240">Furthermore, a keyboard shortcut that is turned off by default may turn on if the feature is now supported in WebView2.</span></span>  <span data-ttu-id="3f60f-241">キーボード ショートカットの変更を避けるため、ブラウザー機能にアクセスするキーはすべて無効にし、基本的なテキスト編集ショートカットと移動ショートカットはすべてオンに維持します `AreBrowserAcceleratorKeysEnabled` `FALSE` 。</span><span class="sxs-lookup"><span data-stu-id="3f60f-241">To avoid changes to your keyboard shortcuts, you may set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, which turns off all keys that access browser features, but keeps all basic text-editing and movement shortcuts turned on.</span></span>  

<span data-ttu-id="3f60f-242">次の表に、WebView2 で常に無効になっているショートカットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3f60f-242">The following table lists the shortcuts that are always turned off in WebView2.</span></span>  <span data-ttu-id="3f60f-243">アスタリスク \( \) 文字は、ショートカットがオフではないが、アクセスする機能がオフになっているか、WebView2 に適用されません。 `*`</span><span class="sxs-lookup"><span data-stu-id="3f60f-243">An asterisk \(`*`\) character indicates that the shortcut isn't turned off, but the feature it accesses is turned off or doesn't apply to WebView2.</span></span>  

| <span data-ttu-id="3f60f-244">操作</span><span class="sxs-lookup"><span data-stu-id="3f60f-244">Action</span></span> | <span data-ttu-id="3f60f-245">Windows</span><span class="sxs-lookup"><span data-stu-id="3f60f-245">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="3f60f-246">に追加する</span><span class="sxs-lookup"><span data-stu-id="3f60f-246">Add to</span></span> Favorites | `Ctrl`+`D` |  
| <span data-ttu-id="3f60f-247">[すべてのタブの追加]</span><span class="sxs-lookup"><span data-stu-id="3f60f-247">Add All Tabs to</span></span> Favorites | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="3f60f-248">フォーカスの場所</span><span class="sxs-lookup"><span data-stu-id="3f60f-248">Focus Location</span></span> | `Ctrl`+`L, Alt`+`D` |  
| <span data-ttu-id="3f60f-249">貼り付けと移動</span><span class="sxs-lookup"><span data-stu-id="3f60f-249">Paste and Go</span></span> | `Ctrl`+`Shift`+`L` |  
| <span data-ttu-id="3f60f-250">ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="3f60f-250">Open File</span></span> | `Ctrl`+`O` |  
| Read Aloud `*` | `Ctrl`+`Shift`+`U` |  
| <span data-ttu-id="3f60f-251">Web キャプチャ</span><span class="sxs-lookup"><span data-stu-id="3f60f-251">Web Capture</span></span> `*` | `Ctrl`+`Shift`+`S` |  
| <span data-ttu-id="3f60f-252">サイドバー</span><span class="sxs-lookup"><span data-stu-id="3f60f-252">Sidebar</span></span> `*` | `Ctrl`+`Shift`+`E` |  
| <span data-ttu-id="3f60f-253">[ページの保存]</span><span class="sxs-lookup"><span data-stu-id="3f60f-253">Save Page</span></span> | `Ctrl`+`S` |  
| <span data-ttu-id="3f60f-254">[最後のタブ] を選択する</span><span class="sxs-lookup"><span data-stu-id="3f60f-254">Select Last Tab</span></span> | `Ctrl`+`9` |  
| <span data-ttu-id="3f60f-255">[次へ] タブを選択する</span><span class="sxs-lookup"><span data-stu-id="3f60f-255">Select Next Tab</span></span> | `Ctrl`+`Tab` |  
| <span data-ttu-id="3f60f-256">[前へ] タブを選択する</span><span class="sxs-lookup"><span data-stu-id="3f60f-256">Select Previous Tab</span></span> | `Ctrl`+`Shift`+`Tab` |  
| <span data-ttu-id="3f60f-257">Tab \(1 - 8\) を選択する</span><span class="sxs-lookup"><span data-stu-id="3f60f-257">Select Tab \(1 - 8\)</span></span> | `Ctrl`+`(1-8)` |  
| <span data-ttu-id="3f60f-258">[バーの Favorites 表示]</span><span class="sxs-lookup"><span data-stu-id="3f60f-258">Show Favorites Bar</span></span> `*` | `Ctrl`+`Shift`+`B` |  
| <span data-ttu-id="3f60f-259">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="3f60f-259">Help</span></span> | `F1` |  
| <span data-ttu-id="3f60f-260">[次のウィンドウにフォーカス]</span><span class="sxs-lookup"><span data-stu-id="3f60f-260">Focus Next Pane</span></span> `*` | `F6` |  
| <span data-ttu-id="3f60f-261">[前のウィンドウにフォーカス]</span><span class="sxs-lookup"><span data-stu-id="3f60f-261">Focus Previous Pane</span></span> `*` | `Shift`+`F6` |  
| <span data-ttu-id="3f60f-262">キャレットブラウズ</span><span class="sxs-lookup"><span data-stu-id="3f60f-262">Caret Browsing</span></span> `*` | `F7` |  
| <span data-ttu-id="3f60f-263">閲覧ビュー</span><span class="sxs-lookup"><span data-stu-id="3f60f-263">Reading View</span></span> `*` | `F9` |  
| <span data-ttu-id="3f60f-264">フォーカス メニュー バー</span><span class="sxs-lookup"><span data-stu-id="3f60f-264">Focus Menu Bar</span></span> | `F10` |  
| <span data-ttu-id="3f60f-265">[ID の表示] メニュー</span><span class="sxs-lookup"><span data-stu-id="3f60f-265">Show Identity Menu</span></span> `*` | `Ctrl`+`Shift`+`M` |  
| Browser Task Manager `*` | `Shift`+`Escape` |  
| <span data-ttu-id="3f60f-266">エッジ フィードバック</span><span class="sxs-lookup"><span data-stu-id="3f60f-266">Edge Feedback</span></span> `*` | `Shift`+`Alt`+`I` |  
| <span data-ttu-id="3f60f-267">[ミュート] タブ</span><span class="sxs-lookup"><span data-stu-id="3f60f-267">Mute Tab</span></span> `*` | `Ctrl`+`M` |  
| <span data-ttu-id="3f60f-268">新しいシークレット ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3f60f-268">New Incognito Window</span></span> | `Ctrl`+`Shift`+`N` |  
| <span data-ttu-id="3f60f-269">新しいタブ</span><span class="sxs-lookup"><span data-stu-id="3f60f-269">New Tab</span></span> | `Ctrl`+`T` |  
| <span data-ttu-id="3f60f-270">新しいウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3f60f-270">New Window</span></span> | `Ctrl`+`N` |  
| <span data-ttu-id="3f60f-271">[最後に閉じたタブを復元]</span><span class="sxs-lookup"><span data-stu-id="3f60f-271">Restore Last Closed Tab</span></span> | `Ctrl`+`Shift`+`T` |  
| <span data-ttu-id="3f60f-272">Focus</span><span class="sxs-lookup"><span data-stu-id="3f60f-272">Focus</span></span> Favorites | `Alt`+`Shift`+`B` |  
| <span data-ttu-id="3f60f-273">フォーカス 非アクティブ ポップアップ</span><span class="sxs-lookup"><span data-stu-id="3f60f-273">Focus Inactive Popup</span></span> | `Alt`+`Shift`+`A` |  
| <span data-ttu-id="3f60f-274">フォーカス検索</span><span class="sxs-lookup"><span data-stu-id="3f60f-274">Focus Search</span></span> | `Ctrl`<span data-ttu-id="3f60f-275">+`E`, `Ctrl`+`K`,</span><span class="sxs-lookup"><span data-stu-id="3f60f-275">+`E`, `Ctrl`+`K`,</span></span> `Search Key` |  
| <span data-ttu-id="3f60f-276">[重複] タブ</span><span class="sxs-lookup"><span data-stu-id="3f60f-276">Duplicate Tab</span></span> | `Ctrl`+`Shift`+`K` |  
| <span data-ttu-id="3f60f-277">フォーカス ツールバー</span><span class="sxs-lookup"><span data-stu-id="3f60f-277">Focus Toolbar</span></span> `*` | `Alt`+`Shift`+`T` |  
| <span data-ttu-id="3f60f-278">Home</span><span class="sxs-lookup"><span data-stu-id="3f60f-278">Home</span></span> | `Alt`<span data-ttu-id="3f60f-279">+`Home`,</span><span class="sxs-lookup"><span data-stu-id="3f60f-279">+`Home`,</span></span> `Browser Home Key` |  
| <span data-ttu-id="3f60f-280">[アプリ の表示] メニュー</span><span class="sxs-lookup"><span data-stu-id="3f60f-280">Show App Menu</span></span> | `Alt`+`E, Alt`+`F` |  
| <span data-ttu-id="3f60f-281">注文詳細</span><span class="sxs-lookup"><span data-stu-id="3f60f-281">Show</span></span> Favorites | `Ctrl`+`Shift`+`O` |  
| <span data-ttu-id="3f60f-282">注文詳細</span><span class="sxs-lookup"><span data-stu-id="3f60f-282">Show</span></span> Downloads | `Ctrl`+`J` |  
| <span data-ttu-id="3f60f-283">履歴の表示</span><span class="sxs-lookup"><span data-stu-id="3f60f-283">Show History</span></span> | `Ctrl`+`H` |  
| <span data-ttu-id="3f60f-284">読み取りモード バーを表示する</span><span class="sxs-lookup"><span data-stu-id="3f60f-284">Show Reading Mode Bar</span></span> `*` | `Shift`+`Alt`+`R` |  
| <span data-ttu-id="3f60f-285">注文詳細</span><span class="sxs-lookup"><span data-stu-id="3f60f-285">Show</span></span> Collections `*` | `Ctrl`+`Shift`+`Y` |  

<span data-ttu-id="3f60f-286">イベントが処理されていないときに表示されるウィンドウを除き、次のキーボード ショートカットは常 `NewWindowRequested` にオフになります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-286">The following keyboard shortcuts are always turned off, except in windows that display when the `NewWindowRequested` event isn't handled.</span></span>

| <span data-ttu-id="3f60f-287">操作</span><span class="sxs-lookup"><span data-stu-id="3f60f-287">Action</span></span> | <span data-ttu-id="3f60f-288">Windows</span><span class="sxs-lookup"><span data-stu-id="3f60f-288">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="3f60f-289">タブを閉じる</span><span class="sxs-lookup"><span data-stu-id="3f60f-289">Close Tab</span></span> | `Ctrl`+`W, Ctrl`+`F4` |  
| <span data-ttu-id="3f60f-290">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="3f60f-290">Close Window</span></span> | `Ctrl`+`Shift`+`W` |  
| <span data-ttu-id="3f60f-291">全画面表示</span><span class="sxs-lookup"><span data-stu-id="3f60f-291">Fullscreen</span></span> | `F11` |  

<span data-ttu-id="3f60f-292">に設定すると `AreBrowserAcceleratorKeysEnabled` `FALSE` 、次の追加のキーボード ショートカットがオフになります。</span><span class="sxs-lookup"><span data-stu-id="3f60f-292">If you set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, the following additional keyboard shortcuts are turned off.</span></span>  

| <span data-ttu-id="3f60f-293">操作</span><span class="sxs-lookup"><span data-stu-id="3f60f-293">Action</span></span> | <span data-ttu-id="3f60f-294">Windows</span><span class="sxs-lookup"><span data-stu-id="3f60f-294">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="3f60f-295">Stop</span><span class="sxs-lookup"><span data-stu-id="3f60f-295">Stop</span></span> | `Escape` |  
| <span data-ttu-id="3f60f-296">ページで検索する</span><span class="sxs-lookup"><span data-stu-id="3f60f-296">Find on Page</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="3f60f-297">[次へ] を検索する</span><span class="sxs-lookup"><span data-stu-id="3f60f-297">Find Next</span></span> | `Ctrl`+`G` |  
| <span data-ttu-id="3f60f-298">前の検索</span><span class="sxs-lookup"><span data-stu-id="3f60f-298">Find Previous</span></span> | `Ctrl`+`Shift`+`G` |  
| <span data-ttu-id="3f60f-299">印刷</span><span class="sxs-lookup"><span data-stu-id="3f60f-299">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="3f60f-300">Refresh</span><span class="sxs-lookup"><span data-stu-id="3f60f-300">Refresh</span></span> | `Ctrl`<span data-ttu-id="3f60f-301">+`R`, `F5`,</span><span class="sxs-lookup"><span data-stu-id="3f60f-301">+`R`, `F5`,</span></span> `Reload Key` |  
| <span data-ttu-id="3f60f-302">キャッシュなしの更新</span><span class="sxs-lookup"><span data-stu-id="3f60f-302">Refresh Without Cache</span></span> | `Ctrl`<span data-ttu-id="3f60f-303">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span><span class="sxs-lookup"><span data-stu-id="3f60f-303">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span></span>`Refresh` |  
| <span data-ttu-id="3f60f-304">ズームアウト</span><span class="sxs-lookup"><span data-stu-id="3f60f-304">Zoom Out</span></span> | `Ctrl`+`-` |  
| <span data-ttu-id="3f60f-305">拡大</span><span class="sxs-lookup"><span data-stu-id="3f60f-305">Zoom In</span></span> | `Ctrl`+`+` |  
| <span data-ttu-id="3f60f-306">ズームのリセット</span><span class="sxs-lookup"><span data-stu-id="3f60f-306">Reset Zoom</span></span> | `Ctrl`+`0` |  
| <span data-ttu-id="3f60f-307">[次へ] を検索する</span><span class="sxs-lookup"><span data-stu-id="3f60f-307">Find Next</span></span> | `F3` |  
| <span data-ttu-id="3f60f-308">前の検索</span><span class="sxs-lookup"><span data-stu-id="3f60f-308">Find Previous</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="3f60f-309">戻る</span><span class="sxs-lookup"><span data-stu-id="3f60f-309">Back</span></span> | `Alt`+`Left, Browser Back Key` |  
| <span data-ttu-id="3f60f-310">Forward</span><span class="sxs-lookup"><span data-stu-id="3f60f-310">Forward</span></span> | `Alt`<span data-ttu-id="3f60f-311">+`Right`,</span><span class="sxs-lookup"><span data-stu-id="3f60f-311">+`Right`,</span></span> `Browser Forward Key` |  
| <span data-ttu-id="3f60f-312">印刷</span><span class="sxs-lookup"><span data-stu-id="3f60f-312">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="3f60f-313">DevTools を開く/閉じる</span><span class="sxs-lookup"><span data-stu-id="3f60f-313">Open / Close DevTools</span></span> | `Ctrl`+`Shift`+`I` |  
| <span data-ttu-id="3f60f-314">DevTools コンソールを開く</span><span class="sxs-lookup"><span data-stu-id="3f60f-314">Open DevTools Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="3f60f-315">Open DevTools Inspect</span><span class="sxs-lookup"><span data-stu-id="3f60f-315">Open DevTools Inspect</span></span> | `Ctrl`+`Shift`+`C` |  

> [!Note] 
> <span data-ttu-id="3f60f-316">キーを個別にカスタマイズするには [、AcceleratorKeyPressed イベントを使用][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] します。</span><span class="sxs-lookup"><span data-stu-id="3f60f-316">To customize any of the keys individually, use the [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] event.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview2-team"></a><span data-ttu-id="3f60f-317">WebView2 チームと連絡を取Microsoft Edgeする</span><span class="sxs-lookup"><span data-stu-id="3f60f-317">Getting in touch with the Microsoft Edge WebView2 team</span></span>  

[!INCLUDE [contact WebView2 team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

<!--[Webview2ReferenceDownloadApi]: ./download-api.md "download API | Microsoft Docs"  -->  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2controller.acceleratorkeypressed?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2Controller.AcceleratorKeyPressed イベント |Microsoft Docs"  

[DevtoolsShortcutsIndex]: ../../devtools-guide-chromium/shortcuts/index.md "Microsoft EdgeDevTools キーボード ショートカット |Microsoft Docs"  

[GithubMicrosoftedgeWebview2feedbackIssues308]: https://github.com/MicrosoftEdge/WebView2Feedback/issues/308 "HTML5 通知 API (#308) |GitHub"  

[PeterExperimentsChromiumCommandLineSwitches]: https://peter.sh/experiments/chromium-command-line-switches "コマンド ライン スイッチChromiumの一覧|Peter Beverloo"  
