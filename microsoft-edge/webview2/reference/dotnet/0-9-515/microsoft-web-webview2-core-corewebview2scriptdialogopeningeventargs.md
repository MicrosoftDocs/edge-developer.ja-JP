---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 1359e9472455acf2949cc329de4280ad970a3b68
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697309"
---
# WebView2 クラス (CoreWebView2ScriptDialogOpeningEventArgs クラス) 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

Scriptな開始イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[DefaultText](#defaulttext) | JavaScript のプロンプトダイアログに渡された2番目のパラメーター。
[種類](#kind) | JavaScript ダイアログボックスの種類。
[メッセージ](#message) | ダイアログボックスのメッセージ。
[ResultText](#resulttext) | Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。
[URI](#uri) | ダイアログボックスを要求したページの URI。
[Accept](#accept) | このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。
[GetDeferral](#getdeferral) | GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。

## Members

#### DefaultText 

JavaScript のプロンプトダイアログに渡された2番目のパラメーター。

> パブリック文字列の[Defaulttext](#defaulttext)

これは、プロンプト JavaScript 関数の結果として使用される既定値です。

#### 種類 

JavaScript ダイアログボックスの種類。

> パブリック CoreWebView2ScriptDialogKind [Kind](#kind)

[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。

#### メッセージ 

ダイアログボックスのメッセージ。

> パブリック文字列[メッセージ](#message)

JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。

#### ResultText 

Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。

> パブリック文字列の[Resulttext](#resulttext)

ダイアログ以外のダイアログでは、このメッセージは無視されます。 Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。

#### URI 

ダイアログボックスを要求したページの URI。

> パブリック文字列の[Uri](#uri)

#### Accept 

このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。

> パブリック void [Accept](#accept)()

これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。 Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。

#### GetDeferral 

GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。

> パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()

これは、後でイベントを完了するために使用できます。

