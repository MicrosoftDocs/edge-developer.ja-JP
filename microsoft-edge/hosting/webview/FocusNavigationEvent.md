---
description: ナビゲーションの理由と場所を含むフォーカスイベントからのディスパッチされたオブジェクト
title: FocusNavigationEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 88f0a4ef8834c6e851f81ee10bf4202a0429f969
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752165"
---
# FocusNavigationEvent オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

[**NavigateFocus**](../webview.md#navigatefocus) / [**Navigationreason**](#navigationreason)と location を含む NavigateFocus[**DepartingFocus**](../webview.md#departingfocus)のディスパッチされたオブジェクト。  

## メソッド  

### requestFocus  

アプリから webview にフォーカスを移動するために呼び出されます。  

### パラメーター  

このメソッドにはパラメーターはありません。  

### 戻り値  

このメソッドに戻り値はありません。  

## プロパティ  

### ナビゲーションの理由  

"左"、"上"、"右"、または "下" のいずれかの列挙型の**Navigationreason**。  

このプロパティは読み取り専用です。  

```javascript
var navigationReason = FocusNavigationEvent.navigationReason;
```  

#### プロパティ値  

種類: **Navigationreason**  

### 原点の高さ  

フォーカスを与える要素の元の高さの場所。  

このプロパティは読み取り専用です。  

```javascript
var originWoriginHeightidth = FocusNavigationEvent.originHeight;
```  

#### プロパティ値  

種類: **float**  

### 残りの原点  

フォーカスを与える要素の左辺の位置。  

このプロパティは読み取り専用です。  

```javascript
var originLeft = FocusNavigationEvent.originLeft;
```  

#### プロパティ値  

種類: **float**  

### 原点の先頭へ  

フォーカスを与える要素の起点の上位の位置。  

このプロパティは読み取り専用です。  

```javascript
var originTop = FocusNavigationEvent.originTop;
```  

#### プロパティ値  

種類: **float**  

### 原点の幅  

フォーカスを与える要素の元の幅。  

このプロパティは読み取り専用です。  

```javascript
var originWidth = FocusNavigationEvent.originWidth;
```  

#### プロパティ値  

種類: **float**  
