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
# <span data-ttu-id="417dc-104">Web 認証と Windows Hello</span><span class="sxs-lookup"><span data-stu-id="417dc-104">Web authentication and Windows Hello</span></span>

<span data-ttu-id="417dc-105">Microsoft Edge の Web Authentication (以前の*FIDO 2.0* ) API では、パスワードの推測、フィッシング詐欺、keylogging などのパスワード管理のすべての問題を回避するために、ユーザーが[Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961)生体認証を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="417dc-105">The Web Authentication (formerly *FIDO 2.0* ) API in Microsoft Edge enables web applications to use [Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961) biometrics for user authentication so that you and your users can avoid all the hassles and risks of password management, including password guessing, phishing, and keylogging attacks.</span></span> <span data-ttu-id="417dc-106">現在の Microsoft Edge (*ms*プレフィックス) の実装は、以前の Web 認証仕様の草案に基づいており、今後変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="417dc-106">The current Microsoft Edge (*ms-* prefixed) implementation is based on an earlier draft of the Web Authentication specification and is likely to change in the future.</span></span> **<span data-ttu-id="417dc-107">このトピックでは、Microsoft Edge で Windows Hello 認証を実行する方法について説明します。これには、ブラウザーの更新プログラムに対するコードの校正も行われます。</span><span class="sxs-lookup"><span data-stu-id="417dc-107">This topic will show you how to try out Windows Hello authentication with Microsoft Edge while also future-proofing your code against browser updates.</span></span>**

