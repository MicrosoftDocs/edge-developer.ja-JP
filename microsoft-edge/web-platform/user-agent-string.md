---
description: このページでは、Microsoft Edge ユーザーエージェント文字列に関するドキュメントを提供します。
title: Microsoft Edge ユーザーエージェント文字列
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム、ユーザーエージェント文字列、ua 文字列、ua の上書き
ms.openlocfilehash: 73401219b7708a739292a46b6131fe40765e9c8c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570800"
---
# Microsoft Edge ユーザーエージェント文字列 (デスクトップ)  

ユーザーエージェント \ (UA \) 文字列は、特定のオペレーティングシステムで使用されている特定のブラウザーのバージョンを検出するために使用できます。  他のブラウザーと同じように、Microsoft Edge で `User-Agent` は、サイトへの要求を行うたびに、HTTP ヘッダーにこの情報が記載されています。  また、の値を照会して、JavaScript を使ってアクセスすることもでき `navigator.userAgent` ます。  

Microsoft は、web 開発者が可能な限り[機能検出](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)を利用して、コードの保守性を向上させ、コードの fragility を減らし、将来の UA 文字列更新が発生した場合に、コード売り上げ高からのリスクを排除することをお勧めします。  

機能の検出が適用されず、UA 検出を使う必要がある場合は、デスクトップの Microsoft Edge UA の形式は次のようになります。

`User-Agent`要求ヘッダーは、次の形式になっています。

```http
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43
``` 

戻り値は、 `navigator.userAgent` 次の形式になります。

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43"
```  

プラットフォーム識別子は、使用されているオペレーティングシステムに基づいて変更されます。また、バージョン番号は、時間の経過に応じて増加します。  この形式は、最後に新しいトークンが追加された Chromium UA と同じです `Edg` 。  Microsoft は、 `Edg` `Edge` EdgeHTML に基づく Microsoft Edge のバージョンによって使用される文字列を使用して発生する可能性のある互換性の問題を回避するために、トークンを選択しました。  `Edg`トークンは、iOS および Android で使用される[既存のトークン](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/)とも整合性があります。

## ブラウザー名への UA 文字列のマッピング
コードで使うために、よりわかりやすいブラウザー名に UA 文字列トークンをマッピングすることは、今日の web 上の一般的なパターンです。 新しい `Edg` トークンをブラウザー名にマッピングする場合、Chromium ベースのブラウザーに適用されない従来の回避策が誤って適用されないように、旧バージョンの Microsoft Edge に使用されている開発者とは異なる名前を使用することをお勧めします。

## ユーザーエージェントの上書き  

場合によっては、更新された Microsoft Edge UA のバージョンが web サイトで認識されないことがあります。  その結果、その web サイトの一連の機能が正しく動作しないことがあります。  Microsoft がこのような種類の問題について通知を受けると、web サイトの所有者に連絡し、更新された UA について通知されます。  

多くの場合、このサイトでは、UA 検出ロジックの更新とテストを行って、Microsoft からサイト所有者に報告される問題に対処する必要があります。  このような場合、Microsoft はベータおよび安定したチャネルでの UA の上書きの一覧を使って、これらのサイトにアクセスするユーザーに対して互換性を最大限に高めています。  この上書きによって、特定のサイトの既定の UA の代わりに Microsoft Edge が送信する新しい UA 値が指定されます。  `edge://compat/useragent`Microsoft Edge のベータ版と安定したチャネルに移動して、現在適用されている UA の上書きの一覧を表示することができます。 

現時点では、Microsoft Edge の既定の UA によって発生した問題について、web 開発者が自分のサイトで問題を簡単に再現できる環境を提供しています。  何らかの理由で Microsoft Edge のベータまたは安定したチャネルでの UA の上書きを無効にする必要がある場合は、次のコマンドライン引数を使用して Microsoft Edge 実行可能ファイルを実行できます。  

```shell
--disable-domain-action-user-agent-override
```  
