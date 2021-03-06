---
description: 非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ
title: 非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d9f2fdb007f00c2ab1d1a2050378af80f0075db6
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398841"
---
# <a name="special-error-properties-from-asynchronous-windows-runtime-methods"></a><span data-ttu-id="0b960-103">非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ</span><span class="sxs-lookup"><span data-stu-id="0b960-103">Special error properties from asynchronous Windows Runtime methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="0b960-104">JavaScript の非同期 Windows ランタイム メソッドは、呼び出し履歴のどこかからエラーがスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b960-104">It can be difficult to debug asynchronous Windows Runtime methods in JavaScript, because the error may be thrown from somewhere deep in the call stack.</span></span>  <span data-ttu-id="0b960-105">JavaScript オブジェクトには、アプリがデバッグ モードで実行されているときに非同期の Windows ランタイム メソッドからエラーがスローされた場合にのみ表示される追加の `Error` プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="0b960-105">The JavaScript `Error` object has extra properties that appear only when the error is thrown from an asynchronous Windows Runtime method when the app is running in debug mode.</span></span>  
  
## <a name="special-error-properties"></a><span data-ttu-id="0b960-106">特別なエラー プロパティ</span><span class="sxs-lookup"><span data-stu-id="0b960-106">Special error properties</span></span>  

<span data-ttu-id="0b960-107">デバッグ モードで Windows ランタイムの非同期操作が失敗した場合のエラー オブジェクトには、次の特別なプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="0b960-107">An error object that results from a failed Windows Runtime asynchronous operation in debug mode has the following special properties:</span></span>  

*   `asyncOpSource` <span data-ttu-id="0b960-108">\(Object\) エラーが発生した呼び出しが行われた元の場所に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0b960-108">\(Object\) Gets information about the original location where the call that produced an error was made.</span></span>  <span data-ttu-id="0b960-109">プロパティ `asyncOpSource.originatingCall` \(String\) は、非同期操作を発生したユーザーのコード内の場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="0b960-109">The property `asyncOpSource.originatingCall` \(String\) displays the location in the user's code that originated the asynchronous operation.</span></span>  
*   <span data-ttu-id="0b960-110">asyncOpType \(String\) エラーが発生した非同期操作の種類の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="0b960-110">asyncOpType \(String\) Gets the name of the asynchronous operation type that raised the error.</span></span>  
    
<span data-ttu-id="0b960-111">非同期操作のエラーの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b960-111">For more information about errors with asynchronous operations, see:</span></span>  

*   [<span data-ttu-id="0b960-112">Promise でエラーを処理する方法</span><span class="sxs-lookup"><span data-stu-id="0b960-112">How to handle errors with promises</span></span>][PreviousVersionsWindowsAppsHh700337]  
*   [<span data-ttu-id="0b960-113">Windows ランタイム エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0b960-113">Troubleshooting Windows Runtime errors</span></span>][PreviousVersionsWindowsAppsHh974350]  
    
<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "promises (HTML) を使用してエラーを処理する|Microsoft Docs"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows ランタイム エラー (HTML) のトラブルシューティング|Microsoft Docs"  
