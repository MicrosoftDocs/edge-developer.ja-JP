---
description: Visual Studio コードでの webhint の使い方
title: webhint VS コード拡張
author: hxlnt
ms.author: raweil
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、vs コード、visual studio コード、web ヒント
ms.openlocfilehash: d3102bf4d8d4a8bba9225d8d3f68432197f775ac
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570723"
---
# webhint VS コード拡張

カスタマイズ可能なカスタマイズされたカスタマイズされた機能[を使って](https://webhint.io)、アクセシビリティ、パフォーマンス、クロスブラウザーの互換性、PWA の互換性、およびサイトのセキュリティを向上させることができます。 ベストプラクティスと一般的なエラーについてコードを確認します。 このオープンソースプロジェクトは、最初に Microsoft Edge チームによって開発されたものであり、 [Openjs Foundation](https://openjsf.org/)に含まれています。 Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。

![Web ヒントとコード拡張のスクリーンショット](./media/webhint-extension.png)

[VS コードの webhint 拡張機能](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint)を追加して、HTML、CSS、JavaScript、TypeScript などの問題を特定して修正します。 ヒントはインライン下線として表示され、[問題] ウィンドウに集計されます。

## 構成

この拡張機能では、HTML、CSS、テンプレートシステム (JSX/TSX、角速度など)、JavaScript/TypeScript などのヒントとパーサーをアクティブ化する[既定の構成](https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json)json ファイルが使用されます。

```json
{
    "connector": "local",
    "extends": [
        "accessibility",
        "progressive-web-apps"
    ],
    "formatters": [
        "html",
        "summary"
    ],
    "hints": [
        "apple-touch-icons",
        "button-type",
        "compat-api/css",
        "compat-api/html",
        "create-element-svg",
        "css-prefix-order",
        "disown-opener",
        "highest-available-document-mode",
        "manifest-exists",
        "meta-charset-utf-8",
        "meta-viewport",
        "no-bom",
        "no-protocol-relative-urls",
        "scoped-svg-styles",
        "sri",
        "typescript-config/consistent-casing",
        "typescript-config/import-helpers",
        "typescript-config/is-valid",
        "typescript-config/no-comments",
        "typescript-config/strict",
        "typescript-config/target"
    ],
    "hintsTimeout": 10000,
    "parsers": [
        "babel-config",
        "css",
        "html",
        "javascript",
        "jsx",
        "less",
        "sass",
        "typescript",
        "typescript-config",
        "webpack-config"
    ]
}
```

アクティブ化されるヒントとパーサーをさらに制御する必要がある場合は、 `.hintrc` web ヒントを構成するためのローカルファイルを作成します。 特定のヒントからの出力に関するヘルプについては、「 [webhint ユーザーガイド](https://webhint.io/docs/user-guide/configuring-webhint/summary/)」を参照してください。

## フィードバック

[Web ヒント GitHub リポジトリ](https://github.com/webhintio/hint)に[問題を提出](https://github.com/webhintio/hint/issues/new)して、フィードバックを送信してください。 

拡張機能に参加するには、 [webhint とコード拡張の投稿ガイド](https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md)を参照してください。

## 関連項目
  - [アクセシビリティ](/microsoft-edge/accessibility)
  - [Visual Studio Code](/microsoft-edge/visual-studio-code/)
