---
title: Windows ランタイムの DateTime および TimeSpan 表現
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime dates and times
- TimeSpan [JavaScript]
- DateTime [JavaScript]
ms.assetid: 9743e9ac-9054-463e-8264-427183e4905f
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1c51bba74bb7e5182eb25342badcae848eeba339
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942054"
---
# <span data-ttu-id="6cd73-102">Windows ランタイムの DateTime と TimeSpan の表現</span><span class="sxs-lookup"><span data-stu-id="6cd73-102">Windows Runtime DateTime and TimeSpan representations</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="6cd73-103">日付と時刻の JavaScript 表現は、Windows ランタイム バージョンとは異なります。</span><span class="sxs-lookup"><span data-stu-id="6cd73-103">The JavaScript representation of dates and times is different from the Windows Runtime version.</span></span>  <span data-ttu-id="6cd73-104">Windows ランタイム[DateTime][UwpWindowsFoundationDatetime]構造体は、データ \(と[Date][MDNDate] `DateTime` JavaScript \ と一致するバックアップの範囲と精度がある、 `Date`</span><span class="sxs-lookup"><span data-stu-id="6cd73-104">The Windows Runtime [DateTime][UwpWindowsFoundationDatetime] structure is represented in JavaScript as a [Date][MDNDate] that has a backing store that matches the `DateTime` data \(and has a different range and precision from the JavaScript `Date`\).</span></span>  <span data-ttu-id="6cd73-105">このカスタム オブジェクトを変更 `Date` すると、標準の JavaScript の精度になります `Date` 。</span><span class="sxs-lookup"><span data-stu-id="6cd73-105">If you modify this custom `Date` object, it becomes a standard JavaScript `Date` and loses precision.</span></span>  <span data-ttu-id="6cd73-106">JavaScript 値を Windows ランタイムにパスし、範囲チェックされるため、例外がマーシャルな場合 `Date` `DateTime` があります。</span><span class="sxs-lookup"><span data-stu-id="6cd73-106">JavaScript `Date` values can be passed to a Windows Runtime `DateTime` and will be range-checked, which might result in marshaling exceptions.</span></span>  

 <span data-ttu-id="6cd73-107">Windows ラン [タイムスペン構造][UwpWindowsFoundationTimespan] 体はミリ秒に変換され、JavaScript 番号として返されます。</span><span class="sxs-lookup"><span data-stu-id="6cd73-107">The Windows Runtime [TimeSpan][UwpWindowsFoundationTimespan] structure is converted to milliseconds and returned as a JavaScript number.</span></span>  

## <span data-ttu-id="6cd73-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cd73-108">See also</span></span>  

[<span data-ttu-id="6cd73-109">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="6cd73-109">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用する |Microsoft ドキュメント"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime Struct |Microsoft ドキュメント"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan Struct |Microsoft ドキュメント"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日付 |MDN"  
