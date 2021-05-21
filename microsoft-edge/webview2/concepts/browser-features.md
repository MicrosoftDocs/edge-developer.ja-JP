---
description: Microsoft Edge と WebView2 作成者の機能の違い
title: Microsoft Edge と WebView2 作成者の機能の違い
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, WebView2, webview, wpf apps, wpf, edge, ICoreWebView2, ICoreWebView2Host, browser control, edge html
no-loc: ["Autofill for Addresses", "Autofill for Passwords", Autofill for Payments", Browser Extensions", "Browser Task Manager", "Collections", "Continue-where-I-left-off prompt", "Downloads", "Edge Shopping", "Family Safety", "Favorites", "Hotkeys", "IE Mode" ,"Immersive Reader", "Intrusive Ads", "Read Aloud", "Smart Screen", "Translate", "Tracking Prevention", "Profile and Identity", "Web Payment API", "Windows Defender Application Guard","edge:// URLs"]  
---
# <a name="browser-feature-differences-between-microsoft-edge-and-webview2"></a><span data-ttu-id="63650-125">ブラウザーの機能の違いMicrosoft Edge WebView2</span><span class="sxs-lookup"><span data-stu-id="63650-125">Browser feature differences between Microsoft Edge and WebView2</span></span>  

<span data-ttu-id="63650-126">WebView2 は、新しいブラウザー Microsoft Edgeです。</span><span class="sxs-lookup"><span data-stu-id="63650-126">WebView2 is based on the new Microsoft Edge browser.</span></span>  <span data-ttu-id="63650-127">ブラウザーから WebView2 ベースのアプリに機能を拡張する機会があります。これは便利です。</span><span class="sxs-lookup"><span data-stu-id="63650-127">You have the opportunity to extend features from the browser to WebView2-based apps, which is useful.</span></span>  <span data-ttu-id="63650-128">ただし、WebView2 はブラウザーのようなアプリに限定されないので、変更または削除する必要があるブラウザー機能があります。</span><span class="sxs-lookup"><span data-stu-id="63650-128">However, since WebView2 isn't limited to browser-like apps, there are some browser features that need to be modified or removed.</span></span>  <span data-ttu-id="63650-129">この記事では、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="63650-129">This article provides the following information.</span></span>  

*   <span data-ttu-id="63650-130">変更されたブラウザー機能とサポート情報。</span><span class="sxs-lookup"><span data-stu-id="63650-130">The modified browser features and supporting information.</span></span>   
*   <span data-ttu-id="63650-131">機能のオンとオフを切り替える機能。</span><span class="sxs-lookup"><span data-stu-id="63650-131">The ability to turn on or off the feature.</span></span>  
*   <span data-ttu-id="63650-132">キーボード ショートカットに関するガイダンス。</span><span class="sxs-lookup"><span data-stu-id="63650-132">Guidance on keyboard shortcuts.</span></span>  
    
## <a name="design-guidelines"></a><span data-ttu-id="63650-133">設計ガイドライン</span><span class="sxs-lookup"><span data-stu-id="63650-133">Design guidelines</span></span>  

<span data-ttu-id="63650-134">WebView2 のコンテキストでは、ブラウザー機能は次の設計ガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="63650-134">In the context of WebView2, browser features adhere to the following design guidelines.</span></span>  

*   <span data-ttu-id="63650-135">ほとんどの機能は、WebView2 および WebView2 および webView2 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="63650-135">Most features work the same in WebView2 and Microsoft Edge.</span></span>  <span data-ttu-id="63650-136">WebView2 のコンテキストや他の理由で機能が意味をなさない場合、機能は変更または無効になります。</span><span class="sxs-lookup"><span data-stu-id="63650-136">If a feature doesn't make sense in the context of WebView2 or for other reasons, the feature is modified or turned off.</span></span> 
*   <span data-ttu-id="63650-137">WebView2 の機能には、ブランド化Microsoft Edge含まれます。</span><span class="sxs-lookup"><span data-stu-id="63650-137">WebView2 features don't include Microsoft Edge branding.</span></span>  
    
## <a name="features"></a><span data-ttu-id="63650-138">機能</span><span class="sxs-lookup"><span data-stu-id="63650-138">Features</span></span>  

<span data-ttu-id="63650-139">次の表に、ブラウザーとは異なる WebView2 Microsoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="63650-139">The following table displays the WebView2 features that differ from the Microsoft Edge browser.</span></span>   

