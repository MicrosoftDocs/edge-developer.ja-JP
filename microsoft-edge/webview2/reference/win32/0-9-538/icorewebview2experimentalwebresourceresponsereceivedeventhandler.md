---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
ms.openlocfilehash: 9447420abddfdb44394042d6742ed1dafd299adf
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886538"
---
# <span data-ttu-id="806ab-104">インターフェイス ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="806ab-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="806ab-105">Web リソースに対する要求に対する応答が webview で受信されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="806ab-105">Fires when a response for a request is received for a Web resource in the webview.</span></span>

## <span data-ttu-id="806ab-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="806ab-106">Summary</span></span>

 <span data-ttu-id="806ab-107">Members</span><span class="sxs-lookup"><span data-stu-id="806ab-107">Members</span></span>                        | <span data-ttu-id="806ab-108">説明</span><span class="sxs-lookup"><span data-stu-id="806ab-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="806ab-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="806ab-109">Invoke</span></span>](#invoke) | <span data-ttu-id="806ab-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="806ab-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="806ab-111">ホストでは、このイベントを使って、Web リソースの実際の要求と応答を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="806ab-111">Host can use this event to view the actual request and response for a Web resource.</span></span> <span data-ttu-id="806ab-112">これには、関連付けられた要求の WebResourceRequested イベントが発生した後の、ネットワークスタックによって行われた要求または応答の変更 (承認ヘッダーの追加など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="806ab-112">This includes any request or response modifications made by the network stack (such as adding of Authorization headers) after the WebResourceRequested event for the associated request has fired.</span></span> <span data-ttu-id="806ab-113">要求オブジェクトまたは応答オブジェクトに加えた変更は無視されます。</span><span class="sxs-lookup"><span data-stu-id="806ab-113">Modifications made to the request or response objects are ignored.</span></span>

## <span data-ttu-id="806ab-114">Members</span><span class="sxs-lookup"><span data-stu-id="806ab-114">Members</span></span>

#### <span data-ttu-id="806ab-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="806ab-115">Invoke</span></span> 

<span data-ttu-id="806ab-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="806ab-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="806ab-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Experimental](icorewebview2experimental.md) \* sender, [ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs](icorewebview2experimentalwebresourceresponsereceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="806ab-117">public HRESULT [Invoke](#invoke)([ICoreWebView2Experimental](icorewebview2experimental.md) \* sender, [ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs](icorewebview2experimentalwebresourceresponsereceivedeventargs.md) \* args)</span></span>

