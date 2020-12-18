---
description: JavaScript での Windows ランタイムの使用。
title: JavaScript での Windows ランタイムの使用
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 10c90a225816cf32e01bc33648571c13a1aae090
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234642"
---
# JavaScript での Windows ランタイムの使用  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

ユニバーサル Windows プラットフォーム \(UWP\) アプリを作成する場合は、ネイティブの JavaScript オブジェクト、メソッド、およびプロパティを使うのと同じ方法で、Windows ランタイムのクラス、メソッド、およびプロパティを使います。  このトピックでは、入門情報と、Windows ランタイム型の表現方法、非同期の Windows ランタイム メソッドの使い方、Windows ランタイム イベントをリッスンして処理する方法など、JavaScript での Windows ランタイム API の使用に関する基本的な概念について説明するトピックへのリンクを示します。  

一般的な言語のドキュメントについては、MDN の JavaScript リファレンス [ライブラリをご覧][MDNJavascriptReference] ください。  

> [!IMPORTANT]
> Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。  

## Windows ランタイムのリファレンス ドキュメント  

リファレンス ドキュメントについては [、「Windows ランタイム リファレンス」を参照してください][UwpApiIndex]。  コード例は、JavaScript および C++、C#、および Visual Basic。  

## C++、C#、または Windows ランタイム コンポーネントのVisual Basic  

JavaScript で使用できる Windows ランタイム コンポーネントを記述するための手順とガイドラインについては [、「C++][WindowsUwpWinrtCpp] での Windows ランタイム コンポーネントの作成」と [「C#][WindowsUwpWinrtCsharpVb]と Visual Basic での Windows ランタイム コンポーネントの作成」を参照してください。  

## Windows ランタイム機能の大文字と小文字の規則  

JavaScript の Windows ランタイム機能の大文字と小文字の表記規則は、他の言語の場合と若干異なります。  

*   パスカル語の場合、名前空間とクラスは次のとおりです。  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   クラスのメンバー (メソッドとプロパティを含む) と構造体と列挙体のメンバーは、次の場合に使用されます。  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   イベント名の小文字は次のとおりです。  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## 関連項目  

[Windows ランタイム API を使用する際の考慮事項][WindowsRuntimeConsiderationsApi]  
[Windows ランタイム非同期メソッドの使用][WindowsRuntimeAsynchronousMethods]   
[JavaScript での Windows ランタイム イベントの処理][WindowsRuntimeEventsJavascript]   
[Windows ランタイム型の JavaScript 表現][WindowsRuntimeJavascriptTypes]   
[Windows ランタイムの DateTime と TimeSpan の JavaScript プロジェクション][WindowsRuntimeDatetimeTimespan]  

<!-- links  -->  

[WindowsRuntimeConsiderationsApi]: ./considerations-when-using-the-windows-runtime-api.md "Windows ランタイム API を使用する場合の考慮事項 |Microsoft Docs"  
[WindowsRuntimeEventsJavascript]: ./handling-windows-runtime-events-in-javascript.md "JavaScript での Windows ランタイム イベントの処理 |Microsoft Docs"  
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイム型の JavaScript 表現 |Microsoft Docs"  
[WindowsRuntimeAsynchronousMethods]: ./using-windows-runtime-asynchronous-methods.md "Windows ランタイム非同期メソッドの使用 |Microsoft Docs"  
[WindowsRuntimeDatetimeTimespan]: ./windows-runtime-datetime-and-timespan-representations.md "Windows ランタイムの DateTime と TimeSpan の表現 |Microsoft Docs"  

[UwpApiIndex]: /uwp/api/index "Windows UWP 名前空間 |Microsoft Docs"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を使った Windows ランタイム コンポーネント |Microsoft Docs"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# と Visual Basic を使った Windows ランタイム コンポーネント |Microsoft Docs"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript リファレンス |MDN"  
