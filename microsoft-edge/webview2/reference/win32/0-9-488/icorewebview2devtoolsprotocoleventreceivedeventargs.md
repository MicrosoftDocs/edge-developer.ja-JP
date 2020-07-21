---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 2ed75f2a12387b6b8de628ac27ef536cf43fb8b1
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885409"
---
# <span data-ttu-id="d9a30-104">0.9.515-インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d9a30-104">0.9.515 - interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="d9a30-105">DevToolsProtocolEventReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="d9a30-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="d9a30-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d9a30-106">Summary</span></span>

 <span data-ttu-id="d9a30-107">Members</span><span class="sxs-lookup"><span data-stu-id="d9a30-107">Members</span></span>                        | <span data-ttu-id="d9a30-108">説明</span><span class="sxs-lookup"><span data-stu-id="d9a30-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d9a30-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="d9a30-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="d9a30-110">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d9a30-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="d9a30-111">Members</span><span class="sxs-lookup"><span data-stu-id="d9a30-111">Members</span></span>

#### <span data-ttu-id="d9a30-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="d9a30-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="d9a30-113">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d9a30-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="d9a30-114">パブリック HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* ParameterObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="d9a30-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

