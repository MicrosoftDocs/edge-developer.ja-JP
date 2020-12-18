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
# <span data-ttu-id="68cc3-103">JavaScript での Windows ランタイム イベントの処理</span><span class="sxs-lookup"><span data-stu-id="68cc3-103">Handling Windows Runtime events in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="68cc3-104">Windows ランタイム イベントは、C++ や .NET Framework の場合と同じ方法で JavaScript で表されません。</span><span class="sxs-lookup"><span data-stu-id="68cc3-104">Windows Runtime events are not represented in the same way in JavaScript as they are in C++ or the .NET Framework.</span></span>  <span data-ttu-id="68cc3-105">クラスプロパティではなく、クラスとメソッドに渡される \(小文字\) 文字列識別子 `addEventListener` として `removeEventListener` 表されます。</span><span class="sxs-lookup"><span data-stu-id="68cc3-105">They are not class properties, but rather are represented as \(lowercase\) string identifiers that are passed to the class's `addEventListener` and `removeEventListener` methods.</span></span>  <span data-ttu-id="68cc3-106">たとえば、次のメソッドに文字列を渡して [、Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] イベントのイベント ハンドラー `positionchanged` を追加 `Geolocator.addEventListener` できます。</span><span class="sxs-lookup"><span data-stu-id="68cc3-106">For example, you can add an event handler for the [Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] event by passing the string `positionchanged` to the `Geolocator.addEventListener` method:</span></span>  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

<span data-ttu-id="68cc3-107">プロパティを設定 `locator.onpositionchanged` できます。</span><span class="sxs-lookup"><span data-stu-id="68cc3-107">You can also set the `locator.onpositionchanged` property:</span></span>  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

<span data-ttu-id="68cc3-108">.NET/C++ と JavaScript のもう 1 つの違いは、イベント ハンドラーによって取られたパラメーターの数です。</span><span class="sxs-lookup"><span data-stu-id="68cc3-108">Another difference between .NET/C++ and JavaScript is the number of parameters taken by an event handler.</span></span>  <span data-ttu-id="68cc3-109">.NET/C++ では、ハンドラーはイベント送信者とイベント データの 2 つを受け取る。</span><span class="sxs-lookup"><span data-stu-id="68cc3-109">In .NET/C++, a handler takes two:  the event sender, and the event data.</span></span>  <span data-ttu-id="68cc3-110">JavaScript では、2 つのオブジェクトが 1 つのオブジェクトとしてバンドル `Event` されています。</span><span class="sxs-lookup"><span data-stu-id="68cc3-110">In JavaScript, the two are bundled as a single `Event` object.</span></span>  <span data-ttu-id="68cc3-111">次の例では、パラメーターにはイベント \(プロパティ\) の送信者とイベント データ プロパティ `ev` `target` \(ここでは\だけ) の両方が含 `position` まれます。</span><span class="sxs-lookup"><span data-stu-id="68cc3-111">In the following example, the `ev` parameter contains both the sender of the event \(the `target` property\) and the event data properties \(here, just `position`\).</span></span>  <span data-ttu-id="68cc3-112">イベント データ プロパティは、各イベントについて文書化されているプロパティです。</span><span class="sxs-lookup"><span data-stu-id="68cc3-112">The event data properties are the ones that are documented for each event.</span></span>  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> <span data-ttu-id="68cc3-113">Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。</span><span class="sxs-lookup"><span data-stu-id="68cc3-113">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="68cc3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="68cc3-114">See also</span></span>  

[<span data-ttu-id="68cc3-115">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="68cc3-115">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript での Windows ランタイムの使用 |Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator クラス |Microsoft Docs"  
