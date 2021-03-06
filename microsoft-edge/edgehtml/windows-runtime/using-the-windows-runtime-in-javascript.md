---
description: JavaScript での Windows ランタイムの使用
title: JavaScript での Windows ランタイムの使用
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4e137526ce147cdeb82749474bd43d1b3697361b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399324"
---
# <a name="using-the-windows-runtime-in-javascript"></a>JavaScript での Windows ランタイムの使用  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

ユニバーサル Windows プラットフォーム \(UWP\) アプリを作成する場合は、ネイティブ JavaScript オブジェクト、メソッド、およびプロパティを使用するのと同じ方法で Windows ランタイム クラス、メソッド、およびプロパティを使用できます。  このトピックでは、Windows ランタイムの種類の表現方法、非同期 Windows ランタイム メソッドの使い方、Windows ランタイム イベントのリッスンおよび処理方法など、JavaScript で Windows ランタイム API を使用する基本的な概念を説明するトピックへの入門情報とリンクを提供します。  

一般的な言語のドキュメントについては、MDN の [JavaScript リファレンス ライブラリを参照][MDNJavascriptReference] してください。  

> [!IMPORTANT]
> Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。  

## <a name="windows-runtime-reference-documentation"></a>Windows ランタイムのリファレンス ドキュメント  

リファレンス ドキュメントについては [、「Windows ランタイム リファレンス」を参照してください][UwpApiIndex]。  コード例は、JavaScript および C++、C#、およびVisual Basic。  

## <a name="writing-windows-runtime-components-in-c-c-or-visual-basic"></a>Windows ランタイム コンポーネントの C++、C#、またはVisual Basic  

JavaScript で使用できる Windows ランタイム コンポーネントを記述する手順とガイドラインについては [、「C++][WindowsUwpWinrtCpp] での Windows ランタイム コンポーネントの作成」および「C# および Visual Basic での Windows ランタイム コンポーネントの作成」 [を参照してください][WindowsUwpWinrtCsharpVb]。  

## <a name="casing-conventions-with-windows-runtime-features"></a>Windows ランタイム機能を使用した大文字と小文字の規則  

JavaScript の Windows ランタイム機能の大文字と小文字の表記規則は、他の言語とは若干異なります。  

*   名前空間とクラスは Pascal の場合です。  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   メソッドとプロパティを含むクラスのメンバー、および構造体と列挙体のメンバーは、camel の場合です。  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   イベント名は小文字です。  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  
    
## <a name="see-also"></a>関連項目  

[Windows ランタイム API を使用する際の考慮事項][WindowsRuntimeConsiderationsApi]  
[Windows ランタイム非同期メソッドの使用][WindowsRuntimeAsynchronousMethods]   
[JavaScript での Windows ランタイム イベントの処理][WindowsRuntimeEventsJavascript]   
[Windows ランタイム型の JavaScript 表現][WindowsRuntimeJavascriptTypes]   
[Windows ランタイムの DateTime と TimeSpan の JavaScript プロジェクション][WindowsRuntimeDatetimeTimespan]  

<!-- links -->  

[WindowsRuntimeConsiderationsApi]: ./considerations-when-using-the-windows-runtime-api.md "Windows ランタイム API を使用する場合の考慮事項|Microsoft Docs"  
[WindowsRuntimeEventsJavascript]: ./handling-windows-runtime-events-in-javascript.md "JavaScript の Windows ランタイム イベントの処理|Microsoft Docs"  
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイム型の JavaScript 表現 |Microsoft Docs"  
[WindowsRuntimeAsynchronousMethods]: ./using-windows-runtime-asynchronous-methods.md "Windows ランタイム非同期メソッドの使用|Microsoft Docs"  
[WindowsRuntimeDatetimeTimespan]: ./windows-runtime-datetime-and-timespan-representations.md "Windows ランタイム DateTime および TimeSpan リプレゼンテーション |Microsoft Docs"  

[UwpApiIndex]: /uwp/api/index "Windows UWP 名前空間 |Microsoft Docs"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX の Windows ランタイム |Microsoft Docs"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "Windows ランタイム コンポーネントとC#およびVisual Basic |Microsoft Docs"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript リファレンス |MDN"  
