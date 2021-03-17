---
description: 開発の開始から Microsoft Edge 拡張機能のパッケージ化までの概要を説明します。
title: 拡張機能 - 使い始める
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, developer, extensions
ms.date: 03/16/2021
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 52d0aa5c1968518194a4e3b90cb0cc876d0c7f86
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439718"
---
# <a name="getting-started-with-extensions"></a>拡張機能の使用を開始する  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

新しい開発者が拡張機能に慣れたい場合でも、移植する Chrome 拡張機能を経験したベテランでも、Microsoft Edge の拡張機能を開発、テスト、パッケージ化、発行するために必要なすべての情報が含まれています。 

## <a name="developing-an-extension"></a>拡張機能の開発

この手順の最初の手順は、Microsoft Edge 拡張機能を作成します。 
- 拡張機能の新機能 最初のブラウザー [拡張機能を作成する方法の](./guides/creating-an-extension.md) 詳細については、拡張機能の作成方法に関するガイドをご覧ください。 
- 拡張 API について既に理解していますか? API が [サポート/開発](./api-support.md) 中である最新の情報については、API サポート ドキュメントを参照してください。 
- Microsoft Edge に移植する Chrome 拡張機能をお持ちですか? Microsoft [Edge 拡張機能を試Toolkit!](./guides/porting-chrome-extensions.md)

## <a name="loading-and-debugging"></a>読み込みとデバッグ

Microsoft Edge で機能する拡張機能が作成された後は、サイド ロードして実際の動作を確認します。 これを行う最初の手順は、拡張機能の開発者機能が有効 [になっていることを確認します](./guides/adding-and-removing-extensions.md)。 これにより、Microsoft Edge で拡張機能ファイルを読み込み、開発中に拡張機能をテストできます。 問題が発生した場合、F12 開発者ツールを使用すると、拡張機能[](./guides/debugging-extensions.md)のさまざまなコンテキストをデバッグして、何が起こっているのかを正確に判断できます。 まだ問題が発生していますか? トラブルシューティング [ガイドには、](./troubleshooting.md) いくつかの一般的な問題に対する解決策があります。 

## <a name="reporting-bugs-and-getting-help"></a>バグの報告とヘルプの取得

拡張機能プラットフォームにバグが見つかったと思いますか? 問題が Microsoft Edge に固有の場合は [、Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/issues/) Issue Tracker で検索して、既に報告済みか確認してください。 それが持つなら、素晴らしい! "+ Me too" ボタンを押すと、バグをアップポートし、問題に関する変更に対する通知を受け取る "この問題を更新プログラムに監視する" ボタンを押します。 実行中の問題が見つからなかった場合は、新しい問題を開いて、開発者が問題を確認できるよう、可能な限り多くの情報を提供してください。 

