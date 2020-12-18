---
description: Microsoft Edge DevTools で Authenticators をエミュレートし、WebAuthn をデバッグします。
title: Microsoft Edge DevTools で認証システムをエミュレートし、WebAuthn をデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3200f22485bfd642a37a7d34ac727b8da4500d06
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231182"
---
# <span data-ttu-id="19046-104">Microsoft Edge DevTools で認証システムをエミュレートし、WebAuthn をデバッグする</span><span class="sxs-lookup"><span data-stu-id="19046-104">Emulate authenticators and debug WebAuthn in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="19046-105">Web サイトまたはアプリで物理認証システムを使用して Web 認証をデバッグする代わりに、Microsoft Edge DevTools の **WebAuthn** ツールを使用して、ソフトウェア ベースの仮想認証システムを作成して操作します。</span><span class="sxs-lookup"><span data-stu-id="19046-105">Instead of debugging Web Authentication in your website or app with physical authenticators, use the **WebAuthn** tool in Microsoft Edge DevTools to create and interact with software-based virtual authenticators.</span></span>  

## <span data-ttu-id="19046-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="19046-106">Before you begin</span></span>  

<span data-ttu-id="19046-107">Web 認証を始めるのに最適な場所は [、Web 認証 API の仕様です][GithubW3cWebauthn]。</span><span class="sxs-lookup"><span data-stu-id="19046-107">A great place to get started with Web Authentication is the [Web Authentication API specification][GithubW3cWebauthn].</span></span>  

## <span data-ttu-id="19046-108">WebAuthn ツールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="19046-108">Set up the WebAuthn tool</span></span>  

1.  <span data-ttu-id="19046-109">次のデモ Web サイトなど、WebAuthn を使用する Web ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="19046-109">Navigate to a webpage that uses WebAuthn, such as the following demo website.</span></span>  
    
    [<span data-ttu-id="19046-110">webauthndemo.appspot.com</span><span class="sxs-lookup"><span data-stu-id="19046-110">webauthndemo.appspot.com</span></span>][AppspotWebauthndemo]  
    
1.  <span data-ttu-id="19046-111">Web サイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="19046-111">Sign into the website.</span></span>  
1.  <span data-ttu-id="19046-112">[DevTools を開きます][DevtoolsGuideChromiumOpen]。</span><span class="sxs-lookup"><span data-stu-id="19046-112">[Open DevTools][DevtoolsGuideChromiumOpen].</span></span>  
1.  <span data-ttu-id="19046-113">**WebAuthn ツールを開**するには **、[DevTools**のカスタマイズと制御] アイコン (\) アイコンを選択し、[その他> WebAuthn ] を `...` \*\*\*\*  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="19046-113">To open the **WebAuthn** tool, choose the **Customize and control DevTools** \(`...`\) icon > **More tools** > **WebAuthn**.</span></span>  
    
    :::image type="complex" source="../media/webauthn-webauthn-tab.msft.png" alt-text="WebAuthn ツール" lightbox="../media/webauthn-webauthn-tab.msft.png":::
       <span data-ttu-id="19046-115">**WebAuthn** ツール</span><span class="sxs-lookup"><span data-stu-id="19046-115">**WebAuthn** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="19046-116">**WebAuthn ツールで、[** 仮想認証環境を有効**にする] チェック ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="19046-116">In the **WebAuthn** tool, turn on **Enable virtual authenticator environment** checkbox.</span></span>  
