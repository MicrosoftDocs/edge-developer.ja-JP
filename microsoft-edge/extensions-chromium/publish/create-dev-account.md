---
description: Microsoft Edge のアドオンストアに拡張機能を公開するために、開発者アカウントに登録する方法について説明します。
title: Microsoft Edge 拡張機能の開発者として登録して、拡張機能を公開する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge-chromium
keywords: エッジ-chromium、拡張機能の開発、ブラウザーの拡張機能、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 55f3520526a97ebbd8eeacf1c46f801b94599694
ms.sourcegitcommit: ad5eb43172280974b8c063867c2097f7c5c0e77d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "10898208"
---
# Microsoft Edge 拡張機能の開発者として登録する  

Microsoft Edge アドオンの web サイトに拡張機能を提出するには、[パートナーセンター][MicrosoftPartnerCenter]で microsoft edge プログラムを開発者として登録する必要があります。  Microsoft Edge プログラムへの拡張機能の送信には、登録料金は必要ありません。  

## 始める前に  

アカウントを持っていない場合、またはパートナーセンターで既存の商用アカウントがある場合は、Microsoft Edge プログラムに登録するための新しい[microsoft アカウント (MSA)][WindowsCommunityEverythingAboutMicrosoftAccounts]を作成する必要があります。  Microsoft アカウント (Outlook/live/Hotmail \) を作成するには、 [account.microsoft.com][MicrosoftAccount]にアクセスし、[ **Microsoft アカウントの作成**] を選択します。  開発者アカウントでパートナーセンターに登録されている場合は、対応する Microsoft アカウント \ (MSA \) を使ってサインインし、Microsoft Edge プログラムに登録します。  

> [!NOTE]
> 現在、Microsoft Edge extensions チームは、職場または学校のアカウントにサインアップすることをサポートしていません。  今後、Microsoft Edge extensions チームは、AAD の管理のための MSA アカウントへの AAD テナントのリンクをサポートする予定です。  

## パートナーセンターで Microsoft Edge プログラムに登録する  

