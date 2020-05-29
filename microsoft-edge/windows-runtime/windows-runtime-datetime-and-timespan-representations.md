---
title: Windows ランタイムの DateTime と TimeSpan の表現
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: d3e138493b80face1238118a99c03f6015a6a8ef
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570775"
---
# Windows ランタイムの DateTime と TimeSpan の表現  

日付と時刻の JavaScript 表現は、Windows ランタイムバージョンとは異なります。  Windows ランタイムの[DateTime][UwpWindowsFoundationDatetime]構造体は、javascript では[Date][MDNDate] 、データに一致するバッキングストア `DateTime` (および javascript \ とは異なる範囲と有効桁数) を持つ日付として表され `Date` ます。  このカスタム `Date` オブジェクトを変更すると、標準 JavaScript となり、精度が低下し `Date` ます。  JavaScript の値は、 `Date` Windows ランタイムに渡すことができます `DateTime` 。範囲がチェックされます。これにより、マーシャリングの例外が発生する可能性があります。  

 Windows ランタイムの[TimeSpan][UwpWindowsFoundationTimespan]構造体は、ミリ秒に変換され、JavaScript の数値として返されます。  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- image links -->  

<!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "JavaScript での Windows ランタイムの使用"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime 構造体"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan 構造体"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日付 |MDN"  
