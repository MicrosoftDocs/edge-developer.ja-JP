---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: cf321ff1091883827b7ce6cda7248a06f1128867
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654414"
---
# <span data-ttu-id="c7ac7-104">インターフェイス IWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="c7ac7-104">interface IWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="c7ac7-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7ac7-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="c7ac7-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7ac7-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="c7ac7-107">DevToolsProtocolEventReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="c7ac7-107">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="c7ac7-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="c7ac7-108">Summary</span></span>

 <span data-ttu-id="c7ac7-109">Members</span><span class="sxs-lookup"><span data-stu-id="c7ac7-109">Members</span></span>                        | <span data-ttu-id="c7ac7-110">説明</span><span class="sxs-lookup"><span data-stu-id="c7ac7-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c7ac7-111">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="c7ac7-111">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="c7ac7-112">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c7ac7-112">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="c7ac7-113">Members</span><span class="sxs-lookup"><span data-stu-id="c7ac7-113">Members</span></span>

#### <span data-ttu-id="c7ac7-114">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="c7ac7-114">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="c7ac7-115">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c7ac7-115">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="c7ac7-116">パブリック HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* ParameterObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="c7ac7-116">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

