---
description: マニフェストで API のアクセス許可を宣言する方法について説明します。
title: 拡張マニフェストで API アクセス許可を宣言する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 987279a8072388d3fd47ee8b7cbf5f9bb3c483e0
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461547"
---
<!-- Copyright A. W. Fuchs

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="declare-api-permissions-in-extension-manifests"></a><span data-ttu-id="8a9e9-104">拡張マニフェストで API アクセス許可を宣言する</span><span class="sxs-lookup"><span data-stu-id="8a9e9-104">Declare API permissions in extension manifests</span></span>  

<span data-ttu-id="8a9e9-105">ほとんどの API を使用するには `chrome.*` 、拡張機能でマニフェストで宣言 `permissions` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-105">To use most of the `chrome.*` APIs, your extension must declare the `permissions` in the manifest.</span></span>  <span data-ttu-id="8a9e9-106">次の表からアクセス許可文字列を使用してアクセス許可を宣言するか、同様の文字列に一致するパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-106">You may declare permissions using a permission string from the table that follows, or use a pattern to match similar strings.</span></span>  <span data-ttu-id="8a9e9-107">アクセス許可は、拡張機能がマルウェアによって侵害された場合に、拡張機能を制限するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-107">Permissions help to constrain your extension if it gets compromised by malware.</span></span>  <span data-ttu-id="8a9e9-108">権限の警告を使用して拡張機能をインストールする前に、一部のアクセス許可がユーザーに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-108">Some permissions may display to users before installation of the extension using Permission Warnings.</span></span>  

<span data-ttu-id="8a9e9-109">API でマニフェストでアクセス許可を宣言する必要がある場合は、その API のドキュメントを参照して、必要なアクセス許可を理解してください。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-109">If an API requires you to declare permissions in the manifest, review the documentation for that API to understand the needed permissions.</span></span>  <span data-ttu-id="8a9e9-110">たとえば、[記憶域 API] ページでは、アクセス許可を宣言する方法について説明 `storage` します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-110">For example, the Storage API page describes how to declare the `storage` permission.</span></span>  

<span data-ttu-id="8a9e9-111">次のコード スニペットでは、マニフェスト ファイルでアクセス許可を宣言する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-111">The following code snippet outlines how to declare permissions in the manifest file.</span></span>  

```json
"permissions": [
  "tabs",
  "bookmarks",
  "http://www.blogger.com/",
  "http://*.google.com/",
  "unlimitedStorage"
]
```  

<span data-ttu-id="8a9e9-112">次の表に、マニフェストで使用する現在使用可能なアクセス許可文字列と説明を示します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-112">The following table lists the currently available permission strings to use in your manifest, and the descriptions.</span></span>  

