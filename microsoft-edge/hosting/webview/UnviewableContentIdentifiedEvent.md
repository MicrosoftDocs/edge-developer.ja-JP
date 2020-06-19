---
description: Webview がサポートされていないファイルをダウンロードしようとしていることを示します。
title: UnviewableContentIdentifiedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 0179522f3eaf0813531084eb996ee9d392e8249d
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752014"
---
# <span data-ttu-id="78397-104">UnviewableContentIdentifiedEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="78397-104">UnviewableContentIdentifiedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="78397-105">[Webview](../webview.md)が、サポートされていないコンテンツタイプのファイルに移動しようとしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="78397-105">Indicates the [webview](../webview.md) is attempting to navigate to a file of an unsupported content type.</span></span>  

## <span data-ttu-id="78397-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="78397-106">Properties</span></span>  

### <span data-ttu-id="78397-107">メディア</span><span class="sxs-lookup"><span data-stu-id="78397-107">mediaType</span></span>  

<span data-ttu-id="78397-108">Unviewable コンテンツのコンテンツタイプを取得します。</span><span class="sxs-lookup"><span data-stu-id="78397-108">Gets the content type of the unviewable content.</span></span>  

<span data-ttu-id="78397-109">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="78397-109">This property is read-only</span></span>  

```javascript
var mediaType = UnviewableContentIdentifiedEvent.mediaType;
```  

#### <span data-ttu-id="78397-110">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="78397-110">Property value</span></span>  

<span data-ttu-id="78397-111">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="78397-111">Type: **DOMString**</span></span>  

### <span data-ttu-id="78397-112">referer</span><span class="sxs-lookup"><span data-stu-id="78397-112">referer</span></span>  

<span data-ttu-id="78397-113">ナビゲーションを要求している[webview](../webview.md)のページの Uniform resource IDENTIFIER (URI) です。</span><span class="sxs-lookup"><span data-stu-id="78397-113">The Uniform Resource Identifier (URI) of the page in the [webview](../webview.md) requesting navigation.</span></span>  

<span data-ttu-id="78397-114">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="78397-114">This property is read-only.</span></span>  

```javascript
var referer = NavigationEventWithReferrer.referer;
```  

#### <span data-ttu-id="78397-115">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="78397-115">Property value</span></span>  

<span data-ttu-id="78397-116">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="78397-116">Type: **DOMString**</span></span>  

### <span data-ttu-id="78397-117">uri</span><span class="sxs-lookup"><span data-stu-id="78397-117">uri</span></span>  

<span data-ttu-id="78397-118">ナビゲーションの送信先の Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="78397-118">The Uniform Resource Identifier (URI) of the destination of the navigation.</span></span>  

<span data-ttu-id="78397-119">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="78397-119">This property is read-only.</span></span>  

```javascript
var uri = NavigationEventWithReferrer.uri;
```  

#### <span data-ttu-id="78397-120">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="78397-120">Property value</span></span>  

<span data-ttu-id="78397-121">Type: **Domstring**</span><span class="sxs-lookup"><span data-stu-id="78397-121">Type: **DOMString**</span></span>  
