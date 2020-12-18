---
description: 非同期 Windows ランタイム メソッドの特殊なエラー プロパティ。
title: 非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3557d0097d632f4058e46acbff748f7177d24ab1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234645"
---
# <span data-ttu-id="87d48-103">非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ</span><span class="sxs-lookup"><span data-stu-id="87d48-103">Special error properties from asynchronous Windows Runtime methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="87d48-104">JavaScript で非同期の Windows ランタイム メソッドをデバッグするのは困難な場合があります。これは、エラーが呼び出し履歴の深い場所からスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="87d48-104">It can be difficult to debug asynchronous Windows Runtime methods in JavaScript, because the error may be thrown from somewhere deep in the call stack.</span></span>  <span data-ttu-id="87d48-105">JavaScript オブジェクトには、アプリがデバッグ モードで実行されているときに非同期の Windows ランタイム メソッドからエラーがスローされた場合にのみ表示される追加のプロパティ `Error` があります。</span><span class="sxs-lookup"><span data-stu-id="87d48-105">The JavaScript `Error` object has extra properties that appear only when the error is thrown from an asynchronous Windows Runtime method when the app is running in debug mode.</span></span>  
  
## <span data-ttu-id="87d48-106">特殊なエラー プロパティ</span><span class="sxs-lookup"><span data-stu-id="87d48-106">Special error properties</span></span>  

<span data-ttu-id="87d48-107">デバッグ モードで Windows ランタイムの非同期操作が失敗した場合のエラー オブジェクトには、次の特別なプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="87d48-107">An error object that results from a failed Windows Runtime asynchronous operation in debug mode has the following special properties:</span></span>  

*   `asyncOpSource` <span data-ttu-id="87d48-108">\(Object\) エラーを発生した呼び出しが行われた元の場所に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="87d48-108">\(Object\) Gets information about the original location where the call that produced an error was made.</span></span>  <span data-ttu-id="87d48-109">プロパティ `asyncOpSource.originatingCall` \(String\) は、非同期操作を発生したユーザーのコード内の場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="87d48-109">The property `asyncOpSource.originatingCall` \(String\) displays the location in the user's code that originated the asynchronous operation.</span></span>  
*   <span data-ttu-id="87d48-110">asyncOpType \(String\) エラーが発生した非同期操作の種類の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="87d48-110">asyncOpType \(String\) Gets the name of the asynchronous operation type that raised the error.</span></span>  
    
<span data-ttu-id="87d48-111">非同期操作でのエラーの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87d48-111">For more information about errors with asynchronous operations, see:</span></span>  
  
*   [<span data-ttu-id="87d48-112">Promise を使用してエラーを処理する方法</span><span class="sxs-lookup"><span data-stu-id="87d48-112">How to handle errors with promises</span></span>][PreviousVersionsWindowsAppsHh700337]  
*   [<span data-ttu-id="87d48-113">Windows ランタイム エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="87d48-113">Troubleshooting Windows Runtime errors</span></span>][PreviousVersionsWindowsAppsHh974350]  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "Promise でエラーを処理する方法 (HTML) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows ランタイム エラーのトラブルシューティング (HTML) |Microsoft Docs"  
