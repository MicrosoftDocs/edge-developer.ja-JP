---
description: Microsoft Edge (Chromium) と Visual Studio コード
title: Visual Studio Code
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/12/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、デバッガー、webhint
ms.openlocfilehash: 94148864edbd43adbe2dc9f3d0c2fa0c1f7f0b43
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570740"
---
# Visual Studio Code

[Visual Studio コード](https://code.visualstudio.com/Docs)は、デスクトップで実行される強力なソースコードエディターであり、Windows、MacOS、Linux で利用できます。 JavaScript、TypeScript、および node.js の組み込みサポートが含まれているので、このボックスから直接、web 開発者に最適なツールです。 まだ使用していない場合は、[このページ](https://code.visualstudio.com/)にアクセスして Visual Studio のコードをダウンロードします。

## 拡張機能

<!-- We want to put something like the tiles for extensions VS Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page. I think it's a web page. I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->

以下で強調表示されている拡張機能を取得するには、 `Ctrl`  +  `Shift`  +  `X` `Command`  +  `Shift`  +  `X` VS コードの [拡張機能] (Windows または Mac の場合) に移動します。

市場で特定の拡張子を検索し、[**インストール**] を選択します。

![Microsoft Edge VS コード拡張用のデバッガーのインストール](./media/vscode-debugger-install.png)

## Microsoft Edge 用デバッガー

`console.log()`Microsoft Edge VS コード拡張機能[のデバッガー](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)を使って、フロントエンド JavaScript コードを行単位でデバッグし、 [Visual Studio コード](https://code.visualstudio.com/)でステートメントを直接表示します。

Microsoft [edge VS のデバッガー](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)を使って、microsoft Edge (EdgeHTML) と microsoft Edge (Chromium) の両方を起動またはアタッチします。 [このページ](./debugger-for-edge.md)では、VS コードからの Microsoft Edge のデバッグ方法と、サンプルの**起動. json**構成のチュートリアルについて説明します。

![Edge VS コード拡張のためのデバッガーの GIF](./media/debugger-for-edge.gif)

## Microsoft Edge の要素

Microsoft Edge VS コード拡張[用の要素](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools)を追加することで、ブラウザーの要素ツールを Visual Studio コード内から使うことができます。 起動またはアタッチのどちらの場合も、要素ツールは Microsoft Edge のインスタンスに接続され、ランタイム HTML 構造を表示し、レイアウトを変更したり、スタイル設定の問題を修正したりすることができます。

詳細については、[このページ](./elements-for-edge.md)をご覧ください。

![Edge VS コード拡張の要素の GIF。](./media/elements-for-edge.gif)

## web ヒント

カスタマイズ可能なカスタマイズされたカスタマイズされた機能[を使って](https://webhint.io)、アクセシビリティ、パフォーマンス、クロスブラウザーの互換性、PWA の互換性、およびサイトのセキュリティを向上させることができます。 ベストプラクティスと一般的なエラーについてコードを確認します。 このオープンソースプロジェクトは、最初に Microsoft Edge チームによって開発されたものであり、 [Openjs Foundation](https://openjsf.org/)に含まれています。 Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。

![Web ヒントとコード拡張のスクリーンショット](./media/webhint-extension.png)

[VS コードの webhint 拡張機能](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint)を追加して、HTML、CSS、JavaScript、TypeScript などの問題を特定して修正します。 ヒントはインライン下線として表示され、[問題] ウィンドウに集計されます。

詳細については、「 [Visual Studio コードでの webhint](./webhint.md)の使い方」を参照してください。
