---
description: Windows ランタイム非同期メソッドの使用。
title: Windows ランタイム非同期メソッドの使用
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime asynchronous methods
ms.assetid: 70756833-44f7-4383-827f-2ac781558082
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 26ed26e07049a9488aebe5fda92a65550474b51c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234641"
---
# Windows ランタイム非同期メソッドの使用  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

多くの Windows ランタイム メソッド、特に完了に時間がかかる可能性があるメソッドは非同期です。  これらのメソッドは、通常、非同期のアクションまたは操作 \(たとえば、, `Windows.Foundation.IAsyncAction` `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` `Windows.Foundation.IAsyncOperationWithProgress` \) を返します。  これらのメソッドは、JavaScript では [CommonJS/Promises/A パターンで表されます][CommonjsWikiPromises]。  つまり、then 関数を持つ Promise[][PreviousVersionsWindowsAppsBr229728]オブジェクトを返します。このオブジェクトには、操作が成功した場合に結果を処理する関数を提供 `completed` する必要があります。  エラー ハンドラーを提供しない場合は、関数の代わりに done [関数][PreviousVersionsWindowsAppsHr701079] を使用する必要 `then` があります。  

> [!IMPORTANT]
> Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。  

## 非同期メソッドの例  

次の例では、関数はメソッドの完成した値を表す `then` パラメーターを受け取 `createResourceAsync` ります。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

この場合、メソッドが失敗した場合、エラー状態の promise を返しますが、例外 `createResourceAsync` はスローしません。  次のような関数を使用して、エラー `then` を処理できます。  

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

エラーを明示的に処理するのではなく、例外をスローする場合は、代わりに関数を `done` 使用できます。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

3 つ目の関数を使用して、完了までの進行状況を表示できます。  

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

非同期プログラミングの詳細については [、「JavaScript での非同期プログラミング」を参照してください][PreviousVersionsWindowsAppsHh700330]。  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript での Windows ランタイムの使用 |Microsoft Docs"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "Promise.then メソッド |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript での非同期プログラミング (HTML) |Microsoft Docs"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise.done メソッド |Microsoft Docs"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "Promises |CommonJS Spec Wiki"  
