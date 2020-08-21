---
title: JavaScript を使用して Windows ランタイム アプリのエラー コード
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- JavaScript, Windows Runtime error codes
- VS.WebClient.Help.APPHOST9601
- VS.WebClient.Help.APPHOST9602
- VS.WebClient.Help.APPHOST9603
- VS.WebClient.Help.APPHOST9604
- VS.WebClient.Help.APPHOST9605
- VS.WebClient.Help.APPHOST9606
- VS.WebClient.Help.APPHOST9607
- VS.WebClient.Help.APPHOST9608
- VS.WebClient.Help.APPHOST9610
- VS.WebClient.Help.APPHOST9611
- VS.WebClient.Help.APPHOST9613
- VS.WebClient.Help.APPHOST9614
- VS.WebClient.Help.APPHOST9615
- VS.WebClient.Help.APPHOST9616
- VS.WebClient.Help.APPHOST9617
- VS.WebClient.Help.APPHOST9618
- VS.WebClient.Help.APPHOST9619
- VS.WebClient.Help.APPHOST9620
- VS.WebClient.Help.APPHOST9623
- VS.WebClient.Help.APPHOST9624
- VS.WebClient.Help.APPHOST9626
ms.assetid: 4c6d4e90-602a-4b56-ae74-3458929da442
caps.latest.revision: 1
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 7779da61da9f011e55eeb496c7332e5b7cd5a023
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942150"
---
# JavaScript を使用して Windows ランタイム アプリのエラー コード  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

