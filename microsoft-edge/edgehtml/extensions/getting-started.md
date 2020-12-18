---
description: 開発の開始から Microsoft Edge 拡張機能のパッケージ化への取り入れについて、概要を説明します。
title: 拡張機能 - 使用の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者, 拡張機能
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f06762692c451ea89b74fdf6f9959172c69a32ca
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235004"
---
# 拡張機能の使用を開始する  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

新しい開発者が拡張機能に精通している場合でも、移植する Chrome 拡張機能を経験した経験の深い経験を持つ開発者でも、このガイドには、Microsoft Edge の拡張機能を開発、テスト、パッケージ化、および公開するために必要なすべての情報が含まれています。 

## 拡張機能の開発

この手順の最初の手順は、Microsoft Edge 拡張機能を作成します。 
- 拡張機能が新しい場合 最初の [ブラウザー拡張機能を構築する方法については](./guides/creating-an-extension.md) 、拡張機能を作成する方法に関するガイドをご覧ください。 
- 拡張 API に既に慣れ親しんだ場合 API が [サポートされている/開発](./api-support.md) 中の最新の情報については、API サポート ドキュメントを参照してください。 
- Microsoft Edge に移植する Chrome 拡張機能がある場合 Microsoft [Edge 拡張機能を試Toolkit!](./guides/porting-chrome-extensions.md)

## 読み込みとデバッグ

Microsoft Edge で動作する拡張機能を作成したら、サイド ロードして動作を確認できます。 これを行う最初の手順は、拡張機能の開発者向け機能 [が有効になることです](./guides/adding-and-removing-extensions.md)。 これにより、Microsoft Edge で拡張機能ファイルをサイド ロードして、拡張機能を開発中にテストできます。 問題が発生した場合は、F12 開発者ツールを使用して拡張機能[](./guides/debugging-extensions.md)のさまざまなコンテキストをデバッグし、何が起こっているのかを正確に判断できます。 それでも問題が発生しますか? トラブルシューティング [ガイドには、](./troubleshooting.md) いくつかの一般的な問題に対する解決策があります。 

## バグの報告とヘルプの取得

拡張機能プラットフォームにバグが見つかったと思いますか? 問題が Microsoft Edge に固有の場合は [、Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/issues/) の問題追跡ツールで問題を検索して、既に報告されていないか確認してください。 設定されている場合は、大きな問題です。 "+ Me too" ボタンを押してバグをアップボトし、問題に関する変更について警告を受け取る [この問題を更新に関してこの問題を見る] ボタンを押します。 発生している問題が見つからない場合は、新しい問題を自由に開き、可能な限り多くの情報を提供して、開発者が問題を確認できます。 

拡張機能が正常に動作するために必要な API が欠落していますか? その場合は [、常に UserVoice をリッスンしています](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer/category/87962-extensions)。 API が既に存在する場合は、それを自由に評価したり、他の開発者もそれを評価できるよう新しいフィードバック項目を作成してください。 