*   <span data-ttu-id="63650-140">**既定の** 状態は、機能が新しい WebView2 インスタンスの既定のエクスペリエンスの一部を示します。</span><span class="sxs-lookup"><span data-stu-id="63650-140">**Default state** indicates that the feature is part of the default experience on a new WebView2 instance.</span></span>  
*   <span data-ttu-id="63650-141">**[構成** 可能] は、WebView2 API またはコマンド ライン スイッチを使用して機能を有効またはオフにできる可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="63650-141">**Configurable** indicates that you may turn on or off the feature using WebView2 APIs or command-line switches.</span></span>  
    
> [!NOTE]  
> <span data-ttu-id="63650-142">この記事では、コマンド ライン スイッチを使用した機能の変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="63650-142">This article doesn't cover modifying features using command-line switches.</span></span>  <span data-ttu-id="63650-143">コマンド ライン スイッチを使用して機能のオンとオフを切り替える方法の詳細については、「コマンド ライン スイッチの一覧[」Chromiumを参照してください][PeterExperimentsChromiumCommandLineSwitches]。</span><span class="sxs-lookup"><span data-stu-id="63650-143">For more information about turning on and off features with command-line switches, navigate to [List of Chromium Command Line Switches][PeterExperimentsChromiumCommandLineSwitches].</span></span>  
    
