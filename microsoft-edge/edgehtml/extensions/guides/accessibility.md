---
ms.assetid: c4544a19-de78-4c69-a042-c0415726548f
description: Light モードと Dark モードの両方で拡張機能のアイコンが表示されるのを確認するには、アクセシビリティ ガイドに従います。
title: アクセシビリティ - 拡張機能 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e6e7dbd2ee66ac785be31eec7189b87e6a6bd91f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234982"
---
# アクセシビリティ - 拡張機能 (EdgeHTML)  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## Microsoft Edge のアクセス可能な拡張機能アイコンの作成

サード パーティ拡張機能の開発者は、淡色テーマと濃色テーマの両方でアイコンを明確に表示するために、Microsoft の厳密なアクセシビリティ要件を満たす画像アセットを使用するようにお勧めしています。 すべての拡張アイコンは、アイコンの背景色とアイコン自体の主要な色との比率が 14:1 にすることをお勧めします。


Microsoft が開発したファースト パーティ拡張機能では、これらの要件を満たすために "ステッカー" による視覚的な処理が適用されます。

### "ステッカー" の例

"ステッカー" の主な目的は、任意の背景色でアイコンに視覚的にアクセス可能に設定します。 ハイ コントラスト要件をサポートするには、白の外側のストロークとアイコンの推奨される色の比率を 14:1 に設定する必要があります。

#### 良いアイコン
ステッカーを使用すると、主に暗いアイコンが任意の背景色で表示されたままになります。


![任意の背景色で表示されているアイコンの画像](./../media/accessibility-light-to-dark-good.png)

#### 悪いアイコン
ステッカーを使用しない場合、アイコンが背景と混じり合って見えなくなる可能性があります。


![黒の背景にブレンドされたアイコンの画像](./../media/accessibility-light-to-dark-bad.png)

### 拡張機能アイコンを "ステッカー" する

次の 5 つの手順では、Microsoft のアクセシビリティ要件を満たす拡張アイコンを作成する推奨される方法の概要を示します。


| ステップ 1                                       | ステップ 2                                       | ステップ 3                                                                                 | ステップ 4                                                                          | ステップ 5                                                       |
|:---------------------------------------------|:---------------------------------------------|:---------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|:-------------------------------------------------------------|
| 指定したグリッド内にアイコンを設定します。    | アイコンのサイズを 2 ピクセル小さくします。           | アイコンをコピーして、その場所に貼り付けます。 角が丸い 2 ピクセルの外側のストロークを作成します。 | ストロークの輪郭を設定し、複合パスを離して、残りの図形を結合します。 | 外側のストロークを白、内側のアイコンを必要に合った色に設定します。 |
| ![step1](./../media/accessibility-step1.png) | ![step2](./../media/accessibility-step2.png) | ![step3](./../media/accessibility-step3.png)                                           | ![step4](./../media/accessibility-step4.png)                                    | ![step5](./../media/accessibility-step5.png)                 |

