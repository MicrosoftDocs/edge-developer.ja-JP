---
description: Windows ランタイム非同期メソッドの使用
title: Windows ランタイム非同期メソッドの使用
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime asynchronous methods
ms.assetid: 70756833-44f7-4383-827f-2ac781558082
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c7e8ac4690525ee89a06eccf843531c2c7a20324
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398155"
---
# <a name="using-windows-runtime-asynchronous-methods"></a>Windows ランタイム非同期メソッドの使用  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

多くの Windows ランタイム メソッド、特に完了に長い時間がかかる可能性があるメソッドは非同期です。  これらのメソッドは、通常、非同期アクションまたは操作 \(たとえば `Windows.Foundation.IAsyncAction` 、、 `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` 、 `Windows.Foundation.IAsyncOperationWithProgress` 、、\) を返します。  これらのメソッドは [、CommonJS/Promises/A パターンによって JavaScript で表されます][CommonjsWikiPromises]。  つまり、then 関数を持つ Promise[][PreviousVersionsWindowsAppsBr229728]オブジェクトを返し、操作が成功した場合に結果を処理する関数を指定 `completed` する必要があります。  エラー ハンドラーを指定しない場合は、関数の代わりに [done][PreviousVersionsWindowsAppsHr701079] 関数を使用する必要 `then` があります。  

> [!IMPORTANT]
> Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。  

## <a name="examples-of-asynchronous-methods"></a>非同期メソッドの例  

次の例では、関数はメソッドの完成値を表す `then` パラメーターを受け取 `createResourceAsync` ります。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

この場合、メソッドが失敗した場合、エラー状態で promise が返されますが、例外 `createResourceAsync` はスローされません。  次のように関数を使用すると、 `then` エラーを処理できます。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
              console.log("New item is: " + newItem.id);
          }
          function(err) {
              console.log("Got error: " + err.message);
          });
```  

エラーを明示的に処理したくないが、例外をスローする場合は、代わりに関数を `done` 使用できます。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

また、3 番目の関数を使用して、完了に向けて行われた進行状況を表示できます。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .then(function(newItem) {
               console.log("New item is: " + newItem.id);
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

非同期プログラミングの詳細については [、「JavaScript の非同期プログラミング」を参照してください][PreviousVersionsWindowsAppsHh700330]。  

## <a name="see-also"></a>関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用|Microsoft Docs"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "Promise.then メソッド|Microsoft Docs"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript (HTML) の非同期プログラミング|Microsoft Docs"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise.done メソッド|Microsoft Docs"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "Promises |CommonJS Spec Wiki"  
