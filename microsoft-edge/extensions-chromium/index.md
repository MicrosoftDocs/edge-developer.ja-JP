---
description: Microsoft Edge (Chromium) の拡張機能の概要と、一般的なブラウザーの拡張機能の構築および公開。
title: Microsoft Edge (Chromium) の拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者、chromium の拡張機能
ms.openlocfilehash: 2c4c34805e93bf6fbae57f1d0230cc821d1f3f65
ms.sourcegitcommit: a5392ab44133d742c0e1fa500ad9a872989b7c3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684700"
---
# Microsoft Edge (Chromium) の拡張機能  

拡張機能とは、Microsoft Edge \ (Chromium \) に新しい機能を追加したり、既存の機能を変更したりするために使用できる小さなプログラムです。  拡張は、対象ユーザーにとって重要なニッチ機能を提供することによって、ユーザーの日常的なブラウジングエクスペリエンスを向上させることを目的としています。  

アイデアまたは製品が特定の web ブラウザーの利用可能性に依存している場合、または提供する機能によって既存の web サイトが拡張されている場合は、拡張機能を作成できます。  コンパニオンエクスペリエンスの例としては、adblockers やパスワードマネージャーなどがあります。  

拡張機能は、通常の web アプリと同じように構成されています。  少なくとも、基本的なプラットフォーム情報を含むアプリマニフェストの JSON ファイル、機能を定義する JavaScript ファイル、およびユーザーインターフェイス \ (必要に応じて) の外観を決定するための HTML ファイルと CSS ファイルが含まれています。  ウィンドウやタブなど、ブラウザーの一部を直接操作するには、API 要求を送信し、多くの場合、名前でブラウザーを参照する必要があります。  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 拡張機能":::
  Microsoft Edge \ (Chromium \) 拡張機能  
:::image-end:::  

## 基本的なガイダンス  

Safari、Firefox、Chrome、Opera、Brave、Microsoft Edge など、一般的なブラウザーの一部を対象として構築します。  拡張機能の開発に関するチュートリアルとドキュメントの調査を始めるのに最適な場所は、ブラウザー組織によってホストされているサイトです。  次の表は確定的なものではありません。これは、便利な出発点として使用してください。  

