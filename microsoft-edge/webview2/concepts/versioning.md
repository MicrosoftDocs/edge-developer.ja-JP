---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/18/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 8463ce403af069cf25dbf7b08bb49d44c1e54501
ms.sourcegitcommit: f1aa8925f7985a2bbfd951f188a8c19c97e4ff6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2020
ms.locfileid: "10659570"
---
# <span data-ttu-id="5b03b-104">ブラウザーのバージョンと WebView2 について</span><span class="sxs-lookup"><span data-stu-id="5b03b-104">Understanding browser versions and WebView2</span></span>  

<span data-ttu-id="5b03b-105">WebView2 は Microsoft Edge によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5b03b-105">WebView2 depends on Microsoft Edge to function.</span></span>  <span data-ttu-id="5b03b-106">各 WebView2 SDK では、最小ブラウザーバージョンがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b03b-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="5b03b-107">このブラウザバージョンは、[リリースノート][Webview2Releasenotes]で指定されています。</span><span class="sxs-lookup"><span data-stu-id="5b03b-107">This browser version is specified in our [Release Notes][Webview2Releasenotes].</span></span>  <span data-ttu-id="5b03b-108">パッケージバージョンの SDK には、最小バージョンが反映されています。</span><span class="sxs-lookup"><span data-stu-id="5b03b-108">You may see the minimum version reflected in the package version of the SDK.</span></span>  <span data-ttu-id="5b03b-109">たとえば、を使用する場合は、 `SDK package version 0.9.488` 488 以降のビルド番号で Microsoft Edge をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b03b-109">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span>  <span data-ttu-id="5b03b-110">ブラウザーの最新リリースの詳細については、「[ブラウザーチャネル][DeployedgeChannels]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b03b-110">For more information on the latest releases of the browser, see [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="5b03b-111">WebView2 は現在、プレビューに表示されています。</span><span class="sxs-lookup"><span data-stu-id="5b03b-111">WebView2 is currently in Preview.</span></span>  <span data-ttu-id="5b03b-112">Microsoft Edge WebView チームは、ブラウザーバージョンと Sdk 間の下位互換性を確保するために努力していますが、ブラウザーの新しいバージョンによっては、古いバージョンの SDK がサポートされていない可能性があることを保証していません。</span><span class="sxs-lookup"><span data-stu-id="5b03b-112">While, the Microsoft Edge WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed as some newer versions of the browser may not support older SDK versions.</span></span>  <span data-ttu-id="5b03b-113">ブラウザーのバージョンと Sdk の間に互換性のある変更がある場合は、Microsoft Edge WebView チームに[リリースノート][Webview2Releasenotes]の変更が示されます。</span><span class="sxs-lookup"><span data-stu-id="5b03b-113">If there are breaking changes between browser versions and SDKs, the Microsoft Edge WebView team indicates the changes in the [release notes][Webview2Releasenotes].</span></span>  

<span data-ttu-id="5b03b-114">今後、Microsoft Edge WebView チームは、配布モデルの変更を計画しています。</span><span class="sxs-lookup"><span data-stu-id="5b03b-114">In the future, the Microsoft Edge WebView team plans to change the distribution model.</span></span>  <span data-ttu-id="5b03b-115">Microsoft Edge WebView チームは、WebView2 から Microsoft Edge ブラウザーへの直接の依存関係を削除することを計画しています。</span><span class="sxs-lookup"><span data-stu-id="5b03b-115">The Microsoft Edge WebView team plans to remove the direct dependency on the Microsoft Edge browser from WebView2.</span></span>  <!--To learn more, see [WebView2 Runtime][Webview2IndexEdgeRuntime] in the [Distribution][Webview2Distibution] section.  -->  

<!--todo: dd link to distribution.md after publication  -->  

## <span data-ttu-id="5b03b-116">試験的な API</span><span class="sxs-lookup"><span data-stu-id="5b03b-116">Experimental APIs</span></span>  

<span data-ttu-id="5b03b-117">WebView2 はプレビューですが、SDK の Api は GA 時に同じであると想定されています。</span><span class="sxs-lookup"><span data-stu-id="5b03b-117">While WebView2 is a preview, the APIs in the SDK are expected to remain the same at GA.</span></span>  <span data-ttu-id="5b03b-118">SDK には[実験的な api][Webview2ReferenceWin3209488Experimental]が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b03b-118">There are [experimental APIs][Webview2ReferenceWin3209488Experimental] included in the SDK.</span></span>  <span data-ttu-id="5b03b-119">試用版 Api を評価し、 [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使ってフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="5b03b-119">Please evaluate the experimental APIs and send your feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

### <span data-ttu-id="5b03b-120">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="5b03b-120">Roadmap</span></span>  

<span data-ttu-id="5b03b-121">WebView2 が安定した一般的な状態に到達して、1.0.0 SDK を解放すると、Microsoft Edge WebView チームは、すべての実験的 Api をプレリリースパッケージに移行することを計画します。</span><span class="sxs-lookup"><span data-stu-id="5b03b-121">After WebView2 reaches a stable general available state and we release the 1.0.0 SDK, the Microsoft Edge WebView team plans to move all experimental APIs to a pre-release package.</span></span>  <span data-ttu-id="5b03b-122">プレリリース版のパッケージでは、引き続き最新機能を利用できます。また、安定性の高いリリースバージョンでは下位互換性が維持されます。</span><span class="sxs-lookup"><span data-stu-id="5b03b-122">The pre-release package continues to allow for feedback and insight into the latest features, while the stable release version maintains backward compatibility.</span></span>  

<!--links -->

[Webview2Distibution]: ./distribution.md "存在しない |Microsoft ドキュメント"  
[Webview2IndexEdgeRuntime]: ../index.md#microsoft-edge-webview2-runtime "Microsoft Edge WebView2 Runtime-Microsoft Edge WebView2 (開発者向けプレビュー) |Microsoft ドキュメント"  
[Webview2ReferenceWin3209488Experimental]: ../reference/win32/0-9-488-reference-webview2.md#experimental "実験的な参照 (WebView2) |Microsoft ドキュメント"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
