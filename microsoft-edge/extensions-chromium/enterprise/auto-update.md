---
description: 拡張機能の自動更新について詳しくは、Microsoft Edge
title: 拡張機能を自動的に更新Microsoft Edge
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: d9901f9c39dabfab111eb7e0c34a3e267a317110
ms.sourcegitcommit: 59d8043e37b89da814f63bc85daf84e0e7167eab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2021
ms.locfileid: "11586389"
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
# <a name="automatically-update-extensions-in-microsoft-edge"></a><span data-ttu-id="f3d88-104">拡張機能を自動的に更新Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f3d88-104">Automatically update extensions in Microsoft Edge</span></span>  

<span data-ttu-id="f3d88-105">拡張機能を自動的に更新するように設定すると、拡張機能は自動的に更新するように設定されている場合Microsoft Edgeと次の利点を共有します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-105">When you set your extension to automatically update, your extension shares the following benefits with Microsoft Edge when set to automatically update.</span></span>  

*   <span data-ttu-id="f3d88-106">バグとセキュリティの修正プログラムを組み込む。</span><span class="sxs-lookup"><span data-stu-id="f3d88-106">Incorporate bug and security fixes.</span></span>  
*   <span data-ttu-id="f3d88-107">新しい機能やパフォーマンスの強化を追加します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-107">Add new features or performance enhancements.</span></span>  
*   <span data-ttu-id="f3d88-108">ユーザー インターフェイスを改善します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-108">Improve the user interface.</span></span>  

<span data-ttu-id="f3d88-109">以前は、ストアベース以外の拡張機能がサポートされました。</span><span class="sxs-lookup"><span data-stu-id="f3d88-109">Previously, non-store based extensions were supported.</span></span>  <span data-ttu-id="f3d88-110">また、ネイティブ バイナリと拡張機能を同時に更新しました。</span><span class="sxs-lookup"><span data-stu-id="f3d88-110">Also, you updated the native binaries and the extension at the same time.</span></span>  

<span data-ttu-id="f3d88-111">これで、Microsoft Edgeアドオン ストアが拡張機能をホストし、拡張機能を更新するには、拡張機能と同じメカニズムをMicrosoft Edge。</span><span class="sxs-lookup"><span data-stu-id="f3d88-111">Now, the Microsoft Edge Add-ons store hosts your extensions and you update your extension using the same mechanism as Microsoft Edge.</span></span>  <span data-ttu-id="f3d88-112">更新メカニズムは制御しない。</span><span class="sxs-lookup"><span data-stu-id="f3d88-112">You don't control the update mechanism.</span></span>  <span data-ttu-id="f3d88-113">ネイティブ バイナリに依存する拡張機能を更新する場合は注意してください。</span><span class="sxs-lookup"><span data-stu-id="f3d88-113">Be careful when you update extensions that have a dependency on native binaries.</span></span>  

> [!NOTE]
> <span data-ttu-id="f3d88-114">この記事は、パートナー センター ダッシュボードを使用して発行する拡張機能 [には適用][MicrosoftPartnerDashboardMicrosoftedgePublicLoginRefDd] されません。</span><span class="sxs-lookup"><span data-stu-id="f3d88-114">This article does not apply to extensions that you publish using the [Partner Center][MicrosoftPartnerDashboardMicrosoftedgePublicLoginRefDd] dashboard.</span></span>  <span data-ttu-id="f3d88-115">ダッシュボードを使用して、更新されたバージョンをユーザーとアドオン ストアMicrosoft Edgeリリースできます。</span><span class="sxs-lookup"><span data-stu-id="f3d88-115">You may use the dashboard to release updated versions to your users and to the Microsoft Edge Add-ons store.</span></span>  <span data-ttu-id="f3d88-116">詳細については、「拡張機能を更新 [または削除する」に移動します][ExtensionsPublishUpdateExtension]。</span><span class="sxs-lookup"><span data-stu-id="f3d88-116">For more information, navigate to [Update or remove your extension][ExtensionsPublishUpdateExtension].</span></span>  

