---
description: Windows ランタイムの DateTime および TimeSpan 表現
title: Windows ランタイムの DateTime および TimeSpan 表現
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime dates and times
- TimeSpan [JavaScript]
- DateTime [JavaScript]
ms.assetid: 9743e9ac-9054-463e-8264-427183e4905f
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1ee3d601e727601aba03f2ff7efa532171b8f815
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234640"
---
# Windows ランタイムの DateTime および TimeSpan 表現  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

日付と時刻の JavaScript 表現は、Windows ランタイム バージョンとは異なります。  Windows ランタイム[の DateTime][UwpWindowsFoundationDatetime]構造体は、データ[][MDNDate] `DateTime` \(JavaScript \ とは異なる範囲と精度を持つバッキング ストアを持つ Date として JavaScript で表 `Date` されます。  このカスタム オブジェクトを変更 `Date` すると、標準の JavaScript になり、 `Date` 精度が失われる可能性があります。  JavaScript の値は Windows ランタイムに渡され、範囲チェックされ、結果として例外 `Date` `DateTime` がマーシャリングされる可能性があります。  

 Windows ランタイム [TimeSpan 構造体は][UwpWindowsFoundationTimespan] ミリ秒単位に変換され、JavaScript 番号として返されます。  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript での Windows ランタイムの使用 |Microsoft Docs"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime 構造体 |Microsoft Docs"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan 構造体 |Microsoft Docs"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日付 |MDN"  