| <span data-ttu-id="63650-144">機能</span><span class="sxs-lookup"><span data-stu-id="63650-144">Feature</span></span> | <span data-ttu-id="63650-145">既定の状態</span><span class="sxs-lookup"><span data-stu-id="63650-145">Default state</span></span> | <span data-ttu-id="63650-146">構成可能</span><span class="sxs-lookup"><span data-stu-id="63650-146">Configurable</span></span> | <span data-ttu-id="63650-147">詳細</span><span class="sxs-lookup"><span data-stu-id="63650-147">Details</span></span> |  
|:--- |:--- |:--- | :--- |  
| Autofill for Addresses | <span data-ttu-id="63650-148">オン</span><span class="sxs-lookup"><span data-stu-id="63650-148">On</span></span> | <span data-ttu-id="63650-149">あり</span><span class="sxs-lookup"><span data-stu-id="63650-149">Yes</span></span> | <span data-ttu-id="63650-150">この機能は既定でオンになっています。WebView2 オートフィル API を使用してオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="63650-150">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| Autofill for Passwords | <span data-ttu-id="63650-151">オン</span><span class="sxs-lookup"><span data-stu-id="63650-151">On</span></span> | <span data-ttu-id="63650-152">あり</span><span class="sxs-lookup"><span data-stu-id="63650-152">Yes</span></span> | <span data-ttu-id="63650-153">この機能は既定でオンになっています。WebView2 オートフィル API を使用してオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="63650-153">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| <span data-ttu-id="63650-154">支払いの自動入力</span><span class="sxs-lookup"><span data-stu-id="63650-154">Autofill for Payments</span></span> | <span data-ttu-id="63650-155">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-155">Off</span></span> | <span data-ttu-id="63650-156">なし</span><span class="sxs-lookup"><span data-stu-id="63650-156">No</span></span> | <span data-ttu-id="63650-157">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-157">This feature is turned off.</span></span>  |  
| <span data-ttu-id="63650-158">ブラウザー拡張機能</span><span class="sxs-lookup"><span data-stu-id="63650-158">Browser Extensions</span></span> | <span data-ttu-id="63650-159">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-159">Off</span></span> | <span data-ttu-id="63650-160">なし</span><span class="sxs-lookup"><span data-stu-id="63650-160">No</span></span> | <span data-ttu-id="63650-161">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-161">This feature is turned off.</span></span>  |  
| Browser Task Manager | <span data-ttu-id="63650-162">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-162">Off</span></span> | <span data-ttu-id="63650-163">なし</span><span class="sxs-lookup"><span data-stu-id="63650-163">No</span></span> | <span data-ttu-id="63650-164">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-164">This feature is turned off.</span></span>  |  
| Collections | <span data-ttu-id="63650-165">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-165">Off</span></span> | <span data-ttu-id="63650-166">なし</span><span class="sxs-lookup"><span data-stu-id="63650-166">No</span></span> | <span data-ttu-id="63650-167">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-167">This feature is turned off.</span></span>  |  
| Continue-where-I-left-off prompt | <span data-ttu-id="63650-168">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-168">Off</span></span> | <span data-ttu-id="63650-169">なし</span><span class="sxs-lookup"><span data-stu-id="63650-169">No</span></span> | <span data-ttu-id="63650-170">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-170">This feature is turned off.</span></span>  |  
| Downloads | <span data-ttu-id="63650-171">オン</span><span class="sxs-lookup"><span data-stu-id="63650-171">On</span></span> | <span data-ttu-id="63650-172">あり</span><span class="sxs-lookup"><span data-stu-id="63650-172">Yes</span></span> | <span data-ttu-id="63650-173">WebView2 には、ダウンロード UI をカスタマイズしてダウンロードを操作できる API が提供されています。</span><span class="sxs-lookup"><span data-stu-id="63650-173">WebView2 provides an API that allows you to customize the download UI to manipulate downloads.</span></span> <span data-ttu-id="63650-174">たとえば、ブロック、リダイレクト、保存、一時停止などです。</span><span class="sxs-lookup"><span data-stu-id="63650-174">For example, you can block, redirect, save, pause, and so on.</span></span>  <!--For more information, navigate to [download API][Webview2ReferenceDownloadApi].--> |  
| Edge Shopping | <span data-ttu-id="63650-175">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-175">Off</span></span> | <span data-ttu-id="63650-176">なし</span><span class="sxs-lookup"><span data-stu-id="63650-176">No</span></span> | <span data-ttu-id="63650-177">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-177">This feature is turned off.</span></span>  |  
| Family Safety | <span data-ttu-id="63650-178">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-178">Off</span></span> | <span data-ttu-id="63650-179">なし</span><span class="sxs-lookup"><span data-stu-id="63650-179">No</span></span> | <span data-ttu-id="63650-180">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-180">This feature is turned off.</span></span>  |  
| Favorites | <span data-ttu-id="63650-181">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-181">Off</span></span> | <span data-ttu-id="63650-182">なし</span><span class="sxs-lookup"><span data-stu-id="63650-182">No</span></span> | <span data-ttu-id="63650-183">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-183">This feature is turned off.</span></span>  |  
| IE Mode | <span data-ttu-id="63650-184">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-184">Off</span></span> | <span data-ttu-id="63650-185">なし</span><span class="sxs-lookup"><span data-stu-id="63650-185">No</span></span> | <span data-ttu-id="63650-186">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-186">This feature is turned off.</span></span>  |  
| Immersive Reader | <span data-ttu-id="63650-187">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-187">Off</span></span> | <span data-ttu-id="63650-188">なし</span><span class="sxs-lookup"><span data-stu-id="63650-188">No</span></span> | <span data-ttu-id="63650-189">この機能は、操作のブラウザー UI によって異なります。</span><span class="sxs-lookup"><span data-stu-id="63650-189">This feature depends on the browser UI for interaction.</span></span>  <span data-ttu-id="63650-190">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-190">This feature is turned off.</span></span>  |  
| Intrusive Ads | <span data-ttu-id="63650-191">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-191">Off</span></span> | <span data-ttu-id="63650-192">なし</span><span class="sxs-lookup"><span data-stu-id="63650-192">No</span></span> | <span data-ttu-id="63650-193">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-193">This feature is turned off.</span></span>  |  
| <span data-ttu-id="63650-194">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="63650-194">Keyboard shortcuts</span></span> | <span data-ttu-id="63650-195">レビューの詳細</span><span class="sxs-lookup"><span data-stu-id="63650-195">Review Details</span></span> | <span data-ttu-id="63650-196">レビューの詳細</span><span class="sxs-lookup"><span data-stu-id="63650-196">Review Details</span></span> | <span data-ttu-id="63650-197">既定でオフになっているキーボード ショートカットは、意味をなさないか、WebView2 で問題を引き起こします。</span><span class="sxs-lookup"><span data-stu-id="63650-197">The keyboard shortcuts that are turned off by default either don't make sense or cause problems in WebView2.</span></span>  <span data-ttu-id="63650-198">これらのショートカットを有効またはオフにしない場合があります。</span><span class="sxs-lookup"><span data-stu-id="63650-198">You may not turn on or off these shortcuts.</span></span>  <span data-ttu-id="63650-199">代わりに、イベントを使用してキーの組み合わせをリッスンし、必要に応じてカスタム `AcceleratorKeyPressed` 応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="63650-199">Instead, you may listen for a key combination using the `AcceleratorKeyPressed` event and create a custom response if needed.</span></span>  <span data-ttu-id="63650-200">詳細については、「その他のキーボード [ショートカット情報」に移動します](#additional-keyboard-shortcuts-information)。</span><span class="sxs-lookup"><span data-stu-id="63650-200">For more information, navigate to [Additional keyboard shortcuts information](#additional-keyboard-shortcuts-information).</span></span> |  
| <span data-ttu-id="63650-201">プッシュ通知</span><span class="sxs-lookup"><span data-stu-id="63650-201">Push notifications</span></span> | <span data-ttu-id="63650-202">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-202">Off</span></span> | <span data-ttu-id="63650-203">なし</span><span class="sxs-lookup"><span data-stu-id="63650-203">No</span></span> | <span data-ttu-id="63650-204">この機能は WebView2 では実装されていません。</span><span class="sxs-lookup"><span data-stu-id="63650-204">This feature is not implemented in WebView2.</span></span>  <span data-ttu-id="63650-205">詳細については [、「HTML5 通知 API のサポートの追加 (#308) 」を参照してください][GithubMicrosoftedgeWebview2feedbackIssues308]。</span><span class="sxs-lookup"><span data-stu-id="63650-205">For more information, navigate to [Add support for HTML5 Notification API (#308)][GithubMicrosoftedgeWebview2feedbackIssues308].</span></span> |  
| Read Aloud | <span data-ttu-id="63650-206">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-206">Off</span></span> | <span data-ttu-id="63650-207">なし</span><span class="sxs-lookup"><span data-stu-id="63650-207">No</span></span> | <span data-ttu-id="63650-208">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-208">This feature is turned off.</span></span>  |  
| Smart Screen | <span data-ttu-id="63650-209">オン</span><span class="sxs-lookup"><span data-stu-id="63650-209">On</span></span>`*` | <span data-ttu-id="63650-210">なし</span><span class="sxs-lookup"><span data-stu-id="63650-210">No</span></span> | `*` <span data-ttu-id="63650-211">この機能の UI は削除されましたが、基になる機能は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="63650-211">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="63650-212">また、コマンド ライン スイッチを Smart Screen 使用してオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="63650-212">Additionally, you may turn off Smart Screen using a command-line switch.</span></span>  |  
| Translate | <span data-ttu-id="63650-213">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-213">Off</span></span> | <span data-ttu-id="63650-214">なし</span><span class="sxs-lookup"><span data-stu-id="63650-214">No</span></span> | <span data-ttu-id="63650-215">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-215">This feature is turned off.</span></span>  |  
| Tracking Prevention | <span data-ttu-id="63650-216">オン</span><span class="sxs-lookup"><span data-stu-id="63650-216">On</span></span>`*` | <span data-ttu-id="63650-217">なし</span><span class="sxs-lookup"><span data-stu-id="63650-217">No</span></span> | `*` <span data-ttu-id="63650-218">この機能の UI は削除されましたが、基になる機能は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="63650-218">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="63650-219">追跡防止は常にバランスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="63650-219">Tracking prevention is always set to balanced.</span></span>|  
| Profile and Identity | <span data-ttu-id="63650-220">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-220">Off</span></span> | <span data-ttu-id="63650-221">なし</span><span class="sxs-lookup"><span data-stu-id="63650-221">No</span></span> | <span data-ttu-id="63650-222">お気に入り、Cookie などと同期する機能はオフになります。</span><span class="sxs-lookup"><span data-stu-id="63650-222">The feature that syncs your favorites, cookies, and so on, is turned off.</span></span>  |  
| Web Payment API | <span data-ttu-id="63650-223">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-223">Off</span></span> | <span data-ttu-id="63650-224">なし</span><span class="sxs-lookup"><span data-stu-id="63650-224">No</span></span> | <span data-ttu-id="63650-225">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-225">This feature is turned off.</span></span>  | 
| Windows Defender Application Guard | <span data-ttu-id="63650-226">オフ</span><span class="sxs-lookup"><span data-stu-id="63650-226">Off</span></span> | <span data-ttu-id="63650-227">なし</span><span class="sxs-lookup"><span data-stu-id="63650-227">No</span></span> | <span data-ttu-id="63650-228">この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="63650-228">This feature is turned off.</span></span>  |  
| edge:// URLs | <span data-ttu-id="63650-229">レビューの詳細</span><span class="sxs-lookup"><span data-stu-id="63650-229">Review Details</span></span> | <span data-ttu-id="63650-230">なし</span><span class="sxs-lookup"><span data-stu-id="63650-230">No</span></span> | <span data-ttu-id="63650-231">設定ブラウザーのMicrosoft Edge URL です `edge://` 。</span><span class="sxs-lookup"><span data-stu-id="63650-231">Settings for the Microsoft Edge browser are on `edge://` URLs.</span></span>  <span data-ttu-id="63650-232">これらの Web ページの多Microsoft Edge、WebView2 のコンテキスト内では意味をなさないので、これらの URL の一部は無効になります。</span><span class="sxs-lookup"><span data-stu-id="63650-232">Because most of these webpages have Microsoft Edge branding or don't make sense within the context of WebView2, some of these URLs are turned off.</span></span>  <span data-ttu-id="63650-233">詳細については、「ブロックされた内部 [URL」に移動します](#blocked-internal-urls)。</span><span class="sxs-lookup"><span data-stu-id="63650-233">For more information, navigate to [Blocked internal URLs](#blocked-internal-urls).</span></span>  |  