## <a name="overview"></a><span data-ttu-id="f3d88-117">概要</span><span class="sxs-lookup"><span data-stu-id="f3d88-117">Overview</span></span>  

<span data-ttu-id="f3d88-118">数時間ごとに、インストールMicrosoft Edgeアプリに更新 URL が含されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3d88-118">Every few hours, Microsoft Edge checks whether each installed extension or app has an update URL.</span></span>  <span data-ttu-id="f3d88-119">拡張機能の更新 URL を指定するには、マニフェスト `update_url` のフィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-119">To specify an update URL for your extension, use the `update_url` field in the manifest.</span></span>  <span data-ttu-id="f3d88-120">マニフェスト `update_url` 内のフィールドは、更新チェックを完了する場所をポイントします。</span><span class="sxs-lookup"><span data-stu-id="f3d88-120">The `update_url` field in the manifest points to a location to complete an update check.</span></span>  <span data-ttu-id="f3d88-121">それぞれについて `update_url` 、更新されたマニフェスト XML ファイルの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-121">For each `update_url`, it sends requests for updated manifest XML files.</span></span>  <span data-ttu-id="f3d88-122">更新マニフェスト XML ファイルにインストールされているバージョンより新しいバージョンが一覧表示されている場合は、Microsoft Edgeバージョンをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f3d88-122">If the update manifest XML file lists a newer version than that installed, Microsoft Edge downloads and installs the newer version.</span></span>  <span data-ttu-id="f3d88-123">手動更新でも同じプロセスが機能します。新しいファイルには、現在インストールされているバージョンと同じプライベート キー `.crx` で署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3d88-123">The same process works for manual updates, where the new `.crx` file must be signed with the same private key as the currently installed version.</span></span>  

> [!NOTE]
> <span data-ttu-id="f3d88-124">ユーザーのプライバシーを維持するために、Microsoft Edge はマニフェストの自動更新要求を含むヘッダーを送信しません。また、これらの要求に対する応答のヘッダーは `Cookie` `Set-Cookie` 無視されます。</span><span class="sxs-lookup"><span data-stu-id="f3d88-124">In order to maintain user privacy, Microsoft Edge does not send any `Cookie` headers with auto-update manifest requests, and ignores any `Set-Cookie` headers in the responses to those requests.</span></span>  

## <a name="update-url"></a><span data-ttu-id="f3d88-125">URL の更新</span><span class="sxs-lookup"><span data-stu-id="f3d88-125">Update URL</span></span>  

<span data-ttu-id="f3d88-126">独自の拡張機能またはアプリをホストする場合は、フィールドを `update_url` ファイルに追加する必要 `manifest.json` があります。</span><span class="sxs-lookup"><span data-stu-id="f3d88-126">If you host your own extension or app, you must add the `update_url` field to your `manifest.json` file.</span></span>  <span data-ttu-id="f3d88-127">の例については、次のコード スニペットを確認 `update_url` してください。</span><span class="sxs-lookup"><span data-stu-id="f3d88-127">Review the following code snippet for an example of the `update_url`.</span></span>  

```json
{
  "name": "My extension",
  ... 
  "update_url": "http://contoso.com/mytestextension/updates.xml",
  ... 
}
```  

## <a name="updated-manifest"></a><span data-ttu-id="f3d88-128">更新されたマニフェスト</span><span class="sxs-lookup"><span data-stu-id="f3d88-128">Updated manifest</span></span>  

<span data-ttu-id="f3d88-129">サーバーによって返される更新されたマニフェストは、XML ドキュメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3d88-129">The updated manifest returned by the server should be an XML document.</span></span>  <span data-ttu-id="f3d88-130">更新されたマニフェスト XML ファイルの例については、次のコード スニペットを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3d88-130">Review the following code snippet for an example of the updated manifest XML file.</span></span>  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' />
  </app>
