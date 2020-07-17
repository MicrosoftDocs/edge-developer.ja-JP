---
ms.assetid: c4544a19-de78-4c69-a042-c0415726548f
description: ライトとダークモードの両方で拡張機能のアイコンが表示されるようにするには、アクセシビリティガイドに従います。
title: アクセシビリティ-拡張子 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 60e794467c6d054e390ce61c40559afa3a110c21
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882794"
---
# アクセシビリティ-拡張子 (EdgeHTML)  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## Microsoft Edge のアクセシビリティ対応の拡張機能アイコンの作成

サードパーティの拡張機能の開発者は、Microsoft の厳格なアクセシビリティ要件を満たしている画像アセットを使用することをお勧めします。これにより、淡色テーマと濃色テーマの両方でアイコンが明確に表示されます。 すべての拡張アイコンには、アイコンの背景色とアイコン自体の主要色との比率を14:1 にすることをお勧めします。


Microsoft が開発した初回パーティの拡張機能は、これらの要件を満たすために "stickering" の視覚的な処理を適用します。

### "Stickering" の例

"Stickering" の主な目標は、アイコンを背景色で視覚的にアクセスできるようにすることです。 白の外側のストロークとアイコンの間の推奨色の比率は、ハイコントラストの要件をサポートするために、14:1 である必要があります。

#### 適切なアイコン
Stickering では、基本的に暗いアイコンが背景色に表示されたままになります。


![背景色に表示されているアイコンの画像](./../media/accessibility-light-to-dark-good.png)

#### 不正なアイコン
Stickering を使わないと、アイコンが背景とブレンドされ、見えなくなる可能性があります。


![黒の背景にブレンドされるアイコンの画像](./../media/accessibility-light-to-dark-bad.png)

### "Stickering" の拡張機能アイコン

次の5つの手順では、Microsoft のアクセシビリティ要件を満たす拡張機能アイコンの作成方法の概要を示します。


| ステップ 1                                       | ステップ 2                                       | ステップ 3                                                                                 | ステップ 4                                                                          | ステップ 5                                                       |
|:---------------------------------------------|:---------------------------------------------|:---------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|:-------------------------------------------------------------|
| 指定した grid 内にアイコンを設定します。    | アイコンのサイズを2ピクセル小さくします。           | アイコンをコピーして、適切な場所に貼り付けます。 角が丸い2ピクセルの外側のストロークを作成します。 | ストロークのアウトラインを作成し、複合パスを解放し、残りの図形を結合します。 | 目的に応じて、外側のストロークの白と内側のアイコンの色を設定します。 |
| ![手順1](./../media/accessibility-step1.png) | ![手順2](./../media/accessibility-step2.png) | ![step3](./../media/accessibility-step3.png)                                           | ![step4](./../media/accessibility-step4.png)                                    | ![step5](./../media/accessibility-step5.png)                 |

