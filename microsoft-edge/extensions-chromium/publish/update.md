---
description: Microsoft Store の拡張機能更新プロセス。
title: 拡張機能の一覧を更新する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/21/2020
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 67b0eddfa7f8641a0db5a4f7b5693c876dd5e345
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607371"
---
# 拡張機能の一覧を更新する  

Microsoft Edge アドオンカタログで既存の登録情報を更新します (Microsoft Edge アドオン \)。  公開された拡張機能はいつでも変更できます。  更新中は、説明やロゴの更新などの変更を行うために、拡張子全体を更新する必要はありません。  ただし、拡張機能パッケージを更新する場合は、毎回バージョン番号を上げておく必要があります。  

## 既に公開されている拡張機能を更新する  

登録情報を更新するには、次の手順を実行します。  

1.  [開発者ダッシュボード][MicrosoftPartnerCenter]に移動します。  [概要] ページで、更新するリストをクリックします。  これにより、発行中に入力した申請フォームの詳細が表示されます。  
1.  パッケージ、説明、グラフィックアセット、またはその他の設定に必要な変更を加えます。  パッケージファイルを更新する場合は、マニフェストのバージョンが前のパッケージバージョンよりも大きいことを確認してください。
1.  変更を加えたら、[保存]、[発行] の順にクリックします。
1.  [パートナーセンター][MicrosoftPartnerCenter]の開発者ダッシュボードにアクセスして、リストがに変更された状態をに確認し `In the store` `In the store.  Certification in progress` ます。  

> [!NOTE]
> 更新プログラムの公開プロセスの期間は、数時間から数日間に及びます。  

`Status`列が表示されたら `In the store` 、拡張機能の更新プログラムを Microsoft Edge のアドオンで利用できます。  

## 認定手順中に拡張機能を更新する  

公開手順を開始する前に、提出後に拡張機能の申請を編集して更新することができます。  [パートナーセンター][MicrosoftPartnerCenter]のリストに関連付けられている拡張**機能の概要**ページで、拡張機能の状態を確認することができます。  

申請を編集するには、次の手順を実行します。  

1.  [開発者ダッシュボード][MicrosoftPartnerCenter]に移動します。  [**概要**] ページで、更新するリストをクリックします。  これにより、発行中に入力した申請フォームの詳細が表示されます。  
1.  左側のナビゲーションバーに表示されている [**拡張機能の概要**] セクションに移動します。  [**送信のキャンセル**] をクリックして、現在の申請をキャンセルします。  
1.  [その他] セクションに移動し、パッケージ、説明、グラフィックアセット、その他の設定に必要な変更を加えます。  パッケージファイルを更新する場合は、マニフェストのバージョンが前のパッケージバージョンよりも大きいことを確認してください。  
1.  変更を加えたら、[**保存**]、[**発行**] の順にクリックします。  

> [!IMPORTANT]
> このプロセスは、認定パイプラインから現在の申請を停止して削除し、新しいレビューは最新の申請から始まります。  

> [!NOTE]
> 更新プログラムの公開プロセスの期間は、数時間から数日間に及びます。  

`Status`列が表示されたら `In the store` 、拡張機能の更新プログラムを Microsoft Edge のアドオンで利用できます。  

## Microsoft Edge アドオンから拡張機能を削除する  

Microsoft Edge アドオンから拡張機能を削除するには、次の操作を行います。  

1.  [開発者ダッシュボード][MicrosoftPartnerCenter]に移動します。  [**概要**] ページで、削除するリストをクリックします。  
1.  リストの [**拡張機能の概要**] ページを開きます。  
1.  [**非公開**] をクリックします。  これにより、Microsoft Edge アドオンの一覧が unpublishes されます。  

次の手順では、拡張機能を Microsoft Edge アドオンから削除します。これは、新しいユーザーが拡張機能を見つけることも、インストールすることもできないことを意味します。ただし、既に拡張機能をインストールしているユーザーは引き続き使用することができます。  

<!-- image links -->  

<!-- links -->  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナーセンター"  