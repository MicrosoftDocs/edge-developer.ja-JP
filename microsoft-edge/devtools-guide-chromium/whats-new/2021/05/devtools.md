---
description: '[その他のツール] ボタン、DevTools 拡張機能の使用を開始するためのコンテキスト内のドキュメント、コンソールでのスクリーン リーダーのサポートの増加など。'
title: DevTools の新機能 (Microsoft Edge 92)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ebd512800b8e55b5e9c0001c314a7c08fd242d5d
ms.sourcegitcommit: 30817cd9ae187a716d14d06962eb23b32dd54548
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "11590877"
---
# <a name="whats-new-in-devtools-microsoft-edge-92"></a><span data-ttu-id="0dcb0-104">DevTools の新機能 (Microsoft Edge 92)</span><span class="sxs-lookup"><span data-stu-id="0dcb0-104">What's New In DevTools (Microsoft Edge 92)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

> [!TIP]
> <span data-ttu-id="0dcb0-105">**Microsoft ビルド 2021 会議**は 5 月 25 日から 27 日に開催されました。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-105">The **Microsoft Build 2021** conference was on May 25-27.</span></span>  <span data-ttu-id="0dcb0-106">DevTools の更新プログラムに関するビルドのビデオを次[に示します。Microsoft Edge |プラットフォームの状態][YoutubeEdgeStateOfThePlatform]- 開発者Microsoft Edgeツールを使用して、説得力のある一貫性のあるプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-106">Here's a video from Build about the updates to DevTools: [Microsoft Edge | State of the Platform][YoutubeEdgeStateOfThePlatform] - Microsoft Edge brings a compelling and consistent platform with tools for developers.</span></span>  <span data-ttu-id="0dcb0-107">従来のブラウザーがサポートから段階的に切り離される中、エッジは近い間に Microsoft からサポートされている唯一のブラウザー Windows 10。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-107">As our legacy browsers phase out of support, Edge will soon be the only supported browser from Microsoft on Windows 10.</span></span>  <span data-ttu-id="0dcb0-108">エッジ プラットフォーム、ツール、および Web アプリ全体で最新の情報を確認するには、ご参加ください。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-108">Join us to learn about the latest across the Edge platform, tools, and web apps.</span></span>


## <a name="the-close-button-is-no-longer-hidden-when-devtools-is-narrow"></a><span data-ttu-id="0dcb0-109">DevTools が狭いときに [閉じる] ボタンが非表示にな</span><span class="sxs-lookup"><span data-stu-id="0dcb0-109">The Close button is no longer hidden when DevTools is narrow</span></span>

<!-- Title: DevTools is now easier to close -->  
<!-- Subtitle: The Close button in DevTools is always displayed, even when DevTools is docked to the right and the DevTools viewport is narrow. -->  

<span data-ttu-id="0dcb0-110">バージョン 91 Microsoft Edge以前では、DevTools\*\*\*\* ビューポートが狭い場合、DevTools を閉じる [閉じる] ボタンは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-110">In Microsoft Edge version 91 or earlier, the **Close** button to close DevTools isn't displayed when the DevTools viewport is narrow.</span></span>  <span data-ttu-id="0dcb0-111">バージョン 92 Microsoft Edge DevTools\*\*\*\* の [閉じる] ボタンは、DevTools ビューポートの幅に関係なく常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-111">In Microsoft Edge version 92, the **Close** button in the DevTools is always present, regardless of the DevTools viewport width.</span></span>

:::image type="complex" source="../../media/2021/05/close-devtools-button-always-displayed.msft.png" alt-text="ビューポートが狭い場合でも、[DevTools を閉じる] ボタンが表示される" lightbox="../../media/2021/05/close-devtools-button-always-displayed.msft.png":::
   <span data-ttu-id="0dcb0-113">ビューポート **が** 狭い場合でも、[DevTools を閉じる] ボタンが表示される</span><span class="sxs-lookup"><span data-stu-id="0dcb0-113">The **Close** DevTools button is now present even when the viewport is narrow</span></span>  
:::image-end:::  


## <a name="add-tools-quickly-with-the-new-more-tools-button"></a><span data-ttu-id="0dcb0-114">新しい [その他のツール] ボタンでツールをすばやく追加する</span><span class="sxs-lookup"><span data-stu-id="0dcb0-114">Add tools quickly with the new More Tools button</span></span>

