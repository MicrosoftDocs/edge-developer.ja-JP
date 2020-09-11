---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2ScriptDialogOpeningEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2ScriptDialogOpeningEventArgs。
ms.openlocfilehash: 9be4a2da9e29dec69f8cc50eef10d5f99e6c5cd4
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010874"
---
# 0.9.579 クラスの WebView2 クラス (CoreWebView2ScriptDialogOpeningEventArgs) 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

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

> パブリック文字列の [Defaulttext](#defaulttext)

これは、プロンプト JavaScript 関数の結果として使用される既定値です。

#### 種類 

JavaScript ダイアログボックスの種類。

> パブリック CoreWebView2ScriptDialogKind [Kind](#kind)

[承諾]、[確認]、[メッセージ]、または [前にアンロード] を選びます。

#### メッセージ 

ダイアログボックスのメッセージ。

> パブリック文字列 [メッセージ](#message)

JavaScript からは、警告、確認、およびプロンプトに渡される最初のパラメーターであり、beforeunload では空です。

#### ResultText 

Accept が呼び出された場合の JavaScript プロンプト関数からの戻り値。

> パブリック文字列の [Resulttext](#resulttext)

ダイアログ以外のダイアログでは、このメッセージは無視されます。 Accept が呼び出されない場合は、この値は無視され、プロンプトから false が返されます。

#### URI 

ダイアログボックスを要求したページの URI。

> パブリック文字列の [Uri](#uri)

#### Accept 

このメソッドを呼び出すことによって、[OK] をクリックすると、ダイアログボックスが表示されます。また、このメソッドを呼び出すことはできません。

> パブリック void [Accept](#accept)()

これは、JavaScript では、Accept が呼び出された場合は、confirm と beforeunload 関数が true を返すことを意味します。 Prompt 関数の場合、Accept が呼び出された場合は ResultText の値を返し、それ以外の場合は false を返します。

#### GetDeferral 

GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。

> パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()

これは、後でイベントを完了するために使用できます。

