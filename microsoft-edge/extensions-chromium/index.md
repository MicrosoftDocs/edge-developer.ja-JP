---
description: Microsoft Edge (Chromium) の拡張機能の概要と、一般的なブラウザーの拡張機能の構築および公開。
title: Microsoft Edge (Chromium) の拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/27/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者、chromium の拡張機能
ms.openlocfilehash: 04b9ffb7ec175bad4f980310819ea6d3551ef9f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230944"
---
# Microsoft Edge (Chromium) 拡張機能の概要 

拡張機能とは、Microsoft Edge \ (Chromium \) に新しい機能を追加したり、既存の機能を変更したりするために使用できる小さなプログラムです。  拡張は、対象ユーザーにとって重要なニッチ機能を提供して、ユーザーの日常的なブラウジング エクスペリエンスの改善を目的としています。  

アイデアまたは製品が特定の web ブラウザーの可用性に依存している場合、または提供する機能によって既存の web サイトが拡張されている場合は、拡張機能を作成できます。  コンパニオン エクスペリエンスの例としては、アドブロッカーやパスワードマネージャーなどがあります。  

拡張機能は、通常の web アプリと同じように構成されています。  少なくとも、これには基本的なプラットフォーム情報を含むアプリマニフェストの JSON ファイル、機能を定義する JavaScript ファイル、およびユーザーインターフェイス \ (必要に応じて) の外観を決定するための HTML ファイルと CSS ファイルが含まれています。  ウィンドウやタブなど、ブラウザーの一部を直接操作するには、API リクエストを送信し、多くの場合、名前でブラウザーを参照する必要があります。  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 拡張機能":::
  Microsoft Edge \ (Chromium \) 拡張機能  
:::image-end:::  

## 基本的なガイダンス  

構築のための最も一般的なブラウザーの一部には、Safari、Firefox、Chrome、Opera、Brave、Microsoft Edge などがあります。  拡張機能の開発に関するチュートリアルとドキュメントの調査を始めるのに最適な場所は、ブラウザー組織によってホストされているサイトです。  次の表は確定的なものではありません。便利な出発点として使用してください。  

