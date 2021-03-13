---
description: 3D ビュー、Visual Studio Microsoft Edge との統合など。
title: DevTools の新機能 (Microsoft Edge 81)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 204a596e2497415eefeeb8aa819106635ff30caa
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408361"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-81"></a>DevTools の新機能 (Microsoft Edge 81)  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームからのお知らせ  

以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。  DevTools、Microsoft コード拡張機能、その他の新機能を試Visual Studioお知らせをご覧ください。  開発者ツールのすべての最新および最大の機能を最新の情報に更新するには [、Microsoft Edge][MicrosoftEdgePreviewChannels] プレビュー チャネルをダウンロードし [、Twitter][EdgeDevToolsTwitterAccount]でフォローしてください。  

### <a name="accessibility-improvements-to-the-devtools"></a>DevTools のアクセシビリティの向上  

DevTools チームは、DevTools で影響の大きなカラー コントラスト、キーボード、スクリーン リーダーの問題に対処するために、クロムに対して 170 の変更を提供しました。  Web を構築する開発者は、すべての開発者が DevTools を使用できる必要があります。  

:::image type="complex" source="../../images/2020/01/a11y-performance-tool.msft.gif" alt-text="キーボード ナビゲーションとスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール" lightbox="../../images/2020/01/a11y-performance-tool.msft.gif":::
   キーボード **ナビゲーション** とスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール  
:::image-end:::  

すべてのユーザーが Web ページにアクセス可能にする方法について説明します。  Microsoft Edge [のアクセシビリティインサイト][AccessibilityInsights] と [webhint][WebhintBrowserExtension] 拡張機能をダウンロードして、開始します。  

