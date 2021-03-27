---
description: Microsoft Edge の拡張機能に対する自動更新について説明します。
title: Microsoft Edge の拡張機能を自動更新する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 0f3f140cd3a2a079cd09f4d61e46a420342e15e0
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461543"
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
# <a name="auto-update-extensions-in-microsoft-edge"></a><span data-ttu-id="5f6c0-104">Microsoft Edge の拡張機能を自動更新する</span><span class="sxs-lookup"><span data-stu-id="5f6c0-104">Auto-update extensions in Microsoft Edge</span></span>  

<span data-ttu-id="5f6c0-105">拡張機能を自動的に更新すると、Microsoft Edge を自動的に更新するのと同じ利点がいくつか共有されます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-105">Automatically updating extensions share some of the same benefits as automatically updating Microsoft Edge:</span></span>   

*   <span data-ttu-id="5f6c0-106">バグとセキュリティの修正プログラムを組み込む。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-106">Incorporate bug and security fixes.</span></span>  
*   <span data-ttu-id="5f6c0-107">新しい機能やパフォーマンスの強化を追加します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-107">Add new features or performance enhancements.</span></span>  
*   <span data-ttu-id="5f6c0-108">ユーザー インターフェイスを改善します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-108">Improve the user interface.</span></span>  

<span data-ttu-id="5f6c0-109">以前は、ストアベース以外の拡張機能がサポートされている場合、ネイティブ バイナリと拡張機能を同時に更新する可能性がありました。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-109">Previously when non-store based extensions were supported, it was possible to update the native binaries and the extension at the same time.</span></span>  <span data-ttu-id="5f6c0-110">これで、これらの拡張機能は Microsoft Edge アドオン ストアでホストされ、Microsoft Edge が使用するのと同じメカニズムを使用して更新が行われた。これは制御できない。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-110">Now, those extensions are hosted in the Microsoft Edge Add-ons store and updates are made using the same mechanism that Microsoft Edge uses, which you can't control.</span></span>  <span data-ttu-id="5f6c0-111">ネイティブ バイナリに依存する拡張機能を更新する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-111">You should be careful when updating extensions that have a dependency on native binaries.</span></span>  

> [!NOTE]
> <span data-ttu-id="5f6c0-112">このトピックは、パートナー センター ダッシュボードを使用して発行された拡張機能 [には適用][MicrosoftPartnerCenter] されません。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-112">This topic does not apply to extensions published using the [Partner Center][MicrosoftPartnerCenter] dashboard.</span></span>  <span data-ttu-id="5f6c0-113">ダッシュボードを使用して、更新されたバージョンをユーザーと Microsoft Edge アドオン ストアにリリースできます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-113">You may use the dashboard to release updated versions to your users and to the Microsoft Edge Add-ons store.</span></span>

## <a name="overview"></a><span data-ttu-id="5f6c0-114">概要</span><span class="sxs-lookup"><span data-stu-id="5f6c0-114">Overview</span></span>  

<span data-ttu-id="5f6c0-115">数時間ごとに、インストールされている各拡張機能またはアプリに更新 URL が含されているかどうかを Microsoft Edge がチェックします。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-115">Every few hours, Microsoft Edge checks whether each installed extension or app has an update URL.</span></span>  <span data-ttu-id="5f6c0-116">拡張機能では、マニフェストのフィールドを使用して更新 URL を指定できます。これは、更新チェックを実行する場所 `update_url` を示します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-116">Extensions can specify an update URL using the `update_url` field in the manifest, which points to a location to perform an update check.</span></span>  <span data-ttu-id="5f6c0-117">それぞれについて `update_url` 、更新されたマニフェスト XML ファイルの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-117">For each `update_url`, it sends requests for updated manifest XML files.</span></span>  <span data-ttu-id="5f6c0-118">更新マニフェスト XML ファイルにインストールされているバージョンよりも新しいバージョンが一覧表示されている場合、Microsoft Edge は新しいバージョンをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-118">If the update manifest XML file lists a newer version than that installed, Microsoft Edge downloads and installs the newer version.</span></span>  <span data-ttu-id="5f6c0-119">手動更新でも同じプロセスが機能します。新しいファイルには、現在インストールされているバージョンと同じプライベート キー `.crx` で署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-119">The same process works for manual updates, where the new `.crx` file must be signed with the same private key as the currently installed version.</span></span>  

> [!NOTE]
> <span data-ttu-id="5f6c0-120">ユーザーのプライバシーを維持するために、Microsoft Edge はマニフェスト要求を自動更新するヘッダーを送信しません。また、それらの要求に対する応答のヘッダー `Cookie` `Set-Cookie` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-120">In order to maintain user privacy, Microsoft Edge does not send any `Cookie` headers with auto-update manifest requests, and ignores any `Set-Cookie` headers in the responses to those requests.</span></span>  

## <a name="update-url"></a><span data-ttu-id="5f6c0-121">URL の更新</span><span class="sxs-lookup"><span data-stu-id="5f6c0-121">Update URL</span></span>  