## <a name="blocked-internal-urls"></a><span data-ttu-id="63650-234">ブロックされた内部 URL</span><span class="sxs-lookup"><span data-stu-id="63650-234">Blocked internal URLs</span></span>  

<span data-ttu-id="63650-235">次のMicrosoft Edge Google Chrome 設定の Web ページは WebView2 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="63650-235">The following Microsoft Edge and Google Chrome settings webpages aren't available in WebView2.</span></span>  

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
    
## <a name="additional-keyboard-shortcuts-information"></a><span data-ttu-id="63650-236">その他のキーボード ショートカット情報</span><span class="sxs-lookup"><span data-stu-id="63650-236">Additional keyboard shortcuts information</span></span>  

<span data-ttu-id="63650-237">キーボード ショートカットまたはキー バインドは、WebView2 Microsoft Edgeサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63650-237">Keyboard shortcuts or key bindings are supported in Microsoft Edge and WebView2.</span></span>  <span data-ttu-id="63650-238">更新Microsoft Edge、既定のキー バインドが変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="63650-238">When Microsoft Edge updates, the default key bindings may change.</span></span>  <span data-ttu-id="63650-239">さらに、WebView2 で機能がサポートされている場合は、既定で無効になっているキーボード ショートカットが有効になります。</span><span class="sxs-lookup"><span data-stu-id="63650-239">Furthermore, a keyboard shortcut that is turned off by default may turn on if the feature is now supported in WebView2.</span></span>  <span data-ttu-id="63650-240">キーボード ショートカットの変更を避けるため、ブラウザー機能にアクセスするキーはすべて無効にし、基本的なテキスト編集ショートカットと移動ショートカットはすべてオンに維持します `AreBrowserAcceleratorKeysEnabled` `FALSE` 。</span><span class="sxs-lookup"><span data-stu-id="63650-240">To avoid changes to your keyboard shortcuts, you may set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, which turns off all keys that access browser features, but keeps all basic text-editing and movement shortcuts turned on.</span></span>  

