---
description: エミュレーション パネルを使用して、さまざまなブラウザー プロファイル、画面サイズと解像度、GPS 位置座標をテストする
title: DevTools - エミュレーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, デバイス エミュレーション, レスポンシブ デザイン, 位置情報, 解像度
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: af740472f22a8b322c03cb672a3da909ef195fac
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234587"
---
# エミュレーション  

> [!NOTE]
> 新しい Microsoft Edge は Chromium を使用して構築され、バージョン 75 から始まります。  詳細については、新 [しい Microsoft Edge をダウンロード][MicrosoftNewEdge]して、新しい [Microsoft Edge (Chromium) 開発者ツールを試してください][DevtoolsGuideChromium]。  
> 
> 新しい DevTools でさまざまなデバイス、ブラウザー、画面サイズ、解像度をエミュレートするには [、Microsoft Edge \(Chromium\) DevTools][DevtoolsGuideChromiumDeviceMode]でモバイル デバイスをエミュレートするに移動します。  

エミュレーション **パネルは** 、次のアクティビティに役立ちます。    

*   さまざまなデバイス [プロファイル、ブラウザー](#device) [、画面サイズ](#browser-profile)と解像度 [をシミュレートする](#display)  
*   さまざまな地理 [位置情報の設定と座標をテストする](#geolocation)  

:::image type="complex" source="./media/emulation.png" alt-text="Microsoft Edge DevTools エミュレーション パネル" lightbox="./media/emulation.png":::
   Microsoft Edge DevTools **エミュレーション** パネル  
:::image-end:::  

1.  [Persist **Emulation settings] ボタン** は、DevTools を閉じて再度開いた場合でも、既定のデスクトップ エミュレーション設定から行った変更を保存します。  

1.  エミュレーション **設定のリセット** ボタンは、エミュレーション設定を既定のデスクトップ ブラウザー プロファイルにリセットし、GPS をオフにした Microsoft Edge ユーザー エージェント文字列に戻します。  

1.  これらのオプションが既定から変更された場合、[ **エミュレーション** ] タブには情報アラートが表示され、ブラウザーの動作のいくつかの側面がエミュレートされています。  

## デバイス  

他のエミュレーション オプションを自動的に構成する Windows デバイス プロファイルの既定の一覧から選択するか、独自のカスタム構成 **を指定** します。  Default に戻 **り、** すべてのエミュレーション ツールをリセットします。  

## モード  

### ブラウザー プロファイル  

Windows Phone デバイスで実行されているページをシミュレートする簡単な方法は、 **ブラウザー** プロファイルの設定を Windows Phone に **変更することです**。  

#### ユーザー エージェント文字列  

別のブラウザーを模倣するようにユーザー エージェント文字列を変更すると、Microsoft Edge でのみ発生するエラーをデバッグする最初の手順として役立ちます。  

スクリプトは、ユーザー エージェント文字列を使用して、使用されているブラウザーを検出します。  スクリプトには、フロントエンド、バック エンド、またはフロントエンドとバック エンドがあります。  コードはブラウザー検出を使用しませんが、サード パーティの JavaScript ライブラリまたはサーバー側スクリプトからコードを継承する場合があります。  

ブラウザー検出の問題は、ブラウザー機能に関する前提を使用して、Web ページの \(または変更\) 機能をスケールバックする可能性があるという問題です。 代わりに、機能検出を使用してブラウザーの機能を検出する方法を検討する必要があります。  次のいずれかの状況が原因で、予期しない動作が発生する可能性があります。  

*   Windows Internet Explorer 8を対象としたコードは、Microsoft Edge で異なる方法で実行される場合があります。  
*   開発者による想定のため、ブラウザーでサポートする機能が無効になります。  

ユーザー エージェント文字列を変更すると問題が解決する場合、ブラウザーの検出が原因である可能性があります。  

## ディスプレイ  

エミュレーションを表示して、さまざまな画面サイズと解像度でサイトをプレビューします。  

*   従来のデスクトップ モニター  
*   小さいモバイル画面  
*   新しい高解像度ディスプレイ  

エミュレーションは、エミュレートされる画面の物理的な次元と一致しようとして調整されます。  エミュレートされたピクセルは、圧縮または拡張された形式で表示される場合があります。 HTML 要素のピクセルを完全に配置する必要がある場合は、エミュレーションをお勧めしません。  ただし、エミュレーションは、レスポンシブ デザインをテストし、より大きな要素配置の問題を特定するのに便利です。  

### Orientation  

横モードまたは**縦モード****から選択**します。  

### 解決方法  

一般的なデバイス解像度の既定の一覧から選択するか、独自のカスタム構成 **を指定** します。 最大 80 インチと 3820 x 2160 の解像度がサポートされています。  

## 位置情報  

Web サイトで位置情報 API を [使用して位置情報][MdnGeolocationUsing] ベースのサービスを提供する場合、デスクトップの利便性から次のアクティビティを利用できます。  

*   さまざまな GPS 座標を簡単にテストする  
*   さまざまなセンサーの状態を簡単にテストする  

この設定は、位置情報をサポートするデバイス上の実際の GPS 座標とセンサーの状態を上書きします。  

Web サイトは、デバイスの場所を使用する前に、ユーザーにアクセス許可を要求して付与する必要があります。  Microsoft Edge の [設定] パネルで、場所のアクセス許可の使用と設定がない場合のサイトの動作を **テスト** します。  

**...** > **設定**  > **詳細設定を表示する**  > **Web サイトのアクセス許可**  > **管理**  

:::image type="complex" source="./media/settings_manage_permissions.png" alt-text="Microsoft Edge の [設定] パネルから Web サイトのアクセス許可を管理する" lightbox="./media/settings_manage_permissions.png":::
   Microsoft Edge の [設定] パネルから Web サイトのアクセス許可 **を管理** する  
:::image-end:::  

## ショートカット

| 操作  | ショートカット  |  
|:--- |:--- |  
| エミュレーション設定のリセット | `Ctrl`+`Shift`+`L` |  

<!-- links -->  


[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsGuideChromiumDeviceMode]: /microsoft-edge/devtools-guide-chromium/device-mode "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  

[MicrosoftNewEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MdnGeolocationUsing]: https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation "位置情報 API |MDN"  
