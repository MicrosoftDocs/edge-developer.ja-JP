---
description: Microsoft Edge (Chromium) 拡張機能の構築と公開の概要。
title: Microsoft Edge (Chromium) 拡張機能の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge、拡張機能の開発、ブラウザーの拡張機能、アドオン、パートナー センター、開発者、Chromium の拡張機能
ms.openlocfilehash: 3ed0871883acfb7c3cf08c2da9f47d18ae3465f0
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327527"
---
# Microsoft Edge (Chromium) 拡張機能の概要  

拡張機能は、\(a developer\) が Microsoft Edge \(Chromium\) の機能を追加または変更するために使用する小さなプログラムです。  拡張機能は、ユーザーの毎日の閲覧エクスペリエンスを向上することを目的とします。  ターゲットのユーザーが重要視するニッチな機能を提供します。  

次のいずれかの条件に基づくアイデアや製品がある場合は、拡張機能を作成できます。  

*   特定の Web ブラウザー。  
*   特定の Web ページの機能の改善。  
    
コンパニオン エクスペリエンスの例としては、アド ブロッカーやパスワード マネージャーなどがあります。  

拡張機能は、通常の web アプリと同じように構成されています。  少なくとも、次の機能を含める必要があります。

*   基本的なプラットフォーム情報を含むアプリ マニフェスト JSON ファイル。  
*   機能を定義する JavaScript ファイル。  
*   ユーザー インターフェイスを定義する HTML ファイルと CSS ファイル。  

ウィンドウやタブなど、ブラウザーの一部を直接操作するには、API リクエストを送信し、多くの場合、名前でブラウザーを参照する必要があります。  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 拡張機能" lightbox="./media/example-extension-screenshot.png":::
  Microsoft Edge \ (Chromium \) 拡張機能  
:::image-end:::  

## 基本的なガイダンス  

拡張機能の構築のための最も一般的なブラウザーの一部には、Safari、Firefox、Chrome、Opera、Brave、Microsoft Edge などがあります。  拡張機能の開発に関するチュートリアルとドキュメントの調査を始めるのに最適な場所は、ブラウザー組織によってホストされているサイトです。  次の表は最終的なものではなく、開始点として使用できます。  

