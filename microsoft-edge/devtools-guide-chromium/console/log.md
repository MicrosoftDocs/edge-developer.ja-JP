---
description: コンソールにメッセージを記録する方法について説明します。
title: コンソールでのメッセージのログ記録の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2f91f1847bf5469e8106edc21553172fc06db9ee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231112"
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

# コンソールでのメッセージのログ記録の開始  

この対話型のチュートリアルでは、Microsoft Edge DevTools コンソールでメッセージをログに記録して [フィルター処理する方法を示][MicrosoftEdgeDevTools] します。  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="コンソール内のメッセージ" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   コンソール内の **メッセージ**  
:::image-end:::  

このチュートリアルは、順番に完了することを目的とします。  JavaScript を使用してページに対話機能を追加する方法など、Web 開発の基本を理解している必要があります。  

## デモと DevTools をセットアップする  

このチュートリアルは、デモを開いて、すべてのワークフローを自分で試しに行くことができる設計です。  物理的に作業を行う場合は、後でワークフローを思い出す可能性が高い。  

1.  `Control`\(Windows, Linux\) または \(macOS\) を保持し、[コンソール ログの例] を選択して新しい `Command` タブで開きます。 ****  
    
    [コンソール ログの例][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  デモにフォーカスを移動し `Control` + `Shift` + `J` 、\(Windows、Linux\) または `Command` + `Option` + `J` \(macOS\) を選択して DevTools を開きます。  既定では、DevTools はデモの右側に開きます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="デモの右側に DevTools が開きます" lightbox="../media/console-example-devtools-right-console.msft.png":::
             デモの右側に DevTools が開きます  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [DevTools をウィンドウの下部にドッキングします][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="デモの下部にドッキングされた DevTools" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             デモの下部にドッキングされた DevTools  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > [DevTools を別のウィンドウにドッキング解除します][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="別ウィンドウのブラウザー" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             別ウィンドウのブラウザー  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [DevTools を別のウィンドウにドッキング解除します][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="DevTools が別のウィンドウでドッキング解除されている" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             DevTools が別のウィンドウでドッキング解除されている  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## JavaScript からログに記録されたメッセージを表示する  

コンソールに表示されるほとんどのメッセージは **、ページ** の JavaScript を作成した Web 開発者からのメッセージです。  このセクションの目的は、コンソールで確認する可能性が高いさまざまなメッセージの種類を紹介し、それぞれの**** メッセージの種類を自分の JavaScript から自分で記録する方法を説明します。  

1.  デモの **[ログ情報]** ボタンを選択します。  `Hello, Console!` がコンソールに記録されます。
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="[ログ情報] を選択した後のコンソール" lightbox="../media/console-log-info.msft.png":::
       [ **ログ情報** ] を選択した **後のコンソール**  
    :::image-end:::  
    
1.  コンソールのメッセージ `Hello, Console!` の横にある ** [log.js:2 ] を選択します**。  [ソース] パネルが開き、メッセージがコンソールに記録される原因となるコード行が強調表示されます。  メッセージは、ページの JavaScript が実行された際にログに記録されます `console.log('Hello, Console!')` 。
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="DevTools は、次の操作を選択した後、[ソース] log.js開きます。" lightbox="../media/console-sources-logjs.msft.png":::
       DevTools は、選択 **した後に [ソース** ] パネルを開きます。 `log.js:2`  
    :::image-end:::  
    
1.  次のワークフローを **使用して** 、コンソールに戻る。  
    
    *   [コンソール] **タブを選択** します。  
    *   コンソール `Control` + `[` パネルにフォーカスが置かれるまで `Command` + `[` \(Windows,Linux\) または \(macOS\) を選択します。 ****  
    *   [コマンド メニューを開き、「][DevToolsCommandMenu]コンソール パネルの表示」コマンドを入力して、次 `Console` に選択**** します `Enter` 。  
    
1.  デモで **[警告のログ** ] ボタンを選択します。  `Abandon Hope All Ye Who Enter` コンソールに記録 **されます**。  このような形式のメッセージは警告です。  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="[警告のログ] を選択した後のコンソール" lightbox="../media/console-log-warning.msft.png":::
       [ **警告のログ** ] を選択 **した後のコンソール**  
    :::image-end:::  
    
    > [!TIP]
    > メッセージが特定の方法でログに記録される原因となったコードを表示する場合は、スクリプト `log.js:12` \(\など) を選択して、メッセージが書式設定される原因となったコードを表示します。  

1.  Choose the **Expand** \( ![ Expand ][ImageExpandIcon] \) icon in front of `Abandon Hope All Ye Who Enter` .  DevTools は、呼 [び出しに至る][WikiStackTrace] スタック トレースを示します。  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="スタック トレース" lightbox="../media/console-log-warning-expanded.msft.png":::
       スタック トレース  
    :::image-end:::  
    
    スタック トレースは、名前付きの関数が実行され、その関数が実行 `logWarning` されたことを示しています `quoteDante` 。  つまり、最初に発生した要求はスタック トレースの一番下になります。  スタック トレースは、実行中にいつでも記録できます `console.trace()` 。  

1.  [ログ **エラー] を選択します**。  次のエラー メッセージがログに記録されます。 `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="エラー メッセージ" lightbox="../media/console-log-error.msft.png":::
       エラー メッセージ  
    :::image-end:::  
    
1.  [ログ **テーブル] を選択します**。  アーティストに関するテーブルがコンソールに記録 **されます**。  
    
    > [!NOTE]
    > 列 `birthday` には、1 行分のみ入力されます。  その理由を判断するには、コードを確認します。
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="コンソール内のテーブル" lightbox="../media/console-log-table.msft.png":::
       コンソール内の **テーブル**  
    :::image-end:::  
    
1.  [ログ **グループ] を選択します**。  4 つの犯罪に対する暴力的な部下の名前がラベルの下にグループ化 `Adolescent Irradiated Espionage Tortoises` されます。  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="コンソール内のメッセージのグループ" lightbox="../media/console-log-group.msft.png":::
       コンソール内のメッセージの **グループ**  
    :::image-end:::  
    
1.  Choose **Log Custom**.  赤い枠線と青い背景のメッセージがコンソールに記録されます。  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="コンソール内のカスタム書式設定を含むメッセージ" lightbox="../media/console-log-custom.msft.png":::
       コンソール内のカスタム書式設定を含む **メッセージ**  
    :::image-end:::  
    
ここでの主な考え方は、JavaScript からコンソールにメッセージを記録する場合は、メソッドの 1 つを `console` 使用するという考え方です。  各メソッドは、メッセージの書式を異なります。  

このセクションで説明したメソッドよりも多くのメソッドがあります。  このチュートリアルでは、残りのメソッドを参照する方法を示します。  

## ブラウザーによってログに記録されたメッセージを表示する  

ブラウザーもコンソールにメッセージをログに記録します。  これは通常、ページに問題がある場合に発生します。  

1.  Choose **Cause 404**.  ページの JavaScript が存在しないファイルをフェッチしようとしたため、ブラウザーはネットワーク エラーの HTTP 状態コード `404` をログに記録します。  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="コンソールの 404 エラー" lightbox="../media/console-cause-404.msft.png":::
       コンソール `404` の **エラー**  
    :::image-end:::  
    
1.  Choose **Cause Error**.  JavaScript が存在しない DOM ノードを更新しようとしているため、ブラウザーはキャッチされていないログ `TypeError` を記録します。  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="コンソールの TypeError" lightbox="../media/console-cause-error.msft.png":::
       コンソール `TypeError` 内の**** A  
    :::image-end:::  
    
1.  [ログ **レベル] ドロップダウンを** 選択し、無効になっている場合は [ **詳細** ] オプションを有効にします。  フィルター処理の詳細については、次のセクションを参照してください。  これを行って、ログに記録する次のメッセージが表示される必要があります。  
    
    > [!NOTE]
    > [既定のレベル] ドロップダウンが無効になっている場合は、コンソール サイドバーを閉じる **必要があります** 。  コンソール サイドバーの詳細については、以下のメッセージ ソースで **フィルター** 処理します。
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="詳細ログ レベルの有効化" lightbox="../media/console-cause-error-log-levels.msft.png":::
       詳細ログ レベルの有効化  
    :::image-end:::  
    
1.  Choose **Cause Violation**.  ページが数秒応答しなくなると、ブラウザーはメッセージをコンソール `[Violation] 'click' handler took 3000ms` に記録します。  正確な期間は異なる場合があります。  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="コンソールでの違反" lightbox="../media/console-cause-violation.msft.png":::
       コンソールでの違反****  
    :::image-end:::  
    
## メッセージをフィルター処理する  

一部の Web ページでは、コンソールに **メッセージ** が表示されます。  DevTools には、該当するタスクに関係ないメッセージをフィルター処理するさまざまな方法が提供されています。  

### ログ レベルでフィルター処理する  

各 `console` メソッドには、次の重大度レベルが `Verbose` 割 `Info` り当 `Warning` てられます `Error` 。  たとえば、 `console.log()` レベルレベルの `Info` メッセージはレベルレベルのメッセージ `console.error()` `Error` ですが、レベルの高いメッセージです。  

1.  [ログ レベル **] ドロップダウンを選択し** 、[エラー] を **無効にします**。  レベルの横にチェック マークが表示されなくなった場合、レベルは無効になります。  レベル `Error` のメッセージは表示されなくなります。  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="コンソールでエラー レベルのメッセージを無効にする" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       コンソールでエラー レベルのメッセージを無効 **にする**  
    :::image-end:::  
    
1.  [ログ レベル **] ドロップダウンを** 再び選択し、エラーを再度 **有効にしてください**。  レベル `Error` のメッセージが再び表示されます。  

### テキストでフィルター処理  

正確な文字列を含むメッセージのみを表示する場合は、その文字列を [フィルター] テキスト ボックス **に** 入力します。  

1.  `Dave` を **フィルター処理** テキスト ボックスに入力します。  文字列を含めないメッセージはすべて `Dave` 非表示になります。  ラベルを確認 `Adolescent Irradiated Espionage Tortoises` する場合があります。  これはバグです。  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="Dave を含めないメッセージをフィルター処理する" lightbox="../media/console-all-messages-text-filter.msft.png":::
       含めないメッセージをフィルター処理する `Dave`  
    :::image-end:::  
    
1.  [ `Dave` フィルター] **テキスト ボックスから** 削除します。  すべてのメッセージが再び表示されます。  

### 正規表現によるフィルター処理  

特定の文字列ではなく、テキストのパターンを含むすべてのメッセージを表示する場合は、正規表現を [使用します][MDNRegularExpressions]。  

1.  `/^[AH]/` を **フィルター処理** テキスト ボックスに入力します。  このパターンを [RegExr に入力][|::ref1::|Main] して、実行内容を説明します。  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="パターンに一致しないメッセージをフィルター処理する" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       パターンに一致しないメッセージをフィルター処理する `/^[AH]/`  
    :::image-end:::  
    
1.  [ `/^[AH]/` フィルター] **テキスト ボックスから** 削除します。  すべてのメッセージが再び表示されます。  

### メッセージ ソースでフィルター処理する  

When you want to only view the messages that came from a certain URL, use the **Sidebar**.  

1.  Choose **Show Console Sidebar** \( Show Console Sidebar ![ ][ImageShowConsoleSidebarIcon] \).  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="サイドバー" lightbox="../media/console-sidebar-all-messages.msft.png":::
       サイドバー  
    :::image-end:::  
    
1.  Choose the **Expand** \( ![ Expand ][ImageExpandIcon] \) icon next to the number of messages.  次の図では、メッセージの数は **13**メッセージとして示されています。  サイドバー **には** 、メッセージのログ記録の原因となる URL の一覧が表示されます。  たとえば `log.js` 、11 件のメッセージが発生したとします。  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="サイドバーでメッセージのソースを表示する" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       サイドバーでメッセージのソースを表示する  
    :::image-end:::  
    
### ユーザー メッセージでフィルター処理する  

以前は、[ログ情報] **を選択**すると、コンソールにメッセージを記録するために名前 `console.log('Hello, Console!')` が付けられたスクリプトです。  このような JavaScript からログに記録されるメッセージは、名前付き **ユーザー メッセージです**。  これに対し、原因 **404 を**選択すると、要求されたリソースが見つからないことを示すレベルのメッセージがブラウザー `Error` に記録されます。  ブラウザー メッセージと見なされる、のような **メッセージ**です。  サイドバーを **使用して** ブラウザー メッセージをフィルター処理し、ユーザー メッセージのみを表示します。  

1.  Choose **9 User Messages**.  ブラウザー メッセージは非表示になります。  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="ブラウザー メッセージのフィルター処理" lightbox="../media/console-sidebar-user-messages.msft.png":::
       ブラウザー メッセージのフィルター処理  
    :::image-end:::  
    
1.  **[13 メッセージ] を選択**して、すべてのメッセージを再び表示します。  

## 他のパネルと一緒にコンソールを使用する  

スタイルを編集しているが、コンソール ログで何かすばやく確認する必要がある場合は、どうなるでしょうか。  ドロワーを使用します。  

1.  [要素] **タブを選択** します。  
1.  `Escape` を選択します。  ドロ **ワーの [** コンソール] **タブが開** きます。  このチュートリアルでは、コンソール パネルのすべての機能を使用しています。  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text="ドロワーの [コンソール] タブ" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         ドロ **ワーの** [コンソール] **タブ**  
    :::image-end:::  
    
<!--## Next steps  -->

<!--
*   Navigate to [Console Reference][DevToolsConsoleApi] to explore more features and workflows related to the Console UI.
*   Navigate to [Console API Reference][DevToolsConsoleReference] to learn more about all of the `console` methods that were demonstrated in [View messages logged from JavaScript(#view-messages-logged-from-javascript) and explore the other `console` methods that were not covered in this tutorial.  
*   Navigate to [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \(Chromium\) 開発者ツール |Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニューを使ってコマンドを実行する |Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更 | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md "コンソール リファレンス |Microsoft Docs"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "メッセージのログ記録の概要 |Glitch"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正規表現 |MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "スタック トレース - Wikipedia"  
> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/log) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