スクリーン リーダーまたはキーボードを使用して DevTools の周りを移動する場合は[][PostTweetEdgeDevTools]、フィードバックの送信アイコンをツイートするか、フィードバックの送信アイコンを選択してフィードバック[を送信](#getting-in-touch-with-microsoft-edge-devtools-team)してください。  

クロムの問題 [#963183][CR963183]  

### <a name="using-the-devtools-in-other-languages"></a>DevTools を他の言語で使用する  

多くの開発者は、英語ではなく、母国語で StackOverflow や Visual Studio コードなどの他の開発者ツールを使用します。  英語以外の 10 か国語で使用できる DevTools のローカライズをお知らせします。  

:::row:::
   :::column span="":::
      中国語 \(簡体字\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;
   :::column-end:::
   :::column span="":::
      中国語 \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      フランス語 – フランス語&#231;ais
   :::column-end:::
   :::column span="":::
      ドイツ語 - deutsch
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      イタリア語 - イタリア語
   :::column-end:::
   :::column span="":::
      日本語 - &#26085;&#26412;&#35486;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      韓国語 - &#54620;&#44397;&#50612;
   :::column-end:::
   :::column span="":::
      ポルトガル語 - portugu&#234;s
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      ロシア語 – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;
   :::column-end:::
   :::column span="":::
      スペイン語 - espa&#241;ol
   :::column-end:::
:::row-end:::

<!--  
|  |  |  
|:--- |:--- |  
| Chinese (Simplified) - 中文(简体)（简体）| Chinese (Traditional) - 中文(繁體)（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

DevTools は、Microsoft Edge で使用する言語と自動的に一致します `edge://settings/languages` 。  

Microsoft Edge を 1 つの言語で使用し、DevTools を英語のままにする場合は `F1` 、DevTools[][Settings]で [設定] を開き、ブラウザー言語の一致を**無効**にします。  

:::image type="complex" source="../../images/2020/01/localized-devtools.msft.png" alt-text="ドイツ語の DevTools" lightbox="../../images/2020/01/localized-devtools.msft.png":::
   ドイツ語の DevTools  
:::image-end:::  

**コンソール** メッセージはローカライズされません。  DevTools UI で使用される文字列だけが、Microsoft Edge で使用する言語で表示されます。  

DevTools を使用可能な言語とは異なる言語で使用する場合は、ツイートするか、[[][PostTweetEdgeDevTools]フィードバックの送信][アイコンを選択](#getting-in-touch-with-microsoft-edge-devtools-team)します。  

クロムの問題 [#941561][CR941561]  

### <a name="webhint-microsoft-edge-extension"></a>webhint Microsoft Edge 拡張機能  

Webhint Microsoft Edge 拡張機能を使用すると、Web ページを簡単にスキャンし、DevTools 内のアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどについてフィードバックを得ることができます。  詳細については、 を参照してください [https://webhint.io][Webhint] 。  

:::image type="complex" source="../../images/2020/01/webhint-browser-extension.msft.png" alt-text="Webhint ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール" lightbox="../../images/2020/01/webhint-browser-extension.msft.png":::
   **Webhint**ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール  
:::image-end:::  

[Microsoft Edge で webhint ブラウザー拡張機能を試してみてください][MicrosoftEdgeInsiderAddons]。  拡張機能をインストールしたら、DevTools を開き、ヒント ツール **を選択** します。  ここから、カスタマイズ可能なサイト スキャンを実行します。  詳細 [については、webhint.io][WebhintBrowserExtension] を参照してください。  

### <a name="3d-view"></a>3D View (3D ビュー)  

**3D ビューを使用**して、ドキュメント オブジェクト モデル[\(DOM\)][MDNDocumentObjectModel]または[z-index][MDNZIndex]スタック コンテキストを移動して、Web アプリケーションをデバッグします。  

:::image type="complex" source="../../images/2020/01/3dview.msft.png" alt-text="DevTools の 3D ビュー" lightbox="../../images/2020/01/3dview.msft.png":::
   DevTools の 3D ビュー  
:::image-end:::  

3D ビューにアクセスするには、[3D ビュー] と入力し `Ctrl`  +  `Shift`  +  `P` **、[3D ビュー**の表示]**を選択します**。  

Microsoft Edge チームは、UI でクロム チームと作業を行い、3D ビューにさらに機能を追加していますので、フィードバックをお寄 [せください](#getting-in-touch-with-microsoft-edge-devtools-team)。  

クロムの問題 [#987787][CR987787]  

### <a name="visual-studio-code-extensions"></a>Visual Studio コード拡張機能  

DevTools チームは、テキスト エディターから [直接 devTools][VisualStudioCode] の機能を使用できる Visual Studio コードの拡張機能もいくつかリリースしました。 以下の拡張機能を確認してください。  

#### <a name="elements-for-microsoft-edge"></a>Microsoft Edge の要素  

Microsoft Edge 用の要素 [\(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studioコード拡張機能を追加して、コード内の Elements ツールVisual Studio使用します。  

:::image type="complex" source="../../images/2020/01/elements-for-edge.msft.png" alt-text="Microsoft Edge 拡張機能の要素Visual Studioコードの要素ツール" lightbox="../../images/2020/01/elements-for-edge.msft.png":::
   Microsoft **** Edge 拡張機能の要素Visual Studioコードの要素ツール  
:::image-end:::  

詳細については [、「Elements for Microsoft Edge Visual Studio コード拡張機能」を参照してください][VisualStudioCodeElementEdgeExtension]。  

#### <a name="debugger-for-microsoft-edge"></a>Microsoft Edge のデバッガー  

デバッガー for [Microsoft Edge Visual Studio][VisualStudioMarketplaceDebuggerEdge] コード拡張機能を使用して、Microsoft Edge で実行されている JavaScript をコードから直接Visual Studioします。  

:::image type="complex" source="../../images/2020/01/vscode-debugger.msft.png" alt-text="コード内の Microsoft Edge 拡張機能のデバッガー Visual Studioします。" lightbox="../../images/2020/01/vscode-debugger.msft.png":::
   コード内の Microsoft Edge 拡張機能のデバッガー Visual Studioします。  
:::image-end:::  

詳細については、「Microsoft Edge をコードからデバッグする方法」 [をVisual Studioしてください][VisualStudioCodeDebuggerEdgeExtension]。  

#### <a name="webhint"></a>Webhint  

[Webhint Visual Studio][VisualStudioMarketplaceWebhintExtension]コード拡張機能は、Web ページの作成中に Web ページを `webhint` 改善するために使用します。  この拡張機能は、分析に基づいてワークスペース ファイルで診断を実行してレポート `webhint` します。  

:::image type="complex" source="../../images/2020/01/webhint-vscode-extension.msft.png" alt-text="webhint Visual Studioコード内の .tsx ファイルを分析する Code Visual Studio拡張機能" lightbox="../../images/2020/01/webhint-vscode-extension.msft.png":::
   webhint Visual Studio コード拡張機能でファイルを分析する Visual Studio `.tsx` Code  
:::image-end:::  

[コード webhint 拡張機能Visual Studio詳細については、以下を参照してください][WebhintVisualStudioCodeExtension]。  

### <a name="visual-studio-integration"></a>Visual Studio統合  

2019 Visual Studio 16.2 以降では、Microsoft Edge で実行されている JavaScript をデバッグVisual Studioデバッガーを使用します。  [2019 Visual Studioダウンロードして][MicrosoftVisualStudioDownloads] 、この機能を試してみてください。  

:::image type="complex" source="../../images/2020/01/vs.msft.png" alt-text="Visual Studio Microsoft Edge Canary、Dev、または Beta で Web アプリを起動するオプションを使用します。" lightbox="../../images/2020/01/vs.msft.png":::
   Visual Studio Microsoft Edge Canary、Dev、または Beta で Web アプリを起動するオプションを使用します。  
:::image-end:::  

[Microsoft Edge のデバッグの詳細については、Visual Studio。][MicrosoftVisualStudio]  

### <a name="tracking-prevention-console-messages"></a>追跡防止コンソール メッセージ  

追跡防止は、以前にアクセスしたことがない Web サイトによって追跡されるのを防く Microsoft Edge の固有の機能です。  既定の追跡防止設定はバランス モードで、プライバシーと Web の互換性のバランスを取るエクスペリエンスのために、サードパーティのトラッカーと既知の悪意のあるトラッカーをブロックします。  特定のトラッカーがブロックされている場合の Web ページの互換性に関する詳細な分析情報を提供するために、トラッカーがブロック**** されているときに警告メッセージがコンソールに追加されました。  

:::image type="complex" source="../../images/2020/01/tracking-prevention.msft.png" alt-text="追跡防止がトラッカーのストレージへのアクセスをブロックする場合のコンソール内のメッセージ" lightbox="../../images/2020/01/tracking-prevention.msft.png":::
   追跡防止が **トラッカーのストレージ** へのアクセスをブロックする場合のコンソール内のメッセージ  
:::image-end:::  

[追跡防止とプライバシーと Web の互換性のバランスについて詳しくは、以下をご覧ください][TrackingPrevention]。  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

次のセクションでは、オープン ソースのクロム プロジェクトに貢献した Microsoft Edge 81 で利用できる追加機能について説明します。  

### <a name="moto-g4-support-in-device-mode"></a>デバイス モードでの Moto G4 のサポート  

デバイス [ツールバーを有効にした][DeviceToolbar]後、デバイス リストから Moto G4 ビューポートの寸法を **シミュレート** します。  

:::image type="complex" source="../../images/2020/01/motog4.msft.png" alt-text="Moto G4 ビューポートのシミュレーション" lightbox="../../images/2020/01/motog4.msft.png":::
   Moto G4 ビューポートのシミュレーション  
:::image-end:::  

[ [デバイス フレームの表示] を][DeviceFrame] 選択して、ビューポートの周囲に Moto G4 ハードウェアを表示します。  

:::image type="complex" source="../../images/2020/01/motog4frame.msft.png" alt-text="Moto G4 ハードウェアの表示" lightbox="../../images/2020/01/motog4frame.msft.png":::
   Moto G4 ハードウェアの表示  
:::image-end:::  

関連する機能:  

*   コマンド メニュー [を開き][CommandMenu] 、コマンドを実行 `Capture screenshot` して、Moto G4 ハードウェアを含むビューポートのスクリーンショットを撮ります (デバイス フレームの表示を **有効**にした後)。  
*   [ネットワークと CPU を調整して][ThrottleNetworkAndCpu] 、モバイル ユーザーの Web ブラウズ条件をより正確にシミュレートします。  

クロムの問題 [#924693][CR924693]  

### <a name="cookie-related-updates"></a>Cookie 関連の更新プログラム  

#### <a name="blocked-cookies-in-the-cookies-pane"></a>[Cookie] ウィンドウのブロックされた Cookie  

[アプリケーション] パネルの [Cookie] ウィンドウに、ブロックされた Cookie が黄色の背景で表示されます。  

:::image type="complex" source="../../images/2020/01/blockedcookies.msft.png" alt-text="[アプリケーション] パネルの [Cookie] ウィンドウでブロックされた Cookie" lightbox="../../images/2020/01/blockedcookies.msft.png":::
   [アプリケーション] パネルの [Cookie] ウィンドウでブロックされた Cookie  
:::image-end:::  

クロムの問題 [#1030258][CR1030258]  <!-- inaccessible  -->  

#### <a name="cookie-priority-in-the-cookie-pane"></a>Cookie ウィンドウの Cookie の優先度  

[ネットワーク] ツールと [アプリケーション] ツール**の** **Cookie**テーブルに [優先度] 列**が含**まれる。  

> [!CAUTION]
> クロム ベースのブラウザー (Microsoft Edge など) は、Cookie の優先度をサポートする唯一のブラウザーです。  

クロムの問題 [#1026879][CR1026879]  

#### <a name="edit-all-cookie-values"></a>すべての Cookie 値を編集する  

Cookie テーブル内のすべてのセルは、サイズ列のセルを除いて**** 編集可能になります。この列は Cookie のネットワーク サイズをバイト単位で表します。  各列の説明については、[フィールド] に [移動します][CookiesFields]。  

:::image type="complex" source="../../images/2020/01/editcookie.msft.png" alt-text="Cookie 値の編集" lightbox="../../images/2020/01/editcookie.msft.png":::
   Cookie 値の編集  
:::image-end:::  

#### <a name="copy-as-nodejs-fetch-to-include-cookie-data"></a>Cookie データをNode.jsフェッチとしてコピーする  

Cookie データを含む式を取得するには、ネットワーク要求にポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[コピーをフェッチとしてコピー] をNode.js `fetch` ****  >  **します**。  

:::image type="complex" source="../../images/2020/01/fetchcookies.msft.png" alt-text="フェッチとしてNode.jsする" lightbox="../../images/2020/01/fetchcookies.msft.png":::
   フェッチとしてNode.jsする  
:::image-end:::  

クロムの問題 [#1029826][CR1029826]  

### <a name="more-accurate-web-app-manifest-icons"></a>より正確な Web アプリ マニフェスト アイコン  

以前は、[アプリケーション] パネルの [マニフェスト] ウィンドウから、Web アプリ マニフェスト アイコンを表示するために独自の要求が送信されました。  DevTools には、Microsoft Edge で使用されるマニフェスト アイコンとまったく同じアイコンが表示されます。  

:::image type="complex" source="../../images/2020/01/manifesticons.msft.png" alt-text="[マニフェスト] ウィンドウのアイコン" lightbox="../../images/2020/01/manifesticons.msft.png":::
   [マニフェスト] ウィンドウのアイコン  
:::image-end:::  

クロムの問題 [#985402][CR985402]  

### <a name="hover-on-css-content-properties-to-display-unescaped-values"></a>CSS コンテンツ プロパティにカーソルを合わせると、エスケープされていない値が表示されます  

プロパティの値にカーソルを合 `content` わせると、エスケープされていないバージョンの値が表示されます。  

たとえば、 [このデモでは][CSSContentDemo] 、擬似要素を検査すると、エスケープされた文字列が [スタイル] `p::after` ウィンドウに **表示** されます。  

:::image type="complex" source="../../images/2020/01/escapedstring.msft.png" alt-text="エスケープされた文字列" lightbox="../../images/2020/01/escapedstring.msft.png":::
   エスケープされた文字列  
:::image-end:::  

値にカーソルを合 `content` わせると、エスケープされていない値が表示されます。  

:::image type="complex" source="../../images/2020/01/unescapedstring.msft.png" alt-text="エスケープされていない値" lightbox="../../images/2020/01/unescapedstring.msft.png":::
   エスケープされていない値  
:::image-end:::  

### <a name="more-detailed-source-map-errors-in-the-console"></a>コンソールのソース マップエラーの詳細  

コンソールでは、ソース マップの読み込みまたは解析に失敗した理由の詳細が表示されます。  以前は、何が間違っていたのかを説明せずにエラーが発生しました。  

:::image type="complex" source="../../images/2020/01/sourcemap.msft.png" alt-text="コンソールでのソース マップの読み込みエラー" lightbox="../../images/2020/01/sourcemap.msft.png":::
   コンソールでのソース マップの読み込みエラー  
:::image-end:::  

### <a name="setting-for-disabling-scrolling-past-the-end-of-a-file"></a>ファイルの末尾を過ぎたスクロールを無効にする設定  

[[設定]][Settings]を**** 開き、[基本設定のソース] を無効にする ファイルの末尾をスクロールし、[ソース] パネルでファイルの最後までスクロールできる既定の UI 動作を無効にします  >  ****  >  ****。 ****  

:::image type="complex" source="../../images/2020/01/settings.msft.png" alt-text="[ファイルの最後までスクロールを許可する] を無効にする" lightbox="../../images/2020/01/settings.msft.png":::
   [設定] **でファイルの末尾をスクロールするを許可するを** 無効にする  
:::image-end:::  

:::image type="complex" source="../../images/2020/01/scrollingsources.msft.png" alt-text="ファイルの末尾をスクロールすると、[ソース] パネルで無効になりました" lightbox="../../images/2020/01/scrollingsources.msft.png":::
   ファイルの末尾をスクロールすると、[ソース] パネルで無効になりました  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DeviceToolbar]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイル ビューポートのシミュレート - Microsoft Edge DevTools アプリケーションでデバイス モードを使用してモバイル デバイスをシミュレート|Microsoft Docs"
[DeviceFrame]: /microsoft-edge/devtools-guide-chromium/device-mode/index#show-device-frame "デバイス フレームの表示 - Microsoft Edge DevTools アプリケーションでデバイス モードを使用してモバイル デバイスをシミュレート|Microsoft Docs"
[CommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行|Microsoft Docs"  
[ThrottleNetworkAndCpu]: /microsoft-edge/devtools-guide-chromium/device-mode/index#throttle-the-network-and-cpu "ネットワークと CPU の調整 - Microsoft Edge DevTools アプリケーションでデバイス モードを使用してモバイル デバイスをシミュレート|Microsoft Docs"
[Settings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"
[MicrosoftVisualStudio]: /microsoft-edge/visual-studio/index "Visual Studio |Microsoft Docs"  
[CookiesFields]: /microsoft-edge/devtools-guide-chromium/storage/cookies#fields "Fields - Microsoft Edge DevTools を使用して Cookie を表示、編集、および削除|Microsoft Docs"  

[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge コード拡張機能Visual Studioデバッガー"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge のコード拡張機能Visual Studio要素"  

[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://aka.ms/vscode "Visual Studioコード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 用デバッガー - Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \(Chromium\) の要素 - Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio Marketplace"

[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿での追跡防止の改善"

[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider アドオン"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Windows Visual Studio Mac 用 2019 &ダウンロード"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | ツイートを投稿する"  

[CR924693]: https://crbug.com/924693 "機能要求: デバイス モード リストに Moto G4 を追加|クロム バグ"  
[CR1030258]: https://crbug.com/1030258 "CR 1030258 |クロム バグ"  
[CR1026879]: https://crbug.com/1026879 "開発コンソールの [Cookie] タブに優先度が表示|クロム バグ"  
[CR1029826]: https://crbug.com/1029826 "ネットワーク タブ ->フェッチでは cookie がコピーされないので、> コピー -> コピーを要求するを選択|クロム バグ"  
[CR985402]: https://crbug.com/985402 "Web アプリ マニフェスト アイコンのエラー文字列は、わかりにくい|クロム バグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG 準拠の|クロム バグ"  
[CR941561]: https://crbug.com/941561 "DevTools ファイルのローカライズ|クロム バグ"  
[CR987787]: https://crbug.com/987787 "Dom 3D ビュー |クロム バグ"  

[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "エスケープされていない CSS コンテンツのデモ"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - Microsoft Docs/Edge Developer"  

[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"  
[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティインサイト"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"  

[Webhint]: https://aka.ms/webhint "webhint"  

[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint Browser Extension |webhint のドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio コード拡張機能 |webhint のドキュメント"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2020/01/devtools/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  