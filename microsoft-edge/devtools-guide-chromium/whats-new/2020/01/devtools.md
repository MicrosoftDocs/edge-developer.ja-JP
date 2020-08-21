---
title: DevTools の新機能 (Microsoft Edge 81)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8e9e6885d04c7ad15a688b51cee4c16440d3ca1e
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942113"
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

# DevTools の新機能 (Microsoft Edge 81)  

## Microsoft Edge DevTools チームからのお知らせ  

以下のセクションは、Microsoft Edge DevTools チームに見つからない可能性があるお知らせの一覧です。 デベロッパー、VS コード拡張機能などで新機能を試すようにしてください。  開発者ツールの最新機能と最大の機能をすべて最新の状態に保つためには [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを [ダウンロードし、Twitter でフォローしてください][EdgeDevToolsTwitterAccount]。  

### DevTools のアクセシビリティの改善  

DevTools チームは Chromium に変更を加え、DevTools のコントラスト、キーボード、スクリーン リーダーの問題に対する影響を許可します。  Web を構築するすべてのデベロッパーが DevTools を使用できるはずです。  

> ##### 図 1  
> キーボード ナビゲーションとスクリーン リーダーの機能強化を使用した DevTools のパフォーマンス ツール  
> ![キーボード ナビゲーションとスクリーン リーダーの機能強化を使用した DevTools のパフォーマンス ツール][ImagePerformanceToolKeyboardReaderImprovements]  

すべてのユーザーが Web ページにアクセスできるようにする方法を学習します。  使い [始めるには][AccessibilityInsights] 、Microsoft Edge 用のアクセシビリティ インサイトと Web [の][WebhintBrowserExtension] 拡張機能をダウンロードします。  

スクリーン リーダーまたはキーボードを使用して DevTools 内を移動する場合は、Microsoft における [タイル][PostTweetEdgeDevTools] をタイーションするか、[フィードバックの送信] アイコンをクリックして、フィードバック [を送信してください](#getting-in-touch-with-microsoft-edge-devtools-team) 。  

Chromium の問題 [#963183][crbug963183]  

### 他の言語で DevTools を使用する  

多くのデベロッパーは、英語以外の開発者ツールをネイティブ言語で使用しています。  この DevTools のローカリゼーションのローカリゼーションを発表するため、英語の両側にある 10 の言語で使用できるようになりました。  

:::row:::
   :::column span="":::
      中小 \(簡体字\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;
   :::column-end:::
   :::column span="":::
      中チェーン \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      フランス語 – フラン&#231;フラン&#231;フラン
   :::column-end:::
   :::column span="":::
      ドイツ語 - deutsch
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      イタリア語 - イタリアノ
   :::column-end:::
   :::column span="":::
      日本語 - &#26085;&#26412;&#35486;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      Korean - &#54620;&#44397;&#50612;
   :::column-end:::
   :::column span="":::
      ポルトガル語 - ポルトガル&#234;トル
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      ロシア語 –  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;
   :::column-end:::
   :::column span="":::
      スペイン語 - エスパス&#241;ーリング
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

DevTools は、Microsoft Edge で使用する言語と自動的に対応付けます `edge://settings/languages` 。  

Microsoft Edge を 1 つの言語にして DevTools を英語のままにする場合は `F1` 、DevTools で [設定] を開き、[ブラウザー言語に合 [わせる]][Settings] **を無効にします**。  

> ##### 図 2  
> ドイツ語の DevTools  
> ![ドイツ語の DevTools][ImageLocalizedGerman]  

**本体メッセージは** ローカライズされません。  DevTools UI で使用されている文字列のみが、Microsoft Edge で使用する言語で表示されます。  

使用可能な言語とは異なる言語で DevTools を使用する場合は、弊内で [チ][PostTweetEdgeDevTools] ェイトをチェイトにするか、[フィードバックの [送信] アイコンをクリック](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromium の [問題#941561][crbug941561]  

### Webhint Microsoft Edge 拡張機能  

Webhint Microsoft Edge 拡張機能を使用すると、Web ページを簡単に見て、DevTools 内のアクセシビリティ、ブラウザー互換性、セキュリティ、パフォーマンスなどに関するフィードバックを受けることができます。  詳細については、次を参照 [https://webhint.io][Webhint] してください。  

> ##### 図 3  
> WebHint ブラウザー拡張機能がインストールされているときの DevTools の [ヒント] タブ  
> ![WebHint ブラウザー拡張機能がインストールされているときの DevTools の [ヒント] タブ][ImageHintsTabWebhintExtension]  

[Microsoft Edge の Web ブラウザー拡張機能を試してください][MicrosoftEdgeInsiderAddons]。  拡張機能をインストールしたら、DevTools を開き、[ヒント] タブを選択します。 ここから、カスタマイズ可能なサイト スキャンを実行します。  詳細については [、webhint.io][WebhintBrowserExtension] にアクセスしてください。  

### 3D View (3D ビュー)  

**3D ビューを使用して**、ドキュメント オブジェクト モデル[\(DOM\)][MDNDocumentObjectModel]または[z イン][MDNZIndex]デックス スタック コンテキストを移動して Web アプリケーションをデバッグします。  

> ##### 図 4  
> DevTools の 3D ビュー  
> ![DevTools の 3D ビュー][Image3DView]  

3D ビューにアクセスするには、3D ビュー `Ctrl`  +  `Shift`  +  `P` **に入力し、[3D ビュー****の表示] を選択します**。  

Microsoft では、UI に関する作業を行い、3D ビューに機能を追加するため、フィードバックをお送り [ください](#getting-in-touch-with-microsoft-edge-devtools-team)。  

Chromium の問題 [#987787][crbug987787]  

### Visual Studio拡張機能  

DevTools チームには、テキスト エディターから直接 DevTools の機能を利用できる [Visual Studio Code \(VS Code\)][VisualStudioCode] 用の拡張機能もいくつかリリースされています。 下の拡張機能を確認してください。  

#### Microsoft Edge の要素  

[Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]および VS コード拡張子を追加して、VS コード内から要素ツールを使用します。  

> ##### 図 5  
> Microsoft Edge 拡張機能の要素を使用した VS コードの要素ツールを ![ VS コード内の要素ツール][ImageElementsVisualStudioCode]  

詳細については [、Microsoft Edge VS コード拡張機能の要素をご覧ください][VisualStudioCodeElementEdgeExtension]。  

#### Microsoft Edge のデバッガー  

Microsoft Edge VS コード [拡張機能][VisualStudioMarketplaceDebuggerEdge] を使用して、VS コードから直接 Microsoft Edge で実行されている JavaScript をデバッグします!  

> ##### 図 6  
> VS コードの Microsoft Edge 拡張機能のデバッガー  
> ![VS コードの Microsoft Edge 拡張機能のデバッガー][ImageDebuggerExtensionVisualStudioCode]  

詳細については [、VS コードから Microsoft Edge をデバッグする方法を確認してください][VisualStudioCodeDebuggerEdgeExtension]。  

#### Webhint  

Web [ハイント][VisualStudioMarketplaceWebhintExtension] VS コード拡張機能を使用して、Web ページの作成中に Web ページ `webhint` を向上させます。 この拡張機能は分析に基づいてワークスペース ファイルに基づいて診定を実行および `webhint` レポートします。  

> ##### 図 7  
> VS コード内の .tsx ファイルを分析する Webhint VS コード拡張子  
> ![VS コード内の .tsx ファイルを分析する Webhint VS コード拡張子][ImageWebhintVisualStudioCodeExtensionWorkspace]  

[VS コードウェート拡張機能の詳細をご覧ください][WebhintVisualStudioCodeExtension]。  

### Visual Studio統合  

Visual Studio 2019 バージョン 16.2 以降では、Visual Studio デバッガーを使用して Microsoft Edge で実行されている JavaScript のデバッグを行います。  [この機能Visual Studioするには、2019][MicrosoftVisualStudioDownloads] をダウンロードしてください。  

> ##### 図 8  
> Visual Studio Microsoft Edge Canary、Dev、Beta で Web アプリを起動するオプションを使用する  
> ![Visual Studio Microsoft Edge Canary、Dev、Beta で Web アプリを起動するオプションを使用する][ImageVisualStudioLaunchWebApp]  

[Microsoft Edge のデバッグの詳細については、こちらVisual Studio。][MicrosoftVisualStudio]  

### 本体メッセージの追跡  

追跡防止は、Microsoft Edge で、これまでアクセスした Web サイトで追跡されないように保護する固有の機能です。  既定の追跡防止設定は、プライバシーと Web 互換性のバランスを取るエクスペリエンスについてサード パーティのトラッカーと既知の重大なトラッカーをブロックするバランス化モードです。  特定のトラッカーがブロックされたときに Web ページの互換性に関する分け情報を取得できるように、トラッカーがブロックされたときに本体に警告メッセージも追加されています。  

> ##### 図 9  
> トラッカーの記憶域へのアクセスを追跡している場合に本体内のメッセージ  
> ![トラッカーの記憶域へのアクセスを追跡している場合に本体内のメッセージ][ImageTrackingPrevention]  

[トラッキング防止の詳細と、][TrackingPrevention]プライバシーと Web 互換性のバランスの残高について説明します。  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、オープン ソース Chromium プロジェクトに投稿された Microsoft Edge 81 で利用可能なその他の機能について説明します。  

### デバイス モードでのモート G4 のサポート  

デバイス [ツール バーを有効][DeviceToolbar]にした後、[デバイス] の一覧からモート G4 のビューポートの大きさを **シリュレート** します。  

> ##### 図 10  
> Moto G4 ビューポートのシンボルシュ  
> ![Moto G4 ビューポートのシンボルシュ][ImageMotoG4]  

[ [デバイス フレームを][DeviceFrame] 表示] をクリックして、ビューポートの周囲の Moto G4 ハードウェアを表示します。  

> ##### 図 11  
> Moto G4 ハードウェアを示しています  
> ![Moto G4 ハードウェアを示しています][ImageMotoG4Frame]  

関連機能:  

*   コマンド メニュー[を開き][CommandMenu]、Moto G4 ハードウェアを含むビューポートの `Capture screenshot` スクリーンショットを撮るコマンドを実行します (デバイス フレームを**有効にした後)。**  
*   [モバイル ユーザーの Web 閲][ThrottleNetworkAndCpu] 覧条件をより正確にシミュレートするのにネットワークと CPU をスロットルします。  

Chromium の問題 [#924693][crbug924693]  

### Cookie 関連の更新プログラム  

#### Cookie ウィンドウでブロックされた Cookie がブロックされています  

アプリケーション パネルの Cookie ウィンドウに、黄色の背景でブロックされている Cookie が表示されるようになりました。  

> ##### 図 12  
> アプリケーション パネルの Cookie ウィンドウでブロックされた Cookie がブロックされました  
> ![アプリケーション パネルの Cookie ウィンドウでブロックされた Cookie がブロックされました][ImageBlockedCookies]  

Chromium の [問題#1030258][crbug|::ref1::|]  

#### Cookie ウィンドウの Cookie 優先度  

ネットワークパネルとアプリケーション パネルの Cookie テーブルに優先 **度列が追加されるようになり** ました。  

> [!CAUTION]
> Microsoft Edge などの Chromium ベースのブラウザーは、Cookie 優先度をサポートするブラウザーのみです。  

Chromium の問題は、Chromium [の問題#1026879][crbug1026879]  

#### すべての Cookie 値を編集する  

Cookie テーブルのすべてのセルは編集可能になり、サイズ列のセルは、 **バ** イト単位で Cookie のネットワーク サイズを表すためです。  各 [列の][CookiesFields] 説明についてはフィールドを参照してください。  

> ##### 図 13  
> Cookie 値を編集する  
> ![Cookie 値を編集する][ImageEditCookie]  

#### フェッチとしてコピーNode.jsCookie データを含める  

ネットワーク要求を右クリックし、[**Copy**  >  **コピーとしてコピーNode.js選択] を選択して** `fetch` 、Cookie データを含む式を取得します。  

> ##### 図 14  
> [コピー] Node.jsフェッチとしてコピーする  
> ![[コピー] Node.jsフェッチとしてコピーする][ImageCopyFetch]  

Chromium の [問題#1029826][crbug1029826]  

### 正確な Web アプリ マニフェスト アイコン  

以前は、アプリケーション パネルのマニフェスト ウィンドウでは、Web アプリ マニフェスト アイコンを表示するため、独自の要求を送信しました。  DevTools では、Microsoft Edge で使用されるのとまる同じマニフェスト アイコンが表示されるようになりました。  

> ##### 図 15  
> マニフェスト ウィンドウのアイコン  
> ![マニフェスト ウィンドウのアイコン][ImageManifestIcon]  

Chromium の [問題#985402][crbug985402]  

### CSS コンテンツ プロパティにマウス ポインターを置くと、不一りの値が表示される  

プロパティの値をマウスで `content` 置き、値の不予重のバージョンが表示されます。  

たとえば、このデ [モでは][CSSContentDemo] 、pseudo 要素を検査すると、[スタイル] ウィンドウにエスケープ文字列 `p::after` が表示されます。  

> ##### 図 16  
> Escaped 文字列  
> ![Escaped 文字列][ImageEscapedString]  

値にマウス ポインタ `content` ーを移動すると、未一の値が表示されます。  

> ##### 図 17  
> 不一の値  
> ![不一の値][ImageUnescapedString]  

### 本体の詳細なソース マップ エラー  

本体では、ソース マップの読み込みや解析に失敗した理由の詳細が提供されるようになりました。  以前は、エラーが発生したものを説明せずにエラーを提供していました。  

> ##### 図 18  
> 本体のソース マッチの読み込みエラー  
> ![本体のソース マッチの読み込みエラー][ImageSourcemapError]  

### ファイルの末尾のスクロールを無効にする設定  

[[設定] を開][Settings]き、[**環境設定ソース]** を無効にして、[ソース] パネルでファイルの末尾をスクロールする既定の UI 動作を  >  **Sources**  >  **Allow scrolling past end of file****無効**にします。  

> ##### 図 19  
> [設定] で [スクロールを許可する] のファイルの末尾の **スクロールを無効** にする  
> ![[スクロールを許可する] ファイルの末尾のスクロールを無効にする][ImageSettings]  

> ##### 図 20  
> [ソース] パネルでファイルの末尾をスクロールすると無効になるようになりました  
> ![[ソース] パネルでファイルの末尾をスクロールすると無効になるようになりました][ImageScroll]  

## Microsoft Edge のプレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームとのつながりを手にする  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- <<../../_shared/devtools-feedback.md>>  

<<../../_shared/canary.md>>  

<<../../_shared/discover.md>> -->  

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2020/01/a11y-performance-tool.msft.gif "図 1: キーボード ナビゲーションとスクリーン リーダーの機能強化を使用して DevTools のパフォーマンス ツール"  
[ImageLocalizedGerman]: ../../images/2020/01/localized-devtools.msft.png "図 2: ドイツ語の DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2020/01/webhint-browser-extension.msft.png "図 3: Web ホント ブラウザー拡張機能がインストールされている場合の Microsoft Edge DevTools の [ヒント] タブ"  
[Image3DView]: ../../images/2020/01/3dview.msft.png "図 4: Microsoft Edge DevTools の 3D ビュー"  
[ImageElementsVisualStudioCode]: ../../images/2020/01/elements-for-edge.msft.png "図 5: Microsoft Edge 拡張機能の要素を使用して VS コード内の要素ツール"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2020/01/vscode-debugger.msft.png "図 6:VS コードの Microsoft Edge 拡張機能のデバッガー"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2020/01/webhint-vscode-extension.msft.png "図 7: VS コードで .tsx ファイルを分析する Webhint VS コード拡張子"  
[ImageVisualStudioLaunchWebApp]: ../../images/2020/01/vs.msft.png "図 8: Microsoft Edge Canary Visual Studio、Dev、Beta で Web アプリを起動するオプションが表示された"  
[ImageTrackingPrevention]: ../../images/2020/01/tracking-prevention.msft.png "図 9: トラッカーの記憶域へのアクセスがブロックされている場合に本体内のメッセージ" 
[ImageMotoG4]: ../../images/2020/01/motog4.msft.png "図 10: Moto G4 ビューポートのシクル" 
[ImageMotoG4Frame]: ../../images/2020/01/motog4frame.msft.png "図 11:Moto G4 ハードウェアを表示する" 
[ImageBlockedCookies]: ../../images/2020/01/blockedcookies.msft.png "図 12: アプリケーション パネルの Cookie ウィンドウでブロックされている Cookie がブロックされました"
[ImageEditCookie]: ../../images/2020/01/editcookie.msft.png "図 13: Cookie 値を編集する"
[ImageCopyFetch]: ../../images/2020/01/fetchcookies.msft.png "図 14: コピーしてフェッチNode.jsする"
[ImageManifestIcon]: ../../images/2020/01/manifesticons.msft.png "図 15:マニフェスト ウィンドウのアイコン"
[ImageEscapedString]: ../../images/2020/01/escapedstring.msft.png "図 16:エスケープ文字列"
[ImageUnescapedString]: ../../images/2020/01/unescapedstring.msft.png "図 17: 未満の値"
[ImageSourcemapError]: ../../images/2020/01/sourcemap.msft.png "図 18: 本体のソース マッチの読み込みエラー"
[ImageSettings]: ../../images/2020/01/settings.msft.png "図 19:[設定] でのファイルの [スクロールを許可する] の [スクロールを許可する]"
[ImageScroll]: ../../images/2020/01/scrollingsources.msft.png "図 20: [ソース] パネルでファイルの末尾のスクロールが無効になりました"

<!-- links -->  

[DeviceToolbar]: ../../../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools のデバイス モードを使用してモバイル ビューポートをシイクルする"
[DeviceFrame]: ../../../device-mode/index.md#show-device-frame "[デバイス フレームを表示] を選びます。ビューポートの周囲にデバイス フレームが表示されます。"
[CommandMenu]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンド メニューでコマンドを実行する"  
[ThrottleNetworkAndCpu]: ../../../device-mode/index.md#throttle-the-network-and-cpu "モバイル ユーザーの Web 閲覧条件をより正確にシミュレートするのに、ネットワークと CPU をスロットルします。"
[crbug924693]: https://crbug.com/924693 "924693: 機能要求: デバイス モード リストにモート G4 を追加する"
[crbug1030258]: https://crbug.com/1030258 "1030258"
[crbug1026879]: https://crbug.com/1026879 "1026879: 開発本体の [Cookie] タブには優先度が表示されない"
[CookiesFields]: ../../../storage/cookies.md#fields "Cookie テーブルのフィールド"
[crbug1029826]: https://crbug.com/1029826 "1029826: ネットワーク タブ - > 右クリックして要求 -> コピーをリクエストする -> > コピーをリクエストしても、Cookie がコピーされない"
[crbug985402]: https://crbug.com/985402 "985402: Web アプリ マニフェスト アイコン エラー文字列がわからない"
[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "Esmo forescaped CSS コンテンツのデモ"
[Settings]: ../../../customize/index.md#settings "設定を使用して Microsoft Edge DevTools をカスタマイズする"
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |チェットを投稿する"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge 開発者"  
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge VS コード拡張機能のデバッガー"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge VS コード拡張機能の要素"  
[crbug963183]: https://crbug.com/963183 "963183 - DevTools は WCAG に準格していません"
[crbug941561]: https://crbug.com/941561 "941561 - DevTools のローカライズ性"
[crbug987787]: https://crbug.com/987787 "987787 - Dom 3D ビュー"
[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティ インサイト"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider アドオン"  
[MicrosoftVisualStudio]: ../../../../visual-studio/index.md "Visual Studio"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Windows \& Mac Visual Studio 2019 for Windows のダウンロード"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "Twitter アカウント@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studioコード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge のデバッガー - マVisual Studio市"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \(Chromium\) - マーケットプレーVisual Studioース"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "Webhint - マーケットプレVisual Studioプレース"
[Webhint]: https://aka.ms/webhint "Webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Web ハイント ブラウザー拡張 |Webhint ドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint VS コード拡張 |Webhint ドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿に追跡防止を行う"

> [!NOTE]
> このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。  
> 元のページがここに [あ](https://developers.google.com/web/updates/2020/01/devtools/index) り [、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools & Lighthouse\) によって作成されます。  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  