<span data-ttu-id="63650-241">次の表に、WebView2 で常に無効になっているショートカットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="63650-241">The following table lists the shortcuts that are always turned off in WebView2.</span></span>  <span data-ttu-id="63650-242">アスタリスク \( \) 文字は、ショートカットがオフではないが、アクセスする機能がオフになっているか、WebView2 に適用されません。 `*`</span><span class="sxs-lookup"><span data-stu-id="63650-242">An asterisk \(`*`\) character indicates that the shortcut isn't turned off, but the feature it accesses is turned off or doesn't apply to WebView2.</span></span>  

| <span data-ttu-id="63650-243">操作</span><span class="sxs-lookup"><span data-stu-id="63650-243">Action</span></span> | <span data-ttu-id="63650-244">Windows</span><span class="sxs-lookup"><span data-stu-id="63650-244">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="63650-245">に追加する</span><span class="sxs-lookup"><span data-stu-id="63650-245">Add to</span></span> Favorites | `Ctrl`+`D` |  
| <span data-ttu-id="63650-246">[すべてのタブの追加]</span><span class="sxs-lookup"><span data-stu-id="63650-246">Add All Tabs to</span></span> Favorites | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="63650-247">フォーカスの場所</span><span class="sxs-lookup"><span data-stu-id="63650-247">Focus Location</span></span> | `Ctrl`+`L, Alt`+`D` |  
| <span data-ttu-id="63650-248">貼り付けと移動</span><span class="sxs-lookup"><span data-stu-id="63650-248">Paste and Go</span></span> | `Ctrl`+`Shift`+`L` |  
| <span data-ttu-id="63650-249">ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="63650-249">Open File</span></span> | `Ctrl`+`O` |  
| Read Aloud `*` | `Ctrl`+`Shift`+`U` |  
| <span data-ttu-id="63650-250">Web キャプチャ</span><span class="sxs-lookup"><span data-stu-id="63650-250">Web Capture</span></span> `*` | `Ctrl`+`Shift`+`S` |  
| <span data-ttu-id="63650-251">サイドバー</span><span class="sxs-lookup"><span data-stu-id="63650-251">Sidebar</span></span> `*` | `Ctrl`+`Shift`+`E` |  
| <span data-ttu-id="63650-252">[ページの保存]</span><span class="sxs-lookup"><span data-stu-id="63650-252">Save Page</span></span> | `Ctrl`+`S` |  
| <span data-ttu-id="63650-253">[最後のタブ] を選択する</span><span class="sxs-lookup"><span data-stu-id="63650-253">Select Last Tab</span></span> | `Ctrl`+`9` |  
| <span data-ttu-id="63650-254">[次へ] タブを選択する</span><span class="sxs-lookup"><span data-stu-id="63650-254">Select Next Tab</span></span> | `Ctrl`+`Tab` |  
| <span data-ttu-id="63650-255">[前へ] タブを選択する</span><span class="sxs-lookup"><span data-stu-id="63650-255">Select Previous Tab</span></span> | `Ctrl`+`Shift`+`Tab` |  
| <span data-ttu-id="63650-256">Tab \(1 - 8\) を選択する</span><span class="sxs-lookup"><span data-stu-id="63650-256">Select Tab \(1 - 8\)</span></span> | `Ctrl`+`(1-8)` |  
| <span data-ttu-id="63650-257">[バーの Favorites 表示]</span><span class="sxs-lookup"><span data-stu-id="63650-257">Show Favorites Bar</span></span> `*` | `Ctrl`+`Shift`+`B` |  
| <span data-ttu-id="63650-258">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="63650-258">Help</span></span> | `F1` |  
| <span data-ttu-id="63650-259">[次のウィンドウにフォーカス]</span><span class="sxs-lookup"><span data-stu-id="63650-259">Focus Next Pane</span></span> `*` | `F6` |  
| <span data-ttu-id="63650-260">[前のウィンドウにフォーカス]</span><span class="sxs-lookup"><span data-stu-id="63650-260">Focus Previous Pane</span></span> `*` | `Shift`+`F6` |  
| <span data-ttu-id="63650-261">キャレットブラウズ</span><span class="sxs-lookup"><span data-stu-id="63650-261">Caret Browsing</span></span> `*` | `F7` |  
| <span data-ttu-id="63650-262">閲覧ビュー</span><span class="sxs-lookup"><span data-stu-id="63650-262">Reading View</span></span> `*` | `F9` |  
| <span data-ttu-id="63650-263">フォーカス メニュー バー</span><span class="sxs-lookup"><span data-stu-id="63650-263">Focus Menu Bar</span></span> | `F10` |  
| <span data-ttu-id="63650-264">[ID の表示] メニュー</span><span class="sxs-lookup"><span data-stu-id="63650-264">Show Identity Menu</span></span> `*` | `Ctrl`+`Shift`+`M` |  
| Browser Task Manager `*` | `Shift`+`Escape` |  
| <span data-ttu-id="63650-265">エッジ フィードバック</span><span class="sxs-lookup"><span data-stu-id="63650-265">Edge Feedback</span></span> `*` | `Shift`+`Alt`+`I` |  
| <span data-ttu-id="63650-266">[ミュート] タブ</span><span class="sxs-lookup"><span data-stu-id="63650-266">Mute Tab</span></span> `*` | `Ctrl`+`M` |  
| <span data-ttu-id="63650-267">新しいシークレット ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="63650-267">New Incognito Window</span></span> | `Ctrl`+`Shift`+`N` |  
| <span data-ttu-id="63650-268">新しいタブ</span><span class="sxs-lookup"><span data-stu-id="63650-268">New Tab</span></span> | `Ctrl`+`T` |  
| <span data-ttu-id="63650-269">新しいウィンドウ</span><span class="sxs-lookup"><span data-stu-id="63650-269">New Window</span></span> | `Ctrl`+`N` |  
| <span data-ttu-id="63650-270">[最後に閉じたタブを復元]</span><span class="sxs-lookup"><span data-stu-id="63650-270">Restore Last Closed Tab</span></span> | `Ctrl`+`Shift`+`T` |  
| <span data-ttu-id="63650-271">Focus</span><span class="sxs-lookup"><span data-stu-id="63650-271">Focus</span></span> Favorites | `Alt`+`Shift`+`B` |  
| <span data-ttu-id="63650-272">フォーカス 非アクティブ ポップアップ</span><span class="sxs-lookup"><span data-stu-id="63650-272">Focus Inactive Popup</span></span> | `Alt`+`Shift`+`A` |  
| <span data-ttu-id="63650-273">フォーカス検索</span><span class="sxs-lookup"><span data-stu-id="63650-273">Focus Search</span></span> | `Ctrl`<span data-ttu-id="63650-274">+`E`, `Ctrl`+`K`,</span><span class="sxs-lookup"><span data-stu-id="63650-274">+`E`, `Ctrl`+`K`,</span></span> `Search Key` |  
| <span data-ttu-id="63650-275">[重複] タブ</span><span class="sxs-lookup"><span data-stu-id="63650-275">Duplicate Tab</span></span> | `Ctrl`+`Shift`+`K` |  
| <span data-ttu-id="63650-276">フォーカス ツールバー</span><span class="sxs-lookup"><span data-stu-id="63650-276">Focus Toolbar</span></span> `*` | `Alt`+`Shift`+`T` |  
| <span data-ttu-id="63650-277">Home</span><span class="sxs-lookup"><span data-stu-id="63650-277">Home</span></span> | `Alt`<span data-ttu-id="63650-278">+`Home`,</span><span class="sxs-lookup"><span data-stu-id="63650-278">+`Home`,</span></span> `Browser Home Key` |  
| <span data-ttu-id="63650-279">[アプリ の表示] メニュー</span><span class="sxs-lookup"><span data-stu-id="63650-279">Show App Menu</span></span> | `Alt`+`E, Alt`+`F` |  
| <span data-ttu-id="63650-280">注文詳細</span><span class="sxs-lookup"><span data-stu-id="63650-280">Show</span></span> Favorites | `Ctrl`+`Shift`+`O` |  
| <span data-ttu-id="63650-281">注文詳細</span><span class="sxs-lookup"><span data-stu-id="63650-281">Show</span></span> Downloads | `Ctrl`+`J` |  
| <span data-ttu-id="63650-282">履歴の表示</span><span class="sxs-lookup"><span data-stu-id="63650-282">Show History</span></span> | `Ctrl`+`H` |  
| <span data-ttu-id="63650-283">読み取りモード バーを表示する</span><span class="sxs-lookup"><span data-stu-id="63650-283">Show Reading Mode Bar</span></span> `*` | `Shift`+`Alt`+`R` |  
| <span data-ttu-id="63650-284">注文詳細</span><span class="sxs-lookup"><span data-stu-id="63650-284">Show</span></span> Collections `*` | `Ctrl`+`Shift`+`Y` |  

