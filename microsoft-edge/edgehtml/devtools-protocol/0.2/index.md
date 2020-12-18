---
description: Microsoft Edge DevTools プロトコル バージョン 0.2 のリリース ノート
title: Microsoft Edge DevTools プロトコル バージョン 0.2 リリース ノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 61d8f5b00dca3505594ca41db6c80c5ba4157092
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234400"
---
# <span data-ttu-id="59bf0-103">DevTools Protocol Version 0.2 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="59bf0-103">DevTools Protocol Version 0.2 Release Notes</span></span>

> [!NOTE]
> <span data-ttu-id="59bf0-104">Microsoft Edge DevTools プロトコルのバージョン 0.2 は [、Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) 以降の [Windows Insider Preview](https://insider.windows.com/getting-started/) ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="59bf0-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) and later [Windows Insider Preview](https://insider.windows.com/getting-started/) builds.</span></span>

<span data-ttu-id="59bf0-105">Microsoft **Edge DevTools プロトコル** のバージョン 0.2 では、新しいスタンドアロンの Microsoft Edge [DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリで EdgeHTML インストルメンテーションと基本的なリモート デバッグをテストするプレビューが提供されています。</span><span class="sxs-lookup"><span data-stu-id="59bf0-105">Version 0.2 of the Microsoft **Edge DevTools Protocol** provides a preview for testing EdgeHTML instrumentation and basic remote debugging in the new standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app.</span></span> <span data-ttu-id="59bf0-106">そのため、Windows [10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) 以降の [Windows Insider Preview](https://insider.windows.com/getting-started/) ビルドを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="59bf0-106">As such, it requires you to be running the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) or a later [Windows Insider Preview](https://insider.windows.com/getting-started/) build.</span></span>

<span data-ttu-id="59bf0-107">DevTools プロトコルの目標は次の 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="59bf0-107">The goals behind the DevTools Protocol are three-fold:</span></span>

 - <span data-ttu-id="59bf0-108">Microsoft Edge にアタッチする DevTools アプリのパブリック API を提供する</span><span class="sxs-lookup"><span data-stu-id="59bf0-108">Provide a public API for our DevTools app to attach to Microsoft Edge</span></span>
 - <span data-ttu-id="59bf0-109">DevTools 機能の外部ツール クライアントへのアクセスを拡張する</span><span class="sxs-lookup"><span data-stu-id="59bf0-109">Expand access of DevTools functionality to external tooling clients</span></span>
 - <span data-ttu-id="59bf0-110">Microsoft Edge を実行しているさまざまな Windows 10 デバイスでリモート デバッグを有効にする</span><span class="sxs-lookup"><span data-stu-id="59bf0-110">Enable remote debugging across the range of Windows 10 devices running Microsoft Edge</span></span> 

<span data-ttu-id="59bf0-111">DevTools プロトコルのバージョン 0.2 には、バージョン 0.1 で導入されたコア スクリプトデバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグとコンソール API 用の新しいドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="59bf0-111">Version 0.2 of the DevTools Protocol includes new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in Version 0.1.</span></span> <span data-ttu-id="59bf0-112">Edge DevTools UI では、これは要素パネル、コンソール パネル[\*\*\*\*](../../devtools-guide/elements.md)、デバッガー パネルで利用可能な[**機能**](../../devtools-guide/console.md)に[**変換**](../../devtools-guide/debugger.md)されます。</span><span class="sxs-lookup"><span data-stu-id="59bf0-112">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../../devtools-guide/elements.md), [**Console**](../../devtools-guide/console.md) and [**Debugger**](../../devtools-guide/debugger.md)  panels.</span></span>
