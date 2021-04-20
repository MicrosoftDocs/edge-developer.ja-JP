---
<span data-ttu-id="702f2-101">説明: Microsoft Edge と WebView2 タイトルの機能の違い: Microsoft Edge と WebView2 作成者の機能の違い: MSEdgeTeam ms.author: msedgedevrel ms.date: 04/19/2021 ms.topic: conceptual ms.prod: microsoft-edge ms.technology: webview キーワード: IWebView2, IWebView2WebView、WebView2、Webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html no-loc:</span><span class="sxs-lookup"><span data-stu-id="702f2-101">description: Feature differences between Microsoft Edge and WebView2 title: Feature differences between Microsoft Edge and WebView2 author: MSEdgeTeam ms.author: msedgedevrel ms.date: 04/19/2021 ms.topic: conceptual ms.prod: microsoft-edge ms.technology: webview keywords: IWebView2, IWebView2WebView, WebView2, webview, wpf apps, wpf, edge, ICoreWebView2, ICoreWebView2Host, browser control, edge html no-loc:</span></span>
- <span data-ttu-id="702f2-102">"Autofill for Addresses"</span><span class="sxs-lookup"><span data-stu-id="702f2-102">"Autofill for Addresses"</span></span>
- <span data-ttu-id="702f2-103">"Autofill for Passwords"</span><span class="sxs-lookup"><span data-stu-id="702f2-103">"Autofill for Passwords"</span></span>
- <span data-ttu-id="702f2-104">"Autofill for Payments""</span><span class="sxs-lookup"><span data-stu-id="702f2-104">"Autofill for Payments""</span></span>
- <span data-ttu-id="702f2-105">"Browser Extensions""</span><span class="sxs-lookup"><span data-stu-id="702f2-105">"Browser Extensions""</span></span>
- <span data-ttu-id="702f2-106">"Browser Task Manager"</span><span class="sxs-lookup"><span data-stu-id="702f2-106">"Browser Task Manager"</span></span>
- <span data-ttu-id="702f2-107">"Collections"</span><span class="sxs-lookup"><span data-stu-id="702f2-107">"Collections"</span></span>
- <span data-ttu-id="702f2-108">"Continue-where-I-left-off prompt"</span><span class="sxs-lookup"><span data-stu-id="702f2-108">"Continue-where-I-left-off prompt"</span></span>
- <span data-ttu-id="702f2-109">"Downloads"</span><span class="sxs-lookup"><span data-stu-id="702f2-109">"Downloads"</span></span>
- <span data-ttu-id="702f2-110">"Edge Shopping"</span><span class="sxs-lookup"><span data-stu-id="702f2-110">"Edge Shopping"</span></span>
- <span data-ttu-id="702f2-111">"Family Safety"</span><span class="sxs-lookup"><span data-stu-id="702f2-111">"Family Safety"</span></span>
- <span data-ttu-id="702f2-112">"Favorites"</span><span class="sxs-lookup"><span data-stu-id="702f2-112">"Favorites"</span></span>
- <span data-ttu-id="702f2-113">"Hotkeys"</span><span class="sxs-lookup"><span data-stu-id="702f2-113">"Hotkeys"</span></span>
- <span data-ttu-id="702f2-114">"IE Mode"</span><span class="sxs-lookup"><span data-stu-id="702f2-114">"IE Mode"</span></span>
- <span data-ttu-id="702f2-115">"Immersive Reader"</span><span class="sxs-lookup"><span data-stu-id="702f2-115">"Immersive Reader"</span></span>
- <span data-ttu-id="702f2-116">"Intrusive Ads"</span><span class="sxs-lookup"><span data-stu-id="702f2-116">"Intrusive Ads"</span></span>
- <span data-ttu-id="702f2-117">"Read Aloud"</span><span class="sxs-lookup"><span data-stu-id="702f2-117">"Read Aloud"</span></span>
- <span data-ttu-id="702f2-118">"Smart Screen"</span><span class="sxs-lookup"><span data-stu-id="702f2-118">"Smart Screen"</span></span>
- <span data-ttu-id="702f2-119">"Translate"</span><span class="sxs-lookup"><span data-stu-id="702f2-119">"Translate"</span></span>
- <span data-ttu-id="702f2-120">"Tracking Prevention"</span><span class="sxs-lookup"><span data-stu-id="702f2-120">"Tracking Prevention"</span></span>
- <span data-ttu-id="702f2-121">"Profile and Identity"</span><span class="sxs-lookup"><span data-stu-id="702f2-121">"Profile and Identity"</span></span>
- <span data-ttu-id="702f2-122">"Web Payment API"</span><span class="sxs-lookup"><span data-stu-id="702f2-122">"Web Payment API"</span></span>
- <span data-ttu-id="702f2-123">"Windows Defender Application Guard"</span><span class="sxs-lookup"><span data-stu-id="702f2-123">"Windows Defender Application Guard"</span></span>
- <span data-ttu-id="702f2-124">"edge:// URLs"</span><span class="sxs-lookup"><span data-stu-id="702f2-124">"edge:// URLs"</span></span>

