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
# <span data-ttu-id="bcafd-102">Windows ランタイム非同期の方法を使用する</span><span class="sxs-lookup"><span data-stu-id="bcafd-102">Using Windows Runtime asynchronous methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="bcafd-103">Windows ランタイムのメソッドの多くは、完了までに時間がかかる場合がある方法です。</span><span class="sxs-lookup"><span data-stu-id="bcafd-103">Many Windows Runtime methods, especially methods that might take a long time to complete, are asynchronous.</span></span>  <span data-ttu-id="bcafd-104">これらのメソッドは通常、非同期のアクションまたは操作 \(たとえば `Windows.Foundation.IAsyncAction` `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` 、\、\ など) を `Windows.Foundation.IAsyncOperationWithProgress` 返します。</span><span class="sxs-lookup"><span data-stu-id="bcafd-104">These methods generally return an asynchronous action or operation \(for example, `Windows.Foundation.IAsyncAction`, `Windows.Foundation.IAsyncOperation`, `Windows.Foundation.IAsyncActionWithProgress`, or `Windows.Foundation.IAsyncOperationWithProgress`\).</span></span>  <span data-ttu-id="bcafd-105">これらのメソッドは [、CommonJS/Promises/A パターンによって表されます][CommonjsWikiPromises]。</span><span class="sxs-lookup"><span data-stu-id="bcafd-105">These methods are represented in JavaScript by the [CommonJS/Promises/A pattern][CommonjsWikiPromises].</span></span>  <span data-ttu-id="bcafd-106">つまり、その関数を含む Promise[then function][PreviousVersionsWindowsAppsBr229728]オブジェクトを返します。つまり、演算が成功した場合に結果を処理する関数を `completed` 指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcafd-106">That is, they return a Promise object that has a [then function][PreviousVersionsWindowsAppsBr229728], for which you must provide a `completed` function that handles the result if the operation succeeds.</span></span>  <span data-ttu-id="bcafd-107">エラー ハンドラーを提供したくない場合は、関数ではなく [done 関数][PreviousVersionsWindowsAppsHr701079] を使用してください `then` 。</span><span class="sxs-lookup"><span data-stu-id="bcafd-107">If you don't want to provide an error handler, you should use the [done function][PreviousVersionsWindowsAppsHr701079] instead of the `then` function.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="bcafd-108">Internet Explorer で実行されているアプリでは、Windows ランタイム機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="bcafd-108">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="bcafd-109">非同期メソッドの例</span><span class="sxs-lookup"><span data-stu-id="bcafd-109">Examples of asynchronous methods</span></span>  

<span data-ttu-id="bcafd-110">次の例では、この関数は、メソッドの完了した値を表すパラメー `then` ターを使用 `createResourceAsync` します。</span><span class="sxs-lookup"><span data-stu-id="bcafd-110">In the following example, the `then` function takes a parameter that represents the completed value of the `createResourceAsync` method.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="bcafd-111">この場合、メソッドが失敗した場合、エラー状態の確率が返されますが、例外は `createResourceAsync` スローされません。</span><span class="sxs-lookup"><span data-stu-id="bcafd-111">In this case, if the `createResourceAsync` method fails, it returns a promise in the error state, but does not throw an exception.</span></span>  <span data-ttu-id="bcafd-112">この関数を使用して、次の関数 `then` を使用してエラーを解決することができます。</span><span class="sxs-lookup"><span data-stu-id="bcafd-112">You can handle an error by using the `then` function as follows.</span></span>  

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

<span data-ttu-id="bcafd-113">エラーをそのものにのみ操作したくないが、例外をスローする場合は、代わりに `done` 代わりに関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcafd-113">If you don't want to handle the error explicitly, but do want it to throw an exception, you can use the `done` function instead.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="bcafd-114">3 番目の関数を使用して完了に対する進捗状況を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcafd-114">You can also display the progress made towards completion by using a third function.</span></span>  

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

<span data-ttu-id="bcafd-115">非同期プログラミングの詳細については [、JavaScript の非同期プログラミングを参照してください][PreviousVersionsWindowsAppsHh700330]。</span><span class="sxs-lookup"><span data-stu-id="bcafd-115">For more information about asynchronous programming, see [Asynchronous Programming in JavaScript][PreviousVersionsWindowsAppsHh700330].</span></span>  

## <span data-ttu-id="bcafd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcafd-116">See also</span></span>  

[<span data-ttu-id="bcafd-117">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="bcafd-117">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用する |Microsoft ドキュメント"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "Promise.then メソッドMicrosoft ドキュメント"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript (HTML) | の非同期プログラミング |Microsoft ドキュメント"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise.done メソッド |Microsoft ドキュメント"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "代表的 |CommonJS Spec Wiki"  
