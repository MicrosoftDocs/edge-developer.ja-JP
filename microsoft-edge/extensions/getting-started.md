---
description: ここでは、開発の開始から Microsoft Edge extensions のパッケージ化までの一連の概要について説明します。
title: 拡張機能-はじめに
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: 5d2bf0ea2236e36b9e6205e13291ffee4118d9d7
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569517"
---
# 拡張機能の概要  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

このガイドには、拡張機能を使用したり、使い慣れた Chrome 拡張機能を使用したりする経験をお持ちの方にも、Microsoft Edge の拡張機能を開発、テスト、パッケージ化、公開するために必要なすべての情報が記載されています。 

## 拡張機能の開発

この旅の最初の手順は、Microsoft Edge 拡張機能を作成することです。 
- 拡張機能について 初めてのブラウザー拡張機能の構築方法については、「[拡張機能を作成する」](./guides/creating-an-extension.md)を参照してください。 
- 拡張 Api についてよく理解していますか? Api の[サポートドキュメント](./api-support.md)を参照して、どの api がサポートされているか開発中かに関する最新情報を確認してください。 
- Chrome 拡張を使用して Microsoft Edge に移植しますか? [Microsoft Edge 拡張ツールキット](./guides/porting-chrome-extensions.md)をお試しください。

## 読み込みとデバッグ

Microsoft Edge で動作する拡張機能がある場合は、それをサイドロードして動作を確認します。 この操作を行う最初の手順は、拡張機能の[開発者向け機能が有効になっ](./guides/adding-and-removing-extensions.md)ていることを確認することです。 これにより、Microsoft Edge で拡張機能ファイルをサイドロードすることができるため、拡張機能の開発中に拡張機能をテストすることができます。 いずれかの問題が発生した場合は、F12 開発者ツールを使用すると、[拡張機能のさまざまなコンテキストをデバッグ](./guides/debugging-extensions.md)して、何が起こっているかを特定することができます。 まだ問題が発生していますか? [トラブルシューティングガイド](./troubleshooting.md)には、いくつかの一般的な問題に対する解決策があります。 

## バグの報告とヘルプの表示

