---
description: このページでは、ユーザー エージェント文字列Microsoft Edgeドキュメントを提供します。
title: Microsoft Edgeユーザー エージェント文字列
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, compatibility, Web プラットフォーム, ユーザー エージェント文字列, ua string, ua overrides
ms.openlocfilehash: 73401219b7708a739292a46b6131fe40765e9c8c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570800"
---
# Microsoft Edgeユーザー エージェント文字列 (デスクトップ)  

ユーザー エージェント \(UA\) 文字列を使用して、特定のオペレーティング システムで使用されている特定のブラウザーのバージョンを検出できます。  他のブラウザーと同様Microsoft Edgeサイトへの要求を行うたびに、HTTP ヘッダーにこの情報 `User-Agent` が含まれます。  また、 の値を照会して JavaScript を介してアクセスすることもできます `navigator.userAgent` 。  

Microsoft では、Web 開発者が可能[](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)な限り機能検出を利用して、コードの保守性を向上し、コードのフラグビリティを低下し、将来の UA 文字列更新が発生した場合にコードが壊れるリスクを排除します。  

機能検出が適用できない場合と UA 検出を使用する必要がある場合、デスクトップ上の UA のMicrosoft Edge形式は次のとおりです。

要求 `User-Agent` ヘッダーの形式は次のとおりです。

```http
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43
``` 

戻り値の `navigator.userAgent` 取得元は次の形式です。

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43"
```  

プラットフォーム識別子は、使用されているオペレーティング システムに基づいて変更され、バージョン番号も時間が経過すると増加します。  この形式は、最後に新Chromium追加した UA の形式 `Edg` と同じです。  Microsoft は、EdgeHTML に基づくバージョンのコードで使用される文字列の使用によって引き起こされる可能性がある互換性の問題を回避Microsoft Edge `Edg` `Edge` トークンを選択しました。  トークン `Edg` は、iOS および Android で [使用される](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/) 既存のトークンと一致しています。

## UA 文字列をブラウザー名にマッピングする
コードで使用するために、UA 文字列トークンを人間が読み取り可能なブラウザー名にマッピングする方法は、今日の Web 上で一般的なパターンです。 新しいトークンをブラウザー名にマッピングする場合、従来のバージョンの Microsoft Edge で使用されている開発者とは異なる名前を使用して、Chromium ベースのブラウザーに適用できない従来の回避策を誤って適用しないようにお勧めします。 `Edg`

## ユーザー エージェントのオーバーライド  

Web サイトが UA の更新されたバージョンを認識Microsoft Edge場合があります。  その結果、その Web サイトの機能のセットが正しく動作しない可能性があります。  Microsoft がこれらの種類の問題について通知を受け取った場合、Web サイトの所有者に連絡し、更新された UA について通知されます。  

多くの場合、サイトでは、Microsoft がサイト所有者に報告する問題に対処するために、UA 検出ロジックを更新してテストする時間が必要です。  このような場合、Microsoft は、これらのサイトにアクセスするユーザーの互換性を最大化するために、ベータ版と安定版のチャネルで UA オーバーライドの一覧を使用します。  オーバーライドでは、特定のサイトの既定の UA Microsoft Edge送信する必要がある新しい UA 値を指定します。  現在適用されている UA オーバーライドの一覧を表示するには、アプリの Beta チャネルと Stable チャネルに `edge://compat/useragent` 移動Microsoft Edge。 

現在、Canary チャネルと Dev チャネルは UA オーバーライドを受け取りないので、Web 開発者は、既定の UA によって発生するサイト上の問題を簡単に再現できる環境Microsoft Edgeしています。  何らかの理由で Microsoft Edge の Beta チャネルまたは Stable チャネルで UA オーバーライドを無効にする機能が必要な場合は、次のコマンド ライン引数を使用して Microsoft Edge 実行可能ファイルを実行できます。  

```shell
--disable-domain-action-user-agent-override
```  
