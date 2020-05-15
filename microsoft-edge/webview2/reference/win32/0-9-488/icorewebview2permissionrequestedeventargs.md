---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 018d986ac0941406a62786bfb6e3666cf33dc09f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654376"
---
# インターフェイス ICoreWebView2PermissionRequestedEventArgs 

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

PermissionRequested されたイベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_IsUserInitiated](#get_isuserinitiated) | アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。
[get_PermissionKind](#get_permissionkind) | 要求されるアクセス許可の型。
[get_State](#get_state) | 権限要求の状態。つまり、
[get_Uri](#get_uri) | アクセス許可を要求する web コンテンツの起点。
[GetDeferral](#getdeferral) | GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。
[put_State](#put_state) | State プロパティを設定します。

## Members

#### get_IsUserInitiated 

アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。

> パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール * isUserInitiated)

ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。

#### get_PermissionKind 

要求されるアクセス許可の型。

> パブリック HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND * 値)

#### get_State 

権限要求の状態。つまり、

> パブリック HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE * 値)

要求を許可するかどうか。 既定値は COREWEBVIEW2_PERMISSION_STATE_DEFAULT です。

#### get_Uri 

アクセス許可を要求する web コンテンツの起点。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### GetDeferral 

GetDeferral を呼び出して、 [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを返すことができます。

> パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) * * 延期)

開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。

#### put_State 

State プロパティを設定します。

> パブリック HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE 値)

