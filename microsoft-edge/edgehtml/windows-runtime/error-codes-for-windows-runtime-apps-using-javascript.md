---
description: JavaScript を使用した Windows ランタイム アプリのエラー コード
title: JavaScript を使用した Windows ランタイム アプリのエラー コード
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
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
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3e7241d675a6f488e70eefb20c40149683f965c8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398491"
---
# <a name="error-codes-for-windows-runtime-apps-using-javascript"></a>JavaScript を使用した Windows ランタイム アプリのエラー コード  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

JavaScript を使用して Windows ランタイム アプリを開発するときに、Microsoft Visual Studioコンソールで表示されるエラー コードを次に示します。  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9601: *"remoteURI*を読み込めない。  アプリはローカル コンテキストでリモート Web コンテンツを読み込めない。 | Web コンテキストで許可される機能の詳細については、「コンテキスト別の機能と [制限」を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9602: "'javascript:' は無効な属性値であり、無視されます。  ローカル コンテキストで 'javascript:' URI を使用しない。 | セキュリティ上の理由から、ローカル コンテキストで 'javascript:' URI を使用することはできません。  ローカル コンテキストで許可される機能の詳細については、「コンテキスト別の機能と [制限」を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9603: "クラス ID classID をActiveXプラグインを読み込 *めない*。  アプリは、コントロールActiveX読み込めない。 | JavaScript を使用する Windows ランタイム アプリは、カスタムの Microsoft ActiveXcontrols をサポートしています。  UI コントロールが必要な場合は、標準の Web コントロール、コントロール ライブラリを使用するか、独自のカスタム コントロールを作成します。  カスタム ロジックを実行する必要がある場合は、代わりにカスタム Windows ランタイム オブジェクトを作成します。  他の HTML、CSS、JavaScript の違いについては [、「HTML、CSS、JavaScript の機能と相違点」を参照してください][PreviousVersionsWindowsAppsHh465380]。  |  
| APPHOST9604: "無効な文字エンコードを使用するために *uri* に移動できない。  アプリは UTF8 でエンコードされたファイルにのみ移動できます。 | Windows ランタイムによってアクセスされる HTML、JavaScript、CSS はすべて、8 ビット Unicode 変換形式 (UTF-8) としてエンコードする必要があります。  他の HTML、CSS、JavaScript の違いについては [、「HTML、CSS、JavaScript の機能と相違点」を参照してください][PreviousVersionsWindowsAppsHh465380]。  |  
| APPHOST9605: "宛先 URI が高いセキュリティ 領域にあるため *、sourceURI*から*targetURI*に移動できない。  Web コンテキスト URI からローカル コンテキスト URI に移動し、ローカル コンテキスト URI を MSApp.addPublicLocalApplicationUri メソッドに登録しない限り、セキュリティが低い領域からセキュリティが高い領域に移動できません。 | 詳細については [、「MSApp.addPublicLocalApplicationUri」を参照してください][PreviousVersionsHh771917]。  |  
| APPHOST9606: "HTTP 接続** を使用し、ms-https-connections-only メタ要素が存在するために uri を読み込めない。  ms-https-connections-only メタ要素を使用する場合は、HTTPS 接続のみ許可されます。  HTTPS 接続を使用するか、セキュリティで保護された接続が必要ない場合は、メタ要素を削除します。 | 詳細については [、「HTTPS 接続を要求する方法」を参照してください][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9607: "アプリはこのエラーが原因で*URI*を起動できない: *failureCode."* | 不足しているリソースまたは無効なファイルは、このエラーの一般的な原因です。  |  
| APPHOST9608: "このエラーが原因で、アプリが about:blank ページに移動できなかった: *errorCode."* |  |  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9610: "アプリがカスタム エラー ページへの移動の準備中にエラーを検出しました: *errorCode."* |  |  
| APPHOST9611: "このエラーが原因でアプリがカスタム エラー ページに移動できなかった: *errorCode."* |  |  
| APPHOST9613: "このエラーが原因でアプリが*uri*に移動できなかった: *errorCode."* |  |  
| APPHOST9614: "iframe 内のドキュメントが要求 *されたDocMode* ドキュメント モードを要求しましたが、システムは *currentDocMode* ドキュメント モードを適用します。  iframe は *currentDocMode ドキュメント モードを* 使用します。 | リモート Web コンテンツの表示の詳細については、「外部 Web ページ [へのリンク方法」を参照してください][PreviousVersionsWindowsAppsHh780594]。  |  
| APPHOST9615: "アプリは、ローカル コンテキストの外部でプログラムによって呼び出されたため *、uri* でファイルをダウンロードできません。 | Web コンテキスト内のコンテンツがプログラムによってファイルをダウンロードしようとするときに発生します。  |  
| APPHOST9616: "この URI では位置情報 API を使用することはできません。  Geolocation API は、パッケージの一部である URI またはマニフェストの ApplicationContentUris 要素に含まれている URI からのみ呼び出すことができます。 | Web コンテキストで許可される機能の詳細については、「コンテキスト別の機能と [制限」を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9617: "この URI ではクリップボード API を使用することはできません。  クリップボード API は、パッケージの一部である URI またはマニフェストの ApplicationContentUris 要素に含まれている URI からのみ呼び出すことができます。 | Web コンテキストで許可される機能の詳細については、「コンテキスト別の機能と [制限」を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9618: "この URI では window.close を使用することはできません。  window.close メソッドは、ms-appx URI スキームで読み込まれたパッケージ化されたコンテンツからのみ呼び出すことができます。 | Web コンテキストで許可される機能の詳細については、「コンテキスト別の機能と [制限」を参照してください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9619: "Web コンテキスト内のページをアプリのトップ レベルドキュメントにできないので、アプリは *uri* に移動できません。  代わりに、iframe でページを読み込む。 | トップ レベル のページをリモート Web ページに移動できますが、アプリは iframe に Web ページを [表示できます][MDNIframe]。  リモート Web コンテンツの表示の詳細については、「外部 Web ページ [へのリンク方法」を参照してください][PreviousVersionsWindowsAppsHh780594]。  |  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9620: "このアプリは HTTP 接続を使用し、ms-https-connections-only メタ要素が存在するために閉じられました。  ms-https-connections-only メタ要素を使用する場合は、HTTPS 接続のみ許可されます。  HTTPS 接続を使用するか、セキュリティで保護された接続を必要としない場合は、メタ要素を削除します。 | 詳細については [、「HTTPS 接続を要求する方法」を参照してください][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9623: "このエラーが原因でアプリが*URL*を解決できなかった: *errorCode."* | このエラーの一般的な原因は、ファイルが見つからない場合です。  |  
| APPHOST9624: "アプリは、URL が別のアプリを起動しますので、スクリプトを使用して *URL* URL を読み込む事ができない。  直接のユーザー操作だけが別のアプリを起動できます。 | アプリは他のアプリを直接起動できません。  他のアプリは、アプリが特定の契約を実装するときにユーザーが起動できます。  詳しくは、[アプリ コントラクトと拡張機能][PreviousVersionsWindowsAppsHh464906]についてのページをご覧ください。  |  
| APPHOST9626: "リソース ファイルへの直接参照 `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png` が検出されました。  この参照により、デバッグ環境外で使用するとエラーが発生します。 | ファイル パスが原因で、この PNG ファイルはローカライズされたリソースとして扱われるので、ローカライズされたリソースのエラーは `logo.scale-140.png` 直接参照できません。  この [ファイルを言語リソースとして使用する場合は、「アプリのグローバル化 (HTML)」][PreviousVersionsWindowsAppsHh465006] を参照してください。  それ以外の場合は、問題のあるディレクトリの名前を変更してみてください。  |  

## <a name="see-also"></a>関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用|Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator クラス |Microsoft Docs"  

[PreviousVersionsHh771917]: /previous-versions/hh771917(v=vs.85) "addPublicLocalApplicationUri メソッドの|Microsoft Docs"  

[PreviousVersionsWindowsAppsHh452771]: /previous-versions/windows/apps/hh452771(v=win.10) "HTTPS 接続 (HTML) を要求する|Microsoft Docs"  
[PreviousVersionsWindowsAppsHh464906]: /previous-versions/windows/apps/hh464906(v=win.10) "アプリコントラクトと拡張機能 (Windows ランタイム アプリ) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh465006]: /previous-versions/windows/apps/hh465006(v=win.10) "アプリ (HTML) のグローバル化|Microsoft Docs"  
[PreviousVersionsWindowsAppsHh465373]: /previous-versions/windows/apps/hh465373(v=win.10) "コンテキスト別の機能と制限 (HTML) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh465380]: /previous-versions/windows/apps/hh465380(v=win.10) "HTML、CSS、JavaScript の機能と相違点 (HTML) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh780594]: /previous-versions/windows/apps/hh780594(v=win.10) "外部 Web ページ (HTML) にリンクする|Microsoft Docs"  

[MDNIframe]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: Inline Frame 要素|MDN"  
