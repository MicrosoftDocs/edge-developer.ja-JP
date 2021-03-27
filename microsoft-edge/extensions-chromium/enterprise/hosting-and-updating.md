---
description: Microsoft Edge (Chromium) のエンタープライズ内の拡張機能をホストおよび発行します。
title: Microsoft Edge アドオン ストアでの拡張機能の発行と更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 2249462b0a2dac86efa4b775171e2a3229a34431
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461221"
---
# <a name="publish-and-update-extensions-in-the-microsoft-edge-add-ons-store"></a>Microsoft Edge アドオン ストアでの拡張機能の発行と更新  

ほとんどの拡張機能は、悪意のある拡張機能からユーザーを保護するために [Microsoft Edge][MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions] アドオン ストアに発行されます。  

## <a name="publish-options-for-extensions"></a>拡張機能の発行オプション  

すべての拡張子は、接尾辞付き特別なアーカイブ \( `.zip` \) ファイルとしてユーザーに配布 `.crx` されます。  Microsoft Edge アドオン ストアに発行された拡張機能は、ファイルとしてアップロード `.zip` されます。  発行プロセスは、ファイルをファイル `.zip` に自動的に変換 `.crx` します。  

次の 2 つのシナリオでは、Microsoft Edge アドオン ストアで拡張機能を発行する必要があります。  

*   エンタープライズ ポリシーを使用して配布される拡張機能。  
*   Microsoft Edge が開発者モードの場合、ローカル コンピューターで展開されていない拡張ディレクトリを使用する。  

## <a name="updates-to-extensions"></a>拡張機能の更新

Microsoft Edge ブラウザーは、インストールされている拡張機能の新しいバージョンを自動的にチェックします。 更新プログラムは、ユーザーの介入なしにインストールされます。  


<!-- image links -->

<!-- links -->  

[MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "拡張機能 - Microsoft Edge Insider アドオン |Microsoft"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページは次 [のページに表示されます](https://developer.chrome.com/extensions/hosting)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
