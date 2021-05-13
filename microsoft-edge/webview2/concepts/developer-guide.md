---
description: WebView2 アプリケーションを開発するときに使用する開発のベスト プラクティスについて説明します。
title: WebView2 開発のベスト プラクティス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Webview2、WebView、Webview、エッジ、ベスト プラクティス
ms.openlocfilehash: 5a11f01ec07aea12599c8bdb8428d451ad7bd013
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564750"
---
# <a name="webview2-development-best-practices"></a>WebView2 開発のベスト プラクティス  

すべての開発チームは、アプリケーションを構築する際にさまざまなプラクティスに従います。 WebView2 アプリケーションをビルドする場合は、以下の方法をお勧めします。 この記事では、運用ベースの WebView2 アプリケーションを構築する際の推奨事項とベスト プラクティスについて説明します。

## <a name="use-evergreen-webview2-runtime-recommended"></a>Evergreen WebView2 ランタイムの使用 (推奨)  

固定バージョンには、厳密な互換性要件を持つアプリの使用例があります。通常、Evergreen WebView2 ランタイムの使用をお勧めします。  Evergreen WebView2 ランタイムは自動的に更新され、WebView2 アプリケーションで使用できる最新の機能とセキュリティ パッチが含まれています。 Evergreen WebView2 ランタイムでは、ディスク上の記憶域も少なくする必要があります。

WebView2 アプリケーションを使用する前に、Evergreen WebView2 ランタイムがインストールされていることを確認してください。  詳細については [、「Evergreen WebView2 ランタイムの展開」に移動します][Webview2ConceptsDistributionDeployingEvergreenWebview2Runtime]。  

## <a name="run-compatibility-tests-regularly-when-using-the-evergreen-webview2-runtime"></a>Evergreen WebView2 ランタイムを使用する場合は、互換性テストを定期的に実行する

Evergreen WebView2 ランタイムを使用する場合は、定期的な互換性テストを実行してください。 ランタイムは自動的に更新されますので、WebView2 コントロールの Web コンテンツを、安定しないバージョンの Microsoft Edge に対してテストして、WebView2 アプリケーションが期待した通り実行されます。 このガイダンスは、Web 開発者に提供するガイダンスに似ています。 詳細については、「Evergreen モードで [互換性を持ち続け」に移動します][Webview2ConceptsDistributionStayCompatibleEvergreenMode]。

## <a name="ensure-apis-are-supported-by-the-installed-webview2-runtime"></a>インストールされている WebView2 ランタイムで API がサポートされていることを確認する

WebView2 アプリケーションの実行には、Webview2 SDK と、コンピューターにインストールされている WebView2 ランタイムの両方が必要です。 SDK とランタイムの両方がバージョン管理されています。 API は WebView2 に継続的に追加され続けるので、新しい API をサポートするために、ランタイムの新しいバージョンもリリースされます。 WebView2 アプリケーションで使用される API が、コンピューターにインストールされている WebView2 ランタイムでサポートされていることを確認する必要があります。 

Evergreen WebView2 ランタイムを使用する場合、ランタイムが最新バージョンを使用するために更新されない場合があります。 たとえば、ユーザーがインターネットにアクセスできない場合、ランタイムは、その環境では自動的に更新されません。 さらに、一部のグループ ポリシーを使用すると、WebView2 の更新が一時停止されます。 WebView2 アプリケーションに更新プログラムをプッシュすると、インストールされているランタイムで使用できない新しい API が使用され、アプリケーションが壊れる可能性があります。   
 
この状況を解決するには、コードが API を呼び出す前に、インストールされているランタイムで API の可用性をテストできます。 この新しい機能のテストは、新しい Web API を使用する前にサポートされている機能を検出する他の Web 開発のベスト プラクティスと似ています。 インストールされているランタイムで API の可用性をテストするには、次の値を使用します。  

*   `queryinterface`C/C++ の場合。 
*   .NET または WinUI の try/catch ブロック。 
    
詳細については [、「Determine WebView2 ランタイム要件」に移動します][Webview2ConceptsVersioningDetermineWebview2RuntimeRequirement]。  

## <a name="update-the-fixed-version-runtime"></a>固定バージョン ランタイムの更新  

固定バージョン ランタイムを使用する場合は、セキュリティリスクを軽減するためにランタイムを定期的に更新してください。 Webview2 アプリケーションでサードパーティ製のコンテンツを使用する場合は、常に信頼されていないコンテンツを考慮してください。  詳細については、「固定バージョン配布 [モード」に移動します][Webview2ConceptsDistributionFixedVersionDistributionMode]。  

