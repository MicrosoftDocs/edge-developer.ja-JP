---
title: Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 10c1ee12777965778ebec2d257399dc231e2a01a
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607427"
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

デバイスモードは、モバイルデバイスでページがどのように表示されるか、どのように感じられるかについての[最初の概算][WikiApproximation]と考えることができます。  デバイスモードでは、モバイルデバイスで実際にコードを実行することはありません。  ノート pc またはデスクトップでモバイルユーザーエクスペリエンスをシミュレートします。  

DevTools はシミュレートできないモバイルデバイスにはいくつかの側面があります。  たとえば、モバイル Cpu のアーキテクチャは、ノート pc またはデスクトップ Cpu のアーキテクチャとは大きく異なります。  疑わしい場合は、実際にモバイルデバイスでページを実行することをお勧めします。  [リモートデバッグ] を使用して、モバイルデバイスで実際に実行しているときに、ノート pc またはデスクトップからページのコードを表示、変更、デバッグ、プロファイルすることができます。  

## モバイルビューポートのシミュレーション   

[**デバイスツールバー**の切り替え] をクリックして ![ ][ImageDeviceToolbarIcon] 、モバイルビューポートをシミュレートできる UI を開きます。  

> ##### 図 1  
> デバイスのツールバー  
> ![デバイスのツールバー][ImageDeviceToolbar]  

既定では、デバイスのツールバーは、応答性のあるビューポートモードで開きます。  

### 応答性ビューポートモード   

