---
ms.assetid: 1319a070-c6e3-4592-9f4b-40ce1575851f
description: Microsoft edge 拡張ツールキットを使って、Chrome 拡張機能を Microsoft Edge に移植する方法について説明します。
title: Chrome 拡張機能の移植
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: 38bf1324c2e7e6f7754912177ce0e53d6c15a276
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569438"
---
# 拡張子を Chrome から Microsoft Edge に移植する  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

[Microsoft Edge 拡張ツールキット](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)を使うと、Chrome から microsoft edge に拡張機能を移植するのが簡単になります。 この開発者ツールでは、展開された Chrome 拡張機能を Api を使って、ファイル内のエラーを提示することによって、展開された Microsoft Edge extension に変換し `manifest.json` ます。


### API ブリッジ
サポートされている Microsoft Edge Api への Chrome Api のシームレスな移植を可能にするために、2つのスクリプトが拡張機能のフォルダーに追加されます。 これらのスクリプトは、必要に応じてブリッジ Api (polyfiling) を使用するため、バックグラウンドスクリプトまたはコンテンツスクリプトで Chrome 固有のコードを変更する必要はありません。

変換後、それらのファイルは、拡張機能のマニフェストファイルに含まれてい `"-ms-preload"` ます。

```json
"-ms-preload": {
  "backgroundScript": "backgroundScriptsAPIBridge.js",
  "contentScript": "contentScriptsAPIBridge.js"
}
```

## Microsoft Edge 拡張ツールキットを使用する

次の手順では、Windows 10 記念日更新プログラムの Microsoft Edge で Chrome 拡張機能を実行するための変換方法について説明します。

1. [Microsoft Edge 拡張機能キット](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)をインストールします。
2. Chrome の拡張機能のフォルダーのコピーを作成して安全を確保します。 変換プロセスによってコードが上書きされます。 
3. Microsoft Edge 拡張ツールキットを実行して、拡張機能のコピーを読み込みます。  
 ![[拡張機能の読み込み] ボタン](./../media/save-folder.png)
4. ツールのテキストエディターで報告されるすべてのエラーを修正します。 修正を行った後にエラーが発生したかどうかを確認するには、"再検証" を選択します。  
 ![拡張機能-ツールキットの検索エラー](./../media/extension-toolkit.png)
5. [ファイルの保存] を選びます。

これで、ツールキットを終了して、Microsoft Edge で拡張機能を読み込むことができます。 

[EdgeHTML issue tracker](http://issues.microsoftedge.com)で、既知のプラットフォームの問題を検索できます。 新しいものが見つかった場合は、[問題を開き](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)ます。
