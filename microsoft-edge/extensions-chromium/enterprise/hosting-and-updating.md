---
description: Edge (Chromium) 拡張機能のエンタープライズドキュメントを拡張します。
title: ホスティングと更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/05/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: eb1f9921d503d25557fc9efb1517537e7a90f4aa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569582"
---
# Web Store のホストと更新  

ほとんどの拡張機能は、 [Microsoft Edge Insider アドオンカタログ (Microsoft Edge insider のアドオン \)][MicrosoftStoreExtensions]にホストされ、ユーザーが悪意のある拡張機能を最大限に保護します。  

## ホスト  

すべての拡張機能は、すべてのユーザーに対して、crx というサフィックスを持つ特別な ZIP ファイルとして配布されます。  Microsoft Edge のアドオンでホストされる拡張機能は、.zip ファイルとしてアップロードされます。 発行処理によって、.zip が自動的に crx ファイルに変換されます。  

Microsoft Edge のアドオンホスティングルールには次の2つの例外があります。  

1.  エンタープライズポリシーを通じて配布される拡張機能。  
1.  開発者モードでローカルコンピューターから拡張機能ディレクトリを展開しました。  

## 更新  

Microsoft Edge ブラウザーでは、ユーザーの操作なしで、インストールされている拡張機能と更新プログラムの新しいバージョンが定期的にチェックされます。  

> [!NOTE]
> Microsoft Edge のアドオンで拡張機能を更新する手順は計画されています。  

<!-- image links -->

<!-- links -->  

[MicrosoftStoreExtensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "拡張機能-Microsoft Edge Insider アドオン"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developer.chrome.com/extensions/hosting)にあります。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
