---
title: JavaScript を使った Windows ランタイムアプリのエラーコード
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: 7aad8577d79bc5612f526e4e2bf1ceb0f2c2929a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570791"
---
# JavaScript を使った Windows ランタイムアプリのエラーコード  

JavaScript を使った Windows ランタイムアプリの開発時に Microsoft Visual Studio 本体によって表示されるエラーコードを以下に示します。  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9601: " *Remoteuri*を読み込むことができません。  アプリは、ローカルコンテキストのリモート web コンテンツを読み込めません。 " | Web コンテキストで許可される内容について詳しくは、「[コンテキストによる機能と制限][PreviousVersionsWindowsAppsHh465373]」をご覧ください。  |  
| APPHOST9602: "' javascript: ' は無効な属性値であり、無視されます。  ローカルコンテキストで ' javascript: ' Uri を使わないでください。 | セキュリティ上の理由から、ローカルコンテキストで ' javascript: ' Uri を使用することはできません。  ローカルコンテキストで許可される内容について詳しくは、「[コンテキストによる機能と制限][PreviousVersionsWindowsAppsHh465373]」をご覧ください。  |  
| APPHOST9603: "クラス ID *classID*を持つ ActiveX プラグインを読み込むことができません。  アプリは ActiveX コントロールを読み込めません。 " | JavaScript を使った Windows ランタイムアプリでは、カスタムの Microsoft ActiveXcontrols はサポートされていません。  UI コントロールが必要な場合は、標準の web コントロール、コントロールライブラリ、または独自のカスタムコントロールを作成します。  カスタムロジックを実行する必要がある場合は、代わりにカスタムの Windows ランタイムオブジェクトを作成します。  HTML、CSS、JavaScript のその他の相違点については、 [html、css、javascript の機能と相違点][PreviousVersionsWindowsAppsHh465380]について説明します。  |  
| APPHOST9604: "無効な文字エンコードを使用しているため、 *uri*に移動できません。  アプリは、UTF8 でエンコードされたファイルにのみ移動できます。 " | Windows ランタイムによってアクセスされるすべての HTML、JavaScript、CSS は、8ビット Unicode 変換形式 (UTF-8) としてエンコードする必要があります。  HTML、CSS、JavaScript のその他の相違点については、 [html、css、javascript の機能と相違点][PreviousVersionsWindowsAppsHh465380]について説明します。  |  
| APPHOST9605: 移動先の URI がセキュリティゾーンの上位にあるため、" *sourceuri*から*TargetURI*に移動できません。  Web コンテキストの URI からローカルコンテキストの URI に移動する場合や、ローカルコンテキストの URI を MSApp Localapplicationuri メソッドとして登録している場合を除き、セキュリティがより低いゾーンからゾーンに移動することはできません。 " | 詳しくは、 [Msapp Localapplicationuri][PreviousVersionsHh771917]に関する情報をご覧ください。  |  
| APPHOST9606: "HTTP 接続を使用していて、ms-chap 接続のみの meta 要素が存在するため、 *uri*を読み込めません。  Https 接続のみの meta 要素を使う場合、HTTPS 接続のみが許可されます。  HTTPS 接続を使用するか、またはセキュリティで保護された接続が必要でない場合は、meta 要素を削除します。 | 詳細については、「 [HTTPS 接続を要求する方法][PreviousVersionsWindowsAppsHh452771]」を参照してください。  |  
| APPHOST9607: "このエラー: *Failurecode*" のため、 *uri*で uri を起動できません。 " | このエラーの一般的な原因は、不足しているリソースまたは無効なファイルです。  |  
| APPHOST9608: "このエラー: *errorCode*" のため、アプリは [バージョン情報] の空白のページに移動できませんでした。 " |  |  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9610: "アプリは、カスタムエラーページへのナビゲートの準備中にエラーを検出しました: *errorCode*" |  |  
| APPHOST9611: "エラー: *errorCode*" というエラーが発生したため、アプリはカスタムエラーページに移動できませんでした。 " |  |  
| APPHOST9613: "このエラーのため、アプリは*uri*に移動できませんでした: *errorCode*" |  |  
| APPHOST9614: "iframe 内のドキュメントで*Requesteddocmode* doc モードが要求されていますが、システムは現在のところ*docmode* doc モードを強制します。  Iframe では、 *Currentdocmode* doc モードが使用されます。 " | リモート web コンテンツの表示について詳しくは、「[外部の web ページへのリンクを設定する方法][PreviousVersionsWindowsAppsHh780594]」をご覧ください。  |  
| APPHOST9615: "アプリは、ローカルコンテキストの外部でプログラムで呼び出されたため、 *uri*でファイルをダウンロードできません。" | Web コンテキストのコンテンツでファイルをプログラムによってダウンロードしようとしたときに発生します。  |  
| APPHOST9616: "この URI は、位置情報 Api を使用できません。  位置情報 Api は、パッケージの一部である URI か、マニフェストの ApplicationContentUris 要素に含まれている URI からのみ呼び出すことができます。 " | Web コンテキストで許可される内容について詳しくは、「[コンテキストによる機能と制限][PreviousVersionsWindowsAppsHh465373]」をご覧ください。  |  
| APPHOST9617: "この URI はクリップボード Api を使用できません。  クリップボード Api は、パッケージの一部である URI か、マニフェストの ApplicationContentUris 要素に含まれている URI からのみ呼び出すことができます。 " | Web コンテキストで許可される内容について詳しくは、「[コンテキストによる機能と制限][PreviousVersionsWindowsAppsHh465373]」をご覧ください。  |  
| APPHOST9618: "この URI は window を使用できません。  Window close メソッドを呼び出すことができるのは、ms appx URI スキームを使って読み込まれたパッケージ化されたコンテンツからのみです。 " | Web コンテキストで許可される内容について詳しくは、「[コンテキストによる機能と制限][PreviousVersionsWindowsAppsHh465373]」をご覧ください。  |  
| APPHOST9619: "web コンテキストのページをアプリの最上位レベルのドキュメントにすることができないため、アプリは*uri*に移動できません。  代わりに、iframe にページを読み込みます。 " | トップレベルのページをリモート web ページに移動することはできませんが、アプリで[iframe][MDNIframe]に web ページを表示することはできます。  リモート web コンテンツの表示について詳しくは、「[外部の web ページへのリンクを設定する方法][PreviousVersionsWindowsAppsHh780594]」をご覧ください。  |  

