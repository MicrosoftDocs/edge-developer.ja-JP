---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 8ed1a10a65a07fc359deea18b8aadd4df3a7b055
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654595"
---
# インターフェイス ICoreWebView2ScriptDialogOpeningEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

Scriptな開始イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | ダイアログボックスを要求したページの URI。
[get_Kind](#get_kind) | JavaScript ダイアログボックスの種類。
[get_Message](#get_message) | ダイアログボックスのメッセージ。
[Accept](#accept) | このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。
[get_DefaultText](#get_defaulttext) | JavaScript のプロンプトダイアログに渡された2番目のパラメーター。
[get_ResultText](#get_resulttext) | Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。
[put_ResultText](#put_resulttext) | ResultText プロパティを設定します。
[GetDeferral](#getdeferral) | GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。

## Members

#### get_Uri 

ダイアログボックスを要求したページの URI。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### get_Kind 

JavaScript ダイアログボックスの種類。

> パブリック HRESULT [get_Kind](#get_kind)(CORE_WEBVIEW2_SCRIPT_DIALOG_KIND * Kind)

[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。

#### get_Message 

ダイアログボックスのメッセージ。

> パブリック HRESULT [get_Message](#get_message)(LPWSTR * Message)

JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。

#### Accept 

このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。

> パブリック HRESULT [Accept](#accept)()

これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。 Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。

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

GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。

> パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) * * 延期)

これは、後でイベントを完了するために使用できます。

