---
description: Windows アプリ認定キットについて説明します。 これにより、内線番号が公開される可能性が高くなります。
title: 拡張機能-Windows アプリ認定キットを実行しています
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 2577d4e5d05dbe55e57b046d001d122a687f87ce
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569447"
---
# <span data-ttu-id="16604-105">Windows アプリ認定キットを実行する</span><span class="sxs-lookup"><span data-stu-id="16604-105">Running the Windows App Certification Kit</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="16604-106">拡張機能が Microsoft ストアに公開される可能性を向上させるには、 [Windows アプリ認定キット](https://go.microsoft.com/fwlink/p/?LinkID=309666)をインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16604-106">To improve the chances of your extension getting published to the Microsoft Store, you'll need to install and run the [Windows App Certification Kit](https://go.microsoft.com/fwlink/p/?LinkID=309666).</span></span>
<span data-ttu-id="16604-107">これにより、拡張パッケージで[一連のテスト](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit-tests)が実行され、Microsoft ストアの準備ができていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="16604-107">This runs a [series of tests](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit-tests) on your extension package to ensure that it's ready for the Microsoft Store.</span></span>

> [!NOTE]
> <span data-ttu-id="16604-108">Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="16604-108">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="16604-109">お客様の内線番号の作成、パッケージ化、テストが完了したら、[延長申請フォーム](https://aka.ms/extension-request)でリクエストを送信してください。</span><span class="sxs-lookup"><span data-stu-id="16604-109">Once you've created, packaged and tested your extension, please submit a request on our [extension submission form](https://aka.ms/extension-request).</span></span>

<span data-ttu-id="16604-110">キットの使用方法について学習する前に、次の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="16604-110">Before learning about how to use the kit, make sure you meet the following prerequisites:</span></span> 

- <span data-ttu-id="16604-111">Windows 10 をインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16604-111">You must install and run Windows 10.</span></span>
- <span data-ttu-id="16604-112">Windows 10 用 Windows ソフトウェア開発キット (Windows SDK) に含まれる [Windows アプリ認定キット 10](https://go.microsoft.com/fwlink/p/?LinkID=309666) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16604-112">You must install [Windows App Certification Kit version 10](https://go.microsoft.com/fwlink/p/?LinkID=309666), which is included in the Windows Software Development Kit (SDK) for Windows 10.</span></span>
- <span data-ttu-id="16604-113">[開発用にデバイスを有効にする](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development)必要があります。</span><span class="sxs-lookup"><span data-stu-id="16604-113">You must [enable your device for development](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development).</span></span>
- <span data-ttu-id="16604-114">[パッケージ化](../packaging.md)された拡張機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="16604-114">You must have a [packaged](../packaging.md) extension.</span></span>


<span data-ttu-id="16604-115">前提条件を満たしている場合は[、windows アプリ](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit#validate-your-windows-app-using-the-windows-app-certification-kit-interactively)認定キットのマニュアルに記載されている、Windows アプリ認定キットを対話的に使用する方法、またはコマンドラインで拡張機能をテストする方法については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16604-115">If you meet the prerequisites, see the [Windows App Certification Kit](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit#validate-your-windows-app-using-the-windows-app-certification-kit-interactively) documentation for info on how to use the Windows App Certification Kit either interactively or with the command line to test your extension.</span></span>
