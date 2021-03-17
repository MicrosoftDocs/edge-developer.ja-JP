---
description: Microsoft Edge の仮想デバイスを使用して、モバイル ファースト Web サイトを構築します。
title: Microsoft Edge DevTools でモバイル デバイスをエミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, エミュレーション, デバイス, シミュレーション, モバイル
ms.openlocfilehash: bb081ddd5f773e5e9ae6a1b83b5fcb13408df6cb
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439452"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="emulate-mobile-devices-in-microsoft-edge-devtools"></a>Microsoft Edge DevTools でモバイル デバイスをエミュレートする  

デバイス **エミュレーションを使用** して、モバイル デバイスでのページの外観と応答を概算します。  Microsoft Edge DevTools には、モバイル デバイスのエミュレートに役立つ機能のコレクションが提供されています。  コレクションには、次の機能が含まれています。  

*   [モバイル ビューポートをシミュレートする](#simulate-a-mobile-viewport)  
*   [ネットワークの調整](#throttle-the-network-only)  
*   [CPU の調整](#throttle-the-cpu-only)  
*   [位置情報をシミュレートする](#override-geolocation)  
*   [方向を設定する](#set-orientation)  
*   [ユーザー エージェントの文字列を設定する](#set-user-agent-string)  

## <a name="limitations"></a>制限事項  

**デバイス エミュレーション** は、 [モバイル デバイス][WikiApproximation] 上のページの外観の 1 次近似です。  **デバイス エミュレーション** は、実際にはモバイル デバイス上でコードを実行しない。  代わりに、ラップトップまたはデスクトップからモバイル ユーザー エクスペリエンスをシミュレートします。  

モバイル デバイスの一部の側面は、DevTools ではエミュレートされません。  たとえば、モバイル CPU のアーキテクチャは、ラップトップまたはデスクトップ CPU のアーキテクチャとは異なります。  疑わしい場合は、モバイル デバイスでページを実際に実行する方法が最善の策です。  [リモート デバッグ][DevToolsRemoteDebugging] を使用して、ページがモバイル デバイス上で実際に実行されている間にコンピューターからページのコードを操作します。  コードを操作している間は、表示、変更、デバッグ、プロファイル、または 4 つすべて表示できます。  コンピューターはノートブックまたはデスクトップ コンピューターである可能性があります。  

## <a name="simulate-a-mobile-viewport"></a>モバイル ビューポートをシミュレートする  

[**デバイス エミュレーションの**切り替え\( Toggle Device Toolbar \) を選択するか ![ ](../media/toggle-device-toolbar-dark-icon.msft.png) **、[DevTools** `...` \( **** \) > デバイス エミュレーションのカスタマイズと制御] を選択して、モバイル ビューポートをシミュレートできる UI を開きます。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="[デバイス] ツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
    [デバイス] ツールバー  
:::image-end:::  

既定では、デバイス ツールバーはレスポンシブ ビューポート モードで開きます。  

### <a name="responsive-viewport-mode"></a>レスポンシブ ビューポート モード  

複数の画面サイズでページの外観をすばやくテストするには、ハンドルをドラッグして必要なサイズに合わせてビューポートのサイズを変更します。  幅と高さのボックスに特定の値を入力することもできます。  次の図では、幅がに設定され `626` 、高さがに設定されています `516` 。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="レスポンシブ ビューポート モードでビューポートの寸法を変更するハンドル" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
    レスポンシブ ビューポート モードでビューポートの寸法を変更するハンドル  
:::image-end:::  

#### <a name="show-media-queries"></a>メディア クエリの表示  

ページでメディア クエリを定義している場合は、ビューポートの上にメディア クエリブレークポイントを表示して、それらのメディア クエリが有効なビューポートディメンションにジャンプします。  [その**他のオプション**  >  **] [メディア クエリの表示] を選択します**。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="メディア クエリの表示" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **メディア クエリの表示**  
:::image-end:::  

ブレークポイントを選択して、メディア クエリがトリガーされるビューポートの幅を変更します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="ブレークポイントを選択してビューポートの幅を変更する" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   ブレークポイントを選択してビューポートの幅を変更する  
:::image-end:::  

#### <a name="set-the-device-type"></a>デバイスの種類を設定する  

モバイル デバイスまたは **デスクトップ デバイスを** シミュレートするには、[デバイスの種類] リストを使用します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="[デバイスの種類] リスト" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   [**デバイスの種類] リスト**  
:::image-end:::  

次の表に、使用可能なデバイスの種類のオプションの違いを示します。  [レンダリング] メソッド列は、Microsoft Edge がページをモバイル ビューポートまたはデスクトップ ビューポートとしてレンダリングするかどうかを示します。  [カーソル] アイコン列は、ページにマウス ポインターを置くと表示されるカーソルの種類を表します。  [イベントがトリガーされた] 列は、ページを操作するときに、ページがトリガーするか `touch` `click` 、イベントをトリガーするかを示します。  

| オプション | レンダリング メソッド | カーソル アイコン | トリガーされるイベント |  
|:--- |:--- |:--- |:--- |  
| モバイル | モバイル | 円形 | タッチ |  
| Mobile \(no touch\) | モバイル | 通常 | て  |  
| Desktop | Desktop | 通常 | て  |  
| デスクトップ \(touch\) | Desktop | 円形 | タッチ |  

> [!NOTE]
> [デバイスの**種類] リストが**表示されない場合は、[その他の**オプション] [デバイスの**  >  **種類の追加] を選択します**。  

### <a name="mobile-device-viewport-mode"></a>モバイル デバイス ビューポート モード  

特定のモバイル デバイスの寸法をシミュレートするには、[デバイス] リストからデバイス **を選択** します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="[デバイス] リスト" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   [**デバイス] リスト**  
:::image-end:::  

#### <a name="rotate-the-viewport-to-landscape-orientation"></a>ビューポートを横向きに回転する  

横向きに Web ページをテストします。  

*   ビューポートを横向きに回転するには、[ **回転]\(** 回転 ![ ](../media/rotate-dark-icon.msft.png) \) を選択します。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横向きに表示されるページ" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
       横向きに表示されるページ  
    :::image-end:::  
    
> [!NOTE]
> デバイス **ツールバーが** 狭い場合は、[回転] **ボタンが** 表示されなくなります。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="[デバイス] ツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   [ **デバイス] ツールバー**  
:::image-end:::  

詳細については、[方向の設定] [に移動します](#set-orientation)。  

#### <a name="show-device-frame"></a>デバイス フレームの表示  

iPhone 6 などの特定のモバイル デバイスの寸法をシミュレートするときに、ビューポートの周囲に物理デバイス フレームを表示します。  

1.  [その **他のオプション] を開きます**。  
1.  [デバイス **フレームの表示] を選択します**。  

> [!NOTE]
> 特定のデバイスのデバイス フレームが表示されない場合は、DevTools にオプションのアートが含められているという意味です。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="デバイス フレームの表示" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         デバイス フレームの表示  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="iPhone 6 のデバイス フレーム" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         iPhone 6 のデバイス フレーム  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="add-a-custom-mobile-device"></a>カスタム モバイル デバイスの追加  

必要なモバイル デバイス オプションが既定のリストに含まれていない場合は、カスタム デバイスを追加できます。  カスタム デバイスを追加するには、次の手順を実行します。  

1.  [編集] **で [デバイス** ] > **を選択します**。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="[編集] を選択します。" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       [編集 **] を選択します。**  
    :::image-end:::  
    
1.  [カスタム **デバイスの追加] を選択します**。  
1.  [ **エミュレートされたデバイス] で**、カスタム デバイスのデバイス名、画面幅、画面の高さを入力します。  デバイス[のピクセル比、][MDNWindowDevicePixelRatio][ユーザー エージェント文字列、][MDNUserAgent][およびデバイスの種類](#set-the-device-type)フィールドはオプションです。  デバイスの種類フィールドの既定値は Mobile **です**。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="カスタム デバイスの作成" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       カスタム デバイスの作成  
    :::image-end:::  
    
### <a name="show-rulers"></a>ルーラーを表示する  

画面のサイズを測定する必要がある場合は、ルーラーを使用して画面サイズをピクセル単位で測定できます。  [**その他のオプション**  >  **] ルーラーを表示**して、ビューポートの上と左にルーラーを表示します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="ルーラーを表示するメニュー項目" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         ルーラーを表示するメニュー項目  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="ビューポートの上と左のルーラー" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         ビューポートの上と左のルーラー  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="zoom-the-viewport"></a>ビューポートをズームする  

複数のズーム レベルでページの外観をテストするには、ズーム リスト**** を使用して拡大または縮小します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="Zoom" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **Zoom**  
:::image-end:::  

## <a name="throttle-the-network-and-cpu"></a>ネットワークと CPU の調整  

多くの場合、モバイル デバイスにはネットワークと CPU の制約があります。  ページの読み込み速度と、さまざまなインターネット速度と CPU 速度での応答方法をテストしてください。  

ネットワークと CPU を調整します。  

1.  [ **スロットル リスト]** を選択し、プリセットを **[中** 層モバイル] または [ローエンド モバイル] **に変更します**。  
    *   **中層モバイルは、CPU** `fast 3G` をシミュレートして調整します。  通常の 4 倍遅くなります。  
    *   **ローエンド モバイルは、CPU** `slow 3G` をシミュレートして調整します。  通常の 6 倍遅くなります。  
    
すべての調整は、ラップトップまたはデスクトップの通常の機能に基づいて行います。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="デバイス ツールバーのスロットル リスト" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   デバイス **ツールバー** のスロットル リスト  
:::image-end:::  

> [!NOTE]
> スロットル リスト **が非表示の** 場合、デバイス **ツールバーが** 狭すぎます。  スロットル リストに **アクセスするには、** デバイス ツールバーの幅を **大きくします**。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="[デバイス] ツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   [ **デバイス] ツールバー**  
:::image-end:::  

### <a name="throttle-the-cpu-only"></a>CPU のみを調整する  

ネットワークではなく CPU のみを調整するには、次の手順を実行します。

1.  [パフォーマンス] **パネルを選択** し、[キャプチャ設定\( Capture **Settings** ![ ](../media/capture-settings-icon.msft.png) \] ) を選択します。
1.  **[CPU**  >  **4x スローダウン] または** **[6 倍のスローダウン] を選択します**。
    
    :::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="[パフォーマンス] パネルの CPU リスト" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
       [**パフォーマンス]** パネルの**CPU リスト**  
    :::image-end:::  
    
### <a name="throttle-the-network-only"></a>ネットワークの調整のみ  

ネットワークのみを調整するには、次の手順を実行します。

1.  [ネットワーク] **ツールを選択** します。
1.  [**オンライン**  >  **高速 3G] または [** 低速**3G] を選択します**。
    
    :::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="[ネットワーク] パネルの [スロットル] リスト" lightbox="../media/device-mode-network-throttle.msft.png":::
       [ **ネットワーク]** パネルの [スロットル] リスト  
    :::image-end:::  
    
    または `Control` + `Shift` + `P` 、[\(Windows, `Command` + `Shift` + `P` Linux\) または \(macOS\)**** `3G` ******** を選択してコマンド メニューを開き、入力し、[高速 3G 調整を有効にする] または [低速 3G 調整を有効にする] を選択します。  
    
    :::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="コマンド メニュー" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
       **コマンド メニュー**  
    :::image-end:::  
    
[パフォーマンス] パネルからネットワーク調整を **設定** することもできます。  

1.  [**キャプチャ設定**\( Capture Settings \) を選択し、[ネットワーク] リストを選択し、プリセットを ![ ](../media/capture-settings-icon.msft.png) **[Fast 3G]** または **[低速 3G] に変更します**。 ****  
    
    :::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="[パフォーマンス] パネルからネットワーク調整を設定する" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
       [パフォーマンス] パネルからネットワーク調整 **を設定** する  
    :::image-end:::  
    
## <a name="override-geolocation"></a>位置情報を上書きする  

:::row:::
   :::column span="":::
      ページがモバイル デバイスからの位置情報に依存して適切にレンダリングされる場合は、地理位置情報オーバーライド UI を使用してさまざまな位置情報を提供します。  

      1.  **[DevTools \(** \) のカスタマイズと制御 `...` ] を選択>**その他のツール**  >  **センサー を選択します**。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="地理位置情報用センサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         **地理位置情報** 用センサー  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  コマンド メニューを開きます。  
          *   `Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  
      1. を `Sensors` 入力し、[センサー **の表示] を選択します**。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="地理位置情報のセンサーを表示する" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **地理位置情報のセンサー** を表示する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

[ **センサー] パネル** で、[場所] ドロップダウン メニューを使用して、DevTools に含まれるプリセットの **場所のいずれかを** 選択できます。  カスタムの場所を入力するには、[その他] **を選択します。** をクリックし、カスタムの場所の座標を入力します。  位置情報が使用できない場合にエラー状態でページをテストするには、[場所を **使用できません] を選択します**。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="事前に設定された場所が選択されたセンサー パネル" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
    **事前に設定** された場所が選択されたセンサー パネル。  
:::image-end:::

## <a name="set-orientation"></a>方向を設定する  

:::row:::
   :::column span="":::
      ページがモバイル デバイスからのオリエンテーション情報に依存して適切にレンダリングされる場合は、向き UI を開きます。  

      1.  **[DevTools \(** \) のカスタマイズと制御 `...` ] を選択>**その他のツール**  >  **センサー を選択します**。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="方向のセンサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         **方向の** センサー  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  コマンド メニューを開きます。  
          *   `Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  
      1. を `Sensors` 入力し、[センサー **の表示] を選択します**。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="方向のセンサーを表示する" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **方向のセンサーを** 表示する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

[センサー **] パネル** で、[方向] ドロップダウン メニューから事前設定 **の向** きを選択できます。  独自の向きを入力するには **、[カスタム**の向き] を選択し、独自のアルファ値、[ベータ][MDNDeviceOrientaitonAlpha]値、ガンマ値[を入力][MDNDeviceOrientaitonGamma]します。 [][MDNDeviceOrientaitonBeta]  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="センサー パネルの方向オプション" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
    **センサー**パネルの**方向オプション**  
:::image-end:::  

## <a name="set-user-agent-string"></a>ユーザー エージェント文字列の設定  

:::row:::
   :::column span="":::
      ページがモバイル デバイスのユーザー エージェント文字列に依存して適切にレンダリングされる場合は****、[ネットワーク条件] パネルを使用して、異なるユーザー エージェント文字列を指定します。  
      
      1.  **[DevTools \(** \) をカスタマイズして制御 `...` する] を選択>**その他のツール**  >  **ネットワーク条件を選択します**。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png" alt-text="[その他のツール] メニューのネットワーク条件エントリ" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png":::
         **[その他のツール**] メニュー**のネットワーク条件エントリ**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  コマンド メニューを開きます。  
          *   `Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  
      1. を `Network conditions` 入力し、[ネットワーク条件 **の表示] を選択します**。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png" alt-text="ネットワーク条件の表示" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png":::
         **ネットワーク条件の表示**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

[ユーザー エージェント **] の横にある**[自動的に選択 **する] チェック ボックスを** オフにします。  次に **、[Custom...] を選択** して、定義済みのユーザー エージェント文字列の一覧から選択します。  独自のユーザー エージェント文字列を入力するには、[カスタム ユーザー エージェントの入力 **] に文字列を入力します**。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png" alt-text="macOS でユーザー エージェント文字列を Microsoft Edge に設定する" lightbox="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png":::
    macOS でユーザー エージェント文字列を Microsoft Edge に設定する  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
[DevToolsRemoteDebugging]: ../remote-debugging/index.md "Android デバイスのリモート デバッグの開始|Microsoft Docs"  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window.devicePixelRatio |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "User Agent |MDN"  
[MDNDeviceOrientaitonAlpha]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/alpha "DeviceOrientationEvent.alpha |MDN"  
[MDNDeviceOrientaitonBeta]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/beta "DeviceOrientationEvent.beta |MDN"  
[MDNDeviceOrientaitonGamma]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/gamma "DeviceOrientationEvent.gamma |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "近似の順序 - 1 次 - Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
