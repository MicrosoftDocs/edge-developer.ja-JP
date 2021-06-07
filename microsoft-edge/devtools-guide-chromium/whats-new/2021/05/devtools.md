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
# <a name="whats-new-in-devtools-microsoft-edge-92"></a>DevTools の新機能 (Microsoft Edge 92)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

> [!TIP]
> **Microsoft ビルド 2021 会議**は 5 月 25 日から 27 日に開催されました。  DevTools の更新プログラムに関するビルドのビデオを次[に示します。Microsoft Edge |プラットフォームの状態][YoutubeEdgeStateOfThePlatform]- 開発者Microsoft Edgeツールを使用して、説得力のある一貫性のあるプラットフォームを提供します。  従来のブラウザーがサポートから段階的に切り離される中、エッジは近い間に Microsoft からサポートされている唯一のブラウザー Windows 10。  エッジ プラットフォーム、ツール、および Web アプリ全体で最新の情報を確認するには、ご参加ください。


## <a name="the-close-button-is-no-longer-hidden-when-devtools-is-narrow"></a>DevTools が狭いときに [閉じる] ボタンが非表示にな

<!-- Title: DevTools is now easier to close -->  
<!-- Subtitle: The Close button in DevTools is always displayed, even when DevTools is docked to the right and the DevTools viewport is narrow. -->  

バージョン 91 Microsoft Edge以前では、DevTools**** ビューポートが狭い場合、DevTools を閉じる [閉じる] ボタンは表示されません。  バージョン 92 Microsoft Edge DevTools**** の [閉じる] ボタンは、DevTools ビューポートの幅に関係なく常に表示されます。

:::image type="complex" source="../../media/2021/05/close-devtools-button-always-displayed.msft.png" alt-text="ビューポートが狭い場合でも、[DevTools を閉じる] ボタンが表示される" lightbox="../../media/2021/05/close-devtools-button-always-displayed.msft.png":::
   ビューポート **が** 狭い場合でも、[DevTools を閉じる] ボタンが表示される  
:::image-end:::  


## <a name="add-tools-quickly-with-the-new-more-tools-button"></a>新しい [その他のツール] ボタンでツールをすばやく追加する

<!-- Title: Add tools quickly with the new More Tools button -->  
<!-- Subtitle: Learn about a new convenient way to open tools in Microsoft Edge DevTools. -->  

DevTools で他のツールを開くMicrosoft Edge新しい方法があります。[その他の**ツール**] ( `+` ) メニュー。 [ **その他のツール** ] メニューは、メイン パネルのツールバーと引き出しのツールバーに表示されます。 [その他のツール] メニューから **ツールを選択** すると、ツール がツール バーに追加されます。

いずれかのツールバーのタブの順序を変更するには、タブを選択してドラッグします。  

[**その他のツール**] メニューは、Microsoft Edgeバージョン 89 の実験として使用できます。現在は常に存在しています。

:::image type="complex" source="../../media/2021/05/more-tools-button.msft.png" alt-text="上部のツールバーと引き出しツールバーの [その他のツール] ボタン" lightbox="../../media/2021/05/more-tools-button.msft.png":::
   上部 **のツールバーと引** き出しツールバーの [その他のツール] ボタン
:::image-end:::  

:::image type="complex" source="../../media/2021/05/more-tools-menu.msft.png" alt-text="[その他のツール] メニュー" lightbox="../../media/2021/05/more-tools-menu.msft.png":::
   [ **その他のツール]** メニュー
:::image-end:::  


## <a name="improvements-for-hovering-selecting-and-closing-tools"></a>ホバー、選択、および終了ツールの機能強化

<!-- Title: Improvements to tab interactions -->
<!-- Subtitle: Interactions related to hovering, selecting, and closing tools are more predictable. -->

ツールを誤って閉じる可能性を減らすために、各ツールのタブが再フォーマットされています。  メイン ツールバーの各タブと引き出しのツールバーで、次の項目を追加しました。
*  タブの周りの間隔。
*  タブの閉じる ( `x` ) ボタンの周囲の間隔。
*  タブにカーソルを合わせると、背景色が表示されます。
*  タブの閉じる ( `x` ) ボタンのヒント。
*  タブの閉じる ( `x` ) ボタンのコントラストが高くなります。

