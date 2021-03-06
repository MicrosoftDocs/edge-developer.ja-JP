---
description: 拡張機能をパッケージ化する方法について学習します。
title: 拡張機能 - パッケージ化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
keywords: edge, Web 開発, html, css, javascript, developer
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 62c7858c38cf0c06e24c25938a885b10b391fd8f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398498"
---
# <a name="packaging-microsoft-edge-extensions"></a>Microsoft Edge 拡張機能のパッケージ化  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

最後に拡張機能を完成し、パッケージ化する準備が整いました。 潜在的なユーザーの手でこれを取得するための次の手順は何か疑問に思う場合があります。 このガイドは、それを行う方法を教えることを目的としています。  

拡張パッケージ ガイドは、パッケージ化について知りたいもの、さらに細かく、細かく詳細な詳細をカバーする包括的なガイドです。 拡張機能のパッケージ化について知っている必要があるすべてを学びたくない場合は、運が良いです。 パッケージ化の苦境の大部分を取り去るオープンソースNode.js、マニホールドJS に拡張機能のサポートが追加されました。  

> [!NOTE]
> Microsoft Edge 拡張機能を Microsoft Store に提出する機能は、現在制限付き機能です。 [Microsoft Store の一](https://developer.microsoft.com/en-us/microsoft-edge/extensions/requests) 部として要求を受け取り、今後の更新について検討します。  

以下のプロセスの概要を使用して、パッケージ化の冒険をマップします。  

## [<a name="extensions-in-the-windows-dev-center"></a>Windows デベロッパー センターの拡張機能](./packaging/extensions-in-the-windows-dev-center.md)  

手動またはマニホールドJS を選択したパッケージ作成ルートに関係なく、最初の手順は Windows Developer アカウントに登録し、拡張機能の名前を予約することです。  

これを行った後は、[拡張機能パッケージの作成とテスト][](./packaging/creating-and-testing-extension-packages.md)に進んで、AppXs の作成方法と拡張機能の手動パッケージ化方法を確認するか、簡単なルートに移動して「[マニホールドJS](./packaging/using-ManifoldJS-to-package-extensions.md)を使用して拡張機能をパッケージ化する」に移動します。  

> [!NOTE]
> Microsoft Store で拡張機能を利用できると承認された場合は、アプリ提出チェックリスト [を確認してください](https://docs.microsoft.com/windows/uwp/publish/app-submissions)。  


## [<a name="creating-and-testing-extension-packages"></a>拡張機能パッケージの作成とテスト](./packaging/creating-and-testing-extension-packages.md)  

このガイドのセクションでは、Windows Developer アカウントを設定し、拡張機能名を予約した後に、手動で拡張パッケージを作成する [方法について説明します](./packaging/extensions-in-the-windows-Dev-Center.md)。 拡張機能のパッケージ化の詳細が気になる場合は、これを読み取って下さい。  

パッケージ化された拡張機能をテストして解凍する方法 [に関する情報も含まれています](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)。 この情報は、マニホールドJS のパッケージ化ルートを行った場合でも関連します。  

## [<a name="localizing-extension-packages"></a>拡張機能パッケージのローカライズ](./packaging/localizing-extension-packages.md)  

パッケージのローカライズ手順は、appxmanifest.xmlファイルを作成し、最終コマンドを実行して拡張機能をパッケージ化する場合の間に行います。  
これにより、Microsoft Store の登録情報で拡張機能がサポートする言語と、Windows で拡張機能の名前が表示される言語を指定できます。  

拡張機能が複数の言語をサポートしない場合は、ガイドのこのセクションで [Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) の名前と説明のローカライズにジャンプできます。  

## [<a name="using-manifoldjs-to-package-extensions"></a>拡張機能をパッケージ化するために ManifoldJS を使用する](./packaging/using-ManifoldJS-to-package-extensions.md)  

拡張機能をパッケージ化するためのツール ルート、ManifoldJS は、最小限の労力で拡張機能を簡単にパッケージ化します。 AppXManifest プロパティを入力した後、いくつかの Windows/Microsoft Store アセットを提供すると、拡張機能はあっという間にパッケージ化されます。  

拡張機能をパッケージ化したら、「Microsoft Edge[](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)拡張機能の作成とテスト」の「テスト」セクションを参照して、サイドロードまたはアンパックする方法について説明します。  

## [<a name="running-the-windows-app-certification-kit"></a>Windows アプリ認定キットの実行](./packaging/running-the-windows-app-certification-kit.md)  

パッケージ化された拡張機能を取得したら、Windows アプリ認定キットを使用して実行できます。 これにより、Microsoft Store の準備ができていることを確認するために、拡張機能パッケージで多数のテストが実行されます。  