<span data-ttu-id="63650-285">イベントが処理されていないときに表示されるウィンドウを除き、次のキーボード ショートカットは常 `NewWindowRequested` にオフになります。</span><span class="sxs-lookup"><span data-stu-id="63650-285">The following keyboard shortcuts are always turned off, except in windows that display when the `NewWindowRequested` event isn't handled.</span></span>

| <span data-ttu-id="63650-286">操作</span><span class="sxs-lookup"><span data-stu-id="63650-286">Action</span></span> | <span data-ttu-id="63650-287">Windows</span><span class="sxs-lookup"><span data-stu-id="63650-287">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="63650-288">タブを閉じる</span><span class="sxs-lookup"><span data-stu-id="63650-288">Close Tab</span></span> | `Ctrl`+`W, Ctrl`+`F4` |  
| <span data-ttu-id="63650-289">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="63650-289">Close Window</span></span> | `Ctrl`+`Shift`+`W` |  
| <span data-ttu-id="63650-290">全画面表示</span><span class="sxs-lookup"><span data-stu-id="63650-290">Fullscreen</span></span> | `F11` |  

<span data-ttu-id="63650-291">に設定すると `AreBrowserAcceleratorKeysEnabled` `FALSE` 、次の追加のキーボード ショートカットがオフになります。</span><span class="sxs-lookup"><span data-stu-id="63650-291">If you set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, the following additional keyboard shortcuts are turned off.</span></span>  

