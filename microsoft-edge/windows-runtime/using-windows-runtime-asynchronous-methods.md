---
title: Windows ランタイム非同期メソッドの使用
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: 6d0f174d22d0d13571d78bc215356ad90a0ae7fa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570776"
---
# Windows ランタイム非同期メソッドの使用  

多くの Windows ランタイムメソッド (特に、完了までに長い時間がかかる可能性のあるメソッド) は非同期です。  通常、これらのメソッドは非同期のアクションまたは操作 (たとえば、、、、など) を返し `Windows.Foundation.IAsyncAction` `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` `Windows.Foundation.IAsyncOperationWithProgress` ます。  これらのメソッドは、JavaScript で[commonjs promise、または pattern][CommonjsWikiPromises]によって表されます。  つまり、 [then 関数][PreviousVersionsWindowsAppsBr229728]を持つ Promise オブジェクトを返します。これは、 `completed` 操作が成功した場合に結果を処理する関数を提供する必要があるためです。  エラーハンドラーを指定しない場合は、関数の代わりに[done 関数][PreviousVersionsWindowsAppsHr701079]を使用する必要があり `then` ます。  

> [!IMPORTANT]
> Windows ランタイム機能は、Internet Explorer で実行されるアプリでは使用できません。  

## 非同期メソッドの例  

次の例では、 `then` 関数はメソッドの completed 値を表すパラメーターを受け取り `createResourceAsync` ます。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

この場合、メソッドが失敗すると、 `createResourceAsync` エラー状態の promise が返されますが、例外はスローされません。  エラーを処理するには、次のように関数を使用し `then` ます。  

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

エラーを明示的に処理せずに、例外をスローさせたい場合は、代わりに関数を使うことができ `done` ます。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

また、3番目の関数を使用して、完了までの進行状況を表示することもできます。  

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

非同期プログラミングについて詳しくは、「 [JavaScript での非同期プログラミング][PreviousVersionsWindowsAppsHh700330]」をご覧ください。  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- image links -->  

<!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "JavaScript での Windows ランタイムの使用"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "約束。 then メソッド"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript での非同期プログラミング (HTML)"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise. done メソッド"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "約束 |CommonJS スペック Wiki"  
