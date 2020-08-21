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
# <span data-ttu-id="837ce-102">JavaScript での Windows ランタイム イベントの使用</span><span class="sxs-lookup"><span data-stu-id="837ce-102">Handling Windows Runtime events in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="837ce-103">Windows ランタイム イベントは、C++ または .NET Framework と同じ方法で表されません。</span><span class="sxs-lookup"><span data-stu-id="837ce-103">Windows Runtime events are not represented in the same way in JavaScript as they are in C++ or the .NET Framework.</span></span>  <span data-ttu-id="837ce-104">クラスのプロパティであり、クラスのメソッドに合わされた \(lowercase\) の文字列識別子として `addEventListener` `removeEventListener` 表されます。</span><span class="sxs-lookup"><span data-stu-id="837ce-104">They are not class properties, but rather are represented as \(lowercase\) string identifiers that are passed to the class's `addEventListener` and `removeEventListener` methods.</span></span>  <span data-ttu-id="837ce-105">たとえば、文字列をメソッドに入力することで [、Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] イベントのイベント ハンド `positionchanged` ラーを `Geolocator.addEventListener` 追加できます。</span><span class="sxs-lookup"><span data-stu-id="837ce-105">For example, you can add an event handler for the [Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] event by passing the string `positionchanged` to the `Geolocator.addEventListener` method:</span></span>  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

<span data-ttu-id="837ce-106">プロパティを設定 `locator.onpositionchanged` する方法:</span><span class="sxs-lookup"><span data-stu-id="837ce-106">You can also set the `locator.onpositionchanged` property:</span></span>  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

<span data-ttu-id="837ce-107">.NET/C++ と JavaScript の別の違いは、イベント ハンドラーによって実行されるパラメーターの数です。</span><span class="sxs-lookup"><span data-stu-id="837ce-107">Another difference between .NET/C++ and JavaScript is the number of parameters taken by an event handler.</span></span>  <span data-ttu-id="837ce-108">.NET/C++では、ハンドラーにはイベントの差出人とイベント データの 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="837ce-108">In .NET/C++, a handler takes two:  the event sender, and the event data.</span></span>  <span data-ttu-id="837ce-109">JavaScript では、2 つは 1 つのオブジェクトとしてバンド `Event` ルされます。</span><span class="sxs-lookup"><span data-stu-id="837ce-109">In JavaScript, the two are bundled as a single `Event` object.</span></span>  <span data-ttu-id="837ce-110">次の例では、パラメ `ev` ーターにはイベント \(プロパティ\) とイベント データ プロパティ `target` \(ここで \) の送信者の `position` 両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="837ce-110">In the following example, the `ev` parameter contains both the sender of the event \(the `target` property\) and the event data properties \(here, just `position`\).</span></span>  <span data-ttu-id="837ce-111">イベント データ プロパティは、イベントごとに文書を作成するものです。</span><span class="sxs-lookup"><span data-stu-id="837ce-111">The event data properties are the ones that are documented for each event.</span></span>  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> <span data-ttu-id="837ce-112">Internet Explorer で実行されているアプリでは、Windows ランタイム機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="837ce-112">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="837ce-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="837ce-113">See also</span></span>  

[<span data-ttu-id="837ce-114">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="837ce-114">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用する |Microsoft ドキュメント"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator Class |Microsoft ドキュメント"  
