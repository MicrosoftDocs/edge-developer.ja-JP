---
description: 開発者アカウントに登録して、Microsoft Edge アドオン ストアに拡張機能を公開する方法について説明します。
title: Microsoft Edge 拡張機能開発者として登録して拡張機能を公開する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/05/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 8277390bb78e6692345e9c30ef26f60528655374
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327520"
---
# Microsoft Edge 拡張機能開発者として登録する  

拡張機能を Microsoft Edge アドオン カタログに提出するには、Microsoft Edge プログラムに開発者として登録する必要があります。  Microsoft Edge プログラムは、パートナー センター [にあります][MicrosoftPartnerCenter]。  

> [!IMPORTANT]
> Microsoft Edge プログラムに拡張機能を提出する際に必要な登録料はありません。  

## 始める前に  

アカウントを持たなかったり、パートナー センターで既存の商用アカウントを持っている場合は、Microsoft Edge プログラムに登録する新しい Microsoft アカウント [(MSA)][WindowsCommunityEverythingAboutMicrosoftAccounts] を作成します。  Microsoft アカウント \(Outlook/live/Hotmail\) を作成するには、次の操作を実行します。  

1.  に移動[account.microsoft.com。][MicrosoftAccount]  
1.  Choose **Create a Microsoft account**.  
    
パートナー センターに登録されている開発者アカウントがある場合は、対応する Microsoft アカウント \(MSA\) を使用して開発者アカウントにサインインし、Microsoft Edge プログラムに登録します。  

> [!NOTE]
> 現在、Microsoft Edge の拡張機能は、仕事や学校のアカウントでのサインアップをサポートしません。  将来、Microsoft Edge の拡張機能チームは、Azure ADテナントと拡張機能管理用の MSA アカウントのリンクをサポートする予定です。  

## パートナー センターで Microsoft Edge プログラムに登録する  

1.  開発者ページに [移動し、[ダッシュボードに][MicrosoftPartnerCenter] 移動 **] を選択します**。  
1.  Microsoft アカウントをお持ちの場合は、今すぐサインインします。  作成されていない場合は、新しい Microsoft アカウントを作成します。  開発者アカウントへのサインインに使用するのと同じ Microsoft アカウントを使用します。  サインインすると、登録フォームが表示されます。 次の表では、登録フォームのフィールドについて説明します。  
    
    Microsoft Edge プログラムに登録するには、アカウントにサインインし、フォームに入力します。  
    
    :::row:::
       :::column span="1":::
          **アカウントの国/地域**  
       :::column-end:::
       :::column span="2":::
          このフィールドは、ユーザーが住んでいる場所か、ビジネスの場所です。  
          
          > [!IMPORTANT]
          > 登録後、このフィールドの値は読み取り専用になります。  
          
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **アカウントの種類**  
       :::column-end:::
       :::column span="2":::
          パートナー センターの Microsoft Edge プログラム [では、個人][MicrosoftPartnerCenter] アカウントと会社アカウントの両方が提供されます。  アカウントの詳細については、次の箇条書きで説明します。  どちらのアカウントの種類でも、Microsoft Edge アドオン カタログに拡張機能を公開できます。  
          
          > [!IMPORTANT]
          > 登録後は、このフィールドの値を変更できます。  
          
          *   `Individual account`  
              個人アカウントは、会社に関連付けされていない開発者に適しています。  アカウント検証プロセスは短く、発行元の表示名が使用可能なか確認する必要があります。  

          *   `Company account`  
              会社のアカウントは、組織または企業に関連付けられている。  アカウントの検証プロセスは長く、会社のアカウントを作成する権限を持っているという確認が含まれる。  プロセスの期間は、数日から数週間までです。  会社が Microsoft 検証パートナーから電話を受ける場合があります。  
              
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **発行元の表示名**  
       :::column-end:::
       :::column span="2":::
          このフィールドには、Microsoft Edge アドオン カタログに表示される名前が含まれる。  使用できる名前と、その名前を使用する権限がある場合にのみ使用できます。  会社のアカウントは、組織の登録された会社名を使用する必要があります。  
          
          > [!NOTE]
          > このフィールドの最大長は 50 文字です。  
          
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **連絡情報**  
       :::column-end:::
       :::column span="2":::
          このフィールドには、アカウントの問題について Microsoft から連絡を受け取る連絡先情報が含されます。  登録が完了すると、確認メールが送信されます。  会社のアカウントの場合は、組織に関連付けられている登録済みの電子メール アドレスを使用する必要があります。  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **会社の承認者**  
       :::column-end:::
       :::column span="2":::
          会社のアカウントの場合は、会社の承認者の連絡先情報を入力する必要があります。  連絡先情報には、名前、メール アドレス、電話番号が含まれます。  Microsoft は、認証プロセスの一部として指定されている会社の承認者に連絡し、拡張機能が組織に属している必要があります。  
       :::column-end:::
    :::row-end:::  
    
1.  登録フォームを提出する前に [、Microsoft Edge][MicrosoftAppDeveloperAgreement]開発者契約の使用条件を読んで同意してください。  
1.  登録を完了するには、[完了] を **選択します**。  
    
## 次の手順  

確認の状態を表示するには、パートナー センターの [アカウント設定] > **移動します**。  検証プロセスが完了するのを待っている間は、引き続き申請のビルド、テスト、準備を行います。  

詳細については、「拡張機能を公開 [する」に移動します][ExtensionsChromiumPublishExtension]。  拡張機能の使用を開始する方法については [、「Microsoft Edge (Chromium)][ExtensionsChromiumGettingStartedIndex]拡張機能の使用を開始する」に移動してください。  

<!-- links -->  

[ExtensionsChromiumGettingStartedIndex]: ../getting-started/index.md "Microsoft Edge (Chromium) 拡張機能の|Microsoft Docs"  
[ExtensionsChromiumPublishExtension]:  ./publish-extension.md "拡張機能を公開|Microsoft Docs"  

[MicrosoftAppDeveloperAgreement]:  /legal/windows/agreements/app-developer-agreement "アプリ開発者契約|Microsoft Docs"  

[MicrosoftAccount]:  https://account.microsoft.com/account "Microsoft アカウント"  

[MicrosoftPartnerCenter]:  https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナー センター"  

[WindowsCommunityEverythingAboutMicrosoftAccounts]:  https://community.windows.com/stories/everything-you-need-to-know-about-microsoft-accounts "Microsoft アカウントについて知る必要がある|Windows コミュニティ"  