</gupdate>
```  

<span data-ttu-id="f3d88-131">次の表では、更新されたマニフェスト XML ファイルの属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-131">The following table describes attributes of the updated manifest XML file.</span></span>  

| <span data-ttu-id="f3d88-132">属性</span><span class="sxs-lookup"><span data-stu-id="f3d88-132">Attribute</span></span> | <span data-ttu-id="f3d88-133">詳細</span><span class="sxs-lookup"><span data-stu-id="f3d88-133">Details</span></span> | 
|:--- |:--- |  
| `appid` | <span data-ttu-id="f3d88-134">拡張 ID は、公開キーのハッシュに基づいて生成されます。</span><span class="sxs-lookup"><span data-stu-id="f3d88-134">The extension ID is generated based on a hash of the public key.</span></span>  <span data-ttu-id="f3d88-135">拡張機能の ID を見つけるには、拡張機能を開Microsoft Edgeに移動します `edge://extensions` 。</span><span class="sxs-lookup"><span data-stu-id="f3d88-135">To find the ID of an extension, open Microsoft Edge and navigate to `edge://extensions`.</span></span> |  
| `codebase` | <span data-ttu-id="f3d88-136">ファイルの `.crx` URL。</span><span class="sxs-lookup"><span data-stu-id="f3d88-136">A URL to the `.crx` file.</span></span> |  
| `version` | <span data-ttu-id="f3d88-137">この属性値は、Microsoft Edgeファイルをダウンロードするかどうかを決定するために `.crx` 使用されます `codebase` 。</span><span class="sxs-lookup"><span data-stu-id="f3d88-137">This attribute value is used by Microsoft Edge to determine whether it should download the `.crx` file specified by `codebase`.</span></span>  <span data-ttu-id="f3d88-138">ファイルのファイルの値 `version` と `manifest.json` 一致する必要 `.crx` があります。</span><span class="sxs-lookup"><span data-stu-id="f3d88-138">It should match the value of `version` in the `manifest.json` file of the `.crx` file.</span></span> |  

<span data-ttu-id="f3d88-139">更新マニフェスト XML ファイルには、複数の要素を含めて複数の拡張子に関する情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3d88-139">The update manifest XML file may contain information about multiple extensions by including multiple elements.</span></span>  

## <a name="testing"></a><span data-ttu-id="f3d88-140">テスト</span><span class="sxs-lookup"><span data-stu-id="f3d88-140">Testing</span></span>  

<span data-ttu-id="f3d88-141">既定の更新チェックの頻度は数時間です。</span><span class="sxs-lookup"><span data-stu-id="f3d88-141">The default update check frequency is several hours.</span></span>  <span data-ttu-id="f3d88-142">強制的に更新するには、[拡張機能を今すぐ更新する] ボタン `edge://extensions` **に移動して選択** します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-142">To force an update, navigate to `edge://extensions` and choose the **Update extensions now** button.</span></span>  

## <a name="advanced-usage-request-parameters"></a><span data-ttu-id="f3d88-143">高度な使用法: 要求パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3d88-143">Advanced usage: request parameters</span></span>  

<span data-ttu-id="f3d88-144">基本的なメカニズムは簡単です。</span><span class="sxs-lookup"><span data-stu-id="f3d88-144">The basic mechanism is simple.</span></span>  <span data-ttu-id="f3d88-145">拡張機能を自動的に更新するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-145">To automatically update your extension, complete the following actions.</span></span>  

1.  <span data-ttu-id="f3d88-146">アップロードなどの静的 XML ファイルを Web サーバー上に保存します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-146">Upload your static XML file on your web server, such as Apache.</span></span>  
1.  <span data-ttu-id="f3d88-147">拡張機能の新しいバージョンをリリースする場合は、XML ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-147">Update the XML file as you release new versions of your extensions.</span></span>  
    
