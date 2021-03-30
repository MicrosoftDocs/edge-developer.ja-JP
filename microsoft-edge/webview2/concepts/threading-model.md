---
description: スレッド化
title: スレッド モデル |WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: 7b447f5cc5fcce3439166638d47a0b87e5536c0a
ms.sourcegitcommit: 5e218b24fb21fcfa9c82b99f17373fed1ba5a21c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "11462044"
---
# <a name="threading-model"></a>スレッド化 

:::row:::
   :::column span="1":::
      サポートされているプラットフォーム:
   :::column-end:::
   :::column span="2":::
      Win32, Windows Forms, WinUi, WPF
   :::column-end:::
:::row-end:::  

WebView2 コントロールはコンポーネント オブジェクト モデル [(COM)][WindowsWin32ComTheComponentObjectModel] に基づいており、単一スレッド アパートメント [(STA) スレッドで実行する必要][WindowsWin32ComSingleThreadedApartments] があります。  

## <a name="thread-safety"></a>スレッド セーフティ  

WebView2 は UI スレッド上に作成する必要があります。  具体的には、メッセージ ポンプを持つスレッドです。  そのスレッドですべてのコールバックが発生し、WebView2 への要求は、そのスレッドで実行する必要があります。  別のスレッドから WebView2 を使用しても安全ではありません。  

唯一の例外は、 の `Content` プロパティです `CoreWebView2WebResourceRequest` 。  プロパティ `Content` ストリームは、バックグラウンド スレッドから読み取ります。  UI スレッドのパフォーマンス低下を防ぐために、ストリームはアジャイルまたはバックグラウンド STA から作成する必要があります。  

## <a name="re-entrancy"></a>再エントランシー  

イベント ハンドラーや完了ハンドラーを含むコールバックは、シリアルに実行されます。  
イベント ハンドラーを実行してメッセージ ループを開始した後、イベント ハンドラーまたは完了コールバックを再入可能な方法で実行できません。  

## <a name="deferrals"></a>遅延  

一部の WebView2 イベントは、関連するイベント引数に設定された値を読み取り、イベント ハンドラーの完了後にいくつかのアクションを開始します。  このようなイベント ハンドラーを非同期操作で実行する必要がある場合は、関連付けられたイベントのイベント引数でメソッド `GetDeferral` を使用します。  返されるオブジェクトは、イベント ハンドラーが要求されるまで、イベント ハンドラーが `Deferral` `Complete` 完全と見なされません `Deferral` 。  

たとえば、イベント ハンドラーが完了すると、子ウィンドウとして接続するイベント `NewWindowRequested` `CoreWebView2` を提供できます。  ただし、非同期的に作成する必要がある場合 `CoreWebView2` は、 で `GetDeferral` メソッドを要求します `NewWindowRequestedEventArgs` 。  非同期的に作成し、オブジェクトのプロパティを設定した後、メソッドを使用してオブジェクトの要求 `CoreWebView2` `NewWindow` `NewWindowRequestedEventArgs` `Complete` `Deferral` を返 `GetDeferral` します。  

## <a name="block-the-ui-thread"></a>UI スレッドをブロックする  

WebView2 は、UI スレッドのメッセージ ポンプに依存して、イベント ハンドラー コールバックと非同期メソッド完了コールバックを実行します。  メッセージ ポンプをブロックするメソッドを使用する場合は、WebView2 イベント ハンドラーと非同期メソッド完了ハンドラーは `Task.Result` `WaitForSingleObject` 実行されません。  たとえば、次のコードは完了しないので、完了するまでメッセージ ポンプを `Task.Result` `ExecuteScriptAsync` 停止します。  メッセージ ポンプがブロックされたので、 `ExecuteScriptAsync` 完了できない。   

```csharp
private void Button_Click(object sender, EventArgs e)
{
    string result = webView2Control.CoreWebView2.ExecuteScriptAsync("'test'").Result;
    MessageBox.Show(this, result, "Script Result");
}
```  

メッセージ ポンプや UI スレッドをブロックしない `await` `async` and などの非同期 `await` メカニズムを使用します。  

```csharp
private async void Button_Click(object sender, EventArgs e)
{
    string result = await webView2Control.CoreWebView2.ExecuteScriptAsync("'test'");
    MessageBox.Show(this, result, "Script Result");
}
```  

## <a name="see-also"></a>関連項目  

*   WebView2 の使用を開始するには [、「WebView2 Getting Started Guides guides」に][Webview2IndexGettingStarted] 移動します。  
*   WebView2 機能の包括的な例については、GitHub の [WebView2Samples リポジトリ][GithubMicrosoftedgeWebview2samples] に移動します。  
*   WebView2 API の詳細については、「API リファレンス」 [に移動します][DotnetApiMicrosoftWebWebview2WpfWebview2]。  
*   WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGettingStarted]: ../index.md#getting-started "はじめに - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス | Microsoft Docs"  

[WindowsWin32ComSingleThreadedApartments]: /windows/win32/com/single-threaded-apartments "シングル スレッド アパートメント |Microsoft Docs"  
[WindowsWin32ComTheComponentObjectModel]: /windows/win32/com/the-component-object-model "Component オブジェクト モデル |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
