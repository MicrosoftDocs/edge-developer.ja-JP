---
description: ページ ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 検査されたページに関連するアクションとイベントは、ページ ドメインに属します。
title: ページ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d969dd100164ace61445a4618174cfa943dcfd2b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398848"
---
# <a name="page-domain---devtools-protocol-version-02-edgehtml"></a>ページ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)  

検査されたページに関連するアクションとイベントは、ページ ドメインに属します。  

| 分類 | Members |  
|:--- |:--- |  
| [メソッド](#methods) | [enable](#enable), [disable](#disable), [navigate](#navigate), [getFrameTree](#getframetree) |  
| [イベント](#events) | [frameAttached](#frameattached), [frameDetached](#framedetached), [frameNavigated](#framenavigated), [loadEventFired](#loadeventfired), [domContentEventFired](#domcontenteventfired) |  
| [型](#types) | [FrameId](#frameid)、 [Frame](#frame)、 [FrameTree](#frametree) |  

## <a name="methods"></a>メソッド  

### <a name="enable"></a>[有効]  

ページ ドメイン通知を有効にします。  

&nbsp;  

---  

### <a name="disable"></a>[無効]  

ページ ドメイン通知を無効にします。  

&nbsp;  

---  

### <a name="navigate"></a>ナビゲート  

現在のページを特定の URL に移動します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| url | `string` | ページを移動する URL。 |  
| frameId \(optional\) | [FrameId](#frameid) | 移動するフレーム ID。  指定しない場合は、トップ ページを移動します。 |  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| frameId | [FrameId](#frameid) | 移動するフレーム ID。 |  

---  

### <a name="getframetree"></a>getFrameTree  

現在のフレーム ツリー構造を返します。  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| frameTree | [FrameTree](#frametree) | 現在のフレーム ツリー構造。 |  

---  

## <a name="events"></a>イベント  

### <a name="frameattached"></a>frameAttached  

フレームが親に接続されている場合に発生します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| frameId | [FrameId](#frameid) | 接続されているフレームの ID。 |  
| parentFrameId | [FrameId](#frameid) | 親フレーム識別子。 |  
| stack \(optional\) | [Runtime.StackTrace](./runtime.md#stacktrace) | フレームが接続された場合の JavaScript スタック トレースは、スクリプトからフレームが開始された場合にのみ設定されます。 |  

---  

### <a name="framedetached"></a>frameDetached  

フレームが親から切り離された場合に発生します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| frameId | [FrameId](#frameid) | デタッチされたフレームの ID。 |  

---  

### <a name="framenavigated"></a>frameNavigated  

フレームのナビゲーションが完了すると発生します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| フレーム | [フレーム](#frame) | Frame オブジェクト。 |  

---  

### <a name="loadeventfired"></a>loadEventFired  

イベントに対応 `window.onload` します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| タイムスタンプ | `number` | エポックからのミリ秒単位。 |  

---  

### <a name="domcontenteventfired"></a>domContentEventFired  

イベントに対応 `document.onDOMContentLoaded` します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| タイムスタンプ | `number` | エポックからのミリ秒単位。 |  

---  

## <a name="types"></a>型  

### <a name="frameid-string"></a>FrameId 文字列  

<a name="frameid"></a>  

一意のフレーム識別子。  

&nbsp;  

---  

### <a name="frame-object"></a>Frame オブジェクト  

<a name="frame"></a>  

ページのフレームに関する情報。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| id | [FrameId](#frameid) | フレームの一意の識別子。 |  
| parentId \(optional\) | [FrameId](#frameid) | 親フレームの一意の識別子。 |  
| name \(optional\) | `string` | タグで指定されているフレームの名前。 |  
| url | `string` | フレーム ドキュメントの URL。 |  
| securityOrigin | `string` | フレーム ドキュメントのセキュリティの発生元。 |  
| mimeType | `string` | ブラウザーによって決定されるドキュメントの mimeType をフレームします。 |  

---  

### <a name="frametree-object"></a>FrameTree オブジェクト  

<a name="frametree"></a>  

フレーム階層に関する情報。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| フレーム | [フレーム](#frame) | このツリー アイテムのフレーム情報。 |  
| childFrames \(optional\) | [FrameTree[]](#frametree) | 子フレーム。 |  

---  
