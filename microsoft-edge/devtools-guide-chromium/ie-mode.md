---
description: IE モードと Microsoft Edge (Chromium) DevTools
title: Internet Explorer モードと DevTools
author: robpaveza
ms.author: ropaveza
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、ie11、internet explorer 11、ie モード
ms.openlocfilehash: 18e5f029d277e446857ec48b9cf129149f219256
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570363"
---
# <span data-ttu-id="18f13-104">Internet Explorer モードと DevTools</span><span class="sxs-lookup"><span data-stu-id="18f13-104">Internet Explorer mode and the DevTools</span></span>

<span data-ttu-id="18f13-105">このドキュメントでは、Internet Explorer モード (IE モード) を Microsoft Edge (Chromium) DevTools と統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18f13-105">This document describes how Internet Explorer mode (IE mode) integrates with the Microsoft Edge (Chromium) DevTools.</span></span>

## <span data-ttu-id="18f13-106">IE モードについて</span><span class="sxs-lookup"><span data-stu-id="18f13-106">Understanding IE mode</span></span>

<span data-ttu-id="18f13-107">IE モードは、現在、Internet Explorer 11 でのみ動作する一連の web サイトを企業が指定するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="18f13-107">IE mode is a mechanism by which enterprises may specify a set of web sites that, until now, only worked in Internet Explorer 11.</span></span> <span data-ttu-id="18f13-108">Microsoft Edge (Chromium) でこれらの web サイトを表示すると、Internet Explorer 11 の完全なインスタンスが実行され、タブ内に表示されます。これにより、エンタープライズは、IE ドキュメントモード、ActiveX コントロール、および現在の最新の web ブラウザーとは互換性のないその他のレガシコンポーネントの互換性を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="18f13-108">When these web sites are viewed in Microsoft Edge (Chromium), a full instance of Internet Explorer 11 is running and rendered within the tab. This allows enterprises to manage compatibility for IE document modes, ActiveX controls, and other legacy components that are currently not compatible with any modern web browsers.</span></span>

<span data-ttu-id="18f13-109">IE モードでは、レンダリングプロセスはすべて、Internet Explorer 11 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="18f13-109">Within IE mode, the rendering process is entirely based in Internet Explorer 11.</span></span> <span data-ttu-id="18f13-110">Microsoft Edge (Chromium) manager プロセスは、レンダリングプロセスの有効期間を管理しますが、特定のサイトまたはアプリケーションのタブの有効期間に制約されます。</span><span class="sxs-lookup"><span data-stu-id="18f13-110">The Microsoft Edge (Chromium) manager process manages the lifetime of the rendering process, but it is constrained to the tab's lifetime on a given site or application.</span></span> <span data-ttu-id="18f13-111">タブが IE モードでレンダリングされている場合、指定したタブのアドレスバーにバッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="18f13-111">When a tab is rendering in IE mode, a badge appears in the address bar for the given tab:</span></span>

![アドレスバーの IE モードバッジ](./media/ie-mode-badge.png)

<span data-ttu-id="18f13-113">IE モードは現在、Windows 10 バージョン 1903 (2019 の更新プログラム) で使用できますが、サポートされているすべての Windows プラットフォームに近い将来利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="18f13-113">IE mode is currently available on Windows 10 Version 1903 (May 2019 Update) but is coming soon to all supported Windows platforms.</span></span>

## <span data-ttu-id="18f13-114">IE モードのタブで DevTools を起動する</span><span class="sxs-lookup"><span data-stu-id="18f13-114">Launching the DevTools on a tab in IE mode</span></span>

<span data-ttu-id="18f13-115">IE モードで web サイトのドキュメントモードを表示しようとしている場合は、アドレスバーのバッジをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18f13-115">If you are trying to view the document mode of a web site in IE mode, you can click on the badge in the address bar.</span></span>

![IE モードバッジでドキュメントモードを表示する](./media/ie-mode-badge-doc-mode.png)

<span data-ttu-id="18f13-117">IE モードのタブでは、DevTools は動作しません。</span><span class="sxs-lookup"><span data-stu-id="18f13-117">While on a tab in IE mode, the DevTools will not work.</span></span> <span data-ttu-id="18f13-118">`F12`または、 `Ctrl` + `Shift` + `I` 次のようなメッセージが表示された Microsoft Edge (Chromium) devtools の空のインスタンスが起動します。 "開発者ツールは Internet Explorer モードでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="18f13-118">Pressing `F12` or `Ctrl`+`Shift`+`I` will only launch a blank instance of the Microsoft Edge (Chromium) DevTools with a message that reads: "Developer Tools are not available in Internet Explorer mode.</span></span> <span data-ttu-id="18f13-119">ページをデバッグするには、Internet Explorer 11 でページを開きます。</span><span class="sxs-lookup"><span data-stu-id="18f13-119">To debug the page, open it in Internet Explorer 11."</span></span> <span data-ttu-id="18f13-120">[**ソースの表示**] は、メモ帳を起動し、IE モードのコンテキストメニューに [要素の**検査**] は表示されません。</span><span class="sxs-lookup"><span data-stu-id="18f13-120">**View Source** will launch Notepad and **Inspect Element** will not be visible in the context menu in IE mode.</span></span>

