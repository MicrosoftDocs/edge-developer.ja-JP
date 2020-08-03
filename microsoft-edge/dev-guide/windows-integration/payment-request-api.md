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
# 支払い要求 API (EdgeHTML)

> [!NOTE]
> この記事では、 [Microsoft Edge のレガシバージョン][MicrosoftSupport44533505]でサポートされているワークフローについて説明します。  Microsoft Edge \ (Chromium \) は、Chromium プロジェクトに基づく別の実装で支払い要求 API をサポートします。  

E-コマース販売は急速に成長し続けています。 [EMarketer](https://www.emarketer.com/)によれば、2018のデジタル売上は2013で測定されたレベルから23% 増加します。  顧客や企業は e コマース販売の利便性を享受していますが、課題はありません。  現在、各 e コマースの web サイト所有者は、高品質支払いのチェックアウトフローと入力規則の開発に時間を投入する必要があります。  消費者は、さまざまな支払いのチェックアウトフローに移動して、ショッピングしているすべてのサイトに同じ支払いと配送情報を再入力する必要があります。  これには時間がかかり、消費者にとって不便な場合があります。これは、ショッピングカートの abandonment を高くして、商人の売り上げを減らします。 ショッピングカートの60% と70% の間の商人の[見積](http://baymard.com/lists/cart-abandonment-rate)は中止されます。      

[支払い要求 API](https://w3.org/TR/payment-request/)は支払いのチェックアウトプロセスを標準化します。 この API は、web 開発者にとってカスタマイズが少なく、より高速で一貫性があり、利用者にとって混乱を招くことがあります。  消費者は Microsoft アカウントから支払い方法と配送先住所を選ぶことができるため、購入を完了するために必要なデータが少ない場合は、支払いを完了するのに必要な時間とデータ入力量が少なくなります。   

[支払い要求 API](https://w3.org/TR/payment-request/)は、ユーザーがクラウドに保存されているマーチャント、消費者、支払方法 (クレジットカードなど) との仲介としてブラウザーを有効にする、オープンなクロスブラウザー標準です。 
  
概要では、[支払い要求 API](https://w3.org/TR/payment-request/)を使用している場合、ユーザーは一般に商人の web サイトを購入することになります。  支払いの準備ができたら、マーチャントの web サイトは**支払い要求**API を呼び出して**支払い要求**を作成し、関連する支払い情報 (サポートされている支払い方法、購入額、通貨など) をブラウザーに渡します。

![支払い要求構成](./../media/payment_request_construct.png)

ブラウザーはユーザーを認証し、ファイルでサポートされている支払い方法をユーザーが選択できるようにし、支払いの詳細を処理します。 次に、ブラウザーは支払い情報の詳細を商人の web サイトに返送して、販売業者が支払いを完了できるようにします。  販売業者は、支払い情報を受け取るだけでなく、**支払い要求**の一部として配送情報を受け取ることもできます。  

![支払いの返信の構成](./../media/payment_response_construct.png)

支払い要求 API の使用方法を確認するには、「このビデオをご覧ください」を参照してください。

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]


> [!NOTE]
> 支払い要求 API は、Microsoft Edge ビルド 14992 + でサポートされています。


## 支払い要求の作成 
[Web ページ] をクリックすると、通常、ユーザーが "購入" ボタンをクリックして支払いプロセスを開始したときに、**支払い要求**が作成されます。  **支払い要求**[コンストラクター](https://msdn.microsoft.com/library/mt790440)には、methoddata、details、および options が含まれます。 

```js
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```

このパラメーターには、 [`methodData`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) web サイトによって承認された支払い方法とネットワークの一覧と、関連する支払い方法に関する特定のデータが含まれます。 Microsoft Edge では、この一覧は、お客様の Microsoft アカウントに保存されている、サポート対象の支払い方法に対応しており、支払いユーザーエクスペリエンスの [お支払い] リストになります。

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

このパラメーターには、 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 販売業者がトランザクションについて顧客に伝える情報が含まれています。  これには、支払い金額に影響を与える、合計、税、送料などの注文の概要項目が含まれます。 これらは、注文明細行の項目としてのものではありません。 
  
この [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) パラメーターは、必要に応じて顧客が利用できる送付オプションを定義するためにも使用されます。  詳細については、下記の「送付の**リクエスト**」を参照してください。 

各 [`detail`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 行には、通貨と金額のラベルが含まれています。  

> [!NOTE]
> **支払い要求**では、これらの金額の合計または合計は計算されません。  行の項目の合計が正しくなるように、商人の web サイトで行う必要があります。   


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

[`PaymentRequest`](https://msdn.microsoft.com/library/mt790440)は返金をサポートしていないため、金額は常に正になる必要があります。割引など、個々のリスト項目を負の値にすることができます。 

ブラウザーは、ラベルを定義したとおりに表示し、顧客のロケールに基づいて正しい通貨書式を自動的に表示します。 ラベルは、コンテンツと同じ言語でレンダリングする必要があることに注意してください。 

この [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) パラメーターは、web ページが**支払い要求**から返すデータを定義します。 これにより、出荷、メールアドレス、電話番号などの情報が必要な場合など、収集する必要があるデータも定義されます。

![メールアドレスドロップダウン](./../media/email_snippet.png)


```js
var options =
    {
        requestPayerEmail: true
    }; 
``` 

## 支払い要求の表示

この [`show()`](https://msdn.microsoft.com/library/mt790448) メソッドは、ユーザーが**支払い要求**のユーザーインターフェイスを操作できるように、web ページによって呼び出されます。  この [`show()`](https://msdn.microsoft.com/library/mt790448) メソッドは、ユーザーが支払い要求を承認したときに解決される Promise を返します。  

```js
paymentRequest.show().then(paymentInstrumentResponse => {

paymentInstrumentResponse.complete('success').then().catch(error => {
    handlePaymentRequestError(error); 
});
```

![確認とお支払いの詳細](./../media/pay_screen_default.png)

## 支払い要求の中止
 
メソッドは、 [`abort()`](https://msdn.microsoft.com/library/mt790437) メソッドが呼び出された後も [`show()`](https://msdn.microsoft.com/library/mt790448) 、Promise が解決されるポイントまで、いつでも web ページから呼び出すことができます。  この [`abort()`](https://msdn.microsoft.com/library/mt790437) メソッドを使うと、ブラウザーで**支払い要求**が中止され、**支払い要求**のユーザーインターフェイスが閉じられます。  たとえば、web ページは、ユーザーが必要な時間内にトランザクションを完了しなかった場合に、中断することを選択できます。

```js
payment.abort();
``` 

## 支払いの返信
顧客が**支払い要求**を承認すると、web サイトに**支払い応答**が返されます。 **支払いの返信**には、次のものが含まれます。 

 プロパティ      | 説明 | 必須かどうか | 追加情報
|---------------|-----------------|-------|-----------------|
[`methodName`](https://msdn.microsoft.com/library/mt790656) | ユーザーによって選択された支払方法の ID | Y | | 
[`details`](https://msdn.microsoft.com/library/mt790655) | 選択された支払い方法または支払いトークンを使って取引を処理するために必要なすべてのデータが含まれている JSON オブジェクト | Y | [基本カード](https://go.microsoft.com/fwlink/?linkid=834965)辞書: cardholderName;カード番号;expiryMonth;expiryYear;cardSecurityCode;住所 | 
[`shippingAddress`](https://msdn.microsoft.com/library/mt790445) | ユーザーによって選択された送付先住所  |  省略可能。 [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須  | 住所辞書: 国;addressLine;地域都市dependentLocality 性;郵便sortingCode;languageCode;組織宛てダイヤル |
[`shippingOption`](https://msdn.microsoft.com/library/mt790446) | 選択されている送付オプションの ID | 省略可能。 [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須  | | 
[`payerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | ユーザーが指定した名前  | 省略可能。 [`requestPayerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須 | |
[`payerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | ユーザーによって選択されたメールアドレス | 省略可能。 [`requestPayerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須  | |
[`PayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | ユーザーによって選択された電話番号 | 省略可能。 [`requestPayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) **True**の場合に必須 | |

[`details`](https://msdn.microsoft.com/library/mt790655#PaymentRequest_params)**支払い応答**の JSON オブジェクトには、支払いを処理するために販売業者が必要とする支払いデータが含まれます。 最も単純な形式では、応答は、クリアテキストの支払い用カードの詳細を含む[基本的なカード](https://go.microsoft.com/fwlink/?linkid=834965)ペイロードになります。 商人が料金のサポートを提供するために、追加のゲートウェイ/プロセッサパートナーとの間で取り決めを行っている場合、販売業者はプロセッサが処理できるペイロードを必要としている可能性があります。 これらは、プロセッサ/ゲートウェイトークン、または暗号化された支払い方法の形を取ることができます。 これらの支払方法は、このドキュメントの範囲外であり、プロセッサ固有のドキュメントに記載されています。 また、[基本的なカード](https://go.microsoft.com/fwlink/?linkid=834965)応答を受信するために、開発者は、暗号化キーのオンボードまたは要求の承認 (oauth) を必要とする可能性があるその他のプロセッサ/ゲートウェイ固有の支払い方法とは異なり、Microsoft への追加のオンボードは必要ありません。 

支払いの**返信**を受信すると、web サイトから支払い情報が支払い処理プロセッサに送信されます。  支払いが処理されている間、ブラウザーはスピンボタンを表示します。

![支払いが処理されているときに表示されるページ](./../media/loading_screen.png)

支払いが完了すると、web ページからメソッドが呼び出され、 [`complete()`](https://msdn.microsoft.com/library/mt790642) **成功**または**失敗**の値が渡されます。  メソッドによって、 [`complete()`](https://msdn.microsoft.com/library/mt790642) 購入が完了したことがブラウザーに通知され、**成功**または**失敗**の値に応じて、適切な終了 UI 画面が表示されるようになります。 

![購入に ](./../media/response_payment-request_complete.png)
![ 失敗したときに表示された ui が、購入に成功したときに表示される ui](./../media/response_payment-request_failure.png)

## 送料付きの支払い要求

### 配送先住所

現物商品を発送する必要がある売上については、配送先住所が必要です。  送付先住所を含めるには、 `requestShipping = True` [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 要求のパラメーターで設定します。   

ユーザーが配送先住所を選択または更新すると、 [`onshippingaddresschange`](https://msdn.microsoft.com/library/mt790442) イベントが実行されます。  イベントリスナーを使用している web サイトでは、変更を認識して、住所を検証し、送料と税金を再計算し、 [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) 選択した住所に適用されている料金および配送オプションの変更 (該当する場合) を反映するように更新することができます。 

### 送付オプション 

送付オプションは、パラメーターに追加することで顧客に表示でき [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) ます。  既定値は、いずれかの送付オプションの設定によって確立でき `selected = True` ます。 
 
ユーザーが shippingOptions を選択または更新すると、 [`onshippingoptionchange`](https://msdn.microsoft.com/library/mt790436) イベントが実行されます。  イベントリスナーを使用する web サイトでは、変更を認識し、 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 正しい配送金額でパラメーターを更新できます。   

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

## API リファレンス
[支払い要求 API](https://msdn.microsoft.com/library/mt790447)

## キャスト
[支払い要求 API](https://w3.org/TR/payment-request/)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "Microsoft Edge Legacy とは何ですか?"  