<!--Are we missing an API that your extension needs to work properly? If so, [we're always listening on UserVoice](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer/category/87962-extensions). Feel free to upvote your API if it already exists, or to create a new feedback item so that other developers can upvote it too! -->  

ドキュメントで回答が見つからなかった質問がありますか? スタック オーバーフローで Microsoft [Edge Extensions コミュニティ](https://stackoverflow.com/questions/tagged/microsoft-edge-extension) に参加し、そこで確認することを強くおすすめします。

## <a name="testing-your-extension"></a>拡張機能のテスト

Windows Anniversary Update の現在 [、Microsoft WebDriver](../webdriver/index.md) は Microsoft Edge セッションでの拡張機能の自動サイド ローディングをサポートしています。 これにより、簡単なテストを記述して、ページを変更するための拡張機能が予期した方法で行われます。 これを行う方法の詳細については、テスト ガイドを [参照してください](./guides/packaging/creating-and-testing-extension-packages.md#automated-testing-with-webdriver)。 また、今後、Microsoft WebDriver に拡張機能固有の機能を追加する予定です。

## <a name="adding-the-final-touches"></a>最後のタッチを追加する

そのため、拡張機能は Microsoft Edge で動作します。 次に何が起こりますか? 拡張機能のパッケージ化を続行する前に、拡張機能がベスト プラクティス ポリシーに従っている必要がある場合は、次のガイドを参照することを強く推奨します。 
- 拡張アイコンのサイズが正[](./guides/design.md)しく、アクセス[](./guides/accessibility.md)可能な状態 (Microsoft Edge の明るいテーマと暗いテーマ、ハイ コントラスト モードの両方で表示される) を確認します。 
- 拡張機能で複数の言語をサポートする必要がある場合は、国際化ガイドを [確認してください](./guides/internationalization.md)。 

## <a name="packaging-an-extension"></a>拡張機能のパッケージ化

これで、拡張機能が最終的に洗練され、パッケージ化される準備が整いました。 パッケージ化して Microsoft Store への提出の準備を行う場合でも、開発/テスト チーム内での配布を容易に行う場合でも、以下に役立つリソースが豊富に用意されています。 

- 拡張パッケージを作成するための推奨されるソリューションは、開発するプラットフォームに関係なく、Node.js ベースのツールを使用して拡張機能を簡単にパッケージ化する手順を説明するマニホールド [JS](./guides/packaging/using-manifoldjs-to-package-extensions.md) パッケージ ガイドに従います。 拡張パッケージの形式に関するより手動で詳細な情報が必要な場合は、AppX パッケージ作成ガイド [を参照してください](./guides/packaging/creating-and-testing-extension-packages.md#preparing-the-submission-folder)。 
- 拡張機能が複数の言語をサポートしている場合は、拡張パッケージのローカライズに関する[](./guides/packaging/localizing-extension-packages.md)ガイドに従って、拡張機能内の言語がパッケージ化後に正しく登録されるようにする必要があります。 

パッケージ化された拡張機能を内部チャネル経由で配布する企業のお客様は、エンタープライズ 向け拡張機能ガイドを[](./extensions-for-enterprise.md)参照して、これを行う方法を確認してください。  

## <a name="publishing-to-the-microsoft-store"></a>Microsoft Store への発行

拡張機能プラットフォームはまだ初期段階にあるので、Microsoft Store への拡張機能の申請を目的として管理し、ユーザーと開発者に質の高いエクスペリエンスを提供します。 つまり、開発者が拡張機能を公開し、可能な限り簡単に公開したいと考えています。 その結果、最近、開発者が拡張機能 AppX[](https://aka.ms/extension-request)を Microsoft Store に提出するためのアクセス許可を要求できる新しい内線番号申請フォームを立ち上げました。
 
発行プロセスの最初の手順は、拡張機能が Microsoft Store ポリシーの**** Microsoft Edge 拡張機能セクションと同様に、ブラウザー拡張機能ポリシーに準拠することを[確認します](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)。  

<!--  The first step of the publishing process is to make sure your extension conforms to our [browser extension policy](./microsoft-browser-extension-policy.md) as well as the [Microsoft Edge extensions section of the Microsoft Store Policies](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12).  -->  

拡張機能がポリシーに従っているのを確認したら、パートナー センターで開発者アカウントに登録し、拡張機能の名前 [を予約する必要があります](./guides/packaging/extensions-in-the-windows-dev-center.md)。 次に、Microsoft Store に発行するアクセス許可[](https://aka.ms/extension-request)を要求するには、内線番号申請フォームから要求を送信する必要があります。 最初にアクセス許可を取得せずに拡張機能 AppX を送信すると、次のエラー メッセージが表示されます。

```text
Package acceptance validation error: com.microsoft.edge.extension is a reserved extension type. Your app does not have permission to use this extension type.
```  

要求を送信すると、通知が届き、できるだけ早く申請にアクセスします。 これは、受信した提出の量が多い場合に少し時間がかかる場合がありますが、承認された時点でメールで通知します。 メールを受け取った後、パートナー センターから拡張機能 AppX を Microsoft ストアに送信できます。 提出する前に AppX に署名する必要がなされていないことに注意してください。Microsoft Store の取り込みプロセスが、その処理を行います。
 
> [!NOTE]
> Microsoft Store に拡張機能を発行するプロセス (新しい拡張機能でも既存の拡張機能への更新でも) は、完了に最大で 72 時間かかる場合があります。 このプロセスを迅速に行う場合は、提出前に以下の一般的な問題を確認し、後で再送信する必要が生じしないようにしてください。 
> - スクリーンショットのサイズが正しく、Microsoft Edge で実行されている拡張機能のスクリーンショット 
> - 拡張機能の説明は、"Edge" ではなく "Microsoft Edge" を参照します (これは法的要件です) 
> - 拡張パッケージの 150x150 アイコンに透明な背景が含まれています [(Microsoft](./guides/design.md#microsoft-store-icon) Store クライアントでは、透明な背景を持つイメージが正しくレンダリングされません) 

上記に加えて、該当する場合は、Web サイト上のプラットフォームの可用性情報に、Microsoft Edge での拡張機能の可用性が正しく記載されていることを確認してください。 Microsoft Store では、1 回クリックのインライン拡張機能のインストールは許可できませんが [、Microsoft Store](./tips-and-tricks.md#get-a-direct-link-to-your-extension-in-the-microsoft-store) の拡張機能に深くリンクして、ユーザーが簡単に入手できます。 

Microsoft Store では、Microsoft Store カタログ内の拡張機能の [表示](https://blogs.windows.com/buildingapps/2015/09/10/managing-hidden-apps-beta-apps-and-visibility-of-in-app-purchases-in-dev-center/) を制御することもできます。 一部のパートナーは、この機能を利用して次の機能を実現しています。 
- 拡張機能の 2 番目のベータ版を Microsoft Store で非表示として公開する。
- 最初は、特定のレベルに達すると、その状態を表示に変更する前に、拡張機能を非表示として公開して初期テレメトリを監視します。

## <a name="thats-it"></a>以上で作業は終了です。

このガイドの下部に達した場合は、Microsoft Edge の拡張機能を開発するプロセスが完了しました。 拡張機能を市場に出 [し、](./tips-and-tricks.md) ユーザーとやり取りする方法に関するアイデアについては、必ずヒントとコツのページをご覧ください。