<span data-ttu-id="18f13-121">これは、レンダリングエンジンが IE モードで Chromium から Internet Explorer 11 に切り替えたときに、DevTools (Network、Performance tools など) のいくつかのコンポーネントが壊れる場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="18f13-121">This is because a number of components in the DevTools (like the Network and Performance tools) would break when the rendering engine switches from Chromium to Internet Explorer 11 in IE mode.</span></span> <span data-ttu-id="18f13-122">フィードバックを送信するには、アイコンをクリックし `:)` ます。</span><span class="sxs-lookup"><span data-stu-id="18f13-122">To give us feedback, click the `:)` icon.</span></span>

![IE モードで起動した DevTools](./media/ie-mode-devtools.png)

<span data-ttu-id="18f13-124">Internet Explorer 11 ベースの web サイトまたはアプリケーションを開発またはメンテナンスする場合は、Internet Explorer 11 で同じページに移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18f13-124">If you are developing or maintaining an Internet Explorer 11-based web site or application, we recommend navigating to the same page in Internet Explorer 11.</span></span> <span data-ttu-id="18f13-125">Windows 10 では、[Windows アクセサリ] の下にある [スタート] メニューで Internet Explorer 11 のショートカットを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="18f13-125">On Windows 10, you can find the shortcut for Internet Explorer 11 on the Start Menu underneath Windows Accessories.</span></span> <span data-ttu-id="18f13-126">Windows 7 では、[スタート] メニューの [Internet Explorer 11] を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="18f13-126">On Windows 7, you can find Internet Explorer 11 on the main Start Menu.</span></span> <span data-ttu-id="18f13-127">次に、 `F12` コンテキストメニューの [**要素の検査**] をクリックまたはクリックして、Internet Explorer の devtools を起動します。</span><span class="sxs-lookup"><span data-stu-id="18f13-127">You can then launch the Internet Explorer DevTools by pressing `F12` or clicking **Inspect element** in the context menu.</span></span> <span data-ttu-id="18f13-128">これらのツールの使用方法の詳細については、[ここ](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85))をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="18f13-128">To learn more about how to use those tools, click [here](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85)).</span></span>

## <span data-ttu-id="18f13-129">リモートデバッグと IE モード</span><span class="sxs-lookup"><span data-stu-id="18f13-129">Remote debugging and IE mode</span></span>

<span data-ttu-id="18f13-130">リモートデバッグが有効になっている Microsoft Edge (Chromium) を起動することができます。これは、通常、Visual Studio や VS コード起動 Edge などのツールがコマンドラインから実行される方法です。</span><span class="sxs-lookup"><span data-stu-id="18f13-130">You can launch Microsoft Edge (Chromium) with remote debugging enabled, which is typically how tools like Visual Studio or VS Code launch Edge, from the command line:</span></span>

`start msedge --remote-debugging-port=9222`

<span data-ttu-id="18f13-131">このコマンドライン引数で Microsoft Edge (Chromium) を起動すると、IE モードは利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="18f13-131">When Microsoft Edge (Chromium) is launched with this command line argument, IE mode will be unavailable.</span></span> <span data-ttu-id="18f13-132">ただし、IE モードに含まれている web サイトまたはアプリケーションに移動することはできますが、Internet Explorer 11 ではなく Chromium 経由でコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="18f13-132">You can still navigate to web sites or applications that would otherwise be in IE mode but the content will render via Chromium, not Internet Explorer 11.</span></span> <span data-ttu-id="18f13-133">ActiveX コントロールなど、IE11 に依存しているページの部分が正しく表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="18f13-133">You can expect that the parts of those pages that rely on IE11, like ActiveX controls, will not render correctly.</span></span> <span data-ttu-id="18f13-134">IE モードのバッジはアドレスバーに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="18f13-134">The IE mode badge will no longer appear in the address bar.</span></span>

<span data-ttu-id="18f13-135">IE モードは、Microsoft Edge (Chromium) を完全に終了するまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="18f13-135">IE mode will remain unavailable until you completely close Microsoft Edge (Chromium).</span></span>