---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2Settings。
ms.openlocfilehash: 87b78956c29dac74bd023556a8c495222d248e9f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012245"
---
# WebView2 クラス (CoreWebView2Settings クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

WebView 機能を有効、無効、または変更するプロパティを定義します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled) | AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが WebView でユーザーに表示されないようにするために使われます。
[Aredefaultscriptて Enabled](#aredefaultscriptdialogsenabled) | Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。
[Aredev| Enabled](#aredevtoolsenabled) | Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。
[Arehostオブジェクトが許可されています](#arehostobjectsallowed) | Arehostobjects Allowed プロパティは、WebView 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。
[IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled) | IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。
[IsScriptEnabled](#isscriptenabled) | WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。
[IsStatusBarEnabled](#isstatusbarenabled) | IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。
[IsWebMessageEnabled](#iswebmessageenabled) | IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。
[IsZoomControlEnabled](#iszoomcontrolenabled) | IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。

NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。

## Members

#### AreDefaultContextMenusEnabled 

AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが WebView でユーザーに表示されないようにするために使われます。

> public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)

既定では true です。

#### Aredefaultscriptて Enabled 

Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。

> public ブール値は [Defaultscriptし enabled](#aredefaultscriptdialogsenabled)

False に設定すると、WebView には、既定の JavaScript ダイアログボックスは表示されません (具体的には、JavaScript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。 True に設定されている場合は、Scriptui> 左中イベントをサブスクライブして、ダイアログのすべての情報が含まれ、ホストアプリが独自のカスタム UI を表示できるようにすることもできます。 既定では true です。

#### Aredev| Enabled 

Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。

> 公開ブール型の [Devtaskenabled](#aredevtoolsenabled)

既定では true です。

#### Arehostオブジェクトが許可されています 

Arehostobjects Allowed プロパティは、WebView 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。

> public bool は [hostオブジェクトを許可](#arehostobjectsallowed)

既定では true です。

#### IsBuiltInErrorPageEnabled 

IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。

> public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)

既定では true です。 無効にすると、関連するエラーが発生したときに空白のページが表示されます。

#### IsScriptEnabled 

WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。

> public bool [Isscriptenabled](#isscriptenabled)

これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。 既定では true です。

#### IsStatusBarEnabled 

IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。

> public bool [IsStatusBarEnabled](#isstatusbarenabled)

通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。 既定では true です。

#### IsWebMessageEnabled 

IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。

> public bool [IsWebMessageEnabled](#iswebmessageenabled)

True に設定されている場合、ホストから WebView のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。 WebView の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と WebMessageReceived イベントによって許可されます (詳しくは WebMessageReceived のドキュメントを参照してください)。 False に設定すると、通信は許可されません。 PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。 既定では true です。

#### IsZoomControlEnabled 

IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。

> public bool [IsZoomControlEnabled](#iszoomcontrolenabled)

既定では true です。 無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは ZoomFactor API を使って設定できます。

