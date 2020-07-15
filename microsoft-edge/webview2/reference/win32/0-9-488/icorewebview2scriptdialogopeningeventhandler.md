---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ScriptDialogOpeningEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 86bb854bbce1a3cc842f656ffea3cf600136f38d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880312"
---
# <span data-ttu-id="9474d-104">0.9.515-インターフェイス ICoreWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="9474d-104">0.9.515 - interface ICoreWebView2ScriptDialogOpeningEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="9474d-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9474d-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="9474d-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9474d-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ScriptDialogOpeningEventHandler
  : public IUnknown
```

<span data-ttu-id="9474d-107">呼び出し元は、このインターフェイスを実装して Scriptの開始イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9474d-107">The caller implements this interface to receive the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="9474d-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="9474d-108">Summary</span></span>

 <span data-ttu-id="9474d-109">Members</span><span class="sxs-lookup"><span data-stu-id="9474d-109">Members</span></span>                        | <span data-ttu-id="9474d-110">説明</span><span class="sxs-lookup"><span data-stu-id="9474d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9474d-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="9474d-111">Invoke</span></span>](#invoke) | <span data-ttu-id="9474d-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9474d-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="9474d-113">Members</span><span class="sxs-lookup"><span data-stu-id="9474d-113">Members</span></span>

#### <span data-ttu-id="9474d-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="9474d-114">Invoke</span></span> 

<span data-ttu-id="9474d-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9474d-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="9474d-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="9474d-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span></span>

