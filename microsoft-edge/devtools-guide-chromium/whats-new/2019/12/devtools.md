---
description: アクセシビリティの向上、他の言語での DevTools の使用など。
title: DevTools の新機能 (Microsoft Edge 80)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 58e5bf43720c7ba94a721804eb44d82ba657b599
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564995"
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
# <a name="whats-new-in-devtools-microsoft-edge-80"></a>DevTools の新機能 (Microsoft Edge 80)  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームからのお知らせ  

以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。  DevTools、コード拡張機能、その他の新機能を試Microsoft Visual Studioお知らせをご覧ください。  開発者ツールのすべての最新および最大の機能を最新の情報に更新するには、プレビュー チャネルMicrosoft Edge[][MicrosoftEdgePreviewChannels]ダウンロードし[、Twitter][EdgeDevToolsTwitterAccount]でフォローしてください。  

### <a name="accessibility-improvements-to-the-devtools"></a>DevTools のアクセシビリティの向上  

DevTools チームは、devTools で影響の大きなカラー コントラスト、キーボード、スクリーン リーダーの問題に対処するために、Chromium に 170 の変更を提供しました。  Web を構築する開発者は、すべての開発者が DevTools を使用できる必要があります。  

:::image type="complex" source="../../images/2019/12/a11y-performance-tool.msft.gif" alt-text="キーボード ナビゲーションとスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール" lightbox="../../images/2019/12/a11y-performance-tool.msft.gif":::
   キーボード **ナビゲーション** とスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール  
:::image-end:::  

すべてのユーザーが Web ページにアクセス可能にする方法について説明します。  アクセシビリティインサイト[と][AccessibilityInsights] [webhint][WebhintBrowserExtension]拡張機能をダウンロードして、Microsoft Edgeを開始します。  

スクリーン リーダーまたはキーボードを使用して DevTools の周りを移動する場合[][PostTweetEdgeDevTools]は、フィードバックの送信アイコンをツイートするか、フィードバックの送信アイコン[を選択してフィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team)してください。  

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
| Chinese (Simplified) - 中文（简体）| Chinese (Traditional) - 中文（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

[ローカライズされた `edge://flags` 開発者ツールを有効 **にする] フラグに移動し、[** 有効] に **設定します**。  また、[開発者ツールの **実験] フラグを [** 有効] に **設定します**。  再起動Microsoft Edge DevTools を開きます。  <!-- Select `F1` in the DevTools or navigate to Settings > Experiments and check the **Match browser language** checkbox.  -->  DevTools は、 で使用する言語とMicrosoft Edge一致します `edge://settings/languages` 。  

:::image type="complex" source="../../images/2019/12/localized-devtools.msft.png" alt-text="ドイツ語の DevTools" lightbox="../../images/2019/12/localized-devtools.msft.png":::
   ドイツ語の DevTools  
:::image-end:::  