| <span data-ttu-id="8a9e9-113">アクセス許可文字列</span><span class="sxs-lookup"><span data-stu-id="8a9e9-113">Permission string</span></span> | <span data-ttu-id="8a9e9-114">詳細</span><span class="sxs-lookup"><span data-stu-id="8a9e9-114">Details</span></span> |  
|:--- |:--- |  
| `activeTab` | <span data-ttu-id="8a9e9-115">仕様に従って拡張機能にアクセス許可が付与される要求 `activeTab` 。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-115">Requests that the extension is granted permissions according to the `activeTab` specification.</span></span> |  
| `alarms` | <span data-ttu-id="8a9e9-116">拡張機能に API へのアクセス権を与 `chrome.alarms` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-116">Gives your extension access to the `chrome.alarms` API.</span></span> |  
| `background` | <span data-ttu-id="8a9e9-117">Microsoft Edge を早期に起動し、遅くシャットダウンし、拡張機能の寿命が長くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-117">Makes Microsoft Edge start up early and shut down late, so that extensions may have a longer life.</span></span>  <span data-ttu-id="8a9e9-118">インストールされている拡張機能にアクセス許可がある場合、ユーザーがユーザーのコンピューターにログインするとすぐに、ユーザーが Microsoft Edge を起動する前に、Microsoft Edge が目に見えて `background` 実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-118">When any installed extension has `background` permission, Microsoft Edge runs invisibly as soon as the user logs into the user's computer, and before the user launches Microsoft Edge.</span></span>  <span data-ttu-id="8a9e9-119">また、このアクセス許可により、ユーザーが明示的に Microsoft Edge を終了するまで、最後のウィンドウが閉じた後でも、Microsoft Edge は実行 `background` を続行できます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-119">The `background` permission also makes Microsoft Edge continue running, even after its last window is closed, until the user explicitly quits Microsoft Edge.</span></span>  <span data-ttu-id="8a9e9-120">このアクセス許可は、ブラウザーで無効になっている拡張機能には影響を与えることはできません。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-120">This permission does not affect extensions that are turned off in the browser.</span></span>  <span data-ttu-id="8a9e9-121">アクセス `background` 許可は、通常、バックグラウンド ページで使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-121">The `background` permission is normally used on a background page.</span></span> |  
| `bookmarks` | <span data-ttu-id="8a9e9-122">拡張機能に API へのアクセス権を与 `chrome.bookmarks` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-122">Gives your extension access to the `chrome.bookmarks` API.</span></span> |  
| `browsingData` | <span data-ttu-id="8a9e9-123">拡張機能に API へのアクセス権を与 `chrome.browsingData` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-123">Gives your extension access to the `chrome.browsingData` API.</span></span> |  
| `certificateProvider` | <span data-ttu-id="8a9e9-124">拡張機能に API へのアクセス権を与 `chrome.certificateProvider` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-124">Gives your extension access to the `chrome.certificateProvider` API.</span></span> |  
| `clipboardRead` | <span data-ttu-id="8a9e9-125">拡張機能で使用する場合は必須 `document.execCommand('paste')` です。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-125">Required if the extension uses `document.execCommand('paste')`.</span></span> |  
| `clipboardWrite` | <span data-ttu-id="8a9e9-126">拡張機能の使用またはを `document.execCommand('copy')` 示します `document.execCommand('cut')` 。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-126">Indicates the extension uses `document.execCommand('copy')` or `document.execCommand('cut')`.</span></span> |  
| `contentSettings` | <span data-ttu-id="8a9e9-127">拡張機能に API へのアクセス権を与 `chrome.contentSettings` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-127">Gives your extension access to the `chrome.contentSettings` API.</span></span> |  
| `contextMenus` | <span data-ttu-id="8a9e9-128">拡張機能に API へのアクセス権を与 `chrome.contextMenus` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-128">Gives your extension access to the `chrome.contextMenus` API.</span></span> |  
| `cookies` | <span data-ttu-id="8a9e9-129">拡張機能に API へのアクセス権を与 `chrome.cookies` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-129">Gives your extension access to the `chrome.cookies` API.</span></span> |  
| `debugger` | <span data-ttu-id="8a9e9-130">拡張機能に API へのアクセス権を与 `chrome.debugger` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-130">Gives your extension access to the `chrome.debugger` API.</span></span> |  
| `declarativeContent` | <span data-ttu-id="8a9e9-131">拡張機能に API へのアクセス権を与 `chrome.declarativeContent` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-131">Gives your extension access to the `chrome.declarativeContent` API.</span></span> |  
| `declarativeNetRequest` | <span data-ttu-id="8a9e9-132">拡張機能に API へのアクセス権を与 `chrome.declarativeNetRequest` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-132">Gives your extension access to the `chrome.declarativeNetRequest` API.</span></span> |  
| `declarativeNetRequestFeedback` | <span data-ttu-id="8a9e9-133">API 内のイベントとメソッドへの拡張機能アクセスを許可し、一致する宣言型ルールに関する `chrome.declarativeNetRequest` 情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-133">Grants the extension access to events and methods within the `chrome.declarativeNetRequest` API, which returns information on declarative rules matched.</span></span> |  
| `declarativeWebRequest` | <span data-ttu-id="8a9e9-134">拡張機能に API へのアクセス権を与 `chrome.declarativeWebRequest` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-134">Gives your extension access to the `chrome.declarativeWebRequest` API.</span></span> |  
| `desktopCapture` | <span data-ttu-id="8a9e9-135">拡張機能に API へのアクセス権を与 `chrome.desktopCapture` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-135">Gives your extension access to the `chrome.desktopCapture` API.</span></span> |  
| `documentScan` | <span data-ttu-id="8a9e9-136">拡張機能に API へのアクセス権を与 `chrome.documentScan` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-136">Gives your extension access to the `chrome.documentScan` API.</span></span> |  
| `downloads` | <span data-ttu-id="8a9e9-137">拡張機能に API へのアクセス権を与 `chrome.downloads` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-137">Gives your extension access to the `chrome.downloads` API.</span></span> |  
| `enterprise.deviceAttributes` | <span data-ttu-id="8a9e9-138">拡張機能に API へのアクセス権を与 `chrome.enterprise.deviceAttributes` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-138">Gives your extension access to the `chrome.enterprise.deviceAttributes` API.</span></span> |  
| `enterprise.hardwarePlatform` | <span data-ttu-id="8a9e9-139">拡張機能に API へのアクセス権を与 `chrome.enterprise.hardwarePlatform` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-139">Gives your extension access to the `chrome.enterprise.hardwarePlatform` API.</span></span> |  
| `enterprise.networkingAttributes` | <span data-ttu-id="8a9e9-140">拡張機能に API へのアクセス権を与 `chrome.enterprise.networkingAttributes` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-140">Gives your extension access to the `chrome.enterprise.networkingAttributes` API.</span></span> |  
| `enterprise.platformKeys` | <span data-ttu-id="8a9e9-141">拡張機能に API へのアクセス権を与 `chrome.enterprise.platformKeys` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-141">Gives your extension access to the `chrome.enterprise.platformKeys` API.</span></span> |  
| `experimental` | <span data-ttu-id="8a9e9-142">拡張機能が API を使用する場合は必須 `chrome.experimental.*` です。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-142">Required if the extension uses any `chrome.experimental.*` API.</span></span> |  
| `fileBrowserHandler` | <span data-ttu-id="8a9e9-143">拡張機能に API へのアクセス権を与 `chrome.fileBrowserHandler` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-143">Gives your extension access to the `chrome.fileBrowserHandler` API.</span></span> |  
| `fileSystemProvider` | <span data-ttu-id="8a9e9-144">拡張機能に API へのアクセス権を与 `chrome.fileSystemProvider` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-144">Gives your extension access to the `chrome.fileSystemProvider` API.</span></span> |  
| `fontSettings` | <span data-ttu-id="8a9e9-145">拡張機能に API へのアクセス権を与 `chrome.fontSettings` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-145">Gives your extension access to the `chrome.fontSettings` API.</span></span> |  
| `geolocation` | <span data-ttu-id="8a9e9-146">ユーザーにアクセス許可を求めることなく、拡張機能で位置情報 API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-146">Allows the extension to use the geolocation API without prompting the user for permission.</span></span> |  
| `history` | <span data-ttu-id="8a9e9-147">拡張機能に API へのアクセス権を与 `chrome.history` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-147">Gives your extension access to the `chrome.history` API.</span></span> |  
| `identity` | <span data-ttu-id="8a9e9-148">拡張機能に API へのアクセス権を与 `chrome.identity` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-148">Gives your extension access to the `chrome.identity` API.</span></span> |  
| `idle` | <span data-ttu-id="8a9e9-149">拡張機能に API へのアクセス権を与 `chrome.idle` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-149">Gives your extension access to the `chrome.idle` API.</span></span> |  
| `loginState` | <span data-ttu-id="8a9e9-150">拡張機能に API へのアクセス権を与 `chrome.loginState` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-150">Gives your extension access to the `chrome.loginState` API.</span></span> |  
| `management` | <span data-ttu-id="8a9e9-151">拡張機能に API へのアクセス権を与 `chrome.management` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-151">Gives your extension access to the `chrome.management` API.</span></span> |  
| `nativeMessaging` | <span data-ttu-id="8a9e9-152">ネイティブ メッセージング API への拡張機能アクセス権を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-152">Gives your extension access to the native messaging API.</span></span> |  
| `notifications` | <span data-ttu-id="8a9e9-153">拡張機能に API へのアクセス権を与 `chrome.notifications` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-153">Gives your extension access to the `chrome.notifications` API.</span></span> |  
| `pageCapture` | <span data-ttu-id="8a9e9-154">拡張機能に API へのアクセス権を与 `chrome.pageCapture` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-154">Gives your extension access to the `chrome.pageCapture` API.</span></span> |  
| `platformKeys` | <span data-ttu-id="8a9e9-155">拡張機能に API へのアクセス権を与 `chrome.platformKeys` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-155">Gives your extension access to the `chrome.platformKeys` API.</span></span> |  
| `power` | <span data-ttu-id="8a9e9-156">拡張機能に API へのアクセス権を与 `chrome.power` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-156">Gives your extension access to the `chrome.power` API.</span></span> |  
| `printerProvider` | <span data-ttu-id="8a9e9-157">拡張機能に API へのアクセス権を与 `chrome.printerProvider` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-157">Gives your extension access to the `chrome.printerProvider` API.</span></span> |  
| `printing` | <span data-ttu-id="8a9e9-158">拡張機能に API へのアクセス権を与 `chrome.printing` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-158">Gives your extension access to the `chrome.printing` API.</span></span> |  
| `printingMetrics` | <span data-ttu-id="8a9e9-159">拡張機能に API へのアクセス権を与 `chrome.printingMetrics` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-159">Gives your extension access to the `chrome.printingMetrics` API.</span></span> |  
| `privacy` | <span data-ttu-id="8a9e9-160">拡張機能に API へのアクセス権を与 `chrome.privacy` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-160">Gives your extension access to the `chrome.privacy` API.</span></span> |  
| `processes` | <span data-ttu-id="8a9e9-161">拡張機能に API へのアクセス権を与 `chrome.processes` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-161">Gives your extension access to the `chrome.processes` API.</span></span> |  
| `proxy` | <span data-ttu-id="8a9e9-162">拡張機能に API へのアクセス権を与 `chrome.proxy` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-162">Gives your extension access to the `chrome.proxy` API.</span></span> |  
| `scripting` | <span data-ttu-id="8a9e9-163">拡張機能に API へのアクセス権を与 `chrome.scripting` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-163">Gives your extension access to the `chrome.scripting` API.</span></span> |  
| `search` | <span data-ttu-id="8a9e9-164">拡張機能に API へのアクセス権を与 `chrome.search` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-164">Gives your extension access to the `chrome.search` API.</span></span> |  
| `sessions` | <span data-ttu-id="8a9e9-165">拡張機能に API へのアクセス権を与 `chrome.sessions` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-165">Gives your extension access to the `chrome.sessions` API.</span></span> |  
| `signedInDevices` | <span data-ttu-id="8a9e9-166">拡張機能に API へのアクセス権を与 `chrome.signedInDevices` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-166">Gives your extension access to the `chrome.signedInDevices` API.</span></span> |  
| `storage` | <span data-ttu-id="8a9e9-167">拡張機能に API へのアクセス権を与 `chrome.storage` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-167">Gives your extension access to the `chrome.storage` API.</span></span> |  
| `system.cpu` | <span data-ttu-id="8a9e9-168">拡張機能に API へのアクセス権を与 `chrome.system.cpu` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-168">Gives your extension access to the `chrome.system.cpu` API.</span></span> |  
| `system.display` | <span data-ttu-id="8a9e9-169">拡張機能に API へのアクセス権を与 `chrome.system.display` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-169">Gives your extension access to the `chrome.system.display` API.</span></span> |  
| `system.memory` | <span data-ttu-id="8a9e9-170">拡張機能に API へのアクセス権を与 `chrome.system.memory` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-170">Gives your extension access to the `chrome.system.memory` API.</span></span> |  
| `system.storage` | <span data-ttu-id="8a9e9-171">拡張機能に API へのアクセス権を与 `chrome.system.storage` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-171">Gives your extension access to the `chrome.system.storage` API.</span></span> |  
| `tabCapture` | <span data-ttu-id="8a9e9-172">拡張機能に API へのアクセス権を与 `chrome.tabCapture` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-172">Gives your extension access to the `chrome.tabCapture` API.</span></span> |  
| `tabGroups` | <span data-ttu-id="8a9e9-173">拡張機能に API へのアクセス権を与 `chrome.tabGroups` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-173">Gives your extension access to the `chrome.tabGroups` API.</span></span> |  
| `tabs` | <span data-ttu-id="8a9e9-174">複数の API で使用される可能性があるオブジェクトの特権フィールドへの拡張機能アクセス権を `Tab` `chrome.tabs` 提供します `chrome.windows` 。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-174">Gives your extension access to privileged fields of the `Tab` objects that may be used by several APIs including `chrome.tabs` and `chrome.windows`.</span></span>  <span data-ttu-id="8a9e9-175">多くの場合、拡張機能は、これらの API を使用するためのアクセス許可を宣言 `tabs` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-175">In many circumstances, your extension does not need to declare the `tabs` permission to make use of these APIs.</span></span> |  
| `topSites` | <span data-ttu-id="8a9e9-176">拡張機能に API へのアクセス権を与 `chrome.topSites` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-176">Gives your extension access to the `chrome.topSites` API.</span></span> |  
| `tts` | <span data-ttu-id="8a9e9-177">拡張機能に API へのアクセス権を与 `chrome.tts` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-177">Gives your extension access to the `chrome.tts` API.</span></span> |  
| `ttsEngine` | <span data-ttu-id="8a9e9-178">拡張機能に API へのアクセス権を与 `chrome.ttsEngine` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-178">Gives your extension access to the `chrome.ttsEngine` API.</span></span> |  
| `unlimitedStorage` | <span data-ttu-id="8a9e9-179">データベースやローカル ストレージ ファイルなどのクライアント側データを格納するための制限なしクォータを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-179">Provides an unlimited quota for storing client-side data, such as databases and local storage files.</span></span>  <span data-ttu-id="8a9e9-180">このアクセス許可がない場合、拡張機能は 5 MB のローカル ストレージに制限されます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-180">Without this permission, the extension is limited to 5 MB of local storage.</span></span> |  
| `vpnProvider` | <span data-ttu-id="8a9e9-181">拡張機能に API へのアクセス権を与 `chrome.vpnProvider` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-181">Gives your extension access to the `chrome.vpnProvider` API.</span></span> |  
| `wallpaper` | <span data-ttu-id="8a9e9-182">拡張機能に API へのアクセス権を与 `chrome.wallpaper` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-182">Gives your extension access to the `chrome.wallpaper` API.</span></span> |  
| `webNavigation` | <span data-ttu-id="8a9e9-183">拡張機能に API へのアクセス権を与 `chrome.webNavigation` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-183">Gives your extension access to the `chrome.webNavigation` API.</span></span> |  
| `webRequest` | <span data-ttu-id="8a9e9-184">拡張機能に API へのアクセス権を与 `chrome.webRequest` えます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-184">Gives your extension access to the `chrome.webRequest` API.</span></span> |  
| `webRequestBlocking` | <span data-ttu-id="8a9e9-185">拡張機能が API を使用して `chrome.webRequest` 要求をブロックする場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-185">Required if the extension uses the `chrome.webRequest` API to block requests.</span></span> |  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="8a9e9-186">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-186">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8a9e9-187">元のページは次 [のページに表示されます](https://developer.chrome.com/docs/extensions/mv3/declare_permissions/)。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-187">The original page is found [here](https://developer.chrome.com/docs/extensions/mv3/declare_permissions/).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="8a9e9-189">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-189">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
