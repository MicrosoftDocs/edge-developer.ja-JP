---
ms.assetid: 88825563-5f5d-421d-861b-7cec01277dec
description: Web 認証 API で Web アプリケーションで、ユーザー認証で Windows Hello と FIDO2 を使用できるようにする方法について説明します。
title: Web 認証 - デベロッパー ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: b8ff3769434c17b5508978c64b5d9c14e7e3bdaa
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941819"
---
# Web 認証と Windows Hello  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge [の Web Authentication API](https://w3c.github.io/webauthn) を使用すると、Web アプリケーションで [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) および [外部の FIDO2](https://fidoalliance.org/fido2) デバイスを使用できるため、パスワードの成功、フィッシング、キー ログ記録アタックの課金など、パスワード管理のあらかじめ、すべてのパスワード管理にパスワード管理のリスクが含まれます。  現在の Microsoft Edge の実装は、Web 認証固有の推奨事項に基づいています。  

> [!IMPORTANT]
> このトピックでは、Microsoft Edge で Windows Hello と FIDO2 の認証を試す方法について説明します。  

Web 認証を使用すると、サーバーはテキスト形式の問題をブラウザーに送信します。  Microsoft Edge が Windows Hello または外部 FIDO2 デバイスを通じてユーザーを確認できるようになりました。システムは、以前にプロビジョニングしたプライベート キーで課金され、署名はサーバーに送られます。  サーバーがそのユーザー用の公開キーを使用して署名を検証し、チャレンジが正しいことを確認できる場合は、ユーザーを正しく認証できます。  こ [のような、アイモリティックの同時](https://en.wikipedia.org/wiki/Public-key_cryptography) 実行を使用すると、公開キーが独自に有効でない意味であり、主キーは共有されません。  さらに、TPM 対応のハードウェアを使用して、セキュリティで保護された要素や最新のシステムから、主キーを移動することはできません。  

Web 認証 API を使用するには、基本的な手順が 2 つ用いらします。  

1.  ユーザーを登録する `create`  
1.  ユーザーを認証する `get`  

次のデベロッパー ガイドでは [、WebAuthn サ](https://github.com/MicrosoftEdge/webauthnsample)ンプル アプリを使用してこのフローを説明します。  

## ユーザーを登録する  

ID プロバイダーとして実行する場合、まず、方法を使用してユーザーの Web 認証資デベロッシュ割り当てを作成する必要 `navigator.credentials.create` があります。  サーバー上のユーザーに資産情報を登録する前に、ユーザーの ID を確認する必要があります。  これは、ユーザーに確認メールで確認を送信するか、従用のログイン方法を使用することを求めて行います。  

メソ `create` ッドは次のパラメーターを実行します。  

:::row:::
   :::column span="1":::
      **relying party information**  
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
      **認証パラメーター**  
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

資情報 [作成パラメーターを使用](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) して、作成する資情報を構成できます。  この場合、設定して外部 FIDO2 デバイスで Windows Hello の資金情報を作成 `authenticatorAttachment` するか、外部の FIDO2 デバイス上でローミング資デ情報を設定することを `platform` `authenticatorAttachment` 選択できます `cross-platform` 。  

この方法を使用すると、最初に Microsoft Edge からユーザーに対して顔または指紋をスキャンするか、PIN を入力するか、外部 FIDO2 デバイスで操作を実行することをユーザーに求 `create` められます。  この手順を完了すると、認証者が公開キー ペアを生成し、主キーを格納します。  これらの資人情報は、元のアカウント別に作成され、認証デバイスに保存されているため、取り出すことはできません。  

結果の確率は、新しい資情報[attestation object](https://w3c.github.io/webauthn#sctn-attestation)を表す属性オブジェクトを返します。  属性オブジェクトには、資情報の公開キーが含まれている。  以降の認証を検証するため、このオブジェクトをサーバーに送信します。  サーバーに戻る前に、生データをベースにして、元のデータをベースにしておく必要があります。  

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

次に、サーバーは、接続テスト オブジェクトをデコードし、認証手順を実行し、この資ートの公開キーを削除し、以降の認証用に格納する必要があります。  WebAuthn の指定の資格情報登録アルゴ [リズ](https://w3c.github.io/webauthn#registering-a-new-credential) ムに記入して詳細な手順の一覧を見つけます。  

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

クライアントに資ーデンシャルが作成されると、次回ユーザーがサイトにログインしながら、ユーザーがサイトにログインしなくても、パスワードの代わりに Web 認証資デンシャルを使用してサインインできるようになります `navigator.credentials.get` 。  

この `get` メソッドは、必須のパラメーターのみのチャレンジを取り上げられます。  チャレンジとは、サーバーがクライアントに送信してユーザーのプライベート キーでサインインする操作の操作に使用するバイトです。  次に、例を示します。  

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

サーバーからチャレンジを取得した後、API と資格情報要求オプションを [呼び出します](https://w3c.github.io/webauthn#credentialrequestoptions-extension)。  Microsoft Edge に、Windows Hello または外付け FIDO2 デバイスを使用してユーザーの ID を確認するプロンプトが表示されます。  ユーザーが確認されると、TPM または FIDO2 デバイス内でチャレンジが付けられます。確率は、サーバーに送信する署名などの[assertion object](https://w3c.github.io/webauthn#authenticatorassertionresponse)メタデータを含むアサーション オブジェクトとともに返されます。  

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

サーバーでアシスタリングを受信したら、署名を検証してユーザーを認証する必要があります。  次に、コードの例を示します。  WebAuthn の指定のアサーションの検証アルゴ [リ](https://w3c.github.io/webauthn#verifying-assertion) ズムに記入して詳細な手順の一覧を記入できます。  

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

*   Web 認証 API の推奨バージョンは、Microsoft EdgeHTML 18 以降 (Windows Insider Preview バージョン 17713 以降) 以降の Microsoft Edge から使用できます。  
*   プ [レフィックス化済み、](https://blogs.windows.com/msedgedev/2016/04/12) プレビュー バージョンが削除され、利用できなくなりました。  
*   Web 認証 API は、UWP アプリおよび PWA ではまだ利用できません。  
*   Internet Explorer Web 認証 API はサポートされていません。  

### サポートされている認証  

Microsoft Edge の Web 認証 API を使用すると、次のテクノロジを使用してユーザーを認証できます。  

*   **Windows Hello**  顔認証、指紋、または PIN でパスワードなしデバイス認証を有効にします。  
*   **FIDO2**  リムーバブル デバイスと指紋または PIN を使用したパスワードなしのローミング認証を有効にします。  
*   **U2F**  パスワードをレスクリプト モデルに移行する準備ができていない Web サイトの第 2 要素認証を有効にします。  

### Windows Hello の特別な考慮事文  

Windows Hello 認証を使用する場合は、次の注意が必要です。  

*   API を呼び出すことで、PC で Windows Hello を利用できるかを `isUserVerifyingPlatformAuthenticatorAvailable` 検出できます。  この API の詳細については、こちら [をご覧ください](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable)。  
*   Windows Hello の資情報を作成する場合は、最高のユーザー エクスペリエンス `authenticatorAttachment` `platform` を得るように設定する必要があります。
*   Windows Hello は、公開キー アルゴリズムとして RS256 \(alg -257\) のみをサポートします。  資格情報を作成するときには必ずこのアルゴリズムを指定してください。  
*   TPM の呼び出しステートメン [トを受け取るには](https://w3c.github.io/webauthn#tpm-attestation)、API を呼び出すときに "direct" に設定 `create` します。  TPM のテストは、最も効果的です。  TPM 2.0 を使用する PC のみが TPM の Attestation ステートメントを返し、さまざまな理えで、試行中のプロセスが失敗する可能性があります。  
*   Windows Hello では、ユーザーの資格情報を保護するさまざまな方法を利用できます。  資情報の作成時に返される属性オブジェクト [の AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) フィールドを使用することで、資情報を保護するために使用された方法を確認できます。  Windows Hello が返す可能性のある AAGUI には、次のような一覧が示されます。   
    *   ソフトウェアが再び認証された認証  
        *   Windows Hello ソフトウェア認証:  `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`  
        *   Windows Hello VBS ソフトウェア認証ツール:  `6E96969E-A5CF-4AAD-9B56-305FE6C82795`  
    *   信頼できるプラットフォーム モジュール \(TPM\) バイト認証  
        *   Windows Hello ハードウェア認証機能:  `08987058-CADC-4B81-B6E1-30DE50DCBE96`  
        *   Windows Hello VBS ハードウェア認証:  `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`  

### API サーフェイス  

*   Microsoft Edge には、コア Web 認証の推奨バージョンの完全な実装があります。  
*   [AppID の拡張子がサポート](https://w3c.github.io/webauthn#sctn-appid-extension)されています。  
*   他の拡張機能はサポートされません。  

## デモ  

[クライアントとサーバーのコード サンプル](https://github.com/MicrosoftEdge/webauthnsample)  

[Windows Hello テスト ドライブのデモ](https://webauthnsample.azurewebsites.net)  

## Specification  

[Web 認証: パブリック キー資情報にアクセスする API](http://w3c.github.io/webauthn)  