<span data-ttu-id="f3d88-148">更新マニフェスト要求に追加された一部のパラメーターが拡張機能とを示しているという事実を利用 `ID` します `version` 。</span><span class="sxs-lookup"><span data-stu-id="f3d88-148">Take advantage of the fact that some parameters added to the update manifest request indicate the extension `ID` and `version`.</span></span>  <span data-ttu-id="f3d88-149">静的 XML ファイルの `update URL` 代わりに、すべての拡張機能で同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3d88-149">You may use the same `update URL` for all your extensions instead of a static XML file.</span></span>  <span data-ttu-id="f3d88-150">すべての拡張機能で同じ機能を使用するには、動的サーバー側コードを実行する URL をポイントしてパラメーター `update URL` をテストします。</span><span class="sxs-lookup"><span data-stu-id="f3d88-150">To use the same `update URL` for all your extensions, point to a URL that runs dynamic server-side code to test the parameters.</span></span>  

<span data-ttu-id="f3d88-151">次の例は、更新 URL の要求パラメーターの形式を示しています。</span><span class="sxs-lookup"><span data-stu-id="f3d88-151">The following example demonstrates the format of the request parameters of update URL.</span></span>  

```url
?x={extension_data}
```  

<span data-ttu-id="f3d88-152">この例では `{extension_data}` 、次の形式を使用する URL エンコード文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-152">In this example, `{extension_data}` is a URL-encoded string that uses the following format.</span></span>  

```url
id={id}&v={version}
```  

<span data-ttu-id="f3d88-153">たとえば、次の 2 つの拡張機能は両方とも同じ更新 URL を指しています `http://contoso.com/extension_updates.php` 。</span><span class="sxs-lookup"><span data-stu-id="f3d88-153">For example, the following two extensions both point to the same update URL `http://contoso.com/extension_updates.php`.</span></span>  

*   <span data-ttu-id="f3d88-154">拡張機能 1</span><span class="sxs-lookup"><span data-stu-id="f3d88-154">Extension 1</span></span>  
    *   <span data-ttu-id="f3d88-155">ID:</span><span class="sxs-lookup"><span data-stu-id="f3d88-155">ID:</span></span> `aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa`  
    *   <span data-ttu-id="f3d88-156">更新 URL:</span><span class="sxs-lookup"><span data-stu-id="f3d88-156">update URL:</span></span> `http://contoso.com/extension_updates.php`
    *   <span data-ttu-id="f3d88-157">バージョン:</span><span class="sxs-lookup"><span data-stu-id="f3d88-157">Version:</span></span> `1.1`  
*   <span data-ttu-id="f3d88-158">拡張機能 2</span><span class="sxs-lookup"><span data-stu-id="f3d88-158">Extension 2</span></span>  
    *   <span data-ttu-id="f3d88-159">ID:</span><span class="sxs-lookup"><span data-stu-id="f3d88-159">ID:</span></span> `bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb`  
    *   <span data-ttu-id="f3d88-160">更新 URL:</span><span class="sxs-lookup"><span data-stu-id="f3d88-160">update URL:</span></span> `http://contoso.com/extension_updates.php`
    *   <span data-ttu-id="f3d88-161">バージョン:</span><span class="sxs-lookup"><span data-stu-id="f3d88-161">Version:</span></span> `0.4`  


<span data-ttu-id="f3d88-162">各拡張機能を更新する要求を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-162">The following are the requests to update each extension.</span></span>  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1
```  

```https
http://contoso.com/extension_updates.php?x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

<span data-ttu-id="f3d88-163">また、一意の更新 URL ごとに 1 つの要求に複数の拡張機能を一覧表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3d88-163">You may also list multiple extensions in a single request for each unique update URL.</span></span>  <span data-ttu-id="f3d88-164">次の使用例は、前の要求を 1 つの要求にマージします。</span><span class="sxs-lookup"><span data-stu-id="f3d88-164">The following example merges the previous requests into a single request.</span></span>  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1&x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

