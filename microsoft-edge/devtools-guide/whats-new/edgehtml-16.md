---
description: Windows 10 での Microsoft Edge DevTools に追加された機能 (EdgeHTML 16)
title: EdgeHTML 16 の DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、edgehtml 16
ms.custom: seodec18
ms.openlocfilehash: 78ede81e022cc8f0f623ecd33fd2303314ec9cb0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569639"
---
# Windows 10 で作成された開発者向けツールの更新プログラム (EdgeHTML 16)

このリリースでは、堅牢性とパフォーマンスを向上させるために、主要な DevTools リファクタリングの取り組みを始めました。また、今すぐ使用できる新しい機能も追加されました。 

ここでは、 [Windows 10 の秋の更新プログラム](/windows/uwp/whats-new/windows-10-build-16299)([EdgeHTML 16](https://aka.ms/devguide_edgehtml_16)) に同梱されている Microsoft Edge の devtools 機能について説明します。

## 祖先イベントリスナー 

[**イベント**] ウィンドウでは、現在選択されている要素 (要素パネル内) の任意の先祖に登録されているイベントリスナーを表示するオプションが追加され、さら**に要素自体**にも表示されます。 さらに、イベントリスナーの表示を*イベント*または*要素*でグループ化できるようになりました。 

![イベントリスナーの検査ウィンドウ](../media/elements_ancestor_events.png)

## DOM 変異のブレークポイント

選択した要素ノードが変更されるたびに、DOM 変異ブレークポイントを設定してデバッガーに割り込むことができるようになりました。 [**要素**] パネルで、[DOM ツリー] ビューの任意の要素を rt でクリックし、次のうち1つ以上を選択します。

 - ノードの区切りが削除されました
 - サブツリーの区切りが変更されました
 - 変更された属性の区切り

[**要素**] または [**デバッガー** ] パネルの [ **DOM ブレークポイント**] ウィンドウから変異させるブレークポイントを管理できます。

![DOM のブレークポイントウィンドウ](../media/elements_dom_breakpoints.png)

## CSS のルールサポート

CSS の "at" (@) ルールは、[**スタイル**] ウィンドウで、アニメーション `@keyframes` ルール (現在は読み取り専用)、 `@supports` 機能クエリ、およびクエリなど、さまざまな css ルールの宣言で表され `@media` ます。

![DevTools のスタイルウィンドウからの CSS のルール検査](../media/elements_at_rules.png)

## CSS フォントウィンドウ

CSS `@font-face` ルールには、フォントの読み込み元 (*ローカル*または*ネットワーク*) と使用されている文字数を表示する専用の**フォント**ウィンドウが用意されています。 フォントがネットワークから読み込まれている場合、DevTools には、そのフォントをエイリアスとフォントの種類と共にインポートしたルールが表示されます。

![CSS フォント情報](../media/elements_fonts.png)

## CSS 擬似要素のサポート

[**スタイル**] ウィンドウは、独自の見出しの下にある擬似要素をグループ化し、コンテンツが取り消し線で表示されなくなります。

**変更前:**
<br>
![生成されたコンテンツは以前に終了しました](../media/gc_before.png)

**変更後:**
<br>
![生成されたコンテンツが取り消し線で表示されなくなりました](../media/gc_after.png)

## コンソールの機能強化

**コンソール**パネルには、操作性を向上させるための UX の見直し、より速く、より高度な Intellisense エクスペリエンスが用意されています。

**前に:** 
![前のコンソール](../media/console_old.png)

**後:** 
![新しいコンソール](../media/console_new.png)

また、次の改善点も追加されました。

 -  `Shift + Enter`コマンドを実行する前に、コマンドに行を追加するために使用 `Enter` します。 (以前のところ、*複数行モードまたは単一行モード*のトグルボタンに切り替えました。)

 - 次の新しい Api がサポートされています。
    - [**console. table (***object***)**](../console/console-api.md#organizing-log-output)メソッド
    - [**Geteventlisteners (***object***)**](../console/command-line.md#event-listeners)コマンド
    - [**キー (***オブジェクト***)**](../console/command-line.md#object-inspection)コマンド
    - [**値 (***オブジェクト***)**](../console/command-line.md#object-inspection)コマンド
    - [**$x (***xpath 式***)**](../console/command-line.md#dom-selectors)セレクター

 - [**% C ()**](../console/console-api.md#logging-custom-messages)の書式設定パラメーターがサポートされるようになりました

## デバッグ機能の改善

[PWA サービスワーカーとキャッシュ](#progressive-web-app-debugging)をデバッグするための新機能のスイートに加えて、次の機能が追加されました。

### 共有リソースの統合デバッグ

CDN から読み込まれたファイルなどのリソースがコードを通じて複数回参照されている場合でも、DevTools では、そのファイルに対して1つのデバッグインスタンスが提供されます。これを使うと、ファイルが参照されている場所に関係なく、一般的なブレークポイントを設定することができます。 (以前のスクリプト参照はそれぞれ、固有のリソースと見なされ、個別のブレークポイントのセットにマップされます)。

### *編集時アイドル*状態のライブ編集 JavaScript

デバッグセッション中に JavaScript live を編集できるようになりました。 この機能は、[以前](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97)の (*Windows 10 experimentally Update*) リリースに含まれている (フラグの背後にあります) ことができました。これは永続的な機能です。 「**デバッガ**」パネルで任意のスクリプトファイルを選択して、「編集」をクリックしてから「**保存**」 (または `Ctrl+S` ) をクリックして、次にそのコードセクションの実行時に変更をテストします。 

![デバッガーを使って、編集スクリプトを実行し、変更内容を比較することができます。](../media/debugger_edit_buttons.png) 

[**元の文書と比較**する] ボタンをクリックして、変更した内容の相違点を表示します。

![デバッガーでの編集されたコードの差分表示](../media/debugger_edit_code.png) 

以下の制約に注意してください。

- スクリプト編集は、外部の *.js*ファイルでのみ機能します (.html 内に埋め込まれているわけではありません `<script>` ) *。*
- 編集はメモリに保存され、ドキュメントの再読み込み時にフラッシュされるため、たとえば、ハンドラー内で編集を実行することはできません。 `DOMContentLoaded`
- 現時点では、DevTools からディスクへの編集を保存する方法はありません ([**名前を付けて保存**] オプションなど)。

## ショートカット

他の主要なブラウザーと同じように、最後に表示されたパネル ( `Ctrl+Shift+I` ) またはコンソール () に対して、DevTools を起動できるようになりました `Ctrl+Shift+J` 。

## プログレッシブ Web アプリのデバッグ

Microsoft Edge および DevTools で、[**サービスワーカーを有効にする**] オプションを選択し、microsoft edge を再起動して、プログレッシブ Web アプリ (pwas) の実験的なサポートをテストし `about:flags` ます。 サイトがサービスの担当**者**や**キャッシュ**API を使っている場合は、web ストレージと cookie の検査機能と同様に、各原点の**デバッガー**パネルにエントリが設定されます。

特定のサービスワーカーエントリをクリックすると、サービスワーカーの**概要**が開きます。ここでは、指定したスコープのサービスワーカー登録を管理し、テストプッシュ通知を強制します。 **Stop** / 個々のサービスワーカーの**開始**を停止して、個別のデバッガーウィンドウから**調べる**こともできます。

![サービスワーカーの概要ウィンドウ](../media/debugger_sw_overview.png)

サービスワーカーのデバッグについては、次の点に注意してください。

 - サービスワーカーをデバッグすると、複数のタブ間でサービスワーカーを共有できるため、ページのツールとは別に、DevTools の新しいインスタンスが起動されます。 
 - サービスワーカーがバックグラウンドで実行されていて、アプリのフロントエンドを直接制御していない場合、サービスワーカーデバッガーから[要素](../elements.md)と[エミュレーション](../emulation.md)パネルは存在しません。
 - 現在、サービスワーカーのネットワークトラフィックは、そのワーカー用の DevTools デバッグインスタンスからのみ報告され、ページ自体の中央インスタンスからは報告されません。

特定のキャッシュエントリをクリックする**と、キャッシュマネージャーが**開きます。ここでは、キャッシュエントリ (*要求*および*応答*のキー/値ペア) を検査し、必要に応じて削除することができます。