---
description: 拡張機能パッケージ内のマニフェスト ファイルの形式について学習します。
title: マニフェスト ファイル形式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, Web 開発, html, css, javascript, developer, extensions, mv2, mv3, manifest
ms.openlocfilehash: ac2358f8927a762dcef98f9e10cc9f343d8a93f1
ms.sourcegitcommit: afeeeea9fccc3c4c096d7d44c401f4fe87ea2cd7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "11599433"
---
# <a name="manifest-file-format-for-extensions"></a><span data-ttu-id="ef22c-104">拡張子のマニフェスト ファイル形式</span><span class="sxs-lookup"><span data-stu-id="ef22c-104">Manifest file format for extensions</span></span>

<span data-ttu-id="ef22c-105">(Chromium) Microsoft Edgeのすべての拡張子には、 という名前の JSON 形式のマニフェスト ファイルがあります `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="ef22c-105">Every extension for Microsoft Edge (Chromium) has a JSON-formatted manifest file, named `manifest.json`.</span></span>  <span data-ttu-id="ef22c-106">マニフェスト ファイルは、拡張機能のブループリントです。</span><span class="sxs-lookup"><span data-stu-id="ef22c-106">The manifest file is the blueprint of your extension.</span></span>  <span data-ttu-id="ef22c-107">マニフェスト ファイルには、次のような情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef22c-107">The manifest file includes information such as:</span></span>

*  <span data-ttu-id="ef22c-108">拡張機能のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="ef22c-108">The version number of the extension.</span></span>
*  <span data-ttu-id="ef22c-109">拡張機能のタイトル。</span><span class="sxs-lookup"><span data-stu-id="ef22c-109">The title of the extension.</span></span>
*  <span data-ttu-id="ef22c-110">拡張機能を実行するために必要なアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="ef22c-110">The permissions that are needed for the extension to run.</span></span>

<span data-ttu-id="ef22c-111">拡張機能の `manifest.json` 形式は、マニフェスト V2 からマニフェスト V3 に移動しています。</span><span class="sxs-lookup"><span data-stu-id="ef22c-111">The format for `manifest.json` for extensions is moving from Manifest V2 to Manifest V3.</span></span>  <span data-ttu-id="ef22c-112">両方の形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ef22c-112">Both formats are shown here.</span></span>  <span data-ttu-id="ef22c-113">マニフェスト V2 拡張機能をマニフェスト V3 に移行するには、[準備] に移動して、マニフェスト v2 から v3 に拡張機能を [更新します][MigrateToMV3]。</span><span class="sxs-lookup"><span data-stu-id="ef22c-113">To migrate a Manifest V2 extension to Manifest V3, navigate to [Prepare to update your extensions from Manifest v2 to v3][MigrateToMV3].</span></span>


## <a name="format-of-manifestjson-for-extensions-using-manifest-v3"></a><span data-ttu-id="ef22c-114">Manifest V3 をmanifest\.js拡張機能に対してオンに設定する形式</span><span class="sxs-lookup"><span data-stu-id="ef22c-114">Format of manifest\.json for extensions using Manifest V3</span></span>

<span data-ttu-id="ef22c-115">次のコードは、マニフェスト V3 パッケージの拡張機能でサポートされている `manifest.json` フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="ef22c-115">The following code shows the fields that are supported in `manifest.json` for extensions, for a Manifest V3 package.</span></span>

<span data-ttu-id="ef22c-116">各フィールドに関する参照情報については、マニフェスト ファイル形式 [(V3)][ChromeDeveloperDocsExtensionsMv3Manifest] に移動し、フィールド上のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ef22c-116">For reference information about each field, navigate to [Manifest file format (V3)][ChromeDeveloperDocsExtensionsMv3Manifest] and then select the links on the fields.</span></span>

```json
{
  // Required
  "manifest_version": 3,
  "name": "My V3 Extension",
  "version": "versionString",

  // Recommended
  "action": {...},
  "default_locale": "en",
  "description": "A plain-text description",
  "icons": {...},

  // Optional
  "action": ...,
  "author": ...,
  "automation": ...,
  "background": {
    // If `background` is included, `service_ worker` is required
    "service_worker": ...
  },
  "chrome_settings_overrides": {...},
  "chrome_url_overrides": {...},
  "commands": {...},
  "content_capabilities": ...,
  "content_scripts": [{...}],
  "content_security_policy": "policyString",
  "converted_from_user_script": ...,
  "current_locale": ...,
  "declarative_net_request": ...,
  "devtools_page": "devtools.html",
  "differential_fingerprint": ...,
  "event_rules": [{...}],
  "externally_connectable": {
    "matches": ["*://*.contoso.com/*"]
  },
  "file_browser_handlers": [...],
  "file_system_provider_capabilities": {
    "configurable": true,
    "multiple_mounts": true,
    "source": "network"
  },
  "homepage_url": "http://path/to/homepage",
  "host_permissions": [...],
  "import": [{"id": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"}],
  "incognito": "spanning, split, or not_allowed",
  "input_components": ...,
  "key": "publicKey",
  "minimum_chrome_version": "versionString",
  "nacl_modules": [...],
  "natively_connectable": ...,
  "oauth2": ...,
  "offline_enabled": true,
  "omnibox": {
    "keyword": "aString"
  },
  "optional_permissions": ["tabs"],
  "options_page": "options.html",
  "options_ui": {
    "chrome_style": true,
    "page": "options.html"
  },
  "permissions": ["tabs"],
  "platforms": ...,
  "replacement_web_app": ...,
  "requirements": {...},
  "sandbox": [...],
  "short_name": "Short Name",
  "storage": {
    "managed_schema": "schema.json"
  },
  "system_indicator": ...,
  "tts_engine": {...},
  "update_url": "http://path/to/updateInfo.xml",
  "version_name": "aString",
  "web_accessible_resources": [...]
}
```

## <a name="format-of-manifestjson-for-extensions-using-manifest-v2"></a><span data-ttu-id="ef22c-117">Manifest V2 をmanifest\.js拡張機能に対してオンに設定する形式</span><span class="sxs-lookup"><span data-stu-id="ef22c-117">Format of manifest\.json for extensions using Manifest V2</span></span>

<span data-ttu-id="ef22c-118">次のコードは、マニフェスト V2 パッケージの拡張機能でサポートされている `manifest.json` フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="ef22c-118">The following code shows the fields that are supported in `manifest.json` for extensions, for a Manifest V2 package.</span></span>

<span data-ttu-id="ef22c-119">各フィールドに関する参照情報については、マニフェスト ファイル形式 [(V2)][ChromeDeveloperDocsExtensionsMv2Manifest] に移動し、フィールドのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ef22c-119">For reference information about each field, navigate to [Manifest file format (V2)][ChromeDeveloperDocsExtensionsMv2Manifest] and then select the links on the fields.</span></span>

```json
{
  // Required
  "manifest_version": 2,
  "name": "My V2 Extension",
  "version": "versionString",

  // Recommended
  "default_locale": "en",
  "description": "A plain-text description",
  "icons": {...},

  // Pick one or none
  "browser_action": {...},
  "page_action": {...},

  // Optional
  "action": ...,
  "author": ...,
  "automation": ...,
  "background": {
    // If `background` is included, `persistent` is recommended
    "persistent": false,
    // If `background` is included, `service_worker` is optional
    "service_worker": ...
  },
  "chrome_settings_overrides": {...},
  "chrome_url_overrides": {...},
  "commands": {...},
  "content_capabilities": ...,
  "content_scripts": [{...}],
  "content_security_policy": "policyString",
  "converted_from_user_script": ...,
  "current_locale": ...,
  "declarative_net_request": ...,
  "devtools_page": "devtools.html",
  "differential_fingerprint": ...,
  "event_rules": [{...}],
  "externally_connectable": {
    "matches": ["*://*.contoso.com/*"]
  },
  "file_browser_handlers": [...],
  "file_system_provider_capabilities": {
    "configurable": true,
    "multiple_mounts": true,
    "source": "network"
  },
  "homepage_url": "http://path/to/homepage",
  "host_permissions": ...,
  "import": [{"id": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"}],
  "incognito": "spanning, split, or not_allowed",
  "input_components": ...,
  "key": "publicKey",
  "minimum_chrome_version": "versionString",
  "nacl_modules": [...],
  "natively_connectable": ...,
  "oauth2": ...,
  "offline_enabled": true,
  "omnibox": {
    "keyword": "aString"
  },
  "optional_permissions": ["tabs"],
  "options_page": "options.html",
  "options_ui": {
    "chrome_style": true,
    "page": "options.html"
  },
  "permissions": ["tabs"],
  "platforms": ...,
  "replacement_web_app": ...,
  "requirements": {...},
  "sandbox": [...],
  "short_name": "Short Name",
  "storage": {
    "managed_schema": "schema.json"
  },
  "system_indicator": ...,
  "tts_engine": {...},
  "update_url": "http://path/to/updateInfo.xml",
  "version_name": ...,
  "web_accessible_resources": [...]
}
```

> [!NOTE]
> <span data-ttu-id="ef22c-120">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="ef22c-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ef22c-121">元のページは次 [のページに表示されます](https://developer.chrome.com/docs/extensions/mv3/manifest/)。</span><span class="sxs-lookup"><span data-stu-id="ef22c-121">The original page is found [here](https://developer.chrome.com/docs/extensions/mv3/manifest/).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ef22c-123">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ef22c-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies


<!-- links -->
[MigrateToMV3]: ../developer-guide/migrate-your-extension-from-manifest-v2-to-v3.md "マニフェスト v2 から v3 に拡張機能を更新する準備を|Microsoft Docs"

[ChromeDeveloperDocsExtensionsMv3Manifest]: https://developer.chrome.com/docs/extensions/mv3/manifest "マニフェスト ファイル形式 (V3) |Chrome 開発者"
[ChromeDeveloperDocsExtensionsMv2Manifest]: https://developer.chrome.com/docs/extensions/mv2/manifest "マニフェスト ファイル形式 (V2) |Chrome 開発者"
