---
ms.assetid: 1319a070-c6e3-4592-9f4b-40ce1575851f
description: Microsoft edge 拡張ツールキットを使って、Chrome 拡張機能を Microsoft Edge に移植する方法について説明します。
title: Chrome 拡張機能の移植
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: 38bf1324c2e7e6f7754912177ce0e53d6c15a276
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569438"
---
# <span data-ttu-id="12584-104">拡張子を Chrome から Microsoft Edge に移植する</span><span class="sxs-lookup"><span data-stu-id="12584-104">Porting an extension from Chrome to Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="12584-105">[Microsoft Edge 拡張ツールキット](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)を使うと、Chrome から microsoft edge に拡張機能を移植するのが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="12584-105">Porting an extension from Chrome to Microsoft Edge is made easy with the help of the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span> <span data-ttu-id="12584-106">この開発者ツールでは、展開された Chrome 拡張機能を Api を使って、ファイル内のエラーを提示することによって、展開された Microsoft Edge extension に変換し `manifest.json` ます。</span><span class="sxs-lookup"><span data-stu-id="12584-106">This developer tool converts an unpacked Chrome extension to an unpacked Microsoft Edge extension by bridging APIs and surfacing any errors in your `manifest.json` file.</span></span>


### <span data-ttu-id="12584-107">API ブリッジ</span><span class="sxs-lookup"><span data-stu-id="12584-107">API bridges</span></span>
<span data-ttu-id="12584-108">サポートされている Microsoft Edge Api への Chrome Api のシームレスな移植を可能にするために、2つのスクリプトが拡張機能のフォルダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="12584-108">In order to allow for seamless porting of Chrome APIs to supported Microsoft Edge APIs, two scripts are added to your extension's folder.</span></span> <span data-ttu-id="12584-109">これらのスクリプトは、必要に応じてブリッジ Api (polyfiling) を使用するため、バックグラウンドスクリプトまたはコンテンツスクリプトで Chrome 固有のコードを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="12584-109">These scripts bridge APIs (polyfiling where necessary), meaning you won't have to worry about changing any Chrome specific code in your background script or content scripts.</span></span>

<span data-ttu-id="12584-110">変換後、それらのファイルは、拡張機能のマニフェストファイルに含まれてい `"-ms-preload"` ます。</span><span class="sxs-lookup"><span data-stu-id="12584-110">After conversion, you will see them included in the manifest file of your extension with the `"-ms-preload"` key:</span></span>

```json
"-ms-preload": {
  "backgroundScript": "backgroundScriptsAPIBridge.js",
  "contentScript": "contentScriptsAPIBridge.js"
}
```

## <span data-ttu-id="12584-111">Microsoft Edge 拡張ツールキットを使用する</span><span class="sxs-lookup"><span data-stu-id="12584-111">Using the Microsoft Edge Extension Toolkit</span></span>

<span data-ttu-id="12584-112">次の手順では、Windows 10 記念日更新プログラムの Microsoft Edge で Chrome 拡張機能を実行するための変換方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="12584-112">The following instructions detail how to convert your Chrome extension to run on Microsoft Edge in the Windows 10 Anniversary Update edition:</span></span>

1. <span data-ttu-id="12584-113">[Microsoft Edge 拡張機能キット](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="12584-113">Install the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span>
2. <span data-ttu-id="12584-114">Chrome の拡張機能のフォルダーのコピーを作成して安全を確保します。</span><span class="sxs-lookup"><span data-stu-id="12584-114">Make a copy of your Chrome extension's folder for safe keeping.</span></span> <span data-ttu-id="12584-115">変換プロセスによってコードが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="12584-115">The conversion process will overwrite the code.</span></span> 
3. <span data-ttu-id="12584-116">Microsoft Edge 拡張ツールキットを実行して、拡張機能のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="12584-116">Run the Microsoft Edge Extension Toolkit and load the copy of your extension.</span></span>  
 ![[拡張機能の読み込み] ボタン](./../media/save-folder.png)
4. <span data-ttu-id="12584-118">ツールのテキストエディターで報告されるすべてのエラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="12584-118">Correct all the errors that are reported within the tool's text editor.</span></span> <span data-ttu-id="12584-119">修正を行った後にエラーが発生したかどうかを確認するには、"再検証" を選択します。</span><span class="sxs-lookup"><span data-stu-id="12584-119">Select "Re-validate" to check for errors after making corrections.</span></span>  
 ![拡張機能-ツールキットの検索エラー](./../media/extension-toolkit.png)
5. <span data-ttu-id="12584-121">[ファイルの保存] を選びます。</span><span class="sxs-lookup"><span data-stu-id="12584-121">Select "Save files".</span></span>

<span data-ttu-id="12584-122">これで、ツールキットを終了して、Microsoft Edge で拡張機能を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="12584-122">You can now exit out of the toolkit and load your extension in Microsoft Edge!</span></span> 

<span data-ttu-id="12584-123">[EdgeHTML issue tracker](http://issues.microsoftedge.com)で、既知のプラットフォームの問題を検索できます。</span><span class="sxs-lookup"><span data-stu-id="12584-123">You can search for known platform issues with the [EdgeHTML issue tracker](http://issues.microsoftedge.com).</span></span> <span data-ttu-id="12584-124">新しいものが見つかった場合は、[問題を開き](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)ます。</span><span class="sxs-lookup"><span data-stu-id="12584-124">If you think you've found something new, [open an issue](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)!</span></span>
