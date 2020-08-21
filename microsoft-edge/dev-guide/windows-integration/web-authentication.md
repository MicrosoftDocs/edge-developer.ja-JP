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
# <span data-ttu-id="efc36-104">Web 認証と Windows Hello</span><span class="sxs-lookup"><span data-stu-id="efc36-104">Web Authentication and Windows Hello</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="efc36-105">Microsoft Edge [の Web Authentication API](https://w3c.github.io/webauthn) を使用すると、Web アプリケーションで [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) および [外部の FIDO2](https://fidoalliance.org/fido2) デバイスを使用できるため、パスワードの成功、フィッシング、キー ログ記録アタックの課金など、パスワード管理のあらかじめ、すべてのパスワード管理にパスワード管理のリスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="efc36-105">The [Web Authentication API](https://w3c.github.io/webauthn) in Microsoft Edge enables web applications to use [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) and [external FIDO2 devices](https://fidoalliance.org/fido2) for user authentication so that you and your users can avoid all the hassles and risks of password management, including password guessing, phishing, and key-logging attacks.</span></span>  <span data-ttu-id="efc36-106">現在の Microsoft Edge の実装は、Web 認証固有の推奨事項に基づいています。</span><span class="sxs-lookup"><span data-stu-id="efc36-106">The current Microsoft Edge implementation is based on the Candidate Recommendation of the Web Authentication specification.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="efc36-107">このトピックでは、Microsoft Edge で Windows Hello と FIDO2 の認証を試す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="efc36-107">This topic will show you how to try out Windows Hello and FIDO2 authentication with Microsoft Edge.</span></span>  

