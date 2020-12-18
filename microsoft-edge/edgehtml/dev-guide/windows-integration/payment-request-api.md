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
# 支払い要求 API (EdgeHTML)  

> [!NOTE]
> この記事では、従来のバージョンの Microsoft Edge でサポート [されているワークフローについて説明します][MicrosoftSupport44533505]。  Microsoft Edge \(Chromium\) は、Chromium プロジェクトに基づく異なる実装による支払い要求 API をサポートしています。  

電子商取引の売り上げは急速に拡大し続けています。  [eMarketer](https://www.emarketer.com)によると、2018 年のデジタル販売は、2013 年に測定されたレベルから 23% 増加すると予測されています。  消費者や企業は電子商取引の利便性を楽しんでいますが、課題は残ります。  現在、各電子商取引 Web サイトの所有者は、高品質の支払いチェックアウト フローと検証ルールを開発するために時間を費やす必要があります。  消費者は、さまざまな支払いチェックアウト フローに移動し、購入したサイトごとに同じ支払いおよび配送情報を再入力する必要があります。  これは、消費者にとって時間がかかり、不満が生じ、ショッピング カートの破棄率が高く、業者の売り上げが減少する可能性があります。  販売業者の [推定](http://baymard.com/lists/cart-abandonment-rate) 値は、ショッピング カートの 60% ~ 70% が破棄されます。  

支払 [い要求 API は](https://w3.org/TR/payment-request) 、支払いチェックアウト プロセスを標準化します。  この API では、Web 開発者のカスタマイズが少なく、より速く、一貫性が高く、消費者にとってわかりにくいエクスペリエンスを提供します。  消費者は Microsoft アカウントから支払い方法と配送先住所を選び、購入を完了するために必要なデータを少なくする必要があります。これは、支払いを完了するために必要な時間とデータ入力を減らします。  

支払い要求 [API](https://w3.org/TR/payment-request) はオープンなクロスブラウザー標準で、ブラウザーが業者、消費者、および消費者がクラウドに保存した支払い方法 \(クレジット カード\など) の仲介者として機能します。  
  
まとめると、支払い要求 [API](https://w3.org/TR/payment-request)を使用する場合、顧客は通常通り販売業者の Web サイトで購入します。  支払いの準備ができたら、業者の Web サイトは支払い要求******API**を呼び出して支払い要求を作成し、関連する支払い情報 \(サポートされている支払い方法、購入金額、通貨など) をブラウザーに渡します。  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="支払い要求の構造" lightbox="../media/payment_request_construct.png":::
   支払い要求の構造  
:::image-end:::  

ブラウザーはユーザーを認証し、ユーザーはファイルでサポートされている支払い方法を選択し、支払いの詳細を処理できます。  その後、ブラウザーは支払い情報の詳細を業者の Web サイトに送り返し、業者が支払いを完了できます。  支払い情報を受け取るだけでなく、業者は支払い要求の一部として配送情報を受け **取る選択もできます**。  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="支払い応答の構造" lightbox="../media/payment_response_construct.png":::
   支払い応答の構造  
:::image-end:::  

支払い要求 API の動作を確認し、その使い方の概要を確認するには、このビデオをご覧ください。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> 支払い要求 API は、Microsoft Edge ビルド 14992 以降でサポートされています。  

## 支払い要求を作成する  

Web ページは **、通常、** ユーザーが [購入] ボタンをクリックして支払いプロセスを開始するときに支払い要求を作成します。  支払**い要求コンストラクターには**[](/previous-versions/mt790440(v=vs.85))、methodData、詳細、およびオプションが含まれます。  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

[methodData パラメーターには](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)、Web サイトで受け入れられる支払い方法とネットワークの一覧と、関連する支払い方法固有のデータが含まれます。  Microsoft Edge では、この一覧は、買い手が Microsoft アカウントに保存したサポートされている支払い方法と一致し、支払いユーザー エクスペリエンスの "支払い方法" リストになります。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="Microsoft Wallet ユーザー エクスペリエンスの支払い一覧" lightbox="../media/pay_with.png":::
         Microsoft **Wallet ユーザー** エクスペリエンスの支払い一覧  
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

details [パラメーター](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) には、業者が取引について顧客に伝えたい情報が含まれている。  これには、合計、税金、出荷金額、支払額に影響を与えるその他のサマリー レベルのアイテムなどの注文の要約アイテムが含まれます。  これらは、注文行アイテムを意図した機能ではありません。  
  
詳細 [パラメーター](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) は、必要に応じて顧客が利用できる配送オプションを定義するためにも使用されます。  詳しくは、下記の「お **支払い要求** と配送先へのお支払い」セクションをご覧ください。  

各 [詳細行](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) には、通貨と金額のラベルが含まれます。  

> [!NOTE]
> 支払 **い要求では** 、これらの金額の合計または合計は計算されない。  行アイテムが正しく合計されるようにするには、業者の Web サイトの責任があります。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="小計、出荷、税金、合計の詳細" lightbox="../media/show_details.png":::
         小計、出荷、税金、合計の詳細  
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

[PaymentRequest は](/previous-versions/mt790440(v=vs.85)) 払い戻しをサポートしていないので、金額は常に正である必要があります。個々のリスト アイテムは、割引などの負の値になる場合があります。  

ブラウザーは、ラベルの定義時にラベルをレンダリングし、顧客のロケールに基づいて正しい通貨書式を自動的にレンダリングします。  ラベルは、コンテンツと同じ言語でレンダリングする必要があります。  

[options パラメーター](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)は、Web ページが支払い要求から返すデータを**定義します**。  また、配送、メール アドレス、電話番号、またはすべてのデータが必要な場合など、収集する必要があるデータも定義します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text="[電子メール アドレス] ドロップダウン" lightbox="../media/email_snippet.png":::
         [電子メール アドレス] ドロップダウン  
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

## 支払い要求の表示  

[show()](/previous-versions/mt790448(v=vs.85))メソッドは、ユーザーが支払い要求ユーザー インターフェイスを操作するために Web ページ**によって**呼び出されます。  [show()](/previous-versions/mt790448(v=vs.85))メソッドは、ユーザーが支払い要求を承認すると解決される Promise を返します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="詳細の確認と支払い" lightbox="../media/pay_screen_default.png":::
         詳細の確認と支払い  
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

## 支払い要求を中止する  
 
web [ページから show()](/previous-versions/mt790437(v=vs.85)) メソッドが呼び出された後は、Promise が解決されるまでいつでも [abort()](/previous-versions/mt790448(v=vs.85)) メソッドを呼び出します。  [abort() メソッドを使用](/previous-versions/mt790437(v=vs.85))すると、ブラウザーは支払**** い要求を中止し、支払い要求のユーザー インターフェイス**を**閉じます。  たとえば、ユーザーが必要な時間内にトランザクションを完了しなかった場合、Web ページで中止を選択できます。  

```javascript
payment.abort();
```  

## 支払い応答  
顧客が支払い要求を **承認すると**、支払い **応答** が Web サイトに返されます。  支払 **い応答には、** 次の情報が含まれます。  

 プロパティ      | 説明 | 必須かどうか | 追加情報
|---------------|-----------------|-------|-----------------|
[methodName](/previous-versions/mt790656(v=vs.85)) | ユーザーが選択した支払い方法の ID | Y | |   
[details](/previous-versions/mt790655(v=vs.85)) | 選択した支払い方法または支払いトークンを使用して、業者がトランザクションを処理するために必要なすべてのデータを含む JSON オブジェクト | Y | [基本カード](https://w3c.github.io/payment-method-basic-card) 辞書: cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress; |   
[shippingAddress](/previous-versions/mt790445(v=vs.85)) | ユーザーが選択した配送先住所  |  省略可能。  [requestShipping が次の場合は必須](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True`  | アドレスディクショナリ: 国addressLine;region;city;dependentLocality;postalCode;sortingCode;languageCode;組織recipient;phone |  
[shippingOption](/previous-versions/mt790446(v=vs.85)) | 選択した配送オプションの ID | 省略可能。  [requestShipping が次の場合は必須](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True`  | |   
[payerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | ユーザーが指定した名前  | 省略可能。  [requestPayerName が次の場合は必須](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True` | |  
[payerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | ユーザーが選択した電子メール アドレス | 省略可能。  [requestPayerEmail が](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True`  | |  
[PayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | ユーザーが選択した電話番号 | 省略可能。  [requestPayerPhone が次の場合は必須](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True` | |  

支払 [い](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) 応答の詳細 JSON オブジェクト **には、支払** いを処理するために業者が必要とする支払いデータが含まれる。  最も単純な形式では、応答はクリア [テキストの支払](https://w3c.github.io/payment-method-basic-card) いカードの詳細を含む基本カードのペイロードになります。  販売業者が支払いサポートを提供するために追加のゲートウェイ/プロセッサ パートナーとの取り決めを行っている場合、業者はプロセッサが処理できるペイロードを必要とする場合があります。  これらは、プロセッサ/ゲートウェイ トークンまたは暗号化された支払い方法の形を取る可能性があります。  これらの支払い方法は、このドキュメントの対象外であり、処理者に固有のドキュメントで説明します。  さらに、基本カードの応答[](https://w3c.github.io/payment-method-basic-card)を受け取る場合、暗号化キーのオンボードまたは要求承認 \(oAuth\) が必要になる可能性がある他のプロセッサ/ゲートウェイ固有の支払い方法とは異なり、開発者は Microsoft への追加のオンボーディングを必要としません。  

支払い応答を **受信すると**、Web サイトは支払い情報を支払い処理者に送信します。  支払いが処理されている間、ブラウザーにスピン ボックス ページが表示されます。  

:::image type="complex" source="../media/loading_screen.png" alt-text="支払いの処理時に表示されるページ" lightbox="../media/loading_screen.png":::
   支払いの処理時に表示されるページ  
:::image-end:::  

支払いが完了すると、Web ページは [complete()](/previous-versions/mt790642(v=vs.85)) メソッドを呼び出し、成功または失敗の値 **を** 渡 **します**。  [complete()](/previous-versions/mt790642(v=vs.85))メソッドは、購入が完了し、成功または失敗の値に応じて適切な終了 UI 画面が表示される必要があるというブラウザー**に通知****します**。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="購入が成功すると表示される UI" lightbox="../media/response_payment-request_complete.png":::
         購入が成功すると表示される UI  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="購入が失敗した場合に表示される UI" lightbox="../media/response_payment-request_failure.png":::
         購入が失敗した場合に表示される UI  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 出荷時の支払い要求  

### 配送先住所  

物理的な商品の配送が必要な販売の場合は、配送先住所が必要です。  配送先住所を含めるには、要求 `requestShipping = True` の [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) パラメーターに設定します。  

ユーザーが配送先住所を選択または更新すると [、onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) イベントが実行されます。  Web サイトは、イベント リスナーを使用して変更を認識し、住所を検証し、配送料と税金を再計算し [、shippingOptions](/previous-versions/mt790440(v=vs.85)) を更新して、選択した \(該当する場合\ ) アドレスで使用可能な変更されたコストと配送オプションを反映することができます。  

### 配送オプション  

[shippingOptions](/previous-versions/mt790440(v=vs.85))を details パラメーターに追加することで、配送オプションを顧客に[提示](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)できます。  出荷オプションの 1 つを設定 `selected = True` することで、既定値を設定できます。  
 
ユーザーが shippingOptions を選択または更新すると [、onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) イベントが実行されます。  イベント リスナーを使用して Web サイトは変更を認識し、 [詳細](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) パラメーターを正しい出荷金額で更新できます。  

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

## API リファレンス  

[支払い要求 API](/previous-versions/mt790447(v=vs.85))  

## 仕様
[支払い要求 API](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "Microsoft Edge レガシとは"  
