---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ScriptDialogOpeningEventArgs
ms.openlocfilehash: 070e7799111113ab8b4f883df85e505894677a31
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879045"
---
# インターフェイス ICoreWebView2ScriptDialogOpeningEventArgs 

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

Scriptな開始イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Accept](#accept) | このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。
[get_DefaultText](#get_defaulttext) | JavaScript のプロンプトダイアログに渡された2番目のパラメーター。
[get_Kind](#get_kind) | JavaScript ダイアログボックスの種類。
[get_Message](#get_message) | ダイアログボックスのメッセージ。
[get_ResultText](#get_resulttext) | Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。
[get_Uri](#get_uri) | ダイアログボックスを要求したページの URI。
[GetDeferral](#getdeferral) | GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。
[put_ResultText](#put_resulttext) | ResultText プロパティを設定します。

## Members

#### Accept 

このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。

> パブリック HRESULT [Accept](#accept)()

これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。 Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。

#### get_DefaultText 

JavaScript のプロンプトダイアログに渡された2番目のパラメーター。

> パブリック HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR * defaulttext)

これは、プロンプト JavaScript 関数の結果として使用される既定値です。

#### get_Kind 

JavaScript ダイアログボックスの種類。

> パブリック HRESULT [get_Kind](#get_kind)(COREWEBVIEW2_SCRIPT_DIALOG_KIND * Kind)

[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。

#### get_Message 

ダイアログボックスのメッセージ。

> パブリック HRESULT [get_Message](#get_message)(LPWSTR * Message)

JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。

#### get_ResultText 

Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。

> パブリック HRESULT [get_ResultText](#get_resulttext)(LPWSTR * resulttext)

ダイアログ以外のダイアログでは、このメッセージは無視されます。 Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。

#### get_Uri 

ダイアログボックスを要求したページの URI。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### GetDeferral 

GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。

> パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) * * 延期)

これは、後でイベントを完了するために使用できます。

#### put_ResultText 

ResultText プロパティを設定します。

> パブリック HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resulttext)

