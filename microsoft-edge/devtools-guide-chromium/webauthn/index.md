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
# <span data-ttu-id="17e03-104">Microsoft Edge DevTools でオーセンティケータをエミュレートして、WebAuthn をデバッグする</span><span class="sxs-lookup"><span data-stu-id="17e03-104">Emulate authenticators and debug WebAuthn in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="17e03-105">Web 認証は、web サイトや物理認証を使ったアプリではなく、Microsoft Edge DevTools の **WebAuthn** ツールを使用して、ソフトウェアベースの仮想オーセンティケータを作成し、操作します。</span><span class="sxs-lookup"><span data-stu-id="17e03-105">Instead of debugging Web Authentication in your website or app with physical authenticators, use the **WebAuthn** tool in Microsoft Edge DevTools to create and interact with software-based virtual authenticators.</span></span>  

## <span data-ttu-id="17e03-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="17e03-106">Before you begin</span></span>  

<span data-ttu-id="17e03-107">Web 認証を始めるのに最適な場所は、 [Web AUTHENTICATION API の仕様][GithubW3cWebauthn]です。</span><span class="sxs-lookup"><span data-stu-id="17e03-107">A great place to get started with Web Authentication is the [Web Authentication API specification][GithubW3cWebauthn].</span></span>  

## <span data-ttu-id="17e03-108">WebAuthn ツールを設定する</span><span class="sxs-lookup"><span data-stu-id="17e03-108">Set up the WebAuthn tool</span></span>  

1.  <span data-ttu-id="17e03-109">次のデモ web サイトなど、WebAuthn を使用する web ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="17e03-109">Navigate to a webpage that uses WebAuthn, such as the following demo website.</span></span>  
    
    [<span data-ttu-id="17e03-110">webauthndemo.appspot.com</span><span class="sxs-lookup"><span data-stu-id="17e03-110">webauthndemo.appspot.com</span></span>][AppspotWebauthndemo]  
    
