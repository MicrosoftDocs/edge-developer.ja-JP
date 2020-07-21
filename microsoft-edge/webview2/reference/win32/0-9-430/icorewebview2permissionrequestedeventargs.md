---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: e29765a4b8a3e620b8c627c7b05b9f0b4ff63f95
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886417"
---
# 0.9.430-インターフェイス ICoreWebView2PermissionRequestedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

PermissionRequested されたイベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | アクセス許可を要求する web コンテンツの起点。
[get_PermissionKind](#get_permissionkind) | 要求されるアクセス許可の型。
[get_IsUserInitiated](#get_isuserinitiated) | アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。
[get_State](#get_state) | 権限要求の状態。つまり、
[put_State](#put_state) | State プロパティを設定します。
[GetDeferral](#getdeferral) | GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。

## Members

#### get_Uri 

アクセス許可を要求する web コンテンツの起点。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### get_PermissionKind 

要求されるアクセス許可の型。

> パブリック HRESULT [get_PermissionKind](#get_permissionkind)(CORE_WEBVIEW2_PERMISSION_KIND * 値)

#### get_IsUserInitiated 

アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。

> パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール * isUserInitiated)

ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。

#### get_State 

権限要求の状態。つまり、

> パブリック HRESULT [get_State](#get_state)(CORE_WEBVIEW2_PERMISSION_STATE * 値)

要求を許可するかどうか。 既定値は CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT です。

#### put_State 

State プロパティを設定します。

> パブリック HRESULT [put_State](#put_state)(CORE_WEBVIEW2_PERMISSION_STATE 値)

#### GetDeferral 

GetDeferral を呼び出して、 [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを返すことができます。

> パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) * * 延期)

開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。

