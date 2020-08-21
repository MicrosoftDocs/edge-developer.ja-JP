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
# 支払要求 API (EdgeHTML)  

> [!NOTE]
> この記事では、従ギャラリー バージョンの [Microsoft Edge でサポートされているワークフローについて説明します][MicrosoftSupport44533505]。  Microsoft Edge \(Chromium\) では、Chromium プロジェクトに基づくさまざまな実装での支払い要求 API をサポートしています。  

電子営業の営業担続は、高いペースで引き続き成まります。  2018 デジタル売上高によって [は](https://www.emarketer.com)、2018 年のデジタル売上高によっては 2013 年のメジャーの 23% が上がります。  コンシューマーやビジネスで、電子営業の手数料を楽しみながら、チャレンジは残ります。  この時点で、高品質な支払いチェックアウトのフローと入力規則を作成するには、各電子業者の Web サイトの所有者が時間を調査する必要があります。  コンシューマーは、別の支払いチェックアウト フローを移動し、シャッピングされているすべてのサイトで同じ支払いと配送情報を再入力する必要があります。  この時間は、コンシューマーのための時間を大量に使用し、高いシャプチャアントの販売を減らし、販売代理販売数を減らすことができます。  シンプリング カー[estimate](http://baymard.com/lists/cart-abandonment-rate)トの 60% から 70% の見積もりが中型的です。  

支払 [要求 API は](https://w3.org/TR/payment-request) 、支払チェックアウト プロセスを標準化します。  この API では、Web 開発者のカスタマイズを少なくし、より高速かつ一致があり、より高速で一致を提供し、ユーザーの操作性が低下します。  コンシューマーはお支払い方法と配送先住所を Microsoft アカウントから選べる可能性があるため、支払いを完了するのに必要な時間とデータ入力を減らすために必要な時間とデータ入力を減らすために、購入を完了する必要があります。  

[支払要求 API は開](https://w3.org/TR/payment-request)いており、クロスブラウザー標準であり、ブラウザーで、コンシューマーがクラウドに保存されているメッセント、コンシューマー、支払方法 \(クレジット カード\など) 間の中間としてブラウザーを操作できます。  
  
まず、 [支払要求 API を](https://w3.org/TR/payment-request)使用する場合、顧客は、メーカーの Web サイトで通常のシェープをシャットします。  支払い準備ができたら、マルチェッカー Web サイトでは **支払** い要求 API を呼び出して、 **支払** い要求 API を呼び出して、関連する支払い方法 \(サポートされる支払い方法、購入金額、通貨など) をブラウザーに合わせます。  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="お支払い要求の構造" lightbox="../media/payment_request_construct.png":::
   お支払い要求の構造  
:::image-end:::  

ブラウザーがユーザーを認証し、ユーザーがファイルに対してサポートされている支払い方法を選択し、支払いの詳細を処理できます。  ブラウザーから支払い情報がお支払いを完了できるように、お支払い情報をメーカーの Web サイトに送信します。  支払い情報を受信する他に、お支払い要求の一部として発送情報を **受**け取るようにすることもできます。  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="お支払いの返答の構造" lightbox="../media/payment_response_construct.png":::
   お支払いの返答の構造  
:::image-end:::  

実算依頼 API を実実に確認する方法とその使い方法の概要を確認するには、このビデオをご覧ください。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> 支払いリクエスト API は、Microsoft Edge ビルド 14992 以降でサポートされています。  

## 支払い要求の作成  

Web ページでは通常 **、ユーザー** が [購入] ボタンをクリックして支払いプロセスを開始したときに、通常は支払い要求が作成されます。  支払**要求のコン**[トラストラクターには](/previous-versions/mt790440(v=vs.85))、methodData、details、オプションが含まれます。  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

[メソッドデータ](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)パラメーターには、Web サイトで受け付けられた支払い方法とネットワークの一覧と、関連するすべての支払い方法に関するデータが含められます。  Microsoft Edge では、この一覧はサポートされている支払い方法と一致しており、お子様が Microsoft アカウントに保存され、支払いのエクスペリエンスの "お支払い" リストに結果が出てきます。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="Microsoft Wallet のユーザー エクスペリエンスのリストに表示されたお支払い" lightbox="../media/pay_with.png":::
         Microsoft **Wallet の** ユーザー エクスペリエンスのリストに表示されたお支払い  
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

詳細 [パラメー](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) ターには、トランザクションに関する顧客に送るようにマーカーが得たい情報が含まれます。  これには、注文の合計、税額、配送額などの項目が支払金額に影響するその他のサマリー 項目が含まれます。  これらは順序の項目を注文するものではありません。  
  
詳細 [パラメー](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) ターは、必要な場合に顧客が利用できる配送オプションを定義するためにも使用されます。  詳細については、以下の配送先**Payment Request**のセクション付きの支払い要求に含まれます。  

各 [詳細](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 行には、通貨のラベルと金額が含まれます。  

> [!NOTE]
> 支払 **要求では** 、これらの金額の合計や合計は計算しません。  これは、明日の Web サイトのサイトで、線のアイテムを合計し、正しくアイテムを合計させる必要があります。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="小計、配送価額、税額、および集計の詳細" lightbox="../media/show_details.png":::
         小計、配送価額、税額、および集計の詳細  
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

[PaymentRequest](/previous-versions/mt790440(v=vs.85)) では返金はサポートされないため、金額は常に正の数にする必要があります。個々のリスト項目は割引率など、負の数にすることができます。  

ブラウザーはラベルを定義するたびにレンダリングし、正しい通貨書式を顧客のロケールに基づいて自動的に表示します。  ラベルはコンテンツと同じ言語でレンダリングされる必要があります。  

オプション [パラ](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) メーターは、支払要求から返される Web ページ **を定義します**。  出荷、メール アドレス、電話番号、すべての情報が必要な場合など、収集する必要があるデータも定義されます。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text="メール アドレス ドロップダウン" lightbox="../media/email_snippet.png":::
         メール アドレス ドロップダウン  
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

シ [ョー()](/previous-versions/mt790448(v=vs.85)) メソッドは、ユーザーが **支払** 要求のユーザー インターフェイスと対話することを許可する Web ページによって呼び出されます。  [ショー()](/previous-versions/mt790448(v=vs.85))メソッドは、ユーザーが支払要求を承認したときに解決されるプロミスを返します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="確認と支払いの詳細" lightbox="../media/pay_screen_default.png":::
         確認と支払いの詳細  
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

## お支払い要求の予定に中止  
 
[Abort()](/previous-versions/mt790437(v=vs.85))メソッドは[、Promise](/previous-versions/mt790448(v=vs.85))が解決されるまで、いつでも Web ページで呼び出すことができます。  [abort() メ](/previous-versions/mt790437(v=vs.85))ソッドにより、ブラウザーで支払要求が**Payment Request**中止され、支払要求のユーザー**インター**フェイスが閉じられます。  たとえば、ユーザーが必要な時間にトランザクションを完了しなかった場合、Web ページが中止することがあります。  

```javascript
payment.abort();
```  

## 支払い回答  
顧客が支払要求を承認すると **、****支払**い回答が Web サイトに返されます。  支払 **いの応答には** 、次のものが含まれます。  

 プロパティ      | 説明 | 必須かどうか | 追加情報
|---------------|-----------------|-------|-----------------|
[methodName](/previous-versions/mt790656(v=vs.85)) | ユーザーが選択したお支払い方法の ID | Y | |   
[details](/previous-versions/mt790655(v=vs.85)) | マルチャントが含まれるすべてのデータを含む JSON オブジェクトでは、選択した支払い方法または支払トークンを使用してトランザクションを処理する必要があります。 | Y | [基本カード](https://w3c.github.io/payment-method-basic-card) 辞書: cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress; |   
[shippingAddress](/previous-versions/mt790445(v=vs.85)) | ユーザーが選択した配送先住所  |  省略可能。  要求の配送[時に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True`  | 住所辞書: 国;addressLine;region;city;dependentLocality;postalCode;sortingCode;languageCode;組織;recipient;電話 |  
[出荷先Option](/previous-versions/mt790446(v=vs.85)) | 選択した配送オプションの ID | 省略可能。  要求の配送[時に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True`  | |   
[payerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | ユーザーによって入力された名前  | 省略可能。  [requestPayerName の場合に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True` | |  
[payerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | ユーザーが選択したメール アドレス | 省略可能。  要求[PayerEmail の場合に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True`  | |  
[PayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | ユーザーが選択した電話番号 | 省略可能。  要求[PayerPhone 要求の場合に必要](/previous-versions/mt790440(v=vs.85)#PaymentOptions) `True` | |  

**支払**[い](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params)応答の詳細な JSON オブジェクトには、お支払いを処理するのに必要な支払データが含まれている。  その最も簡単な形式で、応答はクリアテキスト支払いカードの詳細[Basic Card](https://w3c.github.io/payment-method-basic-card)を含む基本カード ペイロードです。  支払いのサポートを提供するために、マルチエイトウェイ/プロセッサ パートナーと行き込みが行われている場合、階層にはプロセッサが処理できるペイロードが必要になることがあります。  これらは、プロセッサ/ゲートウェイ トークンの形を使用したり、暗号化された支払い方法を利用したりすることができます。  これらの支払方法はこのドキュメントの範囲外であり、プロセッサに固有のドキュメントで説明します。  さらに、基本カード応答[Basic Card](https://w3c.github.io/payment-method-basic-card)を受け取るために、暗号化キーオンによるオンボーディングや承認を要求するなどの他のプロセッサ/ゲートウェイ固有の支払い方法とは異なり、デベロッパーが Microsoft への追加のオンボーディングを行う必要はありません。  

支払いの応答を送る **と、お**支払い情報が支払いプロセッサに送信されます。  支払い処理中は、ブラウザーにスピナー ページが表示されます。  

:::image type="complex" source="../media/loading_screen.png" alt-text="支払い処理中に表示されるページ" lightbox="../media/loading_screen.png":::
   支払い処理中に表示されるページ  
:::image-end:::  

支払いが完了すると、Web ページは完全[な ()](/previous-versions/mt790642(v=vs.85))メソッドを呼び出し、成**success**功するか失**敗をつなげます**。  完全[() メ](/previous-versions/mt790642(v=vs.85))ソッドは、購入が完了したブラウザーを通知し、成功する値または失敗の値に応じて適切な終了 UI**画面が表示****されるようにします**。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="購入が成功したときに表示される UI" lightbox="../media/response_payment-request_complete.png":::
         購入が成功したときに表示される UI  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="購入に失敗したときに表示される UI" lightbox="../media/response_payment-request_failure.png":::
         購入に失敗したときに表示される UI  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 配送付付での支払要求  

### 配送先住所  

出荷の商標が必要な販売の場合、発送先住所が必要です。  配送先住所を含めるには、要求 `requestShipping = True` のオプション パラ [メータ](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) ーを設定します。  

ユーザーが配送先住所を選択または更新すると [、onshipingaddresschange](/previous-versions/mt790442(v=vs.85)) イベントが実行されます。  イベント リストを使用する Web サイトでは、変更を認め、その後住所を検証し、配送コストと税金を再計算し、 [配送オプション](/previous-versions/mt790440(v=vs.85)) を更新して、選択したアドレスで利用可能な変更されたコストと配送オプションを更新できます (適用する場合\(適用する場合\)  

### 配送オプション  

出荷オプションは、詳細パラメーターに [出](/previous-versions/mt790440(v=vs.85)) 荷オプションを追加することで、顧客 [に表示](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) できます。  既定では、いずれかの配送オプションを `selected = True` 設定して設定できます。  
 
出荷オプションを選択または更新すると、 [オン配送オプション変更](/previous-versions/mt790436(v=vs.85)) イベントが実行されます。  イベント リストを使用する Web サイトは変更を確認し、詳細パラメータ[details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)ーを正しい配送金額で更新できます。  

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

## Specification
[支払い要求 API](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "Microsoft Edge レガシとは"  
