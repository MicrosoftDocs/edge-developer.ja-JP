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
# <span data-ttu-id="5a2ec-104">Web 認証と Windows Hello</span><span class="sxs-lookup"><span data-stu-id="5a2ec-104">Web Authentication and Windows Hello</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="5a2ec-105">Microsoft Edge の Web 認証 [API](https://w3c.github.io/webauthn) を使用すると、Web アプリケーションはユーザー認証に [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) デバイスと外部 [FIDO2](https://fidoalliance.org/fido2) デバイスを使用できます。これにより、ユーザーはパスワードの推測、フィッシング、キー ログ攻撃など、パスワード管理の面倒やリスクを回避できます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-105">The [Web Authentication API](https://w3c.github.io/webauthn) in Microsoft Edge enables web applications to use [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) and [external FIDO2 devices](https://fidoalliance.org/fido2) for user authentication so that you and your users can avoid all the hassles and risks of password management, including password guessing, phishing, and key-logging attacks.</span></span>  <span data-ttu-id="5a2ec-106">現在の Microsoft Edge の実装は、Web 認証仕様の推奨候補に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-106">The current Microsoft Edge implementation is based on the Candidate Recommendation of the Web Authentication specification.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="5a2ec-107">このトピックでは、Microsoft Edge で Windows Hello 認証と FIDO2 認証を試す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-107">This topic will show you how to try out Windows Hello and FIDO2 authentication with Microsoft Edge.</span></span>  

<span data-ttu-id="5a2ec-108">Web 認証を使用すると、サーバーはプレーンテキストのチャレンジをブラウザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-108">Using Web Authentication, the server sends down a plain text challenge to the browser.</span></span>  <span data-ttu-id="5a2ec-109">Microsoft Edge が Windows Hello または外部 FIDO2 デバイスを介してユーザーを確認できると、システムは以前にこのユーザーにプロビジョニングされたプライベート キーを使用してチャレンジに署名し、署名をサーバーに送り返します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-109">Once Microsoft Edge is able to verify the user through Windows Hello or an external FIDO2 device, the system will sign the challenge with a private key previously provisioned for this user and send the signature back to the server.</span></span>  <span data-ttu-id="5a2ec-110">サーバーが、そのユーザーに対して持っている公開キーを使用して署名を検証し、チャレンジが正しいと確認できる場合は、ユーザーを安全に認証できます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-110">If the server can validate the signature using the public key it has for that user and verify the challenge is correct, it can authenticate the user securely.</span></span>  <span data-ttu-id="5a2ec-111">このような [非対称暗号化](https://en.wikipedia.org/wiki/Public-key_cryptography) では、公開キーはそれ自身に意味を持たなく、公開キーは共有されるのを一度も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-111">With [asymmetric cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) such as this, the public key is meaningless on its own and the private key is never shared.</span></span>  <span data-ttu-id="5a2ec-112">さらに、TPM が有効なハードウェアを備え、セキュリティで保護された要素や最新のシステムから、プライベート キーを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-112">Furthermore, the private key can never be moved from secure elements or modern systems with TPM-enabled hardware.</span></span>  

<span data-ttu-id="5a2ec-113">Web 認証 API を使用するには、次の 2 つの基本的な手順があります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-113">There are two basic steps to using the Web Authentication API:</span></span>  

1.  <span data-ttu-id="5a2ec-114">ユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="5a2ec-114">Register your user with</span></span> `create`  
1.  <span data-ttu-id="5a2ec-115">ユーザーを認証する</span><span class="sxs-lookup"><span data-stu-id="5a2ec-115">Authenticate your user with</span></span> `get`  

