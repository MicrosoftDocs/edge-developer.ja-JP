---
description: エミュレーションパネルを使用して、さまざまなブラウザープロファイル、画面サイズと解像度、GPS 位置座標をテストする
title: DevTools-エミュレーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/04/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、デバイスエミュレーション、応答性の高いデザイン、位置情報、解像度
ms.custom: seodec18
ms.openlocfilehash: 6eaa8d79cfd64473dcc52beff5659b39054e2a48
ms.sourcegitcommit: 912609aa49864e3363aaa3b245ff2aa4bec3fc3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104848"
---
# エミュレーション  

> [!NOTE]
> 新しい Microsoft Edge は Chromium を使って構築され、バージョン75から始まります。  詳細については、 [新しい Microsoft edge をダウンロード][MicrosoftNewEdge]して、新しい [Microsoft edge (Chromium) 開発者ツール][DevtoolsGuideChromium]をお試しください。  
> 
> 新しい DevTools でさまざまなデバイス、ブラウザー、画面サイズ、および解像度をエミュレートするには、「 [Microsoft Edge \ (Chromium) DevTools でモバイルデバイスをエミュレートする」][DevtoolsGuideChromiumDeviceMode]に移動します。  

**エミュレーション**パネルでは、次のアクティビティを行うことができます。    

*   さまざまな[デバイスプロファイル](#device)、[ブラウザー](#browser-profile)、および[画面サイズと解像度](#display)をシミュレートする  
*   さまざまな[位置情報の設定と座標の](#geolocation)テスト  

:::image type="complex" source="./media/emulation.png" alt-text="Microsoft Edge DevTools エミュレーションパネル" lightbox="./media/emulation.png":::
   Microsoft Edge DevTools **エミュレーション** パネル  
:::image-end:::  

1.  [ **エミュレーションの設定を保持** ] ボタンを使うと、開発者ツールを終了してもう一度開いた場合でも、既定のデスクトップエミュレーション設定で行ったすべての変更が保存されます。  

1.  [ **エミュレーション設定のリセット** ] ボタンをクリックすると、エミュレーションの設定が既定のデスクトップブラウザープロファイルと Microsoft Edge ユーザーエージェント文字列にリセットされ、GPS がオフになります。  

1.  これらのオプションのいずれかを既定値から変更した場合、[ **エミュレーション** ] タブには、ブラウザーの動作の一部がエミュレートされていることを示す情報アラートが表示されます。  

## デバイス  

他のエミュレーションオプションを自動的に構成する、または独自の **カスタム** 構成を指定する、Windows デバイスプロファイルの事前設定リストから選びます。  **既定**の状態に戻すには、すべてのエミュレーションツールをリセットします。  

## モード  

### ブラウザプロファイル  

Windows Phone デバイスで実行されているページをシミュレートする簡単な方法は、 **ブラウザーのプロファイル** 設定を **windows phone**に変更することです。  

#### ユーザーエージェント文字列  

Microsoft Edge でのみ発生するエラーをデバッグするには、最初の手順として、ユーザーエージェント文字列を他のブラウザーに近いものにすることをお勧めします。  

スクリプトは、ユーザーエージェント文字列を使って、使用されているブラウザーを検出します。  スクリプトは、フロントエンド、バックエンド、フロントエンド、バックエンドのいずれかになります。  コードではブラウザーの検出を使用していませんが、コードはサードパーティの JavaScript ライブラリまたはサーバー側スクリプトから継承している可能性があります。  

ブラウザーの検出に関する問題は、ブラウザーの機能について仮定を使って、web ページの機能をスケールバック (または変更) できるという点です。 代わりに、機能検出を使用してブラウザーの機能を検出することを検討してください。  以下のいずれかの状況が原因で、予期しない動作が発生することがあります。  

*   Windows Internet Explorer 8 のコードは、Microsoft Edge では動作が異なる場合があります。  
*   開発者によって想定されているため、ブラウザーでサポートする必要がある機能は無効です。  

ユーザーエージェント文字列を変更すると問題が解消される場合は、ブラウザーの検出が原因である可能性があります。  

## ディスプレイ  

さまざまな画面サイズと解像度でサイトをプレビューするには、[エミュレーション] を表示します。  

*   従来のデスクトップモニター  
*   モバイルの小型画面  
*   より新しい高解像度ディスプレイ  

エミュレーションは、エミュレートされる画面の物理サイズと一致するように調整されます。  エミュレートされたピクセルは、圧縮または展開されている可能性があります。 ピクセルで正確な HTML 要素の配置をテストする必要がある場合は、エミュレーションは推奨されません。  ただし、エミュレーションは、応答性の高いデザインをテストし、要素の配置の大きな問題を特定するのに適しています。  

### Orientation  

[ **横** ] または [ **縦** ] モードから選択します。  

### 解決方法  

一般的なデバイスの解像度の事前設定リストから選ぶか、独自の **カスタム** 構成を指定します。 最大80インチおよび 3820 x 2160 の解像度がサポートされています。  

## 位置情報  

Web サイトが位置情報に基づくサービスを提供するために位置情報 [API][MdnGeolocationUsing] を使用している場合は、デスクトップの便利なアクティビティを次に示します。  

*   さまざまな GPS 座標を簡単にテストする  
*   さまざまなセンサーの状態を簡単にテストする  

設定は、位置情報をサポートするデバイス上の実際の GPS 座標とセンサーの状態を上書きします。  

デバイスの場所を使用する前に、web サイトでユーザーに要求し、アクセス許可を与えられている必要があります。  Microsoft Edge の [ **設定** ] パネルで、サイトの動作を確認し、場所の権限は必要ありません。  

**...** > **設定**  > **詳細設定**  >  を表示する**Web サイトの権限**  > **管理**  

:::image type="complex" source="./media/settings_manage_permissions.png" alt-text="Microsoft Edge DevTools エミュレーションパネル" lightbox="./media/settings_manage_permissions.png":::
   Microsoft Edge の [ **設定** ] パネルから web サイトの権限を管理する  
:::image-end:::  

## ショートカット

| 操作  | ショートカット  |  
|:--- |:--- |  
| エミュレーション設定のリセット | `Ctrl`+`Shift`+`L` |  

<!-- links -->  


[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsGuideChromiumDeviceMode]: /microsoft-edge/devtools-guide-chromium/device-mode "Microsoft Edge DevTools でモバイルデバイスをエミュレートする |Microsoft ドキュメント"  

[MicrosoftNewEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MdnGeolocationUsing]: https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation "位置情報 API |MDN"  