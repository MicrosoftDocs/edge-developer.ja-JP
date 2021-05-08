---
ms.assetid: ffd1bc60-2ef1-4f11-8156-b63544cede77
description: ARIA 情報Microsoft Edge認識し、Microsoft UI オートメーション API を使用できる支援テクノロジに公開する方法について説明します。
title: アクセシビリティ - ARIA と UI オートメーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: アクセシビリティ、開発者向けのアクセシビリティ、アクセス可能な Web サイト、エッジ、Web 開発、ARIA、開発者、UIA、UI オートメーション
ms.custom: seodec18
ms.openlocfilehash: 2fcc8160c830b5a62d8023a5cb7cc9df376c49ca
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568809"
---
# ARIA と UI オートメーション (Microsoft Edge

W3C は、アクセス可能なリッチ インターネット アプリケーション (ARIA) を、動的 Web コンテンツとカスタム UI をアクセス可能にするための構文として定義します。 Microsoft Edge、ARIA の役割、状態、およびプロパティの情報を認識し、支援テクノロジに公開し[、Microsoft UI オートメーション API](https://blogs.msdn.microsoft.com/winuiautomation/)を使用して情報を取得できます。

[HTML5Accessibility に](https://html5accessibility.com)アクセスして、ユーザーがサポートする新しい HTML5 機能に関する情報Microsoft Edge。

次Microsoft Edgeレンダリング エンジン (EdgeHTML) は、次の W3C 仕様に準拠して、Web ページのアクセス可能なプロジェクションを構築します。

1. [HTML アクセシビリティ API Mappings 仕様は](https://w3.org/TR/html-aam-1.0/)、HTML 要素と属性が ARIA オブジェクトおよび UI オートメーション オブジェクトにマップする方法を定義します。
   * [作業下書](https://w3.org/TR/html-aam-1.0/) き - 仕様の安定版
   * [編集者の下書き](https://w3c.github.io/html-aam/) - 進行中の作業。 この仕様には最新の変更点が含まれる一方で、この変更は現在のバージョンMicrosoft Edgeがあります。


2. Core [Accessibility API Mappings 仕様](https://w3.org/TR/core-aam-1.1/) は、アクセシビリティ ツリーを構築し、ARIA 要素と属性を UI オートメーション オブジェクトにマッピングするための一般的な原則を定義します。
   * [作業下書](https://w3.org/TR/core-aam-1.1/) き - 仕様の安定版
   * [編集者の下書き](https://w3c.github.io/core-aam/) - 進行中の作業。 この仕様には最新の変更点が含まれる一方で、この変更は現在のバージョンMicrosoft Edgeがあります。  

3. [ [アクセス可能な名前](https://w3.org/TR/accname-aam-1.1/) と説明: 計算と API マッピング] 仕様では、HTML およびアクセス可能な要素で使用できる ARIA 要素と属性の値を指定して、アクセス可能なオブジェクトの名前と説明を計算する方法を定義します。
   * [作業下書](https://w3.org/TR/accname-aam-1.1/) き - 仕様の安定版  
   * [編集者の下書き](https://w3c.github.io/accname/) - 進行中の作業。 この仕様には最新の変更点が含まれる一方で、この変更は現在のバージョンMicrosoft Edgeがあります。   

ユーザー補助アーキテクチャの詳細については、「Microsoft Edge Web プラットフォームのブログ投稿を作成する[」を](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/)参照してください。  新しいアーキテクチャがエンド ユーザーのエクスペリエンスを向上させる方法の例、特にマークアップがスクリーン リーダーなどの支援テクノロジを使用して移動するエクスペリエンスを定義する方法の例については [、「HTML5](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/)と UIA を使用して、よりアクセスしやすいユーザー エクスペリエンスを構築する」をご覧ください。
