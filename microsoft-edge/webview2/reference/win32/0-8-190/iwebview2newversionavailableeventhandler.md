---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NewVersionAvailableEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 3a9af31477e7b4155bece55ec2faef85efccbd0d
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884982"
---
# <span data-ttu-id="f1a76-104">0.8.355-インターフェイス IWebView2NewVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="f1a76-104">0.8.355 - interface IWebView2NewVersionAvailableEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NewVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="f1a76-105">呼び出し元は、このインターフェイスを実装して、新しいバージョンの利用可能なイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f1a76-105">The caller implements this interface to receive NewVersionAvailable events.</span></span>

## <span data-ttu-id="f1a76-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f1a76-106">Summary</span></span>

 <span data-ttu-id="f1a76-107">Members</span><span class="sxs-lookup"><span data-stu-id="f1a76-107">Members</span></span>                        | <span data-ttu-id="f1a76-108">説明</span><span class="sxs-lookup"><span data-stu-id="f1a76-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f1a76-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f1a76-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f1a76-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f1a76-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="f1a76-111">新しいバージョン番号を取得するには、 [IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md)の get_NewVersion メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1a76-111">Use the get_NewVersion method of [IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) to get the new version number.</span></span>

## <span data-ttu-id="f1a76-112">Members</span><span class="sxs-lookup"><span data-stu-id="f1a76-112">Members</span></span>

#### <span data-ttu-id="f1a76-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="f1a76-113">Invoke</span></span> 

<span data-ttu-id="f1a76-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f1a76-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f1a76-115">パブリック HRESULT[呼び出し](#invoke)([IWebView2Environment](IWebView2Environment.md) \* Webviewenvironment、[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="f1a76-115">public HRESULT [Invoke](#invoke)([IWebView2Environment](IWebView2Environment.md) \* webviewEnvironment,[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) \* args)</span></span>

