---
description: 2019年3月の Microsoft Edge (Chromium) DevTools に追加された機能
title: 2019年3月の Microsoft Edge (Chromium) DevTools の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bf1919b0ab46df378880d664dd4e59aee96605e5
ms.sourcegitcommit: 24430258f363b7dd85f7067afd4565bf102b4a1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "10645323"
---
# Microsoft Edge (Chromium) DevTools の新機能

次のバージョンの Microsoft Edge のプレビューを試してみていただき、ありがとうございました。 このリリースでは、Chromium open source プロジェクトを採用することで、Microsoft Edge の基盤となる web プラットフォームでの大きなシフトを実施しました。 この変更により、Microsoft Edge で web サイトを構築およびテストして、ユーザーが Google Chrome、Vivaldi、Opera、Brave などの別の Chromium ベースのブラウザーで参照している場合でも、引き続き期待どおりに動作することができます。

## 新しい Microsoft Edge (Chromium) DevTools

Microsoft Edge をチェックしていて、Chromium ベースのブラウザーで主に開発している場合は、自宅で適切なことを考えてください。 Microsoft Edge (Chromium) 開発者ツールは、既に知っていて使用している開発者ツールとまったく同じです。

![Microsoft Edge (Chromium) DevTools](./media/devtools.png)

次のバージョンの Microsoft Edge を確認して、主に Microsoft edge (EdgeHTML) で開発している場合は、Microsoft Edge で web サイトを構築およびテストするために、より簡単かつ迅速にするために役立つ新しいツールがいくつか用意されています。 これらの新しいツールについて詳しくは、 [Microsoft Edge (Chromium) DevTools のガイド](../devtools-guide-chromium.md)をご覧ください。

## DevTools 用の新しい濃色とライトのテーマ

お客様にとって気に入っていると考えている DevTools のために、新しいダークテーマと軽量テーマを開発しました。 既定では、Microsoft Edge (Chromium) DevTools は濃色テーマを使用します。 Devtools のテーマを変更するには、 `Fn`  +  `F1` Windows または Mac を押すか、 `...` devtools の右上隅にあるボタンを使用して [設定] に移動します。

![Microsoft Edge (Chromium) DevTools メインメニュー](./media/devtools-main-menu.png)

[設定] から、DevTools のテーマを変更することができます。 Chromium ベースのブラウザーでの DevTools の表示方法が気に入った場合は、[**ダーク (Chromium)** ] または [ **Light (Chromium)** ] のテーマをそれぞれ選ぶことにより、Microsoft Edge (Chromium) の devtools をまったく同じように見せることができます。 

## VS コードから Microsoft Edge (Chromium) をデバッグする

Microsoft Edge とコード拡張[用のデバッガー](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)を使うと、microsoft Edge (EdgeHTML) と microsoft Edge (Chromium) の両方を VS コードから直接デバッグできるようになりました。

![Edge VS のコード拡張用デバッガー](./media/vscode-debugger.png)

VS コードから microsoft Edge (EdgeHTML) の代わりに Microsoft Edge (Chromium) を起動するには、 `version` (、、または) を起動するバージョンの Microsoft edge (Chromium) を使用して、既存の**起動. json**構成に属性を追加する必要があり `dev` `beta` `canary` ます。 次に示すのは、Microsoft Edge (Chromium) のカナリアバージョンを[bing.com](https://www.bing.com/)に起動するためのサンプルのサンプル**です**。

```json
{
    "type": "edge",
    "request": "launch",
    "version": "canary",
    "name": "Launch Microsoft Edge (Chromium) Canary against Bing",
    "url": "https://bing.com"
}
```

詳細については、「 [Microsoft Edge (Chromium) を VS コードからデバッグする方法](../visual-studio-code/debugger-for-edge.md)」を参照してください。

## Edge DevTools プロトコル更新プログラム

Microsoft Edge の基になる web プラットフォームのシフトでは、Edge DevTools プロトコルは今後の更新プログラムを受け取りません。 Microsoft Edge (Chromium) DevTools は、Chrome DevTools プロトコルまたは CDP を使います。 CDP のドメインとメソッドに関するドキュメントを参照するには、 [cdp ビューアー](https://chromedevtools.github.io/devtools-protocol/tot/Accessibility)を参照してください。

次のバージョンの Microsoft Edge では、プレフィックスの付いたメソッドはサポートされ `ms` ません。 Microsoft Edge (Chromium) での CDP の使い方の詳細については、「 [Devtools Protocol (Chromium)](../devtools-protocol-chromium.md)」を参照してください。

## 既知の問題

サードパーティサイト上でホストされているコンテンツへの Microsoft Edge (Chromium) DevTools からの多くのリンクが一時的に削除されました。 これらのリンクを置き換えるとすぐに、開発ツールに再び追加されます。


Microsoft Edge (Chromium) から Android デバイスで web コンテンツをデバッグする場合、**リモートデバイス**ツールの [**検査**] ボタンをクリックしたときに起動する Devtools のバージョンが Android デバイスのブラウザーのバージョンと一致しない可能性があります。 このため、Android デバイスのブラウザーで動作しない、DevTools の新機能が表示されることがあります。 この問題が発生した場合は、ファイルに関する[フィードバック](../devtools-guide-chromium.md#getting-in-touch-with-the-microsoft-edge-devtools-team)をお寄せください。

最後に、Windows と Mac の Visual Studio では、Microsoft Edge (Chromium) はまだサポートされていません。 [ここ](https://visualstudio.microsoft.com/vs/preview/)にサインアップして、ASP.NET プロジェクト用の Microsoft Edge (Chromium) 内で JavaScript のデバッグをサポートする Visual Studio のプレビューバージョンがある場合に、最初にご確認ください。  
