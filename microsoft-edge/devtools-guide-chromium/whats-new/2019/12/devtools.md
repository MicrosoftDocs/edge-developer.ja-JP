---
title: DevTools の新機能 (Microsoft Edge 80)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 03fd78eddf54b68d072ba11401a897ad9f109058
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942142"
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

# DevTools の新機能 (Microsoft Edge 80)  

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
| Chinese (Simplified) - 中文（简体）| Chinese (Traditional) - 中文（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

ローカ `edge://flags` ライズされた **開発者ツール フラグを** 有効に **設定します**。  また **、Developer Tools の実用** フラグを [有効] に **設定します**。  Microsoft Edge を再起動し、DevTools を開きます。  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  DevTools は、Microsoft Edge で使用する言語と一致します `edge://settings/languages` 。  

> ##### 図 2  
> ドイツ語の DevTools  
> ![ドイツ語の DevTools][ImageLocalizedGerman]  

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

3D ビューにアクセスするには `edge://flags` **、Developer Tools の** 有効期限フラグが有効に設定されていることを **確認します**。  Microsoft Edge を再起動し、DevTools を開きます。  `F1`DevTools 内を押すか、[設定 **] セクション**に移動し、[詳細設定] セクションに移動し **、[3D ビューを有効にする] チェック ボックスを**オンにします。 **Experiments**  次に `Ctrl`  +  `Shift`  +  `P` **、3D ビューに入力し、[3D ビュー**の表示]**を選択します**。  