<!-- Title: Add tools quickly with the new More Tools button -->  
<!-- Subtitle: Learn about a new convenient way to open tools in Microsoft Edge DevTools. -->  

<span data-ttu-id="0dcb0-115">DevTools で他のツールを開くMicrosoft Edge新しい方法があります。[その他の**ツール**] ( `+` ) メニュー。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-115">There's a new way to open more tools in Microsoft Edge DevTools: the **More Tools** (`+`) menu.</span></span> <span data-ttu-id="0dcb0-116">[ **その他のツール** ] メニューは、メイン パネルのツールバーと引き出しのツールバーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-116">The **More Tools** menu appears on the toolbar in the main panel and on the toolbar of the drawer.</span></span> <span data-ttu-id="0dcb0-117">[その他のツール] メニューから **ツールを選択** すると、ツール がツール バーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-117">Selecting a tool from the **More Tools** menu adds the tool to the toolbar.</span></span>

<span data-ttu-id="0dcb0-118">いずれかのツールバーのタブの順序を変更するには、タブを選択してドラッグします。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-118">To reorder the tabs on either toolbar, select and drag the tabs.</span></span>  

<span data-ttu-id="0dcb0-119">[**その他のツール**] メニューは、Microsoft Edgeバージョン 89 の実験として使用できます。現在は常に存在しています。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-119">The **More Tools** menu was available as an experiment in Microsoft Edge version 89, and is now always present.</span></span>

:::image type="complex" source="../../media/2021/05/more-tools-button.msft.png" alt-text="上部のツールバーと引き出しツールバーの [その他のツール] ボタン" lightbox="../../media/2021/05/more-tools-button.msft.png":::
   <span data-ttu-id="0dcb0-121">上部 **のツールバーと引** き出しツールバーの [その他のツール] ボタン</span><span class="sxs-lookup"><span data-stu-id="0dcb0-121">The **More Tools** button on the upper toolbar and drawer toolbar</span></span>
:::image-end:::  

:::image type="complex" source="../../media/2021/05/more-tools-menu.msft.png" alt-text="[その他のツール] メニュー" lightbox="../../media/2021/05/more-tools-menu.msft.png":::
   <span data-ttu-id="0dcb0-123">[ **その他のツール]** メニュー</span><span class="sxs-lookup"><span data-stu-id="0dcb0-123">The **More Tools** menu</span></span>
:::image-end:::  


## <a name="improvements-for-hovering-selecting-and-closing-tools"></a><span data-ttu-id="0dcb0-124">ホバー、選択、および終了ツールの機能強化</span><span class="sxs-lookup"><span data-stu-id="0dcb0-124">Improvements for hovering, selecting, and closing tools</span></span>

<!-- Title: Improvements to tab interactions -->
<!-- Subtitle: Interactions related to hovering, selecting, and closing tools are more predictable. -->

<span data-ttu-id="0dcb0-125">ツールを誤って閉じる可能性を減らすために、各ツールのタブが再フォーマットされています。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-125">Tabs for each tool have been reformatted to reduce the chance of accidentally closing a tool.</span></span>  <span data-ttu-id="0dcb0-126">メイン ツールバーの各タブと引き出しのツールバーで、次の項目を追加しました。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-126">On each tab in the main toolbar and in the toolbar of the drawer, we added:</span></span>
*  <span data-ttu-id="0dcb0-127">タブの周りの間隔。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-127">Spacing around the tab.</span></span>
*  <span data-ttu-id="0dcb0-128">タブの閉じる ( `x` ) ボタンの周囲の間隔。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-128">Spacing around the close (`x`) button in the tab.</span></span>
*  <span data-ttu-id="0dcb0-129">タブにカーソルを合わせると、背景色が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-129">A background color when hovering over the tab.</span></span>
*  <span data-ttu-id="0dcb0-130">タブの閉じる ( `x` ) ボタンのヒント。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-130">A tooltip for the close (`x`) button of the tab.</span></span>
*  <span data-ttu-id="0dcb0-131">タブの閉じる ( `x` ) ボタンのコントラストが高くなります。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-131">Higher contrast for the close (`x`) button of the tab.</span></span>