<span data-ttu-id="efc36-108">Web 認証を使用すると、サーバーはテキスト形式の問題をブラウザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="efc36-108">Using Web Authentication, the server sends down a plain text challenge to the browser.</span></span>  <span data-ttu-id="efc36-109">Microsoft Edge が Windows Hello または外部 FIDO2 デバイスを通じてユーザーを確認できるようになりました。システムは、以前にプロビジョニングしたプライベート キーで課金され、署名はサーバーに送られます。</span><span class="sxs-lookup"><span data-stu-id="efc36-109">Once Microsoft Edge is able to verify the user through Windows Hello or an external FIDO2 device, the system will sign the challenge with a private key previously provisioned for this user and send the signature back to the server.</span></span>  <span data-ttu-id="efc36-110">サーバーがそのユーザー用の公開キーを使用して署名を検証し、チャレンジが正しいことを確認できる場合は、ユーザーを正しく認証できます。</span><span class="sxs-lookup"><span data-stu-id="efc36-110">If the server can validate the signature using the public key it has for that user and verify the challenge is correct, it can authenticate the user securely.</span></span>  <span data-ttu-id="efc36-111">こ [のような、アイモリティックの同時](https://en.wikipedia.org/wiki/Public-key_cryptography) 実行を使用すると、公開キーが独自に有効でない意味であり、主キーは共有されません。</span><span class="sxs-lookup"><span data-stu-id="efc36-111">With [asymmetric cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) such as this, the public key is meaningless on its own and the private key is never shared.</span></span>  <span data-ttu-id="efc36-112">さらに、TPM 対応のハードウェアを使用して、セキュリティで保護された要素や最新のシステムから、主キーを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="efc36-112">Furthermore, the private key can never be moved from secure elements or modern systems with TPM-enabled hardware.</span></span>  

<span data-ttu-id="efc36-113">Web 認証 API を使用するには、基本的な手順が 2 つ用いらします。</span><span class="sxs-lookup"><span data-stu-id="efc36-113">There are two basic steps to using the Web Authentication API:</span></span>  

1.  <span data-ttu-id="efc36-114">ユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="efc36-114">Register your user with</span></span> `create`  
1.  <span data-ttu-id="efc36-115">ユーザーを認証する</span><span class="sxs-lookup"><span data-stu-id="efc36-115">Authenticate your user with</span></span> `get`  

<span data-ttu-id="efc36-116">次のデベロッパー ガイドでは [、WebAuthn サ](https://github.com/MicrosoftEdge/webauthnsample)ンプル アプリを使用してこのフローを説明します。</span><span class="sxs-lookup"><span data-stu-id="efc36-116">The following dev guide will walk you through this flow using the [WebAuthn Sample App](https://github.com/MicrosoftEdge/webauthnsample).</span></span>  

## <span data-ttu-id="efc36-117">ユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="efc36-117">Register your user</span></span>  

<span data-ttu-id="efc36-118">ID プロバイダーとして実行する場合、まず、方法を使用してユーザーの Web 認証資デベロッシュ割り当てを作成する必要 `navigator.credentials.create` があります。</span><span class="sxs-lookup"><span data-stu-id="efc36-118">Acting as an identity provider, you will first need to create a Web Authentication credential for your user with the `navigator.credentials.create` method.</span></span>  <span data-ttu-id="efc36-119">サーバー上のユーザーに資産情報を登録する前に、ユーザーの ID を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc36-119">Before you register that credential to the user on your server, you will need to confirm the identity of the user.</span></span>  <span data-ttu-id="efc36-120">これは、ユーザーに確認メールで確認を送信するか、従用のログイン方法を使用することを求めて行います。</span><span class="sxs-lookup"><span data-stu-id="efc36-120">This can be done by sending the user an email confirmation or asking them to use their traditional login method.</span></span>  

<span data-ttu-id="efc36-121">メソ `create` ッドは次のパラメーターを実行します。</span><span class="sxs-lookup"><span data-stu-id="efc36-121">The `create` method takes the following parameters:</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="efc36-122">relying party information</span><span class="sxs-lookup"><span data-stu-id="efc36-122">relying party information</span></span>**  
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
      **<span data-ttu-id="efc36-123">ユーザー アカウント情報</span><span class="sxs-lookup"><span data-stu-id="efc36-123">user account information</span></span>**  
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
      **<span data-ttu-id="efc36-124">crypto パラメーター</span><span class="sxs-lookup"><span data-stu-id="efc36-124">crypto parameters</span></span>**  
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
      **<span data-ttu-id="efc36-125">認証パラメーター</span><span class="sxs-lookup"><span data-stu-id="efc36-125">authenticator selection parameters</span></span>**  
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
      **<span data-ttu-id="efc36-126">その他のオプション</span><span class="sxs-lookup"><span data-stu-id="efc36-126">other options</span></span>**  
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

<span data-ttu-id="efc36-127">資情報 [作成パラメーターを使用](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) して、作成する資情報を構成できます。</span><span class="sxs-lookup"><span data-stu-id="efc36-127">You can use [credential creation parameters](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) to configure the credential you want to create.</span></span>  <span data-ttu-id="efc36-128">この場合、設定して外部 FIDO2 デバイスで Windows Hello の資金情報を作成 `authenticatorAttachment` するか、外部の FIDO2 デバイス上でローミング資デ情報を設定することを `platform` `authenticatorAttachment` 選択できます `cross-platform` 。</span><span class="sxs-lookup"><span data-stu-id="efc36-128">In particular, you can choose to create a Windows Hello credential by setting `authenticatorAttachment` to `platform`, or a roaming credential on an external FIDO2 device by setting `authenticatorAttachment` to `cross-platform`.</span></span>  

<span data-ttu-id="efc36-129">この方法を使用すると、最初に Microsoft Edge からユーザーに対して顔または指紋をスキャンするか、PIN を入力するか、外部 FIDO2 デバイスで操作を実行することをユーザーに求 `create` められます。</span><span class="sxs-lookup"><span data-stu-id="efc36-129">When you use the `create` method, Microsoft Edge will first ask the user to verify their presence by scanning their face or fingerprint, entering a PIN, or taking action on an external FIDO2 device.</span></span>  <span data-ttu-id="efc36-130">この手順を完了すると、認証者が公開キー ペアを生成し、主キーを格納します。</span><span class="sxs-lookup"><span data-stu-id="efc36-130">Once this step is completed the authenticator will generate a publicprivate key pair and store the private key.</span></span>  <span data-ttu-id="efc36-131">これらの資人情報は、元のアカウント別に作成され、認証デバイスに保存されているため、取り出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="efc36-131">These credentials are created per origin, per account, and cannot be extracted because they are stored securely to the authentication device.</span></span>  

<span data-ttu-id="efc36-132">結果の確率は、新しい資情報[attestation object](https://w3c.github.io/webauthn#sctn-attestation)を表す属性オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="efc36-132">The resulting promise returns an [attestation object](https://w3c.github.io/webauthn#sctn-attestation) representing the new credential.</span></span>  <span data-ttu-id="efc36-133">属性オブジェクトには、資情報の公開キーが含まれている。</span><span class="sxs-lookup"><span data-stu-id="efc36-133">The attestation object contains the public key for the credential.</span></span>  <span data-ttu-id="efc36-134">以降の認証を検証するため、このオブジェクトをサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="efc36-134">You'll send this object to the server for validating future authentications.</span></span>  <span data-ttu-id="efc36-135">サーバーに戻る前に、生データをベースにして、元のデータをベースにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc36-135">Before sending back to the server, you'll need to base64-encode the raw data.</span></span>  

**<span data-ttu-id="efc36-136">クライアント</span><span class="sxs-lookup"><span data-stu-id="efc36-136">Client</span></span>**  

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

<span data-ttu-id="efc36-137">次に、サーバーは、接続テスト オブジェクトをデコードし、認証手順を実行し、この資ートの公開キーを削除し、以降の認証用に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc36-137">The server should then decode the attestation object, perform verification steps, extract the public key for this credential, and store it for future authentications.</span></span>  <span data-ttu-id="efc36-138">WebAuthn の指定の資格情報登録アルゴ [リズ](https://w3c.github.io/webauthn#registering-a-new-credential) ムに記入して詳細な手順の一覧を見つけます。</span><span class="sxs-lookup"><span data-stu-id="efc36-138">A detailed list of steps can be found in the [credential registration algorithm](https://w3c.github.io/webauthn#registering-a-new-credential) in the WebAuthn specification.</span></span>  

**<span data-ttu-id="efc36-139">Server</span><span class="sxs-lookup"><span data-stu-id="efc36-139">Server</span></span>**  

```javascript
    attestationObject = cbor.decodeFirstSync(Buffer.from(attestation.attestationObject, 'base64'));
    authenticatorData = parseAuthenticatorData(attestationObject.authData);
    var credential = await storage.Credentials.create({
        id: authenticatorData.attestedCredentialData.credentialId.toString('base64'),
        publicKeyJwk: authenticatorData.attestedCredentialData.publicKeyJwk,
        signCount: authenticatorData.signCount
    });
```  

## <span data-ttu-id="efc36-140">ユーザーを認証する</span><span class="sxs-lookup"><span data-stu-id="efc36-140">Authenticate your user</span></span>  

<span data-ttu-id="efc36-141">クライアントに資ーデンシャルが作成されると、次回ユーザーがサイトにログインしながら、ユーザーがサイトにログインしなくても、パスワードの代わりに Web 認証資デンシャルを使用してサインインできるようになります `navigator.credentials.get` 。</span><span class="sxs-lookup"><span data-stu-id="efc36-141">Once the credential is created on the client, the next time the user attempts to log into the site you can offer to sign them in using their Web Authentication credential instead of a password with a call to `navigator.credentials.get`.</span></span>  

<span data-ttu-id="efc36-142">この `get` メソッドは、必須のパラメーターのみのチャレンジを取り上げられます。</span><span class="sxs-lookup"><span data-stu-id="efc36-142">The `get` method takes the challenge as its only required parameter.</span></span>  <span data-ttu-id="efc36-143">チャレンジとは、サーバーがクライアントに送信してユーザーのプライベート キーでサインインする操作の操作に使用するバイトです。</span><span class="sxs-lookup"><span data-stu-id="efc36-143">The challenge is an opaque sequence of bytes that the server will send down to a client to sign with the user's private key.</span></span>  <span data-ttu-id="efc36-144">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="efc36-144">For example:</span></span>  

**<span data-ttu-id="efc36-145">Server</span><span class="sxs-lookup"><span data-stu-id="efc36-145">Server</span></span>**  

```javascript
    var jwt = require('jsonwebtoken');
    var jwt_secret = "defaultsecret";
    fido.getChallenge = () => {
        return jwt.sign({}, jwt_secret, {
            expiresIn: 120 * 1000
        });
    };
```  

<span data-ttu-id="efc36-146">サーバーからチャレンジを取得した後、API と資格情報要求オプションを [呼び出します](https://w3c.github.io/webauthn#credentialrequestoptions-extension)。</span><span class="sxs-lookup"><span data-stu-id="efc36-146">After retrieving a challenge from the server, you'll call the get API along with [credential request options](https://w3c.github.io/webauthn#credentialrequestoptions-extension).</span></span>  <span data-ttu-id="efc36-147">Microsoft Edge に、Windows Hello または外付け FIDO2 デバイスを使用してユーザーの ID を確認するプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efc36-147">Microsoft Edge will show a prompt, which will verify the identity of the user using Windows Hello or an external FIDO2 device.</span></span>  <span data-ttu-id="efc36-148">ユーザーが確認されると、TPM または FIDO2 デバイス内でチャレンジが付けられます。確率は、サーバーに送信する署名などの[assertion object](https://w3c.github.io/webauthn#authenticatorassertionresponse)メタデータを含むアサーション オブジェクトとともに返されます。</span><span class="sxs-lookup"><span data-stu-id="efc36-148">After the user is verified, the challenge will be signed within the TPM or FIDO2 device and the promise will return with an [assertion object](https://w3c.github.io/webauthn#authenticatorassertionresponse) that contains the signature and other metadata for you to send to the server.</span></span>  

**<span data-ttu-id="efc36-149">クライアント</span><span class="sxs-lookup"><span data-stu-id="efc36-149">Client</span></span>**  

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

<span data-ttu-id="efc36-150">サーバーでアシスタリングを受信したら、署名を検証してユーザーを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc36-150">Once you receive the assertion on the server, you will need to validate the signature to authenticate the user.</span></span>  <span data-ttu-id="efc36-151">次に、コードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="efc36-151">The following is some sample code.</span></span>  <span data-ttu-id="efc36-152">WebAuthn の指定のアサーションの検証アルゴ [リ](https://w3c.github.io/webauthn#verifying-assertion) ズムに記入して詳細な手順の一覧を記入できます。</span><span class="sxs-lookup"><span data-stu-id="efc36-152">A detailed list of steps can be found in the [assertion verification algorithm](https://w3c.github.io/webauthn#verifying-assertion) in the WebAuthn specification.</span></span>  

**<span data-ttu-id="efc36-153">Server</span><span class="sxs-lookup"><span data-stu-id="efc36-153">Server</span></span>**  

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

## <span data-ttu-id="efc36-154">実装上の注意</span><span class="sxs-lookup"><span data-stu-id="efc36-154">Implementation notes</span></span>  

### <span data-ttu-id="efc36-155">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="efc36-155">Supported platforms</span></span>  

*   <span data-ttu-id="efc36-156">Web 認証 API の推奨バージョンは、Microsoft EdgeHTML 18 以降 (Windows Insider Preview バージョン 17713 以降) 以降の Microsoft Edge から使用できます。</span><span class="sxs-lookup"><span data-stu-id="efc36-156">The Candidate Recommendation version of the Web Authentication API can be used from Microsoft Edge beginning with EdgeHTML 18 \(Windows Insider Preview version 17713 or newer\).</span></span>  
*   <span data-ttu-id="efc36-157">プ [レフィックス化済み、](https://blogs.windows.com/msedgedev/2016/04/12) プレビュー バージョンが削除され、利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="efc36-157">The [prefixed, preview version](https://blogs.windows.com/msedgedev/2016/04/12) of the Web Authentication API has been removed and is no longer available.</span></span>  
*   <span data-ttu-id="efc36-158">Web 認証 API は、UWP アプリおよび PWA ではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="efc36-158">The Web Authentication API is not yet available to UWP apps and PWAs.</span></span>  
*   <span data-ttu-id="efc36-159">Internet Explorer Web 認証 API はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="efc36-159">Internet Explorer does not support the Web Authentication API.</span></span>  

### <span data-ttu-id="efc36-160">サポートされている認証</span><span class="sxs-lookup"><span data-stu-id="efc36-160">Supported authenticators</span></span>  

<span data-ttu-id="efc36-161">Microsoft Edge の Web 認証 API を使用すると、次のテクノロジを使用してユーザーを認証できます。</span><span class="sxs-lookup"><span data-stu-id="efc36-161">With the Web Authentication API in Microsoft Edge, you can authenticate users with the following technologies:</span></span>  

*   <span data-ttu-id="efc36-162">**Windows Hello**  顔認証、指紋、または PIN でパスワードなしデバイス認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="efc36-162">**Windows Hello**  Enables passwordless on-device authentication with  face, fingerprint, or PIN</span></span>  
*   <span data-ttu-id="efc36-163">**FIDO2**  リムーバブル デバイスと指紋または PIN を使用したパスワードなしのローミング認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="efc36-163">**FIDO2**  Enables passwordless roaming authentication with a removable device and a fingerprint or PIN</span></span>  
*   <span data-ttu-id="efc36-164">**U2F**  パスワードをレスクリプト モデルに移行する準備ができていない Web サイトの第 2 要素認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="efc36-164">**U2F**  Enables strong second factor authentication for websites that are not ready to move to a passwordless model</span></span>  

### <span data-ttu-id="efc36-165">Windows Hello の特別な考慮事文</span><span class="sxs-lookup"><span data-stu-id="efc36-165">Special considerations for Windows Hello</span></span>  

<span data-ttu-id="efc36-166">Windows Hello 認証を使用する場合は、次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="efc36-166">A few things to note when using the Windows Hello authenticator:</span></span>  

*   <span data-ttu-id="efc36-167">API を呼び出すことで、PC で Windows Hello を利用できるかを `isUserVerifyingPlatformAuthenticatorAvailable` 検出できます。</span><span class="sxs-lookup"><span data-stu-id="efc36-167">You can detect if Windows Hello is available on a PC by calling the `isUserVerifyingPlatformAuthenticatorAvailable` API.</span></span>  <span data-ttu-id="efc36-168">この API の詳細については、こちら [をご覧ください](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable)。</span><span class="sxs-lookup"><span data-stu-id="efc36-168">Learn more about this API [here](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable).</span></span>  
*   <span data-ttu-id="efc36-169">Windows Hello の資情報を作成する場合は、最高のユーザー エクスペリエンス `authenticatorAttachment` `platform` を得るように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc36-169">When creating a credential for Windows Hello, you should set `authenticatorAttachment` to `platform` for the best user experience.</span></span>
*   <span data-ttu-id="efc36-170">Windows Hello は、公開キー アルゴリズムとして RS256 \(alg -257\) のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="efc36-170">Windows Hello only supports RS256 \(alg -257\) as its public key algorithm.</span></span>  <span data-ttu-id="efc36-171">資格情報を作成するときには必ずこのアルゴリズムを指定してください。</span><span class="sxs-lookup"><span data-stu-id="efc36-171">Be sure to specify this algorithm when creating a credential.</span></span>  
*   <span data-ttu-id="efc36-172">TPM の呼び出しステートメン [トを受け取るには](https://w3c.github.io/webauthn#tpm-attestation)、API を呼び出すときに "direct" に設定 `create` します。</span><span class="sxs-lookup"><span data-stu-id="efc36-172">To receive a [TPM attestation statement](https://w3c.github.io/webauthn#tpm-attestation), set attestation to "direct" when calling the `create` API.</span></span>  <span data-ttu-id="efc36-173">TPM のテストは、最も効果的です。</span><span class="sxs-lookup"><span data-stu-id="efc36-173">TPM attestation is a best effort.</span></span>  <span data-ttu-id="efc36-174">TPM 2.0 を使用する PC のみが TPM の Attestation ステートメントを返し、さまざまな理えで、試行中のプロセスが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="efc36-174">Only PCs with TPM 2.0 will return a TPM attestation statement, and the attestation process could fail for a variety of reasons.</span></span>  
*   <span data-ttu-id="efc36-175">Windows Hello では、ユーザーの資格情報を保護するさまざまな方法を利用できます。</span><span class="sxs-lookup"><span data-stu-id="efc36-175">Windows Hello employs a variety of ways to protect user credentials.</span></span>  <span data-ttu-id="efc36-176">資情報の作成時に返される属性オブジェクト [の AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) フィールドを使用することで、資情報を保護するために使用された方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="efc36-176">You can check which method has been used to protect a credential by consuming the [AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) field in the attestation object returned at credential creation.</span></span>  <span data-ttu-id="efc36-177">Windows Hello が返す可能性のある AAGUI には、次のような一覧が示されます。</span><span class="sxs-lookup"><span data-stu-id="efc36-177">The following is the list of AAGUIDs that Windows Hello may return:</span></span>   
    *   <span data-ttu-id="efc36-178">ソフトウェアが再び認証された認証</span><span class="sxs-lookup"><span data-stu-id="efc36-178">Software backed authenticators</span></span>  
        *   <span data-ttu-id="efc36-179">Windows Hello ソフトウェア認証:</span><span class="sxs-lookup"><span data-stu-id="efc36-179">Windows Hello software authenticator:</span></span>  `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`  
        *   <span data-ttu-id="efc36-180">Windows Hello VBS ソフトウェア認証ツール:</span><span class="sxs-lookup"><span data-stu-id="efc36-180">Windows Hello VBS software authenticator:</span></span>  `6E96969E-A5CF-4AAD-9B56-305FE6C82795`  
    *   <span data-ttu-id="efc36-181">信頼できるプラットフォーム モジュール \(TPM\) バイト認証</span><span class="sxs-lookup"><span data-stu-id="efc36-181">Trusted Platform Module \(TPM\) backed authenticators</span></span>  
        *   <span data-ttu-id="efc36-182">Windows Hello ハードウェア認証機能:</span><span class="sxs-lookup"><span data-stu-id="efc36-182">Windows Hello hardware authenticator:</span></span>  `08987058-CADC-4B81-B6E1-30DE50DCBE96`  
        *   <span data-ttu-id="efc36-183">Windows Hello VBS ハードウェア認証:</span><span class="sxs-lookup"><span data-stu-id="efc36-183">Windows Hello VBS hardware authenticator:</span></span>  `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`  

### <span data-ttu-id="efc36-184">API サーフェイス</span><span class="sxs-lookup"><span data-stu-id="efc36-184">API surface</span></span>  

*   <span data-ttu-id="efc36-185">Microsoft Edge には、コア Web 認証の推奨バージョンの完全な実装があります。</span><span class="sxs-lookup"><span data-stu-id="efc36-185">Microsoft Edge has a complete implementation of the Candidate Recommendation version of the core Web Authentication specification.</span></span>  
*   <span data-ttu-id="efc36-186">[AppID の拡張子がサポート](https://w3c.github.io/webauthn#sctn-appid-extension)されています。</span><span class="sxs-lookup"><span data-stu-id="efc36-186">The [AppID extension](https://w3c.github.io/webauthn#sctn-appid-extension) is supported.</span></span>  
*   <span data-ttu-id="efc36-187">他の拡張機能はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="efc36-187">No other extensions are supported.</span></span>  

## <span data-ttu-id="efc36-188">デモ</span><span class="sxs-lookup"><span data-stu-id="efc36-188">Demos</span></span>  

[<span data-ttu-id="efc36-189">クライアントとサーバーのコード サンプル</span><span class="sxs-lookup"><span data-stu-id="efc36-189">Client and server code sample</span></span>](https://github.com/MicrosoftEdge/webauthnsample)  

[<span data-ttu-id="efc36-190">Windows Hello テスト ドライブのデモ</span><span class="sxs-lookup"><span data-stu-id="efc36-190">Windows Hello Test Drive demo</span></span>](https://webauthnsample.azurewebsites.net)  

## <span data-ttu-id="efc36-191">Specification</span><span class="sxs-lookup"><span data-stu-id="efc36-191">Specification</span></span>  

[<span data-ttu-id="efc36-192">Web 認証: パブリック キー資情報にアクセスする API</span><span class="sxs-lookup"><span data-stu-id="efc36-192">Web Authentication: An API for accessing Public Key Credentials</span></span>](http://w3c.github.io/webauthn)  
