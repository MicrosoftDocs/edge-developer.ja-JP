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
ms.openlocfilehash: 7d21db7c3f0a66f60f32e92b3951151b8d13a002
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698079"
---
# <span data-ttu-id="eb1c4-104">インターフェイス ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="eb1c4-104">interface ICoreWebView2Deferral</span></span> 

> [!NOTE]
> <span data-ttu-id="eb1c4-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb1c4-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="eb1c4-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb1c4-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="eb1c4-107">このインターフェイスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="eb1c4-107">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="eb1c4-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="eb1c4-108">Summary</span></span>

 <span data-ttu-id="eb1c4-109">Members</span><span class="sxs-lookup"><span data-stu-id="eb1c4-109">Members</span></span>                        | <span data-ttu-id="eb1c4-110">説明</span><span class="sxs-lookup"><span data-stu-id="eb1c4-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="eb1c4-111">Complete</span><span class="sxs-lookup"><span data-stu-id="eb1c4-111">Complete</span></span>](#complete) | <span data-ttu-id="eb1c4-112">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="eb1c4-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="eb1c4-113">Members</span><span class="sxs-lookup"><span data-stu-id="eb1c4-113">Members</span></span>

#### <span data-ttu-id="eb1c4-114">Complete</span><span class="sxs-lookup"><span data-stu-id="eb1c4-114">Complete</span></span> 

<span data-ttu-id="eb1c4-115">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="eb1c4-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="eb1c4-116">パブリック HRESULT[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="eb1c4-116">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="eb1c4-117">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="eb1c4-117">Complete should only be called once for each deferral taken.</span></span>

