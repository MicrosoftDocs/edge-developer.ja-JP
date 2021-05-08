---
description: パスワード表示ボタンの表示のカスタマイズに関するガイダンスを提供します
title: '[パスワードの表示] ボタンをカスタマイズする'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, 互換, Web プラットフォーム, パスワードの表示, 目のアイコン
ms.openlocfilehash: 93f618d28e5fa2f16dda87b4122a097ef40618c9
ms.sourcegitcommit: 1f0b2534b51417bb19d05945fea54ddad977e88f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2021
ms.locfileid: "11526159"
---
# <a name="customize-the-password-reveal-button"></a>[パスワードの表示] ボタンをカスタマイズする  

パスワード `password` 表示コントロールMicrosoft Edge入力**の種類を指定**します。  ユーザーは、パスワード入力ボタン **を選択して** パスワード フィールドを **表示** できます。  表示されたパスワード **フィールドは** 、ユーザーがパスワードが正しいか確認するのに役立ちます。  ユーザーがパスワード フィールドにテキストを入力**** した後、ユーザーはパスワード表示ボタン**** を選択するか、入力の表示を切り替 `Alt` + `F8` える場合に選択できます。  

:::row:::
   :::column span="":::
      ユーザー **が** 入力した文字をドットで非表示にしたパスワード フィールド。  [ **パスワードの表示** ] ボタンは、パスワード フィールドの右側 **に表示** されます。
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-off.msft.png" alt-text="目の形のアイコンが、パスワード テキストを非表示にするドットの横に表示されます。" lightbox="./media/mdn-demo-password-reveal-off.msft.png":::
         目の形のアイコンが、パスワード テキストを非表示にするドットの横に表示されます。  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      [パスワードの **表示] ボタン** を切り替え、目のアイコンをスラッシュで目のアイコンに変更し、元のパスワード テキストを表示します。  
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-on.msft.png" alt-text="目の形のアイコンにはスラッシュが付き、元のパスワード テキストが表示されます" lightbox="./media/mdn-demo-password-reveal-on.msft.png":::
         目の形のアイコンにはスラッシュが付き、元のパスワード テキストが表示されます :::image-end:::  
   :::column-end:::
:::row-end:::  

既定では、パスワード **表示ボタン** がに設定されているすべての HTML 要素のシャドウ DOM `input` `type` に挿入されます `"password"` 。  バージョン 87 Microsoft Edge、[ユーザーまたは企業][DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled]は、この機能をグローバルに無効にできます。  Web デザイナーと開発者は、ほとんどのユーザーが既定Microsoft Edgeエクスペリエンスを持つ必要があります。  

## <a name="remove-the-password-reveal-control"></a>パスワード表示コントロールを削除する  

擬似要素をターゲットにすることで **、パスワード表示ボタン** を完全に `::-ms-reveal` 削除できます。  

```css
::-ms-reveal {
    display: none;
}
```  

ただし、パスワード表示ボタンの利用 **を検討する必要** があります。  ネイティブパスワード **表示ボタンには** 、動作 [に組み込みの](#visibility-of-the-control) 重要なセキュリティ対策があります。  

## <a name="customize-the-control-style"></a>コントロール のスタイルをカスタマイズする  

コントロールを完全に削除する代わりに、Web サイトの表示言語に合わせてパスワード**** 表示ボタンのスタイルを変更することもできます。  次のスニペットは、このようなスタイルの例を示しています。  

```css
::-ms-reveal {
    border: 1px solid transparent;
    border-radius: 50%;
    box-shadow: 0 0 3px currentColor;
}
```  

パスワード表示ボタンのスタイルを設定する場合は、次の **ことを念頭に置** きます。  

*   目のアイコンは、背景画像として実装されます。  パスワード表示ボタンに **背景色を追加** するには、ショートハンド プロパティの代わりに CSS `background-color` プロパティ `background` を使用します。  
*   パスワード表示ボタンのサイズとスケール **を調整** できます。  
    
    > [!NOTE]
    >ブラウザーは、パスワード入力コントロールの境界外のオーバーフローを非表示にします。  
    
*   現在、パスワード表示ボタンのトグル状態のスタイルを設定できる **状態セレクターはありません** 。  
    
## <a name="visibility-of-the-control"></a>コントロールの表示  

ユーザー **がパスワード フィールド** にテキストを入力するまで、パスワード表示ボタンは **使用** できません。  ユーザーのパスワード エントリを安全に保つために、ブラウザーは次のシナリオでボタンを非表示にします。

*   フォーカスがパスワード フィールドから離 **れた** 場合、ブラウザーはパスワード表示ボタン **を削除** します。  
*   スクリプトがパスワード フィールドを **変更** すると、ブラウザーはパスワード表示ボタン **を削除** します。  

パスワード表示**ボタンが削除**された場合、パスワード表示ボタンが再び表示される**** 前に、ユーザーはパスワード フィールド**の**内容を削除する必要があります。 この動作により、ユーザーがロックされていないデバイスから離れた場合に、ユーザーがパスワードを表示するために細かい調整を行うのを防ぐ。
    
パスワード**マネージャーを使用して**パスワード フィールド**** が自動入力される場合、パスワード表示ボタンは使用できません。  

<!-- links -->  

[DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled]: /deployedge/microsoft-edge-policies#passwordrevealenabled "PasswordRevealEnabled - Microsoft Edge - ポリシー |Microsoft Docs"  
