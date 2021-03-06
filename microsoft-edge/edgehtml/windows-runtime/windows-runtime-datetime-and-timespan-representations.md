---
description: Windows ランタイムの DateTime および TimeSpan 表現
title: Windows ランタイムの DateTime および TimeSpan 表現
ms.custom: ''
ms.date: 11/03/2020
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
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c2627826755f041a440112c3390ecb17d1f703ce
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398127"
---
# <a name="windows-runtime-datetime-and-timespan-representations"></a>Windows ランタイムの DateTime および TimeSpan 表現  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

日付と時刻の JavaScript 表記は、Windows ランタイム バージョンとは異なります。  Windows ランタイム[DateTime][UwpWindowsFoundationDatetime]構造体は、データ \([][MDNDate]および JavaScript \とは異なる範囲と精度を持つバッキング ストアを持つ Date として JavaScript で表されます `DateTime` `Date` 。  このカスタム オブジェクトを変更 `Date` すると、標準の JavaScript になり `Date` 、精度が失われる。  JavaScript の値は Windows ランタイムに渡され、範囲がチェックされ、例外がマーシャリング `Date` `DateTime` される可能性があります。  

Windows ランタイム [TimeSpan 構造体][UwpWindowsFoundationTimespan] はミリ秒単位に変換され、JavaScript 番号として返されます。  

## <a name="see-also"></a>関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用|Microsoft Docs"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime 構造体|Microsoft Docs"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan Struct |Microsoft Docs"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日付|MDN"  
