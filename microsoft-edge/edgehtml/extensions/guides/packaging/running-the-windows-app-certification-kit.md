---
description: Windows アプリ認定キットについて学習します。 これにより、拡張機能が公開される可能性が高くなります。
title: 拡張機能 - Windows アプリ認定キットの実行
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b8ca9117e3d35c01a0fbd2ec4defe38180b773cd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234922"
---
# <span data-ttu-id="a672c-105">Windows アプリ認定キットの実行</span><span class="sxs-lookup"><span data-stu-id="a672c-105">Running the Windows App Certification Kit</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="a672c-106">拡張機能が Microsoft Store に公開される可能性を高するには、Windows アプリ認定キットをインストールして [実行する必要があります](https://go.microsoft.com/fwlink/p/?LinkID=309666)。</span><span class="sxs-lookup"><span data-stu-id="a672c-106">To improve the chances of your extension getting published to the Microsoft Store, you'll need to install and run the [Windows App Certification Kit](https://go.microsoft.com/fwlink/p/?LinkID=309666).</span></span>
<span data-ttu-id="a672c-107">これにより、 [拡張機能パッケージに対](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit-tests) して一連のテストが実行され、Microsoft Store の準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a672c-107">This runs a [series of tests](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit-tests) on your extension package to ensure that it's ready for the Microsoft Store.</span></span>

> [!NOTE]
> <span data-ttu-id="a672c-108">Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="a672c-108">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="a672c-109">拡張機能を作成、パッケージ化、テストしたら、拡張機能の提出フォームで要求 [を送信してください](https://aka.ms/extension-request)。</span><span class="sxs-lookup"><span data-stu-id="a672c-109">Once you've created, packaged and tested your extension, please submit a request on our [extension submission form](https://aka.ms/extension-request).</span></span>

<span data-ttu-id="a672c-110">キットの使い方を確認する前に、次の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a672c-110">Before learning about how to use the kit, make sure you meet the following prerequisites:</span></span> 

- <span data-ttu-id="a672c-111">Windows 10 をインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a672c-111">You must install and run Windows 10.</span></span>
- <span data-ttu-id="a672c-112">Windows 10 用 Windows ソフトウェア開発キット (Windows SDK) に含まれる [Windows アプリ認定キット 10](https://go.microsoft.com/fwlink/p/?LinkID=309666) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a672c-112">You must install [Windows App Certification Kit version 10](https://go.microsoft.com/fwlink/p/?LinkID=309666), which is included in the Windows Software Development Kit (SDK) for Windows 10.</span></span>
- <span data-ttu-id="a672c-113">[開発用にデバイスを有効にする](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development)必要があります。</span><span class="sxs-lookup"><span data-stu-id="a672c-113">You must [enable your device for development](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development).</span></span>
- <span data-ttu-id="a672c-114">パッケージ化された拡張機能 [が必要](../packaging.md) です。</span><span class="sxs-lookup"><span data-stu-id="a672c-114">You must have a [packaged](../packaging.md) extension.</span></span>


<span data-ttu-id="a672c-115">前提条件を満たす場合は [、Windows アプリ](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit#validate-your-windows-app-using-the-windows-app-certification-kit-interactively) 認定キットを対話形式で使う方法、またはコマンド ラインを使って拡張機能をテストする方法について、Windows アプリ認定キットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a672c-115">If you meet the prerequisites, see the [Windows App Certification Kit](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit#validate-your-windows-app-using-the-windows-app-certification-kit-interactively) documentation for info on how to use the Windows App Certification Kit either interactively or with the command line to test your extension.</span></span>
