---
title: 非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: a1fccf1cec811501b94e7da4aa20b69d93754f62
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942066"
---
# <span data-ttu-id="29d9d-102">非同期 Windows ランタイム方法からの特殊なエラー プロパティ</span><span class="sxs-lookup"><span data-stu-id="29d9d-102">Special error properties from asynchronous Windows Runtime methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="29d9d-103">エラーが呼び出し先の場所からどこからでも発生する可能性があるため、JavaScript で非同期 Windows ランタイムメソッドをデバッグするのがわかりにくいことがあります。</span><span class="sxs-lookup"><span data-stu-id="29d9d-103">It can be difficult to debug asynchronous Windows Runtime methods in JavaScript, because the error may be thrown from somewhere deep in the call stack.</span></span>  <span data-ttu-id="29d9d-104">JavaScript オブジェクトには、デバッグ モードで実行されているときに非同期 Windows ランタイム メソッドからエラーが発生した場合にのみ表示される追加プロパティ `Error` があります。</span><span class="sxs-lookup"><span data-stu-id="29d9d-104">The JavaScript `Error` object has extra properties that appear only when the error is thrown from an asynchronous Windows Runtime method when the app is running in debug mode.</span></span>  
  
## <span data-ttu-id="29d9d-105">特殊なエラー プロパティ</span><span class="sxs-lookup"><span data-stu-id="29d9d-105">Special error properties</span></span>  

<span data-ttu-id="29d9d-106">デバッグ モードでの非同期操作で発生するエラー オブジェクトには、次の特殊なプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="29d9d-106">An error object that results from a failed Windows Runtime asynchronous operation in debug mode has the following special properties:</span></span>  

*   `asyncOpSource` <span data-ttu-id="29d9d-107">\(Object\) は、エラーを発生した元の場所に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="29d9d-107">\(Object\) Gets information about the original location where the call that produced an error was made.</span></span>  <span data-ttu-id="29d9d-108">プロパティ \(文字列\) は、非同期操作を元にしたユーザーのコード内の位置 `asyncOpSource.originatingCall` を表示します。</span><span class="sxs-lookup"><span data-stu-id="29d9d-108">The property `asyncOpSource.originatingCall` \(String\) displays the location in the user's code that originated the asynchronous operation.</span></span>  
*   <span data-ttu-id="29d9d-109">asyncOpType \(文字列\) は、エラーを生じた非同期操作の種類の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="29d9d-109">asyncOpType \(String\) Gets the name of the asynchronous operation type that raised the error.</span></span>  
    
<span data-ttu-id="29d9d-110">非同期操作でのエラーの詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d9d-110">For more information about errors with asynchronous operations, see:</span></span>  
  
*   [<span data-ttu-id="29d9d-111">エラーを誤りで処理する方法</span><span class="sxs-lookup"><span data-stu-id="29d9d-111">How to handle errors with promises</span></span>][PreviousVersionsWindowsAppsHh700337]  
*   [<span data-ttu-id="29d9d-112">Windows ランタイム エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="29d9d-112">Troubleshooting Windows Runtime errors</span></span>][PreviousVersionsWindowsAppsHh974350]  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "エラーを誤って処理する方法 (HTML) |Microsoft ドキュメント"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows ランタイム エラー (HTML) のトラブルシューティング |Microsoft ドキュメント"  