## <a name="manage-new-versions-of-the-runtime"></a>ランタイムの新しいバージョンを管理する  

Evergreen WebView2 ランタイムの新しいバージョンがデバイスにダウンロードされるたびに、WebView2 アプリケーションを実行すると、ブラウザー プロセスがリリースされるまで、以前のランタイムを使用し続ける必要があります。 この動作により、アプリケーションは継続的に実行され、以前のランタイムが削除されません。 新しいバージョンのランタイムを使用するには、以前の WebView2 環境オブジェクトへのすべての参照を解放するか、アプリケーションを再起動する必要があります。 次に新しい WebView2 環境を作成すると、新しいバージョンが使用されます。

アプリケーションの再起動をユーザーに通知するなどの新しいバージョンが利用可能な場合にアクションを実行するには、コードで [add_NewBrowserVersionAvailable(Win32)][Webview2ReferenceaddNewBrowserVersionAvailable] イベントまたは [CoreWebView2Environment.NewBrowserVersionAvailable(.NET)][Webview2ReferenceNewBrowserVersionAvailable] イベントを使用できます。 コードがアプリケーションの再起動を処理する場合は、WebView2 アプリケーションが終了する前にユーザー状態を保存してください。  

## <a name="manage-the-lifetime-of-the-user-data-folder"></a>ユーザー データ フォルダーの有効期間を管理する 
WebView2 アプリは、Cookie、資格情報、アクセス許可などのデータを格納するユーザー データ フォルダーを作成します。 フォルダーを作成した後、アプリは、アプリのアンインストール時のクリーンアップなど、ユーザー データ フォルダーの有効期間を管理します。  詳細については、「ユーザー データ フォルダー [の管理」に移動します][Webview2ConceptsUserDataFolder]。  

## <a name="follow-recommended-webview2-security-best-practices"></a>推奨される WebView2 セキュリティのベスト プラクティスに従う 
WebView2 アプリケーションの場合は、推奨される WebView2 セキュリティのベスト プラクティスに従ってください。  詳細については、「セキュリティで保護された [WebView2 アプリケーションを開発するためのベスト プラクティス」に移動します][Webview2ConceptsSecurity]。  

<!-- links -->  

[Webview2ConceptsDistributionDeployingEvergreenWebview2Runtime]: ../concepts/distribution.md#deploying-the-evergreen-webview2-runtime "Evergreen WebView2 ランタイムの展開 - WebView2 ランタイムを使用したアプリ|Microsoft Docs"  
[Webview2ConceptsDistributionFixedVersionDistributionMode]: ../concepts/distribution.md#fixed-version-distribution-mode "固定バージョン配布モード - WebView2 アプリケーションを使用したアプリ|Microsoft Docs"  
[Webview2ConceptsDistributionStayCompatibleEvergreenMode]: ../concepts/distribution.md#stay-compatible-in-evergreen-mode "Evergreen モードで互換性を持つ - WebView2 を使用したアプリの配布 |Microsoft Docs"  
[Webview2ConceptsSecurity]: ../concepts/security.md "セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス |Microsoft Docs"  
[Webview2ConceptsUserDataFolder]: ../concepts/user-data-folder.md "[ユーザー データ フォルダーの管理] |Microsoft Docs"  
[Webview2ConceptsVersioningDetermineWebview2RuntimeRequirement]: ../concepts/versioning.md#determine-webview2-runtime-requirement "WebView2 ランタイム要件の決定 - WebView2 SDK のバージョンの|Microsoft Docs"  
[Webview2GetStartedWin32]: ../get-started/win32.md "WebView2 の使用を|Microsoft Docs"  
[Webview2GetStartedWinforms]: ../get-started/winforms.md "WebView2 の使用を開始するには、Windowsフォーム|Microsoft Docs"  
[Webview2GetStartedWinui]: ../get-started/winui.md "WinUI 3 (プレビュー) の WebView2 の使用を開始|Microsoft Docs"  
[Webview2GetStartedWpf]: ../get-started/wpf.md "WPF サーバーでの WebView2 の|Microsoft Docs"  

[Webview2ReferenceaddNewBrowserVersionAvailable]: /microsoft-edge/webview2/reference/win32/icorewebview2environment#add_newbrowserversionavailable "add_NewBrowserVersionAvailable |Microsoft Docs"  

[Webview2ReferenceNewBrowserVersionAvailable]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.newbrowserversionavailable "CoreWebView2Environment.NewBrowserVersionAvailable イベント |Microsoft Docs"  
