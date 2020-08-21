---
title: JavaScript での Windows ランタイム イベントの処理
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime events
- Windows Runtime events [JavaScript]
ms.assetid: d9436aff-2c30-4846-b8df-eaa3e63fd75c
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: fe44457206569c1e32c40514b4b186bec50d1e3c
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942158"
---
# JavaScript での Windows ランタイム イベントの使用  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

Windows ランタイム イベントは、C++ または .NET Framework と同じ方法で表されません。  クラスのプロパティであり、クラスのメソッドに合わされた \(lowercase\) の文字列識別子として `addEventListener` `removeEventListener` 表されます。  たとえば、文字列をメソッドに入力することで [、Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] イベントのイベント ハンド `positionchanged` ラーを `Geolocator.addEventListener` 追加できます。  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

プロパティを設定 `locator.onpositionchanged` する方法:  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

.NET/C++ と JavaScript の別の違いは、イベント ハンドラーによって実行されるパラメーターの数です。  .NET/C++では、ハンドラーにはイベントの差出人とイベント データの 2 つがあります。  JavaScript では、2 つは 1 つのオブジェクトとしてバンド `Event` ルされます。  次の例では、パラメ `ev` ーターにはイベント \(プロパティ\) とイベント データ プロパティ `target` \(ここで \) の送信者の `position` 両方が含まれています。  イベント データ プロパティは、イベントごとに文書を作成するものです。  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> Internet Explorer で実行されているアプリでは、Windows ランタイム機能は使用できません。  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用する |Microsoft ドキュメント"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator Class |Microsoft ドキュメント"  