| Web ブラウザー | Chromium ベースの場合 | 拡張機能開発のホームページ |  
|:--- |:--- |:--- |  
| Safari | なし | [developer.apple.com/documentation/safariservices/safari_app_extensions][AppleDeveloperSafariservicesAppExtensions] |  
| Firefox | なし | [developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions][MDNWebextensions] |  
| クロム | あり | [developer.chrome.com/extensions][ChromeDeveloperExtensions] |  
| Opera | あり | [dev.opera.com/extensions][OperaDevExtensions] |  
| Brave | あり | [Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]を使用します |  
| 新しい Microsoft Edge | あり | [developer.microsoft.com/microsoft-edge/extensions][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> サイトの多くのチュートリアルでは、開発しているブラウザーと一致しない可能性のあるブラウザー固有の Api を使用しています。  ほとんどの場合、Chromium 拡張機能は、異なる Chromium ブラウザーで動作しており、Api は期待どおりに動作します。  一部の一般的ではない Api は、厳密にはブラウザー固有のものである場合があります。  チュートリアルへのリンクについては、「[関連項目](#see-also)」を参照してください。  

## Chromium  

拡張機能を可能な限り多くのブラウザー拡張ストアに公開することを目標としている場合は、それぞれのブラウザー環境でターゲットを指定して実行するために、複数のバージョンに対して変更する必要があります。  [Safari extensions][AppleDeveloperSafariservicesAppExtensions]は、他の拡張型とは異なり、web とネイティブコードの両方を活用して、ネイティブアプリケーションとの通信に使用できます。  [Firefox extensions][MDNWebextensions]は、他の種類の拡張機能と共通していますが、考慮すべき[点][ExtensionworkshopPorting]もいくつかあります。  ただし、良いお知らせがあります。上記の表の最後の4つのブラウザーでは、同じコードパッケージを活用して、並列バージョンを変更および管理するための要件を最小限に抑えることができます。  これは、ブラウザーが[Chromium のオープンソースプロジェクト][|::ref1::|Home]に基づいているためです。  

Chromium 拡張機能を作成すると、ターゲットとする拡張ストアの数を最大化するコードの量を最小限に抑えることができます。最終的には、拡張機能を検索して取得できるユーザーの数です。  

次のコンテンツは、ほとんどが Chromium の拡張機能に焦点を当てています。  

## ブラウザーの互換性と拡張テスト  

場合によっては、Chromium ブラウザーの間に API パリティが存在しないことがあります。  たとえば、id と支払いの Api には違いがあります。  拡張機能が顧客の期待を満たしていることを確認するには、 [Chrome api][ChromeDeveloperExtensionsApiIndex]、 [Opera でサポートされている拡張 api][OperaDevExtensionsApis]、 [Microsoft (Chromium) Edge へのポート chrome 拡張][ExtensionsChromiumDeveloperGuidePortChrome]機能などの公式ブラウザードキュメントを使って、API の状態を確認します。  

必要な Api によっては、これらの違いにより、各ストアのコードにわずかな違いがあるため、わずかに異なるコードパッケージを作成する必要がある場合があります。  

拡張機能を開発する際には、ブラウザーでサイドローディングを使用して、拡張機能をブラウザーストアに提出する前に、他の環境でテストすることができます。  

## 拡張機能をブラウザーストアに公開する  

次のブラウザーストアで、ブラウザーの拡張機能を送信およびシークすることができます。  

*   [Firefox Browser のアドオン][MozillaAddonsFirefoxExtensions]  
*   [Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]  
*   [Opera のアドオン][OperaAddonsExtensions]  
*   [Microsoft Edge アドオン][MicrosoftEdgeAddonsCategoryExtensions]  

一部のストアでは、他のブラウザーから一覧表示された拡張機能をダウンロードできます。  別のブラウザーからダウンロードした場合、ユーザーがさまざまなブラウザーで既存のストア登録情報に移動できるようになると、(開発者用の) 作業を事前に保存して、追加のストアに提出する必要がない場合があります。  ただし、ブラウザーストアでは、ブラウザー間のアクセスは保証されません。  ユーザーがさまざまなブラウザーで拡張機能を見つけることができるようにするには、各ブラウザー拡張ストアで一覧を保持する必要があります。  

内線番号には、複数のブラウザーを使用することが多い対象ユーザーが重複していることがあります。または、それ以外のユーザーを対象としている可能性があります。  これを実現するために、既存の Chromium の拡張機能をあるブラウザーから別のブラウザーに移行することができます。  

### 既存の拡張機能を Microsoft Edge に移行する  

既に別の Chromium browser の拡張機能を開発していて、それを提供して Microsoft Edge で動作することを確認したい場合は、拡張機能を書き換える必要はありません。  使用している Api がさまざまなブラウザーで使用できる場合や、必要な機能を提供する他の Api がある場合は、既存の Chromium 拡張機能を他の Chromium ブラウザーに移行するのは簡単です。  

Chrome 拡張機能の移植の詳細については、「 [Microsoft (Chromium) Edge のポート Chrome 拡張機能][ExtensionsChromiumDeveloperGuidePortChrome]」を参照してください。  ターゲットブラウザに拡張機能を移植したら、次の手順として公開します。  

### Microsoft Edge のアドオン web サイトに発行する  

Microsoft Edge への拡張機能の公開を開始するには、MSA メールアカウント (@outlook .com、@live など) を持つ[開発者アカウントに登録][MicrosoftDeveloperRegistration]して、ストアで拡張機能の一覧を提出する必要があります。  登録するメールアドレスを選択する場合は、組織内の他のユーザーと内線番号の所有権を移転または共有する必要があるかどうかを検討してください。  登録が完了したら、ストアに新しい拡張機能の申請を作成することができます。  

内線番号をストアに提出するには、次の要件を満たしている必要があります。  

*   コードファイルを含むアーカイブ \ (.zip) ファイル。  
*   必要なすべてのビジュアルアセット。ロゴと小規模プロモーションタイルが含まれます。  
*   スクリーンショット、大きなプロモーションタイル、URL、または拡張機能のビデオへの任意の組み合わせなど、オプションのプロモーションメディア。  
*   名前、短い説明、長い説明、プライバシーポリシーへのリンクなど、拡張機能について説明する情報。  

> [!NOTE]
> ストアによって、送信要件が異なる場合があります。  上記の一覧は、Microsoft Edge に拡張機能を公開するための[要件][ExtensionsChromiumPublish]をまとめたものです。  

申請プロセスが完了すると、拡張機能が確認され、認定プロセスに合格するか、または不合格になります。  所有者には、結果が通知され、必要に応じて次の手順が示されます。  拡張機能一覧の詳細の更新など、更新された拡張機能をストアに提出すると、新しいレビュープロセスが開始されます。  

## 関連項目  

*   [Google Chrome 拡張機能の移植][ExtensionworkshopPorting]  
*   [Safari アプリの拡張機能の構築][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [最初の内線番号 (Firefox)][MDNWebextensionsYourFirst]  
*   [はじめにのチュートリアル (Chrome)][ChromeDeveloperExtensionsGetstarted]  
*   [はじめに (Opera)][OperaDevExtensionsGettingStarted]  
*   [Microsoft Edge (Chromium) の拡張機能の概要][ExtensionsChromiumGettingStartedIndex]  

<!-- image links -->  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "Microsoft (Chromium) Edge のポート Chrome 拡張機能 |Microsoft ドキュメント"  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md "Microsoft Edge (Chromium) Extensions の概要 |Microsoft ドキュメント"  
[ExtensionsChromiumPublish]: ./publish/publish-extension.md "拡張子を公開する |Microsoft ドキュメント"  

[MicrosoftDeveloperEdgeExtensions]: https://developer.microsoft.com/microsoft-edge/extensions "Microsoft Edge 用の拡張機能を開発する |Microsoft 開発者"  
[MicrosoftDeveloperRegistration]: https://developer.microsoft.com/registration "パートナーセンター |Microsoft 開発者"  

[MicrosoftEdgeAddonsCategoryExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 用の拡張機能 |Microsoft Edge"  

[AppleDeveloperSafariservicesAppExtensions]: https://developer.apple.com/documentation/safariservices/safari_app_extensions "Safari アプリの拡張機能 |Apple 開発者"  
[AppleDeveloperSafariservicesAppExtensionsBuilding]: https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension "Safari アプリの拡張機能の構築 |Apple 開発者"  

[ChromeDeveloperExtensions]: https://developer.chrome.com/extensions "拡張子とはChrome 開発者"  
[ChromeDeveloperExtensionsApiIndex]: https://developer.chrome.com/extensions/api_index "Chrome Api |Chrome 開発者"  
[ChromeDeveloperExtensionsGetstarted]: https://developer.chrome.com/extensions/getstarted "はじめにのチュートリアル |Chrome 開発者"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium"  

[ExtensionworkshopPorting]: https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension "Google Chrome 拡張機能の移植 |拡張ワークショップ"  

[GoogleChromeWebstoreCategoryExtensions]: https://chrome.google.com/webstore/category/extensions "拡張子 |Chrome Web ストア"  

[MDNWebextensions]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions "ブラウザーの拡張機能 |MDN"  
[MDNWebextensionsYourFirst]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension "最初の内線番号 |MDN"  

[MozillaAddonsFirefoxExtensions]: https://addons.mozilla.org/firefox/extensions "拡張子 |Firefox 用のアドオン"  

[OperaAddonsExtensions]: https://addons.opera.com/extensions "拡張子 |Opera のアドオン"  

[OperaDevExtensions]: https://dev.opera.com/extensions "拡張機能ドキュメント |Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "Opera でサポートされている拡張 ApiOpera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "はじめにOpera"  
