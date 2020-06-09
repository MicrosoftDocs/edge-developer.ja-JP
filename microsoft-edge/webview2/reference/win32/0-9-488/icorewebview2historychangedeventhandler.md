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
ms.openlocfilehash: 0305517d17bfa812dbaee9b238403f2d9f1fb22d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697806"
---
# <span data-ttu-id="d0e81-104">インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d0e81-104">interface ICoreWebView2HistoryChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="d0e81-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0e81-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="d0e81-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0e81-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="d0e81-107">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d0e81-107">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="d0e81-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d0e81-108">Summary</span></span>

 <span data-ttu-id="d0e81-109">Members</span><span class="sxs-lookup"><span data-stu-id="d0e81-109">Members</span></span>                        | <span data-ttu-id="d0e81-110">説明</span><span class="sxs-lookup"><span data-stu-id="d0e81-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d0e81-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="d0e81-111">Invoke</span></span>](#invoke) | <span data-ttu-id="d0e81-112">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="d0e81-112">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="d0e81-113">Members</span><span class="sxs-lookup"><span data-stu-id="d0e81-113">Members</span></span>

#### <span data-ttu-id="d0e81-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="d0e81-114">Invoke</span></span> 

<span data-ttu-id="d0e81-115">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="d0e81-115">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="d0e81-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="d0e81-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

