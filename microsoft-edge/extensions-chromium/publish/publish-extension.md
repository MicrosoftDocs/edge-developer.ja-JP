---
description: Microsoft Edge アドオン ストアに Microsoft Edge (クロム) 拡張機能を発行する
title: 拡張機能の公開
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 67fdbdb39f3ef0b2b6cef2831520849933ffeeec
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399128"
---
# <a name="publish-your-extension"></a>拡張機能の公開  

拡張機能を開発してテストした後、拡張機能を配布する準備が整いました。 拡張機能を配布するには、Microsoft Edge アドオン ストアを使用します。  Microsoft Edge ユーザー用の既存のクロム拡張機能をリリースするには、既存のクロム拡張機能 [を移植するために移動します][PortChromiumExtension]。  

拡張機能を Microsoft Edge アドオン ストアに発行して、その拡張機能のリーチを拡大し、Microsoft Edge のユーザーが利用できます。  この記事では、Microsoft Edge アドオン ストアに拡張機能を送信するプロセスについて説明します。  

## <a name="before-you-begin"></a>始める前に  

拡張機能のプロトタイプを準備する必要があります。  拡張機能を作成する方法の詳細については、「Getting [started tutorial」を参照してください][ExtensionsGettingStarted]。  

拡張機能を Microsoft Edge アドオン ストアに発行するには、パートナー センターでアクティブな開発者アカウント [を使用します][MicrosoftPartnerCenter]。  開発者アカウントをお持ちでない場合は、新しい開発者アカウントを作成します。  新しい開発者アカウントを開き、Microsoft Edge アドオン プログラムに登録するには、[開発者登録] [に移動します][DeveloperRegistration]。  

拡張機能パッケージを表す zip ファイルを作成します。  拡張機能パッケージには、次のファイルが含まれる必要があります。  

*   拡張機能の名前、簡単な説明、アクセス許可、既定の言語など、詳細を指定する拡張マニフェスト。  
*   拡張機能で必要な画像や他のファイル。  

マニフェストの次のフィールドは、ストアの登録情報の詳細に自動的に含まれます。  フィールドは、[ストアの登録情報] ページ **で読み取り専用** です。  [ストアの登録情報] ページについては、この記事で後述します。  パッケージをパートナー センターにアップロードする前に、フィールドの値がストアの詳細ページの好みの表示と一致する必要があります。  マニフェスト ファイルに必要なコードの例については、マニフェスト ファイルの基本を確認してください。  

*   `Name` マニフェスト ファイルのフィールド (ストアの詳細ページ **の** 表示名) を指定します。  
*   `Description` [ストアの詳細] ページの [短い説明 **]** であるマニフェスト ファイルのフィールドを指定します。  拡張機能の一覧の上部に表示する短い説明を入力します。  含まれていると、拡張機能マニフェスト ファイルに指定された短い説明がストアの一覧に表示されます。  短い説明がマニフェスト ファイルに含まれていない場合は、説明の最初の数行が表示されます。  ストア登録情報ページでコンテンツの繰り返しを避けるための簡単な説明を入力します。  

## <a name="submit-your-extension-to-microsoft-edge-add-ons-store"></a>拡張機能を Microsoft Edge アドオン ストアに提出する  

拡張機能をパートナー センターに [送信するには、][MicrosoftPartnerCenter]次の手順を使用します。  

#### <a name="step-1--start-a-new-submission"></a>手順 1: 新しい申請を開始する  

開発者ダッシュボードに [移動し、[][MicrosoftPartnerCenter] 概要] ページで **[新しい拡張機能の作成** ] **を選択** します。  

#### <a name="step-2--upload-the-extension-package"></a>手順 2: 拡張機能パッケージをアップロードする  

[パッケージ **] ページを** 使用して、拡張機能パッケージの zip ファイルをアップロードします。  一度にアップロードできるパッケージは 1 つのみです。  [パッケージ] ページでパッケージのアップロードが成功しなかった場合は、申請を **続行** できない。  

パッケージをアップロードするには、パッケージを選択してアップロード フィールドにドラッグします。 [ファイルの参照] **を選択することもできます**。  パッケージがアップロードされると、パッケージが検証されます。  検証が成功したら、拡張機能の詳細を確認し、[次へ] **を選択** して続行します。  検証エラーがある場合は、問題を解決し、もう一度アップロードしてみてください。  

#### <a name="step-3--provide-availability-details"></a>手順 3: 可用性の詳細を提供する  

[可用性 **] ページ** で、拡張機能の可用性に関する次の情報を入力します。  

