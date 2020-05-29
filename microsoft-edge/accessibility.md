---
ms.assetid: 1e5c42a7-4604-46ac-ad7b-a65390e5b36a
description: Microsoft Edge でアクセシビリティの高い web サイトを構築、設計、テストする方法について説明します。
title: アクセシビリティ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセシビリティ対応の web サイト、edge、web 開発、ARIA、開発者、UIA、UI オートメーション
ms.openlocfilehash: 6ad95e9c250aa6a4a61ca09470cea86efd715427
ms.sourcegitcommit: 9169d784485e3cb0b1987a8f395c4bb688bd9b2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "10583106"
---
# アクセシビリティ  

> "\ [T/] 障碍の影響は、web 上で大幅に変更されています。 web では、世界中の多くのユーザーがコミュニケーションや操作の障壁を取り除きます。" [(アクセシビリティ |勧告][W3CAccessibility]  

[世界中の正常性組織][WHODisabilities]では、障碍は "ユーザーの身体の機能と、そのユーザーが住んでいる環境の機能との相互作用の不一致" として定義されています。  障碍のある方が、スマートフォンで赤ちゃんや鮮やかな日光を持っている場合や、その他の物理的、聴覚、視覚、または年齢に障碍がある場合など、さまざまな状況障碍があります。  

Web サイトやその他のテクノロジを設計すると、すべてのユーザーが楽しめるようになります。  包括的なデザインと web アクセシビリティにより、すべてのユーザーが web を使用できるようになります。  

Microsoft Edge でのアクセシビリティ対応の web サイトの[設計][AccessibilityDesign]、[構築][AccessibilityBuild]、[テスト][AccessibilityTest]の詳細については、以下のベストプラクティス、コードサンプル、およびその他のリソースを参照してください。  

## Microsoft Edge でのアクセシビリティ  

Microsoft Edge では、最新の[UI オートメーション API][WindowsWin32AutoEntryui] \ (UIA API \) が導入されました。  UIA への変更は、ブラウザーのアクセシビリティに大きな投資となっており、Windows 10 の支援技術に依存するユーザーを対象とした、より包括的な web エクスペリエンスの基盤となっています。  ユーザーは、Chromium エンジンの evergreen な性質を利用することもできます。  

Microsoft Edge のアクセシビリティシステムでは、ARIA、HTML5、CSS3 などの先進の web 標準がサポートされています。  簡略化されたブラウザパイプラインの次の図は、アクセシビリティの高いプレゼンテーション層に web ページのコンテンツを表示する方法を示しています。  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="エンジンモデルに変換されたコンテンツは、視覚的またはアクセシビリティの高いプレゼンテーションとして表示されるビジュアルとアクセシビリティビューに投影されます。":::
   図 1.   エンジンモデルに変換されたコンテンツは、視覚的またはアクセシビリティの高いプレゼンテーションとして表示されるビジュアルとアクセシビリティビューに投影されます。
:::image-end:::

<!--![Figure 1.  Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation][ImageAccessibilityArchitecture]  -->  

Microsoft Edge チームは、W3C およびその他のブラウザーベンダーと継続的に協力して、新しい web プラットフォーム機能に十分なアクセシビリティが組み込まれていることを確認します。  

Microsoft Edge でサポートされている新しい HTML5 機能の accessibly については、 [HTML5Accessibility][HTML5Accessibility]を参照してください。  

## リソース  

#### Microsoft Windows UI Automation ブログ  

[Microsoft WINDOWS UI オートメーションのブログ][ArchiveBlogsWinuiautomation]では、WINDOWS オートメーション API に関連するトピックを取り上げています。  

#### Web アクセシビリティイニシアチブ (WAI-ARIA 使った)  

Bt である[Web アクセシビリティイニシアチブ (wai-aria 使った)][W3CWaiHome]は、web のアクセシビリティを向上させるための取り組みとなっています。  このサイトには、 [Web アクセシビリティの使用を開始][W3CWaiGettingstartedOverview]するためのさまざまなリソースが用意されています。また、[追加][W3CWaiFundamentals]、[チュートリアル、プレゼンテーション][W3CWaiTeachAdvocate]などを行うことができます。  


<!-- image links -->  

<!--[ImageAccessibilityArchitecture]: ./media/accessibilityarchitecture.png "Figure 1: Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation"  -->  

<!-- links -->  

[AccessibilityBuild]: ./accessibility/build.md "アクセシビリティの高い Web サイトを構築する"  
[AccessibilityDesign]: ./accessibility/design.md "アクセシビリティの高い Web サイトを設計する"  
[AccessibilityTest]: ./accessibility/test.md "アクセシビリティテスト"  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 "UI オートメーション"  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ "Microsoft Windows UI Automation ブログ"  

[HTML5Accessibility]: https://html5accessibility.com "HTML5 のアクセシビリティ"  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility "アクセシビリティ |勧告"  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro "Web アクセシビリティの概要 |Web アクセシビリティイニシアチブ (WAI-ARIA 使った) |勧告"  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview "はじめに: Web サイトのアクセシビリティを向上させる |Web アクセシビリティイニシアチブ (WAI-ARIA 使った) |勧告"  
[W3CWaiHome]: https://w3.org/wai "Web アクセシビリティイニシアチブ (WAI-ARIA 使った) |勧告"  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate "講義と代弁の概要 |Web アクセシビリティイニシアチブ (WAI-ARIA 使った) |勧告"  

[WHODisabilities]: https://who.int/topics/disabilities "障碍 |誰が"  

