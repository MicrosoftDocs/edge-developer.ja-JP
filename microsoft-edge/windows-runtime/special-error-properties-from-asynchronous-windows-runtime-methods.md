---
title: 非同期 Windows ランタイムメソッドからの特殊なエラープロパティ
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: 5cf2604e26c84e769cf44e0879ee137cbfbe8b90
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570781"
---
# <span data-ttu-id="ec974-102">非同期 Windows ランタイムメソッドからの特殊なエラープロパティ</span><span class="sxs-lookup"><span data-stu-id="ec974-102">Special Error Properties from Asynchronous Windows Runtime Methods</span></span>  

<span data-ttu-id="ec974-103">JavaScript での非同期 Windows ランタイムメソッドのデバッグは困難である可能性があります。これは、コールスタック内の深い場所からエラーがスローされる可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="ec974-103">It can be difficult to debug asynchronous Windows Runtime methods in JavaScript, because the error may be thrown from somewhere deep in the call stack.</span></span> <span data-ttu-id="ec974-104">JavaScript `Error` オブジェクトには、アプリがデバッグモードで実行されているときに、非同期 Windows ランタイムメソッドからエラーがスローされた場合にのみ表示される追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ec974-104">The JavaScript `Error` object has extra properties that appear only when the error is thrown from an asynchronous Windows Runtime method when the app is running in debug mode.</span></span>  
  
## <span data-ttu-id="ec974-105">特別なエラープロパティ</span><span class="sxs-lookup"><span data-stu-id="ec974-105">Special Error Properties</span></span>  

<span data-ttu-id="ec974-106">デバッグモードでの Windows ランタイム非同期操作の失敗によるエラーオブジェクトには、次の特殊なプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ec974-106">An error object that results from a failed Windows Runtime asynchronous operation in debug mode has the following special properties:</span></span>  

*   `asyncOpSource` <span data-ttu-id="ec974-107">\ (オブジェクト \) エラーが発生した元の場所に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ec974-107">\(Object\) Gets information about the original location where the call that produced an error was made.</span></span> <span data-ttu-id="ec974-108">プロパティ `asyncOpSource.originatingCall` \ (文字列 \) には、非同期操作を生成したユーザーのコード内の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec974-108">The property `asyncOpSource.originatingCall` \(String\) displays the location in the user's code that originated the asynchronous operation.</span></span>  
*   <span data-ttu-id="ec974-109">asyncOpType \ (文字列 \) エラーを発生させた非同期操作の型の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="ec974-109">asyncOpType \(String\) Gets the name of the asynchronous operation type that raised the error.</span></span>  
    
<span data-ttu-id="ec974-110">非同期操作のエラーの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec974-110">For more information about errors with asynchronous operations, see:</span></span>  
  
*   [<span data-ttu-id="ec974-111">約束のエラーを処理する方法</span><span class="sxs-lookup"><span data-stu-id="ec974-111">How to handle errors with promises</span></span>][PreviousVersionsWindowsAppsHh700337]  
*   [<span data-ttu-id="ec974-112">Windows ランタイムエラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ec974-112">Troubleshooting Windows Runtime errors</span></span>][PreviousVersionsWindowsAppsHh974350]  

<!-- image links -->  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "約束のエラーを処理する方法 (HTML)"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows ランタイムエラー (HTML) のトラブルシューティング"  
