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
ms.openlocfilehash: 58d87d1815b81969c4424eacfcec26ffe425192e
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698955"
---
# WebView2 クラス (CoreWebView2PermissionRequestedEventArgs クラス) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

PermissionRequested されたイベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[IsUserInitiated](#isuserinitiated) | アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。
[PermissionKind](#permissionkind) | 要求されるアクセス許可の型。
[状態](#state) | 権限要求の状態。つまり、
[URI](#uri) | アクセス許可を要求する web コンテンツの起点。
[GetDeferral](#getdeferral) | GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。

## Members

#### IsUserInitiated 

アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。

> public bool [Isuserinitiated](#isuserinitiated)

ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。

#### PermissionKind 

要求されるアクセス許可の型。

> パブリック CoreWebView2PermissionKind [Permissionkind](#permissionkind)

#### 状態 

権限要求の状態。つまり、

> パブリック CoreWebView2PermissionState の[状態](#state)

要求を許可するかどうか。

既定値は CoreWebView2PermissionState です。

#### URI 

アクセス許可を要求する web コンテンツの起点。

> パブリック文字列の[Uri](#uri)

#### GetDeferral 

GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。

> パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()

開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。

