---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 9d16f1c72a3921b220bd0046e78ed0c6b32a718a
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654387"
---
# インターフェイス IWebView2PermissionRequestedEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2PermissionRequestedEventArgs
  : public IUnknown
```

PermissionRequested されたイベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | アクセス許可を要求する web コンテンツの起点。
[get_PermissionType](#get_permissiontype) | 要求されるアクセス許可の型。
[get_IsUserInitiated](#get_isuserinitiated) | アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。
[get_State](#get_state) | 権限要求の状態。つまり、
[put_State](#put_state) | State プロパティを設定します。
[GetDeferral](#getdeferral) | GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。

## Members

#### get_Uri 

アクセス許可を要求する web コンテンツの起点。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### get_PermissionType 

要求されるアクセス許可の型。

> パブリック HRESULT [get_PermissionType](#get_permissiontype)(WEBVIEW2_PERMISSION_TYPE * 値)

#### get_IsUserInitiated 

アクセス許可要求がユーザーのジェスチャによって開始された場合は True です。

> パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール * isUserInitiated)

ユーザーのジェスチャを通じて開始された場合は、関連付けられたリソースへのアクセスを意図したユーザーではないことに注意してください。

#### get_State 

権限要求の状態。つまり、

> パブリック HRESULT [get_State](#get_state)(WEBVIEW2_PERMISSION_STATE * 値)

要求を許可するかどうか。 既定値は WEBVIEW2_PERMISSION_STATE_DEFAULT です。

#### put_State 

State プロパティを設定します。

> パブリック HRESULT [put_State](#put_state)(WEBVIEW2_PERMISSION_STATE 値)

#### GetDeferral 

GetDeferral を呼び出して、 [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを返すことができます。

> パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) * * 延期)

開発者は、延期オブジェクトを使用して、後でアクセス許可の決定を行うことができます。

