---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: cb317e9078e48ed14091eb2eda6ff9d59a19c6ce
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654307"
---
# <span data-ttu-id="3cb2b-104">インターフェイス IWebView2Settings2</span><span class="sxs-lookup"><span data-stu-id="3cb2b-104">interface IWebView2Settings2</span></span> 

> [!NOTE]
> <span data-ttu-id="3cb2b-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3cb2b-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="3cb2b-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb2b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Settings2
  : public IWebView2Settings
```

<span data-ttu-id="3cb2b-107">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cb2b-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="3cb2b-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="3cb2b-108">Summary</span></span>

 <span data-ttu-id="3cb2b-109">Members</span><span class="sxs-lookup"><span data-stu-id="3cb2b-109">Members</span></span>                        | <span data-ttu-id="3cb2b-110">説明</span><span class="sxs-lookup"><span data-stu-id="3cb2b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3cb2b-111">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="3cb2b-111">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="3cb2b-112">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="3cb2b-112">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="3cb2b-113">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="3cb2b-113">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="3cb2b-114">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3cb2b-114">Set the AreDefaultContextMenusEnabled property.</span></span>

<span data-ttu-id="3cb2b-115">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="3cb2b-115">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="3cb2b-116">Members</span><span class="sxs-lookup"><span data-stu-id="3cb2b-116">Members</span></span>

#### <span data-ttu-id="3cb2b-117">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="3cb2b-117">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="3cb2b-118">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="3cb2b-118">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="3cb2b-119">パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="3cb2b-119">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="3cb2b-120">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="3cb2b-120">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="3cb2b-121">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="3cb2b-121">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="3cb2b-122">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3cb2b-122">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="3cb2b-123">パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="3cb2b-123">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