Microsoft では、UI に関する作業を行い、さらに機能を 3D ビューに追加するため、フィードバックをお送り [ください](#getting-in-touch-with-microsoft-edge-devtools-team)。  

Chromium の問題 [#987787][crbug987787]

### Visual Studio拡張機能  

DevTools チームには、テキスト エディターから直接 DevTools の機能を利用できる [Visual Studio Code \(VS Code\)][VisualStudioCode] 用の拡張機能もいくつかリリースされています。 下の拡張機能を確認してください。  

#### Microsoft Edge の要素  

[Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]および VS コード拡張子を追加して、VS コード内から要素ツールを使用します。  

> ##### 図 5  
> Microsoft Edge 拡張機能の要素を使用した VS コード内の要素ツール  
> ![Microsoft Edge 拡張機能の要素を使用した VS コード内の要素ツール][ImageElementsVisualStudioCode]  

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

[ブログ投稿を読み、Microsoft Edge を使用して、Microsoft Edge を開発する方法をごVisual Studio。][MicrosoftVisualStudioBlogDebugJavascript]  

### 本体メッセージの追跡  

追跡防止は、Microsoft Edge で、これまでアクセスした Web サイトで追跡されないように保護する固有の機能です。  既定の追跡防止設定は、プライバシーと Web 互換性のバランスを取るエクスペリエンスについてサード パーティのトラッカーと既知の重大なトラッカーをブロックするバランス化モードです。  特定のトラッカーがブロックされたときに Web ページの互換性に関する分け情報を取得できるように、トラッカーがブロックされたときに本体に警告メッセージも追加されています。  

> ##### 図 9  
> トラッカーの記憶域へのアクセスを追跡している場合に本体内のメッセージ  
> ![トラッカーの記憶域へのアクセスを追跡している場合に本体内のメッセージ][ImageTrackingPrevention]  

[トラッキング防止の詳細と、][TrackingPrevention]プライバシーと Web 互換性のバランスの残高について説明します。  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、Microsoft Edge 80 で使用可能な追加機能について、オープン ソース Chromium プロジェクトに投稿された追加機能について説明します。  

### 本体でのサポートとクラスの再宣宣表示のサポート  

本体では、ステートメントの再宣宣文 `let` が `class` サポートされるようになりました。  再展開する機能は、本体を使用して新しい JavaScript コードを実実化している Web 開発者の一般的な発行者の一般的な発行者でした。  

> [!WARNING]
> 本体外または 1 つの本体入力内のスクリプトでスクリプトまたはステートメントを取り換 `let` `class` えた場合でも、引き続きそれを引き換えられます `SyntaxError` 。  

前述のとこそ、ローカル変数を再宣例すると `let` 、本体はエラーを脅威にするエラーをトラッキングします。  

> ##### 図 10  
> Microsoft Edge 79 の本体では、再宣宣宣宣書が失敗する  
> ![Microsoft Edge 79 の本体では、再宣宣宣宣書が失敗する][ImageConsoleRedeclarationFails]  

本体では、本体を再宣計算できます。  

> ##### 図 11  
> Microsoft Edge 80 の本体では、再宣宣宣宣宣宣書が成功したものが示されます  
> ![Microsoft Edge 80 の本体では、再宣宣宣宣宣宣書が成功したものが示されます][ImageConsoleRedeclarationSucceeds]  

Chromium[の問題][crbug1004193]#1004193  

### 改善された WebAssembly デバッグ機能が改善されました  

DevTools は [DWARF デバッグ標準のサポート][DwarfHome]を開始しました。つまり、DevTools 内のソース言語でのコードの手順の詳細設定、ブレードポイントの設定、スタック トレースの解決に関するサポートが向上しています。  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
> ##### Figure  
> The new DWARF-powered WebAssembly debugging  
> ![The new DWARF-powered WebAssembly debugging][ImageDwarfPoweredWebAssemblyDebugging]  
-->  

### ネットワーク パネルの更新  

#### [イニシアター] タブでイニシアター チェーンを要求する  

ネットワーク要求の開始者と依存関係を、ネストされたリストとして表示できるようになりました。  このようにすると、リソースが要求された理や特定のリソース \(スクリプト\など) の原因を理解するのに役立つことがあります。  

> ##### 図 12  
> [イニシアター] タブの要求イニシャー チェーン  
> ![[イニシアター] タブの要求イニシャー チェーン][ImageRequestInitiatorChain]  

ネットワーク [パネルでネットワーク アクティビティ][DevToolsNetworkIndex]をログ記録した後、リソースをクリックし、[ **開始者** ] タブに移動して、[イニシアタ **ー] タブに移動し、[イニシアター] タブに移動して、[イニシアター の Chainor Chain] を表示します**。  

*   検 **査されたリソースは** 太字です。  上のスクリーンショットでは `ai.2.min.js` 、検査されたリソースです。  
*   検査されたリソースの上のリソースはイ **ニシャットです**。  上のスクリーンショットでは `https://www.microsoftedgeinsider.com` 、イニシャーです `ai.2.min.js` 。  つまり、ネットワーク `https://www.microsoftedgeinsider.com` 要求を原因としています `ai.2.min.js` 。  
*   検査されたリソースの下位のリソースは依存 **関係です**。  上のスクリーンショットでは `https://dc.services.visualstudio.com/v2/track` 、依存関係があります `ai.2.min.js` 。  つまり、ネットワーク `ai.2.min.js` 要求を原因としています `https://dc.services.visualstudio.com/v2/track` 。  

> [!NOTE]
> 開始者と依存関係の情報には、ネットワーク リソースをホストしてからマウス `Shift` でホバーすることでもアクセスできます。  イ [ニシャリストと依存関係を表示する][DevToolsNetworkReferenceViewInitiatorsDependencies]。  

Chromium の [問題#842488][crbug842488]  

#### 選択したネットワーク要求を概要で強調表示する  

ネットワーク リソースをクリックして検査するためにネットワーク リソースをクリックすると、[ネットワーク パネル] の概要で、そのリソースを囲む青い枠線が **表示されるようになりました**。  これは、ネットワーク要求が予定よりも以前またはそれ以降のいかを検出するのに役立ちます。  

> ##### 図 13  
> 検査されたリソースが強調表示されている [概要] ウィンドウ  
> ![検査されたリソースが強調表示されている [概要] ウィンドウ][ImageOverviewPaneInspectedResource]  

Chromium の [問題#988253][crbug988253]  

#### [ネットワーク パネル] の URL 列とパス列  

ネットワーク パネ**ルの**新**しいパスと URL**列を使用して、各ネットワーク リソースの絶対パスまたは完全な URL を確認します。 **Network**  

> ##### 図 14  
> [ネットワーク パネル] の新しいパスと URL 列  
> ![[ネットワーク パネル] の新しいパスと URL 列][ImagePathNetworkPanel]  

ウォーターフォール テーブルの見 **出しを** 右クリックし、[ **パス]** または **[URL]** を選び、新しい列を表示します。  

Chromium の [問題#993366][crbug993366]  

#### ユーザー エージェント文字列が更新されました  

DevTools では、[ネットワーク条件] タブからカスタム ユーザー エージェント **の文字列を設定** できます。 ユーザー エージェント文字列は、ネットワーク リソースに添付された HTTP ヘッダーと値 `User-Agent` に影響します `navigator.userAgent` 。  

定義済みのユーザー エージェント文字列は、最新バージョンのブラウザー バージョンに合うように更新されました。  

> ##### 図 15  
> [ネットワークの状態] タブの [ユーザー エージェント] メニュー  
> ![[ネットワークの状態] タブの [ユーザー エージェント] メニュー][ImageUserAgentNetworkConditionsTab]  

ネットワークの**条件にアクセスするには、[**[コマンド メニュー] を開き][DevToolsCommandMenuIndex]、コマンドを実行 `Show Network Conditions` します。  

> [!NOTE]
> デバイス モードでは、 [ユーザー エージェント文字列も設定できます][DevToolsDeviceModeIndex]。  

Chromium の問題は、chromium [の#1029031][crbug1029031]  

### 監査パネルの更新  

#### 新しい構成 UI  

構成 UI には、新しく応答性が高く、構成オプションが簡素化されています。  サ [イドロットの][GitHubGoogleChromeDevToolsAuditsPanelThrottling] UI の変更の詳細については、[監査パネル] のサンプルのサタントリングを参照してください。  

> ##### 図 16  
> 新しい構成 UI  
> ![新しい構成 UI][ImageConfigurationUI]  

### カバレージ タブの更新  

#### 機能ごとまたはブロックごとのカバレッジ モード  

[[カバレージ][DevToolsCoverageIndex]] タブには、関数ごと、ブロックごとのコードカバレッジ データを収集するかどうかを指定できる**新しいドロップダウン****メニューがあります**。  **ブロックご** との範囲ごとの詳細は、さらに詳しくあり、収集の高度な機能です。  DevTools では既定で **関数ご** との範囲を使用します。  

> [!CAUTION]
> HTML ファイルでの大規模なコードの違いは、関数ごとの使用頻度とブロック モードのど **れ** で **使用されるかによって異** なります。  関数モード **で使用すると** 、HTML ファイルのインライン スクリプトは関数としては計算されます。  スクリプトがすべて実行される場合、DevTools は、スクリプト全体をコードとしてマークします。  スクリプトがまったく実行されない場合にのみ、スクリプトは未使用コードとしてマークされます。  

> ##### 図 17  
> カバレッジ モードのドロップダウン メニュー  
> ![カバレッジ モードのドロップダウン メニュー][ImageCoverageMode]  

#### カバレージをページ再読み込みで開始する必要がある  

カバレッジ データが不合成になったためにページ再読み込みを行わないようにコード カバーを切り替えます。  たとえば、ランタイムが長い時間が過ぎていて、V8 ガーバンド コレクターがクリーンアップした場合、関数を未使用として報告できます。  

Chromium の問題は、chromium [の#1004203][crbug1004203]  

## Microsoft Edge のプレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームとのつながりを手にする  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2019/12/a11y-performance-tool.msft.gif "図 1: キーボード ナビゲーションとスクリーン リーダーの機能強化を使用して DevTools のパフォーマンス ツール"  
[ImageLocalizedGerman]: ../../images/2019/12/localized-devtools.msft.png "図 2: ドイツ語の DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2019/12/webhint-browser-extension.msft.png "図 3: Web ホント ブラウザー拡張機能がインストールされている場合の Microsoft Edge DevTools の [ヒント] タブ"  
[Image3DView]: ../../images/2019/12/3dview.msft.png "図 4: Microsoft Edge DevTools の 3D ビュー"  
[ImageElementsVisualStudioCode]: ../../images/2019/12/elements-for-edge.msft.png "図 5: Microsoft Edge 拡張機能の要素を使用して VS コード内の要素ツール"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2019/12/vscode-debugger.msft.png "図 6:VS コードの Microsoft Edge 拡張機能のデバッガー"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2019/12/webhint-vscode-extension.msft.png "図 7: VS コードで .tsx ファイルを分析する Webhint VS コード拡張子"  
[ImageVisualStudioLaunchWebApp]: ../../images/2019/12/vs.msft.png "図 8: Microsoft Edge Canary Visual Studio、Dev、Beta で Web アプリを起動するオプションが表示された"  
[ImageTrackingPrevention]: ../../images/2019/12/tracking-prevention.msft.png "図 9: トラッカーの記憶域へのアクセスがブロックされている場合に本体内のメッセージ"  
[ImageConsoleRedeclarationFails]: ../../images/2019/12/letbefore.msft.png "図 10: Microsoft Edge 79 の本体では、再宣宣宣宣書が失敗する"  
[ImageConsoleRedeclarationSucceeds]: ../../images/2019/12/letafter.msft.png "図 11: Microsoft Edge 80 の本体が、再宣宣宣宣の成功を示す Microsoft Edge 80 の本体"  
[ImageRequestInitiatorChain]: ../../images/2019/12/initiators.msft.png "図 12: [イニシアター] タブの要求イニシアター チェーン"  
[ImageOverviewPaneInspectedResource]: ../../images/2019/12/overview.msft.png "図 13: 検査されたリソースが強調表示されている [概要] ウィンドウ"  
[ImagePathNetworkPanel]: ../../images/2019/12/columns.msft.png "図 14: [ネットワーク パネル] の新しいパスと URL 列"  
[ImageUserAgentNetworkConditionsTab]: ../../images/2019/12/useragent.msft.png "図 15: [ネットワーク条件] タブの [ユーザー エージェント] メニュー"  
[ImageConfigurationUI]: ../../images/2019/12/start.msft.png "図 16:新しい構成 UI"  
[ImageCoverageMode]: ../../images/2019/12/modes.msft.png "図 17: カバレッジ モードのドロップダウン メニュー"  

<!--[ImageDwarfPoweredWebAssemblyDebugging]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンド メニューでコマンドを実行する"  
[DevToolsCoverageIndex]: ../../../coverage/index.md "Microsoft Edge DevTools の [Coverage] タブで未使用の JavaScript および CSS 番号を検索する"  
[DevToolsDeviceModeIndex]: ../../../device-mode/index.md#simulate-a-mobile-viewport "モバイル ビューポートをシイクルする - Microsoft Edge DevTools のデバイス モードを使用してモバイル デバイスをシイクル化する"  
[DevToolsNetworkIndex]: ../../../network/index.md "Microsoft Edge DevTools でのネットワーク アクティビティの検査"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: ../../../network/reference.md#view-initiators-and-dependencies "イニシャリストと依存関係を表示する - ネットワーク分析参照"  
[DevGuideEdgeHtmlWhatsNew]: ../../../../dev-guide/whats-new.md "EdgeHTML の新機能"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge VS コード拡張機能のデバッガー"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge VS コード拡張機能の要素"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[crbug842488]: https://crbug.com/842488 "842488 - [イニシアター] フィールドを [ヘッダー] タブ - モナリ"  
[crbug988253]: https://crbug.com/988253 "988253 - バグのデバッグ デバッグデーション - ネットワーク要求とタイムライン グラフの間の関連付けなし - モノラル"  
[crbug993366]: https://crbug.com/993366 "993366 - ネットワーク パネル要求一覧に URL のパスの一部を表示してください - モナール"  
[crbug1004193]: https://crbug.com/1004193 "1004193 - V8 - モナールの REPL モード"  
[crbug1004203]: https://crbug.com/1004203 "1004203 - モナール"  
[crbug1029031]: https://crbug.com/1029031 "1029031 - UA 文字列が最新のものになりました - モナール" 
[crbug963183]: https://crbug.com/963183 "963183 - DevTools は WCAG に準格していません"
[crbug941561]: https://crbug.com/941561 "941561 - DevTools のローカライズ性"
[crbug987787]: https://crbug.com/987787 "987787 - Dom 3D ビュー"

[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティ インサイト"  

[DwarfHome]: https://dwarfstd.org "Dwarf Home"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools' Audits Panel Throttling - GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge 開発者"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider アドオン"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "Visual Studio |Visual Studioブログ"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Windows \& Mac Visual Studio 2019 for Windows のダウンロード"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |チェットを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "Twitter アカウント@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studioコード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge のデバッガー - マVisual Studio市"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \(Chromium\) - マーケットプレーVisual Studioース"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "Webhint - マーケットプレVisual Studioプレース"
[Webhint]: https://aka.ms/webhint "Webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Web ハイント ブラウザー拡張 |Webhint ドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint VS コード拡張 |Webhint ドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿に追跡防止を行う"
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"

> [!NOTE]
> このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。  
> 元のページがここに [あ](https://developers.google.com/web/updates/2019/12/devtools/index) り [、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools & Lighthouse\) によって作成されます。  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
