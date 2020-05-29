---
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
description: ネイティブメッセージングを使って、拡張機能とコンパニオン UWP アプリとの通信を行う方法について説明します。
title: 拡張機能-パッケージ化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 23c97f366db527cae2672d6ad46fa666583f6398
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569459"
---
# Microsoft Edge extensions のパッケージ化  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

最後に拡張機能を完成させ、パッケージ化する準備ができました。 次の手順は、潜在的なユーザーに対してこの作業を行うためのものです。 このガイドは、そのための方法を説明することを目的としています。

拡張機能パッケージガイドは、パッケージ化について知っておく必要があるものをすべて網羅しており、細かい部分もあります。 拡張機能のパッケージ化について知っておくべきことをすべて学習したくない場合は、運を気にする必要があります。 ManifoldJS の拡張機能のサポートを追加しました。このツールでは、パッケージ woes の大半を使用できます。

> [!NOTE]
> Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。 Microsoft Store の一部として要求が送信された場合は、skype[に](https://aka.ms/extension-request)連絡して、将来の更新についてご検討ください。


以下のプロセスの概要を使用して、パッケージの冒険をマッピングしてください。


## [Windows デベロッパーセンターの拡張機能](./packaging/extensions-in-the-windows-dev-center.md)

どのパッケージ作成ルート (manual または ManifoldJS のいずれを選んでも、最初の手順では、Windows 開発者アカウントに登録し、内線番号の名前を予約しています。

この操作を完了すると、[拡張パッケージの作成とテスト](./packaging/creating-and-testing-extension-packages.md)を行って、appxs の作成方法と拡張機能を手動でパッケージ化する方法、またはより簡単なルートに移動し[て、ManifoldJS を使ってパッケージの拡張子に](./packaging/using-ManifoldJS-to-package-extensions.md)移動することができます。

> [!NOTE]
> Microsoft Store の内線番号に登録されていることを確認したら、[[アプリの申請] チェックリスト](https://docs.microsoft.com/windows/uwp/publish/app-submissions)を参照してください。


## [拡張パッケージの作成とテスト](./packaging/creating-and-testing-extension-packages.md)

このセクションでは、 [Windows 開発者アカウントを設定し、内線番号を予約](./packaging/extensions-in-the-windows-Dev-Center.md)した後の手動による拡張パッケージの作成について説明します。 拡張機能のパッケージ化について詳しく知りたい場合は、こちらを参照してください。

[パッケージ化された拡張機能のテストと展開](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)の方法に関する情報も含まれています。 この情報は、ManifoldJS のパッケージルートを使用していない場合でも関連します。

## [拡張パッケージのローカライズ](./packaging/localizing-extension-packages.md)
パッケージのローカライズ手順では、package.appxmanifest ファイルを作成し、最後のコマンドを実行して拡張機能をパッケージ化します。
これにより、Microsoft ストアの登録情報で、拡張機能でサポートされている言語と、Windows に拡張機能の名前が表示される言語を指定することができます。

拡張機能で複数の言語がサポートされていない場合は、ガイドのこのセクションで[、Microsoft ストアの名前と説明のローカライズ](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store)に進むことができます。

## [ManifoldJS を使って拡張子をパッケージ化する](./packaging/using-ManifoldJS-to-package-extensions.md)

ManifoldJS は、拡張機能をパッケージ化するためのツールルートであり、お客様の最終的な作業を最小限に抑えて、スナップで拡張機能をパッケージ化します。 いくつかの Package.appxmanifest プロパティに入力した後で、いくつかの Windows/Microsoft ストアアセットを提供します。拡張機能は、いつでもパッケージ化されます。

拡張機能をパッケージ化したら、Microsoft Edge 拡張機能のサイドローディングまたは展開に関する[テスト](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)セクションを参照してください。


## [Windows アプリ認定キットを実行する](./packaging/running-the-windows-app-certification-kit.md)

パッケージ化された拡張子を取得したら、Windows アプリ認定キットを使ってその拡張機能を実行できます。 こうすることで、Microsoft ストアの準備ができていることを確認するため、拡張パッケージで多数のテストを実行します。
