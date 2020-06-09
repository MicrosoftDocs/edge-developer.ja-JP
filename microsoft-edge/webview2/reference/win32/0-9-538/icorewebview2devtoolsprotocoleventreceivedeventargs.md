---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 2429c519858aa9c55e52d47bea64fc182b6beb73
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699010"
---
# <span data-ttu-id="35ad1-104">インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="35ad1-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="35ad1-105">DevToolsProtocolEventReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="35ad1-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="35ad1-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="35ad1-106">Summary</span></span>

 <span data-ttu-id="35ad1-107">Members</span><span class="sxs-lookup"><span data-stu-id="35ad1-107">Members</span></span>                        | <span data-ttu-id="35ad1-108">説明</span><span class="sxs-lookup"><span data-stu-id="35ad1-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="35ad1-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="35ad1-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="35ad1-110">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="35ad1-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="35ad1-111">Members</span><span class="sxs-lookup"><span data-stu-id="35ad1-111">Members</span></span>

#### <span data-ttu-id="35ad1-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="35ad1-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="35ad1-113">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="35ad1-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="35ad1-114">パブリック HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* ParameterObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="35ad1-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

