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
# 0.8.355-インターフェイス IWebView2Settings2 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Settings2
  : public IWebView2Settings
```

WebView 機能を有効、無効、または変更するプロパティを定義します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled) | AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。
[put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled) | AreDefaultContextMenusEnabled プロパティを設定します。

NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。

## Members

#### get_AreDefaultContextMenusEnabled 

AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。

> パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール * enabled)

既定値は TRUE です。

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

#### put_AreDefaultContextMenusEnabled 

AreDefaultContextMenusEnabled プロパティを設定します。

> パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)