<span data-ttu-id="417dc-108">Web 認証 API は、 [FIDO](https://fidoalliance.org/)との相互運用を実現することを目的として、Windows Hello やその他の生体認証デバイスを使用して web 認証を行うことを目的とした、新しい標準です。</span><span class="sxs-lookup"><span data-stu-id="417dc-108">The Web Authentication API is an emerging standard put forth by the [FIDO Alliance](https://fidoalliance.org/) with the aim of providing an interoperable way of doing web authentication using Windows Hello and other biometric devices across browsers.</span></span> <span data-ttu-id="417dc-109">Web 認証仕様では、2つの認証シナリオを定義します。パスワードを小さくして2つの要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="417dc-109">The Web Authentication specification defines two authentication scenarios: password-less and two factor.</span></span> <span data-ttu-id="417dc-110">パスワードを使用しない場合、ユーザーは、ユーザー名またはパスワードを使って web ページにログインする必要がなくなります。 Windows Hello を使用する場合にのみログインできます。</span><span class="sxs-lookup"><span data-stu-id="417dc-110">In the password-less case, the user does not need to log into the web page using a user name or password – they can login solely using Windows Hello.</span></span> <span data-ttu-id="417dc-111">この2つの要因により、ユーザーは通常ユーザー名とパスワードを使用してログインしますが、Windows Hello は、全体的な認証を強化するために、2つ目の要因チェックとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="417dc-111">In the two factor case, the user logs in normally using a username and password, but Windows Hello is used as a second factor check to make the overall authentication stronger.</span></span>

<span data-ttu-id="417dc-112">Windows Hello と組み合わせた Web 認証を使用すると、サーバーはプレーンテキストのチャレンジをブラウザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="417dc-112">Using Web Authentication combined with Windows Hello, the server sends down a plain text challenge to the browser.</span></span> <span data-ttu-id="417dc-113">Microsoft Edge が Windows Hello を通じてユーザーを確認できるようになると、このユーザー用に事前にプロビジョニングされた秘密キーを使用してチャレンジに署名し、署名をサーバーに戻します。</span><span class="sxs-lookup"><span data-stu-id="417dc-113">Once Microsoft Edge is able to verify the user through Windows Hello, the system will sign the challenge with a private key previously provisioned for this user and send the signature back to the server.</span></span> <span data-ttu-id="417dc-114">サーバーがそのユーザーに対して持っている公開キーを使って署名を検証し、問題が正しいことを確認できる場合は、ユーザーを安全に認証することができます。</span><span class="sxs-lookup"><span data-stu-id="417dc-114">If the server can validate the signature using the public key it has for that user and verify the challenge is correct, it can authenticate the user securely.</span></span> <span data-ttu-id="417dc-115">このような[非対称暗号化](https://en.wikipedia.org/wiki/Public-key_cryptography)では、公開キーが単独では無意味であり、秘密キーは共有されません。</span><span class="sxs-lookup"><span data-stu-id="417dc-115">With [asymmetric cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) such as this, the public key is meaningless on its own and the private key is never shared.</span></span> <span data-ttu-id="417dc-116">さらに、TPM 対応ハードウェアを搭載した最新システムから秘密キーを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="417dc-116">Furthermore, the private key can never be moved from modern systems with TPM-enabled hardware.</span></span>

<span data-ttu-id="417dc-117">Web 認証 API を使用するには、次の2つの基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="417dc-117">There are two basic steps to using the Web Authentication API:</span></span>

**<span data-ttu-id="417dc-118">1. ユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="417dc-118">1. Register your user with</span></span> `makeCredential`**

**<span data-ttu-id="417dc-119">2. ユーザーの認証方法</span><span class="sxs-lookup"><span data-stu-id="417dc-119">2. Authenticate your user with</span></span> `getAssertion`**

<span data-ttu-id="417dc-120">以下では、推奨される[Webauthn polyfill](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js)を使用して、この流れについて説明します。</span><span class="sxs-lookup"><span data-stu-id="417dc-120">The following will walk you through this flow using the recommended [Webauthn.js polyfill](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js).</span></span> <span data-ttu-id="417dc-121">[完全なコード](https://github.com/adrianba/fido-snippets/)は、このサーバーとクライアント側のデモで利用できます。</span><span class="sxs-lookup"><span data-stu-id="417dc-121">The [complete code](https://github.com/adrianba/fido-snippets/) is available for this server and client side demo.</span></span> <span data-ttu-id="417dc-122">[C#](https://github.com/adrianba/fido-snippets/tree/master/csharp)、 [PHP](https://github.com/adrianba/fido-snippets/tree/master/php)、および[ノード .js](https://github.com/adrianba/fido-snippets/tree/master/nodejs)のサーバー側のバージョンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="417dc-122">[C#](https://github.com/adrianba/fido-snippets/tree/master/csharp), [PHP](https://github.com/adrianba/fido-snippets/tree/master/php), and [Node.JS](https://github.com/adrianba/fido-snippets/tree/master/nodejs) server side versions are available.</span></span>

## <span data-ttu-id="417dc-123">ユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="417dc-123">Register your user</span></span>

<span data-ttu-id="417dc-124">*Id プロバイダー*として機能する場合は、まず、ユーザーに対して、ウィンドウの webauthn を使って Web 認証の資格情報を作成する必要があります。**makeCredential**メソッド。</span><span class="sxs-lookup"><span data-stu-id="417dc-124">Acting as an *identity provider*, you will first need to create a Web Authentication credential for your user with the window.webauthn.**makeCredential** method.</span></span> <span data-ttu-id="417dc-125">その資格情報をサーバー上のユーザーに登録する前に、ユーザーの id を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417dc-125">Before you register that credential to the user on your server, you will need to confirm the identity of the user.</span></span> <span data-ttu-id="417dc-126">これを行うには、ユーザーにメールの確認を送信するか、従来のログイン方法を使用するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="417dc-126">This can be done by sending the user an email confirmation or asking them to use their traditional login method.</span></span>

<span data-ttu-id="417dc-127">MakeCredential メソッドは、次のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="417dc-127">The makeCredential method takes the following parameters:</span></span>
 - **<span data-ttu-id="417dc-128">ユーザーアカウント情報</span><span class="sxs-lookup"><span data-stu-id="417dc-128">user account information</span></span>**

```
    var userAccountInformation = {
        rpDisplayName: "fido-demo",
        displayName: email
    };
```

 - **<span data-ttu-id="417dc-129">暗号化パラメーター</span><span class="sxs-lookup"><span data-stu-id="417dc-129">crypto parameters</span></span>**

```
    var cryptoParams = [
        {
            type: "ScopedCred",
            algorithm: "RSASSA-PKCS1-v1_5",
        }
    ];
```

<span data-ttu-id="417dc-130">結果として得られる promise は、今後の認証を検証するためにサーバーに戻す資格情報を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="417dc-130">The resulting promise returns an object representing the credential that you then send back to the server for validating future authentications:</span></span>

**<span data-ttu-id="417dc-131">クライアント</span><span class="sxs-lookup"><span data-stu-id="417dc-131">Client</span></span>**

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

<span data-ttu-id="417dc-132">MakeCredential メソッドを使用する場合、Microsoft Edge はまず、ユーザーが Windows アカウントにログインしているユーザーと同じユーザーであることを確認するために、Windows Hello に表面または指紋 id を使用するように求めます。</span><span class="sxs-lookup"><span data-stu-id="417dc-132">When you use the makeCredential method, Microsoft Edge will first ask Windows Hello to use face or fingerprint identification to verify that the user is the same user as the one logged into the Windows account.</span></span> <span data-ttu-id="417dc-133">この手順を完了すると、Microsoft Passport によって公開キーと秘密キーのペアが生成され、秘密キーが信頼できるプラットフォームモジュール (TPM) に格納されます。これには、資格情報を保存するために使用される専用の暗号化プロセッサハードウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="417dc-133">Once this step is completed, Microsoft Passport will generate a public/private key pair and store the private key in the Trusted Platform Module (TPM), the dedicated crypto processor hardware used to store credentials.</span></span> <span data-ttu-id="417dc-134">ユーザーが TPM 対応デバイスを持っていない場合、これらのキーはソフトウェアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="417dc-134">If the user doesn’t have a TPM enabled device, these keys will be stored in software.</span></span> <span data-ttu-id="417dc-135">これらの資格情報は、Windows アカウントごとに送信元ごとに作成され、デバイスに関連付けられているため、ローミングされません。</span><span class="sxs-lookup"><span data-stu-id="417dc-135">These credentials are created per origin, per Windows account, and will not be roamed because they are tied to the device.</span></span> <span data-ttu-id="417dc-136">つまり、ユーザーは使用するすべてのデバイスに対して Windows Hello を使用するように登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417dc-136">This means that you’ll need to make sure the user registers to use Windows Hello for every device they use.</span></span>

## <span data-ttu-id="417dc-137">ユーザーを認証する</span><span class="sxs-lookup"><span data-stu-id="417dc-137">Authenticate your user</span></span>

<span data-ttu-id="417dc-138">クライアントで資格情報が作成されると、次回ユーザーがそのサイトにログインしようとしたときに、Windows Hello を使用して、パスワードの代わりに window Hello を使ってサインインすることができます。**getAssertion**。</span><span class="sxs-lookup"><span data-stu-id="417dc-138">Once the credential is created on the client, the next time the user attempts to log into the site you can offer to sign them in using Windows Hello instead of a password with a call to window.webauthn.**getAssertion**.</span></span>

<span data-ttu-id="417dc-139">GetAssertion メソッドは、単に必要なパラメーターとして*チャレンジ*を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="417dc-139">The getAssertion method takes the *challenge* as its only required parameter.</span></span> <span data-ttu-id="417dc-140">チャレンジはランダムに生成された量であり、サーバーがクライアントに送信して、ユーザーの秘密キーを使って署名します。</span><span class="sxs-lookup"><span data-stu-id="417dc-140">The challenge is the randomly generated quantity that the server will send down to a client to sign with the user's private key.</span></span> <span data-ttu-id="417dc-141">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="417dc-141">For example:</span></span>

**<span data-ttu-id="417dc-142">Server</span><span class="sxs-lookup"><span data-stu-id="417dc-142">Server</span></span>**

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

<span data-ttu-id="417dc-143">GetAssertion の呼び出しが行われると、Microsoft Edge に Windows Hello プロンプトが表示され、生体認証を使用してユーザーの id が確認されます。</span><span class="sxs-lookup"><span data-stu-id="417dc-143">Once the getAssertion call is made, Microsoft Edge will show the Windows Hello prompt, which will verify the identity of the user using biometrics.</span></span> <span data-ttu-id="417dc-144">ユーザーが確認されると、チャレンジは TPM 内で署名され、次のようにサーバーに送信するための署名とその他のメタデータを含むアサーションオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="417dc-144">After the user is verified, the challenge will be signed within the TPM and the promise will return with an assertion object that contains the signature and other metadata for you to send to the server:</span></span>

**<span data-ttu-id="417dc-145">クライアント</span><span class="sxs-lookup"><span data-stu-id="417dc-145">Client</span></span>**

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

<span data-ttu-id="417dc-146">サーバーでアサーションを受信したら、署名を検証してユーザーを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417dc-146">Once you receive the assertion on the server, you will need to validate the signature to authenticate the user.</span></span> <span data-ttu-id="417dc-147">たとえば、(NODE.JS の場合):</span><span class="sxs-lookup"><span data-stu-id="417dc-147">For example (in Node.JS):</span></span>

**<span data-ttu-id="417dc-148">Server</span><span class="sxs-lookup"><span data-stu-id="417dc-148">Server</span></span>**

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

## <span data-ttu-id="417dc-149">Microsoft Edge とスペックの違い</span><span class="sxs-lookup"><span data-stu-id="417dc-149">Differences between Microsoft Edge and the spec</span></span>

> [!NOTE]
> <span data-ttu-id="417dc-150">Microsoft Edge で Windows Hello を使用して Web 認証 API を試用する場合は、ここに記載されている不一致を考慮する必要がないように、上記の polyfill を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="417dc-150">When trying out the Web Authentication API with Windows Hello in Microsoft Edge, we recommend using the Webauthn.js polyfill as shown above to avoid having to account for the discrepancies listed here.</span></span> <span data-ttu-id="417dc-151">この polyfill は、定義の主要な公開バージョンごとに更新されます。</span><span class="sxs-lookup"><span data-stu-id="417dc-151">We'll update this polyfill for every major published version of the specification.</span></span>


<span data-ttu-id="417dc-152">現在の Microsoft Edge の実装は、Web 認証仕様の以前のドラフトに基づいており、将来のビルドやスペックの進化に伴って変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="417dc-152">The current Microsoft Edge implementation is based on an earlier draft of the Web Authentication specification and is likely to change in future builds and as the spec evolves.</span></span> <span data-ttu-id="417dc-153">現在の違いは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="417dc-153">The current differences include:</span></span>

- <span data-ttu-id="417dc-154">Microsoft Edge Api には、MS というプレフィックスが付いています。</span><span class="sxs-lookup"><span data-stu-id="417dc-154">Microsoft Edge APIs are MS- prefixed.</span></span>
- <span data-ttu-id="417dc-155">Microsoft Edge では、USB キーや Bluetooth デバイスなどの外部資格情報はまだサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="417dc-155">Microsoft Edge does not yet support external credentials like USB keys or Bluetooth devices.</span></span> <span data-ttu-id="417dc-156">現在の API は、TPM に保存されている埋め込まれた資格情報に制限されています。</span><span class="sxs-lookup"><span data-stu-id="417dc-156">The current API is limited to embedded credentials stored in the TPM.</span></span>
- <span data-ttu-id="417dc-157">現在ログインしている Windows のユーザーアカウントは、少なくとも1つの PIN をサポートするように構成されている必要があります。また、推奨されるフェースまたは指紋の生体認証</span><span class="sxs-lookup"><span data-stu-id="417dc-157">The currently logged in Windows user account must be configured to support at least a PIN, and preferably face or fingerprint biometrics.</span></span> <span data-ttu-id="417dc-158">これにより、Windows で TPM へのアクセスが認証されるようになります。</span><span class="sxs-lookup"><span data-stu-id="417dc-158">This is to ensure that Windows can authenticate the access to the TPM.</span></span>
- <span data-ttu-id="417dc-159">Microsoft Edge の実装では、アカウント選択エクスペリエンスはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="417dc-159">The Microsoft Edge implementation does not yet support the account picker experience.</span></span>
- <span data-ttu-id="417dc-160">MsCredentials への呼び出しには、現在資格情報 id を指定する2つの*filters*パラメーターが必要です。[getAssertion](https://msdn.microsoft.com/library/mt697640)。</span><span class="sxs-lookup"><span data-stu-id="417dc-160">A second *filters* parameter specifying the credential id is currently required for calls to msCredentials.[getAssertion](https://msdn.microsoft.com/library/mt697640).</span></span> <span data-ttu-id="417dc-161">そのため、資格情報の ID 情報は、資格情報を作成するときに、インデックス Db または localStorage のいずれかのクライアントのローカルストレージに格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417dc-161">As such, you’ll need to store your credential ID information in local storage on the client, either in indexDB or localStorage when making your credential.</span></span> <span data-ttu-id="417dc-162">ローカルストレージなどのユーザーが閲覧履歴を削除した場合は、次回ログイン時に Windows Hello を使用するために再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417dc-162">If a user deletes their browsing history, including local storage, they will need to re-register to use Windows Hello the next time they log in.</span></span>
- <span data-ttu-id="417dc-163">Microsoft Edge では、現在の Web 認証仕様の下書き (拡張機能やタイムアウトなど) のオプションをすべてサポートしているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="417dc-163">Microsoft Edge does not support all of the options in the current Web Authentication specification draft, such as extensions or timeouts.</span></span>

<span data-ttu-id="417dc-164">この最終ポイントでは、Microsoft Edge の特定の相違点について、次の Web 認証仕様の定義に記載されています。</span><span class="sxs-lookup"><span data-stu-id="417dc-164">On that last point, the specific Microsoft Edge differences are noted in the following Web Authentication spec definitions:</span></span>

### <span data-ttu-id="417dc-165">W3C spec</span><span class="sxs-lookup"><span data-stu-id="417dc-165">W3C spec</span></span>

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



## <span data-ttu-id="417dc-166">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="417dc-166">API Reference</span></span>

[<span data-ttu-id="417dc-167">MSCredentials</span><span class="sxs-lookup"><span data-stu-id="417dc-167">MSCredentials</span></span>](https://msdn.microsoft.com/library/mt697639)

[<span data-ttu-id="417dc-168">makeCredential</span><span class="sxs-lookup"><span data-stu-id="417dc-168">makeCredential</span></span>](https://msdn.microsoft.com/library/mt697641)

[<span data-ttu-id="417dc-169">getAssertion</span><span class="sxs-lookup"><span data-stu-id="417dc-169">getAssertion</span></span>](https://msdn.microsoft.com/library/mt697640)

## <span data-ttu-id="417dc-170">デモ</span><span class="sxs-lookup"><span data-stu-id="417dc-170">Demos</span></span>

[<span data-ttu-id="417dc-171">クライアントとサーバーのコードサンプル</span><span class="sxs-lookup"><span data-stu-id="417dc-171">Client and server code samples</span></span>](https://github.com/adrianba/fido-snippets/)

[<span data-ttu-id="417dc-172">Webauthn polyfill</span><span class="sxs-lookup"><span data-stu-id="417dc-172">Webauthn.js polyfill</span></span>](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js)

[<span data-ttu-id="417dc-173">Windows Hello のテストドライブのデモ</span><span class="sxs-lookup"><span data-stu-id="417dc-173">Windows Hello Test Drive demo</span></span>](https://testdrive-fido.azurewebsites.net/)

## <span data-ttu-id="417dc-174">キャスト</span><span class="sxs-lookup"><span data-stu-id="417dc-174">Specification</span></span>

[<span data-ttu-id="417dc-175">Web 認証: スコープ指定された資格情報にアクセスするための Web API 1</span><span class="sxs-lookup"><span data-stu-id="417dc-175">Web Authentication: A Web API for accessing scoped credentials 1</span></span>](http://w3c.github.io/webauthn/)  