---
# <a name="browser-feature-differences-between-microsoft-edge-and-webview2"></a><span data-ttu-id="702f2-125">Microsoft Edge と WebView2 のブラウザー機能の違い</span><span class="sxs-lookup"><span data-stu-id="702f2-125">Browser feature differences between Microsoft Edge and WebView2</span></span>  

<span data-ttu-id="702f2-126">WebView2 は、新しい Microsoft Edge ブラウザーに基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="702f2-126">WebView2 is based on the new Microsoft Edge browser.</span></span>  <span data-ttu-id="702f2-127">ブラウザーから WebView2 ベースのアプリに機能を拡張する機会があります。これは便利です。</span><span class="sxs-lookup"><span data-stu-id="702f2-127">You have the opportunity to extend features from the browser to WebView2-based apps, which is useful.</span></span>  <span data-ttu-id="702f2-128">ただし、WebView2 はブラウザーのようなアプリに限定されないので、変更または削除する必要があるブラウザー機能があります。</span><span class="sxs-lookup"><span data-stu-id="702f2-128">However, since WebView2 isn't limited to browser-like apps, there are some browser features that need to be modified or removed.</span></span>  <span data-ttu-id="702f2-129">この記事では、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="702f2-129">This article provides the following information.</span></span>  

*   <span data-ttu-id="702f2-130">変更されたブラウザー機能とサポート情報。</span><span class="sxs-lookup"><span data-stu-id="702f2-130">The modified browser features and supporting information.</span></span>   
*   <span data-ttu-id="702f2-131">機能のオンとオフを切り替える機能。</span><span class="sxs-lookup"><span data-stu-id="702f2-131">The ability to turn on or off the feature.</span></span>  
*   <span data-ttu-id="702f2-132">キーボード ショートカットに関するガイダンス。</span><span class="sxs-lookup"><span data-stu-id="702f2-132">Guidance on keyboard shortcuts.</span></span>  
    
## <a name="design-guidelines"></a><span data-ttu-id="702f2-133">設計ガイドライン</span><span class="sxs-lookup"><span data-stu-id="702f2-133">Design guidelines</span></span>  

<span data-ttu-id="702f2-134">WebView2 のコンテキストでは、ブラウザー機能は次の設計ガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="702f2-134">In the context of WebView2, browser features adhere to the following design guidelines.</span></span>  

*   <span data-ttu-id="702f2-135">ほとんどの機能は、WebView2 と Microsoft Edge で同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="702f2-135">Most features work the same in WebView2 and Microsoft Edge.</span></span>  <span data-ttu-id="702f2-136">WebView2 のコンテキストや他の理由で機能が意味をなさない場合、機能は変更または無効になります。</span><span class="sxs-lookup"><span data-stu-id="702f2-136">If a feature doesn't make sense in the context of WebView2 or for other reasons, the feature is modified or turned off.</span></span> 
*   <span data-ttu-id="702f2-137">WebView2 の機能には、Microsoft Edge のブランド化は含めかねない。</span><span class="sxs-lookup"><span data-stu-id="702f2-137">WebView2 features don't include Microsoft Edge branding.</span></span>  
    
## <a name="features"></a><span data-ttu-id="702f2-138">機能</span><span class="sxs-lookup"><span data-stu-id="702f2-138">Features</span></span>  

<span data-ttu-id="702f2-139">次の表に、Microsoft Edge ブラウザーとは異なる WebView2 機能を示します。</span><span class="sxs-lookup"><span data-stu-id="702f2-139">The following table displays the WebView2 features that differ from the Microsoft Edge browser.</span></span>   

*   <span data-ttu-id="702f2-140">**既定の** 状態は、機能が新しい WebView2 インスタンスの既定のエクスペリエンスの一部を示します。</span><span class="sxs-lookup"><span data-stu-id="702f2-140">**Default state** indicates that the feature is part of the default experience on a new WebView2 instance.</span></span>  
*   <span data-ttu-id="702f2-141">**[構成** 可能] は、WebView2 API またはコマンド ライン スイッチを使用して機能を有効またはオフにできる可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="702f2-141">**Configurable** indicates that you may turn on or off the feature using WebView2 APIs or command-line switches.</span></span>  
    
> [!NOTE]  
> <span data-ttu-id="702f2-142">この記事では、コマンド ライン スイッチを使用した機能の変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="702f2-142">This article doesn't cover modifying features using command-line switches.</span></span>  <span data-ttu-id="702f2-143">コマンド ライン スイッチを使用して機能をオンまたはオフにする方法の詳細については、「クロム コマンド ライン スイッチの一覧 [」に移動します][PeterExperimentsChromiumCommandLineSwitches]。</span><span class="sxs-lookup"><span data-stu-id="702f2-143">For more information about turning on and off features with command-line switches, navigate to [List of Chromium Command Line Switches][PeterExperimentsChromiumCommandLineSwitches].</span></span>  
    
