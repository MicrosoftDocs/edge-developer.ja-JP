---
description: Microsoft Edge DevTools でオーセンティケータをエミュレートし、WebAuthn をデバッグします。
title: Microsoft Edge DevTools でオーセンティケータをエミュレートして、WebAuthn をデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6727e9aeea1a51689a80570a2f1c9df880a8c9db
ms.sourcegitcommit: 6e2b26d41a0aa56ac34e6edc7dddd852ddb415b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2020
ms.locfileid: "11134140"
---
# Microsoft Edge DevTools でオーセンティケータをエミュレートして、WebAuthn をデバッグする  

Web 認証は、web サイトや物理認証を使ったアプリではなく、Microsoft Edge DevTools の **WebAuthn** ツールを使用して、ソフトウェアベースの仮想オーセンティケータを作成し、操作します。  

## 始める前に  

Web 認証を始めるのに最適な場所は、 [Web AUTHENTICATION API の仕様][GithubW3cWebauthn]です。  

## WebAuthn ツールを設定する  

1.  次のデモ web サイトなど、WebAuthn を使用する web ページに移動します。  
    
    [webauthndemo.appspot.com][AppspotWebauthndemo]  
    
1.  Web サイトにサインインします。  
1.  [DevTools を開き][DevtoolsGuideChromiumOpen]ます。  
1.  **Webauthn**ツールを開くには、[**ユーザー設定と制御**のための devtools \ ( `...` \)] アイコン > [**その他のツール**]  >  **WebAuthn**を選びます。  
    
    :::image type="complex" source="../media/webauthn-webauthn-tab.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-webauthn-tab.msft.png":::
       **WebAuthn** ツール  
    :::image-end:::  
    
1.  [ **WebAuthn** ] ツールで、[ **Virtual Authenticator 環境を有効**にする] の横にあるチェックボックスをオンにします。  
1.  有効にすると、新しい [ **authenticator** ] という名前の新しいセクションが表示されます。  
    
    :::image type="complex" source="../media/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-enable-virtual-auth.msft.png":::
        **仮想認証システムを有効にする環境**  
    :::image-end:::  
    
1.  [ **新しい認証** 方法] セクションで、次のオプションを構成します。  
    
    | オプション | 値 | 詳細 |  
    |:--- |:--- |:--- |  
    | `Protocol` | [ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] または [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml] | 仮想化認証でエンコードとデコードに使用されるプロトコル |  
    | `Transport` |   `usb`、 `nfc` 、 `ble` 、または `internal` | 仮想認証は、特定の資格情報のアサーションを取得するために、選択したトランスポートをクライアントと通信するために選択されたトランスポートをシミュレートします。  詳細については、「 [Authenticator トランスポートの列挙][GithubW3cWebauthnEnumTransport]」を参照してください。 |  
    |  `Supports resident keys` | チェックボックスを使用して \ (またはオフ) をオンにする | Web アプリが常駐キー (クライアント側の検出可能な資格情報とも呼ばれます) に依存しているかどうかをオンにします。  詳細については、「 [常駐キーの要件の列挙][GithubW3cWebauthnEnumResidentkeyrequirement]」を参照してください。 |  
    | `Supports user verification` | チェックボックスを使用して \ (またはオフ) をオンにする | Web アプリが、タッチ plus pin コード、パスワード入力、バイオメトリクス認識などのジェスチャモダリティを使用したローカル承認に依存しているかどうかをオンにします。  詳細については、「[ユーザーの確認][GithubW3cWebauthnEnumUserverification]」に移動します。 |  
    
1.  [ **追加** ] ボタンを選択します。  
1.  新しく作成されたオーセンティケータの新しいセクションが表示されます。  
    
    :::image type="complex" source="../media/webauthn-authenticator.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-authenticator.msft.png":::
       アプリ  
    :::image-end:::  
    
[ **認証** 情報] セクションには、 **資格情報** テーブルが含まれます。  資格情報がオーセンティケータに登録されるまで、この表は空になっています。  

:::image type="complex" source="../media/webauthn-no-cred.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-no-cred.msft.png":::
   資格情報なし  
:::image-end:::  

## 新しい資格情報を登録する  

新しい資格情報を登録するには、次の手順を実行します。  新しい資格情報を登録するときの [Web 認証 API][GithubW3cWebauthn] の動作の詳細については、「 [新しい資格情報を作成][GithubW3cWebauthnSctnCreatecredential]する」を参照してください。  

