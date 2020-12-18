---
description: Windows ランタイム (WinRT) を使用して、JavaScript アプリからネイティブの Windows API を呼び出します。
title: JavaScript 用 Windows ランタイム (WinRT)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: Windows ランタイム、WinRT、PWA、JavaScript
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3bd67f052d0a836c754f7b58d0625e09ae8781cd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235073"
---
# JavaScript 用 Windows ランタイム (WinRT)  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

[Windows ランタイム](/windows/uwp/get-started/universal-application-platform-guide#how-the-universal-windows-platform-relates-to-windows-runtime-apis)\(または単に WinRT\) は、すべての[Windows 10](/uwp/extension-sdks/device-families-overview)デバイス ファミリにわたって実行されるユニバーサル[Windows プラットフォーム](/windows/uwp/get-started/universal-application-platform-guide)\(UWP\) アプリをサポートするネイティブ API のコレクションです。  WinRT API は、C#、C++、Visual Basic、JavaScript など、さまざまな言語に投影されます。  

Web 開発者は、Web アプリがインストール済み[Windows 10](../progressive-web-apps/windows-features.md#set-up-and-run-your-universal-windows-app)アプリ \(ブラウザー\ ではなくプロセスから起動) として実行されている場合に、JavaScript からこれらのネイティブ Windows API を要求できます。 `wwahost.exe`  さらに、Windows 10 アプリとして実行されている Web サイトでは [、Microsoft Edge Webview](#webview) コントロールを使用してリモートおよびローカルの Web コンテンツを表示し、BLOB とストリームの処理用 [に MSApp](#msapp) API を表示することもできます。  

次に、すべての Windows 10 アプリで使用できるトップ レベルの WinRT 名前空間領域を示します。  

| WinRT 名前空間 | 説明 |  
|:--- |:--- |  
| [AI](/uwp/api/windows.AI.MachineLearning.Preview) \(Preview\) | アプリが機械学習モデルを読み込み、入力としてデータをバインドし、結果を評価できるクラスが含まれています。  |  
| [ApplicationModel](/uwp/api/windows.applicationmodel) | アプリパッケージに関するコア システム機能と実行時情報へのアクセスをアプリに提供し、中断操作を処理します。  |  
| [データ](/uwp/api/windows.data.html) | HTML、JSON、PDF、テキスト、XML など、さまざまなデータ形式を操作するユーティリティ クラスを提供します。  |  
| [デバイス](/uwp/api/windows.devices) | この名前空間は、ADC、GPIO、I2 C、PWM、SPI など、低レベルのデバイス プロバイダーへのアクセスを提供します。  |  
| [Foundation](/uwp/api/windows.foundation) | 非同期操作の管理やプロパティ ストアへのアクセスなど、基本的な Windows ランタイム機能を有効にします。  この名前空間は、Uniform Resource Identifier \(URI\)、日付と時刻、2-D 測定値、その他の基本的な値を表す共通の値の型も定義します。  |  
| [ゲーム](/uwp/api/windows.gaming.input) |ゲーム コントローラーの入力、ゲーム バー、ゲームの監視、ゲーム チャットへのアクセスを提供します。  |  
| [グローバリゼーション](/uwp/api/windows.globalization) | 言語プロファイル、地域、および国際カレンダーのグローバリゼーション サポートを提供します。  |  
| [グラフィックス](/uwp/api/windows.graphics) | グラフィックスの描画方法に関する情報を含む基本的なデータ型を提供します。  これらのデータ構造体は、CompositionVirtualDrawingSurface クラスを使用するときに大きなサーフェスを描画する方法を定義するために一般的に使用されます。  |  
| [管理](/uwp/api/windows.management) | モバイル デバイス管理 \(MDM\) デバイスからサーバーへの同期を強制する機能を提供します。  この MDM 同期プロトコルは、Open Mobile Alliance - Device Management 標準に基づいて作成されます。  |  
| [Media](/uwp/api/windows.media) | 写真、オーディオ録音、ビデオなどのメディアを作成して操作するためのクラスを提供します。  |  
| [ネットワーク](/uwp/api/windows.networking) | ネットワーク アプリで使用されるホスト名とエンドポイントへのアクセスを提供します。  |  
| [認識](/uwp/api/windows.perception) | ユーザーの周囲を認識するためのクラスが含まれています。アプリは、ユーザーの周囲のサーフェスやホログラムを基準にデバイスを見つけて理由を特定できます。  |  
| [セキュリティ](/uwp/api/windows.security.authentication.identity) | ユーザー認証、資格情報の管理、暗号化操作、およびエンタープライズ データ保護機能のクラスを提供します。  |  
| [サービス](/uwp/api/windows.services.cortana) | Cortana、マップ、Microsoft Store、対象指定 \(サブスクリプション\) コンテンツの Microsoft サービスへのアクセスを提供します。  |  
| [記憶域](/uwp/api/windows.storage) | ファイル、フォルダー、およびアプリケーション設定を管理するためのクラスを提供します。  |  
| [System](/uwp/api/windows.system) | アプリの起動、ユーザーに関する情報の取得、メモリ プロファイリングなどのシステム機能を有効にする。  |  
| [UI](/uwp/api/windows.ui) | UI に関するコア システム機能と実行時情報にアクセスできるアプリを提供します。  **注**: 名前空間内の API は、JavaScript アプリ \(同等の Web 標準ベースのテクノロジを使用する可能性があります\) `Windows.UI.Xaml` では使用できません。  |  
| [Web](/uwp/api/windows.web) | Web サービスの操作に起因するエラーに関する情報を提供します。  |  

使用方法について詳しくは [、JavaScript での Windows ランタイムの使用に関するページをご覧ください](./using-the-windows-runtime-in-javascript.md)。  Web サイトを Windows アプリとして実行する方法については、「Windows 用に PWA を調整 [する」チュートリアルをご覧](../progressive-web-apps/windows-features.md) ください。  

## WebView  

[Microsoft Edge WebView](../hosting/webview/index.md)コントロールを使用すると、Windows 10 アプリ内で Web コンテンツをホストできます。  これは an の使用に似ていますが、より多くの機能を提供し、エクスペリエンス `<iframe>` [を](../hosting/webview/index.md#webview-versus-iframe) 制御します。  

## MSApp  

[MSApp](./reference/msapp.md)グローバル オブジェクト \( \) は、Web 標準ベースと同等の WinRT オブジェクト型を変換するためのユーティリティなど、JavaScript ベースの Windows 10 アプリにさまざまなヘルパー関数を提供します。 `window.MSApp`  
