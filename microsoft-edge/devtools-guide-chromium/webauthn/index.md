---
description: Microsoft Edge DevTools で Authenticators をエミュレートし、WebAuthn をデバッグします。
title: Microsoft Edge DevTools で認証システムをエミュレートし、WebAuthn をデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3200f22485bfd642a37a7d34ac727b8da4500d06
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231182"
---
# Microsoft Edge DevTools で認証システムをエミュレートし、WebAuthn をデバッグする  

Web サイトまたはアプリで物理認証システムを使用して Web 認証をデバッグする代わりに、Microsoft Edge DevTools の **WebAuthn** ツールを使用して、ソフトウェア ベースの仮想認証システムを作成して操作します。  

## 始める前に  

Web 認証を始めるのに最適な場所は [、Web 認証 API の仕様です][GithubW3cWebauthn]。  

## WebAuthn ツールをセットアップする  

1.  次のデモ Web サイトなど、WebAuthn を使用する Web ページに移動します。  
    
    [webauthndemo.appspot.com][AppspotWebauthndemo]  
    
1.  Web サイトにサインインします。  
1.  [DevTools を開きます][DevtoolsGuideChromiumOpen]。  
1.  **WebAuthn ツールを開**するには **、[DevTools**のカスタマイズと制御] アイコン (\) アイコンを選択し、[その他> WebAuthn ] を `...` ****  >  **クリックします**。  
    
    :::image type="complex" source="../media/webauthn-webauthn-tab.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-webauthn-tab.msft.png":::
       **WebAuthn** ツール  
    :::image-end:::  
    
1.  **WebAuthn ツールで、[** 仮想認証環境を有効**にする] チェック ボックスをオン**にします。  
1.  有効にすると、新しい認証システムという名前の新 **しいセクションが** 表示されます。  
    
    :::image type="complex" source="../media/webauthn-enable-virtual-auth.msft.png" alt-text="仮想認証環境を有効にする" lightbox="../media/webauthn-enable-virtual-auth.msft.png":::
        **仮想認証環境を有効にする**  
    :::image-end:::  
    
1.  [新しい **認証システム] セクション** で、次のオプションを構成します。  
    
    | オプション | 設定値 | 詳細 |  
    |:--- |:--- |:--- |  
    | `Protocol` | [ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] または [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml] | 仮想認証システムがエンコードとデコードに使用するプロトコル |  
    | `Transport` |   `usb``nfc`、 `ble` または `internal` | 仮想認証システムは、特定の資格情報のアサーションを取得するために、クライアントと通信するために選択されたトランスポートをシミュレートします。  詳細については [、「Authenticator Transport Enumeration」に移動します。][GithubW3cWebauthnEnumTransport] |  
    |  `Supports resident keys` | チェック ボックスを使用して \(またはオフ)をオンにする | Web アプリが常駐キー \(クライアント側の検出可能な資格情報\ とも呼ばれる) に依存している場合はオンにします。  詳細については、常駐キー要件列挙 [に移動します][GithubW3cWebauthnEnumResidentkeyrequirement]。 |  
    | `Supports user verification` | チェック ボックスを使用して \(または off\) をオンにする | Web アプリが、タッチとピンコード、パスワード入力、生体認証認識などのジェスチャ モダリティを使用したローカル承認に依存している場合にオンになります。  詳細については、[ユーザーの確認] [に移動します。][GithubW3cWebauthnEnumUserverification] |  
    
1.  [追加] **ボタンを選択** します。  
1.  新しく作成した認証システムの新しいセクションが表示されます。  
    
    :::image type="complex" source="../media/webauthn-authenticator.msft.png" alt-text="Authenticator" lightbox="../media/webauthn-authenticator.msft.png":::
       Authenticator  
    :::image-end:::  
    
**Authenticator セクションには****、Credentials テーブルが含**まれています。  資格情報が認証システムに登録されるまで、テーブルは空です。  

:::image type="complex" source="../media/webauthn-no-cred.msft.png" alt-text="資格情報なし" lightbox="../media/webauthn-no-cred.msft.png":::
   資格情報なし  
:::image-end:::  

## 新しい資格情報を登録する  

新しい資格情報を登録するには、次の手順を実行します。  新しい資格情報を登録するときに [Web 認証 API][GithubW3cWebauthn] が実行する操作の詳細については、「新しい資格情報を作成する [」に移動します][GithubW3cWebauthnSctnCreatecredential]。  

