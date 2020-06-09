---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Microsoft Edge WebView2 コントロール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、browser control、edge html、Windows フォーム、WinForms、WPF、.NET
ms.openlocfilehash: 1b140d9f644c7a864cac4966bb4cfdd400feeb0d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697743"
---
# Microsoft Edge WebView2 の概要 (プレビュー)  

Microsoft Edge WebView2 コントロールを使うと、ネイティブアプリケーションで web 技術 (HTML、CSS、JavaScript \) を埋め込むことができます。  WebView2 コントロールは、 [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com)をレンダリングエンジンとして使用して、ネイティブアプリケーションで web コンテンツを表示します。  WebView2 を使用すると、ネイティブアプリケーションのさまざまな場所に web コードを埋め込むことができます。または、1つの WebView 内でネイティブアプリケーション全体をビルドすることもできます。  WebView2 アプリケーションの作成を開始する方法については、「使用[を開始する」を参照し](./index.md#getting-started)てください。  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="WebView とは":::
   WebView とは  
:::image-end:::  

> [!NOTE]
> WebView2 Preview は、早期にプロトタイプを形成し、API の形成に役立つフィードバックを収集することを目的としています。  Microsoft Edge WebView チームでは、運用アプリでプレビューを使用することはお勧めしません。[変更が中断](./releasenotes.md)される可能性があります。  

## ハイブリッドアプリケーションのアプローチ  

通常、開発者は、web アプリケーションまたはネイティブアプリケーションのビルドのどちらかを選ぶ必要があります。  意思決定は、リーチとパワーの間のトレードオフに対して行われます。  Web アプリケーションを使用すると広範なアクセスが可能になります。  Web 開発者は、すべての異なるプラットフォームで、ほとんどのコードを再利用することができます。  ただし、ネイティブアプリケーションは、ネイティブプラットフォーム全体の機能を利用します。  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native":::
   Web native  
:::image-end:::  

ハイブリッドアプリケーションを使用すると、開発者は両方のメリットを享受できます。  ハイブリッドアプリケーションの開発者は、web プラットフォームの ubiquity と強み、およびネイティブプラットフォームの機能と機能を最大限に活用できます。  

## WebView2 の利点   

:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="WebView の理由":::
   WebView の理由  
:::image-end:::  

:::row:::
   :::column span="1":::
      **Web エコシステム \ & のスキルセット**  
      Web エコシステム内に存在する web プラットフォーム、ライブラリ、ツール、人材をすべて活用できます。  
   :::column-end:::
   :::column span="1":::
      **急速な革新**  
      Web 開発により、迅速な展開とイテレーションが可能になります。  
   :::column-end:::
   :::column span="1":::
      **Windows 7、8、10のサポート**  
      Windows 7、8、10での一貫したユーザーエクスペリエンスのサポート。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **ネイティブ機能**  
      ネイティブ Api の完全なセットにアクセスします。  
   :::column-end:::
   :::column span="1":::
      **コード共有**  
      Web コードをコードベースに追加することで、複数のプラットフォーム間での再利用を高速化できます。  
   :::column-end:::
   :::column span="1":::
      **Microsoft サポート**  
      Microsoft は、WebView2 が GA としてリリースされたときにサポートを提供し、新しい機能要求を追加します。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **Evergreen 分布**  
      最新バージョンの Chromium を使用して、定期的なプラットフォームの更新とセキュリティ更新プログラムを利用します。  
   :::column-end:::
   :::column span="1":::
      **固定**\ (近日公開)  
      アプリケーションに Chromium ビットをパッケージ化することを選択します。  
   :::column-end:::
   :::column span="1":::
      **段階的導入**  
      アプリケーションに web コンポーネントを追加します。  
   :::column-end:::
:::row-end:::

## 開始するには  

WebView2 コントロールを使用してアプリケーションをビルドしてテストするには、 [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download)と[WebView2 SDK](https://aka.ms/webviewnuget)の両方をインストールする必要があります。  開始するには、次のいずれかのオプションを選択します。  

*   [Win32 C/C + + の概要](./gettingstarted/win32.md)  
*   [WPF の概要](./gettingstarted/wpf.md)  
*   [WinForms の概要](./gettingstarted/winforms.md)  

[WebView2 サンプル](https://github.com/MicrosoftEdge/WebView2Samples)リポジトリには、WebView2 sdk のすべての機能と API の使用パターンを示すサンプルが含まれています。 WebView2 SDK に追加された機能により、サンプルアプリケーションが更新されます。   

## サポートされているプラットフォーム  

開発者プレビューは、次のプログラミング環境で利用できます。  

*   Win32 C/c + +  
*   .NET Framework 4.6.2 以降  
*   .NET Core 3.0 以降  
*   [WinUI 3.0](/uwp/toolkits/winui3/)  

WebView2 アプリケーションは、次のバージョンの Windows で実行できます。  

*   Windows 10  
*   Windows 8.1  
*   Windows 8  
*   Windows 7  
*   Windows Server 2016  
*   Windows Server 2012  
*   Windows Server 2012R2  
*   Windows Server 2008 R2  

## 次のステップ  

WebView2 アプリケーションを作成して展開する方法の詳細については、概念的なドキュメントと使い方ガイドを参照してください。  

#### 概念  

*   [WebView2 SDK と Microsoft Edge のバージョン管理](./concepts/versioning.md)
*   [WebView2 アプリケーションの配布](./concepts/distribution.md)  
 
#### 使い方ガイド  

*   [DevTools と Visual Studio スクリプトのデバッグによる WebView2 のデバッグ](./howto/debug.md)  
*   [Microsoft EdgeDriver での WebView2 の自動化とデバッグ](./howto/webdriver.md)  

<!--todo: add how-tos when available  -->  

## WebView2 チームと連絡を取り合う  

フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。  WebView[フィードバックリポジトリ](https://aka.ms/webviewfeedback)にアクセスして、機能のリクエストまたはバグレポートを送信します。  また、既知の問題を検索するのに適した場所です。  

> [!NOTE]
> Microsoft Edge WebView チームは、開発者向けプレビューでもデータを収集して、より良い WebView を構築できるようにします。  WebView データの収集をオフにするには `edge://settings/privacy` 、Microsoft Edge ブラウザーを表示し、ブラウザーデータの収集をオフにします。  
