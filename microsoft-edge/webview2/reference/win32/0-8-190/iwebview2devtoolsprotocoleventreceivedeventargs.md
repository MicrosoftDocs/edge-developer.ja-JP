---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 920d95b737a15926e6de33cfed0ee9a98eeade78
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886160"
---
# <span data-ttu-id="10fb8-104">0.8.355-インターフェイス IWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="10fb8-104">0.8.355 - interface IWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="10fb8-105">DevToolsProtocolEventReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="10fb8-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="10fb8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="10fb8-106">Summary</span></span>

 <span data-ttu-id="10fb8-107">Members</span><span class="sxs-lookup"><span data-stu-id="10fb8-107">Members</span></span>                        | <span data-ttu-id="10fb8-108">説明</span><span class="sxs-lookup"><span data-stu-id="10fb8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="10fb8-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="10fb8-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="10fb8-110">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="10fb8-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="10fb8-111">Members</span><span class="sxs-lookup"><span data-stu-id="10fb8-111">Members</span></span>

#### <span data-ttu-id="10fb8-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="10fb8-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="10fb8-113">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="10fb8-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="10fb8-114">パブリック HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* ParameterObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="10fb8-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

