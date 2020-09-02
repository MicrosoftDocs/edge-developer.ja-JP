---
title: DevTools の新機能 (Microsoft Edge 81)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 10696a49a833475d59a6be1189362fdb0c26a96d
ms.sourcegitcommit: 2fa65cca74c5214601900579c0ce9f946ad8a27e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10991149"
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

以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。 これらを確認して、DevTools、VS コード拡張などの新機能を試してみてください。  開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。  

### DevTools のアクセシビリティの改善  

DevTools チームは、Chromium に170の変更を加え、色のコントラスト、キーボード、スクリーンリーダーに関する大きな問題に対応します。  Web を構築するすべての開発者は、DevTools を使用できるようにする必要があります。  

> ##### 図 1  
> キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール  
> ![キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール][ImagePerformanceToolKeyboardReaderImprovements]  

すべてのユーザーが web ページにアクセスできるようにする方法について説明します。  使用を開始するには、Microsoft Edge のアクセシビリティに関する [洞察][AccessibilityInsights] と [webhint][WebhintBrowserExtension] の拡張機能をダウンロードしてください。  

スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、 [ツイート][PostTweetEdgeDevTools] でフィードバックを送信するか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックしてフィードバックを送信してください。  

Chromium の問題 [#963183][crbug963183]  

### 他の言語での DevTools の使用  

多くの開発者は、英語だけでなく、StackOverflow や VS コードなどの他の開発者ツールをネイティブ言語で使用しています。  ここでは、開発ツールのローカライズについて説明します。ここでは、英語以外の10言語のいずれかで使用できるようになっています。  

:::row:::
   :::column span="":::
      中国語 \ (簡体字)- &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;
   :::column-end:::
   :::column span="":::
      中国語 (繁体字)- &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      フランス語– fran&#231;ais
   :::column-end:::
   :::column span="":::
      ドイツ語-deutsch
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      イタリア語-italiano
   :::column-end:::
   :::column span="":::
      日本語- &#26085;&#26412;&#35486;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      韓国語- &#54620;&#44397;&#50612;
   :::column-end:::
   :::column span="":::
      ポルトガル語-portugu&#234;s
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      ロシア語–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;
   :::column-end:::
   :::column span="":::
      スペイン語-&#241;ol
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

DevTools は、Microsoft Edge で使用する言語と自動的に一致し `edge://settings/languages` ます。  

Microsoft Edge を1つの言語で使用し、DevTools を英語のままにしておく場合は、 `F1` DevTools を押して [ [設定][Settings] ] を開き、[ **ブラウザー言語の一致**] を無効にします。  

> ##### 図 2  
> ドイツ語の DevTools  
> ![ドイツ語の DevTools][ImageLocalizedGerman]  

**コンソール** メッセージはローカライズされません。  DevTools UI で使用されている文字列のみが、Microsoft Edge で使用する言語で表示されます。  

用意されているものとは異なる言語で DevTools を使う場合は、 [ツイート][PostTweetEdgeDevTools] にサインインするか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックします。  

Chromium の問題 [#941561][crbug941561]  

### webhint Microsoft Edge extension  

Webhint Microsoft Edge 拡張機能を使用すると、web ページを簡単にスキャンして、開発ツールでアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどのフィードバックを得ることができます。  詳細はこちら [https://webhint.io][Webhint] をご覧ください。  

> ##### 図 3  
> Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ  
> ![Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ][ImageHintsTabWebhintExtension]  

[Microsoft Edge で webhint ブラウザーの拡張機能を試してみてください][MicrosoftEdgeInsiderAddons]。  拡張機能をインストールしたら、DevTools を開いて、[ヒント] タブを選択します。 ここで、カスタマイズ可能なサイトスキャンを実行します。  詳細については、 [webhint.io][WebhintBrowserExtension] にアクセスしてください。  

### 3D View (3D ビュー)  

**3D ビュー**を使って、[ドキュメントオブジェクトモデル \ (DOM \)][MDNDocumentObjectModel]または[z インデックス][MDNZIndex]スタッキングのコンテキストを移動して、web アプリケーションをデバッグします。  

> ##### 図 4  
> DevTools の3D ビュー  
> ![DevTools の3D ビュー][Image3DView]  

3d ビューにアクセスするには、キーを押して `Ctrl`  +  `Shift`  +  `P` **3d ビュー**で入力し、[ **3d ビューの表示**] を選択します。  

現在、UI を使って3D ビューに機能を追加していますので、 [フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team)をお送りください。  

Chromium の問題 [#987787][crbug987787]  

### Visual Studio コード拡張機能  

[Visual Studio コード \ (VS コード \)][VisualStudioCode]用の一部の拡張機能がリリースされました。この機能を使って、テキストエディターから、開発者ツールの機能を直接使うことができます。 以下の拡張子を確認してください。  

#### Microsoft Edge の要素  

[Microsoft Edge \ (Chromium \)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] vs コード拡張の要素を追加して、vs コード内の要素ツールを使います。  

> ##### 図 5  
> Microsoft Edge の要素を使用した VS コードの要素ツールは、 ![ Microsoft edge extension の要素を使って Vs コードの要素ツールを拡張します。][ImageElementsVisualStudioCode]  

詳細については、「 [Microsoft EDGE VS コード拡張の要素][VisualStudioCodeElementEdgeExtension]」を参照してください。  

#### Microsoft Edge 用デバッガー  

[Microsoft edge vs のコード拡張用デバッガー][VisualStudioMarketplaceDebuggerEdge]を使って、microsoft edge で実行されている JAVASCRIPT を vs コードから直接デバッグします。  

> ##### 図 6  
> VS コードの Microsoft Edge Extension のデバッガー  
> ![VS コードの Microsoft Edge Extension のデバッガー][ImageDebuggerExtensionVisualStudioCode]  

詳細については、「 [VS コードから Microsoft Edge をデバッグする方法][VisualStudioCodeDebuggerEdgeExtension]」を参照してください。  

#### Webhint  

Web ページを作成しているときに、web ページの品質を向上させるために、 [webhint][VisualStudioMarketplaceWebhintExtension] VS コード拡張を使います。 `webhint` この拡張機能は、分析に基づいて、ワークスペースファイルで診断を実行して報告し `webhint` ます。  

> ##### 図 7  
> VS コードでの tsx ファイルの分析のための webhint VS コード拡張機能  
> ![VS コードでの tsx ファイルの分析のための webhint VS コード拡張機能][ImageWebhintVisualStudioCodeExtensionWorkspace]  

[詳細については、「VS コード webhint 拡張機能」を参照して][WebhintVisualStudioCodeExtension]ください。  

### Visual Studio との統合  

Visual Studio 2019 バージョン16.2 以降では、Visual Studio デバッガーを使って、Microsoft Edge で実行されている JavaScript をデバッグします。  この機能を試すには、 [Visual Studio 2019 をダウンロード][MicrosoftVisualStudioDownloads]してください。  

> ##### 図 8  
> Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio  
> ![Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio][ImageVisualStudioLaunchWebApp]  

[詳細については、「Visual Studio からの Microsoft Edge のデバッグ」を参照して][MicrosoftVisualStudio]ください。  

### 防止コンソールのメッセージを追跡する  

追跡防止は、以前にアクセスしていない web サイトによって管理されることを防ぐ、Microsoft Edge の固有の機能です。  既定の追跡防止設定はバランスモードで、サードパーティのトラッカーと既知の悪意のあるトラッカーが、プライバシーと web の互換性のバランスを保つためにブロックされます。  特定のトラッカーがブロックされているときに、web ページの互換性をさらに把握できるように、トラッカーがブロックされたときに、コンソールでも警告メッセージが追加されています。  

> ##### 図 9  
> 予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。  
> ![予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。][ImageTrackingPrevention]  

[詳細については、「プライバシーと web の互換性のバランスを管理する」を参照して][TrackingPrevention]ください。  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 81 で利用可能なその他の機能を示します。  

### デバイスモードでの Moto G4 のサポート  

[デバイスのツールバーを有効][DeviceToolbar]にした後、**デバイス**の一覧から Moto G4 のビューポートのサイズをシミュレートします。  

> ##### 図 10  
> Moto G4 のビューポートのシミュレーション  
> ![Moto G4 のビューポートのシミュレーション][ImageMotoG4]  

[ [デバイスフレームの表示][DeviceFrame] ] をクリックして、ビューポートの周りに Moto G4 のハードウェアを表示します。  

> ##### 図 11  
> Moto G4 のハードウェアの表示  
> ![Moto G4 のハードウェアの表示][ImageMotoG4Frame]  

関連する機能:  

*   [コマンドメニュー][CommandMenu]を開き、コマンドを実行して、 `Capture screenshot` Moto G4 ハードウェアを含むビューポートのスクリーンショットを撮ります ([**デバイスの表示] フレームを**有効にした後)。  
*   [ネットワークと CPU を調整][ThrottleNetworkAndCpu] して、モバイルユーザーの web 閲覧条件をより正確にシミュレートします。  

Chromium の問題 [#924693][crbug924693]  

### Cookie 関連の更新プログラム  

#### [Cookie] ウィンドウでブロックされた cookie  

アプリケーションパネルの [Cookie] ウィンドウに、ブロックされている cookie と黄色の背景が表示されるようになりました。  

> ##### 図 12  
> アプリケーションパネルの Cookie ウィンドウのブロックされた cookie  
> ![アプリケーションパネルの Cookie ウィンドウのブロックされた cookie][ImageBlockedCookies]  

Chromium の問題 [#1030258][crbug|::ref1::|]  

#### Cookie ウィンドウの cookie の優先度  

[ネットワーク] および [アプリケーション] パネルの [Cookie] テーブルに、 **優先度** 列が含まれるようになりました。  

> [!CAUTION]
> Chromium ベースのブラウザー (Microsoft Edge など) は、cookie の優先順位をサポートしている唯一のブラウザーです。  

Chromium の問題 [#1026879][crbug1026879]  

#### すべての cookie 値を編集する  

Cookie テーブル内のすべてのセルは、[ **サイズ** ] 列のセルを除いて編集できるようになりました。この列は、cookie のネットワークサイズ (バイト単位) を表しているためです。  各列の説明については、「 [フィールド][CookiesFields] 」を参照してください。  

> ##### 図 13  
> Cookie の値を編集する  
> ![Cookie の値を編集する][ImageEditCookie]  

#### Cookie データを含める Node.js の取得としてコピーする  

ネットワーク要求を右クリックし、[ **Copy**  >  **コピーとして**コピー] を選択して、 `fetch` cookie データを含む式を取得 Node.js ます。  

> ##### 図 14  
> Node.js の取り出しとしてコピーする  
> ![Node.js の取り出しとしてコピーする][ImageCopyFetch]  

Chromium の問題 [#1029826][crbug1029826]  

### より正確な web アプリマニフェストアイコン  

以前は、アプリケーションパネルのマニフェストウィンドウは、web アプリマニフェストのアイコンを表示するために、独自の要求を送信しました。  DevTools には、Microsoft Edge で使用するマニフェストアイコンとまったく同じものが表示されるようになりました。  

> ##### 図 15  
> [マニフェスト] ウィンドウのアイコン  
> ![[マニフェスト] ウィンドウのアイコン][ImageManifestIcon]  

Chromium の問題 [#985402][crbug985402]  

### CSS コンテンツプロパティの上にマウスポインターを移動して、エスケープ解除した値を表示する  

プロパティの値の上にマウスポインターを置くと、 `content` 値のエスケープ解除されたバージョンが表示されます。  

たとえば、この [デモ][CSSContentDemo] では、擬似要素を調べると、 `p::after` [スタイル] ウィンドウにエスケープされた文字列が表示されます。  

> ##### 図 16  
> エスケープされた文字列  
> ![エスケープされた文字列][ImageEscapedString]  

値の上にマウスポインターを置くと `content` 、エスケープされていない値が表示されます。  

> ##### 図 17  
> エスケープされていない値  
> ![エスケープされていない値][ImageUnescapedString]  

### 本体の詳細なソースマップのエラー  

これで、本体のマップで読み込みまたは解析に失敗した理由について、コンソールで詳しく説明されています。  以前は、問題の原因を説明せずにエラーが表示されました。  

> ##### 図18  
> 本体でのソースマップ読み込みエラー  
> ![本体でのソースマップ読み込みエラー][ImageSourcemapError]  

### ファイルの末尾を超えてスクロールを無効にする設定  

[設定][Settings]を開いて、 **[設定] を無効**  >  **Sources**  >  にします。 [**ファイルの最後までスクロール**する] では、[**ソース**] パネルでファイルの末尾を超えてスクロールできる既定の UI 動作を無効にすることができます。  

> ##### 図19  
> [設定] で [ **ファイルの最後までスクロールを許可する** ] を無効にする  
> ![ファイルの最後までのスクロールを無効にする][ImageSettings]  

> ##### 図20  
> ソースパネルでは、ファイルの末尾を超えてスクロールすることができなくなりました  
> ![ソースパネルでは、ファイルの末尾を超えてスクロールすることができなくなりました][ImageScroll]  

## Microsoft Edge preview チャネルをダウンロードする  

Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- <<../../_shared/devtools-feedback.md>>  

<<../../_shared/canary.md>>  

<<../../_shared/discover.md>> -->  

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2020/01/a11y-performance-tool.msft.gif "図 1: キーボードナビゲーションとスクリーンリーダーの機能強化による DevTools のパフォーマンスツール"  
[ImageLocalizedGerman]: ../../images/2020/01/localized-devtools.msft.png "図 2: ドイツ語の DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2020/01/webhint-browser-extension.msft.png "図 3: webhint ブラウザー拡張機能がインストールされている場合の Microsoft Edge DevTools の [ヒント] タブ"  
[Image3DView]: ../../images/2020/01/3dview.msft.png "図 4: Microsoft Edge DevTools の3D ビュー"  
[ImageElementsVisualStudioCode]: ../../images/2020/01/elements-for-edge.msft.png "図 5: Microsoft Edge Extension の要素を使用した VS コードの要素ツール"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2020/01/vscode-debugger.msft.png "図 6: VS コードの Microsoft Edge Extension 用デバッガー"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2020/01/webhint-vscode-extension.msft.png "図 7: web ヒント VS コード拡張機能 (VS コードでの tsx ファイルの分析)"  
[ImageVisualStudioLaunchWebApp]: ../../images/2020/01/vs.msft.png "図 8: Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio"  
[ImageTrackingPrevention]: ../../images/2020/01/tracking-prevention.msft.png "図 9: 予防を追跡するときに本体に表示されるメッセージによって、トラッカーの記憶域へのアクセスがブロックされる" 
[ImageMotoG4]: ../../images/2020/01/motog4.msft.png "図 10: Moto G4 のビューポートのシミュレート" 
[ImageMotoG4Frame]: ../../images/2020/01/motog4frame.msft.png "図 11: Moto G4 ハードウェアの表示" 
[ImageBlockedCookies]: ../../images/2020/01/blockedcookies.msft.png "図 12: アプリケーションパネルの Cookie ウィンドウでブロックされた cookie"
[ImageEditCookie]: ../../images/2020/01/editcookie.msft.png "図 13: cookie の値を編集する"
[ImageCopyFetch]: ../../images/2020/01/fetchcookies.msft.png "図 14: Node.js の取り出しとしてコピーする"
[ImageManifestIcon]: ../../images/2020/01/manifesticons.msft.png "図 15: [マニフェスト] ウィンドウのアイコン"
[ImageEscapedString]: ../../images/2020/01/escapedstring.msft.png "図 16: エスケープされた文字列"
[ImageUnescapedString]: ../../images/2020/01/unescapedstring.msft.png "図 17: エスケープされていない値"
[ImageSourcemapError]: ../../images/2020/01/sourcemap.msft.png "図 18: 本体のソースマップ読み込みエラー"
[ImageSettings]: ../../images/2020/01/settings.msft.png "図 19: [設定] の [ファイルの最後までのスクロールを許可する] を無効にする"
[ImageScroll]: ../../images/2020/01/scrollingsources.msft.png "図 20: [ソース] パネルでファイルの末尾を超えてスクロールできるようになりました"

<!-- links -->  

[DeviceToolbar]: ../../../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools のデバイスモードでモバイルビューポートをシミュレートする"
[DeviceFrame]: ../../../device-mode/index.md#show-device-frame "[デバイスフレームの表示] を選択して、ビューポートの周りに物理デバイスフレームを表示します。"
[CommandMenu]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[ThrottleNetworkAndCpu]: ../../../device-mode/index.md#throttle-the-network-and-cpu "ネットワークと CPU を調整して、モバイルユーザーの web 閲覧条件をより正確にシミュレートします。"
[crbug924693]: https://crbug.com/924693 "924693: 機能の要求: Moto G4 をデバイスモードリストに追加する"
[crbug1030258]: https://crbug.com/1030258 "1030258"
[crbug1026879]: https://crbug.com/1026879 "1026879: dev 本体の [Cookie] タブに優先度が表示されない"
[CookiesFields]: ../../../storage/cookies.md#fields "Cookies テーブルのフィールド"
[crbug1029826]: https://crbug.com/1029826 "1029826: [ネットワーク] タブ-> 右クリックによるコピーの要求-> のコピー > フェッチでは cookie をコピーできません"
[crbug985402]: https://crbug.com/985402 "985402: web アプリマニフェストアイコンのエラー文字列がわかりにくくなっている"
[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "エスケープ解除した CSS コンテンツのデモ"
[Settings]: ../../../customize/index.md#settings "設定を使用して Microsoft Edge DevTools をカスタマイズする"
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |ツイートを投稿する"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題-Microsoft のドキュメント/エッジ-開発者"  
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge VS コード拡張用デバッガー"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge VS コード拡張の要素"  
[crbug963183]: https://crbug.com/963183 "963183-DevTools は WCAG に準拠していません"
[crbug941561]: https://crbug.com/941561 "941561-DevTools のローカライズ可能性"
[crbug987787]: https://crbug.com/987787 "987787-Dom 3D ビュー"
[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティの分析"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider のアドオン"  
[MicrosoftVisualStudio]: ../../../../visual-studio/index.md "Visual Studio"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Visual Studio 2019 for Windows & Mac をダウンロードする"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメントオブジェクトモデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z インデックス |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio コード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 用デバッガー-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium) の要素: Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "web ヒント"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint ブラウザ拡張 |webhint に関するドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint VS コード拡張 |webhint に関するドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿の追跡防止の向上"

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2020/01/devtools/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  