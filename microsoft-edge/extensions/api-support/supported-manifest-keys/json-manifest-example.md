---
ms.assetid: 89ac711a-78ff-4219-8dc3-2bad2099cf49
description: 利用可能なフィールド値については、Microsoft Edge JSON マニフェストの例を参照してください。
title: 拡張機能-JSON マニフェストの例
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: b4055524201821e3051f704b3bc9894de370c76d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569533"
---
# <span data-ttu-id="d47ea-104">JSON マニフェストファイルの例</span><span class="sxs-lookup"><span data-stu-id="d47ea-104">JSON manifest file example</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="d47ea-105">次のスニペットでは、Microsoft Edge の JSON マニフェストファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="d47ea-105">The following snippet provides an example of a Microsoft Edge JSON manifest file.</span></span>

```json
{
    "name" : "Sample extension manifest",
    "version" : "1.0.0.0",
    "author" : "Microsoft Corporation",
    "browser_action" : 
    {
        "default_icon" : 
        {
            "20" : "icon_20.png",
            "40" : "icon_40.png"
        },
        "default_title" : "Sample extension",
        "default_popup" : "popup.html"
    },
    "content_scripts" : [{
            "js" : ["content_script.js"],
            "matches" : ["*://*/*"]
        }
    ],

    "content_security_policy" : "script-src 'self'; object-src 'self'",
    "default_locale" : "en",
    "description" : "This is a sample extension that illustrates the JSON manifest schema",

    "options_page" : "options.html",
    "permissions" : 
    [
        "*://*/*", "notifications", "cookies", "tabs", "storage", "contextMenus", "background"
    ],
    "background" : 
    {
        "page" : "background.html",
        "persistent" : false
    },
    "icons" : {
        "128" : "icon_128.png",
        "16" : "icon_16.png",
        "48" : "icon_48.png"
    },
    "minimum_edge_version" : "33.14281.1000.0",

    "web_accessible_resources" : ["icon_48.png"]

} 
```



