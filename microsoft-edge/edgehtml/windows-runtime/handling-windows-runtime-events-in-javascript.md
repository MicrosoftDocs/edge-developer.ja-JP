---
description: JavaScript での Windows ランタイム イベントの処理
title: JavaScript での Windows ランタイム イベントの処理
ms.custom: ''
ms.date: 11/03/2020
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
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 08562f7ebff0c02b96bfc8229238a62463b95451
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397525"
---
# <a name="handling-windows-runtime-events-in-javascript"></a>JavaScript での Windows ランタイム イベントの処理  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

Windows ランタイム イベントは、JavaScript の C++ イベントまたは Windows ランタイム イベントと同じ方法で.NET Framework。  これらはクラスプロパティではなく、クラスとメソッドに渡される \(小文字\) 文字列識別子 `addEventListener` として `removeEventListener` 表されます。  たとえば、メソッドに文字列を渡して [、Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] イベントのイベント ハンドラー `positionchanged` を追加 `Geolocator.addEventListener` できます。  

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

.NET/C++ と JavaScript のもう 1 つの違いは、イベント ハンドラーによって実行されるパラメーターの数です。  .NET/C++ では、ハンドラーはイベント送信者とイベント データの 2 つを受け取る。  JavaScript では、2 つが 1 つのオブジェクトとしてバンドル `Event` されます。  次の例では、パラメーターにはイベント \(the property\) の送信者とイベント データ プロパティ `ev` `target` \(ここでは\) の両方が含 `position` まれます。  イベント データのプロパティは、各イベントに関して文書化されているプロパティです。  

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

## <a name="see-also"></a>関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用|Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator クラス |Microsoft Docs"  
