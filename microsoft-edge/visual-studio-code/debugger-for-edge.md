---
description: VS コードから Microsoft Edge (Chromium) と Microsoft Edge (EdgeHTML) をデバッグする方法
title: VS コードから Microsoft Edge (Chromium) をデバッグする
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/10/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、デバッガー
ms.openlocfilehash: 7d8d2f87500b3e81866b49de32db91c0a525baf2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570737"
---
# <span data-ttu-id="5b19a-104">Microsoft Edge VS コード拡張用デバッガー</span><span class="sxs-lookup"><span data-stu-id="5b19a-104">Debugger for Microsoft Edge VS Code extension</span></span>

<span data-ttu-id="5b19a-105">[Microsoft Edge VS のコード拡張用のデバッガー](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)を使うと、フロントエンド JavaScript コードを1行ずつデバッグし、 `console.log()` [Visual Studio コード](https://code.visualstudio.com/)からステートメントを直接表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-105">With the [Debugger for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension, you can debug your front-end JavaScript code line by line and see `console.log()` statements all directly from [Visual Studio Code](https://code.visualstudio.com/)!</span></span>

![エッジと、作業中のコード拡張用デバッガーの GIF](./media/debugger-for-edge.gif)

## <span data-ttu-id="5b19a-107">Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="5b19a-107">Launching Microsoft Edge</span></span>

<span data-ttu-id="5b19a-108">`Ctrl`  +  `Shift`  +  `D` アクティビティバーの (Windows または Mac 上の `Command`  +  `Shift`  +  `D` ) **Activity Bar**デバッグビューに移動します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-108">Navigate to the Debug view (`Ctrl` + `Shift` + `D` on Windows or `Command` + `Shift` + `D` on Mac) in the **Activity Bar**.</span></span> <span data-ttu-id="5b19a-109">VS コードにまだ構成がない場合 `F5` は、Windows または Mac を押すか、緑色の**再生**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b19a-109">If you do not have any configurations in VS Code, press `F5` on Windows or Mac or click the green **Play** button.</span></span> <span data-ttu-id="5b19a-110">ドロップダウンで [Edge] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-110">Select "Edge" in the dropdown.</span></span> <span data-ttu-id="5b19a-111">これで、次のように構成された**launch**ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-111">You will now see a **launch.json** file with the following configuration:</span></span>

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "edge",
            "request": "launch",
            "name": "Launch Edge against localhost",
            "url": "http://localhost:8080",
            "webRoot": "${workspaceFolder}"
        }
    ]
}
```

<span data-ttu-id="5b19a-112">`F5`Windows または Mac を押すか、緑色の [**再生**] ボタンをもう一度クリックすると、vs コードによって Microsoft Edge (EdgeHTML) が起動し、ポート**8080**で実行している web プロジェクトを vs コードから直接デバッグできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5b19a-112">If you now press `F5` on Windows or Mac or click the green **Play** button again, VS Code will launch Microsoft Edge (EdgeHTML) and you will be able to debug any web project you have running on port **8080** directly from VS Code!</span></span>

### <span data-ttu-id="5b19a-113">Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="5b19a-113">Microsoft Edge (Chromium)</span></span>

<span data-ttu-id="5b19a-114">Microsoft edge (Chromium) を起動するには、microsoft edge (EdgeHTML) の代わりに、次のバージョンの microsoft edge の代わりに、 `version` 起動する Microsoft edge (Chromium) のバージョンを使用して、既存の構成に属性を追加 `dev` `beta` `canary` します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-114">If you want to launch Microsoft Edge (Chromium), the next version of Microsoft Edge, instead of Microsoft Edge (EdgeHTML), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge (Chromium) you want to launch (`dev`, `beta`, or `canary`).</span></span> <span data-ttu-id="5b19a-115">以下の構成では、Microsoft Edge (Chromium) のカナリアバージョンが起動されます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-115">The configuration below will launch the Canary version of Microsoft Edge (Chromium):</span></span>

```json
{
    "type": "edge",
    "request": "launch",
    "version": "canary",
    "name": "Launch Edge against localhost",
    "url": "http://localhost:8080",
    "webRoot": "${workspaceFolder}"
}
```

## <span data-ttu-id="5b19a-116">Microsoft Edge へのアタッチ</span><span class="sxs-lookup"><span data-stu-id="5b19a-116">Attaching to Microsoft Edge</span></span>

<span data-ttu-id="5b19a-117">また、Microsoft Edge (Chromium) に VS コードをアタッチすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-117">You can also attach VS Code to Microsoft Edge (Chromium).</span></span> <span data-ttu-id="5b19a-118">ターミナルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-118">From your terminal, run the following command:</span></span>

`start msedge --remote-debugging-port=9222`

<span data-ttu-id="5b19a-119">以下の構成を、使用**し**ている json ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-119">Add the configuration below to your **launch.json** file:</span></span>

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```

<span data-ttu-id="5b19a-120">この構成を現在実行している場合、VS コードは Microsoft Edge (Chromium) にアタッチされ、デバッグを開始できます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-120">If you now run this configuration, VS Code will attach to Microsoft Edge (Chromium) and you can start debugging!</span></span>

## <span data-ttu-id="5b19a-121">フィードバック</span><span class="sxs-lookup"><span data-stu-id="5b19a-121">Feedback</span></span>

<span data-ttu-id="5b19a-122">この拡張機能の[GitHub リポジトリ](https://github.com/Microsoft/vscode-edge-debug2)に[関する問題を提出](https://github.com/Microsoft/vscode-edge-debug2/issues/new)して、フィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="5b19a-122">Send us your feedback by [filing an issue](https://github.com/Microsoft/vscode-edge-debug2/issues/new) against this extension's [GitHub repo](https://github.com/Microsoft/vscode-edge-debug2).</span></span> <span data-ttu-id="5b19a-123">名前の付いた% temp% ディレクトリで、実行ごとに作成された debug adapter ログファイルを含めてください `vscode-edge-debug2.txt` 。</span><span class="sxs-lookup"><span data-stu-id="5b19a-123">Please include the debug adapter log file, which is created for each run in the %temp% directory with the name `vscode-edge-debug2.txt`.</span></span> <span data-ttu-id="5b19a-124">このファイルを問題のコメントにドラッグして、GitHub にアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-124">You can drag this file into an issue comment to upload it to GitHub.</span></span>

<span data-ttu-id="5b19a-125">この延長を改善したい場合は、ご協力をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="5b19a-125">If you want to help us make this extension better, we welcome your contributions!</span></span> <span data-ttu-id="5b19a-126">[GitHub リポジトリ](https://github.com/Microsoft/vscode-edge-debug2)での作業を開始するために必要なすべての情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-126">You can find everything you need to get started in [our GitHub repo](https://github.com/Microsoft/vscode-edge-debug2).</span></span>