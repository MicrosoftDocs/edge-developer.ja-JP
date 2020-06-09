---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 84ff41eeb30d5c3561666a71f989e02163419152
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697967"
---
# <span data-ttu-id="eea10-104">インターフェイス ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="eea10-104">interface ICoreWebView2DocumentTitleChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="eea10-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eea10-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="eea10-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eea10-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="eea10-107">呼び出し元は、このインターフェイスを実装して、Documentのイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="eea10-107">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="eea10-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="eea10-108">Summary</span></span>

 <span data-ttu-id="eea10-109">Members</span><span class="sxs-lookup"><span data-stu-id="eea10-109">Members</span></span>                        | <span data-ttu-id="eea10-110">説明</span><span class="sxs-lookup"><span data-stu-id="eea10-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="eea10-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="eea10-111">Invoke</span></span>](#invoke) | <span data-ttu-id="eea10-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="eea10-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="eea10-113">変更したタイトルを取得するには、DocumentTitle プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="eea10-113">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="eea10-114">Members</span><span class="sxs-lookup"><span data-stu-id="eea10-114">Members</span></span>

#### <span data-ttu-id="eea10-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="eea10-115">Invoke</span></span> 

<span data-ttu-id="eea10-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="eea10-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="eea10-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="eea10-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="eea10-118">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="eea10-118">There are no event args and the args parameter will be null.</span></span>

