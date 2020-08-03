---
description: 支払い要求の Api によって、クラウドに保存されている商人、消費者、消費者の支払い方法の間の仲介として Microsoft Edge を使用できるようにする方法について説明します。
title: 開発ガイド-支払い要求 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/30/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: b082e311dcbe5cff3101f084e7ff2c145e6e83df
ms.sourcegitcommit: 19ef1422733ef1fd051d2b4f0263ce191e8d67bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902865"
---
# <span data-ttu-id="5d965-104">支払い要求 API (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="5d965-104">Payment Request API (EdgeHTML)</span></span>

> [!NOTE]
> <span data-ttu-id="5d965-105">この記事では、 [Microsoft Edge のレガシバージョン][MicrosoftSupport44533505]でサポートされているワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5d965-105">This article describes the workflow supported in the [legacy version of Microsoft Edge][MicrosoftSupport44533505].</span></span>  <span data-ttu-id="5d965-106">Microsoft Edge \ (Chromium \) は、Chromium プロジェクトに基づく別の実装で支払い要求 API をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5d965-106">Microsoft Edge \(Chromium\) supports the Payment Request API with a different implementation based on the Chromium project.</span></span>  

<span data-ttu-id="5d965-107">E-コマース販売は急速に成長し続けています。</span><span class="sxs-lookup"><span data-stu-id="5d965-107">E-commerce sales continue growing at a rapid pace.</span></span> <span data-ttu-id="5d965-108">[EMarketer](https://www.emarketer.com/)によれば、2018のデジタル売上は2013で測定されたレベルから23% 増加します。</span><span class="sxs-lookup"><span data-stu-id="5d965-108">According to [eMarketer](https://www.emarketer.com/), by 2018 digital sales are forecasted to increase by 23% from the levels measured in 2013.</span></span>  <span data-ttu-id="5d965-109">顧客や企業は e コマース販売の利便性を享受していますが、課題はありません。</span><span class="sxs-lookup"><span data-stu-id="5d965-109">While consumers and businesses enjoy the convenience of e-commerce sales, challenges remain.</span></span>  <span data-ttu-id="5d965-110">現在、各 e コマースの web サイト所有者は、高品質支払いのチェックアウトフローと入力規則の開発に時間を投入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d965-110">Today each e-commerce website owner needs to invest time to develop high quality payment checkout flows and validation rules.</span></span>  <span data-ttu-id="5d965-111">消費者は、さまざまな支払いのチェックアウトフローに移動して、ショッピングしているすべてのサイトに同じ支払いと配送情報を再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d965-111">Consumers need to navigate different payment checkout flows and re-enter the same payment and shipping information on every site where they shop.</span></span>  <span data-ttu-id="5d965-112">これには時間がかかり、消費者にとって不便な場合があります。これは、ショッピングカートの abandonment を高くして、商人の売り上げを減らします。</span><span class="sxs-lookup"><span data-stu-id="5d965-112">This can be time consuming and frustrating for consumers, leading to a high rate of shopping cart abandonment and decreased sales for merchants.</span></span> <span data-ttu-id="5d965-113">ショッピングカートの60% と70% の間の商人の[見積](http://baymard.com/lists/cart-abandonment-rate)は中止されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-113">Merchants [estimate](http://baymard.com/lists/cart-abandonment-rate) between 60% and 70% of shopping carts are abandoned.</span></span>      

<span data-ttu-id="5d965-114">[支払い要求 API](https://w3.org/TR/payment-request/)は支払いのチェックアウトプロセスを標準化します。</span><span class="sxs-lookup"><span data-stu-id="5d965-114">The [Payment Request API](https://w3.org/TR/payment-request/) standardizes the payment checkout process.</span></span> <span data-ttu-id="5d965-115">この API は、web 開発者にとってカスタマイズが少なく、より高速で一貫性があり、利用者にとって混乱を招くことがあります。</span><span class="sxs-lookup"><span data-stu-id="5d965-115">This API requires less customization for web developers and provides a faster, more consistent, and therefore, less confusing experience for consumers.</span></span>  <span data-ttu-id="5d965-116">消費者は Microsoft アカウントから支払い方法と配送先住所を選ぶことができるため、購入を完了するために必要なデータが少ない場合は、支払いを完了するのに必要な時間とデータ入力量が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="5d965-116">Because consumers can select payment instruments and shipping addresses from their Microsoft account, they are required to enter less data to complete purchases which reduces the time and data entry required to complete a payment.</span></span>   

<span data-ttu-id="5d965-117">[支払い要求 API](https://w3.org/TR/payment-request/)は、ユーザーがクラウドに保存されているマーチャント、消費者、支払方法 (クレジットカードなど) との仲介としてブラウザーを有効にする、オープンなクロスブラウザー標準です。</span><span class="sxs-lookup"><span data-stu-id="5d965-117">The [Payment Request API](https://w3.org/TR/payment-request/) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and the payment methods (e.g. credit cards) that consumers have stored in the cloud.</span></span> 
  
<span data-ttu-id="5d965-118">概要では、[支払い要求 API](https://w3.org/TR/payment-request/)を使用している場合、ユーザーは一般に商人の web サイトを購入することになります。</span><span class="sxs-lookup"><span data-stu-id="5d965-118">In summary, when using the [Payment Request API](https://w3.org/TR/payment-request/), customers shop on merchant websites as normal.</span></span>  <span data-ttu-id="5d965-119">支払いの準備ができたら、マーチャントの web サイトは**支払い要求**API を呼び出して**支払い要求**を作成し、関連する支払い情報 (サポートされている支払い方法、購入額、通貨など) をブラウザーに渡します。</span><span class="sxs-lookup"><span data-stu-id="5d965-119">When ready to pay, the merchant website calls the **Payment Request** API to create a **Payment Request** and passes the relevant payment information (e.g. supported payment methods, purchase amount, currency, etc.) to the browser.</span></span>

![支払い要求構成](./../media/payment_request_construct.png)

<span data-ttu-id="5d965-121">ブラウザーはユーザーを認証し、ファイルでサポートされている支払い方法をユーザーが選択できるようにし、支払いの詳細を処理します。</span><span class="sxs-lookup"><span data-stu-id="5d965-121">The browser authenticates the user, enables the user to select a supported payment method on file, and processes the payment details.</span></span> <span data-ttu-id="5d965-122">次に、ブラウザーは支払い情報の詳細を商人の web サイトに返送して、販売業者が支払いを完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5d965-122">The browser then sends the payment information details back to the merchant website, so that the merchant can complete the payment.</span></span>  <span data-ttu-id="5d965-123">販売業者は、支払い情報を受け取るだけでなく、**支払い要求**の一部として配送情報を受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d965-123">In addition to receiving payment information, the merchant can also elect to receive shipping information as part of the **Payment Request**.</span></span>  

![支払いの返信の構成](./../media/payment_response_construct.png)

<span data-ttu-id="5d965-125">支払い要求 API の使用方法を確認するには、「このビデオをご覧ください」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d965-125">To see the Payment Request API in action, as well as get an overview of how to use it, check out this video.</span></span>

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]


> [!NOTE]
> <span data-ttu-id="5d965-126">支払い要求 API は、Microsoft Edge ビルド 14992 + でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d965-126">The Payment Request API is supported in Microsoft Edge build 14992+.</span></span>


## <span data-ttu-id="5d965-127">支払い要求の作成</span><span class="sxs-lookup"><span data-stu-id="5d965-127">Creating a Payment Request</span></span> 
<span data-ttu-id="5d965-128">[Web ページ] をクリックすると、通常、ユーザーが "購入" ボタンをクリックして支払いプロセスを開始したときに、**支払い要求**が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-128">Web pages create a **Payment Request** typically when the user initiates a payment process by clicking a "buy" button.</span></span>  <span data-ttu-id="5d965-129">**支払い要求**[コンストラクター](https://msdn.microsoft.com/library/mt790440)には、methoddata、details、および options が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d965-129">The **Payment Request** [constructor](https://msdn.microsoft.com/library/mt790440) includes methodData, details, and options.</span></span> 

```js
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```

<span data-ttu-id="5d965-130">このパラメーターには、 [`methodData`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) web サイトによって承認された支払い方法とネットワークの一覧と、関連する支払い方法に関する特定のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d965-130">The [`methodData`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter contains a list of the payment methods and networks accepted by the website and any associated payment method specific data.</span></span> <span data-ttu-id="5d965-131">Microsoft Edge では、この一覧は、お客様の Microsoft アカウントに保存されている、サポート対象の支払い方法に対応しており、支払いユーザーエクスペリエンスの [お支払い] リストになります。</span><span class="sxs-lookup"><span data-stu-id="5d965-131">In Microsoft Edge, this list is matched with the supported payment methods that the shopper has saved in their Microsoft account and results in the "pay with" list in the payment user experience.</span></span>

![Microsoft ウォレットのユーザーエクスペリエンスの [プリペイド] リスト](./../media/pay_with.png)

```js
var supportedInstruments = [{
    supportedMethods: ['basic-card'],
    data: {
        supportedNetworks: ['visa', 'mastercard', 'amex'],
        supportedTypes: ['credit'] 
    }         
}]; 
```

<span data-ttu-id="5d965-133">このパラメーターには、 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 販売業者がトランザクションについて顧客に伝える情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d965-133">The [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter contains information that the merchant wishes to convey to the customer about the transaction.</span></span>  <span data-ttu-id="5d965-134">これには、支払い金額に影響を与える、合計、税、送料などの注文の概要項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d965-134">These include order summary items like total, tax, shipping amount, and other summary level items impacting the payment amount.</span></span> <span data-ttu-id="5d965-135">これらは、注文明細行の項目としてのものではありません。</span><span class="sxs-lookup"><span data-stu-id="5d965-135">These are not intended to be order line items.</span></span> 
  
<span data-ttu-id="5d965-136">この [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) パラメーターは、必要に応じて顧客が利用できる送付オプションを定義するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-136">The [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter is also used to define shipping options available to the customer when required.</span></span>  <span data-ttu-id="5d965-137">詳細については、下記の「送付の**リクエスト**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d965-137">More details are included in the **Payment Request** with Shipping section below.</span></span> 

<span data-ttu-id="5d965-138">各 [`detail`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 行には、通貨と金額のラベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d965-138">Each [`detail`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) line includes a label for the currency and the amount.</span></span>  

> [!NOTE]
> <span data-ttu-id="5d965-139">**支払い要求**では、これらの金額の合計または合計は計算されません。</span><span class="sxs-lookup"><span data-stu-id="5d965-139">The **Payment Request** does not calculate the sum or total of these amounts.</span></span>  <span data-ttu-id="5d965-140">行の項目の合計が正しくなるように、商人の web サイトで行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d965-140">It is the responsibility of the merchant's website to ensure that the line items total correctly.</span></span>   


![小計、発送、税、合計の詳細](./../media/show_details.png)

```js
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

<span data-ttu-id="5d965-142">[`PaymentRequest`](https://msdn.microsoft.com/library/mt790440)は返金をサポートしていないため、金額は常に正になる必要があります。割引など、個々のリスト項目を負の値にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d965-142">[`PaymentRequest`](https://msdn.microsoft.com/library/mt790440) does not support refunds, so the amounts should always be positive; individual list items can be negative, such as discounts.</span></span> 

<span data-ttu-id="5d965-143">ブラウザーは、ラベルを定義したとおりに表示し、顧客のロケールに基づいて正しい通貨書式を自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="5d965-143">The browser will render the labels as you define them and automatically render the correct currency formatting based on the customer's locale.</span></span> <span data-ttu-id="5d965-144">ラベルは、コンテンツと同じ言語でレンダリングする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5d965-144">Note that the labels should be rendered in the same language as your content.</span></span> 

<span data-ttu-id="5d965-145">この [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) パラメーターは、web ページが**支払い要求**から返すデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d965-145">The [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter defines data the web page wants returned from the **Payment Request**.</span></span> <span data-ttu-id="5d965-146">これにより、出荷、メールアドレス、電話番号などの情報が必要な場合など、収集する必要があるデータも定義されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-146">This also defines the data that needs to be collected, including if shipping, email address, and/or phone number are required.</span></span>

![メールアドレスドロップダウン](./../media/email_snippet.png)


```js
var options =
    {
        requestPayerEmail: true
    }; 
``` 

## <span data-ttu-id="5d965-148">支払い要求の表示</span><span class="sxs-lookup"><span data-stu-id="5d965-148">Showing the Payment Request</span></span>

<span data-ttu-id="5d965-149">この [`show()`](https://msdn.microsoft.com/library/mt790448) メソッドは、ユーザーが**支払い要求**のユーザーインターフェイスを操作できるように、web ページによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-149">The [`show()`](https://msdn.microsoft.com/library/mt790448) method is called by the web page to allow the user to interact with the **Payment Request** user interface.</span></span>  <span data-ttu-id="5d965-150">この [`show()`](https://msdn.microsoft.com/library/mt790448) メソッドは、ユーザーが支払い要求を承認したときに解決される Promise を返します。</span><span class="sxs-lookup"><span data-stu-id="5d965-150">The [`show()`](https://msdn.microsoft.com/library/mt790448) method returns a Promise that will be resolved when the user authorizes the payment request.</span></span>  

```js
paymentRequest.show().then(paymentInstrumentResponse => {

paymentInstrumentResponse.complete('success').then().catch(error => {
    handlePaymentRequestError(error); 
});
```

![確認とお支払いの詳細](./../media/pay_screen_default.png)

## <span data-ttu-id="5d965-152">支払い要求の中止</span><span class="sxs-lookup"><span data-stu-id="5d965-152">Aborting a Payment Request</span></span>
 
<span data-ttu-id="5d965-153">メソッドは、 [`abort()`](https://msdn.microsoft.com/library/mt790437) メソッドが呼び出された後も [`show()`](https://msdn.microsoft.com/library/mt790448) 、Promise が解決されるポイントまで、いつでも web ページから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d965-153">The [`abort()`](https://msdn.microsoft.com/library/mt790437) method can be called by the web page any time after the [`show()`](https://msdn.microsoft.com/library/mt790448) method is called, up until the point where the Promise is resolved.</span></span>  <span data-ttu-id="5d965-154">この [`abort()`](https://msdn.microsoft.com/library/mt790437) メソッドを使うと、ブラウザーで**支払い要求**が中止され、**支払い要求**のユーザーインターフェイスが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="5d965-154">The [`abort()`](https://msdn.microsoft.com/library/mt790437) method will cause the browser to abort the **Payment Request** and close the **Payment Request** user interface.</span></span>  <span data-ttu-id="5d965-155">たとえば、web ページは、ユーザーが必要な時間内にトランザクションを完了しなかった場合に、中断することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5d965-155">For example, a web page may choose to abort if the user did not complete the transaction in the required amount of time.</span></span>

```js
payment.abort();
``` 

## <span data-ttu-id="5d965-156">支払いの返信</span><span class="sxs-lookup"><span data-stu-id="5d965-156">Payment Response</span></span>
<span data-ttu-id="5d965-157">顧客が**支払い要求**を承認すると、web サイトに**支払い応答**が返されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-157">When the customer approves the **Payment Request**, a **Payment Response** is returned to the website.</span></span> <span data-ttu-id="5d965-158">**支払いの返信**には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d965-158">The **Payment Response** includes the following:</span></span> 

 <span data-ttu-id="5d965-159">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5d965-159">Property</span></span>      | <span data-ttu-id="5d965-160">説明</span><span class="sxs-lookup"><span data-stu-id="5d965-160">Description</span></span> | <span data-ttu-id="5d965-161">必須かどうか</span><span class="sxs-lookup"><span data-stu-id="5d965-161">Required</span></span> | <span data-ttu-id="5d965-162">追加情報</span><span class="sxs-lookup"><span data-stu-id="5d965-162">Additional Info</span></span>
|---------------|-----------------|-------|-----------------|
[`methodName`](https://msdn.microsoft.com/library/mt790656) | <span data-ttu-id="5d965-163">ユーザーによって選択された支払方法の ID</span><span class="sxs-lookup"><span data-stu-id="5d965-163">The ID for the payment method selected by the user</span></span> | <span data-ttu-id="5d965-164">Y</span><span class="sxs-lookup"><span data-stu-id="5d965-164">Y</span></span> | | 
[`details`](https://msdn.microsoft.com/library/mt790655) | <span data-ttu-id="5d965-165">選択された支払い方法または支払いトークンを使って取引を処理するために必要なすべてのデータが含まれている JSON オブジェクト</span><span class="sxs-lookup"><span data-stu-id="5d965-165">A JSON object that includes all of the data the merchant requires to process the transaction using the selected payment method or a payment token</span></span> | <span data-ttu-id="5d965-166">Y</span><span class="sxs-lookup"><span data-stu-id="5d965-166">Y</span></span> | <span data-ttu-id="5d965-167">[基本カード](https://go.microsoft.com/fwlink/?linkid=834965)辞書: cardholderName;カード番号;expiryMonth;expiryYear;cardSecurityCode;住所</span><span class="sxs-lookup"><span data-stu-id="5d965-167">[Basic Card](https://go.microsoft.com/fwlink/?linkid=834965) Dictionary: cardholderName; cardNumber; expiryMonth; expiryYear; cardSecurityCode; billingAddress;</span></span> | 
[`shippingAddress`](https://msdn.microsoft.com/library/mt790445) | <span data-ttu-id="5d965-168">ユーザーによって選択された送付先住所</span><span class="sxs-lookup"><span data-stu-id="5d965-168">The shipping address selected by the user</span></span>  |  <span data-ttu-id="5d965-169">省略可能。</span><span class="sxs-lookup"><span data-stu-id="5d965-169">Optional.</span></span> <span data-ttu-id="5d965-170">[`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須</span><span class="sxs-lookup"><span data-stu-id="5d965-170">Required when [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span>  | <span data-ttu-id="5d965-171">住所辞書: 国;addressLine;地域都市dependentLocality 性;郵便sortingCode;languageCode;組織宛てダイヤル</span><span class="sxs-lookup"><span data-stu-id="5d965-171">Address dictionary: country; addressLine; region; city; dependentLocality; postalCode; sortingCode; languageCode; organization; recipient; phone</span></span> |
[`shippingOption`](https://msdn.microsoft.com/library/mt790446) | <span data-ttu-id="5d965-172">選択されている送付オプションの ID</span><span class="sxs-lookup"><span data-stu-id="5d965-172">The ID for the selected shipping option</span></span> | <span data-ttu-id="5d965-173">省略可能。</span><span class="sxs-lookup"><span data-stu-id="5d965-173">Optional.</span></span> <span data-ttu-id="5d965-174">[`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須</span><span class="sxs-lookup"><span data-stu-id="5d965-174">Required when [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span>  | | 
[`payerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | <span data-ttu-id="5d965-175">ユーザーが指定した名前</span><span class="sxs-lookup"><span data-stu-id="5d965-175">The name provided by the user</span></span>  | <span data-ttu-id="5d965-176">省略可能。</span><span class="sxs-lookup"><span data-stu-id="5d965-176">Optional.</span></span> <span data-ttu-id="5d965-177">[`requestPayerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須</span><span class="sxs-lookup"><span data-stu-id="5d965-177">Required when [`requestPayerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span> | |
[`payerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | <span data-ttu-id="5d965-178">ユーザーによって選択されたメールアドレス</span><span class="sxs-lookup"><span data-stu-id="5d965-178">The email address selected by the user</span></span> | <span data-ttu-id="5d965-179">省略可能。</span><span class="sxs-lookup"><span data-stu-id="5d965-179">Optional.</span></span> <span data-ttu-id="5d965-180">[`requestPayerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須</span><span class="sxs-lookup"><span data-stu-id="5d965-180">Required when [`requestPayerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span>  | |
[`PayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | <span data-ttu-id="5d965-181">ユーザーによって選択された電話番号</span><span class="sxs-lookup"><span data-stu-id="5d965-181">The phone number selected by the user</span></span> | <span data-ttu-id="5d965-182">省略可能。</span><span class="sxs-lookup"><span data-stu-id="5d965-182">Optional.</span></span> <span data-ttu-id="5d965-183">[`requestPayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須</span><span class="sxs-lookup"><span data-stu-id="5d965-183">Required when [`requestPayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span> | |

<span data-ttu-id="5d965-184">[`details`](https://msdn.microsoft.com/library/mt790655#PaymentRequest_params)**支払い応答**の JSON オブジェクトには、支払いを処理するために販売業者が必要とする支払いデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d965-184">The [`details`](https://msdn.microsoft.com/library/mt790655#PaymentRequest_params) JSON object in the **Payment Response** will contain the payment data required by the merchant to process a payment.</span></span> <span data-ttu-id="5d965-185">最も単純な形式では、応答は、クリアテキストの支払い用カードの詳細を含む[基本的なカード](https://go.microsoft.com/fwlink/?linkid=834965)ペイロードになります。</span><span class="sxs-lookup"><span data-stu-id="5d965-185">In its simplest form, the response will be a [Basic Card](https://go.microsoft.com/fwlink/?linkid=834965) payload containing cleartext payment card details.</span></span> <span data-ttu-id="5d965-186">商人が料金のサポートを提供するために、追加のゲートウェイ/プロセッサパートナーとの間で取り決めを行っている場合、販売業者はプロセッサが処理できるペイロードを必要としている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d965-186">Where merchants have arrangements with additional gateway/processor partners for them to provide payments support, the merchant may require a payload the processor can handle.</span></span> <span data-ttu-id="5d965-187">これらは、プロセッサ/ゲートウェイトークン、または暗号化された支払い方法の形を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5d965-187">These can take the shape of a processor/gateway token or an encrypted payment instrument.</span></span> <span data-ttu-id="5d965-188">これらの支払方法は、このドキュメントの範囲外であり、プロセッサ固有のドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="5d965-188">These payment methods are outside the scope of this document and will be covered in documentation specific to the processor.</span></span> <span data-ttu-id="5d965-189">また、[基本的なカード](https://go.microsoft.com/fwlink/?linkid=834965)応答を受信するために、開発者は、暗号化キーのオンボードまたは要求の承認 (oauth) を必要とする可能性があるその他のプロセッサ/ゲートウェイ固有の支払い方法とは異なり、Microsoft への追加のオンボードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5d965-189">Additionally, to receive a [Basic Card](https://go.microsoft.com/fwlink/?linkid=834965) response, no additional onboarding to Microsoft is required by the developer, unlike other processor/gateway specific payment methods which may require encryption key onboarding or request authorization (oauth).</span></span> 

<span data-ttu-id="5d965-190">支払いの**返信**を受信すると、web サイトから支払い情報が支払い処理プロセッサに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-190">Upon receiving the **Payment Response**, the website submits the payment information to their payment processor.</span></span>  <span data-ttu-id="5d965-191">支払いが処理されている間、ブラウザーはスピンボタンを表示します。</span><span class="sxs-lookup"><span data-stu-id="5d965-191">The browser will display a spinner page while the payment is being processed.</span></span>

![支払いが処理されているときに表示されるページ](./../media/loading_screen.png)

<span data-ttu-id="5d965-193">支払いが完了すると、web ページからメソッドが呼び出され、 [`complete()`](https://msdn.microsoft.com/library/mt790642) **成功**または**失敗**の値が渡されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-193">Once the payment is complete, the web page calls the [`complete()`](https://msdn.microsoft.com/library/mt790642) method and passes a value of **success** or **fail**.</span></span>  <span data-ttu-id="5d965-194">メソッドによって、 [`complete()`](https://msdn.microsoft.com/library/mt790642) 購入が完了したことがブラウザーに通知され、**成功**または**失敗**の値に応じて、適切な終了 UI 画面が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d965-194">The [`complete()`](https://msdn.microsoft.com/library/mt790642) method informs the browser that the purchase is finished and the appropriate terminating UI screen should be shown depending on the value of **success** or **fail**.</span></span> 

![<span data-ttu-id="5d965-195">購入に ](./../media/response_payment-request_complete.png)
![ 失敗したときに表示された ui が、購入に成功したときに表示される ui</span><span class="sxs-lookup"><span data-stu-id="5d965-195">The UI displayed when the purchase succeeded](./../media/response_payment-request_complete.png)
![The UI displayed when the purchase failed</span></span>](./../media/response_payment-request_failure.png)

## <span data-ttu-id="5d965-196">送料付きの支払い要求</span><span class="sxs-lookup"><span data-stu-id="5d965-196">Payment Request with Shipping</span></span>

### <span data-ttu-id="5d965-197">配送先住所</span><span class="sxs-lookup"><span data-stu-id="5d965-197">Shipping Address</span></span>

<span data-ttu-id="5d965-198">現物商品を発送する必要がある売上については、配送先住所が必要です。</span><span class="sxs-lookup"><span data-stu-id="5d965-198">For sales that require shipping physical goods, a shipping address is required.</span></span>  <span data-ttu-id="5d965-199">送付先住所を含めるには、 `requestShipping = True` [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 要求のパラメーターで設定します。</span><span class="sxs-lookup"><span data-stu-id="5d965-199">To include a shipping address, set `requestShipping = True` in the [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter of the request.</span></span>   

<span data-ttu-id="5d965-200">ユーザーが配送先住所を選択または更新すると、 [`onshippingaddresschange`](https://msdn.microsoft.com/library/mt790442) イベントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-200">When the user selects or updates the shipping address, the [`onshippingaddresschange`](https://msdn.microsoft.com/library/mt790442) event will run.</span></span>  <span data-ttu-id="5d965-201">イベントリスナーを使用している web サイトでは、変更を認識して、住所を検証し、送料と税金を再計算し、 [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) 選択した住所に適用されている料金および配送オプションの変更 (該当する場合) を反映するように更新することができます。</span><span class="sxs-lookup"><span data-stu-id="5d965-201">The website, using an event listener, will be aware of the change and can then validate the address, re-calculate shipping costs and taxes, and update [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) to reflect the changed costs and shipping options available for the address selected (if applicable).</span></span> 

### <span data-ttu-id="5d965-202">送付オプション</span><span class="sxs-lookup"><span data-stu-id="5d965-202">Shipping Options</span></span> 

<span data-ttu-id="5d965-203">送付オプションは、パラメーターに追加することで顧客に表示でき [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) ます。</span><span class="sxs-lookup"><span data-stu-id="5d965-203">Shipping options can be presented to the customer by adding [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) to the [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter.</span></span>  <span data-ttu-id="5d965-204">既定値は、いずれかの送付オプションの設定によって確立でき `selected = True` ます。</span><span class="sxs-lookup"><span data-stu-id="5d965-204">A default can be established by setting `selected = True` for one of the shipping options.</span></span> 
 
<span data-ttu-id="5d965-205">ユーザーが shippingOptions を選択または更新すると、 [`onshippingoptionchange`](https://msdn.microsoft.com/library/mt790436) イベントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d965-205">When the user selects or updates the shippingOptions, the [`onshippingoptionchange`](https://msdn.microsoft.com/library/mt790436) event will run.</span></span>  <span data-ttu-id="5d965-206">イベントリスナーを使用する web サイトでは、変更を認識し、 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 正しい配送金額でパラメーターを更新できます。</span><span class="sxs-lookup"><span data-stu-id="5d965-206">The website, using an event listener, will be aware of the change and can update the [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter with the correct shipping amount.</span></span>   

```js
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

## <span data-ttu-id="5d965-207">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="5d965-207">API Reference</span></span>
[<span data-ttu-id="5d965-208">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="5d965-208">Payment Request API</span></span>](https://msdn.microsoft.com/library/mt790447)

## <span data-ttu-id="5d965-209">キャスト</span><span class="sxs-lookup"><span data-stu-id="5d965-209">Specification</span></span>
[<span data-ttu-id="5d965-210">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="5d965-210">Payment Request API</span></span>](https://w3.org/TR/payment-request/)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "Microsoft Edge Legacy とは何ですか?"  
