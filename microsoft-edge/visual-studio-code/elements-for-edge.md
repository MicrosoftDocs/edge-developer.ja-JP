---
description: VS コードから Microsoft Edge (Chromium) の要素を使う方法
title: VS コードからの Microsoft Edge (Chromium) の要素
author: erdraud
ms.author: erdraud
ms.date: 08/08/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、要素
ms.openlocfilehash: 4875a4665fe1561ecf587a050bbd44e116d9ce5e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570741"
---
# Microsoft Edge VS コード拡張の要素

Microsoft Edge VS コード拡張[用の要素](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools)を追加することで、ブラウザーの要素ツールを[Visual Studio コード](https://code.visualstudio.com/)内から使うことができます。 起動またはアタッチのどちらの場合も、要素ツールは Microsoft Edge のインスタンスに接続され、ランタイム HTML 構造を表示し、レイアウトを変更したり、スタイル設定の問題を修正したりすることができます。

![勤務先の Edge VS コード拡張の要素の GIF](./media/elements-for-edge.gif)

## 要素の拡張機能から Microsoft Edge を起動する 

**アクティビティバー**の要素に移動します。 [Microsoft Edge: ターゲットの要素] と表示されている場所の横に、アプリのブラウザーを開くためのプラス記号が付いています。 [*バージョン情報:* ] オプションを選んだ場合は、ブラウザーで web アプリに移動して、VS コードの要素パネルに表示されるようにする必要があります。

## デバッグビューから Microsoft Edge を起動する

Visual Studio コードでデバッグビューを使うことに慣れている場合は、そのツールから要素にアクセスできます。 ( `Ctrl`  +  `Shift`  +  `D` Windows または Mac 上の) [デバッグ] ビューに移動 `Command`  +  `Shift`  +  `D` します。 

VS コードにまだ構成がない場合 `F5` は、Windows または Mac を押すか、緑色の**再生**ボタンをクリックします。 ドロップダウンで [Edge] を選びます。 これで、次のように構成された**launch**ファイルが表示されます。

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            
            "name": "Launch Microsoft Edge and open the Elements tool",
            "request": "launch",
            "type": "vscode-edge-devtools.debug",
            "url": "http://localhost:3000"
        
        }
    ]
}
```

これで正しい構成が読み込まれたので、 `F5` Windows または Mac を押すか、緑色の**再生**ボタンをクリックします。 Microsoft Edge ブラウザーで使い慣れた要素ツールが VS コードで起動し、ブラウザーの screencast にアクセスして、ページのコンポーネントを調べることができるようになりました。

## Microsoft Edge へのアタッチ
Microsoft Edge (Chromium) のインスタンスに VS コードをアタッチする場合は、teminal から次のコマンドを実行して、ブラウザーを起動する必要があります。

`start msedge --remote-debugging-port=9222`

アプリが起動したら、次の構成を起動の**json**ファイルに追加します。

```json
{
    "type": "vscode-edge-devtools.debug",
    "request": "attach",
    "name": "Attach to Microsoft Edge and open the Elements tool",
    "url": "http://localhost:3000/",
    "webRoot": "${workspaceFolder}/out",
    "port": 9222
}
```

[Microsoft Edge にアタッチして、デバッガー] ドロップダウンメニューから [要素ツール] を開きます。 次に、 `F5` Windows または Mac を押すか、緑色の**再生**ボタンをクリックします。 VS コードによって要素ツールが起動し、ブラウザーの screencast にアクセスしたり、DOM を検査したり、ページ上のコンポーネントのスタイルを確認したりすることができます。

## フィードバック
この拡張機能の[GitHub リポジトリ](https://github.com/microsoft/vscode-edge-devtools)に[関する問題を提出](https://github.com/microsoft/vscode-edge-devtools/issues/new)して、フィードバックをお送りください。 

この延長を改善したい場合は、ご協力をお寄せください。 [GitHub リポジトリ](https://github.com/microsoft/vscode-edge-devtools)での作業を開始するために必要なすべての情報を確認できます。