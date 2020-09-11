---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2DevToolsProtocolEventReceivedEventArgs
ms.openlocfilehash: 79af7b28b8b8ab7e2e2b6612f121208b8d917725
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010272"
---
# <span data-ttu-id="42f4e-104">0.9.579-インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="42f4e-104">0.9.579 - interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="42f4e-105">DevToolsProtocolEventReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="42f4e-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="42f4e-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="42f4e-106">Summary</span></span>

 <span data-ttu-id="42f4e-107">Members</span><span class="sxs-lookup"><span data-stu-id="42f4e-107">Members</span></span>                        | <span data-ttu-id="42f4e-108">説明</span><span class="sxs-lookup"><span data-stu-id="42f4e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="42f4e-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="42f4e-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="42f4e-110">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="42f4e-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="42f4e-111">Members</span><span class="sxs-lookup"><span data-stu-id="42f4e-111">Members</span></span>

#### <span data-ttu-id="42f4e-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="42f4e-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="42f4e-113">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="42f4e-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="42f4e-114">パブリック HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* ParameterObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="42f4e-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

