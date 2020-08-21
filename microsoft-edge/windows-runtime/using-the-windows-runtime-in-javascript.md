---
title: JavaScript での Windows ランタイムの使用
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 444008598a2f7a2f5257544304bed87fbfaa203a
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942170"
---
# JavaScript での Windows ランタイムの使用  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

ユニバーサル Windows プラットフォーム \(UWP\) アプリを作成する場合、ネイティブ JavaScript オブジェクト、メソッド、プロパティを使用する場合と同様に、Windows ランタイム クラス、メソッド、プロパティを使用できます。  このトピックでは、Windows ランタイム API を使用する方法、Windows ランタイム API の使用方法、非同期の Windows ランタイムメソッドの使用方法、Windows ランタイム イベントをリッスンおよび操作する方法など、Windows ランタイム API を使用する基本的な概念について説明するトピックとトピックへのリンクを提供します。  

一般的な言語ドキュメントについては、MDN の [JavaScript][MDNJavascriptReference] リファレンス ライブラリを確認してください。  

> [!IMPORTANT]
> Internet Explorer で実行されているアプリでは、Windows ランタイム機能は使用できません。  

## Windows ランタイム リファレンス ドキュメント  

参照ドキュメントについては [、Windows ランタイム リファレンスを参照してください][UwpApiIndex]。  コード例は、JavaScript でも C++、C#、およびVisual Basic。  

## C++、C#、またはステートで Windows ランタイム コンポーポーンを書き Visual Basic込む  

JavaScript で使用できる Windows ランタイム コンポーンを記述するための手順とガイドラインについては、C++ コンポーントの [作成、C#][WindowsUwpWinrtCpp] および Visual Basic で [Windows ランタイム コンポーントを作成する方法を参照してください][WindowsUwpWinrtCsharpVb]。  

## Windows ランタイム機能を使用した基本的な操作  

JavaScript の Windows ランタイム機能の基本的な操作は、他の言語と少し異なります。  

*   名前空間とクラスは、Pascal case の場合:  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   メソッドやプロパティ、構造と列挙のメンバーなど、クラスのメンバーにはカメラケムが含まれます。  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   イベント名は小文字で表示されます。  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## 関連項目  

[Windows ランタイム API を使用する際の考慮事項][WindowsRuntimeConsiderationsApi]  
[Windows ランタイム非同期メソッドの使用][WindowsRuntimeAsynchronousMethods]   
[JavaScript での Windows ランタイム イベントの処理][WindowsRuntimeEventsJavascript]   
[Windows ランタイム型の JavaScript 表現][WindowsRuntimeJavascriptTypes]   
[JavaScript プロジェクト (Windows ランタイム日付Time と TimeSpan の JavaScript プロジェクション)][WindowsRuntimeDatetimeTimespan]  

<!-- links  -->  

[WindowsRuntimeConsiderationsApi]: ./considerations-when-using-the-windows-runtime-api.md "Windows ランタイム API を使用する場合の考慮事例 |Microsoft ドキュメント"  
[WindowsRuntimeEventsJavascript]: ./handling-windows-runtime-events-in-javascript.md "JavaScript での Windows ランタイム イベントの使用 |Microsoft ドキュメント"  
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイムの種類の JavaScript 表記 |Microsoft ドキュメント"  
[WindowsRuntimeAsynchronousMethods]: ./using-windows-runtime-asynchronous-methods.md "Windows ランタイム非同期の方法を使用する |Microsoft ドキュメント"  
[WindowsRuntimeDatetimeTimespan]: ./windows-runtime-datetime-and-timespan-representations.md "Windows ランタイムの DateTime と TimeSpan Representations |Microsoft ドキュメント"  

[UwpApiIndex]: /uwp/api/index "Windows UWP 名前空間 |Microsoft ドキュメント"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を使用した Windows ランタイム コンポーネント |Microsoft ドキュメント"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# およびデバイスを使用した Windows ランタイム コンポーVisual BasicンVisual Basic |Microsoft ドキュメント"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript リファレンス |MDN"  