| <span data-ttu-id="63650-292">操作</span><span class="sxs-lookup"><span data-stu-id="63650-292">Action</span></span> | <span data-ttu-id="63650-293">Windows</span><span class="sxs-lookup"><span data-stu-id="63650-293">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="63650-294">Stop</span><span class="sxs-lookup"><span data-stu-id="63650-294">Stop</span></span> | `Escape` |  
| <span data-ttu-id="63650-295">ページで検索する</span><span class="sxs-lookup"><span data-stu-id="63650-295">Find on Page</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="63650-296">[次へ] を検索する</span><span class="sxs-lookup"><span data-stu-id="63650-296">Find Next</span></span> | `Ctrl`+`G` |  
| <span data-ttu-id="63650-297">前の検索</span><span class="sxs-lookup"><span data-stu-id="63650-297">Find Previous</span></span> | `Ctrl`+`Shift`+`G` |  
| <span data-ttu-id="63650-298">印刷</span><span class="sxs-lookup"><span data-stu-id="63650-298">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="63650-299">Refresh</span><span class="sxs-lookup"><span data-stu-id="63650-299">Refresh</span></span> | `Ctrl`<span data-ttu-id="63650-300">+`R`, `F5`,</span><span class="sxs-lookup"><span data-stu-id="63650-300">+`R`, `F5`,</span></span> `Reload Key` |  
| <span data-ttu-id="63650-301">キャッシュなしの更新</span><span class="sxs-lookup"><span data-stu-id="63650-301">Refresh Without Cache</span></span> | `Ctrl`<span data-ttu-id="63650-302">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span><span class="sxs-lookup"><span data-stu-id="63650-302">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span></span>`Refresh` |  
| <span data-ttu-id="63650-303">ズームアウト</span><span class="sxs-lookup"><span data-stu-id="63650-303">Zoom Out</span></span> | `Ctrl`+`-` |  
| <span data-ttu-id="63650-304">拡大</span><span class="sxs-lookup"><span data-stu-id="63650-304">Zoom In</span></span> | `Ctrl`+`+` |  
| <span data-ttu-id="63650-305">ズームのリセット</span><span class="sxs-lookup"><span data-stu-id="63650-305">Reset Zoom</span></span> | `Ctrl`+`0` |  
| <span data-ttu-id="63650-306">[次へ] を検索する</span><span class="sxs-lookup"><span data-stu-id="63650-306">Find Next</span></span> | `F3` |  
| <span data-ttu-id="63650-307">前の検索</span><span class="sxs-lookup"><span data-stu-id="63650-307">Find Previous</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="63650-308">戻る</span><span class="sxs-lookup"><span data-stu-id="63650-308">Back</span></span> | `Alt`+`Left, Browser Back Key` |  
| <span data-ttu-id="63650-309">Forward</span><span class="sxs-lookup"><span data-stu-id="63650-309">Forward</span></span> | `Alt`<span data-ttu-id="63650-310">+`Right`,</span><span class="sxs-lookup"><span data-stu-id="63650-310">+`Right`,</span></span> `Browser Forward Key` |  
| <span data-ttu-id="63650-311">印刷</span><span class="sxs-lookup"><span data-stu-id="63650-311">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="63650-312">DevTools を開く/閉じる</span><span class="sxs-lookup"><span data-stu-id="63650-312">Open / Close DevTools</span></span> | `Ctrl`+`Shift`+`I` |  
| <span data-ttu-id="63650-313">DevTools コンソールを開く</span><span class="sxs-lookup"><span data-stu-id="63650-313">Open DevTools Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="63650-314">Open DevTools Inspect</span><span class="sxs-lookup"><span data-stu-id="63650-314">Open DevTools Inspect</span></span> | `Ctrl`+`Shift`+`C` |  

