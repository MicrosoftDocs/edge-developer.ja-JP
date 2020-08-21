---
title: Windows ランタイム非同期メソッドの使用
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime asynchronous methods
ms.assetid: 70756833-44f7-4383-827f-2ac781558082
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d9d59fb8b97e34feb002de1477dbe38709bde713
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942072"
---
# Windows ランタイム非同期の方法を使用する  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

Windows ランタイムのメソッドの多くは、完了までに時間がかかる場合がある方法です。  これらのメソッドは通常、非同期のアクションまたは操作 \(たとえば `Windows.Foundation.IAsyncAction` `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` 、\、\ など) を `Windows.Foundation.IAsyncOperationWithProgress` 返します。  これらのメソッドは [、CommonJS/Promises/A パターンによって表されます][CommonjsWikiPromises]。  つまり、その関数を含む Promise[then function][PreviousVersionsWindowsAppsBr229728]オブジェクトを返します。つまり、演算が成功した場合に結果を処理する関数を `completed` 指定する必要があります。  エラー ハンドラーを提供したくない場合は、関数ではなく [done 関数][PreviousVersionsWindowsAppsHr701079] を使用してください `then` 。  

> [!IMPORTANT]
> Internet Explorer で実行されているアプリでは、Windows ランタイム機能は使用できません。  

## 非同期メソッドの例  

次の例では、この関数は、メソッドの完了した値を表すパラメー `then` ターを使用 `createResourceAsync` します。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

この場合、メソッドが失敗した場合、エラー状態の確率が返されますが、例外は `createResourceAsync` スローされません。  この関数を使用して、次の関数 `then` を使用してエラーを解決することができます。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
              console.log("New item is: " + newItem.id);
          }
          function(err) {
              console.log("Got error: " + err.message);
          });
```  

エラーをそのものにのみ操作したくないが、例外をスローする場合は、代わりに `done` 代わりに関数を使用できます。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

3 番目の関数を使用して完了に対する進捗状況を表示することもできます。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .then(function(newItem) {
               console.log("New item is: " + newItem.id);
            },
    // Error.
            function(error) {
               alert("Failed to create a resource.");
            },
    // Progress.
            function(progress, resultSoFar) {
               setProgressBar(progress);
            });
```  

非同期プログラミングの詳細については [、JavaScript の非同期プログラミングを参照してください][PreviousVersionsWindowsAppsHh700330]。  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用する |Microsoft ドキュメント"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "Promise.then メソッドMicrosoft ドキュメント"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript (HTML) | の非同期プログラミング |Microsoft ドキュメント"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise.done メソッド |Microsoft ドキュメント"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "代表的 |CommonJS Spec Wiki"  
