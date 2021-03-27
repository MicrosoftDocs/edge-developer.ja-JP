---
description: Microsoft Edge Developer Tools を使用して、ネイティブ Android アプリのリモート デバッグ WebViews の使用を開始します。
title: Android WebViews のリモート デバッグの開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/25/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4d389473673791d91c38e252c919378c4725db6b
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461537"
---
<!-- Copyright Meggin Kearney 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="get-started-with-remote-debugging-android-webviews"></a><span data-ttu-id="744a8-104">Android WebViews のリモート デバッグの開始</span><span class="sxs-lookup"><span data-stu-id="744a8-104">Get started with remote debugging Android WebViews</span></span>  

<span data-ttu-id="744a8-105">Microsoft Edge Developer Tools を使用して、ネイティブ Android アプリで Android WebViews をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="744a8-105">Debug Android WebViews in your native Android apps using Microsoft Edge Developer Tools.</span></span>  

<span data-ttu-id="744a8-106">Android 4.4 \(KitKat\) 以降では、DevTools を使用してネイティブ Android アプリの WebView コンテンツをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="744a8-106">On Android 4.4 \(KitKat\) or later, use DevTools to debug WebView content in native Android apps.</span></span>  

### <a name="summary"></a><span data-ttu-id="744a8-107">要約</span><span class="sxs-lookup"><span data-stu-id="744a8-107">Summary</span></span>  

*   <span data-ttu-id="744a8-108">ネイティブ Android アプリで Android WebView デバッグを有効にする。Microsoft Edge DevTools で Android WebViews をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="744a8-108">Turn on Android WebView debugging in your native Android app; debug Android WebViews in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="744a8-109">デバッグを有効にした Android WebViews の一覧を表示するには、に移動します `edge://inspect` 。</span><span class="sxs-lookup"><span data-stu-id="744a8-109">To display the list of the Android WebViews with debugging turned on, navigate to `edge://inspect`.</span></span>  
*   <span data-ttu-id="744a8-110">リモート デバッグを使用して Web ページをデバッグするのと同じ方法で、Android WebViews [をデバッグします][RemoteDebuggingGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="744a8-110">Debug Android WebViews in the same way you debug a webpage through [remote debugging][RemoteDebuggingGettingStarted].</span></span>  

## <a name="configure-android-webviews-to-debug"></a><span data-ttu-id="744a8-111">デバッグ用に Android WebViews を構成する</span><span class="sxs-lookup"><span data-stu-id="744a8-111">Configure Android WebViews to debug</span></span>  

<span data-ttu-id="744a8-112">アプリ内で Android WebView デバッグを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="744a8-112">Android WebView debugging must be turned on within your app.</span></span>  <span data-ttu-id="744a8-113">Android WebView デバッグを有効にするには、 [クラスで setWebContentsDebuggingEnabled 静的][AndroidDeveloperWebViewsSetWebContentsDebuggingEnabled] メソッドを実行 `WebView` します。</span><span class="sxs-lookup"><span data-stu-id="744a8-113">To turn on Android WebView debugging, run the [setWebContentsDebuggingEnabled][AndroidDeveloperWebViewsSetWebContentsDebuggingEnabled] static method on the `WebView` class.</span></span>  

```java
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
    WebView.setWebContentsDebuggingEnabled(true);
}
```  

<span data-ttu-id="744a8-114">この設定は、アプリのすべての Android WebView に適用されます。</span><span class="sxs-lookup"><span data-stu-id="744a8-114">The setting applies to all of the Android WebViews of the app.</span></span>  

> [!TIP]
> <span data-ttu-id="744a8-115">Android WebView のデバッグは、アプリのマニフェスト内の `debuggable` フラグの状態の影響を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="744a8-115">Android WebView debugging is not affected by the state of the `debuggable` flag in the manifest of the app.</span></span>  <span data-ttu-id="744a8-116">フラグが指定されている場合にのみ Android WebView デバッグを有効にする場合は、 `debuggable` `true` 実行時にフラグをテストします。</span><span class="sxs-lookup"><span data-stu-id="744a8-116">If you want to turn on Android WebView debugging only when the `debuggable` flag is `true`, test the flag at runtime.</span></span>  
> 
> ```java
> if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
>     if (0 != (getApplicationInfo().flags & ApplicationInfo.FLAG_DEBUGGABLE))
>    { WebView.setWebContentsDebuggingEnabled(true); }
> }
> ```  

## <a name="open-an-android-webview-in-devtools"></a><span data-ttu-id="744a8-117">DevTools で Android WebView を開く</span><span class="sxs-lookup"><span data-stu-id="744a8-117">Open an Android WebView in DevTools</span></span>  

<span data-ttu-id="744a8-118">デバイスで実行されているデバッグを有効にした Android WebView の一覧を表示するには、に移動します `edge://inspect` 。</span><span class="sxs-lookup"><span data-stu-id="744a8-118">To display a list of the Android WebViews with debugging turned on that run on your device, navigate to `edge://inspect`.</span></span>  

<span data-ttu-id="744a8-119">デバッグを開始するには、デバッグする Android WebView の下で、[検査] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="744a8-119">To start debugging, under the Android WebView you want to debug, choose **inspect**.</span></span>  <span data-ttu-id="744a8-120">リモート ブラウザー タブと同じ方法で DevTools を使用します。</span><span class="sxs-lookup"><span data-stu-id="744a8-120">Use DevTools in the same way that you do a remote browser tab.</span></span>  

<!--
:::image type="complex" source=".images/webview-debugging.msft.png" alt-text="Inspecting elements in an Android WebView" lightbox=".images/webview-debugging.msft.png":::
   Inspecting elements in an Android WebView  
:::image-end:::  

The gray graphics listed with the Android WebView represent its size and position relative to the screen of the device.  If your Android WebViews have titles set, the titles are listed as well.  
-->  

## <a name="troubleshoot"></a><span data-ttu-id="744a8-121">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="744a8-121">Troubleshoot</span></span>  

<span data-ttu-id="744a8-122">Android WebViews がページに表示 `edge://inspect` されない場合</span><span class="sxs-lookup"><span data-stu-id="744a8-122">Your Android WebViews aren't displayed on the `edge://inspect` page?</span></span>  

*   <span data-ttu-id="744a8-123">アプリで Android WebView デバッグが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="744a8-123">Verify that Android WebView debugging is turned on for your app.</span></span>  
*   <span data-ttu-id="744a8-124">デバイスで、デバッグする Android WebView を使用してアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="744a8-124">On your device, open the app with the Android WebView you want to debug.</span></span>  <span data-ttu-id="744a8-125">次に、更新 `edge://inspect` します。</span><span class="sxs-lookup"><span data-stu-id="744a8-125">Then, refresh `edge://inspect`.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="744a8-126">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="744a8-126">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "Android デバイスのリモート デバッグの|Microsoft Docs"  

[AndroidDeveloperWebViewsSetWebContentsDebuggingEnabled]: https://developer.android.com/reference/android/webkit/WebView.html#setWebContentsDebuggingEnabled(boolean) "setWebContentsDebuggingEnabled - WebView |Android 開発者"  

> [!NOTE]
> <span data-ttu-id="744a8-129">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="744a8-129">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="744a8-130">元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/webviews) つかり [、Meggin Kearney][MegginKearney] \(Tech Writer\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="744a8-130">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/webviews) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="744a8-132">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="744a8-132">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: http://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
