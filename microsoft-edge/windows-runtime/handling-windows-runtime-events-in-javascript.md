---
title: JavaScript での Windows ランタイムイベントの処理
ms.custom: ''
ms.date: 04/01/2017
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
ms.openlocfilehash: c3db0116a3d464c75fe754e73e41ff1d154f928e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570790"
---
# JavaScript での Windows ランタイムイベントの処理  

Windows ランタイムイベントは、JavaScript で C++ または .NET Framework と同じようには表現されません。  これらはクラスのプロパティではなく、クラスとメソッドに渡される \ (小文字の \) 文字列識別子として表され `addEventListener` `removeEventListener` ます。  たとえば、次のようにメソッドに "positionchanged" という文字列を渡すことによって、 [Geolocator の PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged]イベントのイベントハンドラーを追加することができます。 `Geolocator.addEventListener`  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

プロパティを設定することもでき `locator.onpositionchanged` ます。  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

.NET/C++ と JavaScript のもう1つの違いは、イベントハンドラーによって実行されるパラメーターの数です。  .NET/C++ では、ハンドラーはイベントの送信者とイベントデータの2つの処理を実行します。  JavaScript では、2つは1つのオブジェクトとしてバンドルされ `Event` ます。  次の例では、 `ev` パラメーター \ ( `target` property) と event data properties (\ i) の送信者の両方がパラメーターとして含まれてい `position` ます。  イベントデータプロパティは、各イベントについて記載されているものです。  

```javascript
function (ev) {
    console.log("Sender:  " + ev.target);
    console.log("Position:  " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> Windows ランタイム機能は、Internet Explorer で実行されるアプリでは使用できません。  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

 <!-- image links -->  

 <!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "JavaScript での Windows ランタイムの使用"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator クラス"  
