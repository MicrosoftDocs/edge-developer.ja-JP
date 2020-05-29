---
ms.assetid: 88825563-5f5d-421d-861b-7cec01277dec
description: Web 認証 API を使用して、web アプリケーションが Windows Hello 生体認証を使用してユーザー認証を利用できるようにする方法について説明します。
title: 開発ガイド-Web 認証
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: c49d181633ae1b2b35aa0f88287841d28e806f44
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568831"
---
# Web 認証と Windows Hello

Microsoft Edge の Web Authentication (以前の*FIDO 2.0* ) API では、パスワードの推測、フィッシング詐欺、keylogging などのパスワード管理のすべての問題を回避するために、ユーザーが[Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961)生体認証を使用することができます。 現在の Microsoft Edge (*ms*プレフィックス) の実装は、以前の Web 認証仕様の草案に基づいており、今後変更される可能性があります。 **このトピックでは、Microsoft Edge で Windows Hello 認証を実行する方法について説明します。これには、ブラウザーの更新プログラムに対するコードの校正も行われます。**

Web 認証 API は、 [FIDO](https://fidoalliance.org/)との相互運用を実現することを目的として、Windows Hello やその他の生体認証デバイスを使用して web 認証を行うことを目的とした、新しい標準です。 Web 認証仕様では、2つの認証シナリオを定義します。パスワードを小さくして2つの要素を指定します。 パスワードを使用しない場合、ユーザーは、ユーザー名またはパスワードを使って web ページにログインする必要がなくなります。 Windows Hello を使用する場合にのみログインできます。 この2つの要因により、ユーザーは通常ユーザー名とパスワードを使用してログインしますが、Windows Hello は、全体的な認証を強化するために、2つ目の要因チェックとして使用されます。

Windows Hello と組み合わせた Web 認証を使用すると、サーバーはプレーンテキストのチャレンジをブラウザーに送信します。 Microsoft Edge が Windows Hello を通じてユーザーを確認できるようになると、このユーザー用に事前にプロビジョニングされた秘密キーを使用してチャレンジに署名し、署名をサーバーに戻します。 サーバーがそのユーザーに対して持っている公開キーを使って署名を検証し、問題が正しいことを確認できる場合は、ユーザーを安全に認証することができます。 このような[非対称暗号化](https://en.wikipedia.org/wiki/Public-key_cryptography)では、公開キーが単独では無意味であり、秘密キーは共有されません。 さらに、TPM 対応ハードウェアを搭載した最新システムから秘密キーを移動することはできません。

Web 認証 API を使用するには、次の2つの基本的な手順を実行します。

**1. ユーザーを登録する `makeCredential`**

**2. ユーザーの認証方法 `getAssertion`**

以下では、推奨される[Webauthn polyfill](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js)を使用して、この流れについて説明します。 [完全なコード](https://github.com/adrianba/fido-snippets/)は、このサーバーとクライアント側のデモで利用できます。 [C#](https://github.com/adrianba/fido-snippets/tree/master/csharp)、 [PHP](https://github.com/adrianba/fido-snippets/tree/master/php)、および[ノード .js](https://github.com/adrianba/fido-snippets/tree/master/nodejs)のサーバー側のバージョンを利用できます。

## ユーザーを登録する

*Id プロバイダー*として機能する場合は、まず、ユーザーに対して、ウィンドウの webauthn を使って Web 認証の資格情報を作成する必要があります。**makeCredential**メソッド。 その資格情報をサーバー上のユーザーに登録する前に、ユーザーの id を確認する必要があります。 これを行うには、ユーザーにメールの確認を送信するか、従来のログイン方法を使用するように依頼します。

MakeCredential メソッドは、次のパラメーターを受け取ります。
 - **ユーザーアカウント情報**

```
    var userAccountInformation = {
        rpDisplayName: "fido-demo",
        displayName: email
    };
```

 - **暗号化パラメーター**

```
    var cryptoParams = [
        {
            type: "ScopedCred",
            algorithm: "RSASSA-PKCS1-v1_5",
        }
    ];
```

結果として得られる promise は、今後の認証を検証するためにサーバーに戻す資格情報を表すオブジェクトを返します。

**クライアント**

```
<script src="webauthn.js"><!-- polyfill to map Microsoft Edge experimental implementation to current W3C spec --></script>
<script>
    var email = '<%=user.email%>';
    var name = '<%=user.name%>';

    webauthn.makeCredential(userAccountInformation, cryptoParams)
        .then(function (creds) {
            document.getElementById('form-id').value = creds.credential.id;
            document.getElementById('form-pk').value = JSON.stringify(creds.publicKey);
            document.getElementById('form-email').value = email;
            document.getElementById('form-name').value = name;
            document.getElementById('theform').submit();
        }).catch(function (err) {
            // No acceptable authenticator or user refused consent. Handle appropriately.
            alert(err);
        });
</script>
```

MakeCredential メソッドを使用する場合、Microsoft Edge はまず、ユーザーが Windows アカウントにログインしているユーザーと同じユーザーであることを確認するために、Windows Hello に表面または指紋 id を使用するように求めます。 この手順を完了すると、Microsoft Passport によって公開キーと秘密キーのペアが生成され、秘密キーが信頼できるプラットフォームモジュール (TPM) に格納されます。これには、資格情報を保存するために使用される専用の暗号化プロセッサハードウェアが含まれます。 ユーザーが TPM 対応デバイスを持っていない場合、これらのキーはソフトウェアに保存されます。 これらの資格情報は、Windows アカウントごとに送信元ごとに作成され、デバイスに関連付けられているため、ローミングされません。 つまり、ユーザーは使用するすべてのデバイスに対して Windows Hello を使用するように登録する必要があります。

## ユーザーを認証する

クライアントで資格情報が作成されると、次回ユーザーがそのサイトにログインしようとしたときに、Windows Hello を使用して、パスワードの代わりに window Hello を使ってサインインすることができます。**getAssertion**。

GetAssertion メソッドは、単に必要なパラメーターとして*チャレンジ*を受け取ります。 チャレンジはランダムに生成された量であり、サーバーがクライアントに送信して、ユーザーの秘密キーを使って署名します。 次に、例を示します。

**Server**

```
var crypto = require('crypto');

Strategy.prototype.generateChallenge = function() {
    return this.generateVerifiableString(crypto.randomBytes(32));
};

Strategy.prototype.generateVerifiableString = function(data) {
    // Create cipher using secret
    var d = new Buffer(data);
    var c = crypto.createCipher('aes192',new Buffer(this._secret));

    // Encrypt data
    c.update(d);

    // Hash results of encrypting data
    var hash = crypto.createHash('sha256');
    hash.update(c.final());

    // Combine original data with hash
    return d.toString('hex') + string_separator + hash.digest('hex');
};
```

GetAssertion の呼び出しが行われると、Microsoft Edge に Windows Hello プロンプトが表示され、生体認証を使用してユーザーの id が確認されます。 ユーザーが確認されると、チャレンジは TPM 内で署名され、次のようにサーバーに送信するための署名とその他のメタデータを含むアサーションオブジェクトが返されます。

**クライアント**

```
<script src="webauthn.js"><!-- polyfill to map Microsoft Edge experimental implementation to current W3C spec --></script>
<script>
    var challenge = '<%=challenge%>';

    webauthn.getAssertion(challenge)
    .then(function(assertion) {
      document.getElementById("form-id").value = assertion.credential.id;
      document.getElementById("form-type").value = assertion.credential.type;
      document.getElementById("form-data").value = assertion.clientData;
      document.getElementById("form-sig").value = assertion.signature;
      document.getElementById("form-authnr").value = assertion.authenticatorData;
      document.getElementById("form-challenge").value = challenge;
      document.getElementById("theform").submit();
    })
    .catch(function(err) {
      if(err && err.name) {
        document.getElementById("form-err").value = err.name;
      } else {
        document.getElementById("form-err").value = "unknown";
      }
      document.getElementById("theform").submit();
    });

</script>
```

サーバーでアサーションを受信したら、署名を検証してユーザーを認証する必要があります。 たとえば、(NODE.JS の場合):

**Server**

```
var jwkToPem = require('jwk-to-pem')
var crypto = require('crypto');

var fidoAuthenticator = {
     validateSignature: function (publicKey, clientData, authnrData, signature, challenge) {
         // Make sure the challenge in the client data
         // matches the expected challenge
         var c = new Buffer(clientData, 'base64');
         var cc = JSON.parse(c.toString().replace(/\0/g,''));
         if(cc.challenge != challenge) return false;

         // Hash data with sha256
         const hash = crypto.createHash('sha256');
         hash.update(c);
         var h = hash.digest();

         // Verify signature is correct for authnrData + hash
         var verify = crypto.createVerify('RSA-SHA256');
         verify.update(new Buffer(authnrData,'base64'));
         verify.update(h);
         return verify.verify(jwkToPem(JSON.parse(publicKey)), signature, 'base64');
     }
};   
```

## Microsoft Edge とスペックの違い

> [!NOTE]
> Microsoft Edge で Windows Hello を使用して Web 認証 API を試用する場合は、ここに記載されている不一致を考慮する必要がないように、上記の polyfill を使用することをお勧めします。 この polyfill は、定義の主要な公開バージョンごとに更新されます。


現在の Microsoft Edge の実装は、Web 認証仕様の以前のドラフトに基づいており、将来のビルドやスペックの進化に伴って変更される可能性があります。 現在の違いは次のとおりです。

- Microsoft Edge Api には、MS というプレフィックスが付いています。
- Microsoft Edge では、USB キーや Bluetooth デバイスなどの外部資格情報はまだサポートしていません。 現在の API は、TPM に保存されている埋め込まれた資格情報に制限されています。
- 現在ログインしている Windows のユーザーアカウントは、少なくとも1つの PIN をサポートするように構成されている必要があります。また、推奨されるフェースまたは指紋の生体認証 これにより、Windows で TPM へのアクセスが認証されるようになります。
- Microsoft Edge の実装では、アカウント選択エクスペリエンスはまだサポートされていません。
- MsCredentials への呼び出しには、現在資格情報 id を指定する2つの*filters*パラメーターが必要です。[getAssertion](https://msdn.microsoft.com/library/mt697640)。 そのため、資格情報の ID 情報は、資格情報を作成するときに、インデックス Db または localStorage のいずれかのクライアントのローカルストレージに格納する必要があります。 ローカルストレージなどのユーザーが閲覧履歴を削除した場合は、次回ログイン時に Windows Hello を使用するために再登録する必要があります。
- Microsoft Edge では、現在の Web 認証仕様の下書き (拡張機能やタイムアウトなど) のオプションをすべてサポートしているわけではありません。

この最終ポイントでは、Microsoft Edge の特定の相違点について、次の Web 認証仕様の定義に記載されています。

### W3C spec

```
partial interface Window {
    readonly attribute WebAuthentication webauthn; // msCredentials
};

interface WebAuthentication { // MSCredentials
    Promise <ScopedCredentialInfo> makeCredential (
        Account                                 accountInformation,
        sequence <ScopedCredentialParameters>   cryptoParameters,
        DOMString                               attestationChallenge, // Optional in Microsoft Edge
        optional unsigned long                  credentialTimeoutSeconds, // Not yet supported
        optional sequence <Credential>          blacklist, // Not yet supported
        optional WebAuthnExtensions             credentialExtensions // Not yet supported
    );

    Promise <WebAuthnAssertion> getAssertion (
        DOMString                        assertionChallenge,
        optional unsigned long           assertionTimeoutSeconds, // Not yet supported
        optional sequence <Credential>   whitelist, // Not yet supported
        optional WebAuthnExtensions      assertionExtensions // Not yet supported
    );
};

interface ScopedCredentialInfo { // MSAssertion
    readonly attribute Credential           credential;
    readonly attribute any                  publicKey;
    readonly attribute AttestationStatement attestation;
};

dictionary Account { // MSAccountInfo
    required DOMString rpDisplayName;
    required DOMString displayName;
    DOMString          name; // Not yet supported
    DOMString          id; // Not yet supported
    DOMString          imageUri; // Not yet supported
};

dictionary ScopedCredentialParameters { // MSCredentialParameters
    required CredentialType        type;
    required AlgorithmIdentifier   algorithm;
};

enum CredentialType { // MSCredentialType
    "ScopedCred" // Must be "FIDO_2_0" in Microsoft Edge
};

interface Credential { // MSCredentialSpec
    readonly attribute CredentialType type;
    readonly attribute DOMString      id;
};

dictionary WebAuthnExtensions { // Not supported
};
```



## API リファレンス

[MSCredentials](https://msdn.microsoft.com/library/mt697639)

[makeCredential](https://msdn.microsoft.com/library/mt697641)

[getAssertion](https://msdn.microsoft.com/library/mt697640)

## デモ

[クライアントとサーバーのコードサンプル](https://github.com/adrianba/fido-snippets/)

[Webauthn polyfill](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js)

[Windows Hello のテストドライブのデモ](https://testdrive-fido.azurewebsites.net/)

## キャスト

[Web 認証: スコープ指定された資格情報にアクセスするための Web API 1](http://w3c.github.io/webauthn/)  
