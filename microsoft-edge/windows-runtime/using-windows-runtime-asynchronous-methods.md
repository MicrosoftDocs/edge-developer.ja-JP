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
# <span data-ttu-id="f7605-102">Windows ランタイム非同期メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="f7605-102">Using Windows Runtime Asynchronous Methods</span></span>  

<span data-ttu-id="f7605-103">多くの Windows ランタイムメソッド (特に、完了までに長い時間がかかる可能性のあるメソッド) は非同期です。</span><span class="sxs-lookup"><span data-stu-id="f7605-103">Many Windows Runtime methods, especially methods that might take a long time to complete, are asynchronous.</span></span>  <span data-ttu-id="f7605-104">通常、これらのメソッドは非同期のアクションまたは操作 (たとえば、、、、など) を返し `Windows.Foundation.IAsyncAction` `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` `Windows.Foundation.IAsyncOperationWithProgress` ます。</span><span class="sxs-lookup"><span data-stu-id="f7605-104">These methods generally return an asynchronous action or operation (for example, `Windows.Foundation.IAsyncAction`, `Windows.Foundation.IAsyncOperation`, `Windows.Foundation.IAsyncActionWithProgress`, or `Windows.Foundation.IAsyncOperationWithProgress`).</span></span>  <span data-ttu-id="f7605-105">これらのメソッドは、JavaScript で[commonjs promise、または pattern][CommonjsWikiPromises]によって表されます。</span><span class="sxs-lookup"><span data-stu-id="f7605-105">These methods are represented in JavaScript by the [CommonJS/Promises/A pattern][CommonjsWikiPromises].</span></span>  <span data-ttu-id="f7605-106">つまり、 [then 関数][PreviousVersionsWindowsAppsBr229728]を持つ Promise オブジェクトを返します。これは、 `completed` 操作が成功した場合に結果を処理する関数を提供する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="f7605-106">That is, they return a Promise object that has a [then function][PreviousVersionsWindowsAppsBr229728], for which you must provide a `completed` function that handles the result if the operation succeeds.</span></span>  <span data-ttu-id="f7605-107">エラーハンドラーを指定しない場合は、関数の代わりに[done 関数][PreviousVersionsWindowsAppsHr701079]を使用する必要があり `then` ます。</span><span class="sxs-lookup"><span data-stu-id="f7605-107">If you don't want to provide an error handler, you should use the [done function][PreviousVersionsWindowsAppsHr701079] instead of the `then` function.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="f7605-108">Windows ランタイム機能は、Internet Explorer で実行されるアプリでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f7605-108">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="f7605-109">非同期メソッドの例</span><span class="sxs-lookup"><span data-stu-id="f7605-109">Examples of Asynchronous Methods</span></span>  

<span data-ttu-id="f7605-110">次の例では、 `then` 関数はメソッドの completed 値を表すパラメーターを受け取り `createResourceAsync` ます。</span><span class="sxs-lookup"><span data-stu-id="f7605-110">In the following example, the `then` function takes a parameter that represents the completed value of the `createResourceAsync` method.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="f7605-111">この場合、メソッドが失敗すると、 `createResourceAsync` エラー状態の promise が返されますが、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="f7605-111">In this case, if the `createResourceAsync` method fails, it returns a promise in the error state, but does not throw an exception.</span></span>  <span data-ttu-id="f7605-112">エラーを処理するには、次のように関数を使用し `then` ます。</span><span class="sxs-lookup"><span data-stu-id="f7605-112">You can handle an error by using the `then` function as follows.</span></span>  

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

<span data-ttu-id="f7605-113">エラーを明示的に処理せずに、例外をスローさせたい場合は、代わりに関数を使うことができ `done` ます。</span><span class="sxs-lookup"><span data-stu-id="f7605-113">If you don't want to handle the error explicitly, but do want it to throw an exception, you can use the `done` function instead.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="f7605-114">また、3番目の関数を使用して、完了までの進行状況を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7605-114">You can also display the progress made towards completion by using a third function.</span></span>  

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

<span data-ttu-id="f7605-115">非同期プログラミングについて詳しくは、「 [JavaScript での非同期プログラミング][PreviousVersionsWindowsAppsHh700330]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7605-115">For more information about asynchronous programming, see [Asynchronous Programming in JavaScript][PreviousVersionsWindowsAppsHh700330].</span></span>  

## <span data-ttu-id="f7605-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7605-116">See Also</span></span>  

[<span data-ttu-id="f7605-117">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="f7605-117">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

<!-- image links -->  

<!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "JavaScript での Windows ランタイムの使用"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "約束。 then メソッド"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript での非同期プログラミング (HTML)"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise. done メソッド"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "約束 |CommonJS スペック Wiki"  
