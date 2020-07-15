---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2DocumentTitleChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: d5af18e8a68c6042ce225635bbe5a1cccb1febc6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880789"
---
# <span data-ttu-id="5d291-104">0.9.515-インターフェイス ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="5d291-104">0.9.515 - interface ICoreWebView2DocumentTitleChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="5d291-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d291-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="5d291-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d291-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="5d291-107">呼び出し元は、このインターフェイスを実装して、Documentのイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5d291-107">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="5d291-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="5d291-108">Summary</span></span>

 <span data-ttu-id="5d291-109">Members</span><span class="sxs-lookup"><span data-stu-id="5d291-109">Members</span></span>                        | <span data-ttu-id="5d291-110">説明</span><span class="sxs-lookup"><span data-stu-id="5d291-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5d291-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="5d291-111">Invoke</span></span>](#invoke) | <span data-ttu-id="5d291-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5d291-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="5d291-113">変更したタイトルを取得するには、DocumentTitle プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="5d291-113">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="5d291-114">Members</span><span class="sxs-lookup"><span data-stu-id="5d291-114">Members</span></span>

#### <span data-ttu-id="5d291-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="5d291-115">Invoke</span></span> 

<span data-ttu-id="5d291-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5d291-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="5d291-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="5d291-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="5d291-118">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="5d291-118">There are no event args and the args parameter will be null.</span></span>