<span data-ttu-id="5f6c0-122">独自の拡張機能またはアプリをホストする場合は、フィールドを `update_url` ファイルに追加する必要 `manifest.json` があります。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-122">If you host your own extension or app, you must add the `update_url` field to your `manifest.json` file.</span></span>  <span data-ttu-id="5f6c0-123">の例については、次のコード スニペットを確認 `update_url` してください。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-123">Review the following code snippet for an example of the `update_url`.</span></span>  

```json
{
  "name": "My extension",
  ... 
  "update_url": "http://contoso.com/mytestextension/updates.xml",
  ... 
}
```  

## <a name="updated-manifest"></a><span data-ttu-id="5f6c0-124">更新されたマニフェスト</span><span class="sxs-lookup"><span data-stu-id="5f6c0-124">Updated manifest</span></span>  

<span data-ttu-id="5f6c0-125">サーバーによって返される更新されたマニフェストは、XML ドキュメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-125">The updated manifest returned by the server should be an XML document.</span></span>  <span data-ttu-id="5f6c0-126">更新されたマニフェスト XML ファイルの例については、次のコード スニペットを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-126">Review the following code snippet for an example of the updated manifest XML file.</span></span>  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.microsoft.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' />
  </app>
</gupdate>
```  

<span data-ttu-id="5f6c0-127">次の表では、更新されたマニフェスト XML ファイルの属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-127">The following table describes attributes of the updated manifest XML file.</span></span>  

| <span data-ttu-id="5f6c0-128">属性</span><span class="sxs-lookup"><span data-stu-id="5f6c0-128">Attribute</span></span> | <span data-ttu-id="5f6c0-129">詳細</span><span class="sxs-lookup"><span data-stu-id="5f6c0-129">Details</span></span> | 
|:--- |:--- |  
| `appid` | <span data-ttu-id="5f6c0-130">拡張 ID は、公開キーのハッシュに基づいて生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-130">The extension ID is generated based on a hash of the public key.</span></span>  <span data-ttu-id="5f6c0-131">拡張機能の ID を見つけるには、Microsoft Edge を開き、 に移動します `edge://extensions` 。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-131">To find the ID of an extension, open Microsoft Edge and navigate to `edge://extensions`.</span></span> |  
| `codebase` | <span data-ttu-id="5f6c0-132">ファイルの `.crx` URL。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-132">A URL to the `.crx` file.</span></span> |  
| `version` | <span data-ttu-id="5f6c0-133">この属性値は、Microsoft Edge によって指定されたファイルをダウンロードするかどうかを `.crx` 決定するために使用されます `codebase` 。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-133">This attribute value is used by Microsoft Edge to determine whether it should download the `.crx` file specified by `codebase`.</span></span>  <span data-ttu-id="5f6c0-134">ファイルのファイルの値 `version` と `manifest.json` 一致する必要 `.crx` があります。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-134">It should match the value of `version` in the `manifest.json` file of the `.crx` file.</span></span> |  

<span data-ttu-id="5f6c0-135">更新マニフェスト XML ファイルには、複数の要素を含めて複数の拡張子に関する情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-135">The update manifest XML file may contain information about multiple extensions by including multiple elements.</span></span>  

## <a name="testing"></a><span data-ttu-id="5f6c0-136">テスト</span><span class="sxs-lookup"><span data-stu-id="5f6c0-136">Testing</span></span>  

<span data-ttu-id="5f6c0-137">既定の更新チェックの頻度は数時間です。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-137">The default update check frequency is several hours.</span></span>  <span data-ttu-id="5f6c0-138">強制的に更新するには、[拡張機能を今すぐ更新する] ボタン `edge://extensions` **に移動して選択** します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-138">To force an update, navigate to `edge://extensions` and choose the **Update extensions now** button.</span></span>  

## <a name="advanced-usage-request-parameters"></a><span data-ttu-id="5f6c0-139">高度な使用法: 要求パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f6c0-139">Advanced usage: request parameters</span></span>  

<span data-ttu-id="5f6c0-140">基本的な自動更新メカニズムは、静的 XML ファイルを Apache などの任意の Web サーバーにドロップし、拡張機能の新しいバージョンをリリースする場合と同じ方法で XML ファイルを更新するのと同じほど簡単です。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-140">The basic auto-update mechanism is as easy as dropping a static XML file onto any web server such as Apache, and updating the XML file as you release new versions of your extensions.</span></span>  

<span data-ttu-id="5f6c0-141">拡張 ID とバージョンを示す更新マニフェスト要求にパラメーターが追加されるという事実を利用できます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-141">You may take advantage of the fact that parameters are added to the update manifest request that indicate the extension ID and version.</span></span> <span data-ttu-id="5f6c0-142">静的 XML ファイルの代わりに、すべての拡張機能に同じ更新 URL を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-142">You can use the same update URL for all your extensions instead of a static XML file.</span></span>  <span data-ttu-id="5f6c0-143">すべての拡張機能に同じ更新 URL を使用するには、動的サーバー側コードを実行する URL をポイントして、これらのパラメーターをテストします。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-143">To use the same update URL for all your extensions, point to a URL that runs dynamic server-side code to test these parameters.</span></span>  