ドキュメントに回答が見当たらない質問がありますか? スタック オーバーフローの Microsoft [Edge 拡張機能](https://stackoverflow.com/questions/tagged/microsoft-edge-extension) コミュニティに参加し、そこで質問することを強く推奨します。

## 拡張機能のテスト

Windows Anniversary Update の現在 [、Microsoft WebDriver は Microsoft](../webdriver/index.md) Edge セッションでの拡張機能の自動サイド ローディングをサポートしています。 これにより、ページを変更するための拡張機能が期待した方法で実行されるのを確認する簡単なテストを作成できます。 これを行う方法について詳しくは、テスト ガイドをご [覧ください](./guides/packaging/creating-and-testing-extension-packages.md#automated-testing-with-webdriver)。 また、今後、Microsoft WebDriver に拡張機能固有の機能を追加する予定である場合は、更新プログラムについて調整を行います。

## 最後のタッチの追加

そのため、拡張機能は Microsoft Edge で動作します。 次に何が起こりますか? 拡張機能のパッケージ化を続行する前に、次のガイドを参照して、拡張機能がベスト プラクティス ポリシーに従っている必要があります。 
- 拡張機能のアイコンのサイズが[](./guides/design.md)正しく、アクセス[可能な状態](./guides/accessibility.md)(つまり、Microsoft Edge の淡色テーマと濃色テーマ、ハイ コントラスト モードの両方で表示される) を確認します。 
- 拡張機能で複数の言語をサポートする必要がある場合は、国際化ガイドを [確認してください](./guides/internationalization.md)。 

## 拡張機能のパッケージ化

これで拡張機能が最終的に洗練され、パッケージ化の準備が整いました。 Microsoft Store への申請の準備のためにパッケージ化する場合でも、開発/テスト チーム内での配布を容易に行う場合でも、次のリソースを利用できます。 

- 拡張機能パッケージを作成するための推奨されるソリューションは、Node.js ベースのツールを使用して、開発するプラットフォームに関係なく拡張機能を簡単にパッケージ化する手順を説明する [、ExtensionJS](./guides/packaging/using-manifoldjs-to-package-extensions.md) パッケージ ガイドに従う方法です。 拡張機能のパッケージ形式について、より手動で詳しい情報が必要な場合は、AppX パッケージ作成ガイド [を参照してください](./guides/packaging/creating-and-testing-extension-packages.md#preparing-the-submission-folder)。 
- 拡張機能が複数の言語をサポートしている場合は、パッケージ化後に拡張機能内の[](./guides/packaging/localizing-extension-packages.md)言語が正しく登録されるように、拡張機能パッケージのローカライズに関するガイドに従う必要があります。 

パッケージ化された拡張機能を内部チャネル経由で配布する企業のお客様は、エンタープライズ 向け拡張機能ガイドを[](./extensions-for-enterprise.md)参照して、その方法を確認してください。  

## Microsoft Store への公開

拡張機能プラットフォームは現在も提供中のため、Microsoft Store への拡張機能の申請を目的として管理し、ユーザーと開発者に高品質のエクスペリエンスを提供するようにしています。 しかし、開発者が拡張機能を公開しやすくしたいと考えています。 その結果、最近、開発者が拡張機能 AppX[](https://aka.ms/extension-request)を Microsoft Store に提出するためのアクセス許可を要求できる新しい拡張機能提出フォームが立ち上げされました。
 
公開プロセスの最初の手順は、拡張機能が Microsoft Store ポリシーの****[Microsoft Edge](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)拡張機能セクションと同様に、ブラウザー拡張機能ポリシーに準拠するようにします。  

<!--  The first step of the publishing process is to make sure your extension conforms to our [browser extension policy](./microsoft-browser-extension-policy.md) as well as the [Microsoft Edge extensions section of the Microsoft Store Policies](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12).  -->  

拡張機能がポリシーに従ったことを確認したら、パートナー センターで開発者アカウントに登録し、拡張機能の名前 [を予約する必要があります](./guides/packaging/extensions-in-the-windows-dev-center.md)。 次に、Microsoft Store への公開のアクセス許可[](https://aka.ms/extension-request)を要求するために、内線番号提出フォームを介して要求を送信する必要があります。 最初にアクセス許可を取得せずに拡張機能 AppX を提出すると、次のエラーが表示されます。

```text
Package acceptance validation error: com.microsoft.edge.extension is a reserved extension type. Your app does not have permission to use this extension type.
```  

要求を送信すると、通知が送信され、できるだけ早く申請にアクセスします。 これは、受信した提出の量が多い場合に少し時間がかかる場合がありますが、承認された時点でメールで通知されます。 メールを受信すると、パートナー センターから拡張機能 AppX を Microsoft Store に提出できます。 提出する前に AppX に署名する必要は必ずしもない点に注意してください。Microsoft Store の取り込みプロセスで処理されます。
 
> [!NOTE]
> Microsoft Store に拡張機能を公開するプロセス (新しい拡張機能や既存の拡張機能の更新など) は、完了まで最大 72 時間かかる場合があります。 このプロセスを迅速に行う場合は、後で再提出する必要が生じずに、提出前に次の一般的な問題を確認してください。 
> - スクリーンショットのサイズが正しく、Microsoft Edge で実行されている拡張機能 
> - 拡張機能の説明は、"Edge" ではなく "Microsoft Edge" を参照します (これは法的要件です) 
> - 拡張機能パッケージの 150x150 アイコンに透過的な背景が設定されていません [(Microsoft](./guides/design.md#microsoft-store-icon) Store クライアントは、背景が透明な画像を正しくレンダリングしません) 

上記に加えて、該当する場合は、Web サイト上のプラットフォームの可用性情報に Microsoft Edge での拡張機能の可用性が正しく記載されていることを確認してください。 Microsoft Store では、1 回のクリックでインライン拡張機能をインストールできませんが [、Microsoft Store](./tips-and-tricks.md#get-a-direct-link-to-your-extension-in-the-microsoft-store) 内の拡張機能にディープ リンクして、ユーザーが簡単に入手できます。 

Microsoft Store では、Microsoft [Store](https://blogs.windows.com/buildingapps/2015/09/10/managing-hidden-apps-beta-apps-and-visibility-of-in-app-purchases-in-dev-center/) カタログ内の拡張機能の表示を制御することもできます。 一部のパートナーは、この機能を利用して以下を実現しています。 
- Microsoft Store で非表示にした拡張機能の 2 つ目のベータ版を公開します。
- 最初に拡張機能を非表示として公開し、初期の利用統計情報を監視してから、特定の信頼レベルに達した後、最終的にその状態を表示に変更します。

## 以上で作業は終了です。

このガイドの下部に達すると、Microsoft Edge の拡張機能を開発するプロセスが完了しました。 拡張機能を [マーケティングし、](./tips-and-tricks.md) ユーザーとやり取りする方法に関するアイデアについては、必ずヒントとコツのページをご覧ください。
