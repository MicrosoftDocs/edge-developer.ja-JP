---
ms.assetid: 1319a070-c6e3-4592-9f4b-40ce1575851f
description: Microsoft Edge Extension Toolkit を使用して Chrome 拡張機能を Microsoft Edge に移植する方法について説明します。
title: Chrome 拡張機能の移植
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f226d79dbc9efdc43eb68bfb353fa12748198371
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234916"
---
# <span data-ttu-id="83d96-104">Chrome から Microsoft Edge への拡張機能の移植</span><span class="sxs-lookup"><span data-stu-id="83d96-104">Porting an extension from Chrome to Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="83d96-105">Chrome から Microsoft Edge への拡張機能の移植は [、Microsoft Edge](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)拡張機能のサポートを利用してToolkit。</span><span class="sxs-lookup"><span data-stu-id="83d96-105">Porting an extension from Chrome to Microsoft Edge is made easy with the help of the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span> <span data-ttu-id="83d96-106">この開発者ツールは、API をブリッジし、ファイル内のエラーを表示することで、展開されていない Chrome 拡張機能をアンパックされた Microsoft Edge 拡張機能に変換 `manifest.json` します。</span><span class="sxs-lookup"><span data-stu-id="83d96-106">This developer tool converts an unpacked Chrome extension to an unpacked Microsoft Edge extension by bridging APIs and surfacing any errors in your `manifest.json` file.</span></span>


### <span data-ttu-id="83d96-107">API ブリッジ</span><span class="sxs-lookup"><span data-stu-id="83d96-107">API bridges</span></span>
<span data-ttu-id="83d96-108">Chrome API をサポートされている Microsoft Edge API にシームレスに移植するために、拡張機能のフォルダーに 2 つのスクリプトが追加されます。</span><span class="sxs-lookup"><span data-stu-id="83d96-108">In order to allow for seamless porting of Chrome APIs to supported Microsoft Edge APIs, two scripts are added to your extension's folder.</span></span> <span data-ttu-id="83d96-109">これらのスクリプトは API (必要に応じてポリフィル) をブリッジします。つまり、バックグラウンド スクリプトやコンテンツ スクリプトで Chrome 固有のコードを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="83d96-109">These scripts bridge APIs (polyfiling where necessary), meaning you won't have to worry about changing any Chrome specific code in your background script or content scripts.</span></span>

<span data-ttu-id="83d96-110">変換後、キーを使用して拡張機能のマニフェスト ファイルに含まれているのが表示 `"-ms-preload"` されます。</span><span class="sxs-lookup"><span data-stu-id="83d96-110">After conversion, you will see them included in the manifest file of your extension with the `"-ms-preload"` key:</span></span>

```json
"-ms-preload": {
  "backgroundScript": "backgroundScriptsAPIBridge.js",
  "contentScript": "contentScriptsAPIBridge.js"
}
```

## <span data-ttu-id="83d96-111">Microsoft Edge 拡張機能のToolkit</span><span class="sxs-lookup"><span data-stu-id="83d96-111">Using the Microsoft Edge Extension Toolkit</span></span>

<span data-ttu-id="83d96-112">次の手順では、Chrome 拡張機能を Windows 10 Anniversary Update エディションの Microsoft Edge で実行するように変換する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="83d96-112">The following instructions detail how to convert your Chrome extension to run on Microsoft Edge in the Windows 10 Anniversary Update edition:</span></span>

1. <span data-ttu-id="83d96-113">Microsoft [Edge Extension Toolkit をインストールします](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)。</span><span class="sxs-lookup"><span data-stu-id="83d96-113">Install the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span>
2. <span data-ttu-id="83d96-114">安全な保管のために Chrome 拡張機能のフォルダーのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="83d96-114">Make a copy of your Chrome extension's folder for safe keeping.</span></span> <span data-ttu-id="83d96-115">変換プロセスによってコードが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="83d96-115">The conversion process will overwrite the code.</span></span> 
3. <span data-ttu-id="83d96-116">Microsoft Edge Extension Toolkitを実行し、拡張機能のコピーを読み込む。</span><span class="sxs-lookup"><span data-stu-id="83d96-116">Run the Microsoft Edge Extension Toolkit and load the copy of your extension.</span></span>  
 ![拡張機能の読み込みボタン](./../media/save-folder.png)
4. <span data-ttu-id="83d96-118">ツールのテキスト エディター内で報告されるエラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="83d96-118">Correct all the errors that are reported within the tool's text editor.</span></span> <span data-ttu-id="83d96-119">修正後にエラーを確認するには、[再検証] を選択します。</span><span class="sxs-lookup"><span data-stu-id="83d96-119">Select "Re-validate" to check for errors after making corrections.</span></span>  
 ![extension-toolkit のエラー検出](./../media/extension-toolkit.png)
5. <span data-ttu-id="83d96-121">[ファイルの保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="83d96-121">Select "Save files".</span></span>

<span data-ttu-id="83d96-122">これで、ツールキットから抜け出して、Microsoft Edge で拡張機能を読み込むのが可能です。</span><span class="sxs-lookup"><span data-stu-id="83d96-122">You can now exit out of the toolkit and load your extension in Microsoft Edge!</span></span> 

<span data-ttu-id="83d96-123">EdgeHTML の問題追跡ツールを使用して、既知のプラットフォーム [の問題を検索できます](http://issues.microsoftedge.com)。</span><span class="sxs-lookup"><span data-stu-id="83d96-123">You can search for known platform issues with the [EdgeHTML issue tracker](http://issues.microsoftedge.com).</span></span> <span data-ttu-id="83d96-124">新しい情報が見つかったと思う場合は、 [問題を開きます](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)。</span><span class="sxs-lookup"><span data-stu-id="83d96-124">If you think you've found something new, [open an issue](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)!</span></span>
