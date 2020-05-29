---
description: さまざまな言語の拡張機能にアクセスできるようにし、国際化ガイドを使用して言語の文字列をテストします。
title: 拡張機能-国際化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: d1f553d0e3e39192e68665fe6720daa811777c0b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569467"
---
# 」  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

内線番号をさまざまなユーザーが利用できるようにするには、その他の国で開発することが重要です。 Microsoft Edge extensions では、言語を簡単に変更できるように、さまざまな言語の文字列を拡張子に追加することができます。

拡張機能の国際化の詳細については、「MDN の[国際化ガイド」](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization)をご覧ください。


## 言語のテスト

言語の文字列をテストするには、最初に Windows の表示言語をテスト対象の言語に設定する必要があります。

Windows の表示言語を変更するには、次の手順を実行します。

1. [設定] アプリを開きます。

   ![設定アプリケーション](./../media/loc-settings.png)
2. [時刻 & 言語] を選びます。
3. [地域 & 言語] を選びます。
4. [+ 言語の追加] を選択して、利用可能な言語のリストに言語を追加します。
5. テストする [言語] リストから言語を選択します。
6. [既定に設定] ボタンを選択します (PC の再起動が必要な場合があります)。
7. Microsoft Edge を開き、ロケールに対して定義された文字列が予期したとおりに表示されることを確認します。

[NavigatorLanguage](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language)プロパティを使うと、Microsoft Edge が Windows の表示言語に正しいと判断したことを確認できます。

以下の CodePen のボタンをクリックすると、お使いのブラウザーの表示言語が表示されます。

<iframe height='300' scrolling='no' title='ロケールを取得する' src='//codepen.io/MSEdgeDev/embed/VaRWwR/?height=300&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'> </a> CodePen の「MSEdgeDev (@MSEdgeDev) でペンを取得する」を参照してください <a href='http://codepen.io/MSEdgeDev'> </a> <a href='http://codepen.io'> </a> 。
</iframe>