> [!Note] 
> <span data-ttu-id="63650-315">キーを個別にカスタマイズするには [、AcceleratorKeyPressed イベントを使用][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] します。</span><span class="sxs-lookup"><span data-stu-id="63650-315">To customize any of the keys individually, use the [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] event.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview2-team"></a><span data-ttu-id="63650-316">WebView2 チームと連絡を取Microsoft Edgeする</span><span class="sxs-lookup"><span data-stu-id="63650-316">Getting in touch with the Microsoft Edge WebView2 team</span></span>  

[!INCLUDE [contact WebView2 team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

<!--[Webview2ReferenceDownloadApi]: ./download-api.md "download API | Microsoft Docs"  -->  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2controller.acceleratorkeypressed?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2Controller.AcceleratorKeyPressed イベント |Microsoft Docs"  

[DevtoolsShortcutsIndex]: ../../devtools-guide-chromium/shortcuts/index.md "Microsoft EdgeDevTools キーボード ショートカット |Microsoft Docs"  

[GithubMicrosoftedgeWebview2feedbackIssues308]: https://github.com/MicrosoftEdge/WebView2Feedback/issues/308 "HTML5 通知 API (#308) |GitHub"  

[PeterExperimentsChromiumCommandLineSwitches]: https://peter.sh/experiments/chromium-command-line-switches "コマンド ライン スイッチChromiumの一覧|Peter Beverloo"  