<span data-ttu-id="0dcb0-132">たとえば、パフォーマンス ツールでネットワーク\*\*\*\* ツールのタブにカーソルを合\*\*\*\* わせると、ネットワーク ツールが誤って閉じ込めなく場合に**役立**ちます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-132">For example, when you are in the **Performance** tool and you hover over the **Network** tool's tab, these improvements help prevent accidentally closing the **Network** tool.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-before.msft.png" alt-text="再フォーマットする前のタブ" lightbox="../../media/2021/05/hovering-on-tool-tab-before.msft.png":::
           <span data-ttu-id="0dcb0-134">再フォーマットする前のタブ</span><span class="sxs-lookup"><span data-stu-id="0dcb0-134">Tabs before reformatting</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-after.msft.png" alt-text="再フォーマット後のタブ" lightbox="../../media/2021/05/hovering-on-tool-tab-after.msft.png":::
           <span data-ttu-id="0dcb0-136">再フォーマット後のタブ</span><span class="sxs-lookup"><span data-stu-id="0dcb0-136">Tabs after reformatting</span></span> :::image-end:::
    :::column-end:::
:::row-end:::

<span data-ttu-id="0dcb0-137">これらの機能強化は、タブが狭く、誤って閉じやすくなる、ローカライズされた DevTools のユーザーにとって特に重要です。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-137">These improvements are especially relevant for users of localized DevTools, in which the tabs may be narrower and easier to accidentally close.</span></span>

:::image type="complex" source="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png" alt-text="絞り込みタブを含むローカライズされた DevTools" lightbox="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png":::
   <span data-ttu-id="0dcb0-139">絞り込みタブを含むローカライズされた DevTools</span><span class="sxs-lookup"><span data-stu-id="0dcb0-139">Localized DevTools with narrow tabs</span></span>
:::image-end:::