1.  デモ web サイトで、[ **新しい資格情報の登録**] を選びます。  
1.  新しい資格情報が、WebAuthn ツールの **Credentials** テーブルに追加されました。  
    
    :::image type="complex" source="../media/webauthn-view-cred.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-view-cred.msft.png":::
       資格情報の表示  
    :::image-end:::  
    
デモ web サイトで、[ **認証** ] ボタンを選択します。  **資格情報**テーブルの資格情報の[符号カウント][GithubW3cWebauthnSctnSignCounter]が1で増加したことを確認します。これは、 [authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion]操作が成功したことを示します。  

## 資格情報のエクスポートと削除  

資格情報をエクスポートまたは削除するには、[ **エクスポート** ] または [ **削除** ] ボタンを選択します。  

:::image type="complex" source="../media/webauthn-export-remove.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-export-remove.msft.png":::
   資格情報をエクスポートまたは削除する  
:::image-end:::  

## オーセンティケータの名前を変更する  

オーセンティケータの名前を変更するには、次の手順を実行します。  

1.  オーセンティケータ名の横にある「 **編集** 」ボタンを選択します。  
1.  名前を編集してから、[ **enter** ] を選んで変更を保存します。  

:::image type="complex" source="../media/webauthn-rename.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-rename.msft.png":::
   オーセンティケータの名前を変更する  
:::image-end:::  

## アクティブな認証システムを設定する  

新しく作成されたオーセンティケータは、自動的に有効になります。  別の仮想オーセンティケータを使用するには、オーセンティケータの横にある「 **アクティブ** 」ラジオボタンを選択します。  

> [!NOTE]
> DevTools は、任意の時点でアクティブな仮想オーセンティケータを1つだけサポートします。  アクティブなオーセンティケータを削除した場合、別のオーセンティケータは自動的にアクティブ化されません。  

:::image type="complex" source="../media/webauthn-set-active.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-set-active.msft.png":::
   アクティブな認証システムを設定する  
:::image-end:::  

## 仮想認証を削除する  

仮想オーセンティケータを削除するには、オーセンティケータの横にある「 **削除** 」ボタンを選択します。  

:::image type="complex" source="../media/webauthn-remove-authenticator.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-remove-authenticator.msft.png":::
   オーセンティケータを削除する  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

[AppspotWebauthndemo]: https://webauthndemo.appspot.com "Webauthn デモ |Appspot"  

[FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml]: https://fidoalliance.org/specs/fido-v2.0-id-20180227/fido-client-to-authenticator-protocol-v2.0-id-20180227.html "クライアントから Authenticator へのプロトコル (CTAP) |fido アライアンス"  
[FidoallianceSpecsU2fV12Ps20170411OverviewHtml]: https://fidoalliance.org/specs/fido-u2f-v1.2-ps-20170411/fido-u2f-overview-v1.2-ps-20170411.html "ユニバーサル2要素 (U2F) の概要 |fido アライアンス"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 認証: 公開キーの資格情報レベル2にアクセスするための APIGitHub"  
[GithubW3cWebauthnAuthenticatorgetassertion]: https://w3c.github.io/webauthn#authenticatorgetassertion "AuthenticatorGetAssertion 操作-Web 認証: 公開キーの資格情報レベル2にアクセスするための APIGitHub"  
[GithubW3cWebauthnEnumTransport]: https://w3c.github.io/webauthn#enum-transport "Authenticator トランスポート列挙型 (enum authentication Atortransport)-Web 認証: 公開キー資格情報レベル2にアクセスするための API勧告"  
[GithubW3cWebauthnEnumResidentkeyrequirement]: https://w3c.github.io/webauthn#enum-residentKeyRequirement "常駐キー要件の列挙型 (enum ResidentKeyRequirement)-Web 認証: 公開キーの資格情報レベル2にアクセスするための API勧告"  
[GithubW3cWebauthnEnumUserverification]: https://w3c.github.io/webauthn#user-verification "ユーザー確認-Web 認証: 公開キーの資格情報レベル2にアクセスするための API勧告"  
[GithubW3cWebauthnSctnCreatecredential]: https://w3c.github.io/webauthn#sctn-createCredential "新しい資格情報-PublicKeyCredential の [[作成]] (オリジン、オプション、Sameorigin With祖先) メソッド-Web 認証: 公開キーの資格情報レベル2にアクセスするための APIGitHub"  
[GithubW3cWebauthnSctnSignCounter]: https://w3c.github.io/webauthn/#sctn-sign-counter "署名カウンターに関する考慮事項-Web 認証: 公開キーの資格情報レベル2にアクセスするための APIGitHub"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/webauthn/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
