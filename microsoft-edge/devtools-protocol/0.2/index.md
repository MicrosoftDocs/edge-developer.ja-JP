---
description: Microsoft Edge DevTools プロトコルバージョン0.2 のリリースノート
title: Microsoft Edge DevTools プロトコルバージョン0.2 リリースノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: c4959d2905f95c2bcf98cb78ad67bb88ecfec959
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104743"
---
# <span data-ttu-id="a6e34-103">DevTools プロトコルバージョン0.2 リリースノート</span><span class="sxs-lookup"><span data-stu-id="a6e34-103">DevTools Protocol Version 0.2 Release Notes</span></span>

> [!NOTE]
> <span data-ttu-id="a6e34-104">Microsoft Edge DevTools プロトコルのバージョン0.2 は、 [windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763) 以降の [windows Insider Preview](https://insider.windows.com/getting-started/) ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="a6e34-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) and later [Windows Insider Preview](https://insider.windows.com/getting-started/) builds.</span></span>

<span data-ttu-id="a6e34-105">Microsoft **Edge Devtools プロトコル** のバージョン0.2 には、EdgeHTML インストルメンテーションと基本的なリモートデバッグをテストするためのプレビューが用意されています。新しいスタンドアロンの [Microsoft Edge devtools プレビュー](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリ。</span><span class="sxs-lookup"><span data-stu-id="a6e34-105">Version 0.2 of the Microsoft **Edge DevTools Protocol** provides a preview for testing EdgeHTML instrumentation and basic remote debugging in the new standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app.</span></span> <span data-ttu-id="a6e34-106">そのため、 [windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763) またはそれ以降の [windows Insider Preview](https://insider.windows.com/getting-started/) ビルドを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e34-106">As such, it requires you to be running the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) or a later [Windows Insider Preview](https://insider.windows.com/getting-started/) build.</span></span>

<span data-ttu-id="a6e34-107">DevTools プロトコルの背後にあるゴールは、次の3つになります。</span><span class="sxs-lookup"><span data-stu-id="a6e34-107">The goals behind the DevTools Protocol are three-fold:</span></span>

 - <span data-ttu-id="a6e34-108">Microsoft Edge にアタッチするための DevTools アプリ用のパブリック API を提供する</span><span class="sxs-lookup"><span data-stu-id="a6e34-108">Provide a public API for our DevTools app to attach to Microsoft Edge</span></span>
 - <span data-ttu-id="a6e34-109">DevTools 機能の access を外部ツールクライアントに拡張する</span><span class="sxs-lookup"><span data-stu-id="a6e34-109">Expand access of DevTools functionality to external tooling clients</span></span>
 - <span data-ttu-id="a6e34-110">Microsoft Edge を実行している Windows 10 デバイスの範囲でリモートデバッグを有効にする</span><span class="sxs-lookup"><span data-stu-id="a6e34-110">Enable remote debugging across the range of Windows 10 devices running Microsoft Edge</span></span> 

<span data-ttu-id="a6e34-111">DevTools プロトコルのバージョン0.2 には、スタイルとレイアウトのための新しいドメインが含まれています (読み取り専用) デバッグと本体の Api に加えて、バージョン0.1 で導入されたコアスクリプトのデバッグ機能も含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6e34-111">Version 0.2 of the DevTools Protocol includes new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in Version 0.1.</span></span> <span data-ttu-id="a6e34-112">Edge の DevTools UI では、これは [**要素**](../../devtools-guide/elements.md)、 [**コンソール**](../../devtools-guide/console.md) 、 [**デバッガー**](../../devtools-guide/debugger.md)  パネルで利用できる機能に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a6e34-112">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../../devtools-guide/elements.md), [**Console**](../../devtools-guide/console.md) and [**Debugger**](../../devtools-guide/debugger.md)  panels.</span></span>
