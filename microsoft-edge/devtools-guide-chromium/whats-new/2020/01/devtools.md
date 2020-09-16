---
description: 3D ビュー、Visual Studio と Microsoft Edge の統合など。
title: DevTools の新機能 (Microsoft Edge 81)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3081ebb256a9ede637aaaddc3c3cdf7a70a201bb
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015476"
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

以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。 それらを確認して、DevTools、Visual Studio コード拡張などの新機能を試してみてください。  開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。  

### DevTools のアクセシビリティの改善  

DevTools チームは、Chromium に170の変更を加え、色のコントラスト、キーボード、スクリーンリーダーに関する大きな問題に対応します。  Web を構築するすべての開発者は、DevTools を使用できるようにする必要があります。  

:::image type="complex" source="../../images/2020/01/a11y-performance-tool.msft.gif" alt-text="キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール" lightbox="../../images/2020/01/a11y-performance-tool.msft.gif":::
   キーボードナビゲーションとスクリーンリーダーの改良による DevTools の **パフォーマンス** ツール  
:::image-end:::  

すべてのユーザーが web ページにアクセスできるようにする方法について説明します。  使用を開始するには、Microsoft Edge のアクセシビリティに関する [洞察][AccessibilityInsights] と [webhint][WebhintBrowserExtension] の拡張機能をダウンロードしてください。  

スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、 [ツイート][PostTweetEdgeDevTools] でフィードバックを送信するか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックしてフィードバックを送信してください。  

