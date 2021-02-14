---
description: Microsoft Edge (Chromium) の企業で拡張機能をホストおよび公開します。
title: Microsoft Edge アドオン ストアでの拡張機能の公開と更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 91fdd5c2f625890653085e8999da3e513b072348
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327688"
---
# Microsoft Edge アドオン ストアでの拡張機能の公開と更新  

ほとんどの拡張機能は、悪意のある拡張機能からユーザーを保護するために [Microsoft Edge アドオン][MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions] ストアに公開されます。  

## 拡張機能の公開オプション  

すべての拡張子は、サフィックス付き特別なアーカイブ `.zip` \( \) ファイルとしてユーザーに配布 `.crx` されます。  Microsoft Edge アドオン ストアに公開された拡張機能は、ファイルとしてアップロード `.zip` されます。  発行プロセスでは、ファイルがファイル `.zip` に自動的に変換 `.crx` されます。  

次の 2 つのシナリオでは、Microsoft Edge アドオン ストアで拡張機能を公開する必要が生じることはできません。  

*   エンタープライズ ポリシーを使用して配布される拡張機能。  
*   Microsoft Edge が開発者モードの場合に、ローカル コンピューターで展開されていない拡張ディレクトリを使用する。  

## 拡張機能の更新

Microsoft Edge ブラウザーは、インストールされている拡張機能の新しいバージョンを定期的にチェックし、ユーザーの介入なしに各拡張機能を更新します。  

<!-- links -->  

[MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "拡張機能 - Microsoft Edge Insider アドオン |Microsoft"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここ [です](https://developer.chrome.com/extensions/hosting)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
