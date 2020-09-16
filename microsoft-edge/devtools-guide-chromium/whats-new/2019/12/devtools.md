---
description: ユーザー補助機能の改善、その他の言語の DevTools の使用などがあります。
title: DevTools の新機能 (Microsoft Edge 80)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8f82f46cd683433a37614bcf15745e1de9f31ffb
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015469"
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

以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。 それらを確認して、DevTools、Visual Studio コード拡張などの新機能を試してみてください。  開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。  

### DevTools のアクセシビリティの改善  

DevTools チームは、Chromium に170の変更を加え、色のコントラスト、キーボード、スクリーンリーダーに関する大きな問題に対応します。  Web を構築するすべての開発者は、DevTools を使用できるようにする必要があります。  

:::image type="complex" source="../../images/2019/12/a11y-performance-tool.msft.gif" alt-text="キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール" lightbox="../../images/2019/12/a11y-performance-tool.msft.gif":::
   キーボードナビゲーションとスクリーンリーダーの改良による DevTools の **パフォーマンス** ツール  
:::image-end:::  

すべてのユーザーが web ページにアクセスできるようにする方法について説明します。  使用を開始するには、Microsoft Edge のアクセシビリティに関する [洞察][AccessibilityInsights] と [webhint][WebhintBrowserExtension] の拡張機能をダウンロードしてください。  

スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、 [ツイート][PostTweetEdgeDevTools] でフィードバックを送信するか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックします。  

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
| Chinese (Simplified) - 中文（简体）| Chinese (Traditional) - 中文（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