<span data-ttu-id="f3d88-165">1 つの要求を送信し、同じ更新 URL を使用するインストール済み拡張機能の数が長すぎる場合、更新プログラムのチェックは、より多くの要求を `GET` 発行します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-165">If you send a single request and the number of installed extensions that use the same update URL is too long, the update check issues more `GET` requests.</span></span>  <span data-ttu-id="f3d88-166">要求 `GET` URL が約 2000 文字の場合は長すぎます。</span><span class="sxs-lookup"><span data-stu-id="f3d88-166">A `GET` request URL is too long if it's approximately 2000 characters.</span></span>  

> [!NOTE]
> <span data-ttu-id="f3d88-167">将来、1 つの要求で `POST` 複数の要求が `GET` 置き換わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3d88-167">In the future, a single `POST` request may replace multiple `GET` requests.</span></span>  <span data-ttu-id="f3d88-168">要求 `POST` には、本文に要求パラメーターが含 `POST` まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3d88-168">The `POST` request may contain the request parameters in the `POST` body.</span></span>  

## <a name="advanced-usage-minimum-browser-version"></a><span data-ttu-id="f3d88-169">高度な使用法: 最小ブラウザー バージョン</span><span class="sxs-lookup"><span data-stu-id="f3d88-169">Advanced usage: minimum browser version</span></span>  

<span data-ttu-id="f3d88-170">Microsoft Edge 拡張機能システムの新しい API リリースとして、新しい拡張機能または新しいバージョンでのみ動作する拡張機能またはアプリの更新Microsoft Edgeがあります。</span><span class="sxs-lookup"><span data-stu-id="f3d88-170">As new APIs release for the Microsoft Edge extensions system, you may release an updated version of your extension or app that only works with newer Microsoft Edge versions.</span></span>  <span data-ttu-id="f3d88-171">ユーザー Microsoft Edge自動的に更新される場合、ほとんどのユーザーが新しいリリースに更新されるまで数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3d88-171">When Microsoft Edge is automatically updated, it may take a few days before most of your users update to that new release.</span></span>  <span data-ttu-id="f3d88-172">特定の更新プログラムが特定のバージョンMicrosoft Edgeバージョンよりも新しいバージョンにのみ適用するようにするには、更新マニフェストに属性 `prodversionmin` を追加します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-172">To ensure that a specific update applies only to Microsoft Edge versions that are current or newer than a specific version, add the `prodversionmin` attribute in your update manifest.</span></span>  <span data-ttu-id="f3d88-173">次のコード スニペットでは、属性の値は、ユーザーが新しいアプリを実行している場合にのみ、アプリが自動的にバージョン `prodversionmin` `3.0.193.0` `2.0` Microsoft Edge `3.0.193.0` 指定します。</span><span class="sxs-lookup"><span data-stu-id="f3d88-173">In the following code snippet, the `prodversionmin` attribute value of `3.0.193.0` specifies that your app automatically updated to version `2.0` only when the user is running Microsoft Edge `3.0.193.0` or newer.</span></span>  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' prodversionmin='3.0.193.0' />
  </app>
</gupdate>
```  

<!-- links -->  

[ExtensionsPublishUpdateExtension]: ../publish/update-extension.md "拡張機能の更新または削除|Microsoft Docs"  

[MicrosoftPartnerDashboardMicrosoftedgePublicLoginRefDd]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナー センター"  

> [!NOTE]
> <span data-ttu-id="f3d88-176">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="f3d88-176">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f3d88-177">元のページは次 [のページに表示されます](https://developer.chrome.com/docs/apps/autoupdate)。</span><span class="sxs-lookup"><span data-stu-id="f3d88-177">The original page is found [here](https://developer.chrome.com/docs/apps/autoupdate).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f3d88-179">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f3d88-179">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
