---
ms.assetid: 1319a070-c6e3-4592-9f4b-40ce1575851f
description: Microsoft Edge Extension Toolkit を使用して Chrome 拡張機能を Microsoft Edge に移植する方法について説明します。
title: Chrome 拡張機能の移植
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f226d79dbc9efdc43eb68bfb353fa12748198371
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234916"
---
# Chrome から Microsoft Edge への拡張機能の移植  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

Chrome から Microsoft Edge への拡張機能の移植は [、Microsoft Edge](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)拡張機能のサポートを利用してToolkit。 この開発者ツールは、API をブリッジし、ファイル内のエラーを表示することで、展開されていない Chrome 拡張機能をアンパックされた Microsoft Edge 拡張機能に変換 `manifest.json` します。


### API ブリッジ
Chrome API をサポートされている Microsoft Edge API にシームレスに移植するために、拡張機能のフォルダーに 2 つのスクリプトが追加されます。 これらのスクリプトは API (必要に応じてポリフィル) をブリッジします。つまり、バックグラウンド スクリプトやコンテンツ スクリプトで Chrome 固有のコードを変更する必要はありません。

変換後、キーを使用して拡張機能のマニフェスト ファイルに含まれているのが表示 `"-ms-preload"` されます。

```json
"-ms-preload": {
  "backgroundScript": "backgroundScriptsAPIBridge.js",
  "contentScript": "contentScriptsAPIBridge.js"
}
```

## Microsoft Edge 拡張機能のToolkit

次の手順では、Chrome 拡張機能を Windows 10 Anniversary Update エディションの Microsoft Edge で実行するように変換する方法について詳しく説明します。

1. Microsoft [Edge Extension Toolkit をインストールします](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)。
2. 安全な保管のために Chrome 拡張機能のフォルダーのコピーを作成します。 変換プロセスによってコードが上書きされます。 
3. Microsoft Edge Extension Toolkitを実行し、拡張機能のコピーを読み込む。  
 ![拡張機能の読み込みボタン](./../media/save-folder.png)
4. ツールのテキスト エディター内で報告されるエラーを修正します。 修正後にエラーを確認するには、[再検証] を選択します。  
 ![extension-toolkit のエラー検出](./../media/extension-toolkit.png)
5. [ファイルの保存] を選択します。

これで、ツールキットから抜け出して、Microsoft Edge で拡張機能を読み込むのが可能です。 

EdgeHTML の問題追跡ツールを使用して、既知のプラットフォーム [の問題を検索できます](http://issues.microsoftedge.com)。 新しい情報が見つかったと思う場合は、 [問題を開きます](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)。