Chromium の問題 [#963183][CR963183]  

### 他の言語での DevTools の使用  

多くの開発者は、英語だけでなく、StackOverflow や Visual Studio コードなどの開発者ツールをネイティブ言語で使用しています。  ここでは、開発ツールのローカライズについて説明します。ここでは、英語以外の10言語のいずれかで使用できるようになっています。  

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

:::image type="complex" source="../../images/2020/01/localized-devtools.msft.png" alt-text="ドイツ語の DevTools" lightbox="../../images/2020/01/localized-devtools.msft.png":::
   ドイツ語の DevTools  
:::image-end:::  

**コンソール** メッセージはローカライズされません。  DevTools UI で使用されている文字列のみが、Microsoft Edge で使用する言語で表示されます。  

用意されているものとは異なる言語で DevTools を使う場合は、 [ツイート][PostTweetEdgeDevTools] にサインインするか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックします。  

Chromium の問題 [#941561][CR941561]  

### webhint Microsoft Edge extension  

Webhint Microsoft Edge 拡張機能を使用すると、web ページを簡単にスキャンして、開発ツールでアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどのフィードバックを得ることができます。  詳細はこちら [https://webhint.io][Webhint] をご覧ください。  

:::image type="complex" source="../../images/2020/01/webhint-browser-extension.msft.png" alt-text="Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ" lightbox="../../images/2020/01/webhint-browser-extension.msft.png":::
   Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ **ヒント** ] タブ  
:::image-end:::  

[Microsoft Edge で webhint ブラウザーの拡張機能を試してみてください][MicrosoftEdgeInsiderAddons]。  拡張機能をインストールしたら、DevTools を開いて、[ヒント] タブを選択します。 ここで、カスタマイズ可能なサイトスキャンを実行します。  詳細については、 [webhint.io][WebhintBrowserExtension] にアクセスしてください。  

### 3D View (3D ビュー)  

**3D ビュー**を使って、[ドキュメントオブジェクトモデル \ (DOM \)][MDNDocumentObjectModel]または[z インデックス][MDNZIndex]スタッキングのコンテキストを移動して、web アプリケーションをデバッグします。  

:::image type="complex" source="../../images/2020/01/3dview.msft.png" alt-text="DevTools の3D ビュー" lightbox="../../images/2020/01/3dview.msft.png":::
   DevTools の3D ビュー  
:::image-end:::  

3d ビューにアクセスするには、キーを押して `Ctrl`  +  `Shift`  +  `P` **3d ビュー**で入力し、[ **3d ビューの表示**] を選択します。  

現在、UI を使って3D ビューに機能を追加していますので、 [フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team)をお送りください。  

Chromium の問題 [#987787][CR987787]  

### Visual Studio コード拡張機能  

開発者ツールチームは、テキストエディターから、開発者ツールのパワーを直接使うことができる [Visual Studio コード][VisualStudioCode] の拡張機能もリリースされました。 以下の拡張子を確認してください。  

#### Microsoft Edge の要素  

Visual Studio のコード拡張 [の要素][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] を追加することによって、Visual studio コード内から要素ツールを使います。  

:::image type="complex" source="../../images/2020/01/elements-for-edge.msft.png" alt-text="Microsoft Edge 拡張機能の要素を使った Visual Studio コードの要素ツール" lightbox="../../images/2020/01/elements-for-edge.msft.png":::
   Microsoft Edge 拡張機能の要素を使った Visual Studio コードの **要素** ツール  
:::image-end:::  

詳細については、「 [Microsoft Edge Visual Studio コード拡張の要素][VisualStudioCodeElementEdgeExtension]」を参照してください。  

#### Microsoft Edge 用デバッガー  

Microsoft Edge visual Studio コード拡張 [用デバッガー][VisualStudioMarketplaceDebuggerEdge] を使って、microsoft edge で実行されている JavaScript を Visual Studio コードから直接デバッグします。  

:::image type="complex" source="../../images/2020/01/vscode-debugger.msft.png" alt-text="Visual Studio コードの Microsoft Edge 拡張機能のデバッガー" lightbox="../../images/2020/01/vscode-debugger.msft.png":::
   Visual Studio コードの Microsoft Edge 拡張機能のデバッガー  
:::image-end:::  

詳細については、「 [Visual Studio コードから Microsoft Edge をデバッグする方法][VisualStudioCodeDebuggerEdgeExtension]」を参照してください。  

#### Webhint  

作成中の web ページの品質を向上させるために、 [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio のコードの拡張機能が使用されています。 `webhint` この拡張機能は、分析に基づいて、ワークスペースファイルで診断を実行して報告し `webhint` ます。  

:::image type="complex" source="../../images/2020/01/webhint-vscode-extension.msft.png" alt-text="Visual Studio コードでの tsx ファイルの分析に関する webhint Visual Studio のコード拡張" lightbox="../../images/2020/01/webhint-vscode-extension.msft.png":::
   `.tsx`Visual Studio コードでのファイルの分析に関する webhint Visual Studio コードの拡張機能  
:::image-end:::  

[Visual Studio コード web ヒントの拡張機能について、詳細はこちらをご覧][WebhintVisualStudioCodeExtension]ください。  

### Visual Studio との統合  

Visual Studio 2019 バージョン16.2 以降では、Visual Studio デバッガーを使って、Microsoft Edge で実行されている JavaScript をデバッグします。  この機能を試すには、 [Visual Studio 2019 をダウンロード][MicrosoftVisualStudioDownloads]してください。  

:::image type="complex" source="../../images/2020/01/vs.msft.png" alt-text="Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio" lightbox="../../images/2020/01/vs.msft.png":::
   Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio  
:::image-end:::  

[詳細については、「Visual Studio からの Microsoft Edge のデバッグ」を参照して][MicrosoftVisualStudio]ください。  

### 防止コンソールのメッセージを追跡する  

追跡防止は、以前にアクセスしていない web サイトによって管理されることを防ぐ、Microsoft Edge の固有の機能です。  既定の追跡防止設定はバランスモードで、サードパーティのトラッカーと既知の悪意のあるトラッカーが、プライバシーと web の互換性のバランスを保つためにブロックされます。  特定のトラッカーがブロックされているときに、web ページの互換性をさらに把握できるように、トラッカーがブロックされたときに、コンソールでも警告メッセージが追加されています。  

:::image type="complex" source="../../images/2020/01/tracking-prevention.msft.png" alt-text="予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。" lightbox="../../images/2020/01/tracking-prevention.msft.png":::
   予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。  
:::image-end:::  

[詳細については、「プライバシーと web の互換性のバランスを管理する」を参照して][TrackingPrevention]ください。  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 81 で利用可能なその他の機能を示します。  

### デバイスモードでの Moto G4 のサポート  

[デバイスのツールバーを有効][DeviceToolbar]にした後、**デバイス**の一覧から Moto G4 のビューポートのサイズをシミュレートします。  

:::image type="complex" source="../../images/2020/01/motog4.msft.png" alt-text="Moto G4 のビューポートのシミュレーション" lightbox="../../images/2020/01/motog4.msft.png":::
   Moto G4 のビューポートのシミュレーション  
:::image-end:::  

[ [デバイスフレームの表示][DeviceFrame] ] をクリックして、ビューポートの周りに Moto G4 のハードウェアを表示します。  

:::image type="complex" source="../../images/2020/01/motog4frame.msft.png" alt-text="Moto G4 のハードウェアの表示" lightbox="../../images/2020/01/motog4frame.msft.png":::
   Moto G4 のハードウェアの表示  
:::image-end:::  

関連する機能:  

*   [コマンドメニュー][CommandMenu]を開き、コマンドを実行して、 `Capture screenshot` Moto G4 ハードウェアを含むビューポートのスクリーンショットを撮ります ([**デバイスの表示] フレームを**有効にした後)。  
*   [ネットワークと CPU を調整][ThrottleNetworkAndCpu] して、モバイルユーザーの web 閲覧条件をより正確にシミュレートします。  

Chromium の問題 [#924693][CR924693]  

### Cookie 関連の更新プログラム  

#### [Cookie] ウィンドウでブロックされた cookie  

アプリケーションパネルの [Cookie] ウィンドウに、ブロックされている cookie と黄色の背景が表示されるようになりました。  

:::image type="complex" source="../../images/2020/01/blockedcookies.msft.png" alt-text="アプリケーションパネルの Cookie ウィンドウのブロックされた cookie" lightbox="../../images/2020/01/blockedcookies.msft.png":::
   アプリケーションパネルの Cookie ウィンドウのブロックされた cookie  
:::image-end:::  

Chromium の問題 [#1030258][CR1030258]  <!-- inaccessible  -->  

#### Cookie ウィンドウの cookie の優先度  

[ネットワーク] および [アプリケーション] パネルの [Cookie] テーブルに、 **優先度** 列が含まれるようになりました。  

> [!CAUTION]
> Chromium ベースのブラウザー (Microsoft Edge など) は、cookie の優先順位をサポートしている唯一のブラウザーです。  

Chromium の問題 [#1026879][CR1026879]  

#### すべての cookie 値を編集する  

Cookie テーブル内のすべてのセルは、[ **サイズ** ] 列のセルを除いて編集できるようになりました。この列は、cookie のネットワークサイズ (バイト単位) を表しているためです。  各列の説明については、「 [フィールド][CookiesFields] 」を参照してください。  

:::image type="complex" source="../../images/2020/01/editcookie.msft.png" alt-text="Cookie の値を編集する" lightbox="../../images/2020/01/editcookie.msft.png":::
   Cookie の値を編集する  
:::image-end:::  

#### Cookie データを含める Node.js の取得としてコピーする  

ネットワーク要求を右クリックし、[ **Copy**  >  **コピーとして**コピー] を選択して、 `fetch` cookie データを含む式を取得 Node.js ます。  

:::image type="complex" source="../../images/2020/01/fetchcookies.msft.png" alt-text="Node.js の取り出しとしてコピーする" lightbox="../../images/2020/01/fetchcookies.msft.png":::
   Node.js の取り出しとしてコピーする  
:::image-end:::  

Chromium の問題 [#1029826][CR1029826]  

### より正確な web アプリマニフェストアイコン  

以前は、アプリケーションパネルのマニフェストウィンドウは、web アプリマニフェストのアイコンを表示するために、独自の要求を送信しました。  DevTools には、Microsoft Edge で使用するマニフェストアイコンとまったく同じものが表示されるようになりました。  

:::image type="complex" source="../../images/2020/01/manifesticons.msft.png" alt-text="[マニフェスト] ウィンドウのアイコン" lightbox="../../images/2020/01/manifesticons.msft.png":::
   [マニフェスト] ウィンドウのアイコン  
:::image-end:::  

Chromium の問題 [#985402][CR985402]  

### CSS コンテンツプロパティの上にマウスポインターを移動して、エスケープ解除した値を表示する  

プロパティの値の上にマウスポインターを置くと、 `content` 値のエスケープ解除されたバージョンが表示されます。  

たとえば、この [デモ][CSSContentDemo] では、擬似要素を調べると、 `p::after` [スタイル] ウィンドウにエスケープされた文字列が表示されます。  

:::image type="complex" source="../../images/2020/01/escapedstring.msft.png" alt-text="エスケープされた文字列" lightbox="../../images/2020/01/escapedstring.msft.png":::
   エスケープされた文字列  
:::image-end:::  

値の上にマウスポインターを置くと `content` 、エスケープされていない値が表示されます。  

:::image type="complex" source="../../images/2020/01/unescapedstring.msft.png" alt-text="エスケープされていない値" lightbox="../../images/2020/01/unescapedstring.msft.png":::
   エスケープされていない値  
:::image-end:::  

### 本体の詳細なソースマップのエラー  

これで、本体のマップで読み込みまたは解析に失敗した理由について、コンソールで詳しく説明されています。  以前は、問題の原因を説明せずにエラーが表示されました。  

:::image type="complex" source="../../images/2020/01/sourcemap.msft.png" alt-text="本体でのソースマップ読み込みエラー" lightbox="../../images/2020/01/sourcemap.msft.png":::
   本体でのソースマップ読み込みエラー  
:::image-end:::  

### ファイルの末尾を超えてスクロールを無効にする設定  

[設定][Settings]を開いて、 **[設定] を無効**  >  **Sources**  >  にします。 [**ファイルの最後までスクロール**する] では、[**ソース**] パネルでファイルの末尾を超えてスクロールできる既定の UI 動作を無効にすることができます。  

:::image type="complex" source="../../images/2020/01/settings.msft.png" alt-text="ファイルの最後までのスクロールを無効にする" lightbox="../../images/2020/01/settings.msft.png":::
   [設定] で [ **ファイルの最後までスクロールを許可する** ] を無効にする  
:::image-end:::  

:::image type="complex" source="../../images/2020/01/scrollingsources.msft.png" alt-text="ソースパネルでは、ファイルの末尾を超えてスクロールすることができなくなりました" lightbox="../../images/2020/01/scrollingsources.msft.png":::
   ソースパネルでは、ファイルの末尾を超えてスクロールすることができなくなりました  
:::image-end:::  

## Microsoft Edge preview チャネルをダウンロードする  

Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DeviceToolbar]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイルビューポートをシミュレートする Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする |Microsoft ドキュメント"
[DeviceFrame]: /microsoft-edge/devtools-guide-chromium/device-mode/index#show-device-frame "デバイスの表示フレーム-Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートします。Microsoft ドキュメント"
[CommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[ThrottleNetworkAndCpu]: /microsoft-edge/devtools-guide-chromium/device-mode/index#throttle-the-network-and-cpu "Microsoft Edge DevTools でネットワークと CPU を調整し、デバイスモードでモバイルデバイスをシミュレートします。Microsoft ドキュメント"
[Settings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"
[MicrosoftVisualStudio]: /microsoft-edge/visual-studio/index "Visual Studio |Microsoft ドキュメント"  
[CookiesFields]: /microsoft-edge/devtools-guide-chromium/storage/cookies#fields "フィールド-Microsoft Edge DevTools を使って cookie の表示、編集、削除を行うMicrosoft ドキュメント"  

[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge Visual Studio コード拡張用デバッガー"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge Visual Studio コード拡張の要素"  

[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  

[VisualStudioCode]: https://aka.ms/vscode "Visual Studio コード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 用デバッガー-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium) の要素: Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"

[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿の追跡防止の向上"

[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider のアドオン"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Visual Studio 2019 for Windows & Mac をダウンロードする"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |ツイートを投稿する"  

[CR924693]: https://crbug.com/924693 "機能の要求: Moto G4 をデバイスモードリストに追加する |Chromium のバグ"  
[CR1030258]: https://crbug.com/1030258 "CR 1030258 |Chromium のバグ"  
[CR1026879]: https://crbug.com/1026879 "Dev 本体の [Cookie] タブに [優先度] が表示されなくなりました |Chromium のバグ"  
[CR1029826]: https://crbug.com/1029826 "[ネットワーク] タブ-> 右クリックしてコピーを要求-> のコピーでは、フェッチでは cookie はコピー > ません。Chromium のバグ"  
[CR985402]: https://crbug.com/985402 "web アプリマニフェストアイコンのエラー文字列がわかりにくくなります。Chromium のバグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG に準拠していません |Chromium のバグ"  
[CR941561]: https://crbug.com/941561 "DevTools のローカライズ可能性 |Chromium のバグ"  
[CR987787]: https://crbug.com/987787 "Dom 3D ビュー |Chromium のバグ"  

[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "エスケープ解除した CSS コンテンツのデモ"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題-Microsoft のドキュメント/エッジ-開発者"  

[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"  
[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティの分析"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメントオブジェクトモデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z インデックス |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"  

[Webhint]: https://aka.ms/webhint "web ヒント"  

[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint ブラウザ拡張 |webhint に関するドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio のコード拡張 |webhint に関するドキュメント"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2020/01/devtools/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  