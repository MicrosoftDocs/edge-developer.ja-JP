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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327527"
---
# Microsoft Edge (Chromium) 拡張機能の概要  

拡張機能は、Microsoft Edge \(Chromium\) の機能を追加または変更するために\(開発者\) 使用する小規模なプログラムです。  拡張機能は、ユーザーの毎日の閲覧エクスペリエンスを向上することを目的とします。  対象ユーザーにとって重要な、優れた機能を提供します。  

次のいずれかの条件に基づくアイデアまたは製品がある場合は、拡張機能を作成できます。  

*   特定の Web ブラウザー。  
*   特定の Web ページの機能が向上しました。  
    
コンパニオン エクスペリエンスの例としては、広告のブロックやパスワード マネージャーがあります。  

拡張機能は、通常の web アプリと同じように構成されています。  少なくとも、次の機能が含まれる必要があります。

*   基本的なプラットフォーム情報を含むアプリ マニフェスト JSON ファイル。  
*   機能を定義する JavaScript ファイル。  
*   ユーザー インターフェイスを定義する HTML ファイルと CSS ファイル。  

ウィンドウやタブなど、ブラウザーの一部を直接操作するには、API リクエストを送信し、多くの場合、名前でブラウザーを参照する必要があります。  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 拡張機能" lightbox="./media/example-extension-screenshot.png":::
  Microsoft Edge \ (Chromium \) 拡張機能  
:::image-end:::  

## 基本的なガイダンス  

Safari、Firefox、Chrome、Opera、Safari、Microsoft Edge などの拡張機能を構築する最も一般的なブラウザーの一部です。  拡張機能の開発に関するチュートリアルとドキュメントの調査を始めるのに最適な場所は、ブラウザー組織によってホストされているサイトです。  次の表は確定的ではありません。開始点として使用できます。  

