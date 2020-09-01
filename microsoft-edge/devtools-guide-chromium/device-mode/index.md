---
title: Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6973f28a0cb530e8928976adb1354fa7471ee343
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10985312"
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





# Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする   

  

モバイルデバイスでのページの外観と実行方法については、デバイスモードを使用します。  

デバイスモードは、モバイルデバイスをシミュレートするために役立つ Microsoft Edge DevTools の機能のルースコレクションの名前です。  次のような機能があります。  

*   [モバイルビューポートのシミュレート](#simulate-a-mobile-viewport)  
*   [ネットワークの調整](#throttle-the-network-only)  
*   [CPU の調整](#throttle-the-cpu-only)  
*   [位置情報のシミュレーション](#override-geolocation)  
*   [向きの設定](#set-orientation)  

## 制限事項   

デバイスモードは、モバイルデバイスでページがどのように表示されるか、どのように感じられるかについての [最初の概算][WikiApproximation] と考えることができます。  デバイスモードでは、モバイルデバイスで実際にコードを実行することはありません。  ノート pc またはデスクトップでモバイルユーザーエクスペリエンスをシミュレートします。  

DevTools はシミュレートできないモバイルデバイスにはいくつかの側面があります。  たとえば、モバイル Cpu のアーキテクチャは、ノート pc またはデスクトップ Cpu のアーキテクチャとは大きく異なります。  疑わしい場合は、実際にモバイルデバイスでページを実行することをお勧めします。  [リモートデバッグ] を使用して、モバイルデバイスで実際に実行しているときに、ノート pc またはデスクトップからページのコードを表示、変更、デバッグ、プロファイルすることができます。  

## モバイルビューポートのシミュレーション   

[ **デバイスツールバーの切り替え** ] ( ![ デバイスツールバー ][ImageDeviceToolbarIcon] \ の切り替え) をクリックして、モバイルビューポートをシミュレートできる UI を開きます。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   デバイスのツールバー  
:::image-end:::  

既定では、デバイスのツールバーは、応答性のあるビューポートモードで開きます。  

### 応答性ビューポートモード   

ハンドルをドラッグして、ビューポートのサイズを必要なサイズに変更します。  または、[幅] ボックスと [高さ] ボックスに特定の値を入力します。  次の図では、幅がに設定され、 `626` 高さがに設定されて `516` います。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
   応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル  
:::image-end:::  

#### メディアクエリを表示する   

ビューポートの上にメディアクエリのブレークポイントを表示するには、[ **その他のオプション** ] をクリックし、[ **メディアクエリの表示**] を選択します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="メディアクエリを表示する" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **メディアクエリを表示する**  
:::image-end:::  

ブレークポイントをクリックして、ブレークポイントがトリガーされるようにビューポートの幅を変更します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="ブレークポイントをクリックしてビューポートの幅を変更する" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   ブレークポイントをクリックしてビューポートの幅を変更する  
:::image-end:::  

#### デバイスの種類を設定する   

[ **デバイスの種類** ] の一覧を使用して、モバイルデバイスやデスクトップデバイスをシミュレートします。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="[デバイスの種類] の一覧" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   [ **デバイスの種類** ] の一覧  
:::image-end:::  

次の表では、オプションの違いについて説明します。  **レンダリングメソッド** は、Microsoft Edge がモバイルビューポートまたはデスクトップビューポートとしてページをレンダリングするかどうかを示します。  **カーソルアイコン** は、ページ上にマウスポインターを置いたときに表示されるカーソルの種類を表します。  **イベント** は、 `touch` `click` ページを操作するときにそのページが起動するか、イベントを発生させるかを示します。  

| オプション | レンダリング方法 | カーソルアイコン | イベントを発生させる |  
|:--- |:--- |:--- |:--- |  
| モバイル | モバイル | 円形 | タッチ |  
| モバイル \ (タッチなし) | モバイル | 通常 |  で、 |  
| Desktop | Desktop | 通常 |  で、 |  
| デスクトップ \ (タッチ \) | Desktop | 円形 | タッチ |  

> [!NOTE]
> [ **デバイスの種類** ] の一覧が表示されない場合は、[ **その他のオプション** ] をクリックし、[デバイスの種類の **追加**] を選択します。  

### モバイルデバイスのビューポートモード   

特定のモバイルデバイスのサイズをシミュレートするには、 **デバイス** の一覧からデバイスを選びます。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="デバイスの一覧" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   **デバイス**の一覧  
:::image-end:::  

#### ビューポートを横方向に回転する   

**Rotate** ![ ][ImageRotateIcon] ビューポートを横方向に回転するには、[回転 (回転 \)] をクリックします。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横方向" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
   横方向  
:::image-end:::  

> [!NOTE]
> **デバイスのツールバー**が狭い場合、[**回転**] ボタンは表示されなくなります。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   **デバイスのツールバー**  
:::image-end:::  

「 [方向を設定](#set-orientation)する」もご覧ください。  

#### デバイスフレームの表示   

IPhone 6 など特定のモバイルデバイスのサイズをシミュレートする場合は、[ **その他のオプション** ] を開き、[ **デバイスフレームの表示** ] を選択して、ビューポートの周りに物理デバイスフレームを表示します。  

> [!NOTE]
> 特定のデバイスのデバイスフレームが表示されない場合は、DevTools にその特定のオプション用の art がないことが考えられます。  

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

カスタムデバイスを追加するには:  

1.  **デバイス**の一覧をクリックし、[**編集**] を選択します。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="[編集] を選ぶ" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       [**編集**] を選ぶ  
    :::image-end:::  
    
1.  [ **カスタムデバイスの追加**] をクリックします。  
1.  デバイスの名前、幅、高さを入力します。  [デバイスのピクセル比率][MDNWindowDevicePixelRatio]、[ユーザーエージェントの文字列][MDNUserAgent]、[デバイスの種類](#set-the-device-type)の各フィールドは省略可能です。  [デバイスの種類] フィールドは、既定で [ **モバイル** ] に設定されているリストです。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="カスタムデバイスを作成する" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       カスタムデバイスの作成  
    :::image-end:::  

### ルーラーを表示する   

[ **その他のオプション** ] をクリックし、[ **ルーラーの表示** ] を選択して、ビューポートの左上にあるルーラーを表示します。  ルーラーのサイズ調整単位はピクセルです。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="ルーラーを表示する" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         **ルーラーを表示する**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="ビューポートの左上にあるルーラー" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         ビューポートの左上にあるルーラー  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### ビューポートをズームする   

拡大または縮小するには、[ **ズーム** ] リストを使用します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="ズーム" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **ズーム**  
:::image-end:::  

## ネットワークと CPU を調整する   

ネットワークと CPU を調整するには、[**調整**] の一覧から [**ミッドティアモバイル**] または [**ローエンド**] のモバイルを選択します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="スロットルリスト" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   **スロットル**リスト  
:::image-end:::  

**ミッドティアモバイル** では、高速3g をシミュレートし、CPU を調整して、通常よりも4倍遅くなるようにします。  **ローエンドの携帯電話** では、低速の3g がシミュレートされ、CPU の6倍が通常よりも遅くなります。  調整は、ノート pc またはデスクトップの通常の機能に関連していることに注意してください。  

> [!NOTE]
> **デバイスのツールバー**が狭い場合、**スロットル**リストは表示されません。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   **デバイスのツールバー**  
:::image-end:::  

### CPU のみを調整する   

ネットワークではなく CPU のみを調整するには、[**パフォーマンス**] パネルに移動し、[**キャプチャの設定**] (キャプチャ設定) をクリックして、[ ![ ][ImageCaptureIcon] **CPU** ] の一覧から [ **4 倍速**(減速)] または [ **6x** ] を選びます。  

:::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="CPU リスト" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
   **CPU**リスト  
:::image-end:::  

### ネットワークのみを調整する   

ネットワークのみを対象とし、CPU は調整しない場合は、**ネットワーク**パネルを開いて、[**スロットル**] の一覧から [ **Fast 3G** ] または [**低速の 3g** ] を選びます。  

:::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="スロットルリスト" lightbox="../media/device-mode-network-throttle.msft.png":::
   **スロットル**リスト  
:::image-end:::  

または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押すと、**コマンドメニュー**が開き、「 `3G` 高速な**3g 調整を有効**にする」または「**低速な3g 調整**を有効にする」を選択します。  

:::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="コマンドメニュー" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
   **コマンドメニュー**  
:::image-end:::  

[ **パフォーマンス** ] パネルからネットワークの調整を設定することもできます。  「 **キャプチャ設定** 」 ( ![ キャプチャ設定 ][ImageCaptureIcon] ) をクリックして、「 **Fast 3G** 」または「 **低速な 3g** 」を **ネットワーク** リストから選択します。  

:::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="パフォーマンスパネルからネットワーク調整を設定する" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
   **パフォーマンス**パネルからネットワーク調整を設定する  
:::image-end:::  

## 位置情報を無効にする   

位置情報を上書きする UI を開くには、[**ユーザー設定と制御**] をクリックして ( `...` \)、[**その他のツール**センサー] を選択し  >  **Sensors**ます。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="センサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
   **センサー**  
:::image-end:::  

または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押してコマンドメニューを開き、「 `Sensors` 」と入力して、[**センサーの表示**] を選択します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="センサーの表示" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
   **センサーの表示**  
:::image-end:::  

[ **位置情報] の一覧から** いずれかのプリセットを選ぶか、[ **場所** の指定] を選んで独自の座標を入力するか、[場所を選択 **できません** ] を選択して、位置情報がエラー状態にあるときのページの動作をテストします。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="位置情報" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
   **位置情報**  
:::image-end:::  

## 向きを設定する   

:::row:::
   :::column span="":::
      向きの UI を開くには、[カスタマイズ] をクリックし、[ **devtools** ] をクリックして、[ `...` **その他のツール**センサー] を選択し  >  **Sensors**ます。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="センサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         **センサー**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押してコマンドメニューを開き、「 `Sensors` 」と入力して、[**センサーの表示**] を選択します。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="センサーの表示" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **センサーの表示**  
      :::image-end:::  
   :::column-end:::
:::row-end:::

[ **印刷の向き** ] の一覧からいずれかのプリセットを選択するか、[ **ユーザー設定の向き** ] を選択して、独自のアルファ、ベータ、およびガンマ値を設定します。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="Orientation" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
   **Orientation**  
:::image-end:::  

<!--  
 


-->  

<!--See [Join the DevTools community][DevToolsCommunity] for other ways to leave feedback.  -->  

<!-- image links -->  

[ImageCaptureIcon]: ../media/capture-settings-icon.msft.png  
[ImageDeviceToolbarIcon]: ../media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
[Devて Remoteデバッギング]:...「リモートデバッグ Android デバイスの使用を開始する」をご覧ください。Microsoft ドキュメント "  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window. Deviceピクセルの比率 |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "ユーザーエージェント |MDN"  

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
