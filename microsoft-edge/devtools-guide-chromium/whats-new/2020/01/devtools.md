---
description: 3D ビュー、Visual Studio、Microsoft Edgeとの統合など。
title: DevTools の新機能 (Microsoft Edge 81)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 03b17f524e9be55e1ed37147ce46b7a15fc3a17d
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564960"
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

以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。  DevTools、コード拡張機能、その他の新機能を試Microsoft Visual Studioお知らせをご覧ください。  開発者ツールのすべての最新および最大の機能を最新の情報に更新するには、プレビュー チャネルMicrosoft Edge[][MicrosoftEdgePreviewChannels]ダウンロードし[、Twitter][EdgeDevToolsTwitterAccount]でフォローしてください。  

### <a name="accessibility-improvements-to-the-devtools"></a>DevTools のアクセシビリティの向上  

DevTools チームは、devTools で影響の大きなカラー コントラスト、キーボード、スクリーン リーダーの問題に対処するために、Chromium に 170 の変更を提供しました。  Web を構築する開発者は、すべての開発者が DevTools を使用できる必要があります。  

:::image type="complex" source="../../images/2020/01/a11y-performance-tool.msft.gif" alt-text="キーボード ナビゲーションとスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール" lightbox="../../images/2020/01/a11y-performance-tool.msft.gif":::
   キーボード **ナビゲーション** とスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール  
:::image-end:::  

すべてのユーザーが Web ページにアクセス可能にする方法について説明します。  アクセシビリティインサイト[と][AccessibilityInsights] [webhint][WebhintBrowserExtension]拡張機能をダウンロードして、Microsoft Edgeを開始します。  