<span data-ttu-id="0dcb0-140">また、メイン ツールバーと引き出しツール バーに [その[](#add-tools-quickly-with-the-new-more-tools-button)他のツール] メニューを追加することで、閉じたツールを簡単に再追加しました。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-140">We also made it easier to re-add a tool that you closed by adding a [More Tools menu](#add-tools-quickly-with-the-new-more-tools-button) to the main toolbar and drawer toolbar.</span></span>


## <a name="better-support-for-screen-readers-in-the-console"></a><span data-ttu-id="0dcb0-141">コンソールでのスクリーン リーダーのサポートの向上</span><span class="sxs-lookup"><span data-stu-id="0dcb0-141">Better support for screen readers in the Console</span></span>

<!-- Title: Better screen reader support in the Console -->
<!-- Subtitle: Assistive technologies can now announce autocomplete suggestions and evaluated expressions in the Console. -->

<span data-ttu-id="0dcb0-142">バージョン 92 Microsoft Edge以前は、コンソールで\*\*\*\* スクリーン リーダーなどの支援テクノロジがオートコンプリートの提案や評価された式の結果を発表してくなかった。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-142">Prior to Microsoft Edge version 92, in the **Console**, assistive technologies such as screen readers didn't announce autocomplete suggestions or the results of evaluated expressions.</span></span> <span data-ttu-id="0dcb0-143">これで修正されました。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-143">This has been fixed now.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png" alt-text="コンソールで、スクリーン リーダーが現在選択されているオートコンプリート候補を発表する" lightbox="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png":::
           <span data-ttu-id="0dcb0-145">コンソールで **、** スクリーン リーダーが現在選択されているオートコンプリート候補を発表する</span><span class="sxs-lookup"><span data-stu-id="0dcb0-145">In the **Console**, screen readers now announce the currently selected autocomplete suggestion</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png" alt-text="コンソールで、スクリーン リーダーは評価された式の結果をアナウンスします。" lightbox="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png":::
           <span data-ttu-id="0dcb0-147">コンソールで **、** スクリーン リーダーが評価された式の結果をアナウンスする</span><span class="sxs-lookup"><span data-stu-id="0dcb0-147">In the **Console**, screen readers now announce the result of an evaluated expression</span></span> :::image-end:::
    :::column-end:::
:::row-end:::


## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-118"></a><span data-ttu-id="0dcb0-148">Microsoft Edgeバージョン 1.1.8 Visual Studio Code開発者向けツール</span><span class="sxs-lookup"><span data-stu-id="0dcb0-148">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.8</span></span>

<span data-ttu-id="0dcb0-149">Microsoft Edge[コード][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]Visual Studio Codeバージョン 1.1.8 Microsoft Visual Studio開発者ツールは、前のリリース以降に次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-149">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.8 for Microsoft Visual Studio Code has the following changes since the previous release.</span></span>  <span data-ttu-id="0dcb0-150">Microsoft Visual Studio Code では拡張機能を自動的に更新しています。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-150">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="0dcb0-151">バージョン 1.1.8 に手動で更新するには、[拡張機能を手動で更新 [する] に移動します][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-151">To manually update to version 1.1.8, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  

<span data-ttu-id="0dcb0-152">問題をファイルし[、vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools]GitHubできます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-152">You can file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

### <a name="in-context-documentation-and-ui-to-make-it-easier-to-use-the-devtools-extension"></a><span data-ttu-id="0dcb0-153">DevTools 拡張機能を使いやすくするためのコンテキスト内のドキュメントと UI</span><span class="sxs-lookup"><span data-stu-id="0dcb0-153">In-context documentation and UI to make it easier to use the DevTools extension</span></span>

<!-- Title: In-context documentation and UI make it easier to get started using the Developer Tools extension -->  
<!-- Subtitle: The Microsoft Edge Developer Tools for Visual Studio Code extension now presents helpful text, buttons, and links, and opens a documentation page with guidance on how to get started. -->  

<span data-ttu-id="0dcb0-154">[Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]拡張機能のバージョン 1.1.8 では、手順、ボタン、リンク、およびドキュメント ページを提示することで、Microsoft Edge の新しいインスタンスを簡単に開始できます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-154">Version 1.1.8 of the [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension now features a simpler way to start a new instance of Microsoft Edge, by presenting instructions, buttons, links, and a documentation page to guide you.</span></span>

*  <span data-ttu-id="0dcb0-155">Visual Studio Code の [アクティビティ バー] で\*\*\*\*\*\*[Microsoft Edge\*\*ツール] ボタンを選択すると **、[Microsoft Edge**ツール: ターゲット] パネルに、空白のパネルではなく説明テキスト、ボタン、およびリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-155">When you select the **Microsoft Edge Tools** button in the **Activity Bar** of Visual Studio Code, the **Microsoft Edge Tools: Targets** panel now presents explanatory text, buttons, and links to guide you, instead of a blank panel.</span></span>

*  <span data-ttu-id="0dcb0-156">Visual Studio Code 内から Microsoft Edge の新しいインスタンスを開いた場合、Microsoft Edge には、空白のページではなく、Developer Tools 拡張機能の使い方を説明するスタート ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-156">When you open a new instance of Microsoft Edge from within Visual Studio Code, Microsoft Edge now shows a start page that explains how to use the Developer Tools extension, instead of a blank page.</span></span>

*  <span data-ttu-id="0dcb0-157">**[Microsoft Edge: ターゲット]** パネルに [launch.js\*\*\*\* を生成する] ボタンと手順が表示され、プロジェクトを起動してデバッグMicrosoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-157">The **Microsoft Edge Tools: Targets** panel now has a **Generate launch.json** button and instructions, to help launch your project for debugging in Microsoft Edge.</span></span>

<span data-ttu-id="0dcb0-158">詳細については、「ツールを使用 [する」に移動します][GithubIoDevToolsUsing]。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-158">For more information, navigate to [Using the tools][GithubIoDevToolsUsing].</span></span>


## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="0dcb0-159">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="0dcb0-159">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="0dcb0-160">Windows、Linux、または macOS を使用している場合は、 既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-160">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="0dcb0-161">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-161">The preview channels give you access to the latest DevTools features.</span></span>  


## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="0dcb0-162">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="0dcb0-162">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubIoDevToolsUsing]: https://microsoft.github.io/vscode-edge-devtools/using.html "ツール の使用|GitHub"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge開発者向けツール Visual Studio Code |Visual StudioMarketplace"  

[YoutubeEdgeStateOfThePlatform]: https://www.youtube.com/watch?v=sU0WRZ0kkNo "Microsoft Edge: プラットフォーム の状態|YouTube"

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0dcb0-170">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0dcb0-170">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