| <span data-ttu-id="702f2-144">機能</span><span class="sxs-lookup"><span data-stu-id="702f2-144">Feature</span></span> | <span data-ttu-id="702f2-145">既定の状態</span><span class="sxs-lookup"><span data-stu-id="702f2-145">Default state</span></span> | <span data-ttu-id="702f2-146">構成可能</span><span class="sxs-lookup"><span data-stu-id="702f2-146">Configurable</span></span> | <span data-ttu-id="702f2-147">詳細</span><span class="sxs-lookup"><span data-stu-id="702f2-147">Details</span></span> |  
|:--- |:--- |:--- | :--- |  
| Autofill for Addresses | <span data-ttu-id="702f2-148">オン</span><span class="sxs-lookup"><span data-stu-id="702f2-148">On</span></span> | <span data-ttu-id="702f2-149">はい</span><span class="sxs-lookup"><span data-stu-id="702f2-149">Yes</span></span> | <span data-ttu-id="702f2-150">この機能は既定でオンになっています。WebView2 オートフィル API を使用してオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="702f2-150">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| Autofill for Passwords | <span data-ttu-id="702f2-151">オン</span><span class="sxs-lookup"><span data-stu-id="702f2-151">On</span></span> | <span data-ttu-id="702f2-152">はい</span><span class="sxs-lookup"><span data-stu-id="702f2-152">Yes</span></span> | <span data-ttu-id="702f2-153">この機能は既定でオンになっています。WebView2 オートフィル API を使用してオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="702f2-153">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| <span data-ttu-id="702f2-154">支払いの自動入力</span><span class="sxs-lookup"><span data-stu-id="702f2-154">Autofill for Payments</span></span> | <span data-ttu-id="702f2-155">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-155">Off</span></span> | <span data-ttu-id="702f2-156">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-156">No</span></span> | <span data-ttu-id="702f2-157">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-157">This feature is turned off.</span></span>  |  
| <span data-ttu-id="702f2-158">ブラウザー拡張機能</span><span class="sxs-lookup"><span data-stu-id="702f2-158">Browser Extensions</span></span> | <span data-ttu-id="702f2-159">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-159">Off</span></span> | <span data-ttu-id="702f2-160">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-160">No</span></span> | <span data-ttu-id="702f2-161">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-161">This feature is turned off.</span></span>  |  
| Browser Task Manager | <span data-ttu-id="702f2-162">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-162">Off</span></span> | <span data-ttu-id="702f2-163">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-163">No</span></span> | <span data-ttu-id="702f2-164">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-164">This feature is turned off.</span></span>  |  
| Collections | <span data-ttu-id="702f2-165">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-165">Off</span></span> | <span data-ttu-id="702f2-166">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-166">No</span></span> | <span data-ttu-id="702f2-167">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-167">This feature is turned off.</span></span>  |  
| Continue-where-I-left-off prompt | <span data-ttu-id="702f2-168">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-168">Off</span></span> | <span data-ttu-id="702f2-169">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-169">No</span></span> | <span data-ttu-id="702f2-170">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-170">This feature is turned off.</span></span>  |  
| Downloads | <span data-ttu-id="702f2-171">オン</span><span class="sxs-lookup"><span data-stu-id="702f2-171">On</span></span> | <span data-ttu-id="702f2-172">はい</span><span class="sxs-lookup"><span data-stu-id="702f2-172">Yes</span></span> | <span data-ttu-id="702f2-173">WebView2 には、ダウンロード UI をカスタマイズしてダウンロードを操作できる API が提供されています。</span><span class="sxs-lookup"><span data-stu-id="702f2-173">WebView2 provides an API that allows you to customize the download UI to manipulate downloads.</span></span> <span data-ttu-id="702f2-174">たとえば、ブロック、リダイレクト、保存、一時停止などです。</span><span class="sxs-lookup"><span data-stu-id="702f2-174">For example, you can block, redirect, save, pause, and so on.</span></span>  <!--For more information, navigate to [download API][Webview2ReferenceDownloadApi].--> |  
| Edge Shopping | <span data-ttu-id="702f2-175">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-175">Off</span></span> | <span data-ttu-id="702f2-176">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-176">No</span></span> | <span data-ttu-id="702f2-177">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-177">This feature is turned off.</span></span>  |  
| Family Safety | <span data-ttu-id="702f2-178">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-178">Off</span></span> | <span data-ttu-id="702f2-179">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-179">No</span></span> | <span data-ttu-id="702f2-180">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-180">This feature is turned off.</span></span>  |  
| Favorites | <span data-ttu-id="702f2-181">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-181">Off</span></span> | <span data-ttu-id="702f2-182">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-182">No</span></span> | <span data-ttu-id="702f2-183">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-183">This feature is turned off.</span></span>  |  
| IE Mode | <span data-ttu-id="702f2-184">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-184">Off</span></span> | <span data-ttu-id="702f2-185">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-185">No</span></span> | <span data-ttu-id="702f2-186">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-186">This feature is turned off.</span></span>  |  
| Immersive Reader | <span data-ttu-id="702f2-187">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-187">Off</span></span> | <span data-ttu-id="702f2-188">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-188">No</span></span> | <span data-ttu-id="702f2-189">この機能は、操作のブラウザー UI によって異なります。</span><span class="sxs-lookup"><span data-stu-id="702f2-189">This feature depends on the browser UI for interaction.</span></span>  <span data-ttu-id="702f2-190">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-190">This feature is turned off.</span></span>  |  
| Intrusive Ads | <span data-ttu-id="702f2-191">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-191">Off</span></span> | <span data-ttu-id="702f2-192">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-192">No</span></span> | <span data-ttu-id="702f2-193">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-193">This feature is turned off.</span></span>  |  
| <span data-ttu-id="702f2-194">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="702f2-194">Keyboard shortcuts</span></span> | <span data-ttu-id="702f2-195">レビューの詳細</span><span class="sxs-lookup"><span data-stu-id="702f2-195">Review Details</span></span> | <span data-ttu-id="702f2-196">レビューの詳細</span><span class="sxs-lookup"><span data-stu-id="702f2-196">Review Details</span></span> | <span data-ttu-id="702f2-197">既定でオフになっているキーボード ショートカットは、意味をなさないか、WebView2 で問題を引き起こします。</span><span class="sxs-lookup"><span data-stu-id="702f2-197">The keyboard shortcuts that are turned off by default either don't make sense or cause problems in WebView2.</span></span>  <span data-ttu-id="702f2-198">これらのショートカットを有効またはオフにしない場合があります。</span><span class="sxs-lookup"><span data-stu-id="702f2-198">You may not turn on or off these shortcuts.</span></span>  <span data-ttu-id="702f2-199">代わりに、イベントを使用してキーの組み合わせをリッスンし、必要に応じてカスタム `AcceleratorKeyPressed` 応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="702f2-199">Instead, you may listen for a key combination using the `AcceleratorKeyPressed` event and create a custom response if needed.</span></span>  <span data-ttu-id="702f2-200">詳細については、「その他のキーボード [ショートカット情報」に移動します](#additional-keyboard-shortcuts-information)。</span><span class="sxs-lookup"><span data-stu-id="702f2-200">For more information, navigate to [Additional keyboard shortcuts information](#additional-keyboard-shortcuts-information).</span></span> |  
| <span data-ttu-id="702f2-201">プッシュ通知</span><span class="sxs-lookup"><span data-stu-id="702f2-201">Push notifications</span></span> | <span data-ttu-id="702f2-202">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-202">Off</span></span> | <span data-ttu-id="702f2-203">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-203">No</span></span> | <span data-ttu-id="702f2-204">この機能は WebView2 では実装されていません。</span><span class="sxs-lookup"><span data-stu-id="702f2-204">This feature is not implemented in WebView2.</span></span>  <span data-ttu-id="702f2-205">詳細については [、「HTML5 通知 API のサポートの追加 (#308) 」を参照してください][GithubMicrosoftedgeWebview2feedbackIssues308]。</span><span class="sxs-lookup"><span data-stu-id="702f2-205">For more information, navigate to [Add support for HTML5 Notification API (#308)][GithubMicrosoftedgeWebview2feedbackIssues308].</span></span> |  
| Read Aloud | <span data-ttu-id="702f2-206">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-206">Off</span></span> | <span data-ttu-id="702f2-207">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-207">No</span></span> | <span data-ttu-id="702f2-208">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-208">This feature is turned off.</span></span>  |  
| Smart Screen | <span data-ttu-id="702f2-209">オン</span><span class="sxs-lookup"><span data-stu-id="702f2-209">On</span></span>`*` | <span data-ttu-id="702f2-210">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-210">No</span></span> | `*` <span data-ttu-id="702f2-211">この機能の UI は削除されましたが、基になる機能は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="702f2-211">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="702f2-212">また、コマンド ライン スイッチを Smart Screen 使用してオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="702f2-212">Additionally, you may turn off Smart Screen using a command-line switch.</span></span>  |  
| Translate | <span data-ttu-id="702f2-213">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-213">Off</span></span> | <span data-ttu-id="702f2-214">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-214">No</span></span> | <span data-ttu-id="702f2-215">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-215">This feature is turned off.</span></span>  |  
| Tracking Prevention | <span data-ttu-id="702f2-216">オン</span><span class="sxs-lookup"><span data-stu-id="702f2-216">On</span></span>`*` | <span data-ttu-id="702f2-217">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-217">No</span></span> | `*` <span data-ttu-id="702f2-218">この機能の UI は削除されましたが、基になる機能は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="702f2-218">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="702f2-219">追跡防止は常にバランスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="702f2-219">Tracking prevention is always set to balanced.</span></span>|  
| Profile and Identity | <span data-ttu-id="702f2-220">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-220">Off</span></span> | <span data-ttu-id="702f2-221">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-221">No</span></span> | <span data-ttu-id="702f2-222">お気に入り、Cookie などと同期する機能はオフになります。</span><span class="sxs-lookup"><span data-stu-id="702f2-222">The feature that syncs your favorites, cookies, and so on, is turned off.</span></span>  |  
| Web Payment API | <span data-ttu-id="702f2-223">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-223">Off</span></span> | <span data-ttu-id="702f2-224">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-224">No</span></span> | <span data-ttu-id="702f2-225">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-225">This feature is turned off.</span></span>  | 
| Windows Defender Application Guard | <span data-ttu-id="702f2-226">オフ</span><span class="sxs-lookup"><span data-stu-id="702f2-226">Off</span></span> | <span data-ttu-id="702f2-227">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-227">No</span></span> | <span data-ttu-id="702f2-228">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="702f2-228">This feature is turned off.</span></span>  |  
| edge:// URLs | <span data-ttu-id="702f2-229">レビューの詳細</span><span class="sxs-lookup"><span data-stu-id="702f2-229">Review Details</span></span> | <span data-ttu-id="702f2-230">なし</span><span class="sxs-lookup"><span data-stu-id="702f2-230">No</span></span> | <span data-ttu-id="702f2-231">Microsoft Edge ブラウザーの設定は `edge://` URL にあります。</span><span class="sxs-lookup"><span data-stu-id="702f2-231">Settings for the Microsoft Edge browser are on `edge://` URLs.</span></span>  <span data-ttu-id="702f2-232">これらの Web ページのほとんどが Microsoft Edge のブランド化を持つか、WebView2 のコンテキスト内で意味をなさないので、これらの URL の一部は無効になります。</span><span class="sxs-lookup"><span data-stu-id="702f2-232">Because most of these webpages have Microsoft Edge branding or don't make sense within the context of WebView2, some of these URLs are turned off.</span></span>  <span data-ttu-id="702f2-233">詳細については、「ブロックされた内部 [URL」に移動します](#blocked-internal-urls)。</span><span class="sxs-lookup"><span data-stu-id="702f2-233">For more information, navigate to [Blocked internal URLs](#blocked-internal-urls).</span></span>  |  

## <a name="blocked-internal-urls"></a><span data-ttu-id="702f2-234">ブロックされた内部 URL</span><span class="sxs-lookup"><span data-stu-id="702f2-234">Blocked internal URLs</span></span>  

<span data-ttu-id="702f2-235">次の Microsoft Edge と Google Chrome の設定 Web ページは、WebView2 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="702f2-235">The following Microsoft Edge and Google Chrome settings webpages aren't available in WebView2.</span></span>  

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

## <a name="additional-keyboard-shortcuts-information"></a><span data-ttu-id="702f2-236">その他のキーボード ショートカット情報</span><span class="sxs-lookup"><span data-stu-id="702f2-236">Additional keyboard shortcuts information</span></span>  

<span data-ttu-id="702f2-237">Microsoft Edge と WebView2 では、キーボード ショートカットまたはキー バインドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="702f2-237">Keyboard shortcuts or key bindings are supported in Microsoft Edge and WebView2.</span></span>  <span data-ttu-id="702f2-238">Microsoft Edge が更新された場合、既定のキー バインドが変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="702f2-238">When Microsoft Edge updates, the default key bindings may change.</span></span>  <span data-ttu-id="702f2-239">さらに、WebView2 で機能がサポートされている場合は、既定で無効になっているキーボード ショートカットが有効になります。</span><span class="sxs-lookup"><span data-stu-id="702f2-239">Furthermore, a keyboard shortcut that is turned off by default may turn on if the feature is now supported in WebView2.</span></span>  <span data-ttu-id="702f2-240">キーボード ショートカットの変更を避けるため、ブラウザー機能にアクセスするキーはすべて無効にし、基本的なテキスト編集ショートカットと移動ショートカットはすべてオンに維持します `AreBrowserAcceleratorKeysEnabled` `FALSE` 。</span><span class="sxs-lookup"><span data-stu-id="702f2-240">To avoid changes to your keyboard shortcuts, you may set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, which turns off all keys that access browser features, but keeps all basic text-editing and movement shortcuts turned on.</span></span>  

<span data-ttu-id="702f2-241">次の表に、WebView2 で常に無効になっているショートカットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="702f2-241">The following table lists the shortcuts that are always turned off in WebView2.</span></span>  <span data-ttu-id="702f2-242">アスタリスク \( \) 文字は、ショートカットがオフではないが、アクセスする機能がオフになっているか、WebView2 に適用されません。 `*`</span><span class="sxs-lookup"><span data-stu-id="702f2-242">An asterisk \(`*`\) character indicates that the shortcut isn't turned off, but the feature it accesses is turned off or doesn't apply to WebView2.</span></span>  

| <span data-ttu-id="702f2-243">操作</span><span class="sxs-lookup"><span data-stu-id="702f2-243">Action</span></span> | <span data-ttu-id="702f2-244">Windows</span><span class="sxs-lookup"><span data-stu-id="702f2-244">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="702f2-245">に追加する</span><span class="sxs-lookup"><span data-stu-id="702f2-245">Add to</span></span> Favorites | `Ctrl`+`D` |  
| <span data-ttu-id="702f2-246">[すべてのタブの追加]</span><span class="sxs-lookup"><span data-stu-id="702f2-246">Add All Tabs to</span></span> Favorites | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="702f2-247">フォーカスの場所</span><span class="sxs-lookup"><span data-stu-id="702f2-247">Focus Location</span></span> | `Ctrl`+`L, Alt`+`D` |  
| <span data-ttu-id="702f2-248">貼り付けと移動</span><span class="sxs-lookup"><span data-stu-id="702f2-248">Paste and Go</span></span> | `Ctrl`+`Shift`+`L` |  
| <span data-ttu-id="702f2-249">ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="702f2-249">Open File</span></span> | `Ctrl`+`O` |  
| Read Aloud `*` | `Ctrl`+`Shift`+`U` |  
| <span data-ttu-id="702f2-250">Web キャプチャ</span><span class="sxs-lookup"><span data-stu-id="702f2-250">Web Capture</span></span> `*` | `Ctrl`+`Shift`+`S` |  
| <span data-ttu-id="702f2-251">サイドバー</span><span class="sxs-lookup"><span data-stu-id="702f2-251">Sidebar</span></span> `*` | `Ctrl`+`Shift`+`E` |  
| <span data-ttu-id="702f2-252">[ページの保存]</span><span class="sxs-lookup"><span data-stu-id="702f2-252">Save Page</span></span> | `Ctrl`+`S` |  
| <span data-ttu-id="702f2-253">[最後のタブ] を選択する</span><span class="sxs-lookup"><span data-stu-id="702f2-253">Select Last Tab</span></span> | `Ctrl`+`9` |  
| <span data-ttu-id="702f2-254">[次へ] タブを選択する</span><span class="sxs-lookup"><span data-stu-id="702f2-254">Select Next Tab</span></span> | `Ctrl`+`Tab` |  
| <span data-ttu-id="702f2-255">[前へ] タブを選択する</span><span class="sxs-lookup"><span data-stu-id="702f2-255">Select Previous Tab</span></span> | `Ctrl`+`Shift`+`Tab` |  
| <span data-ttu-id="702f2-256">Tab \(1 - 8\) を選択する</span><span class="sxs-lookup"><span data-stu-id="702f2-256">Select Tab \(1 - 8\)</span></span> | `Ctrl`+`(1-8)` |  
| <span data-ttu-id="702f2-257">[バーの Favorites 表示]</span><span class="sxs-lookup"><span data-stu-id="702f2-257">Show Favorites Bar</span></span> `*` | `Ctrl`+`Shift`+`B` |  
| <span data-ttu-id="702f2-258">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="702f2-258">Help</span></span> | `F1` |  
| <span data-ttu-id="702f2-259">[次のウィンドウにフォーカス]</span><span class="sxs-lookup"><span data-stu-id="702f2-259">Focus Next Pane</span></span> `*` | `F6` |  
| <span data-ttu-id="702f2-260">[前のウィンドウにフォーカス]</span><span class="sxs-lookup"><span data-stu-id="702f2-260">Focus Previous Pane</span></span> `*` | `Shift`+`F6` |  
| <span data-ttu-id="702f2-261">キャレットブラウズ</span><span class="sxs-lookup"><span data-stu-id="702f2-261">Caret Browsing</span></span> `*` | `F7` |  
| <span data-ttu-id="702f2-262">閲覧ビュー</span><span class="sxs-lookup"><span data-stu-id="702f2-262">Reading View</span></span> `*` | `F9` |  
| <span data-ttu-id="702f2-263">フォーカス メニュー バー</span><span class="sxs-lookup"><span data-stu-id="702f2-263">Focus Menu Bar</span></span> | `F10` |  
| <span data-ttu-id="702f2-264">[ID の表示] メニュー</span><span class="sxs-lookup"><span data-stu-id="702f2-264">Show Identity Menu</span></span> `*` | `Ctrl`+`Shift`+`M` |  
| Browser Task Manager `*` | `Shift`+`Escape` |  
| <span data-ttu-id="702f2-265">エッジ フィードバック</span><span class="sxs-lookup"><span data-stu-id="702f2-265">Edge Feedback</span></span> `*` | `Shift`+`Alt`+`I` |  
| <span data-ttu-id="702f2-266">[ミュート] タブ</span><span class="sxs-lookup"><span data-stu-id="702f2-266">Mute Tab</span></span> `*` | `Ctrl`+`M` |  
| <span data-ttu-id="702f2-267">新しいシークレット ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="702f2-267">New Incognito Window</span></span> | `Ctrl`+`Shift`+`N` |  
| <span data-ttu-id="702f2-268">新しいタブ</span><span class="sxs-lookup"><span data-stu-id="702f2-268">New Tab</span></span> | `Ctrl`+`T` |  
| <span data-ttu-id="702f2-269">新しいウィンドウ</span><span class="sxs-lookup"><span data-stu-id="702f2-269">New Window</span></span> | `Ctrl`+`N` |  
| <span data-ttu-id="702f2-270">[最後に閉じたタブを復元]</span><span class="sxs-lookup"><span data-stu-id="702f2-270">Restore Last Closed Tab</span></span> | `Ctrl`+`Shift`+`T` |  
| <span data-ttu-id="702f2-271">Focus</span><span class="sxs-lookup"><span data-stu-id="702f2-271">Focus</span></span> Favorites | `Alt`+`Shift`+`B` |  
| <span data-ttu-id="702f2-272">フォーカス 非アクティブ ポップアップ</span><span class="sxs-lookup"><span data-stu-id="702f2-272">Focus Inactive Popup</span></span> | `Alt`+`Shift`+`A` |  
| <span data-ttu-id="702f2-273">フォーカス検索</span><span class="sxs-lookup"><span data-stu-id="702f2-273">Focus Search</span></span> | `Ctrl`<span data-ttu-id="702f2-274">+`E`, `Ctrl`+`K`,</span><span class="sxs-lookup"><span data-stu-id="702f2-274">+`E`, `Ctrl`+`K`,</span></span> `Search Key` |  
| <span data-ttu-id="702f2-275">[重複] タブ</span><span class="sxs-lookup"><span data-stu-id="702f2-275">Duplicate Tab</span></span> | `Ctrl`+`Shift`+`K` |  
| <span data-ttu-id="702f2-276">フォーカス ツールバー</span><span class="sxs-lookup"><span data-stu-id="702f2-276">Focus Toolbar</span></span> `*` | `Alt`+`Shift`+`T` |  
| <span data-ttu-id="702f2-277">Home</span><span class="sxs-lookup"><span data-stu-id="702f2-277">Home</span></span> | `Alt`<span data-ttu-id="702f2-278">+`Home`,</span><span class="sxs-lookup"><span data-stu-id="702f2-278">+`Home`,</span></span> `Browser Home Key` |  
| <span data-ttu-id="702f2-279">[アプリ の表示] メニュー</span><span class="sxs-lookup"><span data-stu-id="702f2-279">Show App Menu</span></span> | `Alt`+`E, Alt`+`F` |  
| <span data-ttu-id="702f2-280">注文詳細</span><span class="sxs-lookup"><span data-stu-id="702f2-280">Show</span></span> Favorites | `Ctrl`+`Shift`+`O` |  
| <span data-ttu-id="702f2-281">注文詳細</span><span class="sxs-lookup"><span data-stu-id="702f2-281">Show</span></span> Downloads | `Ctrl`+`J` |  
| <span data-ttu-id="702f2-282">履歴の表示</span><span class="sxs-lookup"><span data-stu-id="702f2-282">Show History</span></span> | `Ctrl`+`H` |  
| <span data-ttu-id="702f2-283">読み取りモード バーを表示する</span><span class="sxs-lookup"><span data-stu-id="702f2-283">Show Reading Mode Bar</span></span> `*` | `Shift`+`Alt`+`R` |  
| <span data-ttu-id="702f2-284">注文詳細</span><span class="sxs-lookup"><span data-stu-id="702f2-284">Show</span></span> Collections `*` | `Ctrl`+`Shift`+`Y` |  

<span data-ttu-id="702f2-285">イベントが処理されていないときに表示されるウィンドウを除き、次のキーボード ショートカットは常 `NewWindowRequested` にオフになります。</span><span class="sxs-lookup"><span data-stu-id="702f2-285">The following keyboard shortcuts are always turned off, except in windows that display when the `NewWindowRequested` event isn't handled.</span></span>

| <span data-ttu-id="702f2-286">操作</span><span class="sxs-lookup"><span data-stu-id="702f2-286">Action</span></span> | <span data-ttu-id="702f2-287">Windows</span><span class="sxs-lookup"><span data-stu-id="702f2-287">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="702f2-288">タブを閉じる</span><span class="sxs-lookup"><span data-stu-id="702f2-288">Close Tab</span></span> | `Ctrl`+`W, Ctrl`+`F4` |  
| <span data-ttu-id="702f2-289">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="702f2-289">Close Window</span></span> | `Ctrl`+`Shift`+`W` |  
| <span data-ttu-id="702f2-290">全画面表示</span><span class="sxs-lookup"><span data-stu-id="702f2-290">Fullscreen</span></span> | `F11` |  

<span data-ttu-id="702f2-291">に設定すると `AreBrowserAcceleratorKeysEnabled` `FALSE` 、次の追加のキーボード ショートカットがオフになります。</span><span class="sxs-lookup"><span data-stu-id="702f2-291">If you set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, the following additional keyboard shortcuts are turned off.</span></span>  

| <span data-ttu-id="702f2-292">操作</span><span class="sxs-lookup"><span data-stu-id="702f2-292">Action</span></span> | <span data-ttu-id="702f2-293">Windows</span><span class="sxs-lookup"><span data-stu-id="702f2-293">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="702f2-294">Stop</span><span class="sxs-lookup"><span data-stu-id="702f2-294">Stop</span></span> | `Escape` |  
| <span data-ttu-id="702f2-295">ページで検索する</span><span class="sxs-lookup"><span data-stu-id="702f2-295">Find on Page</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="702f2-296">[次へ] を検索する</span><span class="sxs-lookup"><span data-stu-id="702f2-296">Find Next</span></span> | `Ctrl`+`G` |  
| <span data-ttu-id="702f2-297">前の検索</span><span class="sxs-lookup"><span data-stu-id="702f2-297">Find Previous</span></span> | `Ctrl`+`Shift`+`G` |  
| <span data-ttu-id="702f2-298">印刷</span><span class="sxs-lookup"><span data-stu-id="702f2-298">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="702f2-299">Refresh</span><span class="sxs-lookup"><span data-stu-id="702f2-299">Refresh</span></span> | `Ctrl`<span data-ttu-id="702f2-300">+`R`, `F5`,</span><span class="sxs-lookup"><span data-stu-id="702f2-300">+`R`, `F5`,</span></span> `Reload Key` |  
| <span data-ttu-id="702f2-301">キャッシュなしの更新</span><span class="sxs-lookup"><span data-stu-id="702f2-301">Refresh Without Cache</span></span> | `Ctrl`<span data-ttu-id="702f2-302">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span><span class="sxs-lookup"><span data-stu-id="702f2-302">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span></span>`Refresh` |  
| <span data-ttu-id="702f2-303">ズームアウト</span><span class="sxs-lookup"><span data-stu-id="702f2-303">Zoom Out</span></span> | `Ctrl`+`-` |  
| <span data-ttu-id="702f2-304">拡大</span><span class="sxs-lookup"><span data-stu-id="702f2-304">Zoom In</span></span> | `Ctrl`+`+` |  
| <span data-ttu-id="702f2-305">ズームのリセット</span><span class="sxs-lookup"><span data-stu-id="702f2-305">Reset Zoom</span></span> | `Ctrl`+`0` |  
| <span data-ttu-id="702f2-306">[次へ] を検索する</span><span class="sxs-lookup"><span data-stu-id="702f2-306">Find Next</span></span> | `F3` |  
| <span data-ttu-id="702f2-307">前の検索</span><span class="sxs-lookup"><span data-stu-id="702f2-307">Find Previous</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="702f2-308">戻る</span><span class="sxs-lookup"><span data-stu-id="702f2-308">Back</span></span> | `Alt`+`Left, Browser Back Key` |  
| <span data-ttu-id="702f2-309">Forward</span><span class="sxs-lookup"><span data-stu-id="702f2-309">Forward</span></span> | `Alt`<span data-ttu-id="702f2-310">+`Right`,</span><span class="sxs-lookup"><span data-stu-id="702f2-310">+`Right`,</span></span> `Browser Forward Key` |  
| <span data-ttu-id="702f2-311">印刷</span><span class="sxs-lookup"><span data-stu-id="702f2-311">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="702f2-312">DevTools を開く/閉じる</span><span class="sxs-lookup"><span data-stu-id="702f2-312">Open / Close DevTools</span></span> | `Ctrl`+`Shift`+`I` |  
| <span data-ttu-id="702f2-313">DevTools コンソールを開く</span><span class="sxs-lookup"><span data-stu-id="702f2-313">Open DevTools Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="702f2-314">Open DevTools Inspect</span><span class="sxs-lookup"><span data-stu-id="702f2-314">Open DevTools Inspect</span></span> | `Ctrl`+`Shift`+`C` |  

> [!Note] 
> <span data-ttu-id="702f2-315">キーを個別にカスタマイズするには [、AcceleratorKeyPressed イベントを使用][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] します。</span><span class="sxs-lookup"><span data-stu-id="702f2-315">To customize any of the keys individually, use the [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] event.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview2-team"></a><span data-ttu-id="702f2-316">Microsoft Edge WebView2 チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="702f2-316">Getting in touch with the Microsoft Edge WebView2 team</span></span>  

[!INCLUDE [contact WebView2 team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

<!--[Webview2ReferenceDownloadApi]: ./download-api.md "download API | Microsoft Docs"  -->  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2controller.acceleratorkeypressed?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2Controller.AcceleratorKeyPressed イベント |Microsoft Docs"  

[DevtoolsShortcutsIndex]: ../../devtools-guide-chromium/shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

[GithubMicrosoftedgeWebview2feedbackIssues308]: https://github.com/MicrosoftEdge/WebView2Feedback/issues/308 "HTML5 通知 API (#308) |GitHub"  

[PeterExperimentsChromiumCommandLineSwitches]: https://peter.sh/experiments/chromium-command-line-switches "クロム コマンド ライン スイッチの一覧|Peter Beverloo"  
