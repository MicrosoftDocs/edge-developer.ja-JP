---
description: Microsoft Edge DevTools プロトコルバージョン0.1 のリリースノート
title: DevTools プロトコルバージョン0.1 リリースノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 3c0648467c20572a525fe257788068966efd193c
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104736"
---
# <span data-ttu-id="bd847-103">DevTools プロトコルバージョン0.1 リリースノート</span><span class="sxs-lookup"><span data-stu-id="bd847-103">DevTools Protocol Version 0.1 Release Notes</span></span>

> [!NOTE]
> <span data-ttu-id="bd847-104">Microsoft Edge の DevTools プロトコルは、 [windows 10 年4月の2018更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の [windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="bd847-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="bd847-105">Microsoft **Edge Devtools プロトコル** のバージョン0.1 には、新しいスタンドアロンの [Microsoft Edge devtools プレビュー](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリで EdgeHTML instrumentation と基本的なリモートデバッグをテストするための早期プレビューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bd847-105">Version 0.1 of the Microsoft **Edge DevTools Protocol** provides an early preview for testing EdgeHTML instrumentation and basic remote debugging in the new standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app.</span></span> <span data-ttu-id="bd847-106">そのため、 [windows 10 の2018年4月の更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) またはそれ以降の [windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd847-106">As such, it requires you to be running [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) or a later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) build.</span></span>

<span data-ttu-id="bd847-107">DevTools プロトコルの背後にあるゴールは、次の3つになります。</span><span class="sxs-lookup"><span data-stu-id="bd847-107">The goals behind the DevTools Protocol are three-fold:</span></span>

 - <span data-ttu-id="bd847-108">Microsoft Edge にアタッチするための DevTools アプリ用のパブリック API を提供する</span><span class="sxs-lookup"><span data-stu-id="bd847-108">Provide a public API for our DevTools app to attach to Microsoft Edge</span></span>
 - <span data-ttu-id="bd847-109">DevTools 機能の access を外部ツールクライアントに拡張する</span><span class="sxs-lookup"><span data-stu-id="bd847-109">Expand access of DevTools functionality to external tooling clients</span></span>
 - <span data-ttu-id="bd847-110">Microsoft Edge を実行している Windows 10 デバイスの範囲でリモートデバッグを有効にする</span><span class="sxs-lookup"><span data-stu-id="bd847-110">Enable remote debugging across the range of Windows 10 devices running Microsoft Edge</span></span> 

<span data-ttu-id="bd847-111">この予備リリースでは、ブレークポイントの設定、コードのステップ実行、スタックトレースの表示などの基本的なデバッグ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bd847-111">This preliminary release provides core debugging functionality, such as setting breakpoints, stepping through code, and exploring stack traces.</span></span> <span data-ttu-id="bd847-112">エッジ DevTools UI では、 [**デバッガー**](../../devtools-guide/debugger.md) パネルで使用可能な機能、マイナスキャッシュ検査 (Web ストレージ、Service Worker、cache API、IndexedDB) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="bd847-112">In the Edge DevTools UI, this translates to functionality available in the [**Debugger**](../../devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> 

<span data-ttu-id="bd847-113">今後のリリースでは、さらにデバッガーの機能が追加されます。その後に、他の [Devtools](../../devtools-guide.md) パネルの電源計装が追加されます。</span><span class="sxs-lookup"><span data-stu-id="bd847-113">Further debugger functionality will be added in upcoming releases, followed by the instrumentation powering other [DevTools](../../devtools-guide.md) panels.</span></span>
