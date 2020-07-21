---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2PermissionRequestedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 2bfa4559824c9bb397648249ead8fa8cb60c281c
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884632"
---
# 0.9.515 クラスの WebView2 クラス (CoreWebView2PermissionRequestedEventArgs) 

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

