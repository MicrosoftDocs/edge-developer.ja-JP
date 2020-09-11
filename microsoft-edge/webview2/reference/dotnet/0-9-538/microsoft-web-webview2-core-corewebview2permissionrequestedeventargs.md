---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2PermissionRequestedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2PermissionRequestedEventArgs。
ms.openlocfilehash: 2ad85879ccf69ccecef355ea07d311cc5a23de11
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010941"
---
# 0.9.579 クラスの WebView2 クラス (CoreWebView2PermissionRequestedEventArgs) 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

> パブリック CoreWebView2PermissionState の [状態](#state)

要求を許可するかどうか。

既定値は CoreWebView2PermissionState です。

#### URI 

アクセス許可を要求する web コンテンツの起点。

> パブリック文字列の [Uri](#uri)

#### GetDeferral 

GetDeferral を呼び出して CoreWebView2Deferral オブジェクトを返すことができます。

> パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()

開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。