1.  [[開発] ページ][MicrosoftPartnerCenter]に移動して、[**ダッシュボードに移動**] を選択します。  
1.  **Microsoft アカウント**でまだサインインしていない場合は、今すぐサインインするか、新しい microsoft アカウントを作成します。  開発者アカウントにサインインするときに使用するのと同じ Microsoft アカウントを使用します。  サインインすると、この登録フォームが表示されます。  
    
    Microsoft Edge プログラムに登録するには、アカウントにサインインして、フォームに入力します。  
    <!-- -->
    :::row:::
       :::column span="1":::
          **取引先企業の国/地域**  
       :::column-end:::
       :::column span="2":::
          このフィールドには、live またはビジネスの所在地が表示されます。  
          
          > [!IMPORTANT]
          > 登録後、このフィールドの値を変更することはできません。  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **アカウントの種類**  
       :::column-end:::
       :::column span="2":::
          [パートナーセンター][MicrosoftPartnerCenter]の Microsoft Edge プログラムでは、個人アカウントと会社のアカウントの両方が提供されます。詳細については、次の表を参照してください。  どちらのアカウントの種類を使用しても、Microsoft Edge のアドオンカタログに拡張機能を公開できます。  
          
          > [!IMPORTANT]
          > 登録後、このフィールドの値を変更することはできません。  
          
          *   `Individual account`  
              個人のアカウントは、会社に関連付けられていない開発者に適しています。  アカウントの確認プロセスは短く、発行元の表示名が利用可能であることを確認する必要があります。  

          *   `Company account`  
              会社のアカウントは、組織またはビジネスと関連付けられています。  アカウントの確認プロセスが長く、会社のアカウントを作成する権限を持っていることを確認する必要があります。  プロセスの期間は数日から数週間までとなる場合があります。  会社では、Microsoft 確認パートナーから電話を受けることができます。  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **発行者の表示名**  
       :::column-end:::
       :::column span="2":::
          このフィールドは、Microsoft Edge のアドオンカタログのユーザーに表示される名前です。  名前は利用可能であり、使用する権限がある場合にのみ使用できます。  会社のアカウントは、組織の登録会社名を使用している必要があります。  
          
          > [!NOTE]
          > このフィールドの最大文字数は50文字です。  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **連絡情報**  
       :::column-end:::
       :::column span="2":::
          このフィールドには、Microsoft がアカウントの問題に関して連絡するために使用する可能性がある連絡先情報が含まれています。  登録が完了すると、メールの確認メッセージが送信されます。  会社のアカウントの場合は、組織に関連付けられている登録済みのメールアドレスを使用する必要があります。  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **会社の承認者**  
       :::column-end:::
       :::column span="2":::
          会社のアカウントの場合、会社の承認者の連絡先情報を入力する必要があります (名前、メールアドレス、電話番号)。  Microsoft は、認証プロセスの一部として指定された会社の承認者として、内線番号が組織に属することを確認します。  
       :::column-end:::
    :::row-end:::  
    <!-- -->
    <!--
    1.  The **Account country/region** field  
        
        This field is where you either live or your business is located.  
        
        > [!IMPORTANT]
        > After enrollment, you are not able to change the value of this field.  
        
    1.  The **Account type** field  
        
        The Microsoft Edge program in [Partner Center][MicrosoftPartnerCenter] offers both individual and company accounts, which are described in detail in the table that follows.  Both account types allow you to publish extensions to the Microsoft Edge add-ons catalog.  
        
        > [!IMPORTANT]
        > After enrollment, you are not able to change the value of this field.  
        
        | Individual account | Company account |  
        |:--- |:--- |  
        | Individual accounts are appropriate for developers not associated with a company.  | Company accounts are associated with organizations and businesses.  |  
        | The account verification process is shorter, and involves verifying that the publisher display name is available.  | The account verification process is longer, and involves confirmation that you are authorized to create the account for your company.  The duration of the process may range from a few days to a few weeks.  Your company may receive phone calls from Microsoft verification partners.  |  
        
    1.  The **Publisher display name** field  
        
        This field is the name shown to users in the Microsoft Edge add-ons catalog.  You may use a name only if it is available, and you have the rights to use it.  Company accounts must use the registered business name of your organization.  
        
        > [!NOTE]
        > The maximum length for this field is 50 characters.  
        
    1.  The **Contact details** field  
        
        Any contact information that Microsoft may use to contact you regarding any account issues.  After registration is complete, an email confirmation is sent to you.  Company accounts must use the registered email address associated with your organization.  
        
    1.  The **Company approver** field  
        
        For company accounts, provide the contact information \(name, email address, and phone number\) of your company approver.  Microsoft contacts the company approver specified as a part of the verification process to ensure that the extensions belong to your organization.  
        -->
1. 登録フォームを送信する前に、 [Microsoft Edge 開発者契約][MicrosoftAppDeveloperAgreement]の条項と条件をお読みいただき、同意してください。  
1. 登録手続きを完了するには、[**完了**] を選択します。  

## 次のステップ  

確認の状態は、パートナーセンターの [**アカウント設定**] ページで確認できます。  確認プロセスが完了するまで待ちます。引き続き申請の構築、テスト、準備を行うことができます。  

詳細については、「[拡張機能を発行する][ExtensionsChromiumPublishExtension]」を参照してください。  拡張機能の使用を開始する方法については、「 [Microsoft Edge (Chromium) 拡張機能の][ExtensionsChromiumGettingStartedIndex]概要」を参照してください。  

<!-- links -->  

[ExtensionsChromiumGettingStartedIndex]: ../getting-started/index.md "Microsoft Edge (Chromium) extensions の概要 |Microsoft ドキュメント"  
[ExtensionsChromiumPublishExtension]:  ./publish-extension.md "拡張子を公開する |Microsoft ドキュメント"  

[MicrosoftAppDeveloperAgreement]:  /legal/windows/agreements/app-developer-agreement "アプリ開発者契約 |Microsoft ドキュメント"  

[MicrosoftAccount]:  https://account.microsoft.com/account "Microsoft アカウント"  

[MicrosoftPartnerCenter]:  https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナーセンター"  

[WindowsCommunityEverythingAboutMicrosoftAccounts]:  https://community.windows.com/stories/everything-you-need-to-know-about-microsoft-accounts "Microsoft (または MSA)"  