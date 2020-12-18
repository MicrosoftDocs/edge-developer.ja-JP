---
description: Microsoft Edge DevTools プロトコル バージョン 0.1 のリリース ノート
title: DevTools Protocol Version 0.1 リリース ノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 60e92cb3afa9b10b15c8ebdd520c0061fbb3b366
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234795"
---
# <span data-ttu-id="ccd44-103">DevTools Protocol Version 0.1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="ccd44-103">DevTools Protocol Version 0.1 Release Notes</span></span>

> [!NOTE]
> <span data-ttu-id="ccd44-104">Microsoft Edge DevTools プロトコルは [、Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="ccd44-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="ccd44-105">Microsoft **Edge DevTools プロトコル** のバージョン 0.1 は、新しいスタンドアロンの Microsoft Edge [DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリで EdgeHTML インストルメンテーションと基本的なリモート デバッグをテストする初期プレビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="ccd44-105">Version 0.1 of the Microsoft **Edge DevTools Protocol** provides an early preview for testing EdgeHTML instrumentation and basic remote debugging in the new standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app.</span></span> <span data-ttu-id="ccd44-106">そのため、Windows [10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の Windows [Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccd44-106">As such, it requires you to be running [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) or a later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) build.</span></span>

<span data-ttu-id="ccd44-107">DevTools プロトコルの目標は次の 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="ccd44-107">The goals behind the DevTools Protocol are three-fold:</span></span>

 - <span data-ttu-id="ccd44-108">Microsoft Edge にアタッチする DevTools アプリのパブリック API を提供する</span><span class="sxs-lookup"><span data-stu-id="ccd44-108">Provide a public API for our DevTools app to attach to Microsoft Edge</span></span>
 - <span data-ttu-id="ccd44-109">DevTools 機能の外部ツール クライアントへのアクセスを拡張する</span><span class="sxs-lookup"><span data-stu-id="ccd44-109">Expand access of DevTools functionality to external tooling clients</span></span>
 - <span data-ttu-id="ccd44-110">Microsoft Edge を実行しているさまざまな Windows 10 デバイスでリモート デバッグを有効にする</span><span class="sxs-lookup"><span data-stu-id="ccd44-110">Enable remote debugging across the range of Windows 10 devices running Microsoft Edge</span></span> 

<span data-ttu-id="ccd44-111">この暫定的なリリースでは、ブレークポイントの設定、コードのステップ実行、スタック トレースの探索など、コア デバッグ機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ccd44-111">This preliminary release provides core debugging functionality, such as setting breakpoints, stepping through code, and exploring stack traces.</span></span> <span data-ttu-id="ccd44-112">Edge DevTools UI では、これはデバッガー パネルで使用可能な[\*\*\*\*](../../devtools-guide/debugger.md)機能 (Web ストレージ、サービス ワーカー、キャッシュ API、および IndexedDB の場合) からキャッシュ検査を差し引いた機能に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ccd44-112">In the Edge DevTools UI, this translates to functionality available in the [**Debugger**](../../devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> 

<span data-ttu-id="ccd44-113">今後のリリースでは、デバッガーの機能がさらに追加され、その後に他の [DevTools](../index.md) パネルを起動するインストルメンテーションが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ccd44-113">Further debugger functionality will be added in upcoming releases, followed by the instrumentation powering other [DevTools](../index.md) panels.</span></span>
