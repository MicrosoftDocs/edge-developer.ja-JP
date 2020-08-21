---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: Web 通知 API を使用して Web サイトでユーザーに通知を送信する方法について説明します。
title: Web Notifications API - デベロッパー ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 24b8a7b25fb3e0f0221f6d81b105d5d0374ea423
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941797"
---
# Web 通知 API  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Web Notifications API を使用すると、Web サイトは Microsoft Edge ブラウザー内の Web ページのコンテキスト外でユーザーに通知を送信できます。  この機能の例として、Skype のようなメッセージング アプリケーションが使用されています。  ユーザーが新しいメッセージを受信すると、デスクトップに通知が表示され、メッセージが通知されます。  Web 通知は、Windows 10 内の通知プラットフォームとアクション センターと完全に統合されています。  

## 通知の作成  

以下の CodePen は、タイトル、アイコン、および本文オプションを設定した[Notification](https://msdn.microsoft.com/library/mt710818)通知オブジェクトを作成[title](https://msdn.microsoft.com/library/mt710826)して、[icon](https://msdn.microsoft.com/library/mt710814)マッキピボの Skype 通知[を](https://msdn.microsoft.com/library/mt710811)作成します。  

<iframe height='295' scrolling='no' title='Web 通知' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> </a> CodePen で Microsoft Edge Docs <a href='https://codepen.io/MicrosoftEdgeDocumentation'> (@MicrosoftEdgeDocumentation) によるペン Web の通知 </a> <a href='https://codepen.io'> を確認できます </a> 。</iframe>  

通知ごとにアイコンを指定すること **を** 強くお勧めします。  これにより、UI のビューに表示される通知は改善されるだけでなく、通知の送信先をユーザーに通知するのにも役立ちます。  

下のビデオでは、Web 通知の作成方法と、Windows 10 内での動作を確認できます。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]  

### 通知のプロパティ  

次のプロパティを使用して通知を設定できます。  

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
      通知の URL はアイコンに使用されます。  
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
      [アクセス許可](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      現在の通知表示アクセス許可は、ユーザーが現在の送信先の送信先の位置を付与したことを示しています。  
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

Notification オブジェクトで次のイベントが [使用](https://developer.mozilla.org/docs/Web/API/Notification) されます。  

:::row:::
   :::column span="1":::
      [onclick](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      ユーザーが通知をクリックしたときに、ファイアウォールします。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onclose](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
   :::column-end:::
   :::column span="2":::
      ユーザーまたは自動タイムアウトによって通知が閉じたときに、通知が閉じたときに実行されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onerror](https://developer.mozilla.org/docs/Web/API/Element/error_event)  
   :::column-end:::
   :::column span="2":::
      通知の処理中にエラーが発生したときに、ファイアウォールを実行します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [オン](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      通知が表示されたときにファイアウォールを行います。  
   :::column-end:::
:::row-end:::  

### 通知方法  

Notification オブジェクトでは、次のメソッド [が使用](https://developer.mozilla.org/docs/Web/API/Notification) されます。  

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
      現在の場所に通知を表示することを許可する権限をユーザーに要求します。  
   :::column-end:::
:::row-end:::  

## 通知のアクセス許可  

Microsoft Edge を使用すると、ユーザーは特定の Web サイト ドメインに対する通知権限を管理できます。  ユーザーに通知を表示する準備ができた **ら、[はい** ] または **[い** いえ] を選択します。  [requestPermission メ](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)ソッドは、アクセス許可状態をいずれかのアクセス許可状態として、または `granted` `denied` `default`  値は、ユーザーが同等の決める決める決済 `default` を下す値を示します `denied` 。  

## API リファレンス  

[Web 通知](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## Specification  

[Web 通知](https://notifications.spec.whatwg.org)  