| Web ブラウザー | Chromium ベースの場合 | 拡張機能の開発 Web ページ |  
|:--- |:--- |:--- |  
| Safari | いいえ | [developer.apple.com/documentation/safariservices/safari_app_extensions][AppleDeveloperSafariservicesAppExtensions] |  
| Firefox | いいえ | [developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions][MDNWebextensions] |  
| クロム | はい | [developer.chrome.com/extensions][ChromeDeveloperExtensions] |  
| Opera | はい | [dev.opera.com/extensions][OperaDevExtensions] |  
| Brave | はい | [Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]を使用します |  
| 新しい Microsoft Edge | はい | [developer.microsoft.com/microsoft-edge/extensions][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> サイトの多くのチュートリアルでは、開発しているブラウザーと一致しない可能性のあるブラウザー固有の API を使用しています。  ほとんどの場合、Chromium 拡張機能は、異なる Chromium ブラウザーで動作しており、API は期待どおりに動作します。  一般的ではない一部の API は、厳密にはブラウザー固有のものである場合があります。  チュートリアルへのリンクについては、[関連項目](#see-also) に移動します。  

## Chromium を使用する理由  

拡張機能を拡張ストアで公開することを目標としている場合は、それぞれ別のブラウザー環境でターゲットを指定して実行できるようにするために、複数のバージョンを変更する必要があります。  たとえば、[Safari extensions][AppleDeveloperSafariservicesAppExtensions] は、Web とネイティブ コードの両方を活用して、もう一方のネイティブ アプリケーションとの通信に使用できます。  前の表の最後の 4 つのブラウザーは同じコード パッケージを使用し、並列バージョンを維持するための要件を最小限に抑えます。  これは、ブラウザーが [Chromium のオープンソース プロジェクト][|::ref1::|Home]に基づいています。  

Chromium の拡張機能を作成して、最小量のコードを記述します。  また、拡張ストアの最大数と、最終的に拡張機能を検出して取得するユーザーの最大数もターゲットに指定します。  

次のコンテンツでは、Chromium の拡張機能に焦点を当てています。  

## ブラウザーの互換性と拡張テスト  

場合によっては、Chromium ブラウザーの間に API パリティが存在しないことがあります。  たとえば、ID と API 支払いには違いがあります。  拡張機能が顧客の期待を満たするようにするには、次の公式ブラウザー ドキュメントを通して API の状態を確認します。  

*   [Chrome API][ChromeDeveloperExtensionsApiIndex]  
*   [Opera でサポートされる拡張 API][OperaDevExtensionsApis]  
*   [Chrome 拡張機能を Microsoft Edge (Chromium) に移植する][ExtensionsChromiumDeveloperGuidePortChrome]  
    
必要な API は、各ブラウザー間の違いに対処するために行う必要がある変更を定義します。  つまり、ストアごとに少しずつ異なるコード パッケージを作成することが必要になる場合があります。  

ブラウザー ストアに提出する前に、さまざまな環境で拡張機能をテストするには、開発中にブラウザーにサイドロードします。  

## 拡張機能をブラウザー ストアに公開する  

次のブラウザー ストアで、ブラウザーの拡張機能の提出、検索を行うことができます。  

*   [Firefox ブラウザーのアドオン][MozillaAddonsFirefoxExtensions]  
*   [Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]  
*   [Opera のアドオン][OperaAddonsExtensions]  
*   [Microsoft Edge アドオン][MicrosoftEdgeAddonsCategoryExtensions]  

一部のストアでは、他のブラウザーからリストされた拡張機能をダウンロードできます。  ただし、ブラウザー ストアでは、ブラウザー間のアクセスは保証されません。  ユーザーが異なるブラウザーで拡張機能を見つけるには、各ブラウザー拡張機能ストアでリストを維持する必要があります。  

ユーザーが異なるブラウザーに拡張機能をインストールすることが必要な場合があります。 このシナリオでは、あるブラウザーから別のブラウザーに既存の Chromium 拡張機能を移行できます。  

### 既存の拡張機能を Microsoft Edge に移行する  

既に別の Chromium ブラウザー用の拡張機能を開発している場合は、Microsoft Edge アドオン ストアに提出できます。 拡張機能を書き換える必要はなく、Microsoft Edge で動作することを確認する必要があります。  既存の Chromium 拡張機能を他の Chromium ブラウザーに移行する場合は、ターゲット ブラウザーで同じ API または代替手段を使用できます。  

Chrome 拡張機能を Microsoft Edge に移植する方法の詳細については、[Microsoft Edge (Chromium) の Chrome 拡張機能移植][ExtensionsChromiumDeveloperGuidePortChrome]」を参照してください。 ターゲット ブラウザーに拡張機能を移植したら、次の手順で公開することができます。  

### Microsoft Edge のアドオン web サイトに公開  

Microsoft Edge への拡張機能の公開を開始するには、MSA メールアカウントを持つ [開発者アカウントに登録][MicrosoftDeveloperRegistration] して、拡張機能のリストをストアに提出する必要があります。  MSAのメールアカウントには、`@outlook.com`、`@live.com` などが含まれます。  登録するメールアドレスを選択する場合は、組織内の他のユーザーと拡張機能の所有権を移転または共有する必要があるかどうかを検討してください。  登録が完了したら、ストアに新しい拡張機能の申請を作成することができます。  

拡張機能をストアに提出するには、次の項目を提供する必要があります。  

*   コード ファイルを含むアーカイブ \(`.zip`\) ファイル。  
*   ロゴと小規模プロモーション タイルなどの必要なすべてのビジュアル資産。  
*   スクリーンショット、プロモーション タイル、ビデオ URL などのオプションのプロモーション メディア。  
*   名前、短い説明、プライバシー ポリシーへのリンクなど、拡張機能について説明する情報。  

> [!NOTE]
> ストアによって、送信要件が異なる場合があります。  上記のリストは、Microsoft Edge に拡張機能を公開するための [要件][ExtensionsChromiumPublish] をまとめたものです。  

拡張機能を正常に提出した後、拡張機能にはレビュー プロセスが適用され、認定プロセスに合格または不合格になります。  所有者には、結果が通知され、必要に応じて次の手順が示されます。  拡張機能の更新プログラムをストアに提出すると、新しいレビュー プロセスが開始されます。  

## 関連項目  

*   [Google Chrome 拡張機能を移植する][ExtensionworkshopPorting]  
*   [Safari アプリの拡張機能を構築する][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [初めての拡張機能 (Firefox)][MDNWebextensionsYourFirst]  
*   [チュートリアルの開始 (Chrome)][ChromeDeveloperExtensionsGetstarted]  
*   [作業の開始 (Opera)][OperaDevExtensionsGettingStarted]  
*   [Microsoft Edge (Chromium) 拡張機能の使用を開始する][ExtensionsChromiumGettingStartedIndex]  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "Microsoft Edge (Chromium) へのChrome 拡張機能移植 | Microsoft Docs"  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md "Microsoft Edge (Chromium) の拡張機能をお使いになる前に | Microsoft Docs"  
[ExtensionsChromiumPublish]: ./publish/publish-extension.md "拡張機能公開 | Microsoft Docs"  

[MicrosoftDeveloperEdgeExtensions]: https://developer.microsoft.com/microsoft-edge/extensions "Microsoft Edge 用拡張機能開発 | Microsoft デベロッパー"  
[MicrosoftDeveloperRegistration]: https://developer.microsoft.com/registration "パートナーセンター | Microsoft デベロッパー"  

[MicrosoftEdgeAddonsCategoryExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 用拡張機能 | Microsoft Edge"  

[AppleDeveloperSafariservicesAppExtensions]: https://developer.apple.com/documentation/safariservices/safari_app_extensions "Safari アプリ用拡張機能 | Apple デベロッパー"  
[AppleDeveloperSafariservicesAppExtensionsBuilding]: https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension "Safari アプリ拡張機能構築 | Apple デベロッパー"  

[ChromeDeveloperExtensions]: https://developer.chrome.com/extensions "拡張機能とは | Chrome デベロッパー"  
[ChromeDeveloperExtensionsApiIndex]: https://developer.chrome.com/extensions/api_index "Chrome API | Chrome デベロッパー"  
[ChromeDeveloperExtensionsGetstarted]: https://developer.chrome.com/extensions/getstarted "はじめのチュートリアル | Chrome デベロッパー"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium"  

[ExtensionworkshopPorting]: https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension "Google Chrome 拡張機能移植 | 拡張機能ワークショップ"  

[GoogleChromeWebstoreCategoryExtensions]: https://chrome.google.com/webstore/category/extensions "拡張機能 | Chrome Web ストア"  

[MDNWebextensions]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions "ブラウザーの拡張機能 | MDN"  
[MDNWebextensionsYourFirst]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension "初めての拡張機能 | MDN"  

[MozillaAddonsFirefoxExtensions]: https://addons.mozilla.org/firefox/extensions "拡張機能 | Firefox 用のアドオン"  

[OperaAddonsExtensions]: https://addons.opera.com/extensions "拡張機能 | Opera 用のアドオン"  

[OperaDevExtensions]: https://dev.opera.com/extensions "拡張機能のドキュメント |Dev. Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "Opera | でサポートされる拡張 API | Dev. Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "はじめに | Dev. Opera"  
