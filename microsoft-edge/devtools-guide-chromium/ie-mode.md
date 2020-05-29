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
# Internet Explorer モードと DevTools

このドキュメントでは、Internet Explorer モード (IE モード) を Microsoft Edge (Chromium) DevTools と統合する方法について説明します。

## IE モードについて

IE モードは、現在、Internet Explorer 11 でのみ動作する一連の web サイトを企業が指定するためのメカニズムです。 Microsoft Edge (Chromium) でこれらの web サイトを表示すると、Internet Explorer 11 の完全なインスタンスが実行され、タブ内に表示されます。これにより、エンタープライズは、IE ドキュメントモード、ActiveX コントロール、および現在の最新の web ブラウザーとは互換性のないその他のレガシコンポーネントの互換性を管理することができます。

IE モードでは、レンダリングプロセスはすべて、Internet Explorer 11 に基づいています。 Microsoft Edge (Chromium) manager プロセスは、レンダリングプロセスの有効期間を管理しますが、特定のサイトまたはアプリケーションのタブの有効期間に制約されます。 タブが IE モードでレンダリングされている場合、指定したタブのアドレスバーにバッジが表示されます。

![アドレスバーの IE モードバッジ](./media/ie-mode-badge.png)

IE モードは現在、Windows 10 バージョン 1903 (2019 の更新プログラム) で使用できますが、サポートされているすべての Windows プラットフォームに近い将来利用可能になります。

## IE モードのタブで DevTools を起動する

IE モードで web サイトのドキュメントモードを表示しようとしている場合は、アドレスバーのバッジをクリックします。

![IE モードバッジでドキュメントモードを表示する](./media/ie-mode-badge-doc-mode.png)

IE モードのタブでは、DevTools は動作しません。 `F12`または、 `Ctrl` + `Shift` + `I` 次のようなメッセージが表示された Microsoft Edge (Chromium) devtools の空のインスタンスが起動します。 "開発者ツールは Internet Explorer モードでは使用できません。 ページをデバッグするには、Internet Explorer 11 でページを開きます。 [**ソースの表示**] は、メモ帳を起動し、IE モードのコンテキストメニューに [要素の**検査**] は表示されません。

これは、レンダリングエンジンが IE モードで Chromium から Internet Explorer 11 に切り替えたときに、DevTools (Network、Performance tools など) のいくつかのコンポーネントが壊れる場合があるためです。 フィードバックを送信するには、アイコンをクリックし `:)` ます。

![IE モードで起動した DevTools](./media/ie-mode-devtools.png)

Internet Explorer 11 ベースの web サイトまたはアプリケーションを開発またはメンテナンスする場合は、Internet Explorer 11 で同じページに移動することをお勧めします。 Windows 10 では、[Windows アクセサリ] の下にある [スタート] メニューで Internet Explorer 11 のショートカットを見つけることができます。 Windows 7 では、[スタート] メニューの [Internet Explorer 11] を見つけることができます。 次に、 `F12` コンテキストメニューの [**要素の検査**] をクリックまたはクリックして、Internet Explorer の devtools を起動します。 これらのツールの使用方法の詳細については、[ここ](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85))をクリックしてください。

## リモートデバッグと IE モード

リモートデバッグが有効になっている Microsoft Edge (Chromium) を起動することができます。これは、通常、Visual Studio や VS コード起動 Edge などのツールがコマンドラインから実行される方法です。

`start msedge --remote-debugging-port=9222`

このコマンドライン引数で Microsoft Edge (Chromium) を起動すると、IE モードは利用できなくなります。 ただし、IE モードに含まれている web サイトまたはアプリケーションに移動することはできますが、Internet Explorer 11 ではなく Chromium 経由でコンテンツを表示します。 ActiveX コントロールなど、IE11 に依存しているページの部分が正しく表示されない場合があります。 IE モードのバッジはアドレスバーに表示されなくなります。

IE モードは、Microsoft Edge (Chromium) を完全に終了するまで使用できません。