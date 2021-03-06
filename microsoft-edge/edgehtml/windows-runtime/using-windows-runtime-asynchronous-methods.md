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
# <a name="using-windows-runtime-asynchronous-methods"></a><span data-ttu-id="7ba03-103">Windows ランタイム非同期メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="7ba03-103">Using Windows Runtime asynchronous methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="7ba03-104">多くの Windows ランタイム メソッド、特に完了に長い時間がかかる可能性があるメソッドは非同期です。</span><span class="sxs-lookup"><span data-stu-id="7ba03-104">Many Windows Runtime methods, especially methods that might take a long time to complete, are asynchronous.</span></span>  <span data-ttu-id="7ba03-105">これらのメソッドは、通常、非同期アクションまたは操作 \(たとえば `Windows.Foundation.IAsyncAction` 、、 `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` 、 `Windows.Foundation.IAsyncOperationWithProgress` 、、\) を返します。</span><span class="sxs-lookup"><span data-stu-id="7ba03-105">These methods generally return an asynchronous action or operation \(for example, `Windows.Foundation.IAsyncAction`, `Windows.Foundation.IAsyncOperation`, `Windows.Foundation.IAsyncActionWithProgress`, or `Windows.Foundation.IAsyncOperationWithProgress`\).</span></span>  <span data-ttu-id="7ba03-106">これらのメソッドは [、CommonJS/Promises/A パターンによって JavaScript で表されます][CommonjsWikiPromises]。</span><span class="sxs-lookup"><span data-stu-id="7ba03-106">These methods are represented in JavaScript by the [CommonJS/Promises/A pattern][CommonjsWikiPromises].</span></span>  <span data-ttu-id="7ba03-107">つまり、then 関数を持つ Promise[][PreviousVersionsWindowsAppsBr229728]オブジェクトを返し、操作が成功した場合に結果を処理する関数を指定 `completed` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ba03-107">That is, they return a Promise object that has a [then function][PreviousVersionsWindowsAppsBr229728], for which you must provide a `completed` function that handles the result if the operation succeeds.</span></span>  <span data-ttu-id="7ba03-108">エラー ハンドラーを指定しない場合は、関数の代わりに [done][PreviousVersionsWindowsAppsHr701079] 関数を使用する必要 `then` があります。</span><span class="sxs-lookup"><span data-stu-id="7ba03-108">If you don't want to provide an error handler, you should use the [done function][PreviousVersionsWindowsAppsHr701079] instead of the `then` function.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="7ba03-109">Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。</span><span class="sxs-lookup"><span data-stu-id="7ba03-109">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <a name="examples-of-asynchronous-methods"></a><span data-ttu-id="7ba03-110">非同期メソッドの例</span><span class="sxs-lookup"><span data-stu-id="7ba03-110">Examples of asynchronous methods</span></span>  

<span data-ttu-id="7ba03-111">次の例では、関数はメソッドの完成値を表す `then` パラメーターを受け取 `createResourceAsync` ります。</span><span class="sxs-lookup"><span data-stu-id="7ba03-111">In the following example, the `then` function takes a parameter that represents the completed value of the `createResourceAsync` method.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="7ba03-112">この場合、メソッドが失敗した場合、エラー状態で promise が返されますが、例外 `createResourceAsync` はスローされません。</span><span class="sxs-lookup"><span data-stu-id="7ba03-112">In this case, if the `createResourceAsync` method fails, it returns a promise in the error state, but does not throw an exception.</span></span>  <span data-ttu-id="7ba03-113">次のように関数を使用すると、 `then` エラーを処理できます。</span><span class="sxs-lookup"><span data-stu-id="7ba03-113">You can handle an error by using the `then` function as follows.</span></span>  

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

<span data-ttu-id="7ba03-114">エラーを明示的に処理したくないが、例外をスローする場合は、代わりに関数を `done` 使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ba03-114">If you don't want to handle the error explicitly, but do want it to throw an exception, you can use the `done` function instead.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="7ba03-115">また、3 番目の関数を使用して、完了に向けて行われた進行状況を表示できます。</span><span class="sxs-lookup"><span data-stu-id="7ba03-115">You can also display the progress made towards completion by using a third function.</span></span>  

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

<span data-ttu-id="7ba03-116">非同期プログラミングの詳細については [、「JavaScript の非同期プログラミング」を参照してください][PreviousVersionsWindowsAppsHh700330]。</span><span class="sxs-lookup"><span data-stu-id="7ba03-116">For more information about asynchronous programming, see [Asynchronous Programming in JavaScript][PreviousVersionsWindowsAppsHh700330].</span></span>  

## <a name="see-also"></a><span data-ttu-id="7ba03-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ba03-117">See also</span></span>  

[<span data-ttu-id="7ba03-118">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="7ba03-118">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用|Microsoft Docs"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "Promise.then メソッド|Microsoft Docs"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript (HTML) の非同期プログラミング|Microsoft Docs"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise.done メソッド|Microsoft Docs"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "Promises |CommonJS Spec Wiki"  
