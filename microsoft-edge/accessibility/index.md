---
description: Web サイト内でアクセス可能な Web サイトを構築、設計、テストするMicrosoft Edge。
title: アクセシビリティ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 1e5c42a7-4604-46ac-ad7b-a65390e5b36a
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセス可能な Web サイト、エッジ、Web 開発、ARIA、開発者、UIA、UI オートメーション
ms.openlocfilehash: ae2b0a876b60e0475e283cc52ffd14275fc32aba
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234502"
---
# アクセシビリティの概要  

> "\[T\]障害の影響は、Web が物理的な世界で多くの人々が直面するコミュニケーションと相互作用の障壁を取り除くので、Web 上で根本的に変更されます。 [(アクセシビリティ |W3C)][W3CAccessibility]  

世界 [保健機関は][WHODisabilities] 、障がいを「身体の機能と、その身体が住む環境の特徴との間の相互作用の不一致」と定義しています。  障害は、携帯電話で赤ちゃんや明るい日差しを保持している間の身体の制限など、状況の障害から、他の物理的、聴覚、視覚、または年齢に関連する障害までです。  

Web サイトや他のテクノロジを組み込むデザインは、すべてのユーザーが楽しめるエクスペリエンスを作り出します。  包括的なデザインと Web アクセシビリティは、すべてのユーザーが Web を使用する権限を与え、支援します。  

設計、構築、およびテストのアクセス可能な Web サイトの詳細については、ベスト プラクティス[][AccessibilityBuild]、コード[][AccessibilityTest]サンプル、その他のリソースをMicrosoft Edge。 [][AccessibilityDesign]  

## ユーザー補助Microsoft Edge  

このMicrosoft Edge、モダン[UI オートメーション API][WindowsWin32AutoEntryui] \(UIA API\) を導入しました。  UIA への変更は、ブラウザーアクセシビリティへの大きな投資であり、Windows 10 で支援技術に依存しているユーザーにとって、より包括的な Web エクスペリエンスの基盤を築きます。  また、ユーザーは、エンジンの常緑Chromiumします。  

このシステムのアクセシビリティ システムMicrosoft Edge、ARIA、HTML5、CSS3 などの最新の Web 標準を本質的にサポートしています。  簡略化されたブラウザー パイプラインの次の図は、Web ページのコンテンツをアクセス可能なプレゼンテーション 層に従います。  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="エンジン モデルに変換されたコンテンツは、視覚的またはアクセス可能なプレゼンテーションとして表示される視覚的およびアクセシビリティ ビューに投影されます。":::
   エンジン モデルに変換されたコンテンツは、視覚的またはアクセス可能なプレゼンテーションとして表示される視覚的およびアクセシビリティ ビューに投影されます。  
:::image-end:::  

このMicrosoft Edgeチームは、W3C や他のブラウザー ベンダーと継続的に取り組み、新しい Web プラットフォーム機能に十分な組み込みのアクセシビリティを提供します。  

ユーザーがサポートする新しい HTML5 機能の[Microsoft Edge、HTML5Accessibility に移動します][HTML5Accessibility]。  

## リソース  

#### Microsoft Windows UI オートメーション ブログ  

[Microsoft の UI オートメーションWindowsブログでは、][ArchiveBlogsWinuiautomation]オートメーション API に関連するトピックWindows説明します。  

#### Web アクセシビリティ イニシアチブ (WAI)  

W3C が提供する Web アクセシビリティ イニシアチブ [(WAI)][W3CWaiHome] は、Web のアクセシビリティの向上に役立つ取り組みです。  このサイトには [、Web][W3CWaiGettingstartedOverview]アクセシビリティの使い始 [め、包含][W3CWaiFundamentals]の設計、チュートリアルとプレゼンテーションなど、 [さまざまなリソースが][W3CWaiTeachAdvocate]提供されています。  

<!-- links -->  

[AccessibilityBuild]: ./build/index.md "アクセス可能な Web サイトの|Microsoft Doc"  
[AccessibilityDesign]: ./design.md "アクセス可能な Web サイトの|Microsoft Doc"  
[AccessibilityTest]: ./test.md "アクセシビリティ テスト |Microsoft Docs"  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 "UI オートメーション |Microsoft Doc"  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ "Microsoft Windows UI オートメーション ブログ |Microsoft Doc"  

[HTML5Accessibility]: https://html5accessibility.com "HTML5 アクセシビリティ"  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility "アクセシビリティ |W3C"  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro "Web アクセシビリティ の概要|Web アクセシビリティ イニシアチブ (WAI) |W3C"  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview "開始方法: Web サイトをアクセス可能なユーザー設定|Web アクセシビリティ イニシアチブ (WAI) |W3C"  
[W3CWaiHome]: https://w3.org/wai "Web アクセシビリティ イニシアチブ (WAI) |W3C"  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate "ティーチとアドボケートの概要|Web アクセシビリティ イニシアチブ (WAI) |W3C"  

[WHODisabilities]: https://who.int/topics/disabilities "障が|誰が"  

