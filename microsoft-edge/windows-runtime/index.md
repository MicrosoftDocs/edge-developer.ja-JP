---
description: Windows ランタイム (WinRT) を使って、JavaScript アプリからネイティブ Windows Api を呼び出します。
title: JavaScript の Windows ランタイム (WinRT)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: Windows ランタイム、WinRT、PWA、JavaScript
ms.openlocfilehash: 4ca92323a85a1e90896b4de26778f7cf7dfc9a11
ms.sourcegitcommit: e07de36ee9fbe20422ffc2c62b98839851e1b02b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "10604023"
---
# JavaScript の Windows ランタイム (WinRT)  

[Windows ランタイム](/windows/uwp/get-started/universal-application-platform-guide#how-the-universal-windows-platform-relates-to-windows-runtime-apis)\ (または単に WinRT \) は、すべての[windows 10 デバイスファミリ](/uwp/extension-sdks/device-families-overview)で実行される[ユニバーサル Windows プラットフォーム](/windows/uwp/get-started/universal-application-platform-guide)(UWP) アプリに電力を供給するネイティブ api のコレクションです。  WinRT Api は、C#、C++、Visual Basic、JavaScript など、さまざまな言語に投影されています。  

Web 開発者は、web アプリがインストールされている[windows 10 アプリとして実行](../progressive-web-apps-edgehtml/windows-features.md#set-up-and-run-your-universal-windows-app)されている場合、これらのネイティブ windows Api を JavaScript から要求することができ `wwahost.exe` ます (ブラウザーではなくプロセスから起動します)。  さらに、Windows 10 アプリとして実行されている web サイトでは、 [Microsoft Edge webview](#webview)コントロールを使って、リモートとローカルの web コンテンツ、および blob とストリーム処理用の[msapp](#msapp) api を表示することもできます。  

以下は、すべての Windows 10 アプリで利用可能なトップレベルの WinRT 名前空間領域です。  

| WinRT 名前空間 | 説明 |  
|:--- |:--- |  
| [AI](/uwp/api/windows.AI.MachineLearning.Preview) \ (プレビュー \) | アプリが機械の学習モデルを読み込み、データを入力としてバインドし、結果を評価できるようにするクラスが含まれています。  |  
| [Windows.applicationmodel.chat](/uwp/api/windows.applicationmodel) | アプリパッケージに関するコアシステムの機能と実行時の情報へのアクセスを提供し、中断操作を処理します。  |  
| [データ](/uwp/api/windows.data.html) | HTML、JSON、PDF、テキスト、XML など、さまざまなデータ形式を操作するためのユーティリティクラスを提供します。  |  
| [デバイス](/uwp/api/windows.devices) | この名前空間は、ADC、GPIO、I2 C、PWM、SPI などの下位レベルのデバイスプロバイダーへのアクセスを提供します。  |  
| [Foundation](/uwp/api/windows.foundation) | 非同期操作の管理やプロパティストアへのアクセスなど、Windows ランタイムの基本的な機能を有効にします。  また、この名前空間は、Uniform Resource Identifier \ (URI \)、日付と時刻、2-d の測定値、その他の基本的な値を表す一般的な値型を定義します。  |  
| [ゲーム](/uwp/api/windows.gaming.input) |ゲームコントローラーの入力、ゲームバー、ゲーム監視、ゲームチャットへのアクセスを提供します。  |  
| [グローバリゼーション](/uwp/api/windows.globalization) | 言語プロファイル、地理的地域、および国際カレンダーのグローバリゼーションのサポートを提供します。  |  
| [グラフィックス](/uwp/api/windows.graphics) | グラフィックスを描画する方法についての情報を含む基本的なデータ型が用意されています。  通常、これらのデータ構造体は、CompositionVirtualDrawingSurface クラスを使用するときに大きなサーフェスを描画する方法を定義するために使われます。  |  
| [管理](/uwp/api/windows.management) | モバイルデバイス管理 \ (MDM \) デバイスからサーバーへの同期を強制する機能を提供します。  この MDM 同期プロトコルは、オープンなモバイルアライアンスデバイス管理標準に基づいています。  |  
| [メディア](/uwp/api/windows.media) |写真、オーディオ録音、ビデオなどのメディアを作成して操作するためのクラスが用意されています。  |  
| [ネットワーク](/uwp/api/windows.networking) |ネットワークアプリで使用されるホスト名とエンドポイントへのアクセスを提供します。  |  
| [印象](/uwp/api/windows.perception) |ユーザーの周囲を perceiving するためのクラスが含まれています。このクラスには、ユーザーの周囲のサーフェスやホログラムに関連するデバイスをアプリで見つけて、その理由を示します。  |  
| [セキュリティ](/uwp/api/windows.security.authentication.identity) | ユーザー認証、資格情報管理、暗号化操作、およびエンタープライズデータ保護機能のクラスを提供します。  |  
| [サービス](/uwp/api/windows.services.cortana) |Cortana、マップ、Microsoft ストア、および対象指定の \ (サブスクリプション \) コンテンツのための Microsoft サービスへのアクセスを提供します。  |  
| [記憶域](/uwp/api/windows.storage) |ファイル、フォルダー、アプリケーション設定を管理するためのクラスが用意されています。  |  
| [システム](/uwp/api/windows.system) |アプリの起動、ユーザーに関する情報の取得、メモリのプロファイリングなどのシステム機能を有効にします。  |  
| [UI](/uwp/api/windows.ui) | UI に関するコアシステムの機能と実行時の情報へのアクセスをアプリに提供します。  **注**: `Windows.UI.Xaml` 名前空間の Api は、JavaScript アプリでは使用できません (この場合、対応する web 標準テクノロジを使用している可能性があります)。  |  
| [Web](/uwp/api/windows.web) | Web サービスの操作に起因するエラーについて説明します。  |  

使い方について詳しくは、「 [JavaScript での Windows ランタイムの使用](./using-the-windows-runtime-in-javascript.md)」をご覧ください。  Windows アプリとして web サイトを実行する方法については、「 [windows 版の PWA のカスタマイズ](../progressive-web-apps/windows-features.md)」チュートリアルを参照してください。  

## WebView  

[Microsoft Edge WebView](../webview.md)コントロールでは、Windows 10 アプリ内で web コンテンツをホストすることができます。  これは、の使用に似てい `<iframe>` ますが、より多くの機能を提供し、エクスペリエンスを[制御し](../hosting/webview.md#webview-versus-iframe)ます。  

## MSApp  

[Msapp](./reference/msapp.md) global オブジェクト \ ( `window.MSApp` \) には、web 標準ベースと同等の WinRT オブジェクト型の間で変換するためのユーティリティなど、JavaScript ベースの Windows 10 アプリ用のさまざまなヘルパー関数が用意されています。  
