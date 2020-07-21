---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0. WebView2 Win32 C++ IWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: de8c8cc2c6c6f857a2889ad167061d2834c30c02
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885794"
---
# 0.8.355-インターフェイス IWebView2ScriptDialogOpeningEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

[IWebView2WebView:: add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening)イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | ダイアログボックスを要求したページの URI。
[get_Kind](#get_kind) | JavaScript ダイアログボックスの種類。
[get_Message](#get_message) | ダイアログボックスのメッセージ。
[Accept](#accept) | このメソッドを呼び出すことで、[OK] をクリックして確認とプロンプトを表示することができます。また、このメソッドを呼び出してキャンセルを示すこともできます。
[get_DefaultText](#get_defaulttext) | JavaScript のプロンプトダイアログに渡された2番目のパラメーター。
[get_ResultText](#get_resulttext) | Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。
[put_ResultText](#put_resulttext) | ResultText プロパティを設定します。
[GetDeferral](#getdeferral) | GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。

## Members

#### get_Uri 

ダイアログボックスを要求したページの URI。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### get_Kind 

JavaScript ダイアログボックスの種類。

> パブリック HRESULT [get_Kind](#get_kind)(WEBVIEW2_SCRIPT_DIALOG_KIND * Kind)

#### get_Message 

ダイアログボックスのメッセージ。

> パブリック HRESULT [get_Message](#get_message)(LPWSTR * Message)

JavaScript から、警告、確認、プロンプトに渡される最初のパラメーターです。

#### Accept 

このメソッドを呼び出すことで、[OK] をクリックして確認とプロンプトを表示することができます。また、このメソッドを呼び出してキャンセルを示すこともできます。

> パブリック HRESULT [Accept](#accept)()

JavaScript からは、Accept 関数が呼び出された場合に true が返されることを意味します。 Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。

#### get_DefaultText 

JavaScript のプロンプトダイアログに渡された2番目のパラメーター。

> パブリック HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR * defaulttext)

これは、プロンプト JavaScript 関数の結果として使用される既定値です。

#### get_ResultText 

Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。

> パブリック HRESULT [get_ResultText](#get_resulttext)(LPWSTR * resulttext)

ダイアログ以外のダイアログでは、このメッセージは無視されます。 Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。

#### put_ResultText 

ResultText プロパティを設定します。

> パブリック HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resulttext)

#### GetDeferral 

GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。

> パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) * * 延期)

これは、後でイベントを完了するために使用できます。