JavaScript を使用して Windows ランタイム アプリを開発するときに、Microsoft Visual Studio 本体によって表示されるエラー コードを以下に示します。  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9601: "リモートURIを読み *込むことができません*。  アプリはローカル コンテキストでリモート Web コンテンツを読み込むできません。" | Web コンテキストで許可される機能の詳細については、コンテキスト [による機能と制限を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9602: "'javascript:' は無効な属性値で、無視されます。  ローカル コンテキストでは 、"javascript:' の URIs を使用しないでください。 | セキュリティ上の理えから、ローカル コンテキストで 'javascript:' URIs を使用することができない。  ローカル コンテキストで許可される機能の詳細については、コンテキスト [による機能と制限を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9603:"class ID クラス ID を含む ActiveX プラグインを読み *込むことができません*。  アプリがコントロールを読み込ActiveXできない。 | JavaScript を使用する Windows ランタイム アプリでは、カスタム Microsoft ActiveX コントロールはサポートされません。  UI コントロールが必要な場合は、標準 Web コントロール、コントロール ライブラリを使用するか、独自のカスタム コントロールを作成します。  カスタム ロジックを実行する必要がある場合は、代わりにカスタム Windows ランタイム オブジェクトを作成します。  HTML、CSS、JavaScript のその他の違いについては [、HTML、CSS、JavaScript][PreviousVersionsWindowsAppsHh465380]の機能と違いを参照してください。  |  
| APPHOST9604: "検索に移動できません。無効 *な文字エ* ンコードが使用されているためです。  アプリは UTF8 でエンコードされたファイルにのみ移動できます" というエラーが表示されます。 | Windows ランタイムによってアクセスされたすべての HTML、JavaScript、CSS は、8 ビット Unicode 変換形式 (UTF-8) としてエンコードする必要があります。  HTML、CSS、JavaScript のその他の違いについては [、HTML、CSS、JavaScript][PreviousVersionsWindowsAppsHh465380]の機能と違いを参照してください。  |  
| APPHOST9605:"リンク先の URI がより高いセキュリティ ゾーンにある*ため、ソースURI*からター*ゲーURI*に移動できません。  Web コンテキスト URI からローカル コンテキスト URI に移動し、MSApp.addPublicLocalApplicationUri メソッドでローカル コンテキスト URI を登録している場合を含むゾーンを大きくなっています。 | 詳細については [、MSApp.addPublicLocalApplicationUri を参照してください][PreviousVersionsHh771917]。  |  
| APPHOST9606:"HTTP 接続を使用*uri*し、ms-https-connections-only メタ要素が含まうため、読み込みできません。  ms-https 接続のみのメタ要素を使用する場合、HTTPS 接続のみが許可されます。  HTTPS 接続を使用するか、または、接続が不要な場合は、メタ要素を削除してください。" | 詳細については [、HTTPS 接続を要求する方法を参照してください][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9607: "このエラーのため、アプリは*uri*URI を*起動できません*。" | このエラーが発生しなかったリソースや無効なファイルが一般的な原因です。  |  
| APPHOST9608: "このエラーコードのため、アプリは about:blank ページに *移動*できませんでした。" |  |  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9610: "カスタム エラー ページへの移動の準備中にエラーが見つかりました: *errorCode."* |  |  
| APPHOST9611: "このエラーコードのため、アプリはカスタム エラー ページに *移動*できませんでした。" |  |  
| APPHOST9613: "このエラーのため、アプリが*検索**できませんでした*。" |  |  
| APPHOST9614: "iframe 内のドキュメントは要求 *されたDocMode docMode docMode docMode* モードを要求しましたが、システムは *現在のDocMode docMode docMode* を適用します。  iframe では *、currentDocMode docMode doc モードを* 使用します" と読み上げられます。 | リモート Web コンテンツの表示の詳細については、「 [外部 Web ページへのリンク方法」を参照してください][PreviousVersionsWindowsAppsHh780594]。  |  
| APPHOST9615: "アプリは、ローカル コンテキストの*uri*外部でプログラムによって呼び出されたため、URI 時にファイルをダウンロードできません。" | Web コンテキスト内のコンテンツがプログラムによってファイルをダウンロードしなくても発生します。  |  
| APPHOST9616: "この URI は地名 API を使用できません。  ジオレンジ API は、パッケージの一部である URI またはマニフェストの ApplicationContentUris 要素に含まれている URI からのみ実行できます。 | Web コンテキストで許可される機能の詳細については、コンテキスト [による機能と制限を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9617: "この URI はクリップボード API を使用できません。  クリップボード API は、パッケージの一部である URI またはマニフェストの ApplicationContentUris 要素に含まれている URI からのみ実行できます。 | Web コンテキストで許可される機能の詳細については、コンテキスト [による機能と制限を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9618: "この URI はウィンドウ.閉じます。  window.close メソッドは、ms-appx URI スキームで読み込んでいたパッケージ コンテンツからのみ起動できます。 | Web コンテキストで許可される機能の詳細については、コンテキスト [による機能と制限を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9619: "Web コンテキスト内の*uri*ページをアプリのトップ レベルのドキュメントにできないため、アプリは検索に移動できません。  代わりに iframe でページを読み込みます。" | 最上位のページをリモート Web ページに移動できませんが、アプリでは iframe 内で Web ページを [表示できます][MDNIframe]。  リモート Web コンテンツの表示の詳細については、「 [外部 Web ページへのリンク方法」を参照してください][PreviousVersionsWindowsAppsHh780594]。  |  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9620: "このアプリは HTTP 接続を使用し、ms-https 接続のみのメタ要素が含まったため、このアプリは閉じられました。  ms-https 接続のみのメタ要素を使用する場合、HTTPS 接続のみが許可されます。  HTTPS 接続を使用するか、または、接続を必要としない場合は、メタ要素を削除してください。" | 詳細については [、HTTPS 接続を要求する方法を参照してください][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9623: "このエラーコードが原因で *、* アプリが URL を解決できません *でした*。" | このエラーの一般的な原因として、ファイルが見つからない可能性があります。  |  
| APPHOST9624: "このアプリでは、別のアプリを起動するため、スクリプトを使用して *URL* を読み込めません。  直接ユーザー操作のみで別のアプリを起動できます。" | アプリは他のアプリを直接起動できません。  他のアプリは、アプリが特定のコントラクトを実装したときにユーザーが起動できます。  詳しくは、[アプリ コントラクトと拡張機能][PreviousVersionsWindowsAppsHh464906]についてのページをご覧ください。  |  
| APPHOST9626: "リソース ファイルへの直接参照 `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png` が検出されました。  この参照によって、デバッグ環境の外で使用すると失敗します。" | ファイル パスのため、この PNG ファイルはローカライズされたリソースとして認識されるため、ローカライズされたリソースで直接参照できないエラーが `logo.scale-140.png` 発生しています。  この [ファイルを言語リソースとして使用する場合は、アプリ (HTML)][PreviousVersionsWindowsAppsHh465006] をグローバライズしておきます。  それ以外の場合は、問題のディレクトリ名を変更してみてください。  |  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用する |Microsoft ドキュメント"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator Class |Microsoft ドキュメント"  

[PreviousVersionsHh771917]: /previous-versions/hh771917(v=vs.85) "addPublicLocalApplicationUri メソッド |Microsoft ドキュメント"  

[PreviousVersionsWindowsAppsHh452771]: /previous-versions/windows/apps/hh452771(v=win.10) "HTTPS 接続 (HTML) を要求する方法 |Microsoft ドキュメント"  
[PreviousVersionsWindowsAppsHh464906]: /previous-versions/windows/apps/hh464906(v=win.10) "アプリの終了と拡張 (Windows ランタイム アプリ) |Microsoft ドキュメント"  
[PreviousVersionsWindowsAppsHh465006]: /previous-versions/windows/apps/hh465006(v=win.10) "アプリ (HTML) |Microsoft ドキュメント"  
[PreviousVersionsWindowsAppsHh465373]: /previous-versions/windows/apps/hh465373(v=win.10) "コンテキスト (HTML) による機能と制限Microsoft ドキュメント"  
[PreviousVersionsWindowsAppsHh465380]: /previous-versions/windows/apps/hh465380(v=win.10) "HTML、CSS、JavaScript の機能と違い (HTML) |Microsoft ドキュメント"  
[PreviousVersionsWindowsAppsHh780594]: /previous-versions/windows/apps/hh780594(v=win.10) "外部 Web ページ (HTML) へのリンク方法 |Microsoft ドキュメント"  

[MDNIframe]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: インライン フレーム要素 |MDN"  
