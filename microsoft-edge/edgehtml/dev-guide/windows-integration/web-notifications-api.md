---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: Web 通知 API を使用して、Web サイトが Microsoft Edge ブラウザーのコンテキスト外でユーザーに通知を送信する方法について説明します。
title: Web 通知 API - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2be201a790c6fca1526c8b6eb13e4203e8e53206
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234822"
---
# Web 通知 API  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Web 通知 API を使用すると、Web サイトは Microsoft Edge ブラウザー内の Web ページのコンテキスト外でユーザーに通知を送信できます。  この機能の動作の例として、Skype のようなメッセージング アプリケーションがあります。  ユーザーが新しいメッセージを受信すると、デスクトップに通知が表示され、メッセージが通知されます。  Web 通知は、Windows 10 内の通知プラットフォームおよびアクション センターと完全に統合されています。  

## 通知の作成  

次の CodePen は、タイトル、アイコン、本文のオプションが設定[](https://msdn.microsoft.com/library/mt710826)された[Notification](https://msdn.microsoft.com/library/mt710818)オブジェクトを作成して、Skype[のモック](https://msdn.microsoft.com/library/mt710814)[通知を](https://msdn.microsoft.com/library/mt710811)作成します。  

<iframe height='295' scrolling='no' title='Web 通知' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>CodePen で Microsoft Edge Docs ( @MicrosoftEdgeDocumentation ) によるペン <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> Web </a> <a href='https://codepen.io/MicrosoftEdgeDocumentation'> </a> 通知 <a href='https://codepen.io'> を参照してください </a> 。</iframe>  

通知ごとにアイコンを指定 **する方法を** 強く推奨します。  これにより、UI の観点からの通知が向上するだけでなく、通知の送信場所をユーザーに通知するのにも役立ちます。  

Web 通知の作成に関するチュートリアルと、Windows 10 内での動作を確認するには、以下のビデオをご覧ください。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]  

### 通知プロパティ  

通知は、次のプロパティで設定できます。  

:::row:::
   :::column span="1":::
      [body](https://developer.mozilla.org/docs/Web/API/Notification/body)  
   :::column-end:::
   :::column span="2":::
      通知の本文テキスト。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [dir](https://developer.mozilla.org/docs/Web/API/Notification/dir)  
   :::column-end:::
   :::column span="2":::
      通知のテキストの方向。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [icon](https://developer.mozilla.org/docs/Web/API/Notification/icon)  
   :::column-end:::
   :::column span="2":::
      アイコンに使用される通知の URL。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [lang](https://developer.mozilla.org/docs/Web/API/Notification/lang)  
   :::column-end:::
   :::column span="2":::
      通知の言語。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [permission](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      現在のオリジンに対してユーザーが付与した現在の通知表示アクセス許可。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [tag](https://developer.mozilla.org/docs/Web/API/Notification/tag)  
   :::column-end:::
   :::column span="2":::
      通知のタグ。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [title](https://developer.mozilla.org/docs/Web/API/Notification/title)  
   :::column-end:::
   :::column span="2":::
      通知のタイトル。  
   :::column-end:::
:::row-end:::  

### 通知イベント  

Notification オブジェクトでは、次のイベントが [使用](https://developer.mozilla.org/docs/Web/API/Notification) されます。  

:::row:::
   :::column span="1":::
      [onclick](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      ユーザーが通知をクリックすると発生します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onclose](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
   :::column-end:::
   :::column span="2":::
      ユーザーによって通知が閉じたり、自動タイムアウトが発生したりすると発生します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onerror](https://developer.mozilla.org/docs/Web/API/Element/error_event)  
   :::column-end:::
   :::column span="2":::
      通知の処理中にエラーが発生すると発生します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onshow](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      通知が表示された場合に発生します。  
   :::column-end:::
:::row-end:::  

### 通知メソッド  

Notification オブジェクトでは、次のメソッドが [使用](https://developer.mozilla.org/docs/Web/API/Notification) されます。  

:::row:::
   :::column span="1":::
      [close](https://developer.mozilla.org/docs/Web/API/Notification/close)  
   :::column-end:::
   :::column span="2":::
      表示された通知を閉じます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)  
   :::column-end:::
   :::column span="2":::
      現在のオリジンによる通知の表示を許可するアクセス許可をユーザーに要求します。  
   :::column-end:::
:::row-end:::  

## 通知のアクセス許可  

Microsoft Edge を使用すると、ユーザーは特定の Web サイト ドメインごとに通知のアクセス許可を管理できます。  ドメインから通知の表示を求めるメッセージが**** 表示された**** 場合は、ユーザーが [はい] または [いいえ] を選択します。  [requestPermission メソッドは](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)、アクセス許可の状態を 、または `granted` `denied` `default` .  値は、ユーザーが決定を行いたことがないかどうかを示します。これは、次の値 `default` と同等と見なされます `denied` 。  

## API リファレンス  

[Web 通知](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## 仕様  

[Web 通知](https://notifications.spec.whatwg.org)  
