---
description: JavaScript を使用する Windows ランタイム アプリのエラー コード。
title: JavaScript を使用した Windows ランタイム アプリのエラー コード
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
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5a04a9c348a29aee2ec5936e7d923377dd53b21c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235074"
---
# JavaScript を使用した Windows ランタイム アプリのエラー コード  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

JavaScript を使用して Windows ランタイム アプリを開発するときに、Microsoft Visual Studio コンソールに表示されるエラー コードを次に示します。  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9601: *"remoteURI を読み込めない*。  アプリは、ローカル コンテキストでリモート Web コンテンツを読み込めない。" | Web コンテキストで許可される機能について詳しくは、「コンテキスト別の機能と [制限」をご覧ください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9602: "'javascript:' は無効な属性値であり、無視されます。  'javascript:' URI をローカル コンテキストで使用しない。" | セキュリティ上の理由から、ローカル コンテキストで 'javascript:' URI を使用することはできません。  ローカル コンテキストで許可される機能について詳しくは、「コンテキスト別の機能と [制限」をご覧ください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9603: "クラス ID classID ActiveXプラグインを読み込 *めない*。  アプリはコントロールを読みActiveXできない。" | JavaScript を使う Windows ランタイム アプリでは、カスタム Microsoft ActiveXcontrols はサポートされていません。  UI コントロールが必要な場合は、標準の Web コントロール、コントロール ライブラリを使用するか、独自のカスタム コントロールを作成します。  カスタム ロジックを実行する必要がある場合は、代わりにカスタム Windows ランタイム オブジェクトを作成します。  その他の HTML、CSS、JavaScript の相違点については [、HTML、CSS、JavaScript][PreviousVersionsWindowsAppsHh465380]の機能と相違点を参照してください。  |  
| APPHOST9604: "無効な文字エンコードを使用していますので *、URI* に移動できない。  アプリは UTF8 でエンコードされたファイルにのみ移動できます。" | Windows ランタイムによってアクセスされる HTML、JavaScript、および CSS はすべて、8 ビット Unicode 変換形式 (UTF-8) としてエンコードする必要があります。  その他の HTML、CSS、JavaScript の相違点については [、HTML、CSS、JavaScript][PreviousVersionsWindowsAppsHh465380]の機能と相違点を参照してください。  |  
| APPHOST9605: "destination URI が高いセキュリティ ゾーンにあるため *、sourceURI*から*targetURI*に移動できない。  Web コンテキスト URI からローカル コンテキスト URI に移動し、MSApp.addPublicLocalApplicationUri メソッドでローカル コンテキスト URI を登録している場合を使用しない限り、セキュリティが低いゾーンから高いセキュリティを持つゾーンに移動できません。" | 詳しくは [、MSApp.addPublicLocalApplicationUri に関するページをご覧ください][PreviousVersionsHh771917]。  |  
| APPHOST9606: "HTTP 接続を使用し、ms-https-connections-only メタ要素が存在するために *URI* を読み込めない。  ms-https-connections-only メタ要素を使用する場合は、HTTPS 接続のみ許可されます。  HTTPS 接続を使用するか、セキュリティで保護された接続が必要ない場合は、メタ要素を削除してください。" | 詳しくは [、「HTTPS 接続を要求する方法」をご覧ください][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9607: "アプリは、次のエラーのため*URI*で URI を*起動できない: failureCode."* | 不足しているリソースまたは無効なファイルは、このエラーの一般的な原因です。  |  
| APPHOST9608: "このエラーのため、アプリは about:blank ページに移動できなかった: *errorCode*." |  |  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9610: "アプリは、カスタム エラー ページ *(errorCode)* への移動の準備中にエラーを検出しました。 |  |  
| APPHOST9611: "このエラーのため、アプリはカスタム エラー ページに移動できなかった: *errorCode ."* |  |  
| APPHOST9613: "このエラーのため、アプリは*uri*に移動できなかった: *errorCode ."* |  |  
| APPHOST9614: "iframe 内のドキュメントが *requestedDocMode* ドキュメント モードを要求しましたが、システムは *currentDocMode* ドキュメント モードを適用します。  iframe は *、currentDocMode ドキュメント モードを* 使用します。 | リモート Web コンテンツの表示について詳しくは、「外部 Web ページにリンクする方法」 [をご覧ください][PreviousVersionsWindowsAppsHh780594]。  |  
| APPHOST9615: "アプリはローカル コンテキストの外部からプログラムによって呼び出されたため *、URI* でファイルをダウンロードできません。" | Web コンテキスト内のコンテンツがプログラムによってファイルをダウンロードしようとするときに発生します。  |  
| APPHOST9616: "この URI は位置情報 API を使用することはできません。  位置情報 API は、パッケージの一部である URI またはマニフェストの ApplicationContentUris 要素に含まれている URI からのみ呼び出すことができます。" | Web コンテキストで許可される機能について詳しくは、「コンテキスト別の機能と [制限」をご覧ください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9617: "この URI はクリップボード API を使用することはできません。  クリップボード API は、パッケージの一部である URI またはマニフェストの ApplicationContentUris 要素に含まれている URI からのみ呼び出すことができます。" | Web コンテキストで許可される機能について詳しくは、「コンテキスト別の機能と [制限」をご覧ください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9618: "この URI は window.close を使用することはできません。  window.close メソッドは、ms-appx URI スキームで読み込まれたパッケージ コンテンツからのみ呼び出すことができます。" | Web コンテキストで許可される機能について詳しくは、「コンテキスト別の機能と [制限」をご覧ください][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9619: "Web コンテキスト内のページをアプリのトップ レベル ドキュメントにできないので、アプリは *URI* に移動できません。  代わりに、iframe にページを読み込む。" というエラーが表示されます。 | トップ レベル のページをリモート Web ページに移動できないが、アプリで iframe に Web ページを [表示できる][MDNIframe]。  リモート Web コンテンツの表示について詳しくは、「外部 Web ページにリンクする方法」 [をご覧ください][PreviousVersionsWindowsAppsHh780594]。  |  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9620: "このアプリは HTTP 接続を使用し、ms-https-connections-only メタ要素が存在するために閉じられました。  ms-https-connections-only メタ要素を使用する場合は、HTTPS 接続のみ許可されます。  HTTPS 接続を使用するか、セキュリティで保護された接続を必要としない場合は、メタ要素を削除してください。" | 詳しくは [、「HTTPS 接続を要求する方法」をご覧ください][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9623: "このエラーのため、アプリは*URL*を*解決できなかった: errorCode ."* | このエラーの一般的な原因は、ファイルが見つからない場合です。  |  
| APPHOST9624: "URL が別のアプリを起動する理由から、アプリはスクリプトを使用して *URL* URL を読み込めないので、読み込む必要があります。  直接のユーザー操作だけが別のアプリを起動できます。" | アプリは、他のアプリを直接起動することはできません。  他のアプリは、アプリが特定のコントラクトを実装するときにユーザーが起動できます。  詳しくは、[アプリ コントラクトと拡張機能][PreviousVersionsWindowsAppsHh464906]についてのページをご覧ください。  |  
| APPHOST9626: "リソース ファイルへの直接参照 `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png` が検出されました。  この参照により、デバッグ環境の外部で使用するとエラーが発生します。" | ファイル パスが原因で、この PNG ファイルはローカライズされたリソースとして扱われるので、ローカライズされたリソースを直接参照できないというエラー `logo.scale-140.png` が発生します。  この [ファイルを言語リソースとして使用する場合][PreviousVersionsWindowsAppsHh465006] は、「アプリのグローバル化 (HTML)」をご覧ください。  それ以外の場合は、問題のあるディレクトリの名前を変更してみてください。  |  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript での Windows ランタイムの使用 |Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator クラス |Microsoft Docs"  

[PreviousVersionsHh771917]: /previous-versions/hh771917(v=vs.85) "addPublicLocalApplicationUri メソッド |Microsoft Docs"  

[PreviousVersionsWindowsAppsHh452771]: /previous-versions/windows/apps/hh452771(v=win.10) "HTTPS 接続 (HTML) を要求する方法 |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh464906]: /previous-versions/windows/apps/hh464906(v=win.10) "アプリ コントラクトと拡張機能 (Windows ランタイム アプリ) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh465006]: /previous-versions/windows/apps/hh465006(v=win.10) "アプリのグローバル化 (HTML) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh465373]: /previous-versions/windows/apps/hh465373(v=win.10) "コンテキスト別の機能と制限 (HTML) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh465380]: /previous-versions/windows/apps/hh465380(v=win.10) "HTML、CSS、JavaScript の機能と相違点 (HTML) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh780594]: /previous-versions/windows/apps/hh780594(v=win.10) "外部 Web ページ (HTML) にリンクする方法 |Microsoft Docs"  

[MDNIframe]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: Inline Frame 要素 |MDN"  