スクリーン リーダーまたはキーボードを使用して DevTools の周りを移動する場合は[][PostTweetEdgeDevTools]、フィードバックの送信アイコンをツイートするか、フィードバックの送信アイコンを選択してフィードバック[を送信](#getting-in-touch-with-microsoft-edge-devtools-team)してください。  

Chromium[の問題][CR963183]#963183  

### <a name="using-the-devtools-in-other-languages"></a>DevTools を他の言語で使用する  

多くの開発者は、英語ではなく、母国語で StackOverflow や Visual Studio Codeなどの他の開発者ツールを使用しています。  英語以外の 10 か国語で使用できる DevTools のローカライズをお知らせします。  

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

DevTools は、 で使用する言語と自動的にMicrosoft Edge一致します `edge://settings/languages` 。  

1 つの言語Microsoft Edge DevTools を英語で残す場合は、DevTools で [英語] を選択して、設定 を開き、ブラウザー言語の一致を `F1` **無効にします**。 [][DevtoolsCustomizeIndexSettings]  

:::image type="complex" source="../../images/2020/01/localized-devtools.msft.png" alt-text="ドイツ語の DevTools" lightbox="../../images/2020/01/localized-devtools.msft.png":::
   ドイツ語の DevTools  
:::image-end:::  

**コンソール** メッセージはローカライズされません。  DevTools UI で使用される文字列だけが、ユーザーが使用する言語で表示Microsoft Edge。  

DevTools を使用可能な言語とは異なる言語で使用する場合は、ツイートするか、[[][PostTweetEdgeDevTools]フィードバックの送信][アイコンを選択](#getting-in-touch-with-microsoft-edge-devtools-team)します。  

Chromium[の問題][CR941561]#941561  

### <a name="webhint-microsoft-edge-extension"></a>webhint Microsoft Edge拡張子  

webhint Microsoft Edge拡張機能を使用すると、Web ページを簡単にスキャンし、DevTools 内のアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどについてフィードバックを得ることができます。  詳細については、 を参照してください [https://webhint.io][Webhint] 。  

:::image type="complex" source="../../images/2020/01/webhint-browser-extension.msft.png" alt-text="Webhint ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール" lightbox="../../images/2020/01/webhint-browser-extension.msft.png":::
   **Webhint**ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール  
:::image-end:::  

[webhint ブラウザー拡張機能を試Microsoft Edge。][MicrosoftEdgeInsiderAddons]  拡張機能をインストールしたら、DevTools を開き、ヒント ツール **を選択** します。  ここから、カスタマイズ可能なサイト スキャンを実行します。  詳細 [については、webhint.io][WebhintBrowserExtension] を参照してください。  

### <a name="3d-view"></a>3D View (3D ビュー)  

**3D ビューを使用**して、ドキュメント オブジェクト モデル[\(DOM\)][MDNDocumentObjectModel]または[z-index][MDNZIndex]スタック コンテキストを移動して、Web アプリケーションをデバッグします。  

:::image type="complex" source="../../images/2020/01/3dview.msft.png" alt-text="DevTools の 3D ビュー" lightbox="../../images/2020/01/3dview.msft.png":::
   DevTools の 3D ビュー  
:::image-end:::  

3D ビューにアクセスするには、[3D ビュー] と入力し `Ctrl`  +  `Shift`  +  `P` **、[3D ビュー**の表示]**を選択します**。  

このMicrosoft Edgeチームは、UI Chromiumチームと作業を行い、3D ビューに機能を追加していますので、フィードバックを送信[してください](#getting-in-touch-with-microsoft-edge-devtools-team)。  

Chromium[問題#987787][CR987787]  

### <a name="visual-studio-code-extensions"></a>Visual Studio Code拡張機能  

DevTools チームは、テキスト エディター Visual Studio Code [][VisualStudioCode] DevTools の機能を直接使用できる拡張機能をリリースしました。 以下の拡張機能を確認してください。  

#### <a name="elements-for-microsoft-edge"></a>ユーザーの要素Microsoft Edge  

[\(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]拡張子の要素をVisual Studio Codeして、Microsoft Edge内の要素ツールVisual Studio Codeします。  

:::image type="complex" source="../../images/2020/01/elements-for-edge.msft.png" alt-text="拡張機能の要素を使用Visual Studio Code内の Elements ツールMicrosoft Edgeします。" lightbox="../../images/2020/01/elements-for-edge.msft.png":::
   拡張機能**の要素**を使用Visual Studio Code内の Elements ツールMicrosoft Edgeします。  
:::image-end:::  

詳細については、「Elements for [Microsoft Edge Visual Studio Code」を参照してください][VisualStudioCodeElementEdgeExtension]。  

#### <a name="debugger-for-microsoft-edge"></a>デバッガーのMicrosoft Edge  

デバッガーを[使用して、Microsoft Edge Visual Studio Code][VisualStudioMarketplaceDebuggerEdge]で実行されている JavaScript をデバッグし、Microsoft Edgeから直接実行Visual Studio Code。  

:::image type="complex" source="../../images/2020/01/vscode-debugger.msft.png" alt-text="デバッガー内の Microsoft Edge拡張機能Visual Studio Code" lightbox="../../images/2020/01/vscode-debugger.msft.png":::
   デバッガー内の Microsoft Edge拡張機能Visual Studio Code  
:::image-end:::  

詳細については、「デバッグ方法」を[参照Microsoft Edgeを参照Visual Studio Code。][VisualStudioCodeDebuggerEdgeExtension]  

#### <a name="webhint"></a>Webhint  

[webhint Visual Studio Code][VisualStudioMarketplaceWebhintExtension]は、Web ページの作成中に Web ページを改善 `webhint` するために使用します。  この拡張機能は、分析に基づいてワークスペース ファイルで診断を実行してレポート `webhint` します。  

:::image type="complex" source="../../images/2020/01/webhint-vscode-extension.msft.png" alt-text="webhint Visual Studio Codeで .tsx ファイルを分析する拡張機能Visual Studio Code" lightbox="../../images/2020/01/webhint-vscode-extension.msft.png":::
   webhint Visual Studio Codeファイルを分析する拡張機能 `.tsx` Visual Studio Code  
:::image-end:::  

[webhint 拡張機能のVisual Studio Code詳細を参照してください][WebhintVisualStudioCodeExtension]。  

### <a name="visual-studio-integration"></a>Visual Studio統合  

2019 Visual Studio 16.2 以降では、Visual Studio デバッガーを使用して、Microsoft Edge で実行されている JavaScript をデバッグします。  [2019 Visual Studioダウンロードして][MicrosoftVisualStudioDownloads]、この機能を試してみてください。  

:::image type="complex" source="../../images/2020/01/vs.msft.png" alt-text="Visual Studio、開発、またはベータ版で Web アプリを起動するMicrosoft Edgeオプションを使用します。" lightbox="../../images/2020/01/vs.msft.png":::
   Visual Studio、開発、またはベータ版で Web アプリを起動するMicrosoft Edgeオプションを使用します。  
:::image-end:::  

[デバッグの詳細については、「Microsoft Edge」をVisual Studio。][VisualStudioIndex]  

### <a name="tracking-prevention-console-messages"></a>追跡防止コンソール メッセージ  

追跡防止は、ユーザーが以前Microsoft Edge Web サイトで追跡されるのを防ごう独自の機能です。  既定の追跡防止設定はバランス モードで、プライバシーと Web の互換性のバランスを取るエクスペリエンスのために、サードパーティのトラッカーと既知の悪意のあるトラッカーをブロックします。  特定のトラッカーがブロックされている場合の Web ページの互換性に関する詳細な分析情報を提供するために、トラッカーがブロック**** されているときに警告メッセージがコンソールに追加されました。  

:::image type="complex" source="../../images/2020/01/tracking-prevention.msft.png" alt-text="追跡防止がトラッカーのストレージへのアクセスをブロックする場合のコンソール内のメッセージ" lightbox="../../images/2020/01/tracking-prevention.msft.png":::
   追跡防止が **トラッカーのストレージ** へのアクセスをブロックする場合のコンソール内のメッセージ  
:::image-end:::  

[追跡防止とプライバシーと Web の互換性のバランスについて詳しくは、以下をご覧ください][TrackingPrevention]。  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

次のセクションでは、プロジェクトのオープン ソースにMicrosoft Edgeされた 81 で利用可能な追加のChromiumします。  

### <a name="moto-g4-support-in-device-mode"></a>デバイス モードでの Moto G4 のサポート  

デバイス [ツールバーを有効にした][DevtoolsDeviceModeIndexSimulateMobileViewport]後、デバイス リストから Moto G4 ビューポートの寸法を **シミュレート** します。  

:::image type="complex" source="../../images/2020/01/motog4.msft.png" alt-text="Moto G4 ビューポートのシミュレーション" lightbox="../../images/2020/01/motog4.msft.png":::
   Moto G4 ビューポートのシミュレーション  
:::image-end:::  

[ [デバイス フレームの表示] を][DevtoolsDeviceModeIndexShowDeviceFrame] 選択して、ビューポートの周囲に Moto G4 ハードウェアを表示します。  

:::image type="complex" source="../../images/2020/01/motog4frame.msft.png" alt-text="Moto G4 ハードウェアの表示" lightbox="../../images/2020/01/motog4frame.msft.png":::
   Moto G4 ハードウェアの表示  
:::image-end:::  

関連する機能:  

*   コマンド メニュー [を開き][DevtoolsCommandMenuIndex] 、コマンドを実行 `Capture screenshot` して、Moto G4 ハードウェアを含むビューポートのスクリーンショットを撮ります (デバイス フレームの表示を **有効**にした後)。  
*   [ネットワークと CPU を調整して][DevtoolsDeviceModeIndexThrottleNetworkCpu] 、モバイル ユーザーの Web ブラウズ条件をより正確にシミュレートします。  

Chromium[の問題][CR924693]#924693  

### <a name="cookie-related-updates"></a>Cookie 関連の更新プログラム  

#### <a name="blocked-cookies-in-the-cookies-pane"></a>[Cookie] ウィンドウのブロックされた Cookie  

[アプリケーション] パネルの [Cookie] ウィンドウに、ブロックされた Cookie が黄色の背景で表示されます。  

:::image type="complex" source="../../images/2020/01/blockedcookies.msft.png" alt-text="[アプリケーション] パネルの [Cookie] ウィンドウでブロックされた Cookie" lightbox="../../images/2020/01/blockedcookies.msft.png":::
   [アプリケーション] パネルの [Cookie] ウィンドウでブロックされた Cookie  
:::image-end:::  

Chromiumの問題[#1030258][CR1030258]  <!-- inaccessible  -->  

#### <a name="cookie-priority-in-the-cookie-pane"></a>Cookie ウィンドウの Cookie の優先度  

[ネットワーク] ツールと [アプリケーション] ツール**の** **Cookie**テーブルに [優先度] 列**が含**まれる。  

> [!CAUTION]
> Chromiumベースのブラウザー (Microsoft Edgeなど) は、Cookie の優先度をサポートする唯一のブラウザーです。  

Chromiumの問題[#1026879][CR1026879]  

#### <a name="edit-all-cookie-values"></a>すべての Cookie 値を編集する  

Cookie テーブル内のすべてのセルは、サイズ列のセルを除いて**** 編集可能になります。この列は Cookie のネットワーク サイズをバイト単位で表します。  各列の説明については、[フィールド] に [移動します][DevtoolsStorageCookiesFields]。  

:::image type="complex" source="../../images/2020/01/editcookie.msft.png" alt-text="Cookie 値の編集" lightbox="../../images/2020/01/editcookie.msft.png":::
   Cookie 値の編集  
:::image-end:::  

#### <a name="copy-as-nodejs-fetch-to-include-cookie-data"></a>Cookie データをNode.jsフェッチとしてコピーする  

Cookie データを含む式を取得するには、ネットワーク要求にポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[コピーをフェッチとしてコピー] をNode.js `fetch` ****  >  **します**。  

:::image type="complex" source="../../images/2020/01/fetchcookies.msft.png" alt-text="フェッチとしてNode.jsする" lightbox="../../images/2020/01/fetchcookies.msft.png":::
   フェッチとしてNode.jsする  
:::image-end:::  

Chromium[問題#1029826][CR1029826]  

### <a name="more-accurate-web-app-manifest-icons"></a>より正確な Web アプリ マニフェスト アイコン  

以前は、[アプリケーション] パネルの [マニフェスト] ウィンドウから、Web アプリ マニフェスト アイコンを表示するために独自の要求が送信されました。  DevTools には、ユーザーが使用するマニフェスト アイコンとまったく同Microsoft Edge表示されます。  

:::image type="complex" source="../../images/2020/01/manifesticons.msft.png" alt-text="[マニフェスト] ウィンドウのアイコン" lightbox="../../images/2020/01/manifesticons.msft.png":::
   [マニフェスト] ウィンドウのアイコン  
:::image-end:::  

Chromium[問題#985402][CR985402]  

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

[[設定]][DevtoolsCustomizeIndexSettings]を開き、[**** 基本設定のソース] を無効にします ファイルの末尾をスクロールし、[ソース] パネルでファイルの最後までスクロールできる既定の  >  ****  >  **** UI**** 動作を無効にします。  

:::image type="complex" source="../../images/2020/01/settings.msft.png" alt-text="[ファイルの最後までスクロールを許可する] を無効にする" lightbox="../../images/2020/01/settings.msft.png":::
   [ファイル**の末尾をスクロールする]** を無効設定  
:::image-end:::  

:::image type="complex" source="../../images/2020/01/scrollingsources.msft.png" alt-text="ファイルの末尾をスクロールすると、[ソース] パネルで無効になりました" lightbox="../../images/2020/01/scrollingsources.msft.png":::
   ファイルの末尾をスクロールすると、[ソース] パネルで無効になりました  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../../../device-mode/index.md#simulate-a-mobile-viewport "モバイル ビューポートをシミュレートする - デバイス モードでモバイル デバイスをシミュレートする (DevTools Microsoft Edge) |Microsoft Docs"
[DevtoolsDeviceModeIndexShowDeviceFrame]: ../../../device-mode/index.md#show-device-frame "デバイス フレームの表示 - デバイス モードでモバイル デバイスをシミュレートする (DevTools Microsoft Edge) |Microsoft Docs"
[DevtoolsCommandMenuIndex]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行する | Microsoft Docs"  
[DevtoolsDeviceModeIndexThrottleNetworkCpu]: ../../../device-mode/index.md#throttle-the-network-and-cpu "ネットワークと CPU の調整 - デバイス モードでモバイル デバイスをシミュレートする (DevTools Microsoft Edge) |Microsoft Docs"
[DevtoolsCustomizeIndexSettings]: ../../../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"
[DevtoolsStorageCookiesFields]: ../../../storage/cookies.md#fields "Fields - DevTools を使用して Cookie を表示Microsoft Edge削除|Microsoft Docs"  

[VisualStudioIndex]: ../../../../visual-studio/index.md "Visual Studio |Microsoft Docs"  

[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "デバッガーの拡張機能Microsoft Edge Visual Studio Codeの|Microsoft Docs"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "拡張機能のMicrosoft Edge Visual Studio Code要素|Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioMarketplaceDebuggerEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "デバッガーのMicrosoft Edge |Visual StudioMarketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "\(Microsoft Edge\) の要素Chromium\) |Visual StudioMarketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual StudioMarketplace"

[TrackingPrevention]: https://blogs.windows.com/msedgedev/2019/12/03/improving-tracking-prevention-microsoft-edge-79 "ブログ投稿での追跡防止Microsoft Edge改善"

[MicrosoftEdgeInsiderAddons]: https://microsoftedge.microsoft.com/addons/detail/webhint/mlgfbihcfnkaenjpdcngdnhcpkdmcdee "Microsoft EdgeInsider アドオン"  
[MicrosoftVisualStudioDownloads]: https://visualstudio.microsoft.com/downloads "2019 Visual Studio 2019 for Windows & Mac をダウンロードする"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | ツイートを投稿する"  

[CR924693]: https://crbug.com/924693 "機能要求: デバイス モード リストに Moto G4 を追加|Chromiumバグ"  
[CR1030258]: https://crbug.com/1030258 "CR 1030258 |Chromiumバグ"  
[CR1026879]: https://crbug.com/1026879 "開発コンソールの [Cookie] タブに優先度が表示|Chromiumバグ"  
[CR1029826]: https://crbug.com/1029826 "ネットワーク タブ ->フェッチでは cookie がコピーされないので、> コピー -> コピーを要求するを選択|Chromiumバグ"  
[CR985402]: https://crbug.com/985402 "Web アプリ マニフェスト アイコンのエラー文字列は、わかりにくい|Chromiumバグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG 準拠の|Chromiumバグ"  
[CR941561]: https://crbug.com/941561 "DevTools ファイルのローカライズ|Chromiumバグ"  
[CR987787]: https://crbug.com/987787 "Dom 3D ビュー |Chromiumバグ"  

[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "エスケープされていない CSS コンテンツのデモ"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題 - Microsoft Docs/Edge Developer"  

[TheWebWeWant]: https://webwewant.fyi "必要な Web"  
[AccessibilityInsights]: https://accessibilityinsights.io "アクセシビリティインサイト"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  

[Webhint]: https://webhint.io "webhint"  

[WebhintBrowserExtension]: https://webhint.io/docs/user-guide/extensions/extension-browser "Webhint Browser Extension |webhint のドキュメント"  
[WebhintVisualStudioCodeExtension]: https://webhint.io/docs/user-guide/extensions/vscode-webhint "Webhint Visual Studio Code 拡張機能 |webhint のドキュメント"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developer.chrome.com/blog/new-in-devtools-81) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  