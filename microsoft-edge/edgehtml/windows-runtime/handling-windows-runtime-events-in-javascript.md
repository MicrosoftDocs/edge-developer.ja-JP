---
description: JavaScript での Windows ランタイム イベントの処理。
title: JavaScript での Windows ランタイム イベントの処理
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime events
- Windows Runtime events [JavaScript]
ms.assetid: d9436aff-2c30-4846-b8df-eaa3e63fd75c
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e0a3e35c908c766c0308903381b271f5ccdb27a3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234892"
---
# JavaScript での Windows ランタイム イベントの処理  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

Windows ランタイム イベントは、C++ や .NET Framework の場合と同じ方法で JavaScript で表されません。  クラスプロパティではなく、クラスとメソッドに渡される \(小文字\) 文字列識別子 `addEventListener` として `removeEventListener` 表されます。  たとえば、次のメソッドに文字列を渡して [、Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] イベントのイベント ハンドラー `positionchanged` を追加 `Geolocator.addEventListener` できます。  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

プロパティを設定 `locator.onpositionchanged` できます。  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

.NET/C++ と JavaScript のもう 1 つの違いは、イベント ハンドラーによって取られたパラメーターの数です。  .NET/C++ では、ハンドラーはイベント送信者とイベント データの 2 つを受け取る。  JavaScript では、2 つのオブジェクトが 1 つのオブジェクトとしてバンドル `Event` されています。  次の例では、パラメーターにはイベント \(プロパティ\) の送信者とイベント データ プロパティ `ev` `target` \(ここでは\だけ) の両方が含 `position` まれます。  イベント データ プロパティは、各イベントについて文書化されているプロパティです。  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript での Windows ランタイムの使用 |Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator クラス |Microsoft Docs"  
