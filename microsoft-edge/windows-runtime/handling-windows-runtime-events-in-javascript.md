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
# <span data-ttu-id="8480e-102">JavaScript での Windows ランタイムイベントの処理</span><span class="sxs-lookup"><span data-stu-id="8480e-102">Handling Windows Runtime Events in JavaScript</span></span>  

<span data-ttu-id="8480e-103">Windows ランタイムイベントは、JavaScript で C++ または .NET Framework と同じようには表現されません。</span><span class="sxs-lookup"><span data-stu-id="8480e-103">Windows Runtime events are not represented in the same way in JavaScript as they are in C++ or the .NET Framework.</span></span>  <span data-ttu-id="8480e-104">これらはクラスのプロパティではなく、クラスとメソッドに渡される \ (小文字の \) 文字列識別子として表され `addEventListener` `removeEventListener` ます。</span><span class="sxs-lookup"><span data-stu-id="8480e-104">They are not class properties, but rather are represented as \(lowercase\) string identifiers that are passed to the class's `addEventListener` and `removeEventListener` methods.</span></span>  <span data-ttu-id="8480e-105">たとえば、次のようにメソッドに "positionchanged" という文字列を渡すことによって、 [Geolocator の PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged]イベントのイベントハンドラーを追加することができます。 `Geolocator.addEventListener`</span><span class="sxs-lookup"><span data-stu-id="8480e-105">For example, you can add an event handler for the [Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] event by passing the string "positionchanged" to the `Geolocator.addEventListener` method:</span></span>  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

<span data-ttu-id="8480e-106">プロパティを設定することもでき `locator.onpositionchanged` ます。</span><span class="sxs-lookup"><span data-stu-id="8480e-106">You can also set the `locator.onpositionchanged` property:</span></span>  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

<span data-ttu-id="8480e-107">.NET/C++ と JavaScript のもう1つの違いは、イベントハンドラーによって実行されるパラメーターの数です。</span><span class="sxs-lookup"><span data-stu-id="8480e-107">Another difference between .NET/C++ and JavaScript is the number of parameters taken by an event handler.</span></span>  <span data-ttu-id="8480e-108">.NET/C++ では、ハンドラーはイベントの送信者とイベントデータの2つの処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="8480e-108">In .NET/C++, a handler takes two:  the event sender, and the event data.</span></span>  <span data-ttu-id="8480e-109">JavaScript では、2つは1つのオブジェクトとしてバンドルされ `Event` ます。</span><span class="sxs-lookup"><span data-stu-id="8480e-109">In JavaScript, the two are bundled as a single `Event` object.</span></span>  <span data-ttu-id="8480e-110">次の例では、 `ev` パラメーター \ ( `target` property) と event data properties (\ i) の送信者の両方がパラメーターとして含まれてい `position` ます。</span><span class="sxs-lookup"><span data-stu-id="8480e-110">In the following example, the `ev` parameter contains both the sender of the event \(the `target` property\) and the event data properties \(here, just `position`\).</span></span>  <span data-ttu-id="8480e-111">イベントデータプロパティは、各イベントについて記載されているものです。</span><span class="sxs-lookup"><span data-stu-id="8480e-111">The event data properties are the ones that are documented for each event.</span></span>  

```javascript
function (ev) {
    console.log("Sender:  " + ev.target);
    console.log("Position:  " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> <span data-ttu-id="8480e-112">Windows ランタイム機能は、Internet Explorer で実行されるアプリでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8480e-112">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="8480e-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8480e-113">See Also</span></span>  

[<span data-ttu-id="8480e-114">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="8480e-114">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

 <!-- image links -->  

 <!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "JavaScript での Windows ランタイムの使用"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator クラス"  