拡張プラットフォームでバグが見つかったと考えていますか? 問題が Microsoft Edge に固有のものである場合は、 [Microsoft edge の問題追跡ツール](https://developer.microsoft.com/microsoft-edge/platform/issues/)を検索して、既に報告されているかどうかを確認してください。 それでもすばらしい! 「+」ボタンを押すと、バグに関する情報が表示され、「更新に関するこの問題を監視」ボタンをクリックすると、問題が発生したときの通知を受け取ることができます。 実行している問題が見つからない場合は、新しい問題を開いて、できるだけ多くの情報を提供し、開発者が確認できるようにしてください。 

拡張機能が正しく動作するために必要な API が見つからない場合 そうであれば、[常に UserVoice でリッスンしてい](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer/category/87962-extensions)ます。 既に存在している場合は、API を無料でお知らせします。または、他の開発者が投票できるように、新しいフィードバック項目を作成します。 

ドキュメントに回答が見つからないという質問がありますか? [Microsoft Edge Extensions コミュニティ](https://stackoverflow.com/questions/tagged/microsoft-edge-extension)をスタックオーバーフローに参加させ、そこで質問することを強くお勧めします。

## 拡張機能のテスト

Windows 記念日向けの更新プログラムでは、microsoft [Web ドライバー](../dev-guide/tools/webdriver.md)は microsoft Edge セッションでの内線番号の自動読み込みをサポートしています。 これにより、ページを変更するためのすべての拡張機能が予期したとおりに動作するように、単純なテストを記述することができます。 詳細については、[テストガイド](./guides/packaging/creating-and-testing-extension-packages.md#automated-testing-with-webdriver)を参照してください。 また、今後、Microsoft WebDriver に拡張機能を追加する予定ですので、更新プログラムを常に調整してください。

## 最終仕上げを追加する

Microsoft Edge で拡張機能を使用できます。 次に実行される処理 拡張機能のパッケージ化を続ける前に、これらのガイドをチェックして、お客様の拡張機能がベストプラクティスポリシーに準拠していることを確認することを強くお勧めします。 
- 拡張機能のアイコンが[適切にサイズ](./guides/design.md)変更され、[アクセスできる](./guides/accessibility.md)ことを確認します (つまり、Microsoft Edge とハイコントラストモードの両方で、淡色と濃色の両方のテーマで表示されます)。 
- 拡張機能で複数の言語をサポートする必要がある場合は、「[国際化のガイド」](./guides/internationalization.md)を参照してください。 

## 拡張機能をパッケージ化する

これで、拡張機能が最終的に磨き、パッケージ化される準備が整いました。 Microsoft ストアへの提出を準備するためにパッケージ化する必要があるか、または開発/テストチーム内で簡単に配布できるようにするには、以下の情報を参考にしてください。 

- 拡張パッケージを作成するための推奨される解決策は、 [ManifoldJS パッケージガイド](./guides/packaging/using-manifoldjs-to-package-extensions.md)を使用して、開発しているプラットフォームに関係なく簡単に拡張機能をパッケージ化する方法について説明します。 さらに手動で、拡張パッケージ形式について詳しくは、 [AppX パッケージ作成ガイド](./guides/packaging/creating-and-testing-extension-packages.md#preparing-the-submission-folder)をご覧ください。 
- 拡張機能が複数の言語をサポートしている場合は、パッケージ化後に拡張機能で使用している言語が適切に登録されるように、[拡張機能パッケージのローカライズ](./guides/packaging/localizing-extension-packages.md)に関するガイドを参照する必要があります。 

社内のチャネル経由でパッケージ化された拡張機能を配布する企業向けのお客様の場合は、その方法については、「[エンタープライズ向けのガイド](./extensions-for-enterprise.md)」を参照してください。  

## Microsoft ストアに公開する

拡張機能プラットフォームはまだ infancy のため、Microsoft ストアへの拡張申請を意図的に管理しています。これにより、ユーザーと開発者向けの品質を向上させることに専念できるようになります。 これについては、開発者が自分の内線番号を公開できるようにするため、できる限り簡単にしてください。 このため、最近、Microsoft ストアに拡張 AppX を送信する許可を要求するための新しい[拡張機能申請フォーム](https://aka.ms/extension-request)がリリースされました。
 

公開プロセスの最初の手順では、お使いの[ブラウザー拡張ポリシー](./microsoft-browser-extension-policy.md)と microsoft [Store のポリシーの microsoft Edge extensions セクション](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)に、拡張機能が適合していることを確認します。 

拡張機能がポリシーに準拠していることを確認したら、[パートナーセンターで開発者アカウントに登録し、内線番号の名前を予約](./guides/packaging/extensions-in-the-windows-dev-center.md)する必要があります。 次に、Microsoft ストアに公開するためのアクセス許可を要求するために、[内線番号の申請フォーム](https://aka.ms/extension-request)から要求を送信する必要があります。 初めてアクセス許可を取得しないで拡張機能の AppX を送信しようとすると、次のエラーが表示されます。

`Package acceptance validation error: com.microsoft.edge.extension is a reserved extension type. Your app does not have permission to use this extension type.`

リクエストを送信すると、通知が送信され、できるだけ早く申請にアクセスしようとします。 これにより、大量の申請が送信されるため、多少の時間がかかる場合がありますが、承認された時点でメールで通知されます。 メールを受信したら、パートナーセンターで Microsoft Store に拡張 AppX を送信できます。 送信前に AppX に署名する必要はありませんので、ご了承ください。Microsoft Store の取り込みプロセスは、お客に対応しています。
 
> [!NOTE]
> Microsoft ストアへの拡張機能の公開プロセス (ブランドが新しくなったか、既存のものが更新されたかにかかわらず) が完了するまでに最大72時間かかることがあります。 このプロセスを円滑に進めるために、提出前にこれらの一般的な問題を確認し、後で再送信する必要がないようにしてください。 
> - スクリーンショットのサイズが正しく、Microsoft Edge で実行されている拡張機能である 
> - 拡張機能の説明では、"Edge" ではなく "Microsoft Edge" が参照されます (これは法的要件です) 
> - 拡張機能パッケージの 15 0x150 のアイコン[は、透明な背景を持っていません](./guides/design.md#microsoft-store-icon)(Microsoft Store クライアントでは、透明な背景を持つ画像が適切に表示されません)。 

上記に加えて、該当する場合は、お客様の web サイトのプラットフォームの可用性情報が Microsoft Edge で拡張機能の空き時間情報を正しくメンションしていることを確認してください。 Microsoft ストアでは、ワンクリックでインライン拡張機能をインストールすることはできませんが、ユーザーが簡単に取得できるように[Microsoft store の拡張機能にディープリンク](./tips-and-tricks.md#get-a-direct-link-to-your-extension-in-the-microsoft-store)することができます。 

Microsoft ストアでは、Microsoft Store カタログの[拡張機能の表示を制御](https://blogs.windows.com/buildingapps/2015/09/10/managing-hidden-apps-beta-apps-and-visibility-of-in-app-purchases-in-dev-center/)することもできます。 一部のパートナーは、この機能を活用して次のことを実現しています。 
- 第2のベータ版の拡張機能を Microsoft Store で非表示にして公開します。
- 最初に、初期のテレメトリを監視するために拡張機能を hidden として発行してから、一定の信頼度に達した時点で状態を "visible" に変更します。

## 以上で作業は終了です。

このガイドの一番下に到達した場合は、Microsoft Edge の拡張機能の開発プロセスを完了したことになります。 お客さまの内線番号を販売し、ユーザと連絡を取る方法については、「[ヒントとテクニック](./tips-and-tricks.md)」ページをご覧ください。
