---
description: Microsoft Edge 内でアクセス可能な Web サイトを構築、設計、テストする方法について説明します。
title: アクセシビリティ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 1e5c42a7-4604-46ac-ad7b-a65390e5b36a
keywords: アクセシビリティ, 開発者向けアクセシビリティ, アクセシビリティ対応の Web サイト, エッジ, Web 開発, ARIA, 開発者, UIA, UI オートメーション
ms.openlocfilehash: ae2b0a876b60e0475e283cc52ffd14275fc32aba
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234502"
---
# アクセシビリティの概要  

> "\[T\]障がいへの影響は、Web 上で根本的に変更されています。Web は、多くのユーザーが物理的な世界で直面する通信とやり取りに対する障壁を取り除くからです。" [(アクセシビリティ |W3C)][W3CAccessibility]  

世界 [保健機関][WHODisabilities] は、障がいを 「身体の機能と、その人が住んでいる環境の機能との相互作用の不一致」と定義しています。  障がいを持っている場合は、限られた運動障がいを持ちながら携帯電話に光を当て、その他の物理的、監査、視覚、または年齢に関連する障がいがあります。  

含める Web サイトや他のテクノロジを設計すると、すべてのユーザーが楽しいエクスペリエンスを実現できます。  包括的なデザインと Web アクセシビリティにより、すべてのユーザーが Web を使用できます。  

Microsoft Edge でのアクセス可能な Web サイトの設計、構築、テストについて詳しくは[][AccessibilityBuild]、ベスト[][AccessibilityTest]プラクティス、コード サンプル、その他のリソースをご覧ください。 [][AccessibilityDesign]  

## Microsoft Edge のアクセシビリティ  

Microsoft Edge では、最新の [UI オートメーション API][WindowsWin32AutoEntryui] \(UIA API\) を導入しました。  UIA の変更は、ブラウザーのアクセシビリティに大きな投資を行い、Windows 10 の支援技術に依存するユーザーにとってより包括的な Web エクスペリエンスの基盤を構築しました。  また、Chromium エンジンの常に存在する性質も利用できます。  

Microsoft Edge のアクセシビリティ システムは、ARIA、HTML5、CSS3 などの最新の Web 標準を本質的にサポートしています。  簡素化されたブラウザー パイプラインの次の図は、Web ページのコンテンツに従って、アクセス可能なプレゼンテーション層に入ります。  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="エンジン モデルに変換されたコンテンツは、視覚的またはアクセシビリティに対応したプレゼンテーションとして表示されるビジュアル ビューとアクセシビリティ ビューに投影されます。":::
   エンジン モデルに変換されたコンテンツは、視覚的またはアクセシビリティに対応したプレゼンテーションとして表示されるビジュアル ビューとアクセシビリティ ビューに投影されます。  
:::image-end:::  

Microsoft Edge チームは、W3C や他のブラウザー ベンダーと継続的に取り組み、新しい Web プラットフォーム機能に十分な組み込みのアクセシビリティが備わっています。  

Microsoft Edge でサポートされている新しい HTML5 機能の詳細については [、HTML5Accessibility に移動します][HTML5Accessibility]。  

## リソース  

#### Microsoft Windows UI オートメーションに関するブログ  

[Microsoft Windows UI Automation ブログでは、Windows][ArchiveBlogsWinuiautomation]オートメーション API に関連するトピックについて説明します。  

#### Web Accessibility Initiative (INITIATIVE)  

[WEB アクセシビリティ イニシアティブ (INITIATIVE)][W3CWaiHome]が提供する bt the W3C は、Web のアクセシビリティを向上させる取り組みです。  このサイトでは[、Web][W3CWaiGettingstartedOverview]アクセシビリティの使用の開始、包含のための設計、チュートリアル[][W3CWaiFundamentals]とプレゼンテーションなど、さまざまな[リソースが提供][W3CWaiTeachAdvocate]されています。  

<!-- links -->  

[AccessibilityBuild]: ./build/index.md "アクセス可能な Web サイトの構築 |Microsoft Doc"  
[AccessibilityDesign]: ./design.md "アクセス可能な Web サイトの設計 |Microsoft Doc"  
[AccessibilityTest]: ./test.md "アクセシビリティ テスト |Microsoft Docs"  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 "UI オートメーション |Microsoft Doc"  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ "Microsoft Windows UI オートメーションブログ |Microsoft Doc"  

[HTML5Accessibility]: https://html5accessibility.com "HTML5 アクセシビリティ"  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility "アクセシビリティ |W3C"  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro "Web アクセシビリティの概要 |Web アクセシビリティ イニシアティブ (INITIATIVE) |W3C"  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview "概要: Web サイトをアクセス可能にする |Web アクセシビリティ イニシアティブ (INITIATIVE) |W3C"  
[W3CWaiHome]: https://w3.org/wai "Web アクセシビリティ イニシアティブ (INITIATIVE) |W3C"  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate "教えと支持者の概要 |Web アクセシビリティ イニシアティブ (INITIATIVE) |W3C"  

[WHODisabilities]: https://who.int/topics/disabilities "障がい |誰が"  

