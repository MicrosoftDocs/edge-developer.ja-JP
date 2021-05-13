---
description: 開発者向けツールを使用して、ネイティブ Android アプリのリモート デバッグ WebViews Microsoft Edge開始します。
title: Android WebViews のリモート デバッグの開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 75d948465c62c63c9ccbe0fcd46616819a04e79d
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565079"
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
# <a name="get-started-with-remote-debugging-android-webviews"></a>Android WebViews のリモート デバッグの開始  

開発者ツールを使用して、ネイティブ Android アプリで Android WebViews Microsoft Edgeデバッグします。  

Android 4.4 \(KitKat\) 以降では、DevTools を使用してネイティブ Android アプリの WebView コンテンツをデバッグします。  

### <a name="summary"></a>要約  

*   ネイティブ Android アプリで Android WebView デバッグを有効にする。DevTools で Android WebViews Microsoft Edgeデバッグします。  
*   デバッグを有効にした Android WebViews の一覧を表示するには、に移動します `edge://inspect` 。  
*   リモート デバッグを使用して Web ページをデバッグするのと同じ方法で、Android WebViews [をデバッグします][RemoteDebuggingGettingStarted]。  

## <a name="configure-android-webviews-to-debug"></a>デバッグ用に Android WebViews を構成する  

アプリ内で Android WebView デバッグを有効にする必要があります。  Android WebView デバッグを有効にするには、 [クラスで setWebContentsDebuggingEnabled 静的][AndroidDeveloperWebViewsSetWebContentsDebuggingEnabled] メソッドを実行 `WebView` します。  

```java
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
    WebView.setWebContentsDebuggingEnabled(true);
}
```  

この設定は、アプリのすべての Android WebView に適用されます。  

> [!TIP]
> Android WebView のデバッグは、アプリのマニフェスト内の `debuggable` フラグの状態の影響を受け取る必要があります。  フラグが指定されている場合にのみ Android WebView デバッグを有効にする場合は、 `debuggable` `true` 実行時にフラグをテストします。  
> 
> ```java
> if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
>     if (0 != (getApplicationInfo().flags & ApplicationInfo.FLAG_DEBUGGABLE))
>    { WebView.setWebContentsDebuggingEnabled(true); }
> }
> ```  

## <a name="open-an-android-webview-in-devtools"></a>DevTools で Android WebView を開く  

デバイスで実行されているデバッグを有効にした Android WebView の一覧を表示するには、に移動します `edge://inspect` 。  

デバッグを開始するには、デバッグする Android WebView の下で、[検査] を選択 **します**。  リモート ブラウザー タブと同じ方法で DevTools を使用します。  

<!--
:::image type="complex" source=".images/webview-debugging.msft.png" alt-text="Inspecting elements in an Android WebView" lightbox=".images/webview-debugging.msft.png":::
   Inspecting elements in an Android WebView  
:::image-end:::  

The gray graphics listed with the Android WebView represent its size and position relative to the screen of the device.  If your Android WebViews have titles set, the titles are listed as well.  
-->  

## <a name="troubleshoot"></a>トラブルシューティング  

Android WebViews がページに表示 `edge://inspect` されない場合  

*   アプリで Android WebView デバッグが有効になっていることを確認します。  
*   デバイスで、デバッグする Android WebView を使用してアプリを開きます。  次に、更新 `edge://inspect` します。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "はじめに リモート デバッグ Android デバイスの使用|Microsoft Docs"  

[AndroidDeveloperWebViewsSetWebContentsDebuggingEnabled]: https://developer.android.com/reference/android/webkit/WebView.html#setWebContentsDebuggingEnabled(boolean) "setWebContentsDebuggingEnabled - WebView |Android 開発者"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/webviews) つかり [、Meggin Kearney][MegginKearney] \(Tech Writer\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: http://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
