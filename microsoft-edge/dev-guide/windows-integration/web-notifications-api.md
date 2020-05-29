---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: Web 通知 API を使用して、Web サイトが Microsoft Edge ブラウザーのコンテキスト外でユーザー通知を送信できるようにする方法について説明します。
title: 開発ガイド-Web 通知 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/18/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: da563a333491ef699925adec6f97b3c21d3e54a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569172"
---
# Web 通知 API

Web 通知 API を使用すると、web サイトは Microsoft Edge ブラウザー内で web ページのコンテキスト外でユーザー通知を送信することができます。 この機能の例としては、Skype などのメッセージングアプリケーションがあります。 ユーザーが新しいメッセージを受信すると、デスクトップに通知が表示され、メッセージが通知されます。 Web 通知は、Windows 10 の通知プラットフォームとアクションセンターと完全に統合されています。 

## 通知の作成

以下の CodePen では、、、オプションセットを使用してオブジェクトを作成することで、モックの Skype 通知を作成し [`Notification`](https://msdn.microsoft.com/library/mt710818) [`title`](https://msdn.microsoft.com/library/mt710826) [`icon`](https://msdn.microsoft.com/library/mt710814) [`body`](https://msdn.microsoft.com/library/mt710811) ます。


<iframe height='295' scrolling='no' title='Web 通知' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> </a> CodePen で Microsoft Edge ドキュメント (@MicrosoftEdgeDocumentation) によるペン Web 通知を参照してください <a href='https://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='https://codepen.io'> </a> 。
</iframe>

通知ごとに指定することを強くお勧め `icon` します。 これにより、UI ポイントからの通知が改善されるだけでなく、通知が送信される場所をユーザーに通知することもできます。

Web 通知の作成と Windows 10 での動作の確認については、以下のビデオをご覧ください。


> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]

### 通知プロパティ

通知を設定するには、次のオプションがあります。

プロパティ | 説明
:-------- | :----------
[body](https://msdn.microsoft.com/library/mt710811) | 通知の本文テキスト。
[dir](https://msdn.microsoft.com/library/mt710813) | 通知のテキストの方向。
[icon](https://msdn.microsoft.com/library/mt710814) | アイコンに使用される通知の URL。
[言語](https://msdn.microsoft.com/library/mt710815) | 通知の言語。
[アクセス許可](https://msdn.microsoft.com/library/mt670637) | 現在の起点に対してユーザーが付与した現在の通知表示アクセス許可。
[tag](https://msdn.microsoft.com/library/mt710825) | 通知のタグ。
[title](https://msdn.microsoft.com/library/mt710826) | 通知のタイトル。

### 通知イベント

このオブジェクトでは、次のイベントが使用され [`Notification`](https://msdn.microsoft.com/library/mt710818) ます。

イベント | 説明
:-------- | :----------
[onclick](https://msdn.microsoft.com/library/mt712180) | ユーザーが通知をクリックしたときに発生します。
[閉じる](https://msdn.microsoft.com/library/mt712178) | ユーザーまたは自動タイムアウトによって通知が閉じられたときに発生します。
[時](https://msdn.microsoft.com/library/mt712181) | 通知の処理中にエラーが発生したときに発生します。
[onshow](https://msdn.microsoft.com/library/mt712182) | 通知が表示されたときに発生します。

### 通知方法

このオブジェクトでは、次のメソッドが使用され [`Notification`](https://msdn.microsoft.com/library/mt710818) ます。

メソッド | [説明]
:-------- | :----------
[close](https://msdn.microsoft.com/library/mt670636) | 表示された通知を閉じます。
[requestPermission](https://msdn.microsoft.com/library/mt710824) | 現在の起点によって通知が表示されるように、ユーザーにアクセス許可を要求します。

## 通知のアクセス許可

Microsoft Edge では、ユーザーが特定の web サイトドメインごとに通知のアクセス許可を管理することができます。 通知を表示するようにドメインによって要求された場合は、ユーザーが [はい] または [いいえ] を選択することができます。 メソッドは、、 [`requestPermission`](https://msdn.microsoft.com/library/mt710824) 、またはのいずれかとしてアクセス許可の状態を通知するために使われ `granted` `denied` `default` ます。 値は、 `default` ユーザーが決定を行っていないことを示します。これは、という値に `denied` なります。




## API リファレンス

[Web 通知](https://msdn.microsoft.com/library/mt710827)

## キャスト

[Web 通知](https://notifications.spec.whatwg.org)
