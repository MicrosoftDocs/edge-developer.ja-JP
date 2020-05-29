---
description: VS コードから Microsoft Edge (Chromium) の要素を使う方法
title: VS コードからの Microsoft Edge (Chromium) の要素
author: erdraud
ms.author: erdraud
ms.date: 08/08/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、要素
ms.openlocfilehash: 4875a4665fe1561ecf587a050bbd44e116d9ce5e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570741"
---
# <span data-ttu-id="90f8d-104">Microsoft Edge VS コード拡張の要素</span><span class="sxs-lookup"><span data-stu-id="90f8d-104">Elements for Microsoft Edge VS Code extension</span></span>

<span data-ttu-id="90f8d-105">Microsoft Edge VS コード拡張[用の要素](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools)を追加することで、ブラウザーの要素ツールを[Visual Studio コード](https://code.visualstudio.com/)内から使うことができます。</span><span class="sxs-lookup"><span data-stu-id="90f8d-105">By adding the [Elements for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools) VS Code extension, you can use the browser's Elements tool from within [Visual Studio Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="90f8d-106">起動またはアタッチのどちらの場合も、要素ツールは Microsoft Edge のインスタンスに接続され、ランタイム HTML 構造を表示し、レイアウトを変更したり、スタイル設定の問題を修正したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="90f8d-106">By either launching or attaching, the Elements tool will connect to an instance of Microsoft Edge, display the runtime HTML structure, and allow you to alter the layout or fix styling issues.</span></span>

![勤務先の Edge VS コード拡張の要素の GIF](./media/elements-for-edge.gif)

## <span data-ttu-id="90f8d-108">要素の拡張機能から Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="90f8d-108">Launching Microsoft Edge From the Elements extension</span></span> 

<span data-ttu-id="90f8d-109">**アクティビティバー**の要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="90f8d-109">Navigate to Elements in the **Activity Bar**.</span></span> <span data-ttu-id="90f8d-110">[Microsoft Edge: ターゲットの要素] と表示されている場所の横に、アプリのブラウザーを開くためのプラス記号が付いています。</span><span class="sxs-lookup"><span data-stu-id="90f8d-110">Next to where it says "Elements for Microsoft Edge: Targets," there is a plus sign that will open the browser for your app.</span></span> <span data-ttu-id="90f8d-111">[*バージョン情報:* ] オプションを選んだ場合は、ブラウザーで web アプリに移動して、VS コードの要素パネルに表示されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f8d-111">If you selected the *about:blank* option, you will have to navigate to your web app in the browser for it to appear in the Elements panel in VS Code.</span></span>

## <span data-ttu-id="90f8d-112">デバッグビューから Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="90f8d-112">Launching Microsoft Edge from the Debug view</span></span>

<span data-ttu-id="90f8d-113">Visual Studio コードでデバッグビューを使うことに慣れている場合は、そのツールから要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="90f8d-113">If you are accustomed to using the Debug view in Visual Studio Code, you can access Elements from that tool.</span></span> <span data-ttu-id="90f8d-114">( `Ctrl`  +  `Shift`  +  `D` Windows または Mac 上の) [デバッグ] ビューに移動 `Command`  +  `Shift`  +  `D` します。</span><span class="sxs-lookup"><span data-stu-id="90f8d-114">Navigate to the Debug view (`Ctrl` + `Shift` + `D` on Windows or `Command` + `Shift` + `D` on Mac).</span></span> 

<span data-ttu-id="90f8d-115">VS コードにまだ構成がない場合 `F5` は、Windows または Mac を押すか、緑色の**再生**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f8d-115">If you do not have any configurations in VS Code, press `F5` on Windows or Mac or click the green **Play** button.</span></span> <span data-ttu-id="90f8d-116">ドロップダウンで [Edge] を選びます。</span><span class="sxs-lookup"><span data-stu-id="90f8d-116">Select "Edge" in the dropdown.</span></span> <span data-ttu-id="90f8d-117">これで、次のように構成された**launch**ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90f8d-117">You will now see a **launch.json** file with the following configuration:</span></span>

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            
            "name": "Launch Microsoft Edge and open the Elements tool",
            "request": "launch",
            "type": "vscode-edge-devtools.debug",
            "url": "http://localhost:3000"
        
        }
    ]
}
```

<span data-ttu-id="90f8d-118">これで正しい構成が読み込まれたので、 `F5` Windows または Mac を押すか、緑色の**再生**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f8d-118">Now that you have loaded the correct configuration, either press `F5` on Windows or Mac or click the green **Play** button.</span></span> <span data-ttu-id="90f8d-119">Microsoft Edge ブラウザーで使い慣れた要素ツールが VS コードで起動し、ブラウザーの screencast にアクセスして、ページのコンポーネントを調べることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="90f8d-119">The Elements tool you are familiar with from the Microsoft Edge browser will now launch in VS Code, allowing you to access a screencast of your browser and examine the components of your page.</span></span>

## <span data-ttu-id="90f8d-120">Microsoft Edge へのアタッチ</span><span class="sxs-lookup"><span data-stu-id="90f8d-120">Attaching to Microsoft Edge</span></span>
<span data-ttu-id="90f8d-121">Microsoft Edge (Chromium) のインスタンスに VS コードをアタッチする場合は、teminal から次のコマンドを実行して、ブラウザーを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f8d-121">If you'd like to attach VS Code to an instance of Microsoft Edge (Chromium), you must start the browser by running the following command from your teminal:</span></span>

`start msedge --remote-debugging-port=9222`

<span data-ttu-id="90f8d-122">アプリが起動したら、次の構成を起動の**json**ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="90f8d-122">Once the app has launched, add the configuration below to your **launch.json** file:</span></span>

```json
{
    "type": "vscode-edge-devtools.debug",
    "request": "attach",
    "name": "Attach to Microsoft Edge and open the Elements tool",
    "url": "http://localhost:3000/",
    "webRoot": "${workspaceFolder}/out",
    "port": 9222
}
```

<span data-ttu-id="90f8d-123">[Microsoft Edge にアタッチして、デバッガー] ドロップダウンメニューから [要素ツール] を開きます。</span><span class="sxs-lookup"><span data-stu-id="90f8d-123">Select "Attach to Microsoft Edge and open the Elements tool" from the Debugger drop-down menu.</span></span> <span data-ttu-id="90f8d-124">次に、 `F5` Windows または Mac を押すか、緑色の**再生**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f8d-124">Next, either press `F5` on Windows or Mac or click the green **Play** button.</span></span> <span data-ttu-id="90f8d-125">VS コードによって要素ツールが起動し、ブラウザーの screencast にアクセスしたり、DOM を検査したり、ページ上のコンポーネントのスタイルを確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="90f8d-125">VS Code will launch the Elements tool, allowing you to access a screencast of your browser, inspect the DOM, and the styling of the components on your page.</span></span>

## <span data-ttu-id="90f8d-126">フィードバック</span><span class="sxs-lookup"><span data-stu-id="90f8d-126">Feedback</span></span>
<span data-ttu-id="90f8d-127">この拡張機能の[GitHub リポジトリ](https://github.com/microsoft/vscode-edge-devtools)に[関する問題を提出](https://github.com/microsoft/vscode-edge-devtools/issues/new)して、フィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="90f8d-127">Send us your feedback by [filing an issue](https://github.com/microsoft/vscode-edge-devtools/issues/new) against this extension's [GitHub repo](https://github.com/microsoft/vscode-edge-devtools).</span></span> 

<span data-ttu-id="90f8d-128">この延長を改善したい場合は、ご協力をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="90f8d-128">If you want to help us make this extension better, we welcome your contributions!</span></span> <span data-ttu-id="90f8d-129">[GitHub リポジトリ](https://github.com/microsoft/vscode-edge-devtools)での作業を開始するために必要なすべての情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="90f8d-129">You can find everything you need to get started in [our GitHub repo](https://github.com/microsoft/vscode-edge-devtools).</span></span>