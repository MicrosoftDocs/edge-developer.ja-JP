---
description: Microsoft Edge で仮想デバイスを使用して、モバイルの最初の web サイトを構築します。
title: Microsoft Edge DevTools でモバイルデバイスをエミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/04/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、エミュレーション、デバイス、シミュレーション、モバイル
ms.openlocfilehash: c70b81eabb145461eac7d1b9a8f438d6a18fbc89
ms.sourcegitcommit: cc96ada9679b23feb841e46f19d8077251c4a4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "10997117"
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

# Microsoft Edge DevTools でモバイルデバイスをエミュレートする  

モバイルデバイスでページがどのように表示され、どのように応答するかについては、 **デバイスエミュレーション** を使用します。  Microsoft Edge の DevTools には、モバイルデバイスをエミュレートするための機能のコレクションが用意されています。  このコレクションには、次の機能が含まれています。  

*   [モバイルビューポートのシミュレーション](#simulate-a-mobile-viewport)  
*   [ネットワークを調整する](#throttle-the-network-only)  
*   [CPU を調整する](#throttle-the-cpu-only)  
*   [位置情報のシミュレーション](#override-geolocation)  
*   [向きを設定する](#set-orientation)  
*   [ユーザーエージェントの文字列を設定する](#set-user-agent-string)  

## 制限事項  

**デバイスエミュレーション** は、モバイルデバイスでのページのルックアンドフィールの最初の部分に [近い][WikiApproximation] ものです。  **デバイスエミュレーション** では、モバイルデバイスで実際にコードが実行されるわけではありません。  代わりに、モバイルユーザーエクスペリエンスをノート pc またはデスクトップからシミュレートします。  

モバイルデバイスのいくつかの側面は、DevTools ではエミュレートされません。  たとえば、モバイル Cpu のアーキテクチャは、ノート pc またはデスクトップ Cpu のアーキテクチャとは異なります。  疑わしい場合は、実際にモバイルデバイスでページを実行することをお勧めします。  [リモートデバッグ] を使って、ページがモバイルデバイスで実際に実行されているときに、コンピューターからページのコードを操作します。  コードを操作しているときに、表示、変更、デバッグ、プロファイル、またはすべて4つの操作を行うことができます。  使用しているコンピューターがノートブックまたはデスクトップコンピューターである可能性があります。  

## モバイルビューポートのシミュレーション  

[ **デバイスエミュレーションの切り替え**  \] ( ![ デバイスツールバー \ の切り替え) を選ぶ ][ImageDeviceToolbarIcon] か、[ **カスタマイズと > 制御** ] を選び `...` ます。 **デバイスエミュレーション** は、モバイルビューポートをシミュレートするための UI を開くために使用します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
    デバイスのツールバー  
:::image-end:::  

既定では、デバイスのツールバーは、応答性のあるビューポートモードで開きます。  

### 応答性ビューポートモード  

ページの外観を複数の画面サイズにわたってすばやくテストするには、ハンドルをドラッグしてビューポートのサイズを必要なサイズに変更します。  [幅] ボックスと [高さ] ボックスに特定の値を入力することもできます。  次の図では、幅がに設定され、 `626` 高さがに設定されて `516` います。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
    応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル  
:::image-end:::  

#### メディアクエリを表示する  

ページでメディアクエリを定義している場合は、ビューポートの上にメディアクエリのブレークポイントを表示して、メディアクエリが有効になるビューポートのサイズにジャンプします。  [**その他のオプション**] で [  >  **メディアクエリ] を**選びます。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="メディアクエリを表示する" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **メディアクエリを表示する**  
:::image-end:::  

メディアクエリがトリガーされるようにビューポートの幅を変更するには、ブレークポイントを選択します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="ブレークポイントを選択してビューポートの幅を変更する" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   ブレークポイントを選択してビューポートの幅を変更する  
:::image-end:::  

#### デバイスの種類を設定する  

[ **デバイスの種類** ] の一覧を使用して、モバイルデバイスやデスクトップデバイスをシミュレートします。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="[デバイスの種類] の一覧" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   [ **デバイスの種類** ] の一覧  
:::image-end:::  

次の表では、使用可能なデバイスの種類のオプションの違いについて説明します。  [レンダリング方法] 列は、Microsoft Edge が、モバイルまたはデスクトップのビューポートとしてページをレンダリングするかどうかを示します。  カーソルのアイコン列は、ページ上にカーソルを置いたときに表示されるカーソルの種類を示しています。  [トリガーされたイベント] 列は、 `touch` `click` ページを操作するときにページがトリガーまたはイベントを発生させるかどうかを示します。  

| オプション | レンダリング方法 | カーソルアイコン | トリガーされたイベント |  
|:--- |:--- |:--- |:--- |  
| モバイル | モバイル | 円形 | タッチ |  
| モバイル \ (タッチなし) | モバイル | 通常 |  で、 |  
| Desktop | Desktop | 通常 |  で、 |  
| デスクトップ \ (タッチ \) | Desktop | 円形 | タッチ |  

> [!NOTE]
> [**デバイスの種類**] の一覧が表示されない場合は、[**その他**のデバイスの種類の追加] を選択し  >  **Add device type**ます。  

### モバイルデバイスのビューポートモード  

特定のモバイルデバイスのサイズをシミュレートするには、 **デバイス** の一覧からデバイスを選びます。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="デバイスの一覧" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   **デバイス**の一覧  
:::image-end:::  

#### ビューポートを横方向に回転する  

Web ページを横方向にテストします。  

*   ビューポートを横方向に回転するには、[ **回転** \ (回転 \)] を選び ![ ][ImageRotateIcon] ます。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横方向に表示されたページ" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
       横方向に表示されたページ  
    :::image-end:::  
    
> [!NOTE]
> **デバイスのツールバー**が狭い場合、[**回転**] ボタンは表示されなくなります。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   **デバイスのツールバー**  
:::image-end:::  

詳細については、「 [印刷の向きを設定](#set-orientation)する」を参照してください。  

#### デバイスフレームの表示  

IPhone 6 などの特定のモバイルデバイスのサイズをシミュレートするときに、ビューポートの周りに物理デバイスフレームを表示します。  

1.  **その他のオプション**を開きます。  
1.  [ **デバイスフレームの表示]** を選びます。  

> [!NOTE]
> 特定のデバイスのデバイスフレームが表示されない場合は、DevTools にそのオプション用の art がないことを意味します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="デバイスフレームの表示" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         デバイスフレームの表示  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="IPhone 6 のデバイスフレーム" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         IPhone 6 のデバイスフレーム  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### カスタムモバイルデバイスを追加する  

必要なモバイルデバイスオプションが既定のリストに含まれていない場合は、カスタムデバイスを追加できます。  カスタムデバイスを追加するには、次の手順を実行します。  

1.  [ **Edit**] >**デバイス**の一覧を選択します。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="[編集] を選ぶ" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       [**編集**] を選ぶ  
    :::image-end:::  
    
1.  [ **カスタムデバイスの追加**] を選びます。  
1.  エミュレートされた **デバイス**では、デバイス名、画面の幅、およびカスタムデバイスの画面の高さを入力します。  [デバイスのピクセル比率][MDNWindowDevicePixelRatio]、[ユーザーエージェントの文字列][MDNUserAgent]、[デバイスの種類](#set-the-device-type)の各フィールドは省略可能です。  [デバイスの種類] フィールドは既定で [ **モバイル**] に設定されています。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="カスタムデバイスを作成する" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       カスタムデバイスを作成する  
    :::image-end:::  
    
### ルーラーを表示する  

画面のサイズを測定する必要がある場合は、ルーラーを使用して画面サイズをピクセル単位で測定することができます。  [**その他のオプション**] を選択  >  **Show rulers**すると、ビューポートの左上にルーラーが表示されます。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="ルーラーを表示するためのメニュー項目" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         ルーラーを表示するためのメニュー項目  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="ビューポートの左上にあるルーラー" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         ビューポートの左上にあるルーラー  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### ビューポートをズームする  

ページの外観を複数のズームレベルでテストするには、[ **ズーム** ] リストを使用して拡大または縮小します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="ズーム" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **ズーム**  
:::image-end:::  

## ネットワークと CPU を調整する  

多くの場合、モバイルデバイスではネットワークと CPU の制約があります。  ページの読み込みの速度と、さまざまなインターネットおよび CPU の速度での応答方法を確認します。  

ネットワークと CPU を調整します。  

1.  [ **スロットル** リスト] を選択して、事前設定を [ **中間層モバイル** ] または [ **ローエンド] モバイル**に変更します。  
    *   **ミッドティアのモバイル** では `fast 3G` 、CPU のシミュレーションと調整を行います。  通常よりも4倍遅くなります。  
    *   **ローエンドの携帯電話** では、 `slow 3G` CPU のシミュレーションと調整を行います。  通常よりも6倍遅くなります。  
    
すべての調整は、ノート pc またはデスクトップの通常の機能に基づいています。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="デバイスツールバーのスロットルリスト" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   デバイスツールバーの **スロットル** リスト  
:::image-end:::  

> [!NOTE]
> **スロットルリスト**が非表示になっている場合、**デバイスのツールバー**は狭すぎます。  **スロットルの一覧**にアクセスするには、デバイスの**ツールバー**の幅を広げます。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   **デバイスのツールバー**  
:::image-end:::  

### CPU のみを調整する  

ネットワークではなく CPU のみを調整するには、次の手順を実行します。

1.  [ **パフォーマンス** ] パネルを選択し、[ **キャプチャ設定** ] ( ![ キャプチャ設定) を選択し ][ImageCaptureIcon] ます。
1.  **CPU**  >  の**4 倍の速度**または6x の**減速**を選択します。
    
    :::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="パフォーマンスパネルの CPU リスト" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
       **パフォーマンス**パネルの**CPU**リスト  
    :::image-end:::  
    
### ネットワークのみを調整する  

ネットワークを調整するには、次の手順を実行します。

1.  [ **ネットワーク** ] パネルを選択します。
1.  「**オンライン**  >  **高速 3g** 」または「**低速 3g**」を選択します。
    
    :::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="[ネットワーク] パネルのスロットルリスト" lightbox="../media/device-mode-network-throttle.msft.png":::
       [ネットワーク] パネルの **スロットル** リスト  
    :::image-end:::  
    
    または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を選択して**コマンドメニュー**を開き、「 `3G` 高速な**3g 調整を有効**にする」または「**低速の3g 調整を**有効にする」を選択します。  
    
    :::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="コマンドメニュー" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
       **コマンドメニュー**  
    :::image-end:::  
    
また、[ **パフォーマンス** ] パネルからネットワークの調整を設定することもできます。  

1.  [ **キャプチャの設定** ] (キャプチャ設定) を選択し、[ ![ ][ImageCaptureIcon] **ネットワーク** ] リストを選択して、[設定] を [ **高速 3g** ] または [ **低速 3g**] に変更します。  
    
    :::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="パフォーマンスパネルからネットワーク調整を設定する" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
       **パフォーマンス**パネルからネットワーク調整を設定する  
    :::image-end:::  
    
## 位置情報を無効にする  

:::row:::
   :::column span="":::
      適切に表示するために、モバイルデバイスからの位置情報に依存しているページの場合は、位置情報オーバーライド UI を使って、さまざまな geolocations 場所を指定します。  

      1.  [**カスタマイズと制御] を選択して、** ( `...` \)**その他のツール**  >  **センサー**> します。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="位置情報のセンサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         位置情報の**センサー**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  コマンドメニューを開きます。  
          *   [ `Control` + `Shift` + `P` \ (Windows \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選びます。  
      1. 「」 `Sensors` と入力して、「 **センサーを表示**」を選択します。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="位置情報のセンサーを表示する" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         位置情報の**センサーを表示する**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

[ **センサー** ] パネルで、[ **場所** ] ドロップダウンメニューを使用して、devtools に含まれている既定の場所のいずれかを選ぶことができます。  カスタムの場所を入力するには、[**その他...** ] を選択します。 目的の場所の座標を入力します。  位置情報を利用できないときにエラー状態のページをテストするには、[ **場所を使用できませ**ん] を選択します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="既定の場所が選択されたセンサーパネル" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
    既定の場所が選択されている**センサー**パネル。  
:::image-end:::

## 向きを設定する  

:::row:::
   :::column span="":::
      適切に表示するために、モバイルデバイスからの向き情報に依存するページの場合は、方向 UI を開きます。  

      1.  [**カスタマイズと制御] を選択して、** ( `...` \)**その他のツール**  >  **センサー**> します。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="向きのセンサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         向きの**センサー**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  コマンドメニューを開きます。  
          *   [ `Control` + `Shift` + `P` \ (Windows \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選びます。  
      1. 「」 `Sensors` と入力して、「 **センサーを表示**」を選択します。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="向きのセンサーを表示する" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         向きの**センサーを表示する**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

[ **センサー** ] パネルで、[ **印刷の向き** ] ドロップダウンメニューから既定の向きを選ぶことができます。  独自の向きを入力するには、[ **ユーザー設定の向き**] を選択し、独自の [アルファ][MDNDeviceOrientaitonAlpha]、 [ベータ][MDNDeviceOrientaitonBeta]、および [ガンマ][MDNDeviceOrientaitonGamma] 値を入力します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="センサーパネルの [向き] オプション" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
    **センサー**パネルの [**向き**] オプション  
:::image-end:::  

## ユーザーエージェント文字列を設定する  

:::row:::
   :::column span="":::
      ページがモバイルデバイスからのユーザーエージェント文字列に依存して適切に表示される場合は、[ **ネットワークの条件** ] パネルを使用して、さまざまなユーザーエージェント文字列を指定します。  
      
      1.  [**カスタマイズと制御 devtools** \ (\)] を選択して、 `...` **その他**  >  のツールの**ネットワーク条件**> します。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png" alt-text="[その他のツール] メニューの [ネットワークの状態] エントリ" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png":::
         [**その他のツール**] メニューの [**ネットワークの状態**] エントリ  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  コマンドメニューを開きます。  
          *   [ `Control` + `Shift` + `P` \ (Windows \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選びます。  
      1. 「 `Network conditions` **ネットワーク条件を表示**」を選択します。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png" alt-text="ネットワークの状態を表示する" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png":::
         **ネットワークの状態を表示する**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

[ **ユーザーエージェント**] の横にある **[自動的に選択** する] チェックボックスをオフにします。  次に、[ **カスタム** ] を選択して、定義済みのユーザーエージェント文字列の一覧から選択します。  独自のユーザーエージェント文字列を入力するには、[ **カスタムユーザーエージェントの入力**] に文字列を入力します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png" alt-text="MacOS でユーザーエージェント文字列を Microsoft Edge に設定します。" lightbox="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png":::
    MacOS でユーザーエージェント文字列を Microsoft Edge に設定します。  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureIcon]: ../media/capture-settings-icon.msft.png  
[ImageDeviceToolbarIcon]: ../media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
[Devて Remoteデバッギング]:...「リモートデバッグ Android デバイスの使用を開始する」をご覧ください。Microsoft ドキュメント "  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window. Deviceピクセルの比率 |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "ユーザーエージェント |MDN"  
[MDNDeviceOrientaitonAlpha]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/alpha "DeviceOrientationEvent |MDN"  
[MDNDeviceOrientaitonBeta]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/beta "DeviceOrientationEvent |MDN"  
[MDNDeviceOrientaitonGamma]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/gamma "DeviceOrientationEvent |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "最初の順序での Wikipedia の順序"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