ハンドルをドラッグして、ビューポートのサイズを必要なサイズに変更します。  または、[幅] ボックスと [高さ] ボックスに特定の値を入力します。  [図 2](#figure-2)では、幅がに設定され、 `626` 高さがに設定されて `516` います。  

> ##### 図 2  
> 応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル  
> ![応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル][ImageResponsiveHandles]  

#### メディアクエリを表示する   

ビューポートの上にメディアクエリのブレークポイントを表示するには、[**その他のオプション**] をクリックし、[**メディアクエリの表示**] を選択します。  

> ##### 図 3  
> メディアクエリを表示する  
> ![メディアクエリを表示する][ImageShowMediaQueries]  

ブレークポイントをクリックして、ブレークポイントがトリガーされるようにビューポートの幅を変更します。  

> ##### 図 4  
> ブレークポイントをクリックしてビューポートの幅を変更する  
> ![ブレークポイントをクリックしてビューポートの幅を変更する][ImageBreakpoint]  

#### デバイスの種類を設定する   

[**デバイスの種類**] の一覧を使用して、モバイルデバイスやデスクトップデバイスをシミュレートします。  

> ##### 図 5  
> [**デバイスの種類**] の一覧  
> ![[デバイスの種類] の一覧][ImageDeviceType]  

次の表では、オプションの違いについて説明します。  **レンダリングメソッド**は、Microsoft Edge がモバイルビューポートまたはデスクトップビューポートとしてページをレンダリングするかどうかを示します。  **カーソルアイコン**は、ページ上にマウスポインターを置いたときに表示されるカーソルの種類を表します。  **イベント**は、 `touch` `click` ページを操作するときにそのページが起動するか、イベントを発生させるかを示します。  

| オプション | レンダリング方法 | カーソルアイコン | イベントを発生させる |  
|:--- |:--- |:--- |:--- |  
| モバイル | モバイル | 円形 | タッチ |  
| モバイル \ (タッチなし) | モバイル | 通常 |  で、 |  
| Desktop | Desktop | 通常 |  で、 |  
| デスクトップ \ (タッチ \) | Desktop | 円形 | タッチ |  

> [!NOTE]
> [**デバイスの種類**] の一覧が表示されない場合は、[**その他のオプション**] をクリックし、[デバイスの種類の**追加**] を選択します。  

### モバイルデバイスのビューポートモード   

特定のモバイルデバイスのサイズをシミュレートするには、**デバイス**の一覧からデバイスを選びます。  

> ##### 図 6  
> デバイスの一覧  
> ![デバイスの一覧][ImageDeviceList]  

#### ビューポートを横方向に回転する   

[回転回転] を**クリックし** ![ ][ImageRotateIcon] て、ビューポートを横方向に回転させます。  

> ##### 図 7  
> 横方向  
> ![横方向][ImageLandscape]  

> [!NOTE]
> **デバイスのツールバー**が狭い場合、[**回転**] ボタンは表示されなくなります。  

> ##### 図 8  
> デバイスのツールバー  
> ![デバイスのツールバー][ImageDeviceToolbar2]  

「[方向を設定](#set-orientation)する」もご覧ください。  

#### デバイスフレームの表示   

IPhone 6 など特定のモバイルデバイスのサイズをシミュレートする場合は、[**その他のオプション**] を開き、[**デバイスフレームの表示**] を選択して、ビューポートの周りに物理デバイスフレームを表示します。  

> [!NOTE]
> 特定のデバイスのデバイスフレームが表示されない場合は、DevTools にその特定のオプション用の art がないことが考えられます。  

> ##### 図 9  
> デバイスフレームの表示  
> ![デバイスフレームの表示][ImageShowDeviceFrame]  

> ##### 図 10  
> IPhone 6 のデバイスフレーム  
> ![IPhone 6 のデバイスフレーム][ImageIphoneFrame]  

#### カスタムモバイルデバイスを追加する   

カスタムデバイスを追加するには:  

1.  **デバイス**の一覧をクリックし、[**編集**] を選択します。  

> ##### 図 11  
> [**編集]** の [編集] を選ぶ 
> ![][ImageEdit]  

1.  [**カスタムデバイスの追加**] をクリックします。  

1.  デバイスの名前、幅、高さを入力します。  [デバイスのピクセル比率][MDNWindowDevicePixelRatio]、[ユーザーエージェントの文字列][MDNUserAgent]、[デバイスの種類](#set-the-device-type)の各フィールドは省略可能です。  [デバイスの種類] フィールドは、既定で [**モバイル**] に設定されているリストです。  

> ##### 図 12  
> カスタムデバイスの作成  
> ![カスタムデバイスの作成][ImageAddCustomDevice]  

### ルーラーを表示する   

[**その他のオプション**] をクリックし、[**ルーラーの表示**] を選択して、ビューポートの左上にあるルーラーを表示します。  ルーラーのサイズ調整単位はピクセルです。  

> ##### 図 13  
> ルーラーを表示する  
> ![ルーラーを表示する][ImageShowRulers]  

> ##### 図 14  
> ビューポートの左上にあるルーラー  
> ![ビューポートの左上にあるルーラー][ImageRulers]  

### ビューポートをズームする   

拡大または縮小するには、[**ズーム**] リストを使用します。  

> ##### 図 15  
> ズーム  
> ![ズーム][ImageZoomViewport]  

## ネットワークと CPU を調整する   

ネットワークと CPU を調整するには、[**調整**] の一覧から [**ミッドティアモバイル**] または [**ローエンド**] のモバイルを選択します。  

> ##### 図 16  
> スロットルリスト  
> ![スロットルリスト][ImageThrottling]  

**ミッドティアモバイル**では、高速3g をシミュレートし、CPU を調整して、通常よりも4倍遅くなるようにします。  **ローエンドの携帯電話**では、低速の3g がシミュレートされ、CPU の6倍が通常よりも遅くなります。  調整は、ノート pc またはデスクトップの通常の機能に関連していることに注意してください。  

> [!NOTE]
> **デバイスのツールバー**が狭い場合は、**スロットル**リストが非表示になります。  

> ##### 図 17  
> デバイスのツールバー  
> ![デバイスのツールバー][ImageDeviceToolbar3]  

### CPU のみを調整する   

ネットワークではなく CPU のみを調整するには、[**パフォーマンス**] パネルに移動し、[**キャプチャ設定**キャプチャの設定] をクリックして、[ ![ ][ImageCaptureIcon] **CPU** ] 一覧から [ **4 倍速**] または [ **6x の速度**] を選びます。  

> ##### 図18  
> CPU リスト  
> ![CPU リスト][ImageCPU]  

### ネットワークのみを調整する   

ネットワークのみを対象とし、CPU は調整しない場合は、**ネットワーク**パネルを開いて、[**スロットル**] の一覧から [ **Fast 3G** ] または [**低速の 3g** ] を選びます。  

> ##### 図19  
> スロットルリスト  
> ![スロットルリスト][ImageNetwork]  

または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押すと、コマンドメニューが開き、「 `3G` **高速な3g 調整を有効**にする」または「低速な**3g 調整**を有効にする」を選択します。  

> ##### 図20  
> コマンドメニュー  
> ![コマンドメニュー][ImageCommandMenu]  

[**パフォーマンス**] パネルからネットワークの調整を設定することもできます。  「**キャプチャ設定** ![ キャプチャ設定」をクリックし ][ImageCaptureIcon] て、「 **Fast 3G** 」または「**低速な 3g** 」を**ネットワーク**リストから選択します。  

> ##### 図21  
> パフォーマンスパネルからネットワーク調整を設定する  
> ![パフォーマンスパネルからネットワーク調整を設定する][ImageNetwork2]  

## 位置情報を無効にする   

位置情報を上書きする UI を開くには、[ **devtools のカスタマイズと制御**] をクリックし、[ `...` **その他のツール**センサー] を選択し  >  **Sensors**ます。  

> ##### 図22  
> センサー  
> ![センサー][ImageSensors]  

または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押してコマンドメニューを開き、「 `Sensors` 」と入力して、[**センサーの表示**] を選択します。  

> ##### 図23  
> センサーの表示  
> ![センサーの表示][ImageShowSensors]  

[**位置情報] の一覧から**いずれかのプリセットを選ぶか、[**場所**の指定] を選んで独自の座標を入力するか、[場所を選択**できません**] を選択して、位置情報がエラー状態にあるときのページの動作をテストします。  

> ##### 図24  
> 位置情報  
> ![位置情報][ImageGeolocation]  

## 向きを設定する   

向きの UI を開くには、[カスタマイズ] をクリックし、[ **devtools** ] をクリックして、[ `...` **その他のツール**センサー] を選択し  >  **Sensors**ます。  

> ##### 図25  
> センサー  
> ![センサー][ImageSensors2]  

または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押してコマンドメニューを開き、「 `Sensors` 」と入力して、[**センサーの表示**] を選択します。  

> ##### 図26  
> センサーの表示  
> ![センサーの表示][ImageShowSensors2]  

[**印刷の向き**] の一覧からいずれかのプリセットを選択するか、[**ユーザー設定の向き**] を選択して、独自のアルファ、ベータ、およびガンマ値を設定します。  

> ##### 図27  
> Orientation  
> ![Orientation][ImageOrientation]  

 



<!--See [Join the DevTools community][DevToolsCommunity] for other ways to leave feedback.  -->  

<!-- image links -->  

[ImageCaptureIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageCustomizeIcon]: /microsoft-edge/devtools-guide-chromium/media/customize-and-control-devtools-icon.msft.png  
[ImageDeviceToolbarIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: /microsoft-edge/devtools-guide-chromium/media/rotate-dark-icon.msft.png  

[ImageDeviceToolbar]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-highlighted.msft.png "図 1: デバイスのツールバー"  
[ImageResponsiveHandles]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png "図 2: 応答可能なビューポートモードのときにビューポートの寸法を変更するためのハンドル"  
[ImageShowMediaQueries]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png "図 3: メディアクエリを表示する"  
[ImageBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png "図 4: ブレークポイントをクリックしてビューポートの幅を変更する"  
[ImageDeviceType]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-device-type-list.msft.png "図 5: [デバイスの種類] の一覧"  
[ImageDeviceList]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-device-list.msft.png "図 6: デバイスの一覧"  
[ImageLandscape]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-landscape.msft.png "図 7: 横方向"  
[ImageDeviceToolbar2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-highlighted.msft.png "図 8: デバイスのツールバー"  
[ImageShowDeviceFrame]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png "図 9: デバイスフレームの表示"  
[ImageIphoneFrame]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png "図 10: iPhone 6 のデバイスフレーム"  
[ImageEdit]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-device-list-edit.msft.png "図 11: [編集] を選ぶ"  
[ImageAddCustomDevice]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png "図 12: カスタムデバイスの作成"  
[ImageShowRulers]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png "図 13: ルーラーを表示する"  
[ImageRulers]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-rulers.msft.png "図 14: ビューポートの左上にあるルーラー"  
[ImageZoomViewport]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-zoom.msft.png "図 15: ズーム"  
[ImageThrottling]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-throttle.msft.png "図 16: スロットルリスト"  
[ImageDeviceToolbar3]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-highlighted.msft.png "図 17: デバイスのツールバー"  
[ImageCPU]: /microsoft-edge/devtools-guide-chromium/media/device-mode-performance-cpu-throttle.msft.png "図 18: CPU の一覧"  
[ImageNetwork]: /microsoft-edge/devtools-guide-chromium/media/device-mode-network-throttle.msft.png "図 19: スロットルの一覧"  
[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/device-mode-command-menu-throttle.msft.png "図 20: コマンドメニュー"  
[ImageNetwork2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-performance-network-throttle.msft.png "図 21: パフォーマンスパネルからネットワーク調整を設定する"  
[ImageSensors]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png "図 22: センサー"  
[ImageShowSensors]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png "図 23: センサーを表示する"  
[ImageGeolocation]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png "図 24: 位置情報"  
[ImageSensors2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png "図 25: センサー"  
[ImageShowSensors2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png "図 26: センサーを表示する"  
[ImageOrientation]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png "図 27: 向き"  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community"  -->
[Devて Remoteデバッギング]:/microsoft-edge/devtools-guide-chromium/remote-debugging/index "Android デバイスのリモートデバッグの開始"  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window. Deviceピクセルの比率 |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "ユーザーエージェント |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "最初の順序での Wikipedia の順序"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