| Web ブラウザー | Chromium ベースの場合 | 拡張機能開発のホームページ |  
|:--- |:--- |:--- |  
| Safari | いいえ | [developer.apple.com/documentation/safariservices/safari_app_extensions][AppleDeveloperSafariservicesAppExtensions] |  
| Firefox | いいえ | [developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions][MDNWebextensions] |  
| クロム | はい | [developer.chrome.com/extensions][ChromeDeveloperExtensions] |  
| Opera | はい | [dev.opera.com/extensions][OperaDevExtensions] |  
| Brave | はい | [Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]を使用します |  
| 新しい Microsoft Edge | はい | [developer.microsoft.com/microsoft-edge/extensions][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> サイトの多くのチュートリアルでは、開発しているブラウザーと一致しない可能性のあるブラウザー固有の API を使用しています。  ほとんどの場合、Chromium 拡張機能は、異なる Chromium ブラウザーで動作しており、API は期待どおりに動作します。  一般的ではない一部の API は、厳密にはブラウザー固有のものである場合があります。  チュートリアルへのリンクについては、[関連項目](#see-also) を参照してください。  

## Chromium を使用する理由

拡張機能を可能な限り多くのブラウザー拡張ストアに公開することを目標としている場合は、それぞれ別のブラウザー環境でターゲットを指定して実行できるようにするために、複数のバージョンを変更する必要があります。  [Safari extensions][AppleDeveloperSafariservicesAppExtensions]は、他の拡張型とは異なり、web とネイティブコードの両方を活用して、もう一方のネイティブ アプリケーションとの通信に使用できます。  [Firefox extensions][MDNWebextensions] は、他の種類の拡張機能と共通していますが、考慮すべき [違い][ExtensionworkshopPorting] もいくつかあります。  ただし、良いお知らせもあります。上記の表の最後の4つのブラウザーでは、同じコードパッケージを活用し、要件を最小限に抑え、並行バージョンを変更および管理することができます。  これは、ブラウザーが [Chromium のオープンソース プロジェクト][|::ref1::|Home]に基づいているためです。  

Chromium 拡張機能を作成すると、コードの量を最小限に抑え、対象の拡張ストアの数と、最終的には拡張機能を検索して取得できるユーザーの数の両方を最大限にすることができます。  

次のコンテンツでは、Chromium の拡張機能に焦点を当てています。  

## ブラウザーの互換性と拡張テスト  

場合によっては、Chromium ブラウザーの間に API パリティが存在しないことがあります。  たとえば、ID と API 支払いには違いがあります。  拡張機能が顧客の期待を満たしていることを確認するには、 [Chrome API][ChromeDeveloperExtensionsApiIndex]、 [Opera でサポートされている拡張機能 API][OperaDevExtensionsApis]、 [Microsoft (Chromium) Edge へのポート Chrome 拡張機能][ExtensionsChromiumDeveloperGuidePortChrome] などの公式ブラウザー ドキュメントを使用して、API の状態を確認します。  

必要な API によっては、これらの違いにより、各ストアのコードでわずかに異なるコードパッケージを作成する必要があります。  

拡張機能を開発する場合には、拡張機能をブラウザー ストアに提出する前に、ブラウザーでサイドロードして、他の環境でテストすることができます。  

## 拡張機能をブラウザー ストアに公開する  

次のブラウザー ストアで、ブラウザーの拡張機能の提出、検索を行うことができます。  

*   [Firefox ブラウザーのアドオン][MozillaAddonsFirefoxExtensions]  
*   [Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]  
*   [Opera のアドオン][OperaAddonsExtensions]  
*   [Microsoft Edge アドオン][MicrosoftEdgeAddonsCategoryExtensions]  

一部のストアでは、他のブラウザーからリストされた拡張機能をダウンロードできます。  別のブラウザーからダウンロードすると、ユーザーが異なるブラウザーで既存のストアリストに移動できる場合は、今後の開発者の業務を減らして、追加のストアに提出する要件を削除することができます。  ただし、ブラウザー ストアでは、ブラウザー間のアクセスは保証されません。  ユーザーがさまざまなブラウザーで拡張機能を見つけることができるようにするには、各ブラウザー拡張機能ストアでリストを維持する必要があります。  

拡張機能には、複数のブラウザーを使用することが多い対象ユーザーが重複していることがあります。または、拡張機能が以前にはなかったユーザーを対象にしていると思われることがあります。  これを実現するために、既存の Chromium の拡張機能をあるブラウザーから別のブラウザーに移行することができます。  

### 既存の拡張機能を Microsoft Edge に移行する  

既に別の Chromium のブラウザー拡張機能を開発しており、それを提供して Microsoft Edge で動作することを確認したい場合は、拡張機能を書き換える必要はありません。  使用している API がさまざまなブラウザーで使用できる場合や、必要な機能を提供する他の API がある場合、既存の Chromium 拡張機能の他の Chromium ブラウザーへの移行は簡単です。  

Chrome 拡張機能移植の詳細については、[Microsoft (Chromium) Edge の Chrome 拡張機能移植][ExtensionsChromiumDeveloperGuidePortChrome]」を参照してください。  対象のブラウザに拡張機能を移植したら、次の手順で公開することができます。  

### Microsoft Edge のアドオン web サイトに公開  

Microsoft Edge への拡張機能の公開を開始するには、MSA メールアカウント (@outlook .com、@live など) を持つ [開発者アカウントに登録][MicrosoftDeveloperRegistration] して、ストアで拡張機能のリストを提出する必要があります。  登録するメールアドレスを選択する場合は、組織内の他のユーザーと拡張機能の所有権を移転または共有する必要があるかどうかを検討してください。  登録が完了したら、ストアに新しい拡張機能の申請を作成することができます。  

拡張機能をストアに提出するには、次の要件を満たしている必要があります。  

*   コードファイルを含むアーカイブ \ (.zip) ファイル。  
*   ロゴと小規模プロモーション タイルなどの必要なすべてのビジュアル資産。  
*   拡張機能のスクリーンショット、大規模プロモーション タイル、URL、またはビデオへの組み合わせなど、オプションのプロモーション メディア。  
*   名前、短い説明、長い説明、プライバシーポリシーへのリンクなど、拡張機能について説明する情報。  

> [!NOTE]
> ストアによって、送信要件が異なる場合があります。  上記のリストは、Microsoft Edge に拡張機能を公開するための [要件][ExtensionsChromiumPublish] をまとめたものです。  

申請プロセスが完了すると、拡張機能が確認され、認定プロセスに合格するか、または不合格になります。  所有者には、結果が通知され、必要に応じて次の手順が示されます。  拡張機能リストの詳細の更新など、更新された拡張機能をストアに提出すると、新しいレビュープロセスが開始されます。  

## 関連項目  

*   [Google Chrome 拡張機能の移植][ExtensionworkshopPorting]  
*   [Safari アプリの拡張機能の構築][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [初めての拡張機能 (Firefox)][MDNWebextensionsYourFirst]  
*   [はじめのチュートリアル (Chrome)][ChromeDeveloperExtensionsGetstarted]  
*   [はじめに (Opera)][OperaDevExtensionsGettingStarted]  
*   [Microsoft Edge (Chromium) の拡張機能をお使いになる前に][ExtensionsChromiumGettingStartedIndex]  

<!-- image links -->  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "Microsoft (Chromium) Edge へのChrome 拡張機能移植 | Microsoft Docs"  
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

[OperaDevExtensions]: https://dev.opera.com/extensions "拡張機能ドキュメント | Dev.Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "Opera でサポートされている拡張機能 | Dev.Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "はじめに | Dev.Opera"  