1.  <span data-ttu-id="19046-117">有効にすると、新しい認証システムという名前の新 **しいセクションが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="19046-117">After it is enabled, a new section named **New authenticator** is displayed.</span></span>  
    
    :::image type="complex" source="../media/webauthn-enable-virtual-auth.msft.png" alt-text="仮想認証環境を有効にする" lightbox="../media/webauthn-enable-virtual-auth.msft.png":::
        **<span data-ttu-id="19046-119">仮想認証環境を有効にする</span><span class="sxs-lookup"><span data-stu-id="19046-119">Enable virtual authenticator environment</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="19046-120">[新しい **認証システム] セクション** で、次のオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="19046-120">In the **New authenticator** section, configure the following options.</span></span>  
    
    | <span data-ttu-id="19046-121">オプション</span><span class="sxs-lookup"><span data-stu-id="19046-121">Option</span></span> | <span data-ttu-id="19046-122">設定値</span><span class="sxs-lookup"><span data-stu-id="19046-122">Value</span></span> | <span data-ttu-id="19046-123">詳細</span><span class="sxs-lookup"><span data-stu-id="19046-123">Details</span></span> |  
    |:--- |:--- |:--- |  
    | `Protocol` | <span data-ttu-id="19046-124">[ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] または [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml]</span><span class="sxs-lookup"><span data-stu-id="19046-124">[ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] or [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml]</span></span> | <span data-ttu-id="19046-125">仮想認証システムがエンコードとデコードに使用するプロトコル</span><span class="sxs-lookup"><span data-stu-id="19046-125">The protocol the virtual authenticator uses for encoding and decoding</span></span> |  
    | `Transport` |   `usb`<span data-ttu-id="19046-126">`nfc`、 `ble` または</span><span class="sxs-lookup"><span data-stu-id="19046-126">, `nfc`, `ble`, or</span></span> `internal` | <span data-ttu-id="19046-127">仮想認証システムは、特定の資格情報のアサーションを取得するために、クライアントと通信するために選択されたトランスポートをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="19046-127">The virtual authenticator simulates the selected transport for communicating with clients in order to obtain an assertion for a specific credential.</span></span>  <span data-ttu-id="19046-128">詳細については [、「Authenticator Transport Enumeration」に移動します。][GithubW3cWebauthnEnumTransport]</span><span class="sxs-lookup"><span data-stu-id="19046-128">For more information, navigate to [Authenticator Transport Enumeration][GithubW3cWebauthnEnumTransport]</span></span> |  
    |  `Supports resident keys` | <span data-ttu-id="19046-129">チェック ボックスを使用して \(またはオフ)をオンにする</span><span class="sxs-lookup"><span data-stu-id="19046-129">Turn on \(or off\) using the checkbox</span></span> | <span data-ttu-id="19046-130">Web アプリが常駐キー \(クライアント側の検出可能な資格情報\ とも呼ばれる) に依存している場合はオンにします。</span><span class="sxs-lookup"><span data-stu-id="19046-130">Turn on if your web app relies on resident keys \(also known as client-side discoverable credentials\).</span></span>  <span data-ttu-id="19046-131">詳細については、常駐キー要件列挙 [に移動します][GithubW3cWebauthnEnumResidentkeyrequirement]。</span><span class="sxs-lookup"><span data-stu-id="19046-131">For more information, navigate to [Resident Key Requirement Enumeration][GithubW3cWebauthnEnumResidentkeyrequirement].</span></span> |  
    | `Supports user verification` | <span data-ttu-id="19046-132">チェック ボックスを使用して \(または off\) をオンにする</span><span class="sxs-lookup"><span data-stu-id="19046-132">Turn on \(or off\) using the checkbox</span></span> | <span data-ttu-id="19046-133">Web アプリが、タッチとピンコード、パスワード入力、生体認証認識などのジェスチャ モダリティを使用したローカル承認に依存している場合にオンになります。</span><span class="sxs-lookup"><span data-stu-id="19046-133">Turn on if your web app relies on local authorization using gesture modalities like touch plus pin code, password entry, or biometric recognition.</span></span>  <span data-ttu-id="19046-134">詳細については、[ユーザーの確認] [に移動します。][GithubW3cWebauthnEnumUserverification]</span><span class="sxs-lookup"><span data-stu-id="19046-134">For more information, navigate to [User Verification][GithubW3cWebauthnEnumUserverification]</span></span> |  
    
1.  <span data-ttu-id="19046-135">[追加] **ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="19046-135">Choose the **Add** button.</span></span>  
1.  <span data-ttu-id="19046-136">新しく作成した認証システムの新しいセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19046-136">A new section of your newly created authenticator is displayed.</span></span>  
    
    :::image type="complex" source="../media/webauthn-authenticator.msft.png" alt-text="Authenticator" lightbox="../media/webauthn-authenticator.msft.png":::
       <span data-ttu-id="19046-138">Authenticator</span><span class="sxs-lookup"><span data-stu-id="19046-138">Authenticator</span></span>  
    :::image-end:::  
    
<span data-ttu-id="19046-139">**Authenticator セクションには\*\*\*\*、Credentials テーブルが含**まれています。</span><span class="sxs-lookup"><span data-stu-id="19046-139">The **Authenticator** section includes a **Credentials** table.</span></span>  <span data-ttu-id="19046-140">資格情報が認証システムに登録されるまで、テーブルは空です。</span><span class="sxs-lookup"><span data-stu-id="19046-140">The table is empty until a credential is registered to the authenticator.</span></span>  