DevTools を使用可能な言語とは異なる言語で使用する場合は、ツイートするか、[[][PostTweetEdgeDevTools]フィードバックの送信][アイコンを選択](#getting-in-touch-with-microsoft-edge-devtools-team)します。  

Chromium[の問題][CR941561]#941561  

### <a name="webhint-microsoft-edge-extension"></a>webhint Microsoft Edge拡張子  

webhint Microsoft Edge拡張機能を使用すると、Web ページを簡単にスキャンし、DevTools 内のアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどについてフィードバックを得ることができます。  詳細については、 を参照してください [https://webhint.io][Webhint] 。  

:::image type="complex" source="../../images/2019/12/webhint-browser-extension.msft.png" alt-text="Webhint ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール" lightbox="../../images/2019/12/webhint-browser-extension.msft.png":::
   **Webhint**ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール  
:::image-end:::  

[webhint ブラウザー拡張機能を試Microsoft Edge。][MicrosoftEdgeInsiderAddons]  拡張機能をインストールしたら、DevTools を開き、ヒント ツール **を選択** します。  ここから、カスタマイズ可能なサイト スキャンを実行します。  詳細 [については、webhint.io][WebhintBrowserExtension] を参照してください。

### <a name="3d-view"></a>3D View (3D ビュー)  

**3D ビューを使用**して、ドキュメント オブジェクト モデル[\(DOM\)][MDNDocumentObjectModel]または[z-index][MDNZIndex]スタック コンテキストを移動して、Web アプリケーションをデバッグします。  

:::image type="complex" source="../../images/2019/12/3dview.msft.png" alt-text="DevTools の 3D ビュー" lightbox="../../images/2019/12/3dview.msft.png":::
   DevTools **の 3D** ビュー  
:::image-end:::  

3D ビューにアクセスするには、[開発者ツールの実験] フラグが [有効] に設定されています `edge://flags` 。 **** ****  再起動Microsoft Edge DevTools を開きます。  `F1`[DevTools] で選択するか、[テスト設定]**セクション**を開き、[3D ビューを有効にする  >  ****]**チェック ボックスをオン**にします。  次に `Ctrl`  +  `Shift`  +  `P` **、[3D**ビュー] と入力し **、[3D ビューの表示] を選択します**。  

UI に取り組み、3D ビューに機能を追加していますので、フィードバックをお寄 [せください](#getting-in-touch-with-microsoft-edge-devtools-team)。  

Chromium[問題#987787][CR987787]

### <a name="visual-studio-code-extensions"></a>Visual Studio Code拡張機能  

DevTools チームは、テキスト エディター Visual Studio Code [][VisualStudioCode] DevTools の機能を直接使用できる拡張機能をリリースしました。 次の拡張機能を確認してください。  

#### <a name="elements-for-microsoft-edge"></a>ユーザーの要素Microsoft Edge  

拡張機能 (Visual Studio Code) の要素を追加して、Microsoft Edge[内ChromiumツールVisual Studio Code][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]します。  

:::image type="complex" source="../../images/2019/12/elements-for-edge.msft.png" alt-text="拡張機能の要素を使用Visual Studio Code内の Elements ツールMicrosoft Edgeします。" lightbox="../../images/2019/12/elements-for-edge.msft.png":::
   拡張機能**の要素**を使用Visual Studio Code内の Elements ツールMicrosoft Edgeします。  
:::image-end:::  

詳細については、「Elements for [Microsoft Edge Visual Studio Code」を参照してください][VisualStudioCodeElementEdgeExtension]。  

#### <a name="debugger-for-microsoft-edge"></a>デバッガーのMicrosoft Edge  

デバッガーを[使用して、Microsoft Edge Visual Studio Code][VisualStudioMarketplaceDebuggerEdge]で実行されている JavaScript をデバッグし、Microsoft Edgeから直接実行Visual Studio Code。  

:::image type="complex" source="../../images/2019/12/vscode-debugger.msft.png" alt-text="デバッガー内の Microsoft Edge拡張機能Visual Studio Code" lightbox="../../images/2019/12/vscode-debugger.msft.png":::
   デバッガー内の Microsoft Edge拡張機能Visual Studio Code  
:::image-end:::  

詳細については、「デバッグ方法」を[参照Microsoft Edgeを参照Visual Studio Code。][VisualStudioCodeDebuggerEdgeExtension]  

#### <a name="webhint"></a>Webhint  

[webhint Visual Studio Code][VisualStudioMarketplaceWebhintExtension]は、Web ページの作成中に Web ページを改善 `webhint` するために使用します。 この拡張機能は、分析に基づいてワークスペース ファイルで診断を実行してレポート `webhint` します。  

:::image type="complex" source="../../images/2019/12/webhint-vscode-extension.msft.png" alt-text="webhint Visual Studio Codeで .tsx ファイルを分析する拡張機能Visual Studio Code" lightbox="../../images/2019/12/webhint-vscode-extension.msft.png":::
   webhint Visual Studio Codeファイルを分析する拡張機能 `.tsx` Visual Studio Code  
:::image-end:::  

[webhint 拡張機能のVisual Studio Code詳細を参照してください][WebhintVisualStudioCodeExtension]。  

### <a name="visual-studio-integration"></a>Visual Studio統合  

2019 Visual Studio 16.2 以降では、Visual Studio デバッガーを使用して、Microsoft Edge で実行されている JavaScript をデバッグします。  [2019 Visual Studioダウンロード][MicrosoftVisualStudioDownloads]して、この機能を試してください。  

:::image type="complex" source="../../images/2019/12/vs.msft.png" alt-text="Visual Studio、開発、またはベータ版で Web アプリを起動するMicrosoft Edgeオプションを使用します。" lightbox="../../images/2019/12/vs.msft.png":::
   Visual Studio、開発、またはベータ版で Web アプリを起動するMicrosoft Edgeオプションを使用します。  
:::image-end:::  

[ブログの投稿を読んで、ブログ記事からMicrosoft EdgeをVisual Studio。][MicrosoftVisualStudioBlogDebugJavascript]  

### <a name="tracking-prevention-console-messages"></a>追跡防止コンソール メッセージ  

追跡防止は、Web サイトをMicrosoft Edgeする前に Web サイトで追跡されるのをブロックする、サイト内の一意の機能です。  既定の追跡防止設定はバランス モードで、プライバシーと Web の互換性のバランスを取るエクスペリエンスのために、サードパーティのトラッカーと既知の悪意のあるトラッカーをブロックします。  特定のトラッカーがブロックされている場合の Web ページの互換性に関する詳細な分析情報を提供するために、Microsoft Edge チームはトラッカーがブロックされている**** ときに警告メッセージをコンソールに追加しました。  

:::image type="complex" source="../../images/2019/12/tracking-prevention.msft.png" alt-text="追跡防止がトラッカーのストレージへのアクセスをブロックする場合のコンソール内のメッセージ" lightbox="../../images/2019/12/tracking-prevention.msft.png":::
   追跡防止が **トラッカーのストレージ** へのアクセスをブロックする場合のコンソール内のメッセージ  
:::image-end:::  

[追跡防止とプライバシーと Web の互換性のバランスについて詳しくは、以下をご覧ください][TrackingPrevention]。  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

次のセクションでは、80 で利用可能Microsoft Edge、プロジェクトのオープン ソースにChromiumします。  

### <a name="support-for-let-and-class-redeclarations-in-the-console"></a>コンソールでの let および class redeclarations のサポート  

コンソール **は** 、ステートメントの再宣言 `let` を `class` サポートします。  redeclare が利用できなかったのは、コンソールを使用して新しい JavaScript コードを試す Web 開発者に対して一般的な迷惑でした。  

> [!WARNING]
> コンソールの外部または単一のコンソール入力内のスクリプトで a または ステートメントを再設定すると、引き続き `let` `class` `SyntaxError` .  

たとえば、以前は、ローカル変数を使用して再宣言すると、 `let` コンソールはエラーを発生しました。  

:::image type="complex" source="../../images/2019/12/letbefore.msft.png" alt-text="79 のコンソールMicrosoft Edge再宣言が失敗した場合" lightbox="../../images/2019/12/letbefore.msft.png":::
   **79**のコンソールMicrosoft Edge再宣言が失敗した場合  
:::image-end:::  

次に、コンソールで再宣言を許可します。  

:::image type="complex" source="../../images/2019/12/letafter.msft.png" alt-text="let 再宣言Microsoft Edge成功を示す 80 のコンソール" lightbox="../../images/2019/12/letafter.msft.png":::
   let **** 再宣言Microsoft Edge成功を示すコンソール (80)  
:::image-end:::  

Chromiumの問題[#1004193][CR1004193]  

### <a name="improved-webassembly-debugging"></a>WebAssembly デバッグの改善  

DevTools は DWARF デバッグ標準のサポートを開始しました。つまり、コードのステップオーバー、ブレークポイントの設定、DevTools 内のソース言語でのスタック トレースの解決に対するサポートが強化されました。  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
:::image type="complex" source="../../images/2019/12/wasm.msft.png" alt-text="The new DWARF-powered WebAssembly debugging" lightbox="../../images/2019/12/wasm.msft.png":::
   The new DWARF-powered WebAssembly debugging  
:::image-end:::  
-->  

### <a name="network-panel-updates"></a>ネットワーク パネルの更新  

#### <a name="request-initiator-chains-in-the-initiator-panel"></a>イニシエーター パネルでイニシエータ チェーンを要求する  

これで、ネットワーク要求の開始者と依存関係を入れ子になったリストとして表示できます。  これは、リソースが要求された理由、または特定のリソース \(script\など) が引き起こしたネットワーク アクティビティを理解するのに役立ちます。  

:::image type="complex" source="../../images/2019/12/initiators.msft.png" alt-text="イニシエーター パネルの要求イニシエーター チェーン" lightbox="../../images/2019/12/initiators.msft.png":::
   イニシエーター パネルの要求 **イニシエーター** チェーン  
:::image-end:::  

[[ネットワーク] パネルでネットワーク アクティビティを][DevToolsNetworkIndex]ログに記録した後、リソース**** を選択し、[イニシエーター] パネルに移動して、要求イニシエータ**ー チェーンを表示します**。  

*   検査 **されたリソースは太字** です。  上のスクリーンショットでは `ai.2.min.js` 、検査されたリソースです。  
*   検査されたリソースの上にあるリソースは、イニシエータ **ーです**。  上のスクリーンショットでは `https://www.microsoftedgeinsider.com` 、 の開始者 `ai.2.min.js` です。  つまり、ネットワーク `https://www.microsoftedgeinsider.com` 要求が発生しました `ai.2.min.js` 。  
*   検査されたリソースの下のリソースは、依存関係 **です**。  上のスクリーンショットでは `https://dc.services.visualstudio.com/v2/track` 、 の依存関係です `ai.2.min.js` 。  つまり、ネットワーク `ai.2.min.js` 要求が発生しました `https://dc.services.visualstudio.com/v2/track` 。  

> [!NOTE]
> イニシエーターと依存関係の情報にアクセスするには、ネットワーク リソースを保持してから `Shift` ホバリングします。  [イニシエータと [依存関係の表示] に移動します][DevToolsNetworkReferenceDisplayInitiatorsDependencies]。  

Chromium[問題#842488][CR842488]  

#### <a name="highlight-the-selected-network-request-in-the-overview"></a>[概要] で選択したネットワーク要求を強調表示する  

ネットワーク リソースを検査するために選択した後、ネットワーク パネルは、そのリソースの周囲に青い枠線を [概要] に **表示します**。  これにより、ネットワーク要求が予想よりも早くまたは後で発生した場合の検出に役立ちます。  

:::image type="complex" source="../../images/2019/12/overview.msft.png" alt-text="検査されたリソースを強調表示する [概要] ウィンドウ" lightbox="../../images/2019/12/overview.msft.png":::
   検査 **されたリソース** を強調表示する [概要] ウィンドウ  
:::image-end:::  

Chromium[の問題][CR988253]#988253  

#### <a name="url-and-path-columns-in-the-network-panel"></a>[ネットワーク] パネルの URL 列とパス列  

ネットワーク ツールの**新しい [パス**] 列と******[URL]** 列を使用して、各ネットワーク リソースの絶対パスまたは完全な URL を表示します。  

:::image type="complex" source="../../images/2019/12/columns.msft.png" alt-text="[ネットワーク] パネルの新しい [パス] 列と [URL] 列" lightbox="../../images/2019/12/columns.msft.png":::
   ネットワーク ツールの新しい [パス] **列と** [URL] 列  
:::image-end:::  

新しい列を表示するには、**ウォーター**フォール テーブル ヘッダーにマウス ポインターを置き、コンテキスト メニュー \(righ-click\) を開き、[パス] または **[URL]****を**選択します。  

Chromium[問題#993366][CR993366]  

#### <a name="updated-user-agent-strings"></a>更新されたUser-Agent文字列  

DevTools では、[ネットワーク条件] パネルをUser-Agentカスタム 文字列 **の設定がサポート** されています。  このUser-Agentは、ネットワーク リソースに接続されている HTTP ヘッダーに影響します。また、 `User-Agent` の値にも影響します `navigator.userAgent` 。  

定義済みのUser-Agentは、最新のブラウザー バージョンを反映するように更新されています。  

:::image type="complex" source="../../images/2019/12/useragent.msft.png" alt-text="[ネットワーク条件] パネルの [ユーザー エージェント] メニュー" lightbox="../../images/2019/12/useragent.msft.png":::
   [ネットワーク条件] パネルの **[ユーザー エージェント]** メニュー  
:::image-end:::  

ネットワーク条件**にアクセスするには、**[コマンド メニューを開き][DevToolsCommandMenuIndex]、コマンドを実行 `Show Network Conditions` します。  

> [!NOTE]
> デバイス モードで [文字列User-Agent設定することもできます][DevToolsDeviceModeIndex]。  

Chromiumの問題[#1029031][CR1029031]  

### <a name="audits-panel-updates"></a>監査パネルの更新  

#### <a name="new-configuration-ui"></a>新しい構成 UI  

構成 UI には応答性の高い新しいデザインが追加され、調整の構成オプションが簡略化されました。  調整 UI の変更の詳細については [、「Audits Panel Throttling」に移動します][GitHubGoogleChromeDevToolsAuditsPanelThrottling]。  

:::image type="complex" source="../../images/2019/12/start.msft.png" alt-text="新しい構成 UI" lightbox="../../images/2019/12/start.msft.png":::
   新しい構成 UI  
:::image-end:::  

### <a name="coverage-tool-updates"></a>カバレッジ ツールの更新  

#### <a name="per-function-or-per-block-coverage-modes"></a>関数単位またはブロック単位のカバレッジ モード  

カバレッジ[ツールには][DevToolsCoverageIndex]新しいドロップダウン メニューが追加され、コード カバレッジ データを関数**** ごとに収集するか、ブロックごとに収集するかどうかを**指定できます**。  **ブロックごとのカバレッジ** は、より詳細ですが、収集するコストもはるかに高くなります。  DevTools では、関数 **ごとの範囲が既定** で使用されます。  

> [!CAUTION]
> HTML ファイルのコード範囲の違いは、関数ごとに使用するか、ブロック**** モードごとに使用するかによって**大きく異なる場合**があります。  関数ごとの **モードを使用する** 場合、HTML ファイル内のインライン スクリプトは関数として扱います。  スクリプトが全く実行されている場合、DevTools はスクリプト全体を使用コードとしてマークします。  スクリプトが全く実行されない場合にのみ、DevTools はスクリプトを未使用のコードとしてマークします。  

:::image type="complex" source="../../images/2019/12/modes.msft.png" alt-text="[カバレッジ モード] ドロップダウン メニュー" lightbox="../../images/2019/12/modes.msft.png":::
   [カバレッジ モード] ドロップダウン メニュー  
:::image-end:::  

#### <a name="coverage-must-now-be-initiated-by-a-page-refresh"></a>ページの更新によってカバレッジを開始する必要があります  

ページの更新を行わずにコード範囲を切り込むのは、カバレッジ データが不当だったため削除されました。  たとえば、ランタイムが長時間前で、V8 ガベージ コレクターがクリーンアップした場合、関数が使用されていないと報告される場合があります。  

Chromiumの問題[#1004203][CR1004203]  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevToolsCommandMenuIndex]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行する | Microsoft Docs"  
[DevToolsCoverageIndex]: ../../../coverage/index.md "DevTools ページの [カバレッジ] ツールを使用して、使用されていない JavaScript および CSS Microsoft Edgeを|Microsoft Docs"  
[DevToolsDeviceModeIndex]: ../../../device-mode/index.md#simulate-a-mobile-viewport "モバイル ビューポートをシミュレートする - デバイス モードでモバイル デバイスをシミュレートする (DevTools Microsoft Edge) |Microsoft Docs"  
[DevToolsNetworkIndex]: ../../../network/index.md "DevTools サーバーでネットワークMicrosoft Edgeを調|Microsoft Docs"  
[DevToolsNetworkReferenceDisplayInitiatorsDependencies]: ../../../network/reference.md#display-initiators-and-dependencies "開始者と依存関係の表示 - ネットワーク分析リファレンス |Microsoft Docs"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "デバッガーの拡張機能Microsoft Edge Visual Studio Codeの|Microsoft Docs"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "拡張機能のMicrosoft Edge Visual Studio Code要素|Microsoft Docs"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[CR842488]: https://crbug.com/842488 "[イニシエーター] フィールドを [ヘッダー] タブに追加|Chromiumバグ"  
[CR988253]: https://crbug.com/988253 "Bug DevTools - ネットワーク要求とタイムライン の間に関連付Graph |Chromiumバグ"  
[CR993366]: https://crbug.com/993366 "ネットワーク パネル要求リストに URL のパス部分を表示|Chromiumバグ"  
[CR1004193]: https://crbug.com/1004193 "V8 の REPL モード|Chromiumバグ"  
[CR1004203]: https://crbug.com/1004203 "コード カバレッジをすばらしい|Chromiumバグ"  
[CR1029031]: https://crbug.com/1029031 "UA 文字列が古くなっている|Chromiumバグ" 
[CR963183]: https://crbug.com/963183 "DevTools は WCAG 準拠の|Chromiumバグ"
[CR941561]: https://crbug.com/941561 "DevTools ファイルのローカライズ|Chromiumバグ"
[CR987787]: https://crbug.com/987787 "Dom 3D ビュー |Chromiumバグ"

[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティインサイト"  

[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools の監査パネル調整 - GoogleChrome/ライトハウス |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edgeプレビュー チャネル"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft EdgeInsider アドオン"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "JavaScript を Microsoft EdgeからデバッグVisual Studio |Visual Studioブログ"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "ダウンロード Visual Studio 2019 for Windows \& Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio Code"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "デバッガー for Microsoft Edge - Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "\Chromium(Microsoft Edge\) の要素 - Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint Browser Extension |webhint のドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio Code 拡張機能 |webhint のドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "ブログ投稿での追跡防止Microsoft Edge改善"
[TheWebWeWant]: https://aka.ms/webwewant "必要とされる Web"

> [!NOTE]
> このページの一部は、[Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更であり、「[Creative Commons Attribution 4.0 International License][CCA4IL]」に記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developer.chrome.com/blog/new-in-devtools-80) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