<span data-ttu-id="5a2ec-116">次の開発ガイドでは [、WebAuthn](https://github.com/MicrosoftEdge/webauthnsample)サンプル アプリを使用してこのフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-116">The following dev guide will walk you through this flow using the [WebAuthn Sample App](https://github.com/MicrosoftEdge/webauthnsample).</span></span>  

## <span data-ttu-id="5a2ec-117">ユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="5a2ec-117">Register your user</span></span>  

<span data-ttu-id="5a2ec-118">ID プロバイダーとして機能するには、まず、メソッドを使用してユーザーの Web 認証資格情報を作成する必要 `navigator.credentials.create` があります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-118">Acting as an identity provider, you will first need to create a Web Authentication credential for your user with the `navigator.credentials.create` method.</span></span>  <span data-ttu-id="5a2ec-119">サーバー上のユーザーに資格情報を登録する前に、ユーザーの ID を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-119">Before you register that credential to the user on your server, you will need to confirm the identity of the user.</span></span>  <span data-ttu-id="5a2ec-120">これは、ユーザーに電子メールの確認を送信するか、従来のログイン方法を使用してユーザーに要求することで行えます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-120">This can be done by sending the user an email confirmation or asking them to use their traditional login method.</span></span>  

<span data-ttu-id="5a2ec-121">この `create` メソッドは、次のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-121">The `create` method takes the following parameters:</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="5a2ec-122">証明書利用者情報</span><span class="sxs-lookup"><span data-stu-id="5a2ec-122">relying party information</span></span>**  
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
      **<span data-ttu-id="5a2ec-123">ユーザー アカウント情報</span><span class="sxs-lookup"><span data-stu-id="5a2ec-123">user account information</span></span>**  
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
      **<span data-ttu-id="5a2ec-124">crypto パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a2ec-124">crypto parameters</span></span>**  
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
      **<span data-ttu-id="5a2ec-125">authenticator の選択パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a2ec-125">authenticator selection parameters</span></span>**  
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
      **<span data-ttu-id="5a2ec-126">その他のオプション</span><span class="sxs-lookup"><span data-stu-id="5a2ec-126">other options</span></span>**  
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

<span data-ttu-id="5a2ec-127">資格情報の作成 [パラメーターを使用して](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) 、作成する資格情報を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-127">You can use [credential creation parameters](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) to configure the credential you want to create.</span></span>  <span data-ttu-id="5a2ec-128">特に、Windows Hello の資格情報を作成するには、次の値に設定するか、外部 FIDO2 デバイスでローミング資格情報を `authenticatorAttachment` `platform` 作成 `authenticatorAttachment` します `cross-platform` 。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-128">In particular, you can choose to create a Windows Hello credential by setting `authenticatorAttachment` to `platform`, or a roaming credential on an external FIDO2 device by setting `authenticatorAttachment` to `cross-platform`.</span></span>  

<span data-ttu-id="5a2ec-129">このメソッドを使用すると、Microsoft Edge は最初に、顔や指紋をスキャンしたり、PIN を入力したり、外部の FIDO2 デバイスでアクションを実行したりして、ユーザーにプレゼンスの確認を求めるメッセージを表示します。 `create`</span><span class="sxs-lookup"><span data-stu-id="5a2ec-129">When you use the `create` method, Microsoft Edge will first ask the user to verify their presence by scanning their face or fingerprint, entering a PIN, or taking action on an external FIDO2 device.</span></span>  <span data-ttu-id="5a2ec-130">この手順が完了すると、認証者は公開主キーペアを生成し、そのキーを保存します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-130">Once this step is completed the authenticator will generate a publicprivate key pair and store the private key.</span></span>  <span data-ttu-id="5a2ec-131">これらの資格情報は、認証デバイスに安全に保存されるので、作成元ごとにアカウントごとに作成され、抽出できません。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-131">These credentials are created per origin, per account, and cannot be extracted because they are stored securely to the authentication device.</span></span>  

<span data-ttu-id="5a2ec-132">結果の promise は、新しい資格情報 [を表す](https://w3c.github.io/webauthn#sctn-attestation) 構成証明オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-132">The resulting promise returns an [attestation object](https://w3c.github.io/webauthn#sctn-attestation) representing the new credential.</span></span>  <span data-ttu-id="5a2ec-133">構成証明オブジェクトには、資格情報の公開キーが含まれている。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-133">The attestation object contains the public key for the credential.</span></span>  <span data-ttu-id="5a2ec-134">将来の認証を検証するために、このオブジェクトをサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-134">You'll send this object to the server for validating future authentications.</span></span>  <span data-ttu-id="5a2ec-135">サーバーに送り返す前に、base64 で生データをエンコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-135">Before sending back to the server, you'll need to base64-encode the raw data.</span></span>  

**<span data-ttu-id="5a2ec-136">クライアント</span><span class="sxs-lookup"><span data-stu-id="5a2ec-136">Client</span></span>**  

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

<span data-ttu-id="5a2ec-137">サーバーは、構成証明オブジェクトをデコードし、検証手順を実行し、この資格情報の公開キーを抽出して、将来の認証のために保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-137">The server should then decode the attestation object, perform verification steps, extract the public key for this credential, and store it for future authentications.</span></span>  <span data-ttu-id="5a2ec-138">手順の詳細な一覧は、WebAuthn 仕様の資格情報登録 [アルゴリズム](https://w3c.github.io/webauthn#registering-a-new-credential) で確認できます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-138">A detailed list of steps can be found in the [credential registration algorithm](https://w3c.github.io/webauthn#registering-a-new-credential) in the WebAuthn specification.</span></span>  

**<span data-ttu-id="5a2ec-139">Server</span><span class="sxs-lookup"><span data-stu-id="5a2ec-139">Server</span></span>**  

```javascript
    attestationObject = cbor.decodeFirstSync(Buffer.from(attestation.attestationObject, 'base64'));
    authenticatorData = parseAuthenticatorData(attestationObject.authData);
    var credential = await storage.Credentials.create({
        id: authenticatorData.attestedCredentialData.credentialId.toString('base64'),
        publicKeyJwk: authenticatorData.attestedCredentialData.publicKeyJwk,
        signCount: authenticatorData.signCount
    });
```  

## <span data-ttu-id="5a2ec-140">ユーザーを認証する</span><span class="sxs-lookup"><span data-stu-id="5a2ec-140">Authenticate your user</span></span>  

<span data-ttu-id="5a2ec-141">クライアントで資格情報が作成されると、次回ユーザーがサイトにログインしようとして、パスワードの代わりに Web 認証資格情報を使用してサインインして呼び出しを実行できます `navigator.credentials.get` 。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-141">Once the credential is created on the client, the next time the user attempts to log into the site you can offer to sign them in using their Web Authentication credential instead of a password with a call to `navigator.credentials.get`.</span></span>  

<span data-ttu-id="5a2ec-142">この `get` メソッドは、唯一の必須パラメーターとしてチャレンジを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-142">The `get` method takes the challenge as its only required parameter.</span></span>  <span data-ttu-id="5a2ec-143">課題は、サーバーがクライアントに送信してユーザーのプライベート キーで署名する、不透明なバイト シーケンスです。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-143">The challenge is an opaque sequence of bytes that the server will send down to a client to sign with the user's private key.</span></span>  <span data-ttu-id="5a2ec-144">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-144">For example:</span></span>  

**<span data-ttu-id="5a2ec-145">Server</span><span class="sxs-lookup"><span data-stu-id="5a2ec-145">Server</span></span>**  

```javascript
    var jwt = require('jsonwebtoken');
    var jwt_secret = "defaultsecret";
    fido.getChallenge = () => {
        return jwt.sign({}, jwt_secret, {
            expiresIn: 120 * 1000
        });
    };
```  

<span data-ttu-id="5a2ec-146">サーバーからチャレンジを取得した後、資格情報要求オプションと共に get API [を呼び出します](https://w3c.github.io/webauthn#credentialrequestoptions-extension)。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-146">After retrieving a challenge from the server, you'll call the get API along with [credential request options](https://w3c.github.io/webauthn#credentialrequestoptions-extension).</span></span>  <span data-ttu-id="5a2ec-147">Microsoft Edge には、Windows Hello または外部 FIDO2 デバイスを使用しているユーザーの ID を確認するプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-147">Microsoft Edge will show a prompt, which will verify the identity of the user using Windows Hello or an external FIDO2 device.</span></span>  <span data-ttu-id="5a2ec-148">ユーザーが確認された後、チャレンジは TPM または FIDO2 デバイス内で署名され、Promise は、[](https://w3c.github.io/webauthn#authenticatorassertionresponse)サーバーに送信する署名と他のメタデータを含むアサーション オブジェクトで戻されます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-148">After the user is verified, the challenge will be signed within the TPM or FIDO2 device and the promise will return with an [assertion object](https://w3c.github.io/webauthn#authenticatorassertionresponse) that contains the signature and other metadata for you to send to the server.</span></span>  

**<span data-ttu-id="5a2ec-149">クライアント</span><span class="sxs-lookup"><span data-stu-id="5a2ec-149">Client</span></span>**  

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

<span data-ttu-id="5a2ec-150">サーバーでアサーションを受け取った後、ユーザーを認証するために署名を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-150">Once you receive the assertion on the server, you will need to validate the signature to authenticate the user.</span></span>  <span data-ttu-id="5a2ec-151">サンプル コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-151">The following is some sample code.</span></span>  <span data-ttu-id="5a2ec-152">手順の詳細な一覧は、WebAuthn 仕様の [アサーション検証アルゴリズム](https://w3c.github.io/webauthn#verifying-assertion) に記載されています。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-152">A detailed list of steps can be found in the [assertion verification algorithm](https://w3c.github.io/webauthn#verifying-assertion) in the WebAuthn specification.</span></span>  

**<span data-ttu-id="5a2ec-153">Server</span><span class="sxs-lookup"><span data-stu-id="5a2ec-153">Server</span></span>**  

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

## <span data-ttu-id="5a2ec-154">実装上の注意</span><span class="sxs-lookup"><span data-stu-id="5a2ec-154">Implementation notes</span></span>  

### <span data-ttu-id="5a2ec-155">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="5a2ec-155">Supported platforms</span></span>  

*   <span data-ttu-id="5a2ec-156">Web 認証 API の候補推奨バージョンは、EdgeHTML 18 \(Windows Insider Preview バージョン 17713 以降\) で始まる Microsoft Edge から使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-156">The Candidate Recommendation version of the Web Authentication API can be used from Microsoft Edge beginning with EdgeHTML 18 \(Windows Insider Preview version 17713 or newer\).</span></span>  
*   <span data-ttu-id="5a2ec-157">プレフィックス [付きプレビュー バージョンの](https://blogs.windows.com/msedgedev/2016/04/12) Web 認証 API は削除され、使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-157">The [prefixed, preview version](https://blogs.windows.com/msedgedev/2016/04/12) of the Web Authentication API has been removed and is no longer available.</span></span>  
*   <span data-ttu-id="5a2ec-158">Web 認証 API は、UWP アプリと PAS ではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-158">The Web Authentication API is not yet available to UWP apps and PWAs.</span></span>  
*   <span data-ttu-id="5a2ec-159">Internet Explorer、Web 認証 API はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-159">Internet Explorer does not support the Web Authentication API.</span></span>  

### <span data-ttu-id="5a2ec-160">サポートされている認証システム</span><span class="sxs-lookup"><span data-stu-id="5a2ec-160">Supported authenticators</span></span>  

<span data-ttu-id="5a2ec-161">Microsoft Edge の Web 認証 API を使用すると、次のテクノロジを使用してユーザーを認証できます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-161">With the Web Authentication API in Microsoft Edge, you can authenticate users with the following technologies:</span></span>  

*   <span data-ttu-id="5a2ec-162">**Windows Hello**  顔認証、指紋認証、または PIN によるパスワードレスオンデバイス認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="5a2ec-162">**Windows Hello**  Enables passwordless on-device authentication with  face, fingerprint, or PIN</span></span>  
*   <span data-ttu-id="5a2ec-163">**FIDO2**  リムーバブル デバイスと指紋または PIN によるパスワードレス ローミング認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-163">**FIDO2**  Enables passwordless roaming authentication with a removable device and a fingerprint or PIN</span></span>  
*   <span data-ttu-id="5a2ec-164">**U2F**  パスワードレス モデルに移行する準備ができていない Web サイトに対して、強力な第 2 要素認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-164">**U2F**  Enables strong second factor authentication for websites that are not ready to move to a passwordless model</span></span>  

### <span data-ttu-id="5a2ec-165">Windows Hello に関する特別な考慮事項</span><span class="sxs-lookup"><span data-stu-id="5a2ec-165">Special considerations for Windows Hello</span></span>  

<span data-ttu-id="5a2ec-166">Windows Hello 認証システムを使用する場合の注意点は次の通りです。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-166">A few things to note when using the Windows Hello authenticator:</span></span>  

*   <span data-ttu-id="5a2ec-167">API を呼び出して、PC で Windows Hello が利用可能な場合に検出 `isUserVerifyingPlatformAuthenticatorAvailable` できます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-167">You can detect if Windows Hello is available on a PC by calling the `isUserVerifyingPlatformAuthenticatorAvailable` API.</span></span>  <span data-ttu-id="5a2ec-168">この API の詳細については、こちらを参照 [してください](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable)。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-168">Learn more about this API [here](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable).</span></span>  
*   <span data-ttu-id="5a2ec-169">Windows Hello の資格情報を作成する場合は、最適なユーザー エクスペリエンス `authenticatorAttachment` `platform` を提供するために設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-169">When creating a credential for Windows Hello, you should set `authenticatorAttachment` to `platform` for the best user experience.</span></span>
*   <span data-ttu-id="5a2ec-170">Windows Hello は、公開キー アルゴリズムとして RS256 \(alg -257\) のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-170">Windows Hello only supports RS256 \(alg -257\) as its public key algorithm.</span></span>  <span data-ttu-id="5a2ec-171">資格情報を作成する場合は、必ずこのアルゴリズムを指定してください。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-171">Be sure to specify this algorithm when creating a credential.</span></span>  
*   <span data-ttu-id="5a2ec-172">TPM 構成証明 [ステートメントを受信するには](https://w3c.github.io/webauthn#tpm-attestation)、API を呼び出す際に構成証明を "ダイレクト" に設定 `create` します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-172">To receive a [TPM attestation statement](https://w3c.github.io/webauthn#tpm-attestation), set attestation to "direct" when calling the `create` API.</span></span>  <span data-ttu-id="5a2ec-173">TPM の構成証明は最善の取り組みです。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-173">TPM attestation is a best effort.</span></span>  <span data-ttu-id="5a2ec-174">TPM 2.0 を備える PC だけが TPM 構成証明ステートメントを返し、構成証明プロセスはさまざまな理由で失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-174">Only PCs with TPM 2.0 will return a TPM attestation statement, and the attestation process could fail for a variety of reasons.</span></span>  
*   <span data-ttu-id="5a2ec-175">Windows Hello では、ユーザーの資格情報を保護するさまざまな方法が採用されています。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-175">Windows Hello employs a variety of ways to protect user credentials.</span></span>  <span data-ttu-id="5a2ec-176">資格情報の作成時に返される構成証明オブジェクトの [AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) フィールドを使用して、資格情報の保護に使用されたメソッドを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-176">You can check which method has been used to protect a credential by consuming the [AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) field in the attestation object returned at credential creation.</span></span>  <span data-ttu-id="5a2ec-177">Windows Hello が返す AAGUID の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-177">The following is the list of AAGUIDs that Windows Hello may return:</span></span>   
    *   <span data-ttu-id="5a2ec-178">ソフトウェア バックアップ認証</span><span class="sxs-lookup"><span data-stu-id="5a2ec-178">Software backed authenticators</span></span>  
        *   <span data-ttu-id="5a2ec-179">Windows Hello ソフトウェア認証システム:</span><span class="sxs-lookup"><span data-stu-id="5a2ec-179">Windows Hello software authenticator:</span></span>  `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`  
        *   <span data-ttu-id="5a2ec-180">Windows Hello VBS ソフトウェア認証システム:</span><span class="sxs-lookup"><span data-stu-id="5a2ec-180">Windows Hello VBS software authenticator:</span></span>  `6E96969E-A5CF-4AAD-9B56-305FE6C82795`  
    *   <span data-ttu-id="5a2ec-181">トラステッド プラットフォーム モジュール \(TPM\) ベースの認証システム</span><span class="sxs-lookup"><span data-stu-id="5a2ec-181">Trusted Platform Module \(TPM\) backed authenticators</span></span>  
        *   <span data-ttu-id="5a2ec-182">Windows Hello ハードウェア認証システム:</span><span class="sxs-lookup"><span data-stu-id="5a2ec-182">Windows Hello hardware authenticator:</span></span>  `08987058-CADC-4B81-B6E1-30DE50DCBE96`  
        *   <span data-ttu-id="5a2ec-183">Windows Hello VBS ハードウェア認証システム:</span><span class="sxs-lookup"><span data-stu-id="5a2ec-183">Windows Hello VBS hardware authenticator:</span></span>  `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`  

### <span data-ttu-id="5a2ec-184">API サーフェス</span><span class="sxs-lookup"><span data-stu-id="5a2ec-184">API surface</span></span>  

*   <span data-ttu-id="5a2ec-185">Microsoft Edge には、主要な Web 認証仕様の候補推奨バージョンの完全な実装があります。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-185">Microsoft Edge has a complete implementation of the Candidate Recommendation version of the core Web Authentication specification.</span></span>  
*   <span data-ttu-id="5a2ec-186">[AppID 拡張機能](https://w3c.github.io/webauthn#sctn-appid-extension)がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-186">The [AppID extension](https://w3c.github.io/webauthn#sctn-appid-extension) is supported.</span></span>  
*   <span data-ttu-id="5a2ec-187">他の拡張機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5a2ec-187">No other extensions are supported.</span></span>  

## <span data-ttu-id="5a2ec-188">デモ</span><span class="sxs-lookup"><span data-stu-id="5a2ec-188">Demos</span></span>  

[<span data-ttu-id="5a2ec-189">クライアントとサーバーのコード サンプル</span><span class="sxs-lookup"><span data-stu-id="5a2ec-189">Client and server code sample</span></span>](https://github.com/MicrosoftEdge/webauthnsample)  

[<span data-ttu-id="5a2ec-190">Windows Hello テスト ドライブのデモ</span><span class="sxs-lookup"><span data-stu-id="5a2ec-190">Windows Hello Test Drive demo</span></span>](https://webauthnsample.azurewebsites.net)  

## <span data-ttu-id="5a2ec-191">仕様</span><span class="sxs-lookup"><span data-stu-id="5a2ec-191">Specification</span></span>  

[<span data-ttu-id="5a2ec-192">Web 認証: 公開キー資格情報にアクセスするための API</span><span class="sxs-lookup"><span data-stu-id="5a2ec-192">Web Authentication: An API for accessing Public Key Credentials</span></span>](http://w3c.github.io/webauthn)  