<span data-ttu-id="5f6c0-144">次の例は、更新 URL の要求パラメーターの形式を示しています `?x={extension_data}` 。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-144">The following example demonstrates the format of the request parameters of update URL: `?x={extension_data}`.</span></span>

<span data-ttu-id="5f6c0-145">この例では `{extension_data}` 、次の形式を使用する URL エンコードされた文字列です `id={id}&v={version}` 。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-145">In this example, `{extension_data}` is a URL-encoded string that uses the following format: `id={id}&v={version}`.</span></span>

<span data-ttu-id="5f6c0-146">たとえば、次の 2 つの拡張機能は両方とも同じ更新 URL を指しています `http://contoso.com/extension_updates.php` 。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-146">For example, the following two extensions both point to the same update URL `http://contoso.com/extension_updates.php`.</span></span>  

*  <span data-ttu-id="5f6c0-147">内線番号 1 - ID: "aaaaaaaaaa" バージョン: "1.1"</span><span class="sxs-lookup"><span data-stu-id="5f6c0-147">Extension 1 - ID: "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa" Version: "1.1"</span></span>
*  <span data-ttu-id="5f6c0-148">拡張 2 - ID: "bbbbbbbb" バージョン: "0.4"</span><span class="sxs-lookup"><span data-stu-id="5f6c0-148">Extension 2 - ID: "bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb" Version: "0.4"</span></span>


<span data-ttu-id="5f6c0-149">各拡張機能を更新する要求を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-149">The following are the requests to update each extension.</span></span>  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1
```  

```https
http://contoso.com/extension_updates.php?x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

<span data-ttu-id="5f6c0-150">また、一意の更新 URL ごとに 1 つの要求に複数の拡張機能を一覧表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-150">You may also list multiple extensions in a single request for each unique update URL.</span></span>  <span data-ttu-id="5f6c0-151">次の使用例は、前の要求を 1 つの要求にマージします。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-151">The following example merges the previous requests into a single request.</span></span>  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1&x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

<span data-ttu-id="5f6c0-152">1 つの要求を送信し、同じ更新 URL を使用するインストール済み拡張機能の数が長すぎる場合、更新プログラムのチェックは、より多くの要求を `GET` 発行します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-152">If you send a single request and the number of installed extensions that use the same update URL is too long, the update check issues more `GET` requests.</span></span>  <span data-ttu-id="5f6c0-153">要求 `GET` URL が約 2000 文字の場合は長すぎます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-153">A `GET` request URL is too long if it is approximately 2000 characters.</span></span>  

> [!NOTE]
> <span data-ttu-id="5f6c0-154">将来、1 つの要求で `POST` 複数の要求が `GET` 置き換わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-154">In the future, a single `POST` request may replace multiple `GET` requests.</span></span>  <span data-ttu-id="5f6c0-155">要求 `POST` には、本文に要求パラメーターが含 `POST` まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-155">The `POST` request may contain the request parameters in the `POST` body.</span></span>  

## <a name="advanced-usage-minimum-browser-version"></a><span data-ttu-id="5f6c0-156">高度な使用法: 最小ブラウザー バージョン</span><span class="sxs-lookup"><span data-stu-id="5f6c0-156">Advanced usage: minimum browser version</span></span>  

<span data-ttu-id="5f6c0-157">Microsoft Edge 拡張機能システムの新しい API リリースとして、新しい Microsoft Edge バージョンでのみ動作する拡張機能またはアプリの更新バージョンをリリースできます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-157">As new APIs release for the Microsoft Edge extensions system, you may release an updated version of your extension or app that only works with newer Microsoft Edge versions.</span></span>  <span data-ttu-id="5f6c0-158">Microsoft Edge が自動更新される場合、ほとんどのユーザーが新しいリリースに更新されるまで数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-158">When Microsoft Edge is auto-updated, it may take a few days before most of your users update to that new release.</span></span>  <span data-ttu-id="5f6c0-159">特定の更新プログラムが特定のバージョンより最新または新しい Microsoft Edge バージョンにのみ適用される場合は、更新マニフェストに属性 `prodversionmin` を追加します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-159">To ensure that a specific update applies only to Microsoft Edge versions that are current or newer than a specific version, add the `prodversionmin` attribute in your update manifest.</span></span>  <span data-ttu-id="5f6c0-160">次のコード スニペットでは、属性の値は、ユーザーが Microsoft Edge 以降を実行している場合にのみ、アプリがバージョンに `prodversionmin` `3.0.193.0` 自動更新するように `2.0` `3.0.193.0` 指定します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-160">In the following code snippet, the `prodversionmin` attribute value of `3.0.193.0` specifies that your app auto-updates to version `2.0` only when the user is running Microsoft Edge `3.0.193.0` or newer.</span></span>  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' prodversionmin='3.0.193.0' />
  </app>
</gupdate>
```  

<!-- links -->  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナー センター"  

> [!NOTE]
> <span data-ttu-id="5f6c0-162">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-162">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5f6c0-163">元のページは次 [のページに表示されます](https://developer.chrome.com/docs/apps/autoupdate/)。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-163">The original page is found [here](https://developer.chrome.com/docs/apps/autoupdate/).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5f6c0-165">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-165">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
