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
# <span data-ttu-id="a6e88-104">Web 認証と Windows Hello</span><span class="sxs-lookup"><span data-stu-id="a6e88-104">Web Authentication and Windows Hello</span></span>

<span data-ttu-id="a6e88-105">Microsoft Edge の[Web 認証 API](https://w3c.github.io/webauthn)では、パスワードの推測、フィッシング詐欺、キーの記録攻撃など、ユーザーがパスワード管理のすべての面倒なリスクを回避することができるように、web アプリケーションが[Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961)と[外部の FIDO2 デバイス](https://fidoalliance.org/fido2)を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6e88-105">The [Web Authentication API](https://w3c.github.io/webauthn) in Microsoft Edge enables web applications to use [Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961) and [external FIDO2 devices](https://fidoalliance.org/fido2) for user authentication so that you and your users can avoid all the hassles and risks of password management, including password guessing, phishing, and key-logging attacks.</span></span> <span data-ttu-id="a6e88-106">現在の Microsoft Edge の実装は、Web 認証仕様の候補に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a6e88-106">The current Microsoft Edge implementation is based on the Candidate Recommendation of the Web Authentication specification.</span></span> **<span data-ttu-id="a6e88-107">このトピックでは、Microsoft Edge で Windows Hello と FIDO2 認証を試す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-107">This topic will show you how to try out Windows Hello and FIDO2 authentication with Microsoft Edge.</span></span>**

<span data-ttu-id="a6e88-108">Web 認証を使用すると、サーバーはプレーンテキストのチャレンジをブラウザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-108">Using Web Authentication, the server sends down a plain text challenge to the browser.</span></span> <span data-ttu-id="a6e88-109">Microsoft Edge が Windows Hello または外部の FIDO2 デバイスを通じてユーザーを確認できるようになると、このユーザー用に事前にプロビジョニングされた秘密キーを使ってチャレンジに署名し、署名をサーバーに戻します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-109">Once Microsoft Edge is able to verify the user through Windows Hello or an external FIDO2 device, the system will sign the challenge with a private key previously provisioned for this user and send the signature back to the server.</span></span> <span data-ttu-id="a6e88-110">サーバーがそのユーザーに対して持っている公開キーを使って署名を検証し、問題が正しいことを確認できる場合は、ユーザーを安全に認証することができます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-110">If the server can validate the signature using the public key it has for that user and verify the challenge is correct, it can authenticate the user securely.</span></span> <span data-ttu-id="a6e88-111">このような[非対称暗号化](https://en.wikipedia.org/wiki/Public-key_cryptography)では、公開キーが単独では無意味であり、秘密キーは共有されません。</span><span class="sxs-lookup"><span data-stu-id="a6e88-111">With [asymmetric cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) such as this, the public key is meaningless on its own and the private key is never shared.</span></span> <span data-ttu-id="a6e88-112">さらに、秘密キーは、TPM 対応ハードウェアを使用して、セキュリティで保護された要素または先進システムから移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6e88-112">Furthermore, the private key can never be moved from secure elements or modern systems with TPM-enabled hardware.</span></span>

<span data-ttu-id="a6e88-113">Web 認証 API を使用するには、次の2つの基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-113">There are two basic steps to using the Web Authentication API:</span></span>

**<span data-ttu-id="a6e88-114">1. ユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="a6e88-114">1. Register your user with</span></span> `create`**

**<span data-ttu-id="a6e88-115">2. ユーザーの認証方法</span><span class="sxs-lookup"><span data-stu-id="a6e88-115">2. Authenticate your user with</span></span> `get`**

<span data-ttu-id="a6e88-116">以下の開発ガイドでは、 [WebAuthn サンプルアプリ](https://github.com/MicrosoftEdge/webauthnsample)を使ってこの流れについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-116">The following dev guide will walk you through this flow using the [WebAuthn Sample App](https://github.com/MicrosoftEdge/webauthnsample).</span></span>

## <span data-ttu-id="a6e88-117">ユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="a6e88-117">Register your user</span></span>

<span data-ttu-id="a6e88-118">*Id プロバイダー*として機能する場合は、まず、ユーザー用の Web 認証資格情報をナビゲーターで作成する必要があります。**create**メソッド。</span><span class="sxs-lookup"><span data-stu-id="a6e88-118">Acting as an *identity provider*, you will first need to create a Web Authentication credential for your user with the navigator.credentials.**create** method.</span></span> <span data-ttu-id="a6e88-119">その資格情報をサーバー上のユーザーに登録する前に、ユーザーの id を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e88-119">Before you register that credential to the user on your server, you will need to confirm the identity of the user.</span></span> <span data-ttu-id="a6e88-120">これを行うには、ユーザーにメールの確認を送信するか、従来のログイン方法を使用するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-120">This can be done by sending the user an email confirmation or asking them to use their traditional login method.</span></span>


<span data-ttu-id="a6e88-121">この `create` メソッドは、次のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a6e88-121">The `create` method takes the following parameters:</span></span>

 - **<span data-ttu-id="a6e88-122">証明書利用者情報</span><span class="sxs-lookup"><span data-stu-id="a6e88-122">relying party information</span></span>**

```javascript
    rp: {
        name: "WebAuthn Sample App",
        icon: "https://example.com/rpIcon.png"
    },
```

 - **<span data-ttu-id="a6e88-123">ユーザーアカウント情報</span><span class="sxs-lookup"><span data-stu-id="a6e88-123">user account information</span></span>**

```javascript
    user: {
        id: stringToArrayBuffer("some.user.id"),
        name: "bob.smith@contoso.com",
        displayName: "Bob Smith",
        icon: "https://example.com/userIcon.png"
    },
```

 - **<span data-ttu-id="a6e88-124">暗号化パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6e88-124">crypto parameters</span></span>**

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

 - **<span data-ttu-id="a6e88-125">authenticator の選択パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6e88-125">authenticator selection parameters</span></span>**

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

- **<span data-ttu-id="a6e88-126">その他のオプション</span><span class="sxs-lookup"><span data-stu-id="a6e88-126">other options</span></span>**

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

<span data-ttu-id="a6e88-127">[資格情報作成パラメーター](https://w3c.github.io/webauthn/#dictdef-publickeycredentialcreationoptions)を使用して、作成する資格情報を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-127">You can use [credential creation parameters](https://w3c.github.io/webauthn/#dictdef-publickeycredentialcreationoptions) to configure the credential you want to create.</span></span> <span data-ttu-id="a6e88-128">特に、をに設定して、Windows Hello の資格情報を設定して `authenticatorAttachment` `platform` 、または外部の FIDO2 デバイスでローミングの資格情報を作成することができ `authenticatorAttachment` `cross-platform` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-128">In particular, you can choose to create a Windows Hello credential by setting `authenticatorAttachment` to `platform`, or a roaming credential on an external FIDO2 device by setting `authenticatorAttachment` to `cross-platform`.</span></span> 

<span data-ttu-id="a6e88-129">この方法を使用する場合 `create` 、Microsoft Edge はまず、ユーザーに自分の表面または指紋をスキャンするか、PIN を入力するか、外部の FIDO2 デバイスで操作を実行して、自分のプレゼンスを確認するように求めます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-129">When you use the `create` method, Microsoft Edge will first ask the user to verify their presence by scanning their face or fingerprint, entering a PIN, or taking action on an external FIDO2 device.</span></span> <span data-ttu-id="a6e88-130">この手順を完了すると、オーセンティケータによって公開/秘密キーのペアが生成され、秘密キーが保存されます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-130">Once this step is completed the authenticator will generate a public/private key pair and store the private key.</span></span> <span data-ttu-id="a6e88-131">これらの資格情報は、元のアカウントごとに作成され、認証デバイスに安全に保存されているため、抽出することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6e88-131">These credentials are created per origin, per account, and cannot be extracted because they are stored securely to the authentication device.</span></span> 

<span data-ttu-id="a6e88-132">結果として得られる promise は、新しい資格情報を表す[構成証明オブジェクト](https://w3c.github.io/webauthn/#sctn-attestation)を返します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-132">The resulting promise returns an [attestation object](https://w3c.github.io/webauthn/#sctn-attestation) representing the new credential.</span></span> <span data-ttu-id="a6e88-133">構成証明オブジェクトには、資格情報の公開キーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6e88-133">The attestation object contains the public key for the credential.</span></span> <span data-ttu-id="a6e88-134">今後の認証を検証するために、このオブジェクトをサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-134">You'll send this object to the server for validating future authentications.</span></span> <span data-ttu-id="a6e88-135">サーバーに再送信する前に、生データを base64 でエンコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e88-135">Before sending back to the server, you'll need to base64-encode the raw data.</span></span>

**<span data-ttu-id="a6e88-136">クライアント</span><span class="sxs-lookup"><span data-stu-id="a6e88-136">Client</span></span>**

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

<span data-ttu-id="a6e88-137">次に、サーバーは構成証明オブジェクトのデコード、確認手順の実行、この資格情報の公開キーの抽出、将来の認証のための保存を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e88-137">The server should then decode the attestation object, perform verification steps, extract the public key for this credential, and store it for future authentications.</span></span> <span data-ttu-id="a6e88-138">手順の詳細な一覧は、WebAuthn 仕様の[資格情報登録アルゴリズム](https://w3c.github.io/webauthn/#registering-a-new-credential)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="a6e88-138">A detailed list of steps can be found in the [credential registration algorithm](https://w3c.github.io/webauthn/#registering-a-new-credential) in the WebAuthn specification.</span></span>

**<span data-ttu-id="a6e88-139">Server</span><span class="sxs-lookup"><span data-stu-id="a6e88-139">Server</span></span>**

```javascript
    attestationObject = cbor.decodeFirstSync(Buffer.from(attestation.attestationObject, 'base64'));
    authenticatorData = parseAuthenticatorData(attestationObject.authData);
    var credential = await storage.Credentials.create({
        id: authenticatorData.attestedCredentialData.credentialId.toString('base64'),
        publicKeyJwk: authenticatorData.attestedCredentialData.publicKeyJwk,
        signCount: authenticatorData.signCount
    });
```

## <span data-ttu-id="a6e88-140">ユーザーを認証する</span><span class="sxs-lookup"><span data-stu-id="a6e88-140">Authenticate your user</span></span>

<span data-ttu-id="a6e88-141">クライアントで資格情報が作成されると、次回ユーザーがそのサイトにログインしようとしたときに、ユーザーはナビゲーターを呼び出してパスワードの代わりに、Web 認証資格情報を使用してサインインすることができます。**取得**します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-141">Once the credential is created on the client, the next time the user attempts to log into the site you can offer to sign them in using their Web Authentication credential instead of a password with a call to navigator.credentials.**get**.</span></span>

<span data-ttu-id="a6e88-142">この `get` メソッドは、必要な唯一のパラメーターとして*チャレンジ*を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a6e88-142">The `get` method takes the *challenge* as its only required parameter.</span></span> <span data-ttu-id="a6e88-143">チャレンジは、ユーザーの秘密キーを使用して署名するためにサーバーがクライアントに送信する、符号化されたバイトシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="a6e88-143">The challenge is an opaque sequence of bytes that the server will send down to a client to sign with the user's private key.</span></span> <span data-ttu-id="a6e88-144">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-144">For example:</span></span>

**<span data-ttu-id="a6e88-145">Server</span><span class="sxs-lookup"><span data-stu-id="a6e88-145">Server</span></span>**

```javascript
    var jwt = require('jsonwebtoken');
    var jwt_secret = "defaultsecret";
    fido.getChallenge = () => {
        return jwt.sign({}, jwt_secret, {
            expiresIn: 120 * 1000
        });
    };
```

<span data-ttu-id="a6e88-146">サーバーからチャレンジを取得したら、[資格情報要求オプション](https://w3c.github.io/webauthn/#credentialrequestoptions-extension)と共に get API を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-146">After retrieving a challenge from the server, you'll call the get API along with [credential request options](https://w3c.github.io/webauthn/#credentialrequestoptions-extension).</span></span> <span data-ttu-id="a6e88-147">Microsoft Edge にプロンプトが表示され、Windows Hello または外部の FIDO2 デバイスを使ってユーザーの id が確認されます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-147">Microsoft Edge will show a prompt, which will verify the identity of the user using Windows Hello or an external FIDO2 device.</span></span> <span data-ttu-id="a6e88-148">ユーザーが確認されると、チャレンジは TPM または FIDO2 デバイス内で署名され、promise は、サーバーに送信するための署名とその他のメタデータを含む[アサーションオブジェクト](https://w3c.github.io/webauthn/#authenticatorassertionresponse)を返します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-148">After the user is verified, the challenge will be signed within the TPM or FIDO2 device and the promise will return with an [assertion object](https://w3c.github.io/webauthn/#authenticatorassertionresponse) that contains the signature and other metadata for you to send to the server.</span></span>

**<span data-ttu-id="a6e88-149">クライアント</span><span class="sxs-lookup"><span data-stu-id="a6e88-149">Client</span></span>**

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

<span data-ttu-id="a6e88-150">サーバーでアサーションを受信したら、署名を検証してユーザーを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e88-150">Once you receive the assertion on the server, you will need to validate the signature to authenticate the user.</span></span> <span data-ttu-id="a6e88-151">いくつかのサンプルコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-151">The following is some sample code.</span></span>  <span data-ttu-id="a6e88-152">ステップの詳細な一覧は、WebAuthn の仕様の[assertion の検証アルゴリズム](https://w3c.github.io/webauthn/#verifying-assertion)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="a6e88-152">A detailed list of steps can be found in the [assertion verification algorithm](https://w3c.github.io/webauthn/#verifying-assertion) in the WebAuthn specification.</span></span>

**<span data-ttu-id="a6e88-153">Server</span><span class="sxs-lookup"><span data-stu-id="a6e88-153">Server</span></span>**

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

## <span data-ttu-id="a6e88-154">実装上の注意</span><span class="sxs-lookup"><span data-stu-id="a6e88-154">Implementation notes</span></span>

### <span data-ttu-id="a6e88-155">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="a6e88-155">Supported platforms</span></span>
- <span data-ttu-id="a6e88-156">Web Authentication API の候補候補は、EdgeHTML 18 (Windows Insider Preview バージョン17713および up) 以降の Microsoft Edge から使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-156">The Candidate Recommendation version of the Web Authentication API can be used from Microsoft Edge beginning with EdgeHTML 18 (Windows Insider Preview version 17713 and up).</span></span>
- <span data-ttu-id="a6e88-157">[プレフィックスが付いた、プレビュー版](https://blogs.windows.com/msedgedev/2016/04/12/a-world-without-passwords-windows-hello-in-microsoft-edge/)の WEB 認証 API は削除されたため、利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a6e88-157">The [prefixed, preview version](https://blogs.windows.com/msedgedev/2016/04/12/a-world-without-passwords-windows-hello-in-microsoft-edge/) of the Web Authentication API has been removed and is no longer available.</span></span>
- <span data-ttu-id="a6e88-158">UWP アプリと PWAs では、Web 認証 API はまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="a6e88-158">The Web Authentication API is not yet available to UWP apps and PWAs.</span></span>
- <span data-ttu-id="a6e88-159">Internet Explorer では、Web 認証 API をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a6e88-159">Internet Explorer does not support the Web Authentication API.</span></span> 

### <span data-ttu-id="a6e88-160">サポートされている認証</span><span class="sxs-lookup"><span data-stu-id="a6e88-160">Supported authenticators</span></span>
<span data-ttu-id="a6e88-161">Microsoft Edge の Web 認証 API では、次のテクノロジを使用してユーザーを認証することができます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-161">With the Web Authentication API in Microsoft Edge, you can authenticate users with the following technologies:</span></span>
- <span data-ttu-id="a6e88-162">**Windows Hello**では、パスワードを使用して、デバイス上でのパスワードの認証を可能にします。</span><span class="sxs-lookup"><span data-stu-id="a6e88-162">**Windows Hello**, enabling passwordless on-device authentication with  face, fingerprint, or PIN</span></span>
- <span data-ttu-id="a6e88-163">**FIDO2**は、リムーバブルデバイスと指紋またはピンでのパスワードを使用しないローミング認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a6e88-163">**FIDO2**, enabling passwordless roaming authentication with a removable device and a fingerprint or PIN</span></span>
- <span data-ttu-id="a6e88-164">**U2F**、パスワードを使用しないモデルに移行する準備ができていない web サイトに対して強力な2要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="a6e88-164">**U2F**, enabling strong second factor authentication for websites that are not ready to move to a passwordless model</span></span>

### <span data-ttu-id="a6e88-165">Windows Hello に関する特別な考慮事項</span><span class="sxs-lookup"><span data-stu-id="a6e88-165">Special considerations for Windows Hello</span></span> 
<span data-ttu-id="a6e88-166">Windows Hello 認証システムを使用する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6e88-166">A few things to note when using the Windows Hello authenticator:</span></span>
- <span data-ttu-id="a6e88-167">API を呼び出すことによって、PC で Windows Hello が利用可能かどうかを検出でき `isUserVerifyingPlatformAuthenticatorAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-167">You can detect if Windows Hello is available on a PC by calling the `isUserVerifyingPlatformAuthenticatorAvailable` API.</span></span> <span data-ttu-id="a6e88-168">この API の詳細について[は、こちら](https://www.w3.org/TR/webauthn/#isUserVerifyingPlatformAuthenticatorAvailable)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e88-168">Learn more about this API [here](https://www.w3.org/TR/webauthn/#isUserVerifyingPlatformAuthenticatorAvailable).</span></span>
- <span data-ttu-id="a6e88-169">Windows Hello の資格情報を作成する場合は、最適なユーザーエクスペリエンスを設定する必要があり `authenticatorAttachment` `platform` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-169">When creating a credential for Windows Hello, you should set `authenticatorAttachment` to `platform` for the best user experience.</span></span>
- <span data-ttu-id="a6e88-170">Windows Hello は、公開キーアルゴリズムとして RS256 (alg-257) のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a6e88-170">Windows Hello only supports RS256 (alg -257) as its public key algorithm.</span></span> <span data-ttu-id="a6e88-171">資格情報を作成するときは、必ずこのアルゴリズムを指定してください。</span><span class="sxs-lookup"><span data-stu-id="a6e88-171">Be sure to specify this algorithm when creating a credential.</span></span>
- <span data-ttu-id="a6e88-172">[TPM 構成証明ステートメント](https://w3c.github.io/webauthn/#tpm-attestation)を受け取るには、API を呼び出すときに、構成証明を "直接" に設定し `create` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e88-172">To receive a [TPM attestation statement](https://w3c.github.io/webauthn/#tpm-attestation), set attestation to "direct" when calling the `create` API.</span></span> <span data-ttu-id="a6e88-173">TPM の構成証明は、ベストエフォートです。</span><span class="sxs-lookup"><span data-stu-id="a6e88-173">TPM attestation is a best effort.</span></span> <span data-ttu-id="a6e88-174">TPM 2.0 を搭載した Pc のみが TPM 構成証明書を返し、構成証明プロセスはさまざまな理由で失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="a6e88-174">Only PCs with TPM 2.0 will return a TPM attestation statement, and the attestation process could fail for a variety of reasons.</span></span>
- <span data-ttu-id="a6e88-175">Windows Hello には、ユーザーの資格情報を保護するためのさまざまな方法が採用しています。</span><span class="sxs-lookup"><span data-stu-id="a6e88-175">Windows Hello employs a variety of ways to protect user credentials.</span></span> <span data-ttu-id="a6e88-176">資格情報を保護するために使用された認証方法を確認するには、資格情報の作成時に返された構成証明オブジェクトの " [uid](https://w3c.github.io/webauthn/#sec-attested-credential-data) " フィールドを使います。</span><span class="sxs-lookup"><span data-stu-id="a6e88-176">You can check which method has been used to protect a credential by consuming the [AAGUID](https://w3c.github.io/webauthn/#sec-attested-credential-data) field in the attestation object returned at credential creation.</span></span> <span data-ttu-id="a6e88-177">Windows Hello が返すことができる AAGUIDs の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6e88-177">The following is the list of AAGUIDs that Windows Hello may return:</span></span> 
  - <span data-ttu-id="a6e88-178">ソフトウェアでサポートされているオーセンティケータ</span><span class="sxs-lookup"><span data-stu-id="a6e88-178">Software backed authenticators</span></span>
    - <span data-ttu-id="a6e88-179">Windows Hello ソフトウェア認証システム:</span><span class="sxs-lookup"><span data-stu-id="a6e88-179">Windows Hello software authenticator:</span></span> `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`
    - <span data-ttu-id="a6e88-180">Windows Hello VBS software authenticator:</span><span class="sxs-lookup"><span data-stu-id="a6e88-180">Windows Hello VBS software authenticator:</span></span> `6E96969E-A5CF-4AAD-9B56-305FE6C82795`
  - <span data-ttu-id="a6e88-181">トラステッドプラットフォームモジュール (TPM) バックアップされたオーセンティケータ</span><span class="sxs-lookup"><span data-stu-id="a6e88-181">Trusted Platform Module (TPM) backed authenticators</span></span>
    - <span data-ttu-id="a6e88-182">Windows Hello ハードウェア認証システム:</span><span class="sxs-lookup"><span data-stu-id="a6e88-182">Windows Hello hardware authenticator:</span></span> `08987058-CADC-4B81-B6E1-30DE50DCBE96`
    - <span data-ttu-id="a6e88-183">Windows Hello VBS ハードウェア認証システム:</span><span class="sxs-lookup"><span data-stu-id="a6e88-183">Windows Hello VBS hardware authenticator:</span></span> `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`


### <span data-ttu-id="a6e88-184">API サーフェス</span><span class="sxs-lookup"><span data-stu-id="a6e88-184">API surface</span></span>
- <span data-ttu-id="a6e88-185">Microsoft Edge では、基本的な Web 認証仕様の候補の候補を完全に実装しています。</span><span class="sxs-lookup"><span data-stu-id="a6e88-185">Microsoft Edge has a complete implementation of the Candidate Recommendation version of the core Web Authentication specification.</span></span>
- <span data-ttu-id="a6e88-186">[AppID の拡張機能](https://w3c.github.io/webauthn/#sctn-appid-extension)がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e88-186">The [AppID extension](https://w3c.github.io/webauthn/#sctn-appid-extension) is supported.</span></span> 
- <span data-ttu-id="a6e88-187">その他の拡張機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a6e88-187">No other extensions are supported.</span></span>


## <span data-ttu-id="a6e88-188">デモ</span><span class="sxs-lookup"><span data-stu-id="a6e88-188">Demos</span></span>

[<span data-ttu-id="a6e88-189">クライアントとサーバーコードのサンプル</span><span class="sxs-lookup"><span data-stu-id="a6e88-189">Client and server code sample</span></span>](https://github.com/MicrosoftEdge/webauthnsample)

[<span data-ttu-id="a6e88-190">Windows Hello のテストドライブのデモ</span><span class="sxs-lookup"><span data-stu-id="a6e88-190">Windows Hello Test Drive demo</span></span>](https://webauthnsample.azurewebsites.net/)

## <span data-ttu-id="a6e88-191">キャスト</span><span class="sxs-lookup"><span data-stu-id="a6e88-191">Specification</span></span>

[<span data-ttu-id="a6e88-192">Web 認証: 公開キーの資格情報にアクセスするための API</span><span class="sxs-lookup"><span data-stu-id="a6e88-192">Web Authentication: An API for accessing Public Key Credentials</span></span>](http://w3c.github.io/webauthn/)
