---
ms.assetid: 88825563-5f5d-421d-861b-7cec01277dec
description: Web 認証 API を使用して、web アプリケーションで Windows Hello と FIDO2 を使用してユーザー認証を行う方法について説明します。
title: 開発ガイド-Web 認証
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: cb561ae4147a24489138263a83dd37bd6f599074
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569176"
---
# Web 認証と Windows Hello

Microsoft Edge の[Web 認証 API](https://w3c.github.io/webauthn)では、パスワードの推測、フィッシング詐欺、キーの記録攻撃など、ユーザーがパスワード管理のすべての面倒なリスクを回避することができるように、web アプリケーションが[Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961)と[外部の FIDO2 デバイス](https://fidoalliance.org/fido2)を使用できるようにします。 現在の Microsoft Edge の実装は、Web 認証仕様の候補に基づいています。 **このトピックでは、Microsoft Edge で Windows Hello と FIDO2 認証を試す方法について説明します。**

Web 認証を使用すると、サーバーはプレーンテキストのチャレンジをブラウザーに送信します。 Microsoft Edge が Windows Hello または外部の FIDO2 デバイスを通じてユーザーを確認できるようになると、このユーザー用に事前にプロビジョニングされた秘密キーを使ってチャレンジに署名し、署名をサーバーに戻します。 サーバーがそのユーザーに対して持っている公開キーを使って署名を検証し、問題が正しいことを確認できる場合は、ユーザーを安全に認証することができます。 このような[非対称暗号化](https://en.wikipedia.org/wiki/Public-key_cryptography)では、公開キーが単独では無意味であり、秘密キーは共有されません。 さらに、秘密キーは、TPM 対応ハードウェアを使用して、セキュリティで保護された要素または先進システムから移行することはできません。

Web 認証 API を使用するには、次の2つの基本的な手順を実行します。

**1. ユーザーを登録する `create`**

**2. ユーザーの認証方法 `get`**

以下の開発ガイドでは、 [WebAuthn サンプルアプリ](https://github.com/MicrosoftEdge/webauthnsample)を使ってこの流れについて説明します。

## ユーザーを登録する

*Id プロバイダー*として機能する場合は、まず、ユーザー用の Web 認証資格情報をナビゲーターで作成する必要があります。**create**メソッド。 その資格情報をサーバー上のユーザーに登録する前に、ユーザーの id を確認する必要があります。 これを行うには、ユーザーにメールの確認を送信するか、従来のログイン方法を使用するように依頼します。


この `create` メソッドは、次のパラメーターを受け取ります。

 - **証明書利用者情報**

```javascript
    rp: {
        name: "WebAuthn Sample App",
        icon: "https://example.com/rpIcon.png"
    },
```

 - **ユーザーアカウント情報**

```javascript
    user: {
        id: stringToArrayBuffer("some.user.id"),
        name: "bob.smith@contoso.com",
        displayName: "Bob Smith",
        icon: "https://example.com/userIcon.png"
    },
```

 - **暗号化パラメーター**

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

 - **authenticator の選択パラメーター**

```javascript
    authenticatorSelection: {
        //Select authenticators that support username-less flows
        requireResidentKey: true,
        //Select authenticators that have a second factor (e.g. PIN, Bio)
        userVerification: "required",
        //Selects between bound or detachable authenticators
        authenticatorAttachment: "platform"
    },
```

- **その他のオプション**

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

[資格情報作成パラメーター](https://w3c.github.io/webauthn/#dictdef-publickeycredentialcreationoptions)を使用して、作成する資格情報を構成することができます。 特に、をに設定して、Windows Hello の資格情報を設定して `authenticatorAttachment` `platform` 、または外部の FIDO2 デバイスでローミングの資格情報を作成することができ `authenticatorAttachment` `cross-platform` ます。 

この方法を使用する場合 `create` 、Microsoft Edge はまず、ユーザーに自分の表面または指紋をスキャンするか、PIN を入力するか、外部の FIDO2 デバイスで操作を実行して、自分のプレゼンスを確認するように求めます。 この手順を完了すると、オーセンティケータによって公開/秘密キーのペアが生成され、秘密キーが保存されます。 これらの資格情報は、元のアカウントごとに作成され、認証デバイスに安全に保存されているため、抽出することはできません。 

結果として得られる promise は、新しい資格情報を表す[構成証明オブジェクト](https://w3c.github.io/webauthn/#sctn-attestation)を返します。 構成証明オブジェクトには、資格情報の公開キーが含まれています。 今後の認証を検証するために、このオブジェクトをサーバーに送信します。 サーバーに再送信する前に、生データを base64 でエンコードする必要があります。

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

次に、サーバーは構成証明オブジェクトのデコード、確認手順の実行、この資格情報の公開キーの抽出、将来の認証のための保存を行う必要があります。 手順の詳細な一覧は、WebAuthn 仕様の[資格情報登録アルゴリズム](https://w3c.github.io/webauthn/#registering-a-new-credential)に記載されています。

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

クライアントで資格情報が作成されると、次回ユーザーがそのサイトにログインしようとしたときに、ユーザーはナビゲーターを呼び出してパスワードの代わりに、Web 認証資格情報を使用してサインインすることができます。**取得**します。

この `get` メソッドは、必要な唯一のパラメーターとして*チャレンジ*を受け取ります。 チャレンジは、ユーザーの秘密キーを使用して署名するためにサーバーがクライアントに送信する、符号化されたバイトシーケンスです。 次に、例を示します。

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

サーバーからチャレンジを取得したら、[資格情報要求オプション](https://w3c.github.io/webauthn/#credentialrequestoptions-extension)と共に get API を呼び出します。 Microsoft Edge にプロンプトが表示され、Windows Hello または外部の FIDO2 デバイスを使ってユーザーの id が確認されます。 ユーザーが確認されると、チャレンジは TPM または FIDO2 デバイス内で署名され、promise は、サーバーに送信するための署名とその他のメタデータを含む[アサーションオブジェクト](https://w3c.github.io/webauthn/#authenticatorassertionresponse)を返します。

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

サーバーでアサーションを受信したら、署名を検証してユーザーを認証する必要があります。 いくつかのサンプルコードを次に示します。  ステップの詳細な一覧は、WebAuthn の仕様の[assertion の検証アルゴリズム](https://w3c.github.io/webauthn/#verifying-assertion)に記載されています。

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
- Web Authentication API の候補候補は、EdgeHTML 18 (Windows Insider Preview バージョン17713および up) 以降の Microsoft Edge から使用できます。
- [プレフィックスが付いた、プレビュー版](https://blogs.windows.com/msedgedev/2016/04/12/a-world-without-passwords-windows-hello-in-microsoft-edge/)の WEB 認証 API は削除されたため、利用できなくなりました。
- UWP アプリと PWAs では、Web 認証 API はまだ利用できません。
- Internet Explorer では、Web 認証 API をサポートしていません。 

### サポートされている認証
Microsoft Edge の Web 認証 API では、次のテクノロジを使用してユーザーを認証することができます。
- **Windows Hello**では、パスワードを使用して、デバイス上でのパスワードの認証を可能にします。
- **FIDO2**は、リムーバブルデバイスと指紋またはピンでのパスワードを使用しないローミング認証を有効にします。
- **U2F**、パスワードを使用しないモデルに移行する準備ができていない web サイトに対して強力な2要素認証を有効にする

### Windows Hello に関する特別な考慮事項 
Windows Hello 認証システムを使用する場合は、次の点に注意してください。
- API を呼び出すことによって、PC で Windows Hello が利用可能かどうかを検出でき `isUserVerifyingPlatformAuthenticatorAvailable` ます。 この API の詳細について[は、こちら](https://www.w3.org/TR/webauthn/#isUserVerifyingPlatformAuthenticatorAvailable)を参照してください。
- Windows Hello の資格情報を作成する場合は、最適なユーザーエクスペリエンスを設定する必要があり `authenticatorAttachment` `platform` ます。
- Windows Hello は、公開キーアルゴリズムとして RS256 (alg-257) のみをサポートしています。 資格情報を作成するときは、必ずこのアルゴリズムを指定してください。
- [TPM 構成証明ステートメント](https://w3c.github.io/webauthn/#tpm-attestation)を受け取るには、API を呼び出すときに、構成証明を "直接" に設定し `create` ます。 TPM の構成証明は、ベストエフォートです。 TPM 2.0 を搭載した Pc のみが TPM 構成証明書を返し、構成証明プロセスはさまざまな理由で失敗することがあります。
- Windows Hello には、ユーザーの資格情報を保護するためのさまざまな方法が採用しています。 資格情報を保護するために使用された認証方法を確認するには、資格情報の作成時に返された構成証明オブジェクトの " [uid](https://w3c.github.io/webauthn/#sec-attested-credential-data) " フィールドを使います。 Windows Hello が返すことができる AAGUIDs の一覧を次に示します。 
  - ソフトウェアでサポートされているオーセンティケータ
    - Windows Hello ソフトウェア認証システム: `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`
    - Windows Hello VBS software authenticator: `6E96969E-A5CF-4AAD-9B56-305FE6C82795`
  - トラステッドプラットフォームモジュール (TPM) バックアップされたオーセンティケータ
    - Windows Hello ハードウェア認証システム: `08987058-CADC-4B81-B6E1-30DE50DCBE96`
    - Windows Hello VBS ハードウェア認証システム: `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`


### API サーフェス
- Microsoft Edge では、基本的な Web 認証仕様の候補の候補を完全に実装しています。
- [AppID の拡張機能](https://w3c.github.io/webauthn/#sctn-appid-extension)がサポートされています。 
- その他の拡張機能はサポートされていません。


## デモ

[クライアントとサーバーコードのサンプル](https://github.com/MicrosoftEdge/webauthnsample)

[Windows Hello のテストドライブのデモ](https://webauthnsample.azurewebsites.net/)

## キャスト

[Web 認証: 公開キーの資格情報にアクセスするための API](http://w3c.github.io/webauthn/)
