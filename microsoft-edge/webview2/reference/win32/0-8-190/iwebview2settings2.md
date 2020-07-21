---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2Settings2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 4ba0299f3afbc6fc2846481f52c1000cd338ecd8
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885787"
---
# <span data-ttu-id="96179-104">0.8.355-インターフェイス IWebView2Settings2</span><span class="sxs-lookup"><span data-stu-id="96179-104">0.8.355 - interface IWebView2Settings2</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Settings2
  : public IWebView2Settings
```

<span data-ttu-id="96179-105">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="96179-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="96179-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="96179-106">Summary</span></span>

 <span data-ttu-id="96179-107">Members</span><span class="sxs-lookup"><span data-stu-id="96179-107">Members</span></span>                        | <span data-ttu-id="96179-108">説明</span><span class="sxs-lookup"><span data-stu-id="96179-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="96179-109">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="96179-109">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="96179-110">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="96179-110">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="96179-111">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="96179-111">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="96179-112">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="96179-112">Set the AreDefaultContextMenusEnabled property.</span></span>

<span data-ttu-id="96179-113">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="96179-113">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="96179-114">Members</span><span class="sxs-lookup"><span data-stu-id="96179-114">Members</span></span>

#### <span data-ttu-id="96179-115">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="96179-115">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="96179-116">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="96179-116">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="96179-117">パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="96179-117">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="96179-118">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="96179-118">Defaults to TRUE.</span></span>

```cpp
            BOOL allowContextMenus;
            CHECK_FAILURE(m_settings->get_AreDefaultContextMenusEnabled(
                &allowContextMenus));
            if (allowContextMenus) {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(FALSE));
                MessageBox(nullptr,
                L"Context menus will be disabled after the next navigation.",
                L"Settings change", MB_OK);
            }
            else {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(TRUE));
                MessageBox(nullptr,
                    L"Context menus will be enabled after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="96179-119">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="96179-119">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="96179-120">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="96179-120">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="96179-121">パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="96179-121">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

