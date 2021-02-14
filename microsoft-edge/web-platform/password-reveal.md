---
description: パスワード表示ボタンの表示のカスタマイズに関するガイダンスを提供します。
title: パスワード表示ボタンをカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: Microsoft Edge, 互換性, Web プラットフォーム, パスワード表示, 目のアイコン
ms.openlocfilehash: af8120aad7316ffc051113591e770fa913814eb3
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327721"
---
# パスワード表示ボタンをカスタマイズする  

`password`Microsoft Edge の入力の種類には、パスワード表示**コントロールが含**まれています。  ユーザーは、パスワード入力ボタン **を選択して** パスワード フィールドを **表示** できます。  表示されたパスワード **フィールドは** 、ユーザーがパスワードが正しいか確認するのに役立ちます。  ユーザーがパスワード フィールドにテキストを入力**** した後、ユーザーはパスワード表示ボタン**** を選択するか、入力の表示/非表示を切り替 `Alt` + `F8` える選択を行います。  

:::row:::
   :::column span="":::
      ユーザー **が** 入力した文字をドットで非表示にしたパスワード フィールド。  パスワード **表示ボタン** は、パスワード フィールドの右側に **表示** されます。
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-off.msft.png" alt-text="目の形をしたアイコンが、パスワード テキストを非表示にするドットの横に表示されます。" lightbox="./media/mdn-demo-password-reveal-off.msft.png":::
         目の形をしたアイコンが、パスワード テキストを非表示にするドットの横に表示されます。  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      パスワード表示 **ボタンを切** り替え、目のアイコンをスラッシュで目のアイコンに変更し、元のパスワード テキストを表示します。  
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-on.msft.png" alt-text="目の形をしたアイコンにはスラッシュが付き、元のパスワード テキストが表示されます。" lightbox="./media/mdn-demo-password-reveal-on.msft.png":::
         目の形をしたアイコンにはスラッシュが付き、元のパスワード テキストが表示されます。 :::image-end:::  
   :::column-end:::
:::row-end:::  

既定では、パスワード表示 **ボタンは** 、設定が設定されているすべての HTML 要素のシャドウ DOM `input` `type` に挿入されます `"password"` 。  Microsoft Edge バージョン 87 から、 [ユーザーまたは企業][DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled] は、この機能をグローバルに無効にできます。  Web デザイナーと開発者は、ほとんどの Microsoft Edge ユーザーに既定のエクスペリエンスを提供する必要があります。  

## パスワード表示コントロールを削除する  

擬似要素をターゲットにすることで **、パスワード** 表示ボタンを完全に `::-ms-reveal` 削除できます。  

```css
::-ms-reveal {
    display: none;
}
```  

ただし、パスワード表示ボタンの利用 **を検討する必要** があります。  ネイティブの **パスワード表示ボタンには** 、動作 [に組み込みの](#visibility-of-the-control) 重要なセキュリティ対策があります。  

## コントロール スタイルをカスタマイズする  

代わりに、コントロールを完全に削除する代わりに、パスワード表示ボタンのスタイルを**** Web サイトの表示言語に合わせて変更できます。  次のスニペットは、このようなスタイルの例を示しています。  

```css
::-ms-reveal {
    border: 1px solid transparent;
    border-radius: 50%;
    box-shadow: 0 0 3px currentColor;
}
```  

パスワード表示ボタンのスタイルを設定する場合は、次の **ことを念頭に置いてお** きます。  

*   目のアイコンは背景画像として実装されます。  パスワード表示ボタンに背景色を追加**** するには、shorthand プロパティの代わりに CSS `background-color` `background` プロパティを使用します。  
*   パスワード表示ボタンのサイズとスケール **を調整** できます。  
    
    > [!NOTE]
    >ブラウザーは、パスワード入力コントロールの境界の外側でオーバーフローを非表示にしています。  
    
*   現在、パスワード表示ボタンのトグル状態のスタイルを設定できる **状態セレクターはありません** 。  
    
## コントロールの可視性  

パスワード **表示ボタンは** 、ユーザーがパスワード フィールドにテキストを入力するまで **使用** できません。  ユーザーのパスワード 入力をセキュリティで保護するために、ブラウザーは次のシナリオでボタンを非表示にします。

*   フォーカスがパスワード フィールドから離 **れた場合** 、ブラウザーはパスワード表示ボタン **を削除** します。  
*   スクリプトがパスワード フィールド **を変更すると** 、ブラウザーはパスワード表示ボタン **を削除** します。  
*   ユーザーがパスワード表示**ボタンを削除**した場合、パスワード表示ボタンが再び表示される**** 前に、ユーザーはパスワード フィールドの**内容を削除**する必要があります。  
    
    > [!NOTE]
    > この機能により、ユーザーがロック解除されたデバイスから離れた場合に、ユーザーがパスワードを表示するために細かい調整を行うのを防ぐことができません。
    
パスワード**マネージャーを使用**してパスワード フィールド**** がオートフィルされた場合、パスワード表示ボタンは使用できません。  

<!-- links -->  

[DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled]: /deployedge/microsoft-edge-policies#passwordrevealenabled "PasswordRevealEnabled - Microsoft Edge - ポリシー|Microsoft Docs"  