たとえば、パフォーマンス ツールでネットワーク**** ツールのタブにカーソルを合**** わせると、ネットワーク ツールが誤って閉じ込めなく場合に**役立**ちます。

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-before.msft.png" alt-text="再フォーマットする前のタブ" lightbox="../../media/2021/05/hovering-on-tool-tab-before.msft.png":::
           再フォーマットする前のタブ :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-after.msft.png" alt-text="再フォーマット後のタブ" lightbox="../../media/2021/05/hovering-on-tool-tab-after.msft.png":::
           再フォーマット後のタブ :::image-end:::
    :::column-end:::
:::row-end:::

これらの機能強化は、タブが狭く、誤って閉じやすくなる、ローカライズされた DevTools のユーザーにとって特に重要です。

:::image type="complex" source="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png" alt-text="絞り込みタブを含むローカライズされた DevTools" lightbox="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png":::
   絞り込みタブを含むローカライズされた DevTools
:::image-end:::

また、メイン ツールバーと引き出しツール バーに [その[](#add-tools-quickly-with-the-new-more-tools-button)他のツール] メニューを追加することで、閉じたツールを簡単に再追加しました。


## <a name="better-support-for-screen-readers-in-the-console"></a>コンソールでのスクリーン リーダーのサポートの向上

<!-- Title: Better screen reader support in the Console -->
<!-- Subtitle: Assistive technologies can now announce autocomplete suggestions and evaluated expressions in the Console. -->

バージョン 92 Microsoft Edge以前は、コンソールで**** スクリーン リーダーなどの支援テクノロジがオートコンプリートの提案や評価された式の結果を発表してくなかった。 これで修正されました。

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png" alt-text="コンソールで、スクリーン リーダーが現在選択されているオートコンプリート候補を発表する" lightbox="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png":::
           コンソールで **、** スクリーン リーダーが現在選択されているオートコンプリート候補を発表する :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png" alt-text="コンソールで、スクリーン リーダーは評価された式の結果をアナウンスします。" lightbox="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png":::
           コンソールで **、** スクリーン リーダーが評価された式の結果をアナウンスする :::image-end:::
    :::column-end:::
:::row-end:::


## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-118"></a>Microsoft Edgeバージョン 1.1.8 Visual Studio Code開発者向けツール

Microsoft Edge[コード][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]Visual Studio Codeバージョン 1.1.8 Microsoft Visual Studio開発者ツールは、前のリリース以降に次の変更を加えます。  Microsoft Visual Studio Code では拡張機能を自動的に更新しています。  バージョン 1.1.8 に手動で更新するには、[拡張機能を手動で更新 [する] に移動します][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。  

問題をファイルし[、vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools]GitHubできます。  

### <a name="in-context-documentation-and-ui-to-make-it-easier-to-use-the-devtools-extension"></a>DevTools 拡張機能を使いやすくするためのコンテキスト内のドキュメントと UI

<!-- Title: In-context documentation and UI make it easier to get started using the Developer Tools extension -->  
<!-- Subtitle: The Microsoft Edge Developer Tools for Visual Studio Code extension now presents helpful text, buttons, and links, and opens a documentation page with guidance on how to get started. -->  

[Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]拡張機能のバージョン 1.1.8 では、手順、ボタン、リンク、およびドキュメント ページを提示することで、Microsoft Edge の新しいインスタンスを簡単に開始できます。

*  Visual Studio Code の [アクティビティ バー] で******[Microsoft Edge**ツール] ボタンを選択すると **、[Microsoft Edge**ツール: ターゲット] パネルに、空白のパネルではなく説明テキスト、ボタン、およびリンクが表示されます。

*  Visual Studio Code 内から Microsoft Edge の新しいインスタンスを開いた場合、Microsoft Edge には、空白のページではなく、Developer Tools 拡張機能の使い方を説明するスタート ページが表示されます。

*  **[Microsoft Edge: ターゲット]** パネルに [launch.js**** を生成する] ボタンと手順が表示され、プロジェクトを起動してデバッグMicrosoft Edge。

詳細については、「ツールを使用 [する」に移動します][GithubIoDevToolsUsing]。


## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows、Linux、または macOS を使用している場合は、 既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]の使用を検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  


## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubIoDevToolsUsing]: https://microsoft.github.io/vscode-edge-devtools/using.html "ツール の使用|GitHub"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge開発者向けツール Visual Studio Code |Visual StudioMarketplace"  

[YoutubeEdgeStateOfThePlatform]: https://www.youtube.com/watch?v=sU0WRZ0kkNo "Microsoft Edge: プラットフォーム の状態|YouTube"

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