##### <a name="visibility"></a>表示  

Microsoft Edge アドオン ストアで拡張機能が検出可能な場合は、次のいずれかの表示オプションを選択して定義します。  

*   `Public` \(default\)  
    Public を使用すると、すべてのユーザーが検索、Microsoft Edge アドオン ストアでの参照、または Microsoft Edge アドオン ストアの拡張機能のリスト URL を使用して拡張機能を検出できます。  リスト URL は、[拡張機能の概要] ページのパートナー センター ダッシュボードで **使用** できます。  
    
*   `Hidden`  
    非表示を指定すると、Microsoft Edge アドオン ストアの検索結果や閲覧から拡張機能が削除されます。  Microsoft Edge アドオン ストアで非表示の拡張機能を配布するには、リスト URL を顧客と拡張機能に共有する必要があります。  
    
> [!NOTE]
> 拡張機能の表示設定を [パブリック] から [非表示]**に変更****できます**。  表示設定がパブリックに設定されている間に拡張機能をインストールしたユーザーは、拡張機能へのアクセス権を保持し、Microsoft Edge アドオン Web サイトを通じて利用可能にした更新プログラムを受け取る。  

##### <a name="markets"></a>市場  

拡張機能を提供する予定の特定の市場を定義します。  市場の既定の設定は、すべての市場であり、後で追加される将来の市場が含まれます。  特定の市場を選択するには、[市場の変更 **] を選択します**。  個々のマーケットを切り替え、各**** マーケットを除外するか、[すべて選択解除] を選択して、選択した個別のマーケットを追加します。  

> [!NOTE]
> 拡張機能が提供される市場を変更できます。  ユーザーの市場で利用できる間に拡張機能をインストールしたユーザーは、拡張機能へのアクセスを保持します。  ただし、ユーザーは Microsoft Edge アドオン ストアに提出される将来の更新プログラムにアクセスできます。  

[保存 **] を** 選択して、[プロパティ] **セクションに進** む。  

#### <a name="step-4-select-properties-for-your-extension"></a>手順 4: 拡張機能の [プロパティ] を選択する  

[プロパティ **] ページで**、拡張機能のプロパティを指定する次の情報を入力します。  プロパティは、Microsoft Edge アドオン ストアのユーザーに表示されます。  