| エラー | 注釈 |  
|:--- |:--- |  
| APPHOST9620: "このアプリは、HTTP 接続を使用していて、ms https-接続のみの meta 要素が存在するため、閉じられました。  Https 接続のみの meta 要素を使う場合、HTTPS 接続のみが許可されます。  HTTPS 接続を使うか、またはセキュリティで保護された接続を必要としない場合は、meta 要素を削除します。 " | 詳細については、「 [HTTPS 接続を要求する方法][PreviousVersionsWindowsAppsHh452771]」を参照してください。  |  
| APPHOST9623: "このエラーのため、アプリは*Url*を解決できませんでした。" というエラーが表示*されます*。 | このエラーの一般的な原因として、ファイルが見つからないことが考えられます。  |  
| APPHOST9624: url が別のアプリを起動するため、アプリはスクリプトを使用して*url* url を読み込めません。  直接ユーザー操作のみが別のアプリを起動できます。 " | アプリでは、他のアプリを直接起動することはできません。  アプリが特定のコントラクトを実装するときに、ユーザーが他のアプリを起動することができます。  詳しくは、[アプリ コントラクトと拡張機能][PreviousVersionsWindowsAppsHh464906]についてのページをご覧ください。  |  
| APPHOST9626: "リソースファイルへの直接参照 `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png` が検出されました。  この参照では、デバッグ環境以外で使用するとエラーが発生します。」 | この PNG ファイルは、のファイルパスのために `logo.scale-140.png` ローカライズされたリソースとして扱われるため、ローカライズされたリソースのエラーは直接参照できません。  このファイルを言語リソースとして使用する場合は、「[アプリをグローバライズする (HTML)][PreviousVersionsWindowsAppsHh465006] 」をご覧ください。  それ以外の場合は、問題のあるディレクトリの名前を変更してみてください。  |  

## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- image links -->  

<!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "JavaScript での Windows ランタイムの使用"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator クラス"  

[PreviousVersionsHh771917]: /previous-versions/hh771917(v=vs.85) "addPublicLocalApplicationUri メソッド"  

[PreviousVersionsWindowsAppsHh452771]: /previous-versions/windows/apps/hh452771(v=win.10) "HTTPS 接続を要求する方法 (HTML)"  
[PreviousVersionsWindowsAppsHh464906]: /previous-versions/windows/apps/hh464906(v=win.10) "アプリコントラクトと拡張機能 (Windows ランタイムアプリ)"  
[PreviousVersionsWindowsAppsHh465006]: /previous-versions/windows/apps/hh465006(v=win.10) "アプリをグローバライズする (HTML)"  
[PreviousVersionsWindowsAppsHh465373]: /previous-versions/windows/apps/hh465373(v=win.10) "コンテキストによる機能と制限 (HTML)"  
[PreviousVersionsWindowsAppsHh465380]: /previous-versions/windows/apps/hh465380(v=win.10) "HTML、CSS、JavaScript の機能と相違点 (HTML)"  
[PreviousVersionsWindowsAppsHh780594]: /previous-versions/windows/apps/hh780594(v=win.10) "外部 web ページへのリンクを設定する方法 (HTML)"  

[MDNIframe]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: インラインフレームの要素 |MDN"  
