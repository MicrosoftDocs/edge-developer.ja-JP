---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: f0ac0bf7ae3b237bca45b22ed97ec16513666922
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697554"
---
# WebView2 クラス (CoreWebView2Settings クラス) 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

WebView 機能を有効、無効、または変更するプロパティを定義します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled) | AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。
[Aredefaultscriptて Enabled](#aredefaultscriptdialogsenabled) | Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。
[Aredev| Enabled](#aredevtoolsenabled) | Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。
[Arehostオブジェクトが許可されています](#arehostobjectsallowed) | Arehostobjects Allowed プロパティは、webview 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。
[IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled) | IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。
[IsScriptEnabled](#isscriptenabled) | WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。
[IsStatusBarEnabled](#isstatusbarenabled) | IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。
[IsWebMessageEnabled](#iswebmessageenabled) | IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。
[IsZoomControlEnabled](#iszoomcontrolenabled) | IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。

NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。

## Members

#### AreDefaultContextMenusEnabled 

AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。

> public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)

既定値は TRUE です。

#### Aredefaultscriptて Enabled 

Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。

> public ブール値は[Defaultscriptし enabled](#aredefaultscriptdialogsenabled)

False に設定すると、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。 代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。

#### Aredev| Enabled 

Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。

> 公開ブール型の[Devtaskenabled](#aredevtoolsenabled)

既定では true です。

#### Arehostオブジェクトが許可されています 

Arehostobjects Allowed プロパティは、webview 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。

> public bool は[hostオブジェクトを許可](#arehostobjectsallowed)

既定値は TRUE です。

#### IsBuiltInErrorPageEnabled 

IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。

> public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)

既定値は TRUE です。 無効にすると、関連するエラーが発生したときに空白のページが表示されます。

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

True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。 Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。 False に設定すると、通信は許可されません。 PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。 既定では true です。

#### IsZoomControlEnabled 

IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。

> public bool [IsZoomControlEnabled](#iszoomcontrolenabled)

既定値は TRUE です。 無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは ZoomFactor API を使って設定できます。

