---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2DevToolsProtocolEventReceivedEventArgs
ms.openlocfilehash: 079b7840689fbeb2931a22f72ad78c1ce0f590b8
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012375"
---
# <span data-ttu-id="70289-104">インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="70289-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="70289-105">DevToolsProtocolEventReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="70289-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="70289-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="70289-106">Summary</span></span>

 <span data-ttu-id="70289-107">Members</span><span class="sxs-lookup"><span data-stu-id="70289-107">Members</span></span>                        | <span data-ttu-id="70289-108">説明</span><span class="sxs-lookup"><span data-stu-id="70289-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="70289-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="70289-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="70289-110">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="70289-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="70289-111">Members</span><span class="sxs-lookup"><span data-stu-id="70289-111">Members</span></span>

#### <span data-ttu-id="70289-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="70289-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="70289-113">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="70289-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="70289-114">パブリック HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* ParameterObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="70289-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

