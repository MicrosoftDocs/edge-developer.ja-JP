---
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
description: 拡張機能をパッケージ化する方法について学習します。
title: 拡張機能 - パッケージ化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0ea4d6a4450d47d116164fd8481fdfb0f79bd30b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234944"
---
# Microsoft Edge 拡張機能のパッケージ化  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

最後に拡張機能が完成し、パッケージ化する準備が整いました。 潜在的なユーザーの手でこれを実現するための次の手順は何か疑問に思うでしょう。 このガイドは、その方法を教えることを目的にしています。

拡張機能のパッケージ 化ガイドは、パッケージ化に関して知りたいすべての情報を含む包括的なガイドです。さらに細かく、細かい詳細な詳細も含まれています。 拡張機能のパッケージ化について知る必要があるすべての情報を知りたくない場合は、幸いです。 パッケージ化の問題の大部分を取り上Node.jsオープン ソース ソース ツールである、MajorityJS の拡張機能のサポートが追加されました。

> [!NOTE]
> Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。 Microsoft Store[の一](https://aka.ms/extension-request)部としてお客様からのリクエストをお問い合わせください。今後の更新について検討します。


以下のプロセス アウトラインを使用して、パッケージ化の手順を説明します。


## [Windows デベロッパー センターの拡張機能](./packaging/extensions-in-the-windows-dev-center.md)

選ぶパッケージの作成ルート (手動または分作JS) に関係なく、最初の手順は Windows 開発者アカウントに登録し、拡張機能の名前を予約することです。

これを行った後は、拡張機能パッケージの作成とテストに[](./packaging/creating-and-testing-extension-packages.md)進み、AppX の作成方法と拡張機能の手動パッケージ化方法を確認するか、簡単なルートに移動して[、ExtensionJS](./packaging/using-ManifoldJS-to-package-extensions.md)を使用して拡張機能をパッケージ化します。

> [!NOTE]
> Microsoft Store にアクセスして拡張機能の提供が承認された後は、アプリの申請のチェックリスト [を確認してください](https://docs.microsoft.com/windows/uwp/publish/app-submissions)。


## [拡張機能パッケージの作成とテスト](./packaging/creating-and-testing-extension-packages.md)

このガイドのこのセクションでは、Windows 開発者アカウントを設定し、拡張機能名を予約した後に、拡張機能パッケージを手動で作成する方法 [について説明します](./packaging/extensions-in-the-windows-Dev-Center.md)。 拡張機能のパッケージ化の詳細について知りたがっている場合は、この記事を読んでおきます。

パッケージ化された拡張機能をテストして展開 [する方法に関する情報も含まれています](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)。 この情報は、分かっている場合でも関連します。

## [拡張機能パッケージのローカライズ](./packaging/localizing-extension-packages.md)
パッケージのローカライズ手順は、appxmanifest.xml ファイルを作成し、拡張機能をパッケージ化する最後のコマンドを実行する手順の間に含まれます。
これにより、Microsoft Store 登録情報で拡張機能がサポートする言語と、拡張機能の名前が Windows に表示される言語を指定できます。

拡張機能が複数の言語をサポートしない場合は、ガイドのこのセクションで [Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) のローカライズ名と説明に移動できます。

## [拡張機能をパッケージ化するために ManifoldJS を使用する](./packaging/using-ManifoldJS-to-package-extensions.md)

Extension をパッケージ化するためのツール ルート、MinimalJS は最小限の労力で拡張機能をスナップでパッケージ化します。 AppXManifest プロパティを入力した後、いくつかの Windows/Microsoft Store アセットを提供すると、拡張機能はあっという間にパッケージ化されます。

拡張機能をパッケージ化したら、「Microsoft Edge[](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)拡張機能の作成とテスト」のテスト セクションを参照して、サイドロードまたはアンパックする方法について説明します。


## [Windows アプリ認定キットの実行](./packaging/running-the-windows-app-certification-kit.md)

パッケージ化された拡張機能を取得したら、Windows アプリ認定キットから実行できます。 そうすると、拡張機能パッケージに対して多数のテストが実行されます。これにより、Microsoft Store の準備ができていることを確認できます。
