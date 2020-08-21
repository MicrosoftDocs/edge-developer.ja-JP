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
# Windows ランタイムの DateTime と TimeSpan の表現  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

日付と時刻の JavaScript 表現は、Windows ランタイム バージョンとは異なります。  Windows ランタイム[DateTime][UwpWindowsFoundationDatetime]構造体は、データ \(と[Date][MDNDate] `DateTime` JavaScript \ と一致するバックアップの範囲と精度がある、 `Date`  このカスタム オブジェクトを変更 `Date` すると、標準の JavaScript の精度になります `Date` 。  JavaScript 値を Windows ランタイムにパスし、範囲チェックされるため、例外がマーシャルな場合 `Date` `DateTime` があります。  

 Windows ラン [タイムスペン構造][UwpWindowsFoundationTimespan] 体はミリ秒に変換され、JavaScript 番号として返されます。  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用する |Microsoft ドキュメント"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime Struct |Microsoft ドキュメント"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan Struct |Microsoft ドキュメント"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日付 |MDN"  