:::image type="complex" source="../media/webauthn-no-cred.msft.png" alt-text="資格情報なし" lightbox="../media/webauthn-no-cred.msft.png":::
   <span data-ttu-id="19046-142">資格情報なし</span><span class="sxs-lookup"><span data-stu-id="19046-142">No credentials</span></span>  
:::image-end:::  

## <span data-ttu-id="19046-143">新しい資格情報を登録する</span><span class="sxs-lookup"><span data-stu-id="19046-143">Register a new credential</span></span>  

<span data-ttu-id="19046-144">新しい資格情報を登録するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19046-144">To register a new credential, complete the following steps.</span></span>  <span data-ttu-id="19046-145">新しい資格情報を登録するときに [Web 認証 API][GithubW3cWebauthn] が実行する操作の詳細については、「新しい資格情報を作成する [」に移動します][GithubW3cWebauthnSctnCreatecredential]。</span><span class="sxs-lookup"><span data-stu-id="19046-145">For more information about what the [Web Authentication API][GithubW3cWebauthn] is doing when registering a new credential, navigate to [Create a New Credential][GithubW3cWebauthnSctnCreatecredential].</span></span>  

1.  <span data-ttu-id="19046-146">デモ Web サイトで、[新しい資格情報の **登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="19046-146">On the demo website, choose **Register new credential**.</span></span>  
1.  <span data-ttu-id="19046-147">これで、WebAuthn ツールの **[資格情報** ] テーブルに新しい資格情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="19046-147">A new credential is now added to the **Credentials** table in the WebAuthn tool.</span></span>  
    
    :::image type="complex" source="../media/webauthn-view-cred.msft.png" alt-text="資格情報を表示する" lightbox="../media/webauthn-view-cred.msft.png":::
       <span data-ttu-id="19046-149">資格情報を表示する</span><span class="sxs-lookup"><span data-stu-id="19046-149">View credentials</span></span>  
    :::image-end:::  
    
<span data-ttu-id="19046-150">デモ Web サイトで、[認証] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="19046-150">On the demo website, choose the **Authenticate** button.</span></span>  <span data-ttu-id="19046-151">Credentials テーブル内の資格情報の Sign \*\*\*\* [Count][GithubW3cWebauthnSctnSignCounter]が 1 増加し[、authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion]操作が成功したとマークされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="19046-151">Verify that the [Sign Count][GithubW3cWebauthnSctnSignCounter] of the credential in the **Credentials** table increased by 1, which marks a successful [authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion] operation.</span></span>  

## <span data-ttu-id="19046-152">資格情報のエクスポートと削除</span><span class="sxs-lookup"><span data-stu-id="19046-152">Export and remove credentials</span></span>  

<span data-ttu-id="19046-153">資格情報をエクスポートまたは削除するには、[エクスポート] ボタンまたは [削除 **]** ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="19046-153">To export or remove a credential, choose the **Export** or **Remove** button.</span></span>  

:::image type="complex" source="../media/webauthn-export-remove.msft.png" alt-text="資格情報をエクスポートまたは削除する" lightbox="../media/webauthn-export-remove.msft.png":::
   <span data-ttu-id="19046-155">資格情報をエクスポートまたは削除する</span><span class="sxs-lookup"><span data-stu-id="19046-155">Export or remove a credential</span></span>  
:::image-end:::  

## <span data-ttu-id="19046-156">認証システムの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="19046-156">Rename an authenticator</span></span>  

<span data-ttu-id="19046-157">認証システムの名前を変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19046-157">To rename an authenticator, complete the following steps.</span></span>  

1.  <span data-ttu-id="19046-158">認証者名の横にある [編集] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="19046-158">Next to the authenticator name, choose the **Edit** button.</span></span>  
1.  <span data-ttu-id="19046-159">名前を編集し **、Enter** キーを押して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="19046-159">Edit the name, then choose **Enter** to save the changes.</span></span>  

:::image type="complex" source="../media/webauthn-rename.msft.png" alt-text="認証システムの名前を変更する" lightbox="../media/webauthn-rename.msft.png":::
   <span data-ttu-id="19046-161">認証システムの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="19046-161">Rename an authenticator</span></span>  
:::image-end:::  

## <span data-ttu-id="19046-162">アクティブな認証システムを設定する</span><span class="sxs-lookup"><span data-stu-id="19046-162">Set the active authenticator</span></span>  

<span data-ttu-id="19046-163">新しく作成された認証システムが自動的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="19046-163">A newly created authenticator is automatically activated.</span></span>  <span data-ttu-id="19046-164">別の仮想認証を使用するには、認証システム **の横にある [アクティブ** ] ラジオ ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="19046-164">To use another virtual authenticator, choose the **Active** radio button next to the authenticator.</span></span>  

> [!NOTE]
> <span data-ttu-id="19046-165">DevTools は、任意の時点で 1 つのアクティブな仮想認証システムのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="19046-165">DevTools supports only one active virtual authenticator at any point of time.</span></span>  <span data-ttu-id="19046-166">アクティブな認証システムを削除すると、別の認証システムが自動的にアクティブ化されません。</span><span class="sxs-lookup"><span data-stu-id="19046-166">If you remove the active authenticator, another authenticator is not automatically activated.</span></span>  

:::image type="complex" source="../media/webauthn-set-active.msft.png" alt-text="アクティブな認証システムを設定する" lightbox="../media/webauthn-set-active.msft.png":::
   <span data-ttu-id="19046-168">アクティブな認証システムを設定する</span><span class="sxs-lookup"><span data-stu-id="19046-168">Set active authenticator</span></span>  
:::image-end:::  

## <span data-ttu-id="19046-169">仮想認証システムを削除する</span><span class="sxs-lookup"><span data-stu-id="19046-169">Remove a virtual authenticator</span></span>  

<span data-ttu-id="19046-170">仮想認証システムを削除するには、認証者の横にある [削除] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="19046-170">To remove a virtual authenticator, next to the authenticator, choose the **Remove** button.</span></span>  

:::image type="complex" source="../media/webauthn-remove-authenticator.msft.png" alt-text="認証システムを削除する" lightbox="../media/webauthn-remove-authenticator.msft.png":::
   <span data-ttu-id="19046-172">認証システムを削除する</span><span class="sxs-lookup"><span data-stu-id="19046-172">Remove authenticator</span></span>  
:::image-end:::  

## <span data-ttu-id="19046-173">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="19046-173">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[AppspotWebauthndemo]: https://webauthndemo.appspot.com "Webauthn デモ |Appspot"  

[FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml]: https://fidoalliance.org/specs/fido-v2.0-id-20180227/fido-client-to-authenticator-protocol-v2.0-id-20180227.html "クライアントから Authenticator プロトコル (CTAP) |fido alliance"  
[FidoallianceSpecsU2fV12Ps20170411OverviewHtml]: https://fidoalliance.org/specs/fido-u2f-v1.2-ps-20170411/fido-u2f-overview-v1.2-ps-20170411.html "ユニバーサル 2nd Factor (U2F) の概要 |fido alliance"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |GitHub"  
[GithubW3cWebauthnAuthenticatorgetassertion]: https://w3c.github.io/webauthn#authenticatorgetassertion "authenticatorGetAssertion 操作 - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |GitHub"  
[GithubW3cWebauthnEnumTransport]: https://w3c.github.io/webauthn#enum-transport "Authenticator Transport 列挙 (Enum AuthenticatorTransport) - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |W3C"  
[GithubW3cWebauthnEnumResidentkeyrequirement]: https://w3c.github.io/webauthn#enum-residentKeyRequirement "Resident Key Requirement Enumeration (enum ResidentKeyRequirement) - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |W3C"  
[GithubW3cWebauthnEnumUserverification]: https://w3c.github.io/webauthn#user-verification "ユーザーの確認 - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |W3C"  
[GithubW3cWebauthnSctnCreatecredential]: https://w3c.github.io/webauthn#sctn-createCredential "Create a New Credential - PublicKeyCredential's [Create]](origin, options, sameOriginWithAncestors) Method - Web Authentication: An API for accessing Public Key Credentials Level 2 |GitHub"  
[GithubW3cWebauthnSctnSignCounter]: https://w3c.github.io/webauthn/#sctn-sign-counter "署名カウンターに関する考慮事項 - Web 認証: 公開キー資格情報レベル 2 にアクセスするための API |GitHub"  

> [!NOTE]
> <span data-ttu-id="19046-185">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="19046-185">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="19046-186">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/tools/chrome-devtools/webauthn/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="19046-186">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/webauthn/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="19046-188">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="19046-188">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
