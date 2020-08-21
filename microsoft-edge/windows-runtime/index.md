---
description: Windows ランタイム (WinRT) を使用して、JavaScript アプリからネイティブ Windows API を呼び出します。
title: JavaScript の Windows ランタイム (WinRT)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/29/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: Windows ランタイム、WinRT、PWA、JavaScript
ms.openlocfilehash: e4b6eab4ecfbd26ccda8ef1c6e51a7a30dfaecfc
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942210"
---
# JavaScript の Windows ランタイム (WinRT)  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

[Windows ランタイム](/windows/uwp/get-started/universal-application-platform-guide#how-the-universal-windows-platform-relates-to-windows-runtime-apis)\(または簡単に WinRT\) は、[すべての Windows 10](/uwp/extension-sdks/device-families-overview)デバイス ファミリにわたって実行される[ユニバーサ](/windows/uwp/get-started/universal-application-platform-guide)ル Windows プラットフォーム \(UWP\) アプリを利用するネイティブ API のコレクションです。  WinRT API は、C#、C++、Visual Basic、JavaScript など、さまざまな言語に関して表示されます。  

Web 開発者は、Web アプリが [インストールされている Windows 10](../progressive-web-apps-edgehtml/windows-features.md#set-up-and-run-your-universal-windows-app) アプリ \(ブラウザー\ でなくプロセスから起動) として実行されているときに、JavaScript からネイティブ Windows API `wwahost.exe` を要求できます。  また、Windows 10 アプリとして実行されている Web サイトでは [、Microsoft Edge WebView](#webview) コントロールを使用して、リモート Web コンテンツや、ブローブやストリーミング処理用 [の MSApp](#msapp) API を表示することもできます。  

すべての Windows 10 アプリで使用できる最上位 WinRT 名前空間領域を次に示します。  

| WinRT 名前空間 | 説明 |  
|:--- |:--- |  
| [AI](/uwp/api/windows.AI.MachineLearning.Preview) \(プレビュー\) | アプリにマシン学習モデルを読み込み、入力としてデータをバインド、結果を評価できるクラスが含まれています。  |  
| [ApplicationModel](/uwp/api/windows.applicationmodel) | コア システム機能のコア機能やアプリ パッケージに関する実行時情報にアクセスし、一時中使用操作を処理します。  |  
| [データ](/uwp/api/windows.data.html) | HTML、JSON、PDF、テキスト、XML など、さまざまなデータ形式を操作するユーティリティ クラスを提供します。  |  
| [デバイス](/uwp/api/windows.devices) | この名前空間を使用すると、ADC、GPIO、I2 C、PWM、SPI など、低レベルのデバイス プロバイダーにアクセスできます。  |  
| [Foundation](/uwp/api/windows.foundation) | 非同期操作の管理やプロパティ ストアへのアクセスなど、基数的な Windows ランタイム機能を有効にします。  この名前空間は、Uniform Resource Identifier \(URI\)、日付と時刻、2-D 測定値、その他の基本的な値を表す共通値の種類も定義します。  |  
| [ゲーム](/uwp/api/windows.gaming.input) |ゲーム コントローラーの入力、ゲーム バー、ゲームのモニタリング、およびゲーム チャットにアクセスできるようにします。  |  
| [グローバリゼーション](/uwp/api/windows.globalization) | 言語プロファイル、地域、国際カレンダーのグローバライ化のサポートを提供します。  |  
| [グラフィックス](/uwp/api/windows.graphics) | グラフィックの描画方法に関する情報を含む基本的なデータ型を提供します。  これらのデータ構造体は、CompositionVirtualDrawingSurface クラスの使用時に大規模なサーフェイスが描画される方法を定義するために使用されます。  |  
| [管理](/uwp/api/windows.management) | モバイル デバイス管理 \(MDM\) デバイスからサーバーへの同期を強化する機能を提供します。  この MDM 同期プロトコルは、Open Mobile Alliance - デバイス管理標準に基づいています。  |  
| [メディア](/uwp/api/windows.media) | 写真、オーディオ録音、ビデオなどのメディアを作成および操作するためのクラスを提供します。  |  
| [ネットワーク](/uwp/api/windows.networking) | ネットワーク アプリで使用されるホスト名とエンドポイントにアクセスできるようにします。  |  
| [パーセプション](/uwp/api/windows.perception) | ユーザーの周囲を認められるクラスが含まれているため、アプリがユーザーの周囲のサーフェスとホログラムに対するデバイスを見つけて理理に合うクラスが含まれている。  |  
| [セキュリティ](/uwp/api/windows.security.authentication.identity) | ユーザー認証、資情報の管理、データ保護機能のクラスを提供します。  |  
| [サービス](/uwp/api/windows.services.cortana) | Cortana、マップ、Microsoft Store、および対象指定 \(サブスクリプション\) コンテンツの Microsoft サービスにアクセスできます。  |  
| [記憶域](/uwp/api/windows.storage) | ファイル、フォルダー、およびアプリケーション設定を管理するクラスを提供します。  |  
| [System](/uwp/api/windows.system) | アプリの起動、ユーザーに関する情報の入手、メモリ プロファイリングなどのシステム機能を有効にします。  |  
| [UI](/uwp/api/windows.ui) | コア システム機能と UI に関するランタイム情報にアクセスできるアプリを提供します。  **注**: 名前空間の API `Windows.UI.Xaml` は JavaScript アプリ \ では使用できません (この場合、等しい Web 標準の標準のテクノロジを使用する場合があります)。  |  
| [Web](/uwp/api/windows.web) | Web サービス操作で発生したエラーに関する情報を提供します。  |  

使用方法の詳細については [、JavaScript で Windows ランタイムを使用して確認してください](./using-the-windows-runtime-in-javascript.md)。  Web サイトを Windows アプリとして実行する方法については [、PWA for Windows](../progressive-web-apps/windows-features.md) チュートリアルを試してください。  

## WebView  

[Microsoft Edge WebView コントロール](../webview.md)を使用すると、Windows 10 アプリ内で Web コンテンツをホストできます。  これは使用におすすめしますが、機能の向上と操作性を制御 `<iframe>` [する機能](../hosting/webview.md#webview-versus-iframe) が多く用意されています。  

## MSApp  

[MSApp](./reference/msapp.md)グローバル オブジェクト \( \( \) は、Web 標準および同等の WinRT オブジェクト タイプ間の変換に使用するユーティリティ関数 `window.MSApp` を提供します。  
