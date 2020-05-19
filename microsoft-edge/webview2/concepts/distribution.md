---
description: Microsoft Edge WebView2 を使用してアプリをリリースするときの配布オプション
title: Microsoft Edge WebView2 アプリケーションの配布
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: a789b0f4f9c482670f843ed21368b4168f99abe0
ms.sourcegitcommit: 5bdffe91a6594f77eeffa4e864fda90a02784771
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "10659713"
---
# WebView2 を使用したアプリケーションの配布 

WebView2 コントロールでは、Microsoft Edge \ (Chromium \) ブラウザーが利用されています。 アプリを配布するときに、アプリケーションが実行されるすべてのユーザーコンピューターに Edge ブラウザーがインストールされていることを確認します。 WebView2 コントロールでは、コンピューターにインストールされている、最も安定したバージョンのブラウザーを使用します。 たとえば、安定性の高いベータ、開発、またはカナリアが同時にインストールされている可能性があり、この場合、WebView2 コントロールは安定したチャネルで実行されます。 WebView2 コントロールを実行しているコンピューターにインストールされているブラウザーのバージョンが最小バージョンの要件を満たしていることを確認して、リリースノートを確認してください。

## ロードマップ

アプリケーションが実行されるすべてのユーザーコンピューター、または組織全体で Edge ブラウザーをインストールすることが難しい場合があることを認識しています。 インストールされている Microsoft Edge ブラウザーに関係なく、すべてのコンピューターでアプリケーションが実行されるようにするには、Microsoft Edge WebView2 ランタイムをリリースします。 また、インストールされているブラウザーのプレリリース版を検索する前に、WebView2 を更新してランタイムの安定バージョンを検索します。

WebView2 Runtime: evergreen と fixed バージョンを使った2つの配布オプションがサポートされます。

Evergreen は、ほとんどの開発者に推奨される配布モデルです。 このモードでは、アプリケーションの作業を追加しなくても、更新プログラムは WebView2 ランタイムに自動的にプッシュされます。 Evergreen モデルを使用すると、アプリは、ホストされた web コンテンツの最新機能とセキュリティ更新プログラムを利用できるようになります。

制約のある環境の場合、固定バージョンの配布モデルがサポートされます。 このモデルでは、アプリケーションで特定のバージョンの WebView2 を選択してパッケージ化します。 WebView バージョンの更新プログラムは自動的には発生しません。また、アプリケーションの責任となります。 修正されたバージョンモデルは、ブラウザーのバージョンを制御する必要がある場合や、アプリケーションを更新する場合に便利です。 

### Microsoft Edge WebView2 ランタイム

Microsoft Edge WebView2 ランタイムは、WebView2 アプリケーションで使用するために最適化されたブラウザーのバイナリをパッケージ化します。 クライアント Edge ブラウザーがインストールされている単体または並行して機能します。 ランタイムを1回インストールすると、クライアントコンピューターで実行されている多くの WebView2 アプリケーションがサポートされます。 ランタイムのインストールは、ブラウザーとしてエンドユーザーには表示されず、デスクトップショートカット、スタートメニューのエントリポイント、またはプロトコルの登録も行われません。

WebView2 ランタイムを使うアプリケーションは、ランタイムのインストールが完了していることを確認する必要があります。 アプリケーションが依存関係としてランタイムをインストールするようにするために、ランタイムをインストールフローに追加することができます。 
