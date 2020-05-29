---
ms.assetid: c4397525-b978-4dc2-89bc-2198b3069742
description: ManifoldJS でのスナップで Microsoft Edge 拡張機能をパッケージ化する方法については、「.js open source ツール」を参照してください。
title: ManifoldJS を使って拡張子をパッケージ化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: cca83a26c9f80eca6454e3b5b329f72a7491b6e2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569441"
---
# ManifoldJS を使用して拡張 AppX パッケージを作成する  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

ManifoldJS は、オープンなソースノード .js ツールであり、Microsoft ストアへの申請に使用できるパッケージをすばやくおり作成することができます。

拡張機能でネイティブメッセージングを使用している場合は、この手順をスキップして、 [Microsoft Edge の [ネイティブメッセージング](../native-messaging.md#creating-an-extension-with-native-messaging)] に移動して、パッケージ化の手順を実行する必要があります。 

作業を始める前に、次の記事を参照する必要があります。

- [Windows デベロッパーセンターの拡張機能](./extensions-in-the-windows-dev-center.md)
- [拡張パッケージのローカライズ](./localizing-extension-packages.md)

> [!NOTE]
> Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。 お客様の内線番号の作成、パッケージ化、テストが完了したら、[延長申請フォーム](https://aka.ms/extension-request)でリクエストを送信してください。


## ノード .js と ManifoldJS のインストール

まず、 [LTS](https://nodejs.org/en/download/)をインストールする必要があります。
ノードを取得したら、コマンドライン (PowerShell を推奨) から次のコマンドを実行して、ManifoldJS をインストールします。

`npm install -g manifoldjs`

ManifoldJS が正常にインストールされていることを確認するには、 `manifoldjs` コマンドラインから実行します。 ManifoldJS が認識されない場合は、 `%APPDATA%\npm` PATH 変数にを追加します。

## ManifoldJS でパッケージ化する

パッケージ処理を開始するには、コマンドラインを開き、パッケージ化された拡張のコピー先になるフォルダーにディレクトリを変更する必要があります。

次に、例を示します。

`cd C:\manifoldJSTest`

> [!NOTE]
> ManifoldJS は、現在のディレクトリに出力され、コンテンツを上書きすることができます。



目的のフォルダーに移動したら、次のコマンドを実行します。

`manifoldjs -l debug -p edgeextension -f edgeextension -m <EXTENSION LOCATION>\manifest.json`


このコマンドは、次の部分に分けることができます。
 -    **-l debug**: ログレベルを [デバッグ] に変更し、完全に印刷されるようにします。
 -    **-p edgeextension**: edgeextension への変換を実行する唯一のプラットフォームを設定します。
 -    **-f edgeextension**: マニフェストの形式が edgeextension 形式であり、検証に失敗した場合は注意しないようプログラムに指示します。
 -    **-m \ < 拡張機能の場所 > \ manifest¥ json**: 変換する拡張機能マニフェストへのパス。


ManifoldJS の実行が完了すると、次の内容のフォルダーが表示されます。

    My Extension
        edgeextension
            generationInfo.json
            manifest
                   appxmanifest.xml
                Assets
                    Square150x150Logo.png
                    Square44x44Logo.png
                    StoreLogo.png    
                Extension
                    manifest.json
                    popup.html
                    ...
                ...

GenerationInfo ファイルは、ManifoldJS を実行して生成されたログであり、拡張機能パッケージには含まれません。 **マニフェスト**フォルダーのコンテンツのみがパッケージ化されます。 [マニフェスト] フォルダーでは、[アセット] フォルダーには、Windows と Microsoft Store の UI で使用する画像が含まれています。また、拡張機能のフォルダーには、拡張機能の内容が含まれています。


適切なファイルを作成したので、**マニフェスト**フォルダー内で、生成された package.appxmanifest ファイルを編集する必要があります。 拡張機能の manifest.xml ファイルに "name" フィールドの国際化文字列が含まれている場合、ManifoldJS を実行すると、最上位のレイヤーフォルダー名にはアンダースコアがなく、"MSG" が含まれます。

たとえば、次のフィールドを含む manifest.xml ファイル `"name"` 。

`"name" : "__MSG_appName__"`

存在するマニフェストフォルダーがあり `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` ます。

Package.appxmanifest ファイルでは、次のことを行う必要があります。
 -    [ここで](./creating-and-testing-extension-packages.md#app-identity-template-values)説明するように、必須の id フィールドと PublisherDisplayName フィールドを置き換えます。 テスト目的またはエンタープライズ配布用にのみパッケージ化する場合は、Windows デベロッパーセンターアカウントに登録するのではなく、プレースホルダー値を使用できます。
 -    [アセット] フォルダーのプレースホルダーアイコンを、同じサイズ (150x150、50x50、44x44)、名前の拡張機能のアイコンに置き換えます。 これらのアイコンが使用されている場所については、[設計](./../design.md#icons-for-packaging)ガイドを参照してください。
 - 拡張機能がローカライズされている場合は、「 [Microsoft Edge のローカライズ](./localizing-extension-packages.md)ガイド」の全機能について説明します。 ローカライズされていない場合は、「 [Microsoft Store」セクションでローカライズする名前と説明](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store)のみを参照してください。

Package.appxmanifest ファイルが並べ替えられたら、次のコマンドを実行してパッケージを作成します。

`manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\`

これで、パッケージが edgeextension フォルダー内の**パッケージ**フォルダーに保存されます。 新しいパッケージをサイドローディングする方法について詳しくは、「拡張パッケージの[テスト](./creating-and-testing-extension-packages.md#testing-an-appx-package)とテスト」をご覧ください。

パッケージのテストが完了したら、Microsoft ストアへの公開を検討するために、[内線番号の申請フォーム](https://aka.ms/extension-request)で要求を送信してください。