| Web ブラウザー | Chromium ベースの場合 | 拡張機能開発 Web ページ |  
|:--- |:--- |:--- |  
| Safari | いいえ | [developer.apple.com/documentation/safariservices/safari_app_extensions][AppleDeveloperSafariservicesAppExtensions] |  
| Firefox | いいえ | [developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions][MDNWebextensions] |  
| クロム | はい | [developer.chrome.com/extensions][ChromeDeveloperExtensions] |  
| Opera | はい | [dev.opera.com/extensions][OperaDevExtensions] |  
| Brave | はい | [Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]を使用します |  
| 新しい Microsoft Edge | はい | [developer.microsoft.com/microsoft-edge/extensions][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> サイトのチュートリアルの多くは、開発するブラウザーと一致しない可能性があるブラウザー固有の API を使用します。  ほとんどの場合、Chromium 拡張機能は、異なる Chromium ブラウザーで動作しており、API は期待どおりに動作します。  一般的ではない一部の API は、厳密にはブラウザー固有のものである場合があります。  チュートリアルへのリンクについては、[関連情報] [に移動します](#see-also)。  

## Chromium を使用する理由  

各ブラウザーの拡張機能ストアで拡張機能を公開する場合は、各バージョンで個別のブラウザー環境を対象として実行するように、拡張機能を変更する必要があります。  たとえば [、Safari 拡張機能では、Web][AppleDeveloperSafariservicesAppExtensions] とネイティブ の両方のコードを使用して、対応するネイティブ アプリケーションと通信できます。  前の表の最後の 4 つのブラウザーは同じコード パッケージを使用し、並列バージョンを維持するための要件を最小限に抑えます。  これらのブラウザーは Chromium オープン ソース [プロジェクトに基づいて作成されています][|::ref1::|Home]。  

Chromium 拡張機能を作成して、最小量のコードを書き込む。  また、拡張機能ストアの最大数と、拡張機能を見つけて取得するユーザーの最終的な最大数も対象とします。  

次のコンテンツでは、Chromium の拡張機能に焦点を当てています。  

## ブラウザーの互換性と拡張テスト  

Chromium ブラウザー間に API パリティが存在しない場合があります。  たとえば、ID と API 支払いには違いがあります。  拡張機能が顧客の期待を満たするように、次の公式ブラウザー ドキュメントを通じて API の状態を確認します。  

*   [Chrome API][ChromeDeveloperExtensionsApiIndex]  
*   [Opera でサポートされている拡張 API][OperaDevExtensionsApis]  
*   [Chrome 拡張機能を Microsoft Edge に移植する (Chromium)][ExtensionsChromiumDeveloperGuidePortChrome]  
    
必要な API は、各ブラウザー間の違いに対処するために行う必要がある変更を定義します。  これは、ストアごとに少し異なるコード パッケージを作成する必要がある場合があります。  

拡張機能をブラウザー ストアに提出する前に、さまざまな環境で拡張機能をテストするには、開発中にブラウザーにサイドロードします。  

## 拡張機能をブラウザー ストアに公開する  

次のブラウザー ストアで、ブラウザーの拡張機能の提出、検索を行うことができます。  

*   [Firefox ブラウザーのアドオン][MozillaAddonsFirefoxExtensions]  
*   [Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]  
*   [Opera のアドオン][OperaAddonsExtensions]  
*   [Microsoft Edge アドオン][MicrosoftEdgeAddonsCategoryExtensions]  

一部のストアでは、他のブラウザーからリストされた拡張機能をダウンロードできます。  ただし、ブラウザー ストアでは、ブラウザー間のアクセスは保証されません。  ユーザーが異なるブラウザーで拡張機能を見つけるには、各ブラウザー拡張機能ストアに登録情報を保持する必要があります。  

ユーザーが拡張機能を別のブラウザーにインストールする必要がある場合があります。 このシナリオでは、既存の Chromium 拡張機能をあるブラウザーから別のブラウザーに移行できます。  

### 既存の拡張機能を Microsoft Edge に移行する  

既に別の Chromium ブラウザー用の拡張機能を開発している場合は、Microsoft Edge アドオン ストアに提出できます。 拡張機能を書き換える必要はなく、Microsoft Edge で動作を確認する必要があります。  既存の Chromium 拡張機能を他の Chromium ブラウザーに移行する場合は、ターゲット ブラウザーで同じ API または代替機能を使用できます。  

Chrome 拡張機能を Microsoft Edge に移植する方法について詳しくは、「Chrome 拡張機能を [Microsoft Edge (Chromium)][ExtensionsChromiumDeveloperGuidePortChrome]に移植する」をご覧ください。 拡張機能をターゲット ブラウザーに移植した後、次の手順で公開します。  

### Microsoft Edge アドオン Web サイトへの公開  

Microsoft Edge への拡張機能の公開を開始するには、MSA メール アカウントを使用して開発者アカウントに登録し、拡張機能の登録情報をストアに提出する必要があります。 [][MicrosoftDeveloperRegistration]  MSA メール アカウントには `@outlook.com` 、次 `@live.com` が含まれます。  登録するメール アドレスを選択する場合は、拡張機能の所有権を組織内の他のユーザーに転送または共有する必要がある場合を検討します。  登録が完了したら、ストアに新しい拡張機能の申請を作成することができます。  

拡張機能をストアに提出するには、次の項目を指定してください。  

*   コード ファイルを含 `.zip` むアーカイブ \( \) ファイル。  
*   ロゴと小さなプロモーション 用タイルを含む、必要なすべてのビジュアル アセット。  
*   オプションのプロモーション 用メディア (スクリーンショット、プロモーション 用タイル、ビデオ URL など)。  
*   名前、簡単な説明、プライバシー ポリシーのリンクなど、拡張機能について説明する情報。  

> [!NOTE]
> ストアによって、送信要件が異なる場合があります。  上記の一覧は、Microsoft Edge [の拡張機能を][ExtensionsChromiumPublish] 公開する場合の要件をまとめたものです。  

拡張機能を正常に提出すると、拡張機能はレビュー プロセスを受け、認定プロセスに合格または不合格になります。  所有者には、結果が通知され、必要に応じて次の手順が示されます。  拡張機能の更新プログラムをストアに提出すると、新しいレビュー プロセスが開始されます。  

## 関連項目  

*   [Google Chrome 拡張機能の移植][ExtensionworkshopPorting]  
*   [Safari アプリ拡張機能を構築する][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [初めての拡張機能 (Firefox)][MDNWebextensionsYourFirst]  
*   [チュートリアルの開始 (Chrome)][ChromeDeveloperExtensionsGetstarted]  
*   [開始する (Opera)][OperaDevExtensionsGettingStarted]  
*   [Microsoft Edge (Chromium) 拡張機能の使用を開始する][ExtensionsChromiumGettingStartedIndex]  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "Chrome 拡張機能を Microsoft Edge (Chromium) |Microsoft Docs"  
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

[OperaAddonsExtensions]: https://addons.opera.com/extensions "拡張機能 | Opera のアドオン"  

[OperaDevExtensions]: https://dev.opera.com/extensions "Extensions ドキュメント |Dev. Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "Opera | でサポートされている拡張 APIDev. Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "使い始|Dev. Opera"  
