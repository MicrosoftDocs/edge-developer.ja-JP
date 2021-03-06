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
# <a name="handling-windows-runtime-events-in-javascript"></a><span data-ttu-id="4b990-103">JavaScript での Windows ランタイム イベントの処理</span><span class="sxs-lookup"><span data-stu-id="4b990-103">Handling Windows Runtime events in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="4b990-104">Windows ランタイム イベントは、JavaScript の C++ イベントまたは Windows ランタイム イベントと同じ方法で.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="4b990-104">Windows Runtime events are not represented in the same way in JavaScript as they are in C++ or the .NET Framework.</span></span>  <span data-ttu-id="4b990-105">これらはクラスプロパティではなく、クラスとメソッドに渡される \(小文字\) 文字列識別子 `addEventListener` として `removeEventListener` 表されます。</span><span class="sxs-lookup"><span data-stu-id="4b990-105">They are not class properties, but rather are represented as \(lowercase\) string identifiers that are passed to the class's `addEventListener` and `removeEventListener` methods.</span></span>  <span data-ttu-id="4b990-106">たとえば、メソッドに文字列を渡して [、Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] イベントのイベント ハンドラー `positionchanged` を追加 `Geolocator.addEventListener` できます。</span><span class="sxs-lookup"><span data-stu-id="4b990-106">For example, you can add an event handler for the [Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] event by passing the string `positionchanged` to the `Geolocator.addEventListener` method:</span></span>  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

<span data-ttu-id="4b990-107">プロパティを設定 `locator.onpositionchanged` できます。</span><span class="sxs-lookup"><span data-stu-id="4b990-107">You can also set the `locator.onpositionchanged` property:</span></span>  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

<span data-ttu-id="4b990-108">.NET/C++ と JavaScript のもう 1 つの違いは、イベント ハンドラーによって実行されるパラメーターの数です。</span><span class="sxs-lookup"><span data-stu-id="4b990-108">Another difference between .NET/C++ and JavaScript is the number of parameters taken by an event handler.</span></span>  <span data-ttu-id="4b990-109">.NET/C++ では、ハンドラーはイベント送信者とイベント データの 2 つを受け取る。</span><span class="sxs-lookup"><span data-stu-id="4b990-109">In .NET/C++, a handler takes two:  the event sender, and the event data.</span></span>  <span data-ttu-id="4b990-110">JavaScript では、2 つが 1 つのオブジェクトとしてバンドル `Event` されます。</span><span class="sxs-lookup"><span data-stu-id="4b990-110">In JavaScript, the two are bundled as a single `Event` object.</span></span>  <span data-ttu-id="4b990-111">次の例では、パラメーターにはイベント \(the property\) の送信者とイベント データ プロパティ `ev` `target` \(ここでは\) の両方が含 `position` まれます。</span><span class="sxs-lookup"><span data-stu-id="4b990-111">In the following example, the `ev` parameter contains both the sender of the event \(the `target` property\) and the event data properties \(here, just `position`\).</span></span>  <span data-ttu-id="4b990-112">イベント データのプロパティは、各イベントに関して文書化されているプロパティです。</span><span class="sxs-lookup"><span data-stu-id="4b990-112">The event data properties are the ones that are documented for each event.</span></span>  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> <span data-ttu-id="4b990-113">Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。</span><span class="sxs-lookup"><span data-stu-id="4b990-113">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4b990-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b990-114">See also</span></span>  

[<span data-ttu-id="4b990-115">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="4b990-115">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用|Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator クラス |Microsoft Docs"  
