---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2PermissionRequestedEventArgs。
ms.openlocfilehash: ede6cef20a1a0f5fcd0780376b5ddec07bf05d26
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878800"
---
# WebView2 クラス (CoreWebView2PermissionRequestedEventArgs クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

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

