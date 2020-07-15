---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: bd2ff8092ce0b8367ce4cc381e94dbd273ae1849
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880830"
---
# <span data-ttu-id="592ec-104">0.9.515-インターフェイス ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="592ec-104">0.9.515 - interface ICoreWebView2Deferral</span></span> 

> [!NOTE]
> <span data-ttu-id="592ec-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="592ec-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="592ec-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="592ec-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="592ec-107">このインターフェイスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="592ec-107">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="592ec-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="592ec-108">Summary</span></span>

 <span data-ttu-id="592ec-109">Members</span><span class="sxs-lookup"><span data-stu-id="592ec-109">Members</span></span>                        | <span data-ttu-id="592ec-110">説明</span><span class="sxs-lookup"><span data-stu-id="592ec-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="592ec-111">Complete</span><span class="sxs-lookup"><span data-stu-id="592ec-111">Complete</span></span>](#complete) | <span data-ttu-id="592ec-112">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="592ec-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="592ec-113">Members</span><span class="sxs-lookup"><span data-stu-id="592ec-113">Members</span></span>

#### <span data-ttu-id="592ec-114">Complete</span><span class="sxs-lookup"><span data-stu-id="592ec-114">Complete</span></span> 

<span data-ttu-id="592ec-115">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="592ec-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="592ec-116">パブリック HRESULT[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="592ec-116">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="592ec-117">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="592ec-117">Complete should only be called once for each deferral taken.</span></span>

