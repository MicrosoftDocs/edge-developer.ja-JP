---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e7fbc952a44bdd38e6e59c46adafb8e71b7904b6
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654437"
---
# <span data-ttu-id="47fdb-104">インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="47fdb-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="47fdb-105">DevToolsProtocolEventReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="47fdb-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="47fdb-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="47fdb-106">Summary</span></span>

 <span data-ttu-id="47fdb-107">Members</span><span class="sxs-lookup"><span data-stu-id="47fdb-107">Members</span></span>                        | <span data-ttu-id="47fdb-108">説明</span><span class="sxs-lookup"><span data-stu-id="47fdb-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="47fdb-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="47fdb-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="47fdb-110">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="47fdb-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="47fdb-111">Members</span><span class="sxs-lookup"><span data-stu-id="47fdb-111">Members</span></span>

#### <span data-ttu-id="47fdb-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="47fdb-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="47fdb-113">JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="47fdb-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="47fdb-114">パブリック HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* ParameterObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="47fdb-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