| Extension プロパティ名 | 説明 |  
|:--- |:--- |  
| Category \(required\) | 拡張機能を最も表すカテゴリ。  適切なカテゴリに拡張機能を登録すると、ユーザーは拡張機能を簡単に見つけ、その詳細を理解できます。  |  
| プライバシー ポリシーの要件 \(必須\) | 拡張機能が個人情報にアクセス、収集、または送信したかどうかを示します。  [はい] を選択し、 **を** 指定しない場合、拡張機能で認定手順が失敗する場合があります `Privacy policy URL` 。  |  
| プライバシー ポリシーの URL | 拡張機能がプライバシーに関する法律および規制に従う方法を伝える有効なプライバシー ポリシー URL。  お客様は、プライバシーに関する法律および規制に従って拡張機能を確保する責任があります。  また、個人情報が内線でアクセス、送信、または収集されている場合は、プライバシー ポリシーの URL を提供する責任があります。  内線番号にプライバシー ポリシーが必要かどうかを確認するには [、Microsoft Edge Developer Agreement][MicrosoftAppDeveloperAgreement] および Microsoft Edge アドオン ストア開発者ポリシー [に移動します][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  |  
| Web サイトの URL | 拡張機能に関する追加情報を提供する Web ページ。  Microsoft Edge アドオン ストアの拡張機能の Web リストではなく、独自の Web サイトのページをポイント `Website URL` する必要があります。  拡張機能、機能、その他の関連情報の詳細をユーザー `Website URL` が知るのに役立ちます。  |  
| サポート連絡先の詳細 | サポート Web ページの URL、またはサポート チームに連絡するメール アドレス。  |  
| 成熟したコンテンツ | 拡張機能に成熟したコンテンツが含まれる場合は、チェック ボックスをオンにします。  拡張機能の評価は、拡張機能の対象ユーザーの適切な年齢グループを決定するのに役立ちます。  拡張機能に成熟したコンテンツが含つかどうかを確認するには、Microsoft Edge アドオン ストア開発者ポリシー [に移動します][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  |  

[ **保存] を** 選択して、[ストアの登録情報 **] セクションに進** む。  

> [!Important]
> 登録時に送信した開発者/組織名、Web サイトの URL、サポート連絡先の詳細は、Microsoft Edge アドオン ストアのユーザーに表示されます。  

#### <a name="step-5-add-store-listing-details-for-your-extension"></a>手順 5: 拡張機能のストア登録情報の詳細を追加する  

次のセクションで提供される情報は、Microsoft Edge アドオン ストアで登録情報を確認するユーザーに表示されます。  一部のフィールドはオプションですが、可能な限り多くの情報を提供する必要があります。  ストアに拡張機能を一覧表示するには、次の詳細が必要です。  

*   **拡張** パッケージ内の各言語の説明。  
*   **拡張機能パッケージ内の** 各言語の拡張ストア のロゴ。  
    
> [!NOTE]
> 拡張機能の zip パッケージに記載されている言語の少なくとも 1 つについて、ストアの登録情報の最小情報を入力する必要があります。  Microsoft Edge アドオン ストアのストア登録情報に言語を追加または削除するには、[ストアの登録**** 情報] ページの [言語の追加]**ドロップダウンを使用**します。  さらに、言語の詳細ページの [重複する機能] ボタンを使用して、1 つの言語から他の言語のアセットを複製することもできます。  

| 言語の詳細プロパティ名 | 説明 |  
|:--- |:--- |  
| 表示名 \(required\) | 拡張子 `name` のマニフェスト ファイルで指定された拡張子の値。  申請後にストアの表示名を変更するには、マニフェスト ファイル内の名前を更新し、新しい拡張パッケージを作成してから、再アップロードできます。  |  
| 説明 \(required\) | このフィールドでは、拡張機能の機能、ユーザーがインストールする理由、またはユーザーが知る必要があるその他の関連情報について `description` 説明します。  10,000 文字未満である必要があります。  |  
| 拡張機能ストアのロゴ \(必須\) | 会社を表す画像、または縦横比が 1 で、推奨サイズが `extension logo` 300 x 300 ピクセルの画像。  さらに、重複ボタンを使用して、1 つの言語から他のすべての言語にアセットをコピーすることもできます。  ボタンは、言語のロゴをアップロードした後、フィールドの後に表示されます。  |  
| 小さなプロモーション タイル \(optional\) | イメージ `Small promotional tile` は、ストア内の他の拡張機能と共に拡張機能を表示するために使用されます。  画像のサイズは 440 x 280 ピクセルである必要があります。  さらに、重複ボタンを使用して、1 つの言語から他のすべての言語にアセットをコピーすることもできます。  このボタンは、言語のプロモーション タイルをアップロードした後、フィールドの後に表示されます。  |  
| スクリーンショット \(optional\) | 拡張機能の機能を詳細に説明する最大 10 `screenshots` を提出できます。  スクリーンショットのサイズは、640 x 480 ピクセルまたは 1280 x 800 ピクセルである必要があります。  さらに、重複ボタンを使用して、1 つの言語から他のすべての言語にアセットをコピーすることもできます。  このボタンは、言語用に少なくとも 1 つをアップロードした後、フィールドの後に表示されます。|  
| 大きなプロモーション タイル \(optional\) | `Large promotion tiles` は、Microsoft Edge アドオン Web サイトで拡張機能を目立つように機能するためにストアで使用されます。  送信された画像は、ユーザーに表示されます。  PNG ファイルのサイズは 1400 x 560 ピクセルである必要があります。  さらに、重複ボタンを使用して、1 つの言語から他のすべての言語にアセットをコピーすることもできます。  このボタンは、言語のプロモーション タイルをアップロードした後、フィールドの後に表示されます。  |  
| YouTube ビデオ URL \(optional\) | 拡張機能のプロモーション YouTube ビデオを含める場合があります。  ビデオ `YouTube video URL` は、拡張機能のストア登録情報ページに表示されます。  |  
| 簡単な説明 \(必須\) | 編集するには、拡張パッケージのマニフェスト ファイルの説明フィールドを更新し、再アップロード `short description` する必要があります。  |  
| 検索用語 \(optional\) | `Search terms` は、Microsoft Edge アドオン ストアで検索するときにユーザーが内線番号を検出するのに役立つ単一の単語または語句です。  検索用語はユーザーに表示されません。  |  

##### <a name="youtube-video-url-requirements"></a>YouTube ビデオ URL の要件  

ビデオが次の要件を満たしていることを確認します。  

*   YouTube ビデオのコンテンツが Microsoft Edge アドオン ストアの開発者向けポリシーに従 [っているのを確認します][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  
*   ビデオの広告をオフにします。  詳細については、「埋め込みビデオに [既定の広告形式と][GoogleYoutubeAnswer2531367Topic7072227] 広告を設定する [」に移動します][GoogleYoutubeAnswer132596]。  
*   ビデオの埋め込み機能を有効にする。  詳細については、「埋め込みビデオ [と再生リスト&移動します][GoogleYoutubeAnswer171780]。  
    
ビデオの YouTube ビデオ URL を送信するには、次の手順を実行します。  

1.  YouTube で、ストア登録情報ページに追加するビデオを探します。  
1.  ビデオの下で、[埋め込み共有 **] を**  >  **選択します**。  
1.  表示される HTML コードをコピーします。  
1.  [ストア一覧の詳細] ページで、フィールドに HTML コードを貼り付 `YouTube video URL` けます。  
    
##### <a name="search-terms-requirements"></a>検索用語の要件  

検索用語は、次の要件を満たしている必要があります。  

*   最大 21 単語まで使用する検索用語を入力できます。  単一の単語、語句、または両方の組み合わせとして使用する場合でも、最大 21 単語しか使用できません。  
*   最大で 7 つの検索用語 (単一の単語または語句) を指定できます。  各検索用語の文字数制限は 30 文字です。  
    
#### <a name="step-6-complete-your-submission"></a>手順 6: 申請を完了する  

[拡張機能 **の提出] ページで** 、拡張機能のテストに役立つ認定用のメモを追加します。  

##### <a name="notes-for-certification-optional"></a>認定に関するメモ (オプション)  

拡張機能を提出する場合は、[認定用メモ] ページ **を使用** して、認定テスターに追加情報を提供します。  追加情報は、拡張機能が正しくテストされていることを確認するのに役立ちます。  拡張機能が完全にテストされていない場合は、認定に失敗する可能性があります。  

必要に応じて、次の情報を含める必要があります。  

*   テスト アカウントのユーザー名とパスワード。  
*   非表示またはロックされた機能にアクセスする手順。  
*   地域や他のユーザー設定に基づく機能の予想される違い。  
*   申請が既存の拡張機能の更新である場合は、拡張機能に加えた変更に関する情報を含めます。  
*   申請に関してテスターが理解する必要がある追加情報。  

情報を提供した後、[発行] **を選択** して拡張機能を Microsoft Edge アドオン ストアに送信します。  申請は認定ステップに進みます。  認定プロセスは、申請後最大 7 営業日かかる場合があります。  

申請が認定に合格すると、拡張機能は Microsoft Edge アドオン ストアに発行されます。  パートナー センター ダッシュボードの拡張機能の状態がに変わります `In the Store` 。  

> [!NOTE]
> 申請または登録プロセスで問題が発生した場合は、[拡張機能の新しいサポート要求[][ExtensionsSupportForm]] にサポート チケットを提出するか、電子メールを送信[ext_dev_support@microsoft.com。][MailtoExtDevSupportMicrosoftCom]  

<!-- links -->  

[ExtensionsGettingStarted]: ../getting-started/index.md "Microsoft Edge (Chromium) の拡張機能をお使いになる前に | Microsoft Docs"  
[DeveloperRegistration]: ./create-dev-account.md "Microsoft Edge 拡張機能開発者として登録|Microsoft Docs"  
[PortChromiumExtension]: ../developer-guide/port-chrome-extension.md "クロム拡張機能を Microsoft Edge サーバーに移植|Microsoft Docs"  
[MicrosoftEdgeAddonsCatalogDeveloperPolicies]: ../store-policies/developer-policies.md "Microsoft Edge アドオンストア開発者ポリシー |Microsoft Docs"  

[MicrosoftAppDeveloperAgreement]: /legal/windows/agreements/app-developer-agreement "アプリ開発者契約|Microsoft Docs"  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナー センター"  

[ExtensionsSupportForm]: https://support.microsoft.com/supportrequestform/e7a381be-9c9a-fafb-ed76-262bc93fd9e4 "拡張機能 新しいサポート要求|Microsoft サポート"  

[GoogleYoutubeAnswer2531367Topic7072227]: https://support.google.com/youtube/answer/2531367?ref_topic=7072227 "既定の広告形式を設定|YouTube ヘルプ"  

[GoogleYoutubeAnswer132596]: https://support.google.com/youtube/answer/132596 "埋め込みビデオの広告|YouTube ヘルプ"  
[GoogleYoutubeAnswer171780]: https://support.google.com/youtube/answer/171780 "再生リスト&埋め込み|YouTube ヘルプ"  

[MailtoExtDevSupportMicrosoftCom]: mailto:ext_dev_support@microsoft.com "メールをメールに ext_dev_support@microsoft.com" 
