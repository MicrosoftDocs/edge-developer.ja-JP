---
ms.assetid: 88825563-5f5d-421d-861b-7cec01277dec
description: Web 認証 API を使用して Web アプリケーションで Windows Hello と FIDO2 をユーザー認証に使用する方法について説明します。
title: Web 認証 - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 07f1de47156f43ff4726e8907a123c2cb1afc337
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234616"
---
# Web 認証と Windows Hello  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge の Web 認証 [API](https://w3c.github.io/webauthn) を使用すると、Web アプリケーションはユーザー認証に [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) デバイスと外部 [FIDO2](https://fidoalliance.org/fido2) デバイスを使用できます。これにより、ユーザーはパスワードの推測、フィッシング、キー ログ攻撃など、パスワード管理の面倒やリスクを回避できます。  現在の Microsoft Edge の実装は、Web 認証仕様の推奨候補に基づいて行います。  

> [!IMPORTANT]
> このトピックでは、Microsoft Edge で Windows Hello 認証と FIDO2 認証を試す方法について説明します。  

Web 認証を使用すると、サーバーはプレーンテキストのチャレンジをブラウザーに送信します。  Microsoft Edge が Windows Hello または外部 FIDO2 デバイスを介してユーザーを確認できると、システムは以前にこのユーザーにプロビジョニングされたプライベート キーを使用してチャレンジに署名し、署名をサーバーに送り返します。  サーバーが、そのユーザーに対して持っている公開キーを使用して署名を検証し、チャレンジが正しいと確認できる場合は、ユーザーを安全に認証できます。  このような [非対称暗号化](https://en.wikipedia.org/wiki/Public-key_cryptography) では、公開キーはそれ自身に意味を持たなく、公開キーは共有されるのを一度も行う必要はありません。  さらに、TPM が有効なハードウェアを備え、セキュリティで保護された要素や最新のシステムから、プライベート キーを移動することはできません。  

Web 認証 API を使用するには、次の 2 つの基本的な手順があります。  

1.  ユーザーを登録する `create`  
1.  ユーザーを認証する `get`  

次の開発ガイドでは [、WebAuthn](https://github.com/MicrosoftEdge/webauthnsample)サンプル アプリを使用してこのフローについて説明します。  

## ユーザーを登録する  

ID プロバイダーとして機能するには、まず、メソッドを使用してユーザーの Web 認証資格情報を作成する必要 `navigator.credentials.create` があります。  サーバー上のユーザーに資格情報を登録する前に、ユーザーの ID を確認する必要があります。  これは、ユーザーに電子メールの確認を送信するか、従来のログイン方法を使用してユーザーに要求することで行えます。  

この `create` メソッドは、次のパラメーターを受け取ります。  

:::row:::
   :::column span="1":::
      **証明書利用者情報**  
   :::column-end:::
   :::column span="3":::
      ```javascript
      rp: {
          name: "WebAuthn Sample App",
          icon: "https://example.com/rpIcon.png"
      },
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ユーザー アカウント情報**  
   :::column-end:::
   :::column span="3":::
      ```javascript
      user: {
          id: stringToArrayBuffer("some.user.id"),
          name: "bob.smith@contoso.com",
          displayName: "Bob Smith",
          icon: "https://example.com/userIcon.png"
      },
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **crypto パラメーター**  
   :::column-end:::
   :::column span="3":::
      ```javascript
      pubKeyCredParams: [
          {
              //External authenticators support the ES256 algorithm
              type: "public-key",
              alg: -7                 
          }, 
          {
              //Windows Hello supports the RS256 algorithm
              type: "public-key",
              alg: -257
          }
      ],
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **authenticator の選択パラメーター**  
   :::column-end:::
   :::column span="3":::
      ```javascript
      authenticatorSelection: {
          //Select authenticators that support username-less flows
          requireResidentKey: true,
          //Select authenticators that have a second factor (such as PIN, Bio)
          userVerification: "required",
          //Selects between bound or detachable authenticators
          authenticatorAttachment: "platform"
      },
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **その他のオプション**  
   :::column-end:::
   :::column span="3":::
      ```javascript
      //Select larger timeout values, as Microsoft Edge shows UI
      timeout: 50000,
      //an opaque challenge that the authenticator signs over
      challenge: challenge,
      //prevent re-registration by specifying existing credentials here
      excludeCredentials: [],
      //specifies whether you need an attestation statement
      attestation: "none" 
      ```  
   :::column-end:::
:::row-end:::  

資格情報の作成 [パラメーターを使用して](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) 、作成する資格情報を構成できます。  特に、Windows Hello の資格情報を作成するには、次の値に設定するか、外部 FIDO2 デバイスでローミング資格情報を `authenticatorAttachment` `platform` 作成 `authenticatorAttachment` します `cross-platform` 。  

このメソッドを使用すると、Microsoft Edge は最初に、顔や指紋をスキャンしたり、PIN を入力したり、外部の FIDO2 デバイスでアクションを実行したりして、ユーザーにプレゼンスの確認を求めるメッセージを表示します。 `create`  この手順が完了すると、認証者は公開主キーペアを生成し、そのキーを保存します。  これらの資格情報は、認証デバイスに安全に保存されるので、作成元ごとにアカウントごとに作成され、抽出できません。  

結果の promise は、新しい資格情報 [を表す](https://w3c.github.io/webauthn#sctn-attestation) 構成証明オブジェクトを返します。  構成証明オブジェクトには、資格情報の公開キーが含まれている。  将来の認証を検証するために、このオブジェクトをサーバーに送信します。  サーバーに送り返す前に、base64 で生データをエンコードする必要があります。  

**クライアント**  

```javascript
<script>
    navigator.credentials.create({
        publicKey: createCredentialOptions
    }).then(rawAttestation => {
        var attestation = {
            id: base64encode(rawAttestation.rawId),
            clientDataJSON: arrayBufferToString(rawAttestation.response.clientDataJSON),
            attestationObject: base64encode(rawAttestation.response.attestationObject)
        };
        return rest_put("/credentials", attestation);
    })
</script>
```  

サーバーは、構成証明オブジェクトをデコードし、検証手順を実行し、この資格情報の公開キーを抽出して、将来の認証のために保存する必要があります。  手順の詳細な一覧は、WebAuthn 仕様の資格情報登録 [アルゴリズム](https://w3c.github.io/webauthn#registering-a-new-credential) で確認できます。  

**Server**  

```javascript
    attestationObject = cbor.decodeFirstSync(Buffer.from(attestation.attestationObject, 'base64'));
    authenticatorData = parseAuthenticatorData(attestationObject.authData);
    var credential = await storage.Credentials.create({
        id: authenticatorData.attestedCredentialData.credentialId.toString('base64'),
        publicKeyJwk: authenticatorData.attestedCredentialData.publicKeyJwk,
        signCount: authenticatorData.signCount
    });
```  

## ユーザーを認証する  

クライアントで資格情報が作成されると、次回ユーザーがサイトにログインしようとして、パスワードの代わりに Web 認証資格情報を使用してサインインして呼び出しを実行できます `navigator.credentials.get` 。  

この `get` メソッドは、唯一の必須パラメーターとしてチャレンジを受け取ります。  課題は、サーバーがクライアントに送信してユーザーのプライベート キーで署名する、不透明なバイト シーケンスです。  次に、例を示します。  

**Server**  

```javascript
    var jwt = require('jsonwebtoken');
    var jwt_secret = "defaultsecret";
    fido.getChallenge = () => {
        return jwt.sign({}, jwt_secret, {
            expiresIn: 120 * 1000
        });
    };
```  

サーバーからチャレンジを取得した後、資格情報要求オプションと共に get API [を呼び出します](https://w3c.github.io/webauthn#credentialrequestoptions-extension)。  Microsoft Edge には、Windows Hello または外部 FIDO2 デバイスを使用しているユーザーの ID を確認するプロンプトが表示されます。  ユーザーが確認された後、チャレンジは TPM または FIDO2 デバイス内で署名され、Promise は、[](https://w3c.github.io/webauthn#authenticatorassertionresponse)サーバーに送信する署名と他のメタデータを含むアサーション オブジェクトで戻されます。  

**クライアント**  

```javascript
    var credentialRequestOptions = {
        //specifies which credential IDs are allowed to authenticate the user
        //if empty, any credential can authenticate the users
        allowCredentials: allowCredentials,
        //an opaque challenge that the authenticator signs over
        challenge: challenge,
        //Select larger timeout values, as Microsoft Edge shows UI
        timeout: 50000
    };

    navigator.credentials.get({
        publicKey: credentialRequestOptions
    }).then(rawAssertion => {
        var assertion = {
            id: base64encode(rawAssertion.rawId),
            clientDataJSON: arrayBufferToString(rawAssertion.response.clientDataJSON),
            userHandle: base64encode(rawAssertion.response.userHandle),
            signature: base64encode(rawAssertion.response.signature),
            authenticatorData: base64encode(rawAssertion.response.authenticatorData)
        };
        return rest_put("/assertion", assertion);
    })
```  

サーバーでアサーションを受け取った後、ユーザーを認証するために署名を検証する必要があります。  サンプル コードを次に示します。  手順の詳細な一覧は、WebAuthn 仕様の [アサーション検証アルゴリズム](https://w3c.github.io/webauthn#verifying-assertion) に記載されています。  

**Server**  

```javascript
    var jwkToPem = require('jwk-to-pem')
    var crypto = require('crypto');

    ...

    // Using credential’s id attribute, look up the corresponding 
    // credential public key.
    var credential = await storage.Credentials.findOne({
        id: assertion.id
    });

    //Refer to sample to see how to verify client data and authenticator data

    ...

    //Using the credential public key from lookup, verify that sig is a valid
    //signature over the binary concatenation of authData and hash.
    var publicKey = credential.publicKeyJwk;
    var verify = (publicKey.kty === "RSA") ? crypto.createVerify('RSA-SHA256') : crypto.createVerify('sha256');
    verify.update(authData);
    verify.update(hash);
    if (!verify.verify(jwkToPem(publicKey), sig))
        throw new Error("Could not verify signature");

    //Verify signCount has increased or is zero 
    if (authenticatorData.signCount != 0 &&
        authenticatorData.signCount < credential.signCount) {
        throw new Error("Received signCount of " + authenticatorData.signCount +
            " expected signCount > " + credential.signCount);
    }
```  

## 実装上の注意  

### サポートされているプラットフォーム  

*   Web 認証 API の候補推奨バージョンは、EdgeHTML 18 \(Windows Insider Preview バージョン 17713 以降\) で始まる Microsoft Edge から使用できます。  
*   プレフィックス [付きプレビュー バージョンの](https://blogs.windows.com/msedgedev/2016/04/12) Web 認証 API は削除され、使用できなくなりました。  
*   Web 認証 API は、UWP アプリと PAS ではまだ利用できません。  
*   Internet Explorer、Web 認証 API はサポートされていません。  

### サポートされている認証システム  

Microsoft Edge の Web 認証 API を使用すると、次のテクノロジを使用してユーザーを認証できます。  

*   **Windows Hello**  顔認証、指紋認証、または PIN によるパスワードレスオンデバイス認証を有効にする  
*   **FIDO2**  リムーバブル デバイスと指紋または PIN によるパスワードレス ローミング認証を有効にします。  
*   **U2F**  パスワードレス モデルに移行する準備ができていない Web サイトに対して、強力な第 2 要素認証を有効にします。  

### Windows Hello に関する特別な考慮事項  

Windows Hello 認証システムを使用する場合の注意点は次の通りです。  

*   API を呼び出して、PC で Windows Hello が利用可能な場合に検出 `isUserVerifyingPlatformAuthenticatorAvailable` できます。  この API の詳細については、こちらを参照 [してください](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable)。  
*   Windows Hello の資格情報を作成する場合は、最適なユーザー エクスペリエンス `authenticatorAttachment` `platform` を提供するために設定する必要があります。
*   Windows Hello は、公開キー アルゴリズムとして RS256 \(alg -257\) のみをサポートしています。  資格情報を作成する場合は、必ずこのアルゴリズムを指定してください。  
*   TPM 構成証明 [ステートメントを受信するには](https://w3c.github.io/webauthn#tpm-attestation)、API を呼び出す際に構成証明を "ダイレクト" に設定 `create` します。  TPM の構成証明は最善の取り組みです。  TPM 2.0 を備える PC だけが TPM 構成証明ステートメントを返し、構成証明プロセスはさまざまな理由で失敗する可能性があります。  
*   Windows Hello では、ユーザーの資格情報を保護するさまざまな方法が採用されています。  資格情報の作成時に返される構成証明オブジェクトの [AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) フィールドを使用して、資格情報の保護に使用されたメソッドを確認できます。  Windows Hello が返す AAGUID の一覧を次に示します。   
    *   ソフトウェア バックアップ認証  
        *   Windows Hello ソフトウェア認証システム:  `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`  
        *   Windows Hello VBS ソフトウェア認証システム:  `6E96969E-A5CF-4AAD-9B56-305FE6C82795`  
    *   トラステッド プラットフォーム モジュール \(TPM\) ベースの認証システム  
        *   Windows Hello ハードウェア認証システム:  `08987058-CADC-4B81-B6E1-30DE50DCBE96`  
        *   Windows Hello VBS ハードウェア認証システム:  `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`  

### API サーフェス  

*   Microsoft Edge には、主要な Web 認証仕様の候補推奨バージョンの完全な実装があります。  
*   [AppID 拡張機能](https://w3c.github.io/webauthn#sctn-appid-extension)がサポートされています。  
*   他の拡張機能はサポートされていません。  

## デモ  

[クライアントとサーバーのコード サンプル](https://github.com/MicrosoftEdge/webauthnsample)  

[Windows Hello テスト ドライブのデモ](https://webauthnsample.azurewebsites.net)  

## 仕様  

[Web 認証: 公開キー資格情報にアクセスするための API](http://w3c.github.io/webauthn)  
