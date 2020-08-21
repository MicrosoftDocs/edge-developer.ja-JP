---
description: Microsoft Edge がクラウドに保存されているメッカー、コンシューマー、コンシューマー支払い方法間の中間として機能する方法について説明します。
title: お支払い要求 API - 開発ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 338940ab6f7e6bb04c6d5a8cc6ff0a198e7afbcc
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941848"
---
# <span data-ttu-id="a7c5f-104">支払要求 API (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="a7c5f-104">Payment Request API (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="a7c5f-105">この記事では、従ギャラリー バージョンの [Microsoft Edge でサポートされているワークフローについて説明します][MicrosoftSupport44533505]。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-105">This article describes the workflow supported in the [legacy version of Microsoft Edge][MicrosoftSupport44533505].</span></span>  <span data-ttu-id="a7c5f-106">Microsoft Edge \(Chromium\) では、Chromium プロジェクトに基づくさまざまな実装での支払い要求 API をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-106">Microsoft Edge \(Chromium\) supports the Payment Request API with a different implementation based on the Chromium project.</span></span>  

<span data-ttu-id="a7c5f-107">電子営業の営業担続は、高いペースで引き続き成まります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-107">E-commerce sales continue growing at a rapid pace.</span></span>  <span data-ttu-id="a7c5f-108">2018 デジタル売上高によって [は](https://www.emarketer.com)、2018 年のデジタル売上高によっては 2013 年のメジャーの 23% が上がります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-108">According to [eMarketer](https://www.emarketer.com), by 2018 digital sales are forecasted to increase by 23% from the levels measured in 2013.</span></span>  <span data-ttu-id="a7c5f-109">コンシューマーやビジネスで、電子営業の手数料を楽しみながら、チャレンジは残ります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-109">While consumers and businesses enjoy the convenience of e-commerce sales, challenges remain.</span></span>  <span data-ttu-id="a7c5f-110">この時点で、高品質な支払いチェックアウトのフローと入力規則を作成するには、各電子業者の Web サイトの所有者が時間を調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-110">Today each e-commerce website owner needs to invest time to develop high quality payment checkout flows and validation rules.</span></span>  <span data-ttu-id="a7c5f-111">コンシューマーは、別の支払いチェックアウト フローを移動し、シャッピングされているすべてのサイトで同じ支払いと配送情報を再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-111">Consumers need to navigate different payment checkout flows and re-enter the same payment and shipping information on every site where they shop.</span></span>  <span data-ttu-id="a7c5f-112">この時間は、コンシューマーのための時間を大量に使用し、高いシャプチャアントの販売を減らし、販売代理販売数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-112">This can be time consuming and frustrating for consumers, leading to a high rate of shopping cart abandonment and decreased sales for merchants.</span></span>  <span data-ttu-id="a7c5f-113">シンプリング カー[estimate](http://baymard.com/lists/cart-abandonment-rate)トの 60% から 70% の見積もりが中型的です。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-113">Merchants [estimate](http://baymard.com/lists/cart-abandonment-rate) between 60% and 70% of shopping carts are abandoned.</span></span>  

<span data-ttu-id="a7c5f-114">支払 [要求 API は](https://w3.org/TR/payment-request) 、支払チェックアウト プロセスを標準化します。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-114">The [Payment Request API](https://w3.org/TR/payment-request) standardizes the payment checkout process.</span></span>  <span data-ttu-id="a7c5f-115">この API では、Web 開発者のカスタマイズを少なくし、より高速かつ一致があり、より高速で一致を提供し、ユーザーの操作性が低下します。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-115">This API requires less customization for web developers and provides a faster, more consistent, and therefore, less confusing experience for consumers.</span></span>  <span data-ttu-id="a7c5f-116">コンシューマーはお支払い方法と配送先住所を Microsoft アカウントから選べる可能性があるため、支払いを完了するのに必要な時間とデータ入力を減らすために必要な時間とデータ入力を減らすために、購入を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-116">Because consumers can select payment instruments and shipping addresses from their Microsoft account, they are required to enter less data to complete purchases which reduces the time and data entry required to complete a payment.</span></span>  

<span data-ttu-id="a7c5f-117">[支払要求 API は開](https://w3.org/TR/payment-request)いており、クロスブラウザー標準であり、ブラウザーで、コンシューマーがクラウドに保存されているメッセント、コンシューマー、支払方法 \(クレジット カード\など) 間の中間としてブラウザーを操作できます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-117">The [Payment Request API](https://w3.org/TR/payment-request) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  
  
<span data-ttu-id="a7c5f-118">まず、 [支払要求 API を](https://w3.org/TR/payment-request)使用する場合、顧客は、メーカーの Web サイトで通常のシェープをシャットします。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-118">In summary, when using the [Payment Request API](https://w3.org/TR/payment-request), customers shop on merchant websites as normal.</span></span>  <span data-ttu-id="a7c5f-119">支払い準備ができたら、マルチェッカー Web サイトでは **支払** い要求 API を呼び出して、 **支払** い要求 API を呼び出して、関連する支払い方法 \(サポートされる支払い方法、購入金額、通貨など) をブラウザーに合わせます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-119">When ready to pay, the merchant website calls the **Payment Request** API to create a **Payment Request** and passes the relevant payment information \(such as supported payment methods, purchase amount, currency, and so on\) to the browser.</span></span>  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="お支払い要求の構造" lightbox="../media/payment_request_construct.png":::
   <span data-ttu-id="a7c5f-121">お支払い要求の構造</span><span class="sxs-lookup"><span data-stu-id="a7c5f-121">Payment request construct</span></span>  
:::image-end:::  

<span data-ttu-id="a7c5f-122">ブラウザーがユーザーを認証し、ユーザーがファイルに対してサポートされている支払い方法を選択し、支払いの詳細を処理できます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-122">The browser authenticates the user, enables the user to select a supported payment method on file, and processes the payment details.</span></span>  <span data-ttu-id="a7c5f-123">ブラウザーから支払い情報がお支払いを完了できるように、お支払い情報をメーカーの Web サイトに送信します。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-123">The browser then sends the payment information details back to the merchant website, so that the merchant can complete the payment.</span></span>  <span data-ttu-id="a7c5f-124">支払い情報を受信する他に、お支払い要求の一部として発送情報を **受**け取るようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-124">In addition to receiving payment information, the merchant can also elect to receive shipping information as part of the **Payment Request**.</span></span>  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="お支払いの返答の構造" lightbox="../media/payment_response_construct.png":::
   <span data-ttu-id="a7c5f-126">お支払いの返答の構造</span><span class="sxs-lookup"><span data-stu-id="a7c5f-126">Payment response construct</span></span>  
:::image-end:::  

<span data-ttu-id="a7c5f-127">実算依頼 API を実実に確認する方法とその使い方法の概要を確認するには、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-127">To see the Payment Request API in action, as well as get an overview of how to use it, check out this video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> <span data-ttu-id="a7c5f-128">支払いリクエスト API は、Microsoft Edge ビルド 14992 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-128">The Payment Request API is supported in Microsoft Edge build 14992 or newer.</span></span>  

## <span data-ttu-id="a7c5f-129">支払い要求の作成</span><span class="sxs-lookup"><span data-stu-id="a7c5f-129">Creating a Payment Request</span></span>  

<span data-ttu-id="a7c5f-130">Web ページでは通常 **、ユーザー** が [購入] ボタンをクリックして支払いプロセスを開始したときに、通常は支払い要求が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-130">Web pages create a **Payment Request** typically when the user initiates a payment process by clicking a "buy" button.</span></span>  <span data-ttu-id="a7c5f-131">支払**要求のコン**[トラストラクターには](/previous-versions/mt790440(v=vs.85))、methodData、details、オプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-131">The **Payment Request** [constructor](/previous-versions/mt790440(v=vs.85)) includes methodData, details, and options.</span></span>  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

<span data-ttu-id="a7c5f-132">[メソッドデータ](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)パラメーターには、Web サイトで受け付けられた支払い方法とネットワークの一覧と、関連するすべての支払い方法に関するデータが含められます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-132">The [methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains a list of the payment methods and networks accepted by the website and any associated payment method specific data.</span></span>  <span data-ttu-id="a7c5f-133">Microsoft Edge では、この一覧はサポートされている支払い方法と一致しており、お子様が Microsoft アカウントに保存され、支払いのエクスペリエンスの "お支払い" リストに結果が出てきます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-133">In Microsoft Edge, this list is matched with the supported payment methods that the shopper has saved in their Microsoft account and results in the "pay with" list in the payment user experience.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="Microsoft Wallet のユーザー エクスペリエンスのリストに表示されたお支払い" lightbox="../media/pay_with.png":::
         <span data-ttu-id="a7c5f-135">Microsoft **Wallet の** ユーザー エクスペリエンスのリストに表示されたお支払い</span><span class="sxs-lookup"><span data-stu-id="a7c5f-135">The **pay with** list in the Microsoft Wallet user experience</span></span>  
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

<span data-ttu-id="a7c5f-136">詳細 [パラメー](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) ターには、トランザクションに関する顧客に送るようにマーカーが得たい情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-136">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains information that the merchant wishes to convey to the customer about the transaction.</span></span>  <span data-ttu-id="a7c5f-137">これには、注文の合計、税額、配送額などの項目が支払金額に影響するその他のサマリー 項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-137">These include order summary items like total, tax, shipping amount, and other summary level items impacting the payment amount.</span></span>  <span data-ttu-id="a7c5f-138">これらは順序の項目を注文するものではありません。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-138">These are not intended to be order line items.</span></span>  
  
<span data-ttu-id="a7c5f-139">詳細 [パラメー](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) ターは、必要な場合に顧客が利用できる配送オプションを定義するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-139">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter is also used to define shipping options available to the customer when required.</span></span>  <span data-ttu-id="a7c5f-140">詳細については、以下の配送先**Payment Request**のセクション付きの支払い要求に含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-140">More details are included in the **Payment Request** with Shipping section below.</span></span>  

<span data-ttu-id="a7c5f-141">各 [詳細](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 行には、通貨のラベルと金額が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-141">Each [detail](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) line includes a label for the currency and the amount.</span></span>  

> [!NOTE]
> <span data-ttu-id="a7c5f-142">支払 **要求では** 、これらの金額の合計や合計は計算しません。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-142">The **Payment Request** does not calculate the sum or total of these amounts.</span></span>  <span data-ttu-id="a7c5f-143">これは、明日の Web サイトのサイトで、線のアイテムを合計し、正しくアイテムを合計させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-143">It is the responsibility of the merchant's website to ensure that the line items total correctly.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="小計、配送価額、税額、および集計の詳細" lightbox="../media/show_details.png":::
         <span data-ttu-id="a7c5f-145">小計、配送価額、税額、および集計の詳細</span><span class="sxs-lookup"><span data-stu-id="a7c5f-145">Subtotal, shipping, taxes, and total details</span></span>  
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

<span data-ttu-id="a7c5f-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) では返金はサポートされないため、金額は常に正の数にする必要があります。個々のリスト項目は割引率など、負の数にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) does not support refunds, so the amounts should always be positive; individual list items can be negative, such as discounts.</span></span>  

<span data-ttu-id="a7c5f-147">ブラウザーはラベルを定義するたびにレンダリングし、正しい通貨書式を顧客のロケールに基づいて自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-147">The browser will render the labels as you define them and automatically render the correct currency formatting based on the customer's locale.</span></span>  <span data-ttu-id="a7c5f-148">ラベルはコンテンツと同じ言語でレンダリングされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-148">Note that the labels should be rendered in the same language as your content.</span></span>  

<span data-ttu-id="a7c5f-149">オプション [パラ](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) メーターは、支払要求から返される Web ページ **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-149">The [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter defines data the web page wants returned from the **Payment Request**.</span></span>  <span data-ttu-id="a7c5f-150">出荷、メール アドレス、電話番号、すべての情報が必要な場合など、収集する必要があるデータも定義されます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-150">This also defines the data that needs to be collected, including if shipping, email address, phone number or all are required.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text="メール アドレス ドロップダウン" lightbox="../media/email_snippet.png":::
         <span data-ttu-id="a7c5f-152">メール アドレス ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="a7c5f-152">Email address dropdown</span></span>  
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

## <span data-ttu-id="a7c5f-153">支払い要求の表示</span><span class="sxs-lookup"><span data-stu-id="a7c5f-153">Showing the Payment Request</span></span>  

<span data-ttu-id="a7c5f-154">シ [ョー()](/previous-versions/mt790448(v=vs.85)) メソッドは、ユーザーが **支払** 要求のユーザー インターフェイスと対話することを許可する Web ページによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-154">The [show()](/previous-versions/mt790448(v=vs.85)) method is called by the web page to allow the user to interact with the **Payment Request** user interface.</span></span>  <span data-ttu-id="a7c5f-155">[ショー()](/previous-versions/mt790448(v=vs.85))メソッドは、ユーザーが支払要求を承認したときに解決されるプロミスを返します。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-155">The [show()](/previous-versions/mt790448(v=vs.85)) method returns a Promise that will be resolved when the user authorizes the payment request.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="確認と支払いの詳細" lightbox="../media/pay_screen_default.png":::
         <span data-ttu-id="a7c5f-157">確認と支払いの詳細</span><span class="sxs-lookup"><span data-stu-id="a7c5f-157">Confirm and pay details</span></span>  
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

## <span data-ttu-id="a7c5f-158">お支払い要求の予定に中止</span><span class="sxs-lookup"><span data-stu-id="a7c5f-158">Aborting a Payment Request</span></span>  
 
<span data-ttu-id="a7c5f-159">[Abort()](/previous-versions/mt790437(v=vs.85))メソッドは[、Promise](/previous-versions/mt790448(v=vs.85))が解決されるまで、いつでも Web ページで呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-159">The [abort()](/previous-versions/mt790437(v=vs.85)) method can be called by the web page any time after the [show()](/previous-versions/mt790448(v=vs.85)) method is called, up until the point where the Promise is resolved.</span></span>  <span data-ttu-id="a7c5f-160">[abort() メ](/previous-versions/mt790437(v=vs.85))ソッドにより、ブラウザーで支払要求が**Payment Request**中止され、支払要求のユーザー**インター**フェイスが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-160">The [abort()](/previous-versions/mt790437(v=vs.85)) method will cause the browser to abort the **Payment Request** and close the **Payment Request** user interface.</span></span>  <span data-ttu-id="a7c5f-161">たとえば、ユーザーが必要な時間にトランザクションを完了しなかった場合、Web ページが中止することがあります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-161">For example, a web page may choose to abort if the user did not complete the transaction in the required amount of time.</span></span>  

```javascript
payment.abort();
```  

## <span data-ttu-id="a7c5f-162">支払い回答</span><span class="sxs-lookup"><span data-stu-id="a7c5f-162">Payment Response</span></span>  
<span data-ttu-id="a7c5f-163">顧客が支払要求を承認すると **、\*\*\*\*支払**い回答が Web サイトに返されます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-163">When the customer approves the **Payment Request**, a **Payment Response** is returned to the website.</span></span>  <span data-ttu-id="a7c5f-164">支払 **いの応答には** 、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-164">The **Payment Response** includes the following:</span></span>  

 <span data-ttu-id="a7c5f-165">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a7c5f-165">Property</span></span>      | <span data-ttu-id="a7c5f-166">説明</span><span class="sxs-lookup"><span data-stu-id="a7c5f-166">Description</span></span> | <span data-ttu-id="a7c5f-167">必須かどうか</span><span class="sxs-lookup"><span data-stu-id="a7c5f-167">Required</span></span> | <span data-ttu-id="a7c5f-168">追加情報</span><span class="sxs-lookup"><span data-stu-id="a7c5f-168">Additional Info</span></span>
|---------------|-----------------|-------|-----------------|
[<span data-ttu-id="a7c5f-169">methodName</span><span class="sxs-lookup"><span data-stu-id="a7c5f-169">methodName</span></span>](/previous-versions/mt790656(v=vs.85)) | <span data-ttu-id="a7c5f-170">ユーザーが選択したお支払い方法の ID</span><span class="sxs-lookup"><span data-stu-id="a7c5f-170">The ID for the payment method selected by the user</span></span> | <span data-ttu-id="a7c5f-171">Y</span><span class="sxs-lookup"><span data-stu-id="a7c5f-171">Y</span></span> | |   
[<span data-ttu-id="a7c5f-172">details</span><span class="sxs-lookup"><span data-stu-id="a7c5f-172">details</span></span>](/previous-versions/mt790655(v=vs.85)) | <span data-ttu-id="a7c5f-173">マルチャントが含まれるすべてのデータを含む JSON オブジェクトでは、選択した支払い方法または支払トークンを使用してトランザクションを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-173">A JSON object that includes all of the data the merchant requires to process the transaction using the selected payment method or a payment token</span></span> | <span data-ttu-id="a7c5f-174">Y</span><span class="sxs-lookup"><span data-stu-id="a7c5f-174">Y</span></span> | <span data-ttu-id="a7c5f-175">[基本カード](https://w3c.github.io/payment-method-basic-card) 辞書: cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress;</span><span class="sxs-lookup"><span data-stu-id="a7c5f-175">[Basic Card](https://w3c.github.io/payment-method-basic-card) Dictionary:  cardholderName; cardNumber; expiryMonth; expiryYear; cardSecurityCode; billingAddress;</span></span> |   
[<span data-ttu-id="a7c5f-176">shippingAddress</span><span class="sxs-lookup"><span data-stu-id="a7c5f-176">shippingAddress</span></span>](/previous-versions/mt790445(v=vs.85)) | <span data-ttu-id="a7c5f-177">ユーザーが選択した配送先住所</span><span class="sxs-lookup"><span data-stu-id="a7c5f-177">The shipping address selected by the user</span></span>  |  <span data-ttu-id="a7c5f-178">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-178">Optional.</span></span>  <span data-ttu-id="a7c5f-179">要求の配送[時に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="a7c5f-179">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | <span data-ttu-id="a7c5f-180">住所辞書: 国;addressLine;region;city;dependentLocality;postalCode;sortingCode;languageCode;組織;recipient;電話</span><span class="sxs-lookup"><span data-stu-id="a7c5f-180">Address dictionary:  country; addressLine; region; city; dependentLocality; postalCode; sortingCode; languageCode; organization; recipient; phone</span></span> |  
[<span data-ttu-id="a7c5f-181">出荷先Option</span><span class="sxs-lookup"><span data-stu-id="a7c5f-181">shippingOption</span></span>](/previous-versions/mt790446(v=vs.85)) | <span data-ttu-id="a7c5f-182">選択した配送オプションの ID</span><span class="sxs-lookup"><span data-stu-id="a7c5f-182">The ID for the selected shipping option</span></span> | <span data-ttu-id="a7c5f-183">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-183">Optional.</span></span>  <span data-ttu-id="a7c5f-184">要求の配送[時に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="a7c5f-184">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |   
[<span data-ttu-id="a7c5f-185">payerName</span><span class="sxs-lookup"><span data-stu-id="a7c5f-185">payerName</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="a7c5f-186">ユーザーによって入力された名前</span><span class="sxs-lookup"><span data-stu-id="a7c5f-186">The name provided by the user</span></span>  | <span data-ttu-id="a7c5f-187">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-187">Optional.</span></span>  <span data-ttu-id="a7c5f-188">[requestPayerName の場合に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="a7c5f-188">Required when [requestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  
[<span data-ttu-id="a7c5f-189">payerEmail</span><span class="sxs-lookup"><span data-stu-id="a7c5f-189">payerEmail</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="a7c5f-190">ユーザーが選択したメール アドレス</span><span class="sxs-lookup"><span data-stu-id="a7c5f-190">The email address selected by the user</span></span> | <span data-ttu-id="a7c5f-191">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-191">Optional.</span></span>  <span data-ttu-id="a7c5f-192">要求[PayerEmail の場合に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="a7c5f-192">Required when [requestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |  
[<span data-ttu-id="a7c5f-193">PayerPhone</span><span class="sxs-lookup"><span data-stu-id="a7c5f-193">PayerPhone</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="a7c5f-194">ユーザーが選択した電話番号</span><span class="sxs-lookup"><span data-stu-id="a7c5f-194">The phone number selected by the user</span></span> | <span data-ttu-id="a7c5f-195">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-195">Optional.</span></span>  <span data-ttu-id="a7c5f-196">要求[PayerPhone 要求の場合に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions)</span><span class="sxs-lookup"><span data-stu-id="a7c5f-196">Required when [requestPayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  

<span data-ttu-id="a7c5f-197">**支払**[い](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params)応答の詳細な JSON オブジェクトには、お支払いを処理するのに必要な支払データが含まれている。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-197">The [details](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) JSON object in the **Payment Response** will contain the payment data required by the merchant to process a payment.</span></span>  <span data-ttu-id="a7c5f-198">その最も簡単な形式で、応答はクリアテキスト支払いカードの詳細[Basic Card](https://w3c.github.io/payment-method-basic-card)を含む基本カード ペイロードです。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-198">In its simplest form, the response will be a [Basic Card](https://w3c.github.io/payment-method-basic-card) payload containing cleartext payment card details.</span></span>  <span data-ttu-id="a7c5f-199">支払いのサポートを提供するために、マルチエイトウェイ/プロセッサ パートナーと行き込みが行われている場合、階層にはプロセッサが処理できるペイロードが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-199">Where merchants have arrangements with additional gateway/processor partners for them to provide payments support, the merchant may require a payload the processor can handle.</span></span>  <span data-ttu-id="a7c5f-200">これらは、プロセッサ/ゲートウェイ トークンの形を使用したり、暗号化された支払い方法を利用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-200">These can take the shape of a processor/gateway token or an encrypted payment instrument.</span></span>  <span data-ttu-id="a7c5f-201">これらの支払方法はこのドキュメントの範囲外であり、プロセッサに固有のドキュメントで説明します。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-201">These payment methods are outside the scope of this document and will be covered in documentation specific to the processor.</span></span>  <span data-ttu-id="a7c5f-202">さらに、基本カード応答[Basic Card](https://w3c.github.io/payment-method-basic-card)を受け取るために、暗号化キーオンによるオンボーディングや承認を要求するなどの他のプロセッサ/ゲートウェイ固有の支払い方法とは異なり、デベロッパーが Microsoft への追加のオンボーディングを行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-202">Additionally, to receive a [Basic Card](https://w3c.github.io/payment-method-basic-card) response, no additional onboarding to Microsoft is required by the developer, unlike other processor/gateway specific payment methods which may require encryption key onboarding or request authorization \(oAuth\).</span></span>  

<span data-ttu-id="a7c5f-203">支払いの応答を送る **と、お**支払い情報が支払いプロセッサに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-203">Upon receiving the **Payment Response**, the website submits the payment information to their payment processor.</span></span>  <span data-ttu-id="a7c5f-204">支払い処理中は、ブラウザーにスピナー ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-204">The browser will display a spinner page while the payment is being processed.</span></span>  

:::image type="complex" source="../media/loading_screen.png" alt-text="支払い処理中に表示されるページ" lightbox="../media/loading_screen.png":::
   <span data-ttu-id="a7c5f-206">支払い処理中に表示されるページ</span><span class="sxs-lookup"><span data-stu-id="a7c5f-206">The page displayed when the payment is being processed</span></span>  
:::image-end:::  

<span data-ttu-id="a7c5f-207">支払いが完了すると、Web ページは完全[な ()](/previous-versions/mt790642(v=vs.85))メソッドを呼び出し、成**success**功するか失**敗をつなげます**。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-207">Once the payment is complete, the web page calls the [complete()](/previous-versions/mt790642(v=vs.85)) method and passes a value of **success** or **fail**.</span></span>  <span data-ttu-id="a7c5f-208">完全[() メ](/previous-versions/mt790642(v=vs.85))ソッドは、購入が完了したブラウザーを通知し、成功する値または失敗の値に応じて適切な終了 UI**画面が表示\*\*\*\*されるようにします**。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-208">The [complete()](/previous-versions/mt790642(v=vs.85)) method informs the browser that the purchase is finished and the appropriate terminating UI screen should be shown depending on the value of **success** or **fail**.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="購入が成功したときに表示される UI" lightbox="../media/response_payment-request_complete.png":::
         <span data-ttu-id="a7c5f-210">購入が成功したときに表示される UI</span><span class="sxs-lookup"><span data-stu-id="a7c5f-210">The UI displayed when the purchase succeeded</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="購入に失敗したときに表示される UI" lightbox="../media/response_payment-request_failure.png":::
         <span data-ttu-id="a7c5f-212">購入に失敗したときに表示される UI</span><span class="sxs-lookup"><span data-stu-id="a7c5f-212">The UI displayed when the purchase failed</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="a7c5f-213">配送付付での支払要求</span><span class="sxs-lookup"><span data-stu-id="a7c5f-213">Payment Request with Shipping</span></span>  

### <span data-ttu-id="a7c5f-214">配送先住所</span><span class="sxs-lookup"><span data-stu-id="a7c5f-214">Shipping Address</span></span>  

<span data-ttu-id="a7c5f-215">出荷の商標が必要な販売の場合、発送先住所が必要です。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-215">For sales that require shipping physical goods, a shipping address is required.</span></span>  <span data-ttu-id="a7c5f-216">配送先住所を含めるには、要求 `requestShipping = True` のオプション パラ [メータ](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) ーを設定します。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-216">To include a shipping address, set `requestShipping = True` in the [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter of the request.</span></span>  

<span data-ttu-id="a7c5f-217">ユーザーが配送先住所を選択または更新すると [、onshipingaddresschange](/previous-versions/mt790442(v=vs.85)) イベントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-217">When the user selects or updates the shipping address, the [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) event will run.</span></span>  <span data-ttu-id="a7c5f-218">イベント リストを使用する Web サイトでは、変更を認め、その後住所を検証し、配送コストと税金を再計算し、 [配送オプション](/previous-versions/mt790440(v=vs.85)) を更新して、選択したアドレスで利用可能な変更されたコストと配送オプションを更新できます (適用する場合\(適用する場合\)</span><span class="sxs-lookup"><span data-stu-id="a7c5f-218">The website, using an event listener, will be aware of the change and can then validate the address, re-calculate shipping costs and taxes, and update [shippingOptions](/previous-versions/mt790440(v=vs.85)) to reflect the changed costs and shipping options available for the address selected \(if applicable\).</span></span>  

### <span data-ttu-id="a7c5f-219">配送オプション</span><span class="sxs-lookup"><span data-stu-id="a7c5f-219">Shipping Options</span></span>  

<span data-ttu-id="a7c5f-220">出荷オプションは、詳細パラメーターに [出](/previous-versions/mt790440(v=vs.85)) 荷オプションを追加することで、顧客 [に表示](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) できます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-220">Shipping options can be presented to the customer by adding [shippingOptions](/previous-versions/mt790440(v=vs.85)) to the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter.</span></span>  <span data-ttu-id="a7c5f-221">既定では、いずれかの配送オプションを `selected = True` 設定して設定できます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-221">A default can be established by setting `selected = True` for one of the shipping options.</span></span>  
 
<span data-ttu-id="a7c5f-222">出荷オプションを選択または更新すると、 [オン配送オプション変更](/previous-versions/mt790436(v=vs.85)) イベントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-222">When the user selects or updates the shippingOptions, the [onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) event will run.</span></span>  <span data-ttu-id="a7c5f-223">イベント リストを使用する Web サイトは変更を確認し、詳細パラメータ[details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)ーを正しい配送金額で更新できます。</span><span class="sxs-lookup"><span data-stu-id="a7c5f-223">The website, using an event listener, will be aware of the change and can update the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter with the correct shipping amount.</span></span>  

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

## <span data-ttu-id="a7c5f-224">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="a7c5f-224">API Reference</span></span>  

[<span data-ttu-id="a7c5f-225">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="a7c5f-225">Payment Request API</span></span>](/previous-versions/mt790447(v=vs.85))  

## <span data-ttu-id="a7c5f-226">Specification</span><span class="sxs-lookup"><span data-stu-id="a7c5f-226">Specification</span></span>
[<span data-ttu-id="a7c5f-227">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="a7c5f-227">Payment Request API</span></span>](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "Microsoft Edge レガシとは"  