1.  デモ Web サイトで、[新しい資格情報の **登録] を選択します**。  
1.  これで、WebAuthn ツールの **[資格情報** ] テーブルに新しい資格情報が追加されます。  
    
    :::image type="complex" source="../media/webauthn-view-cred.msft.png" alt-text="資格情報を表示する" lightbox="../media/webauthn-view-cred.msft.png":::
       資格情報を表示する  
    :::image-end:::  
    
デモ Web サイトで、[認証] ボタン **を選択** します。  Credentials テーブル内の資格情報の Sign **** [Count][GithubW3cWebauthnSctnSignCounter]が 1 増加し[、authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion]操作が成功したとマークされたことを確認します。  

## 資格情報のエクスポートと削除  

資格情報をエクスポートまたは削除するには、[エクスポート] ボタンまたは [削除 **]** ボタン **を選択** します。  

:::image type="complex" source="../media/webauthn-export-remove.msft.png" alt-text="資格情報をエクスポートまたは削除する" lightbox="../media/webauthn-export-remove.msft.png":::
   資格情報をエクスポートまたは削除する  
:::image-end:::  

## 認証システムの名前を変更する  

認証システムの名前を変更するには、次の手順を実行します。  

1.  認証者名の横にある [編集] ボタン **を選択** します。  
1.  名前を編集し **、Enter** キーを押して変更を保存します。  

:::image type="complex" source="../media/webauthn-rename.msft.png" alt-text="認証システムの名前を変更する" lightbox="../media/webauthn-rename.msft.png":::
   認証システムの名前を変更する  
:::image-end:::  

## アクティブな認証システムを設定する  

新しく作成された認証システムが自動的にアクティブ化されます。  別の仮想認証を使用するには、認証システム **の横にある [アクティブ** ] ラジオ ボタンを選択します。  

> [!NOTE]
> DevTools は、任意の時点で 1 つのアクティブな仮想認証システムのみをサポートします。  アクティブな認証システムを削除すると、別の認証システムが自動的にアクティブ化されません。  

:::image type="complex" source="../media/webauthn-set-active.msft.png" alt-text="アクティブな認証システムを設定する" lightbox="../media/webauthn-set-active.msft.png":::
   アクティブな認証システムを設定する  
:::image-end:::  

## 仮想認証システムを削除する  

仮想認証システムを削除するには、認証者の横にある [削除] ボタン **を選択** します。  

:::image type="complex" source="../media/webauthn-remove-authenticator.msft.png" alt-text="認証システムを削除する" lightbox="../media/webauthn-remove-authenticator.msft.png":::
   認証システムを削除する  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[AppspotWebauthndemo]: https://webauthndemo.appspot.com "Webauthn デモ |Appspot"  

[FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml]: https://fidoalliance.org/specs/fido-v2.0-id-20180227/fido-client-to-authenticator-protocol-v2.0-id-20180227.html "クライアントから Authenticator プロトコル (CTAP) |fido alliance"  
[FidoallianceSpecsU2fV12Ps20170411OverviewHtml]: https://fidoalliance.org/specs/fido-u2f-v1.2-ps-20170411/fido-u2f-overview-v1.2-ps-20170411.html "ユニバーサル 2nd Factor (U2F) の概要 |fido alliance"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |GitHub"  
[GithubW3cWebauthnAuthenticatorgetassertion]: https://w3c.github.io/webauthn#authenticatorgetassertion "authenticatorGetAssertion 操作 - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |GitHub"  
[GithubW3cWebauthnEnumTransport]: https://w3c.github.io/webauthn#enum-transport "Authenticator Transport 列挙 (Enum AuthenticatorTransport) - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |W3C"  
[GithubW3cWebauthnEnumResidentkeyrequirement]: https://w3c.github.io/webauthn#enum-residentKeyRequirement "Resident Key Requirement Enumeration (enum ResidentKeyRequirement) - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |W3C"  
[GithubW3cWebauthnEnumUserverification]: https://w3c.github.io/webauthn#user-verification "ユーザーの確認 - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |W3C"  
[GithubW3cWebauthnSctnCreatecredential]: https://w3c.github.io/webauthn#sctn-createCredential "Create a New Credential - PublicKeyCredential's [Create]](origin, options, sameOriginWithAncestors) Method - Web Authentication: An API for accessing Public Key Credentials Level 2 |GitHub"  
[GithubW3cWebauthnSctnSignCounter]: https://w3c.github.io/webauthn/#sctn-sign-counter "署名カウンターに関する考慮事項 - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |GitHub"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/tools/chrome-devtools/webauthn/index)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
