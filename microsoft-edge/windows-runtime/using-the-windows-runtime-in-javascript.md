---
title: JavaScript での Windows ランタイムの使用
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: bffde93aa973f492189aedcfcaa9c3694d9e61bc
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570779"
---
# JavaScript での Windows ランタイムの使用  

ユニバーサル Windows プラットフォーム \ (UWP) アプリを作成するときに、ネイティブ JavaScript オブジェクト、メソッド、プロパティを使うのと同じように Windows ランタイムクラス、メソッド、プロパティを使うことができます。  このトピックでは、JavaScript での Windows ランタイム Api の基本的な概念について説明しているトピックへのリンクを提供します。これには、Windows ランタイム型の表現方法、非同期 Windows ランタイムメソッドの使い方、Windows ランタイムイベントをリッスンして処理する方法などがあります。  

一般的な言語のドキュメントについては、「MDN の[JavaScript リファレンス][MDNJavascriptReference]ライブラリ」をご覧ください。  

> [!IMPORTANT]
> Windows ランタイム機能は、Internet Explorer で実行されるアプリでは使用できません。  

## Windows ランタイムリファレンスドキュメント  

参考資料については、「 [Windows ランタイムリファレンス][UwpApiIndex]」をご覧ください。  コード例は JavaScript でも、C++、C#、Visual Basic でも利用できます。  

## C++、C#、または Visual Basic での Windows ランタイムコンポーネントの作成  

JavaScript で利用できる Windows ランタイムコンポーネントを作成するための手順とガイドラインについては、「 [C++ での Windows ランタイムコンポーネントの作成][WindowsUwpWinrtCpp]」および「 [C# と Visual Basic での][WindowsUwpWinrtCsharpVb]Windows ランタイムコンポーネントの作成」を参照してください。  

## Windows ランタイム機能を使用した大文字と小文字の規則  

JavaScript での Windows ランタイム機能の大文字と小文字の規則は、他の言語とは若干異なります。  

*   名前空間とクラスは Pascal の場合にあります。  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   メソッドやプロパティ、構造体と列挙体のメンバーなどのクラスのメンバーは、camel 形式で実行されます。  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   イベント名は小文字で示します。  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## 関連項目  

[Windows ランタイム API を使用する際の考慮事項][WindowsRuntimeConsiderationsApi]  
[Windows ランタイム非同期メソッドの使用][WindowsRuntimeAsynchronousMethods]   
[JavaScript での Windows ランタイムイベントの処理][WindowsRuntimeEventsJavascript]   
[Windows ランタイム型の JavaScript 表現][WindowsRuntimeJavascriptTypes]   
[Windows ランタイムの DateTime と TimeSpan の JavaScript のプロジェクション][WindowsRuntimeDatetimeTimespan]  
 
<!-- image links -->  

<!-- links  -->  

[WindowsRuntimeConsiderationsApi]: /microsoft-edge/windows-runtime/considerations-when-using-the-windows-runtime-api "Windows ランタイム API を使用する際の考慮事項"  
[WindowsRuntimeEventsJavascript]: /microsoft-edge/windows-runtime/handling-windows-runtime-events-in-javascript "JavaScript での Windows ランタイムイベントの処理"  
[WindowsRuntimeJavascriptTypes]: /microsoft-edge/windows-runtime/javascript-representation-of-windows-runtime-types "Windows ランタイム型の JavaScript 表現"  
[WindowsRuntimeAsynchronousMethods]: /microsoft-edge/windows-runtime/using-windows-runtime-asynchronous-methods "Windows ランタイム非同期メソッドの使用"  
[WindowsRuntimeDatetimeTimespan]: /microsoft-edge/windows-runtime/windows-runtime-datetime-and-timespan-representations "Windows ランタイムの DateTime と TimeSpan の表現"  

[UwpApiIndex]: /uwp/api/index "Windows UWP の名前空間"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を備えた Windows ランタイムコンポーネント"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# と Visual Basic を使った Windows ランタイムコンポーネント"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript リファレンス |MDN"  
