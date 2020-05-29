---
ms.assetid: ffd1bc60-2ef1-4f11-8156-b63544cede77
description: Microsoft Edge で ARIA の情報を認識して、Microsoft UI オートメーション Api を使用できる支援技術に公開する方法について説明します。
title: アクセシビリティ-ARIA と UI オートメーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセシビリティ対応の web サイト、edge、web 開発、ARIA、開発者、UIA、UI オートメーション
ms.custom: seodec18
ms.openlocfilehash: 2fcc8160c830b5a62d8023a5cb7cc9df376c49ca
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568809"
---
# Microsoft Edge の ARIA と UI オートメーション

W3C は、動的な web コンテンツとカスタム UI を作成するための構文として、アクセシビリティに対応したリッチインターネットアプリケーション (ARIA) を定義しています。 Microsoft Edge は、ARIA の役割、状態、プロパティの情報を認識して、支援技術に公開します。これにより、 [MICROSOFT UI オートメーション](https://blogs.msdn.microsoft.com/winuiautomation/)api を使って情報を取得できるようになります。

Microsoft Edge でサポートされている新しい HTML5 機能 accessibly については、 [HTML5Accessibility](https://html5accessibility.com)を参照してください。

Microsoft Edge レンダリングエンジン (EdgeHTML) は、次の W3C 仕様に準拠した、アクセシビリティに対応した web ページの予測を構築します。

1. [Html アクセシビリティ API マッピング](https://w3.org/TR/html-aam-1.0/)の仕様では、html 要素と属性が ARIA と UI オートメーションオブジェクトにどのようにマッピングされるかを定義します。
   * [ドラフト](https://w3.org/TR/html-aam-1.0/)-安定バージョンの仕様
   * [編集者の下書き](https://w3c.github.io/html-aam/)-作業中。 この仕様には最新の変更が含まれていますが、変更は Microsoft Edge ではまだ利用できない場合があることに注意してください。


2. [コアアクセシビリティ API マッピング](https://w3.org/TR/core-aam-1.1/)仕様では、アクセシビリティツリーを構築し、ARIA 要素と属性を UI オートメーションオブジェクトにマッピングするための一般的な原則を定義します。
   * [ドラフト](https://w3.org/TR/core-aam-1.1/)-安定バージョンの仕様
   * [編集者の下書き](https://w3c.github.io/core-aam/)-作業中。 この仕様には最新の変更が含まれていますが、変更は Microsoft Edge ではまだ利用できない場合があることに注意してください。  

3. [アクセシビリティ対応の名前と説明: 計算と API のマッピング](https://w3.org/TR/accname-aam-1.1/)の仕様では、アクセシビリティの高い要素で使用できる、HTML と ARIA の要素と属性の値を指定して、アクセシビリティの高いオブジェクトの名前と説明を計算する方法を定義します。
   * [ドラフト](https://w3.org/TR/accname-aam-1.1/)-安定バージョンの仕様  
   * [編集者の下書き](https://w3c.github.io/accname/)-作業中。 この仕様には最新の変更が含まれていますが、変更は Microsoft Edge ではまだ利用できない場合があることに注意してください。   

Microsoft Edge のアクセシビリティアーキテクチャについて詳しくは、「アクセシビリティの[高い web platform ブログの投稿を作成する](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/)」をご覧ください。  新しいアーキテクチャがエンドユーザーのエクスペリエンスを向上させる方法、特にマークアップでスクリーンリーダーなどの支援技術を使用したナビゲーションの操作性を定義する方法については、「 [HTML5 と UIA を使用してアクセシビリティの高いユーザーエクスペリエンスを構築](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/)する」を参照してください。