1.  <span data-ttu-id="17e03-111">Web サイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="17e03-111">Sign into the website.</span></span>  
1.  <span data-ttu-id="17e03-112">[DevTools を開き][DevtoolsGuideChromiumOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="17e03-112">[Open DevTools][DevtoolsGuideChromiumOpen].</span></span>  
1.  <span data-ttu-id="17e03-113">**Webauthn**ツールを開くには、[**ユーザー設定と制御**のための devtools \ ( `...` \)] アイコン > [**その他のツール**]  >  **WebAuthn**を選びます。</span><span class="sxs-lookup"><span data-stu-id="17e03-113">To open the **WebAuthn** tool, choose the **Customize and control DevTools** \(`...`\) icon > **More tools** > **WebAuthn**.</span></span>  
    
    :::image type="complex" source="../media/webauthn-webauthn-tab.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-webauthn-tab.msft.png":::
       <span data-ttu-id="17e03-115">**WebAuthn** ツール</span><span class="sxs-lookup"><span data-stu-id="17e03-115">**WebAuthn** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="17e03-116">[ **WebAuthn** ] ツールで、[ **Virtual Authenticator 環境を有効**にする] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="17e03-116">In the **WebAuthn** tool, choose the checkbox next to **Enable virtual authenticator environment**.</span></span>  
1.  <span data-ttu-id="17e03-117">有効にすると、新しい [ **authenticator** ] という名前の新しいセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17e03-117">After it is enabled, a new section named **New authenticator** is displayed.</span></span>  
    
    :::image type="complex" source="../media/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-enable-virtual-auth.msft.png":::
        **<span data-ttu-id="17e03-119">仮想認証システムを有効にする環境</span><span class="sxs-lookup"><span data-stu-id="17e03-119">Enable virtual authenticator environment</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="17e03-120">[ **新しい認証** 方法] セクションで、次のオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="17e03-120">In the **New authenticator** section, configure the following options.</span></span>  
    
    | <span data-ttu-id="17e03-121">オプション</span><span class="sxs-lookup"><span data-stu-id="17e03-121">Option</span></span> | <span data-ttu-id="17e03-122">値</span><span class="sxs-lookup"><span data-stu-id="17e03-122">Value</span></span> | <span data-ttu-id="17e03-123">詳細</span><span class="sxs-lookup"><span data-stu-id="17e03-123">Details</span></span> |  
    |:--- |:--- |:--- |  
    | `Protocol` | <span data-ttu-id="17e03-124">[ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] または [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml]</span><span class="sxs-lookup"><span data-stu-id="17e03-124">[ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] or [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml]</span></span> | <span data-ttu-id="17e03-125">仮想化認証でエンコードとデコードに使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="17e03-125">The protocol the virtual authenticator uses for encoding and decoding</span></span> |  
    | `Transport` |   `usb`<span data-ttu-id="17e03-126">、 `nfc` 、 `ble` 、または</span><span class="sxs-lookup"><span data-stu-id="17e03-126">, `nfc`, `ble`, or</span></span> `internal` | <span data-ttu-id="17e03-127">仮想認証は、特定の資格情報のアサーションを取得するために、選択したトランスポートをクライアントと通信するために選択されたトランスポートをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="17e03-127">The virtual authenticator simulates the selected transport for communicating with clients in order to obtain an assertion for a specific credential.</span></span>  <span data-ttu-id="17e03-128">詳細については、「 [Authenticator トランスポートの列挙][GithubW3cWebauthnEnumTransport]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e03-128">For more information, navigate to [Authenticator Transport Enumeration][GithubW3cWebauthnEnumTransport]</span></span> |  
    |  `Supports resident keys` | <span data-ttu-id="17e03-129">チェックボックスを使用して \ (またはオフ) をオンにする</span><span class="sxs-lookup"><span data-stu-id="17e03-129">Turn on \(or off\) using the checkbox</span></span> | <span data-ttu-id="17e03-130">Web アプリが常駐キー (クライアント側の検出可能な資格情報とも呼ばれます) に依存しているかどうかをオンにします。</span><span class="sxs-lookup"><span data-stu-id="17e03-130">Turn on if your web app relies on resident keys \(also known as client-side discoverable credentials\).</span></span>  <span data-ttu-id="17e03-131">詳細については、「 [常駐キーの要件の列挙][GithubW3cWebauthnEnumResidentkeyrequirement]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e03-131">For more information, navigate to [Resident Key Requirement Enumeration][GithubW3cWebauthnEnumResidentkeyrequirement].</span></span> |  
    | `Supports user verification` | <span data-ttu-id="17e03-132">チェックボックスを使用して \ (またはオフ) をオンにする</span><span class="sxs-lookup"><span data-stu-id="17e03-132">Turn on \(or off\) using the checkbox</span></span> | <span data-ttu-id="17e03-133">Web アプリが、タッチ plus pin コード、パスワード入力、バイオメトリクス認識などのジェスチャモダリティを使用したローカル承認に依存しているかどうかをオンにします。</span><span class="sxs-lookup"><span data-stu-id="17e03-133">Turn on if your web app relies on local authorization using gesture modalities like touch plus pin code, password entry, or biometric recognition.</span></span>  <span data-ttu-id="17e03-134">詳細については、「[ユーザーの確認][GithubW3cWebauthnEnumUserverification]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="17e03-134">For more information, navigate to [User Verification][GithubW3cWebauthnEnumUserverification]</span></span> |  
    
1.  <span data-ttu-id="17e03-135">[ **追加** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="17e03-135">Choose the **Add** button.</span></span>  
1.  <span data-ttu-id="17e03-136">新しく作成されたオーセンティケータの新しいセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17e03-136">A new section of your newly created authenticator is displayed.</span></span>  
    
    :::image type="complex" source="../media/webauthn-authenticator.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-authenticator.msft.png":::
       <span data-ttu-id="17e03-138">アプリ</span><span class="sxs-lookup"><span data-stu-id="17e03-138">Authenticator</span></span>  
    :::image-end:::  
    
<span data-ttu-id="17e03-139">[ **認証** 情報] セクションには、 **資格情報** テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="17e03-139">The **Authenticator** section includes a **Credentials** table.</span></span>  <span data-ttu-id="17e03-140">資格情報がオーセンティケータに登録されるまで、この表は空になっています。</span><span class="sxs-lookup"><span data-stu-id="17e03-140">The table is empty until a credential is registered to the authenticator.</span></span>  

:::image type="complex" source="../media/webauthn-no-cred.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-no-cred.msft.png":::
   <span data-ttu-id="17e03-142">資格情報なし</span><span class="sxs-lookup"><span data-stu-id="17e03-142">No credentials</span></span>  
:::image-end:::  

## <span data-ttu-id="17e03-143">新しい資格情報を登録する</span><span class="sxs-lookup"><span data-stu-id="17e03-143">Register a new credential</span></span>  

<span data-ttu-id="17e03-144">新しい資格情報を登録するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17e03-144">To register a new credential, complete the following steps.</span></span>  <span data-ttu-id="17e03-145">新しい資格情報を登録するときの [Web 認証 API][GithubW3cWebauthn] の動作の詳細については、「 [新しい資格情報を作成][GithubW3cWebauthnSctnCreatecredential]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e03-145">For more information about what the [Web Authentication API][GithubW3cWebauthn] is doing when registering a new credential, navigate to [Create a New Credential][GithubW3cWebauthnSctnCreatecredential].</span></span>  

1.  <span data-ttu-id="17e03-146">デモ web サイトで、[ **新しい資格情報の登録**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="17e03-146">On the demo website, choose **Register new credential**.</span></span>  
1.  <span data-ttu-id="17e03-147">新しい資格情報が、WebAuthn ツールの **Credentials** テーブルに追加されました。</span><span class="sxs-lookup"><span data-stu-id="17e03-147">A new credential is now added to the **Credentials** table in the WebAuthn tool.</span></span>  
    
    :::image type="complex" source="../media/webauthn-view-cred.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-view-cred.msft.png":::
       <span data-ttu-id="17e03-149">資格情報の表示</span><span class="sxs-lookup"><span data-stu-id="17e03-149">View credentials</span></span>  
    :::image-end:::  
    
<span data-ttu-id="17e03-150">デモ web サイトで、[ **認証** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="17e03-150">On the demo website, choose the **Authenticate** button.</span></span>  <span data-ttu-id="17e03-151">**資格情報**テーブルの資格情報の[符号カウント][GithubW3cWebauthnSctnSignCounter]が1で増加したことを確認します。これは、 [authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion]操作が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="17e03-151">Verify that the [Sign Count][GithubW3cWebauthnSctnSignCounter] of the credential in the **Credentials** table increased by 1, which marks a successful [authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion] operation.</span></span>  

## <span data-ttu-id="17e03-152">資格情報のエクスポートと削除</span><span class="sxs-lookup"><span data-stu-id="17e03-152">Export and remove credentials</span></span>  

<span data-ttu-id="17e03-153">資格情報をエクスポートまたは削除するには、[ **エクスポート** ] または [ **削除** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="17e03-153">To export or remove a credential, choose the **Export** or **Remove** button.</span></span>  

:::image type="complex" source="../media/webauthn-export-remove.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-export-remove.msft.png":::
   <span data-ttu-id="17e03-155">資格情報をエクスポートまたは削除する</span><span class="sxs-lookup"><span data-stu-id="17e03-155">Export or remove a credential</span></span>  
:::image-end:::  

## <span data-ttu-id="17e03-156">オーセンティケータの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="17e03-156">Rename an authenticator</span></span>  

<span data-ttu-id="17e03-157">オーセンティケータの名前を変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17e03-157">To rename an authenticator, complete the following steps.</span></span>  

1.  <span data-ttu-id="17e03-158">オーセンティケータ名の横にある「 **編集** 」ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="17e03-158">Next to the authenticator name, choose the **Edit** button.</span></span>  
1.  <span data-ttu-id="17e03-159">名前を編集してから、[ **enter** ] を選んで変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="17e03-159">Edit the name, then choose **Enter** to save the changes.</span></span>  

:::image type="complex" source="../media/webauthn-rename.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-rename.msft.png":::
   <span data-ttu-id="17e03-161">オーセンティケータの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="17e03-161">Rename an authenticator</span></span>  
:::image-end:::  

## <span data-ttu-id="17e03-162">アクティブな認証システムを設定する</span><span class="sxs-lookup"><span data-stu-id="17e03-162">Set the active authenticator</span></span>  

<span data-ttu-id="17e03-163">新しく作成されたオーセンティケータは、自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="17e03-163">A newly created authenticator is automatically activated.</span></span>  <span data-ttu-id="17e03-164">別の仮想オーセンティケータを使用するには、オーセンティケータの横にある「 **アクティブ** 」ラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="17e03-164">To use another virtual authenticator, choose the **Active** radio button next to the authenticator.</span></span>  

> [!NOTE]
> <span data-ttu-id="17e03-165">DevTools は、任意の時点でアクティブな仮想オーセンティケータを1つだけサポートします。</span><span class="sxs-lookup"><span data-stu-id="17e03-165">DevTools supports only one active virtual authenticator at any point of time.</span></span>  <span data-ttu-id="17e03-166">アクティブなオーセンティケータを削除した場合、別のオーセンティケータは自動的にアクティブ化されません。</span><span class="sxs-lookup"><span data-stu-id="17e03-166">If you remove the active authenticator, another authenticator is not automatically activated.</span></span>  

:::image type="complex" source="../media/webauthn-set-active.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-set-active.msft.png":::
   <span data-ttu-id="17e03-168">アクティブな認証システムを設定する</span><span class="sxs-lookup"><span data-stu-id="17e03-168">Set active authenticator</span></span>  
:::image-end:::  

## <span data-ttu-id="17e03-169">仮想認証を削除する</span><span class="sxs-lookup"><span data-stu-id="17e03-169">Remove a virtual authenticator</span></span>  

<span data-ttu-id="17e03-170">仮想オーセンティケータを削除するには、オーセンティケータの横にある「 **削除** 」ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="17e03-170">To remove a virtual authenticator, next to the authenticator, choose the **Remove** button.</span></span>  

:::image type="complex" source="../media/webauthn-remove-authenticator.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-remove-authenticator.msft.png":::
   <span data-ttu-id="17e03-172">オーセンティケータを削除する</span><span class="sxs-lookup"><span data-stu-id="17e03-172">Remove authenticator</span></span>  
:::image-end:::  

## <span data-ttu-id="17e03-173">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="17e03-173">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
> <span data-ttu-id="17e03-185">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="17e03-185">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="17e03-186">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/webauthn/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。</span><span class="sxs-lookup"><span data-stu-id="17e03-186">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/webauthn/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="17e03-188">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="17e03-188">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
