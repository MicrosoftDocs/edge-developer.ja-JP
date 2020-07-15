---
description: Microsoft Edge WebView2 を使用してアプリをリリースするときの配布オプション
title: Microsoft Edge WebView2 アプリケーションの配布
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 1b7ebf9dde594b7cdac3b41915fa9d9187d09da1
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879178"
---
# WebView2 を使用したアプリケーションの配布  

WebView2 コントロールでは、Microsoft Edge \ (Chromium \) プラットフォームが利用されます。  アプリをパッケージ化して配布する場合は、アプリが起動される前にプラットフォームまたは WebView2 ランタイムのコピーが存在することを確認してください。  次のページでは、お客様が WebView2 ランタイムをインストールして、WebView2 アプリケーション用に2つの配布モードを使用する方法について説明します。 [Evergreen](#evergreen-distribution-mode)と[修正バージョン](#fixed-version-distribution-mode)。  

## Evergreen 配布モード  

Evergreen 配布モードでは、アプリが最新の機能とセキュリティ更新プログラムを利用していることが保証されます。  Evergreen 配布モードには、次の特徴があります。  

*   Web platform は、追加の作業を行わなくても自動的に更新されます。  
*   Evergreen 配布モードを利用するすべてのアプリケーションでは、プラットフォームのバイナリの共有コピーが使用されます。これにより、ディスク領域を節約できます。  

アプリケーションが web プラットフォームとして使用できるチャネル WebView2 は複数あります。  既定では、WebView2 は、WebView2 SDK の最小バージョン要件を満たすデバイスで利用可能な最も安定したチャネルをターゲットとしています。  以下のチャネルは、安定していないチャネルの順に一覧表示されています。  

1.  WebView2 ランタイム \ (プレビュー \)  
1.  Microsoft Edge Beta チャネル  
1.  Microsoft Edge Dev チャネル  
1.  Microsoft Edge Canary チャネル    

> [!NOTE]
> ほとんどの開発者は、evergreen の配布モデルをお勧めします。  

> [!IMPORTANT]
> Microsoft Edge の安定したチャネルは、WebView2 の有効なターゲットではないため、この理由については後で説明します。  

バージョン管理の詳細については、「[バージョン管理][ConceptsVersioning]と[グローバル][ReferenceWin3209538WebviewIdl]化」を参照してください。  

### WebView2 のランタイムとインストーラーについて (プレビュー)  

アプリケーションが実行されているすべてのユーザーコンピューターに Microsoft Edge の厩舎チャネルがインストールされていない可能性があります。  ユーザーが Microsoft Edge をインストールする必要がないように、アプリケーションでは Evergreen WebView2 Runtime および Installer \ (Preview \) を使うことができます。  WebView2 Runtime は、WebView2 アプリケーションを実行するために使用される Microsoft Edge バイナリのカスタマイズされたコピーです。  WebView2 ランタイムがインストールされている場合、ユーザーは通常のブラウザーとして使用することはできません。  たとえば、デスクトップショートカット、スタートメニューエントリがない場合、ユーザーはランタイムバイナリを使用してブラウザーウィンドウを開くことはできません。  デバイス上のすべての Evergreen WebView2 アプリケーションは、単一の Evergreen WebView2 ランタイムインストールを使用する場合があります。  

現在、プレビュー中に、Evergreen WebView2 Runtime と Microsoft Edge Dev チャネルが同時に更新され、同じビルドが存在します。  プレビュー中に、WebView2 チームは WebView2 ランタイムを更新して、Microsoft Edge ベータチャネルと同じビルドを一致させます。  今後、WebView2 が一般的な可用性 \ (GA) に達すると、WebView2 チームは WebView2 ランタイムの更新を計画し、Microsoft Edge の厩舎チャネルと同じビルドを一致させます。  GA 後、アプリケーションでは、WebView2 ランタイムを運用環境で使用する必要があります。  

> [!IMPORTANT]
> プレビュー中に WebView2 アプリケーションを運用環境に出荷しないでください。  

アプリケーションが起動する前に、Evergreen WebView2 Runtime がインストールされていることを確認することをお勧めします。 ワークフローの例を次に示します。  

1.  最新の[Evergreen WebView2 ランタイムインストーラー][Webview2Installer]をダウンロードします。  
1.  アプリケーションのインストーラーまたはアップデーターにインストーラーを含めます。  
1.  アプリケーションのインストールまたは更新時に、 [GetAvailableCoreWebView2BrowserVersionString](../reference/win32/0-9-538/webview2-idl.md#getavailablecorewebview2browserversionstring) API を使って、ユーザーのコンピューターに Evergreen WebView2 Runtime が既にインストールされているかどうかを確認し、VERSIONINFO が NULL であるかどうかを確認します。 インストールされていない場合は、アプリケーションのインストーラー/アップデーターによって、昇格したプロセスまたはコマンドプロンプトからランタイムインストーラーを自動的に呼び出すことができ `MicrosoftEdgeWebView2RuntimeInstallerX64.exe /silent /install` ます。 

シナリオによっては、上記のワークフローを変更する必要がある場合があります。  たとえば、アプリケーションのインストーラーでは、アプリケーションパッケージに Evergreen WebView2 Runtime Installer を含める代わりに、インストーラーをダウンロードすることができます。  

> [!NOTE]
> WebView2 Runtime インストーラーと WebView2 Runtime インストーラーの両方がプレビューに表示されています。  プレビューには、初期スコープが限定されています。また、x64 の Windows 10 では、スタンドアロンのマシン単位インストールとしてのみ使用できます。  将来的には、Windows 7、x86、および ARM64 のサポートが計画されています。  

### WebView2 Runtime と非安定した Microsoft Edge チャネルを使用するためのベストプラクティス  

プレビュー時には、次の推奨事項について検討してください。  

*   [Evergreen WebView2 Runtime と Installer][Webview2Installer]を使って、パッケージ化パイプラインと配布パイプラインを開発またはテストしてください。  今後は、運用アプリケーションにインストーラーを含める必要があります。  
*   アプリケーションを開発するには、Evergreen WebView2 ランタイムを使うことができます。  ただし、ランタイムは Dev チャネルからベータチャネルまたは安定したチャネルにシフトするため、ランタイムビルド番号は最新の preview WebView2 SDK 最小バージョン要件を満たしていない可能性があります。  最新の SDK を使用する場合は、Microsoft Edge カナリアチャネルをインストールして、デバイスで互換性のあるビルドが利用できることを確認します。  バージョン管理の詳細については、「[バージョン管理][ConceptsVersioning]」を参照してください。  
*   安定したチャネルで利用できないプラットフォームに対する変更と互換性のある web コンテンツをテストするには、必要に応じて、適切でない非安定チャネルを使用します。  

## 固定バージョンの配布モード  

> [!NOTE]
> 固定バージョンの配布モデルは現在利用できません。  

制限された環境では、固定バージョン \ (以前は "独自の \" 配布モード) をサポートする予定です。  修正済みのバージョン配布モードでは、特定のバージョンの WebView2 ランタイムを選択してパッケージ化することができます。  修正されたバージョンの配布モードでは、どのバージョンの WebView2 ランタイムをアプリケーションで使うか、ユーザーコンピューターが更新されるタイミングを制御することができます。  修正済みのバージョン配布モードでは、自動更新は取得されません。また、手動で更新プログラムを適用することを計画する必要があります。  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[ReferenceWin3209538WebviewIdl]: ../reference/win32/0-9-538/webview2-idl.md  "Globals |Microsoft ドキュメント"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 Installer"  
