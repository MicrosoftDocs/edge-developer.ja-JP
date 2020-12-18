---
description: 支払い要求 API を使用すると、Microsoft Edge が、業者、消費者、およびクラウドに保存されているコンシューマーの支払い方法の仲介者として機能する方法について説明します。
title: 支払い要求 API - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: efcad701fec73f858fa9490f12b094259cd8c793
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234617"
---
# <span data-ttu-id="76081-104">支払い要求 API (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="76081-104">Payment Request API (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="76081-105">この記事では、従来のバージョンの Microsoft Edge でサポート [されているワークフローについて説明します][MicrosoftSupport44533505]。</span><span class="sxs-lookup"><span data-stu-id="76081-105">This article describes the workflow supported in the [legacy version of Microsoft Edge][MicrosoftSupport44533505].</span></span>  <span data-ttu-id="76081-106">Microsoft Edge \(Chromium\) は、Chromium プロジェクトに基づく異なる実装による支払い要求 API をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="76081-106">Microsoft Edge \(Chromium\) supports the Payment Request API with a different implementation based on the Chromium project.</span></span>  

<span data-ttu-id="76081-107">電子商取引の売り上げは急速に拡大し続けています。</span><span class="sxs-lookup"><span data-stu-id="76081-107">E-commerce sales continue growing at a rapid pace.</span></span>  <span data-ttu-id="76081-108">[eMarketer](https://www.emarketer.com)によると、2018 年のデジタル販売は、2013 年に測定されたレベルから 23% 増加すると予測されています。</span><span class="sxs-lookup"><span data-stu-id="76081-108">According to [eMarketer](https://www.emarketer.com), by 2018 digital sales are forecasted to increase by 23% from the levels measured in 2013.</span></span>  <span data-ttu-id="76081-109">消費者や企業は電子商取引の利便性を楽しんでいますが、課題は残ります。</span><span class="sxs-lookup"><span data-stu-id="76081-109">While consumers and businesses enjoy the convenience of e-commerce sales, challenges remain.</span></span>  <span data-ttu-id="76081-110">現在、各電子商取引 Web サイトの所有者は、高品質の支払いチェックアウト フローと検証ルールを開発するために時間を費やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="76081-110">Today each e-commerce website owner needs to invest time to develop high quality payment checkout flows and validation rules.</span></span>  <span data-ttu-id="76081-111">消費者は、さまざまな支払いチェックアウト フローに移動し、購入したサイトごとに同じ支払いおよび配送情報を再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76081-111">Consumers need to navigate different payment checkout flows and re-enter the same payment and shipping information on every site where they shop.</span></span>  <span data-ttu-id="76081-112">これは、消費者にとって時間がかかり、不満が生じ、ショッピング カートの破棄率が高く、業者の売り上げが減少する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76081-112">This can be time consuming and frustrating for consumers, leading to a high rate of shopping cart abandonment and decreased sales for merchants.</span></span>  <span data-ttu-id="76081-113">販売業者の [推定](http://baymard.com/lists/cart-abandonment-rate) 値は、ショッピング カートの 60% ~ 70% が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="76081-113">Merchants [estimate](http://baymard.com/lists/cart-abandonment-rate) between 60% and 70% of shopping carts are abandoned.</span></span>  

<span data-ttu-id="76081-114">支払 [い要求 API は](https://w3.org/TR/payment-request) 、支払いチェックアウト プロセスを標準化します。</span><span class="sxs-lookup"><span data-stu-id="76081-114">The [Payment Request API](https://w3.org/TR/payment-request) standardizes the payment checkout process.</span></span>  <span data-ttu-id="76081-115">この API では、Web 開発者のカスタマイズが少なく、より速く、一貫性が高く、消費者にとってわかりにくいエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="76081-115">This API requires less customization for web developers and provides a faster, more consistent, and therefore, less confusing experience for consumers.</span></span>  <span data-ttu-id="76081-116">消費者は Microsoft アカウントから支払い方法と配送先住所を選び、購入を完了するために必要なデータを少なくする必要があります。これは、支払いを完了するために必要な時間とデータ入力を減らします。</span><span class="sxs-lookup"><span data-stu-id="76081-116">Because consumers can select payment instruments and shipping addresses from their Microsoft account, they are required to enter less data to complete purchases which reduces the time and data entry required to complete a payment.</span></span>  

<span data-ttu-id="76081-117">支払い要求 [API](https://w3.org/TR/payment-request) はオープンなクロスブラウザー標準で、ブラウザーが業者、消費者、および消費者がクラウドに保存した支払い方法 \(クレジット カード\など) の仲介者として機能します。</span><span class="sxs-lookup"><span data-stu-id="76081-117">The [Payment Request API](https://w3.org/TR/payment-request) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  
  
<span data-ttu-id="76081-118">まとめると、支払い要求 [API](https://w3.org/TR/payment-request)を使用する場合、顧客は通常通り販売業者の Web サイトで購入します。</span><span class="sxs-lookup"><span data-stu-id="76081-118">In summary, when using the [Payment Request API](https://w3.org/TR/payment-request), customers shop on merchant websites as normal.</span></span>  <span data-ttu-id="76081-119">支払いの準備ができたら、業者の Web サイトは支払い要求\*\*\*\*\*\*API\*\*を呼び出して支払い要求を作成し、関連する支払い情報 \(サポートされている支払い方法、購入金額、通貨など) をブラウザーに渡します。</span><span class="sxs-lookup"><span data-stu-id="76081-119">When ready to pay, the merchant website calls the **Payment Request** API to create a **Payment Request** and passes the relevant payment information \(such as supported payment methods, purchase amount, currency, and so on\) to the browser.</span></span>  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="支払い要求の構造" lightbox="../media/payment_request_construct.png":::
   <span data-ttu-id="76081-121">支払い要求の構造</span><span class="sxs-lookup"><span data-stu-id="76081-121">Payment request construct</span></span>  
:::image-end:::  

<span data-ttu-id="76081-122">ブラウザーはユーザーを認証し、ユーザーはファイルでサポートされている支払い方法を選択し、支払いの詳細を処理できます。</span><span class="sxs-lookup"><span data-stu-id="76081-122">The browser authenticates the user, enables the user to select a supported payment method on file, and processes the payment details.</span></span>  <span data-ttu-id="76081-123">その後、ブラウザーは支払い情報の詳細を業者の Web サイトに送り返し、業者が支払いを完了できます。</span><span class="sxs-lookup"><span data-stu-id="76081-123">The browser then sends the payment information details back to the merchant website, so that the merchant can complete the payment.</span></span>  <span data-ttu-id="76081-124">支払い情報を受け取るだけでなく、業者は支払い要求の一部として配送情報を受け **取る選択もできます**。</span><span class="sxs-lookup"><span data-stu-id="76081-124">In addition to receiving payment information, the merchant can also elect to receive shipping information as part of the **Payment Request**.</span></span>  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="支払い応答の構造" lightbox="../media/payment_response_construct.png":::
   <span data-ttu-id="76081-126">支払い応答の構造</span><span class="sxs-lookup"><span data-stu-id="76081-126">Payment response construct</span></span>  
:::image-end:::  

<span data-ttu-id="76081-127">支払い要求 API の動作を確認し、その使い方の概要を確認するには、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="76081-127">To see the Payment Request API in action, as well as get an overview of how to use it, check out this video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> <span data-ttu-id="76081-128">支払い要求 API は、Microsoft Edge ビルド 14992 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="76081-128">The Payment Request API is supported in Microsoft Edge build 14992 or newer.</span></span>  

## <span data-ttu-id="76081-129">支払い要求を作成する</span><span class="sxs-lookup"><span data-stu-id="76081-129">Creating a Payment Request</span></span>  

<span data-ttu-id="76081-130">Web ページは **、通常、** ユーザーが [購入] ボタンをクリックして支払いプロセスを開始するときに支払い要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="76081-130">Web pages create a **Payment Request** typically when the user initiates a payment process by clicking a "buy" button.</span></span>  <span data-ttu-id="76081-131">支払**い要求コンストラクターには**[](/previous-versions/mt790440(v=vs.85))、methodData、詳細、およびオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="76081-131">The **Payment Request** [constructor](/previous-versions/mt790440(v=vs.85)) includes methodData, details, and options.</span></span>  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

<span data-ttu-id="76081-132">[methodData パラメーターには](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)、Web サイトで受け入れられる支払い方法とネットワークの一覧と、関連する支払い方法固有のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="76081-132">The [methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains a list of the payment methods and networks accepted by the website and any associated payment method specific data.</span></span>  <span data-ttu-id="76081-133">Microsoft Edge では、この一覧は、買い手が Microsoft アカウントに保存したサポートされている支払い方法と一致し、支払いユーザー エクスペリエンスの "支払い方法" リストになります。</span><span class="sxs-lookup"><span data-stu-id="76081-133">In Microsoft Edge, this list is matched with the supported payment methods that the shopper has saved in their Microsoft account and results in the "pay with" list in the payment user experience.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="Microsoft Wallet ユーザー エクスペリエンスの支払い一覧" lightbox="../media/pay_with.png":::
         <span data-ttu-id="76081-135">Microsoft **Wallet ユーザー** エクスペリエンスの支払い一覧</span><span class="sxs-lookup"><span data-stu-id="76081-135">The **pay with** list in the Microsoft Wallet user experience</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      ```javascript
      var supportedInstruments = [{
          supportedMethods: ['basic-card'],
          data: {
              supportedNetworks: ['visa', 'mastercard', 'amex'],
              supportedTypes: ['credit'] 
          }         
      }]; 
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="76081-136">details [パラメーター](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) には、業者が取引について顧客に伝えたい情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="76081-136">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains information that the merchant wishes to convey to the customer about the transaction.</span></span>  <span data-ttu-id="76081-137">これには、合計、税金、出荷金額、支払額に影響を与えるその他のサマリー レベルのアイテムなどの注文の要約アイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="76081-137">These include order summary items like total, tax, shipping amount, and other summary level items impacting the payment amount.</span></span>  <span data-ttu-id="76081-138">これらは、注文行アイテムを意図した機能ではありません。</span><span class="sxs-lookup"><span data-stu-id="76081-138">These are not intended to be order line items.</span></span>  
  
<span data-ttu-id="76081-139">詳細 [パラメーター](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) は、必要に応じて顧客が利用できる配送オプションを定義するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="76081-139">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter is also used to define shipping options available to the customer when required.</span></span>  <span data-ttu-id="76081-140">詳しくは、下記の「お **支払い要求** と配送先へのお支払い」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="76081-140">More details are included in the **Payment Request** with Shipping section below.</span></span>  

<span data-ttu-id="76081-141">各 [詳細行](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) には、通貨と金額のラベルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="76081-141">Each [detail](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) line includes a label for the currency and the amount.</span></span>  

> [!NOTE]
> <span data-ttu-id="76081-142">支払 **い要求では** 、これらの金額の合計または合計は計算されない。</span><span class="sxs-lookup"><span data-stu-id="76081-142">The **Payment Request** does not calculate the sum or total of these amounts.</span></span>  <span data-ttu-id="76081-143">行アイテムが正しく合計されるようにするには、業者の Web サイトの責任があります。</span><span class="sxs-lookup"><span data-stu-id="76081-143">It is the responsibility of the merchant's website to ensure that the line items total correctly.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="小計、出荷、税金、合計の詳細" lightbox="../media/show_details.png":::
         <span data-ttu-id="76081-145">小計、出荷、税金、合計の詳細</span><span class="sxs-lookup"><span data-stu-id="76081-145">Subtotal, shipping, taxes, and total details</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      ```javascript
      var details = {
          total: {
              label: 'Total (USD)',
              amount: {currency: 'USD', value: '193.98'}
          },
          displayItems: [{
                  label: 'Subtotal',
                  amount: {currency: 'USD', value: '174.99'}
              }, {
                  label: 'Taxes',
                  amount: {currency: "USD", value: '18.99'}
          }],
      };  
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="76081-146">[PaymentRequest は](/previous-versions/mt790440(v=vs.85)) 払い戻しをサポートしていないので、金額は常に正である必要があります。個々のリスト アイテムは、割引などの負の値になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="76081-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) does not support refunds, so the amounts should always be positive; individual list items can be negative, such as discounts.</span></span>  

<span data-ttu-id="76081-147">ブラウザーは、ラベルの定義時にラベルをレンダリングし、顧客のロケールに基づいて正しい通貨書式を自動的にレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="76081-147">The browser will render the labels as you define them and automatically render the correct currency formatting based on the customer's locale.</span></span>  <span data-ttu-id="76081-148">ラベルは、コンテンツと同じ言語でレンダリングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76081-148">Note that the labels should be rendered in the same language as your content.</span></span>  

<span data-ttu-id="76081-149">[options パラメーター](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)は、Web ページが支払い要求から返すデータを**定義します**。</span><span class="sxs-lookup"><span data-stu-id="76081-149">The [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter defines data the web page wants returned from the **Payment Request**.</span></span>  <span data-ttu-id="76081-150">また、配送、メール アドレス、電話番号、またはすべてのデータが必要な場合など、収集する必要があるデータも定義します。</span><span class="sxs-lookup"><span data-stu-id="76081-150">This also defines the data that needs to be collected, including if shipping, email address, phone number or all are required.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text="[電子メール アドレス] ドロップダウン" lightbox="../media/email_snippet.png":::
         <span data-ttu-id="76081-152">[電子メール アドレス] ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="76081-152">Email address dropdown</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      ```javascript
      var options =
          {
              requestPayerEmail: true
          }; 
      ```  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="76081-153">支払い要求の表示</span><span class="sxs-lookup"><span data-stu-id="76081-153">Showing the Payment Request</span></span>  

<span data-ttu-id="76081-154">[show()](/previous-versions/mt790448(v=vs.85))メソッドは、ユーザーが支払い要求ユーザー インターフェイスを操作するために Web ページ**によって**呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="76081-154">The [show()](/previous-versions/mt790448(v=vs.85)) method is called by the web page to allow the user to interact with the **Payment Request** user interface.</span></span>  <span data-ttu-id="76081-155">[show()](/previous-versions/mt790448(v=vs.85))メソッドは、ユーザーが支払い要求を承認すると解決される Promise を返します。</span><span class="sxs-lookup"><span data-stu-id="76081-155">The [show()](/previous-versions/mt790448(v=vs.85)) method returns a Promise that will be resolved when the user authorizes the payment request.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="詳細の確認と支払い" lightbox="../media/pay_screen_default.png":::
         <span data-ttu-id="76081-157">詳細の確認と支払い</span><span class="sxs-lookup"><span data-stu-id="76081-157">Confirm and pay details</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      ```javascript
      paymentRequest.show().then(paymentInstrumentResponse => {
          paymentInstrumentResponse.complete('success').then().catch(error => {
              handlePaymentRequestError(error); 
      });
      ```  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="76081-158">支払い要求を中止する</span><span class="sxs-lookup"><span data-stu-id="76081-158">Aborting a Payment Request</span></span>  
 
<span data-ttu-id="76081-159">web [ページから show()](/previous-versions/mt790437(v=vs.85)) メソッドが呼び出された後は、Promise が解決されるまでいつでも [abort()](/previous-versions/mt790448(v=vs.85)) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="76081-159">The [abort()](/previous-versions/mt790437(v=vs.85)) method can be called by the web page any time after the [show()](/previous-versions/mt790448(v=vs.85)) method is called, up until the point where the Promise is resolved.</span></span>  <span data-ttu-id="76081-160">[abort() メソッドを使用](/previous-versions/mt790437(v=vs.85))すると、ブラウザーは支払\*\*\*\* い要求を中止し、支払い要求のユーザー インターフェイス**を**閉じます。</span><span class="sxs-lookup"><span data-stu-id="76081-160">The [abort()](/previous-versions/mt790437(v=vs.85)) method will cause the browser to abort the **Payment Request** and close the **Payment Request** user interface.</span></span>  <span data-ttu-id="76081-161">たとえば、ユーザーが必要な時間内にトランザクションを完了しなかった場合、Web ページで中止を選択できます。</span><span class="sxs-lookup"><span data-stu-id="76081-161">For example, a web page may choose to abort if the user did not complete the transaction in the required amount of time.</span></span>  

```javascript
payment.abort();
```  

## <span data-ttu-id="76081-162">支払い応答</span><span class="sxs-lookup"><span data-stu-id="76081-162">Payment Response</span></span>  
<span data-ttu-id="76081-163">顧客が支払い要求を **承認すると**、支払い **応答** が Web サイトに返されます。</span><span class="sxs-lookup"><span data-stu-id="76081-163">When the customer approves the **Payment Request**, a **Payment Response** is returned to the website.</span></span>  <span data-ttu-id="76081-164">支払 **い応答には、** 次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="76081-164">The **Payment Response** includes the following:</span></span>  

 <span data-ttu-id="76081-165">プロパティ</span><span class="sxs-lookup"><span data-stu-id="76081-165">Property</span></span>      | <span data-ttu-id="76081-166">説明</span><span class="sxs-lookup"><span data-stu-id="76081-166">Description</span></span> | <span data-ttu-id="76081-167">必須かどうか</span><span class="sxs-lookup"><span data-stu-id="76081-167">Required</span></span> | <span data-ttu-id="76081-168">追加情報</span><span class="sxs-lookup"><span data-stu-id="76081-168">Additional Info</span></span>
|---------------|-----------------|-------|-----------------|
[<span data-ttu-id="76081-169">methodName</span><span class="sxs-lookup"><span data-stu-id="76081-169">methodName</span></span>](/previous-versions/mt790656(v=vs.85)) | <span data-ttu-id="76081-170">ユーザーが選択した支払い方法の ID</span><span class="sxs-lookup"><span data-stu-id="76081-170">The ID for the payment method selected by the user</span></span> | <span data-ttu-id="76081-171">Y</span><span class="sxs-lookup"><span data-stu-id="76081-171">Y</span></span> | |   
[<span data-ttu-id="76081-172">details</span><span class="sxs-lookup"><span data-stu-id="76081-172">details</span></span>](/previous-versions/mt790655(v=vs.85)) | <span data-ttu-id="76081-173">選択した支払い方法または支払いトークンを使用して、業者がトランザクションを処理するために必要なすべてのデータを含む JSON オブジェクト</span><span class="sxs-lookup"><span data-stu-id="76081-173">A JSON object that includes all of the data the merchant requires to process the transaction using the selected payment method or a payment token</span></span> | <span data-ttu-id="76081-174">Y</span><span class="sxs-lookup"><span data-stu-id="76081-174">Y</span></span> | <span data-ttu-id="76081-175">[基本カード](https://w3c.github.io/payment-method-basic-card) 辞書: cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress;</span><span class="sxs-lookup"><span data-stu-id="76081-175">[Basic Card](https://w3c.github.io/payment-method-basic-card) Dictionary:  cardholderName; cardNumber; expiryMonth; expiryYear; cardSecurityCode; billingAddress;</span></span> |   
[<span data-ttu-id="76081-176">shippingAddress</span><span class="sxs-lookup"><span data-stu-id="76081-176">shippingAddress</span></span>](/previous-versions/mt790445(v=vs.85)) | <span data-ttu-id="76081-177">ユーザーが選択した配送先住所</span><span class="sxs-lookup"><span data-stu-id="76081-177">The shipping address selected by the user</span></span>  |  <span data-ttu-id="76081-178">省略可能。</span><span class="sxs-lookup"><span data-stu-id="76081-178">Optional.</span></span>  <span data-ttu-id="76081-179">[requestShipping が次の場合は必須](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="76081-179">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | <span data-ttu-id="76081-180">アドレスディクショナリ: 国addressLine;region;city;dependentLocality;postalCode;sortingCode;languageCode;組織recipient;phone</span><span class="sxs-lookup"><span data-stu-id="76081-180">Address dictionary:  country; addressLine; region; city; dependentLocality; postalCode; sortingCode; languageCode; organization; recipient; phone</span></span> |  
[<span data-ttu-id="76081-181">shippingOption</span><span class="sxs-lookup"><span data-stu-id="76081-181">shippingOption</span></span>](/previous-versions/mt790446(v=vs.85)) | <span data-ttu-id="76081-182">選択した配送オプションの ID</span><span class="sxs-lookup"><span data-stu-id="76081-182">The ID for the selected shipping option</span></span> | <span data-ttu-id="76081-183">省略可能。</span><span class="sxs-lookup"><span data-stu-id="76081-183">Optional.</span></span>  <span data-ttu-id="76081-184">[requestShipping が次の場合は必須](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="76081-184">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |   
[<span data-ttu-id="76081-185">payerName</span><span class="sxs-lookup"><span data-stu-id="76081-185">payerName</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="76081-186">ユーザーが指定した名前</span><span class="sxs-lookup"><span data-stu-id="76081-186">The name provided by the user</span></span>  | <span data-ttu-id="76081-187">省略可能。</span><span class="sxs-lookup"><span data-stu-id="76081-187">Optional.</span></span>  <span data-ttu-id="76081-188">[requestPayerName が次の場合は必須](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="76081-188">Required when [requestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  
[<span data-ttu-id="76081-189">payerEmail</span><span class="sxs-lookup"><span data-stu-id="76081-189">payerEmail</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="76081-190">ユーザーが選択した電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="76081-190">The email address selected by the user</span></span> | <span data-ttu-id="76081-191">省略可能。</span><span class="sxs-lookup"><span data-stu-id="76081-191">Optional.</span></span>  <span data-ttu-id="76081-192">[requestPayerEmail が](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="76081-192">Required when [requestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |  
[<span data-ttu-id="76081-193">PayerPhone</span><span class="sxs-lookup"><span data-stu-id="76081-193">PayerPhone</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="76081-194">ユーザーが選択した電話番号</span><span class="sxs-lookup"><span data-stu-id="76081-194">The phone number selected by the user</span></span> | <span data-ttu-id="76081-195">省略可能。</span><span class="sxs-lookup"><span data-stu-id="76081-195">Optional.</span></span>  <span data-ttu-id="76081-196">[requestPayerPhone が次の場合は必須](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="76081-196">Required when [requestPayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  

<span data-ttu-id="76081-197">支払 [い](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) 応答の詳細 JSON オブジェクト **には、支払** いを処理するために業者が必要とする支払いデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="76081-197">The [details](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) JSON object in the **Payment Response** will contain the payment data required by the merchant to process a payment.</span></span>  <span data-ttu-id="76081-198">最も単純な形式では、応答はクリア [テキストの支払](https://w3c.github.io/payment-method-basic-card) いカードの詳細を含む基本カードのペイロードになります。</span><span class="sxs-lookup"><span data-stu-id="76081-198">In its simplest form, the response will be a [Basic Card](https://w3c.github.io/payment-method-basic-card) payload containing cleartext payment card details.</span></span>  <span data-ttu-id="76081-199">販売業者が支払いサポートを提供するために追加のゲートウェイ/プロセッサ パートナーとの取り決めを行っている場合、業者はプロセッサが処理できるペイロードを必要とする場合があります。</span><span class="sxs-lookup"><span data-stu-id="76081-199">Where merchants have arrangements with additional gateway/processor partners for them to provide payments support, the merchant may require a payload the processor can handle.</span></span>  <span data-ttu-id="76081-200">これらは、プロセッサ/ゲートウェイ トークンまたは暗号化された支払い方法の形を取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76081-200">These can take the shape of a processor/gateway token or an encrypted payment instrument.</span></span>  <span data-ttu-id="76081-201">これらの支払い方法は、このドキュメントの対象外であり、処理者に固有のドキュメントで説明します。</span><span class="sxs-lookup"><span data-stu-id="76081-201">These payment methods are outside the scope of this document and will be covered in documentation specific to the processor.</span></span>  <span data-ttu-id="76081-202">さらに、基本カードの応答[](https://w3c.github.io/payment-method-basic-card)を受け取る場合、暗号化キーのオンボードまたは要求承認 \(oAuth\) が必要になる可能性がある他のプロセッサ/ゲートウェイ固有の支払い方法とは異なり、開発者は Microsoft への追加のオンボーディングを必要としません。</span><span class="sxs-lookup"><span data-stu-id="76081-202">Additionally, to receive a [Basic Card](https://w3c.github.io/payment-method-basic-card) response, no additional onboarding to Microsoft is required by the developer, unlike other processor/gateway specific payment methods which may require encryption key onboarding or request authorization \(oAuth\).</span></span>  

<span data-ttu-id="76081-203">支払い応答を **受信すると**、Web サイトは支払い情報を支払い処理者に送信します。</span><span class="sxs-lookup"><span data-stu-id="76081-203">Upon receiving the **Payment Response**, the website submits the payment information to their payment processor.</span></span>  <span data-ttu-id="76081-204">支払いが処理されている間、ブラウザーにスピン ボックス ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="76081-204">The browser will display a spinner page while the payment is being processed.</span></span>  

:::image type="complex" source="../media/loading_screen.png" alt-text="支払いの処理時に表示されるページ" lightbox="../media/loading_screen.png":::
   <span data-ttu-id="76081-206">支払いの処理時に表示されるページ</span><span class="sxs-lookup"><span data-stu-id="76081-206">The page displayed when the payment is being processed</span></span>  
:::image-end:::  

<span data-ttu-id="76081-207">支払いが完了すると、Web ページは [complete()](/previous-versions/mt790642(v=vs.85)) メソッドを呼び出し、成功または失敗の値 **を** 渡 **します**。</span><span class="sxs-lookup"><span data-stu-id="76081-207">Once the payment is complete, the web page calls the [complete()](/previous-versions/mt790642(v=vs.85)) method and passes a value of **success** or **fail**.</span></span>  <span data-ttu-id="76081-208">[complete()](/previous-versions/mt790642(v=vs.85))メソッドは、購入が完了し、成功または失敗の値に応じて適切な終了 UI 画面が表示される必要があるというブラウザー**に通知\*\*\*\*します**。</span><span class="sxs-lookup"><span data-stu-id="76081-208">The [complete()](/previous-versions/mt790642(v=vs.85)) method informs the browser that the purchase is finished and the appropriate terminating UI screen should be shown depending on the value of **success** or **fail**.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="購入が成功すると表示される UI" lightbox="../media/response_payment-request_complete.png":::
         <span data-ttu-id="76081-210">購入が成功すると表示される UI</span><span class="sxs-lookup"><span data-stu-id="76081-210">The UI displayed when the purchase succeeded</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="購入が失敗した場合に表示される UI" lightbox="../media/response_payment-request_failure.png":::
         <span data-ttu-id="76081-212">購入が失敗した場合に表示される UI</span><span class="sxs-lookup"><span data-stu-id="76081-212">The UI displayed when the purchase failed</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="76081-213">出荷時の支払い要求</span><span class="sxs-lookup"><span data-stu-id="76081-213">Payment Request with Shipping</span></span>  

### <span data-ttu-id="76081-214">配送先住所</span><span class="sxs-lookup"><span data-stu-id="76081-214">Shipping Address</span></span>  

<span data-ttu-id="76081-215">物理的な商品の配送が必要な販売の場合は、配送先住所が必要です。</span><span class="sxs-lookup"><span data-stu-id="76081-215">For sales that require shipping physical goods, a shipping address is required.</span></span>  <span data-ttu-id="76081-216">配送先住所を含めるには、要求 `requestShipping = True` の [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) パラメーターに設定します。</span><span class="sxs-lookup"><span data-stu-id="76081-216">To include a shipping address, set `requestShipping = True` in the [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter of the request.</span></span>  

<span data-ttu-id="76081-217">ユーザーが配送先住所を選択または更新すると [、onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) イベントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="76081-217">When the user selects or updates the shipping address, the [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) event will run.</span></span>  <span data-ttu-id="76081-218">Web サイトは、イベント リスナーを使用して変更を認識し、住所を検証し、配送料と税金を再計算し [、shippingOptions](/previous-versions/mt790440(v=vs.85)) を更新して、選択した \(該当する場合\ ) アドレスで使用可能な変更されたコストと配送オプションを反映することができます。</span><span class="sxs-lookup"><span data-stu-id="76081-218">The website, using an event listener, will be aware of the change and can then validate the address, re-calculate shipping costs and taxes, and update [shippingOptions](/previous-versions/mt790440(v=vs.85)) to reflect the changed costs and shipping options available for the address selected \(if applicable\).</span></span>  

### <span data-ttu-id="76081-219">配送オプション</span><span class="sxs-lookup"><span data-stu-id="76081-219">Shipping Options</span></span>  

<span data-ttu-id="76081-220">[shippingOptions](/previous-versions/mt790440(v=vs.85))を details パラメーターに追加することで、配送オプションを顧客に[提示](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)できます。</span><span class="sxs-lookup"><span data-stu-id="76081-220">Shipping options can be presented to the customer by adding [shippingOptions](/previous-versions/mt790440(v=vs.85)) to the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter.</span></span>  <span data-ttu-id="76081-221">出荷オプションの 1 つを設定 `selected = True` することで、既定値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="76081-221">A default can be established by setting `selected = True` for one of the shipping options.</span></span>  
 
<span data-ttu-id="76081-222">ユーザーが shippingOptions を選択または更新すると [、onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) イベントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="76081-222">When the user selects or updates the shippingOptions, the [onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) event will run.</span></span>  <span data-ttu-id="76081-223">イベント リスナーを使用して Web サイトは変更を認識し、 [詳細](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) パラメーターを正しい出荷金額で更新できます。</span><span class="sxs-lookup"><span data-stu-id="76081-223">The website, using an event listener, will be aware of the change and can update the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter with the correct shipping amount.</span></span>  

```javascript
var details = {
    total: {
        label: 'Total (USD)',
        amount: {currency: 'USD', value: '193.98'}
    },
    displayItems: [{
         label: 'Subtotal',
         amount: {currency: 'USD', value: '174.99'}
        }, {
            label: 'Shipping',
            amount: {currency: 'USD', value: '0.00'}
        }, {
            label: 'Taxes',
            amount: {currency: "USD", '18.99'}
    }],
    shippingOptions: [{
        id: 'STANDARD',
        label: 'Standard – FREE (5-6 Business days)',
        amount: {currency: 'USD', value: '0.00'},
        selected: true
    }, {
        id: 'EXPEDITED',
        label: 'Two-Day Shipping',
        amount: {currency: 'USD', value: '7.00'}
    }]
};
        
var options = {
    requestShipping: true,
    requestPayerEmail: true
}; 
```  

## <span data-ttu-id="76081-224">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="76081-224">API Reference</span></span>  

[<span data-ttu-id="76081-225">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="76081-225">Payment Request API</span></span>](/previous-versions/mt790447(v=vs.85))  

## <span data-ttu-id="76081-226">仕様</span><span class="sxs-lookup"><span data-stu-id="76081-226">Specification</span></span>
[<span data-ttu-id="76081-227">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="76081-227">Payment Request API</span></span>](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "Microsoft Edge レガシとは"  