に移動 `edge://flags` して、[ローカライズされた **開発者ツールを有効** にする] フラグを [ **有効**] に設定します。  また、 **開発者ツールの実験** フラグを [ **有効**にする」に設定します。  Microsoft Edge を再起動して、DevTools を開きます。  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  DevTools は、Microsoft Edge で使用する言語と一致し `edge://settings/languages` ます。  

:::image type="complex" source="../../images/2019/12/localized-devtools.msft.png" alt-text="ドイツ語の DevTools" lightbox="../../images/2019/12/localized-devtools.msft.png":::
   ドイツ語の DevTools  
:::image-end:::  

用意されているものとは異なる言語で DevTools を使う場合は、 [ツイート][PostTweetEdgeDevTools] にサインインするか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックします。  

Chromium の問題 [#941561][CR941561]  

### webhint Microsoft Edge extension  

Webhint Microsoft Edge 拡張機能を使用すると、web ページを簡単にスキャンして、開発ツールでアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどのフィードバックを得ることができます。  詳細はこちら [https://webhint.io][Webhint] をご覧ください。  

:::image type="complex" source="../../images/2019/12/webhint-browser-extension.msft.png" alt-text="Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ" lightbox="../../images/2019/12/webhint-browser-extension.msft.png":::
   Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ **ヒント** ] タブ  
:::image-end:::  

[Microsoft Edge で webhint ブラウザーの拡張機能を試してみてください][MicrosoftEdgeInsiderAddons]。  拡張機能をインストールしたら、DevTools を開いて、[ヒント] タブを選択します。 ここで、カスタマイズ可能なサイトスキャンを実行します。  詳細については、 [webhint.io][WebhintBrowserExtension] にアクセスしてください。

### 3D View (3D ビュー)  

**3D ビュー**を使って、[ドキュメントオブジェクトモデル \ (DOM \)][MDNDocumentObjectModel]または[z インデックス][MDNZIndex]スタッキングのコンテキストを移動して、web アプリケーションをデバッグします。  

:::image type="complex" source="../../images/2019/12/3dview.msft.png" alt-text="DevTools の3D ビュー" lightbox="../../images/2019/12/3dview.msft.png":::
   DevTools の**3D ビュー**  
:::image-end:::  

3D ビューにアクセスするには、 `edge://flags` **開発者ツールの実験** フラグが [ **有効**] に設定されていることを確認します。  Microsoft Edge を再起動して、DevTools を開きます。  `F1`DevTools または [**設定**] に移動し、[**実験**] セクションに移動して、[ **3d ビューを有効にする**] チェックボックスをオンにします。  を押して、 `Ctrl`  +  `Shift`  +  `P` **3d ビュー**を入力し、[ **3d ビューの表示**] を選択します。  

現在、UI を使って3D ビューに機能を追加しています。 [フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team)をお送りください。  

Chromium の問題 [#987787][CR987787]

### Visual Studio コード拡張機能  

開発者ツールチームは、テキストエディターからコードを直接使うことができる [Visual Studio コード][VisualStudioCode] の拡張機能もいくつかリリースされました。 次の拡張子を確認してください。  

#### Microsoft Edge の要素  

Visual Studio のコード拡張 [の要素][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] を追加することによって、Visual studio コード内から要素ツールを使います。  

:::image type="complex" source="../../images/2019/12/elements-for-edge.msft.png" alt-text="Microsoft Edge 拡張機能の要素を使った Visual Studio コードの要素ツール" lightbox="../../images/2019/12/elements-for-edge.msft.png":::
   Microsoft Edge 拡張機能の要素を使った Visual Studio コードの **要素** ツール  
:::image-end:::  

詳細については、「 [Microsoft Edge Visual Studio コード拡張の要素][VisualStudioCodeElementEdgeExtension]」を参照してください。  

#### Microsoft Edge 用デバッガー  

Microsoft Edge visual Studio コード拡張 [用デバッガー][VisualStudioMarketplaceDebuggerEdge] を使って、microsoft edge で実行されている JavaScript を Visual Studio コードから直接デバッグします。  

:::image type="complex" source="../../images/2019/12/vscode-debugger.msft.png" alt-text="Visual Studio コードの Microsoft Edge 拡張機能のデバッガー" lightbox="../../images/2019/12/vscode-debugger.msft.png":::
   Visual Studio コードの Microsoft Edge 拡張機能のデバッガー  
:::image-end:::  

詳細については、「 [Visual Studio コードから Microsoft Edge をデバッグする方法][VisualStudioCodeDebuggerEdgeExtension]」を参照してください。  

#### Webhint  

作成中の web ページの品質を向上させるために、 [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio のコードの拡張機能が使用されています。 `webhint` この拡張機能は、分析に基づいて、ワークスペースファイルで診断を実行して報告し `webhint` ます。  

:::image type="complex" source="../../images/2019/12/webhint-vscode-extension.msft.png" alt-text="Visual Studio コードでの tsx ファイルの分析に関する webhint Visual Studio のコード拡張" lightbox="../../images/2019/12/webhint-vscode-extension.msft.png":::
   `.tsx`Visual Studio コードでのファイルの分析に関する webhint Visual Studio コードの拡張機能  
:::image-end:::  

[Visual Studio コード web ヒントの拡張機能について、詳細はこちらをご覧][WebhintVisualStudioCodeExtension]ください。  

### Visual Studio との統合
Visual Studio 2019 バージョン16.2 以降では、Visual Studio デバッガーを使って、Microsoft Edge で実行されている JavaScript をデバッグします。  この機能を試すには、 [Visual Studio 2019 をダウンロード][MicrosoftVisualStudioDownloads]してください。  

:::image type="complex" source="../../images/2019/12/vs.msft.png" alt-text="Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio" lightbox="../../images/2019/12/vs.msft.png":::
   Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio  
:::image-end:::  

[Visual Studio から Microsoft Edge をデバッグする方法については、ブログの投稿を参照][MicrosoftVisualStudioBlogDebugJavascript]してください。  

### 防止コンソールのメッセージを追跡する  

追跡防止は、以前にアクセスしていない web サイトによって管理されることを防ぐ、Microsoft Edge の固有の機能です。  既定の追跡防止設定はバランスモードで、サードパーティのトラッカーと既知の悪意のあるトラッカーが、プライバシーと web の互換性のバランスを保つためにブロックされます。  特定のトラッカーがブロックされているときに、web ページの互換性をさらに把握できるように、トラッカーがブロックされたときに、コンソールでも警告メッセージが追加されています。  

:::image type="complex" source="../../images/2019/12/tracking-prevention.msft.png" alt-text="予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。" lightbox="../../images/2019/12/tracking-prevention.msft.png":::
   予防を追跡するときに **本体** に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。  
:::image-end:::  

[詳細については、「プライバシーと web の互換性のバランスを管理する」を参照して][TrackingPrevention]ください。  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 80 で利用可能なその他の機能を示します。  

### 本体での let と class の宣言のサポート  

**本体**で `let` 、and ステートメントの再宣言がサポートされるようになりました `class` 。  再宣言できないことは、本体を使って新しい JavaScript コードを試す web 開発者にとってよくある面倒な方法です。  

> [!WARNING]
> `let` `class` コンソールの外部にあるスクリプト、または1つの本体に含まれていないスクリプトの Redeclaring a またはステートメントは、引き続き発生 `SyntaxError` します。  

たとえば、前に示したように、ローカル変数を再宣言すると `let` 、本体からエラーが返されます。  

:::image type="complex" source="../../images/2019/12/letbefore.msft.png" alt-text="再宣言が失敗することを示す Microsoft Edge 79 のコンソール" lightbox="../../images/2019/12/letbefore.msft.png":::
   再宣言が失敗することを示す Microsoft Edge 79 の**コンソール**  
:::image-end:::  

これで、コンソールは再宣言を許可します。  

:::image type="complex" source="../../images/2019/12/letafter.msft.png" alt-text="再宣言が正常に完了したことを示す Microsoft Edge 80 のコンソール" lightbox="../../images/2019/12/letafter.msft.png":::
   再宣言が成功することを示す Microsoft Edge 80 の**コンソール**  
:::image-end:::  

Chromium の問題 [#1004193][CR1004193]  

### 優れたデバッグ  

DevTools は、 [DWARF のデバッグ標準][DwarfHome]をサポートするために開始されています。これは、コードのステップオーバーのサポートが強化され、ブレークポイントを設定して、devtools 内のソース言語でスタックトレースを解決することをサポートしています。  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
:::image type="complex" source="../../images/2019/12/wasm.msft.png" alt-text="The new DWARF-powered WebAssembly debugging" lightbox="../../images/2019/12/wasm.msft.png":::
   The new DWARF-powered WebAssembly debugging  
:::image-end:::  
-->  

### ネットワークパネルの更新  

#### [イニシエーター] タブでイニシエーターチェーンを要求する  

これで、ネットワーク要求のイニシエーターと依存関係を入れ子になったリストとして表示できるようになりました。  これは、リソースが要求された理由や、特定のリソース (たとえば、スクリプト \ など) が原因で発生したネットワークアクティビティを理解するのに役立ちます。  

:::image type="complex" source="../../images/2019/12/initiators.msft.png" alt-text="[イニシエーター] タブの要求イニシエーターチェーン" lightbox="../../images/2019/12/initiators.msft.png":::
   [ **イニシエーター** ] タブの要求イニシエーターチェーン  
:::image-end:::  

[ [ネットワーク] パネルでネットワークアクティビティを記録][DevToolsNetworkIndex]したら、リソースをクリックし、[ **イニシエーター** ] タブに移動して **要求イニシエーターチェーン**を表示します。  

*   検査された **リソース** は太字です。  上のスクリーンショットは、 `ai.2.min.js` 検査されたリソースを示しています。  
*   検査されたリソースの上にあるリソースが **イニシエーター**になります。  上のスクリーンショットは、 `https://www.microsoftedgeinsider.com` のイニシエーターを示して `ai.2.min.js` います。  つまり、という `https://www.microsoftedgeinsider.com` ネットワーク要求が発生しました `ai.2.min.js` 。  
*   検査されたリソースの下にあるリソースは、 **依存関係**です。  上のスクリーンショットは、 `https://dc.services.visualstudio.com/v2/track` の依存関係を示してい `ai.2.min.js` ます。  つまり、という `ai.2.min.js` ネットワーク要求が発生しました `https://dc.services.visualstudio.com/v2/track` 。  

> [!NOTE]
> また、イニシエーターと依存関係の情報にアクセスするには、ネットワークリソースを保持するか、 `Shift` マウスでポイントします。  「 [イニシエーターと依存関係の表示」を][DevToolsNetworkReferenceViewInitiatorsDependencies]ご覧ください。  

Chromium の問題 [#842488][CR842488]  

#### 概要で選択されたネットワーク要求を強調表示する  

ネットワークリソースを調べるためにクリックした後、[ネットワーク] パネル **では、** そのリソースの周囲に青色の境界線が表示されます。  これにより、ネットワーク要求が予期したより前または後に発生しているかどうかを検出することができます。  

:::image type="complex" source="../../images/2019/12/overview.msft.png" alt-text="調査したリソースを強調表示した [概要] ウィンドウ" lightbox="../../images/2019/12/overview.msft.png":::
   調査したリソースを強調表示した [ **概要** ] ウィンドウ  
:::image-end:::  

Chromium の問題 [#988253][CR988253]  

#### [ネットワーク] パネルの [URL] と [path] 列  

[**ネットワーク**] パネルの [新しい**パス**] 列と [ **url** ] 列を使用して、各ネットワークリソースの絶対パスまたは完全な url を確認します。  

:::image type="complex" source="../../images/2019/12/columns.msft.png" alt-text="ネットワークパネルの新しいパスと URL 列" lightbox="../../images/2019/12/columns.msft.png":::
   **ネットワーク**パネルの新しいパスと URL 列  
:::image-end:::  

**ウォーターフォール**テーブルのヘッダーを右クリックし、[**パス**] または [ **URL** ] を選択して新しい列を表示します。  

Chromium の問題 [#993366][CR993366]  

#### 更新されたユーザーエージェント文字列  

DevTools は、[ **ネットワークの条件** ] タブを使用したカスタムユーザーエージェント文字列の設定をサポートしています。 ユーザーエージェントの文字列は、 `User-Agent` ネットワークリソースに接続される HTTP ヘッダーと、の値に影響し `navigator.userAgent` ます。  

定義済みのユーザーエージェント文字列は、最新のブラウザーバージョンを反映するように更新されています。  

:::image type="complex" source="../../images/2019/12/useragent.msft.png" alt-text="[ネットワークの条件] タブの [ユーザーエージェント] メニュー" lightbox="../../images/2019/12/useragent.msft.png":::
   [ **ネットワークの条件** ] タブの [ユーザーエージェント] メニュー  
:::image-end:::  

ネットワークの **状態**にアクセスするには、 [コマンドメニューを開い][DevToolsCommandMenuIndex] てコマンドを実行し `Show Network Conditions` ます。  

> [!NOTE]
> [デバイスモードでは、ユーザーエージェント文字列を設定][DevToolsDeviceModeIndex]することもできます。  

Chromium の問題 [#1029031][CR1029031]  

### 監査パネルの更新  

#### 新しい構成 UI  

構成 UI には、応答性の高い新しいデザインがあり、調整構成オプションが簡素化されています。  調整 UI の変更について詳しくは、「 [監査パネルの調整][GitHubGoogleChromeDevToolsAuditsPanelThrottling] 」をご覧ください。  

:::image type="complex" source="../../images/2019/12/start.msft.png" alt-text="新しい構成 UI" lightbox="../../images/2019/12/start.msft.png":::
   新しい構成 UI  
:::image-end:::  

### [カバレッジ] タブの更新  

#### 関数単位またはブロック単位のカバレッジモード  

[ [カバレッジ] タブ][DevToolsCoverageIndex] には、1つの **関数** または **ブロック**ごとにコードカバレッジデータを収集するかどうかを指定できる新しいドロップダウンメニューがあります。  **ブロック範囲ごと** に、さらに詳しい情報を収集することができます。  DevTools では、既定で **機能ごとに機能** を使用します。  

> [!CAUTION]
> **各機能**と**ブロック**モードのどちらを使用するかによって、HTML ファイルに大きなコードカバレッジの違いが表示されることがあります。  **関数単位**モードを使う場合、HTML ファイル内のインラインスクリプトは関数として扱われます。  スクリプトがすべて実行された場合は、DevTools はスクリプト全体を使用コードとしてマークします。  スクリプトがまったく実行されない場合のみ、DevTools はスクリプトを未使用コードとしてマークします。  

:::image type="complex" source="../../images/2019/12/modes.msft.png" alt-text="[カバレッジモード] ドロップダウンメニュー" lightbox="../../images/2019/12/modes.msft.png":::
   [カバレッジモード] ドロップダウンメニュー  
:::image-end:::  

#### ページの再読み込みによってカバーが開始されるようになりました  

カバレッジデータの信頼性が低いため、ページの再読み込みを行わずにコードカバレッジを切り替えることはできません。  たとえば、ランタイムが長時間前であり、V8 ガベージコレクターによってクリーンアップされている場合、関数は未使用として報告されることがあります。  

Chromium の問題 [#1004203][CR1004203]  

## Microsoft Edge preview チャネルをダウンロードする  

Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->

<!-- image links -->  

<!--[../../images/2019/12/wasm.msft.png]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevToolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブを使用して、使用されていない JavaScript と CSS コードを見つけます。Microsoft ドキュメント"  
[DevToolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイルビューポートをシミュレートする Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする |Microsoft ドキュメント"  
[DevToolsNetworkIndex]: /microsoft-edge/devtools-guide-chromium/network/index "Microsoft Edge DevTools でネットワークアクティビティを検査する |Microsoft ドキュメント"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/network/reference#view-initiators-and-dependencies "イニシエーターと依存関係の表示-ネットワーク分析リファレンス |Microsoft ドキュメント"  
[DevGuideEdgeHtmlWhatsNew]: /microsoft-edge/dev-guide/whats-new "EdgeHTML の新機能 |Microsoft ドキュメント"  
[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge Visual Studio コード拡張機能のデバッガー |Microsoft ドキュメント"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge Visual Studio コード拡張の要素 |Microsoft ドキュメント"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[CR842488]: https://crbug.com/842488 "[ヘッダー] タブに [イニシエーター] フィールドを追加します。Chromium のバグ"  
[CR988253]: https://crbug.com/988253 "バグ DevTools-ネットワーク要求とタイムライングラフの間に関連性がありません |Chromium のバグ"  
[CR993366]: https://crbug.com/993366 "ネットワークパネル要求リストで URL のパス部分を表示してください |Chromium のバグ"  
[CR1004193]: https://crbug.com/1004193 "V8 の REPL モード |Chromium のバグ"  
[CR1004203]: https://crbug.com/1004203 "コードカバレッジをすばらしいものにする |Chromium のバグ"  
[CR1029031]: https://crbug.com/1029031 "UA 文字列が古くなります。 |Chromium のバグ" 
[CR963183]: https://crbug.com/963183 "DevTools は WCAG に準拠していません |Chromium のバグ"
[CR941561]: https://crbug.com/941561 "DevTools のローカライズ可能性 |Chromium のバグ"
[CR987787]: https://crbug.com/987787 "Dom 3D ビュー |Chromium のバグ"

[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティの分析"  

[DwarfHome]: https://dwarfstd.org "Dwarf ホーム"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools の監査パネルの調整-GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題-Microsoft のドキュメント/エッジ-開発者"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider のアドオン"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "Visual Studio からの Microsoft Edge で JavaScript をデバッグする |Visual Studio ブログ"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Visual Studio 2019 for Windows & Mac をダウンロードする"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメントオブジェクトモデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z インデックス |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio コード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 用デバッガー-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium) の要素: Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "web ヒント"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint ブラウザ拡張 |webhint に関するドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio のコード拡張 |webhint に関するドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿の追跡防止の向上"
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2019/12/devtools/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
