---
description: PWA が Xbox の優れたエクスペリエンスを提供することを確認する
title: Windows 用の PWA をカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、UWP、Xbox、Xbox One、TVJS
ms.openlocfilehash: 8c2660c8821826660d2030f832ae449ff4a061ad
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570764"
---
# Xbox One 向けのプログレッシブ Web アプリ

既存のフレームワーク、CDN、サーバーバックエンドの使用を継続しながら、web アプリケーションを拡張し、Microsoft Store 経由で Xbox One アプリとして利用できるようにすることができます。  また、すべてのユニバーサル Windows プラットフォーム (UWP) アプリと同様に、Xbox One で実行されているプログレッシブ Web アプリ (PWAs) は、ネイティブ Windows 10 Api を呼び出すこともできます。  Xbox One では、特に[メディア再生アプリ](#media-pwas-on-xbox)のカテゴリにいくつかの pwas が用意されています。  

ほとんどの場合、 [Windows と同じよう](./windows-features.md)に、Pwa を Windows と同じ方法でパッケージ化することができます。 pwa[ビルダー](https://www.pwabuilder.com/)ツールまたは[Visual Studio](https://visualstudio.microsoft.com/vs/) IDE を使用して、pwa を UWP アプリとして実行するために必要な*package.appxmanifest*ファイルを生成できます。 ただし、このガイドでは、いくつかの重要な相違点について説明します。

## Xbox での PWAs の展開とテスト

始めるには、次の手順に従って、 [ *Xbox One 開発者モード*をアクティブに](/windows/uwp/xbox-apps/devkit-activation)します。 開発者モードが有効になっている場合、 [ *Xbox 用 Device Portal* ](/windows/uwp/debug-test-perf/device-portal-xbox)をセットアップして、開発環境のブラウザーから xbox にリモートアクセスできるようにします。

これで、 *PWA ビルダー*または*Visual Studio*を使ってテスト用のアプリを展開する準備ができました。

### オプション 1: PWA ビルダー

[PWA ビルダー](https://www.pwabuilder.com/)は、ノードパッケージマネージャー (npm) からインストールできる node.js アプリです。 Android、iOS、Windows でネイティブにホストされるアプリを生成するために、web サイトのメタデータを使用します。 サイトに既に[web アプリマニフェスト](https://developer.mozilla.org/docs/Web/Manifest)が含まれている場合、PWA ビルダーは、プラットフォーム固有のインストールパッケージを生成するためにそれを使います。 そうしないと、PWA ビルダーは、サイトの特性に基づいて基本的な*manifest.xml*ファイルを生成します。

#### 要件
 - [Node.js](https://nodejs.org/en/)。 npm が含まれます。

#### セットアップ

1. ノードコマンドプロンプトを開いて、PWA ビルダーをインストールします。

    ```
    npm install pwabuilder --global
    ```

2. 自分の web サイトの URL で PWA ビルダーを実行します。

    ```
    pwabuilder https://example.com/ -windows10
    ```

    *-Windows 10*フラグは、パッケージの生成を Windows 10 (UWP) に制限します。 これを省略して、iOS や Android など、サポートされているすべてのプラットフォームでパッケージを生成することができます。 詳しい情報については、「 [PWA ビルダーのドキュメント](https://docs.pwabuilder.com/)」を参照してください。

3. [Xbox の Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox)で、[**ホーム**]、& [アプリの追加] の順に移動し、  >  **My games & apps**  >  **Add**圧縮していない*ファイルをアップロード*するオプションを選択して、PWA ビルダーによって生成された Windows 10 アプリのマニフェストフォルダーを現在のディレクトリで選択します。

4. ウィザードの手順に従って、インストール処理を完了します。 インストールが完了したら、 Xbox One ダッシュボードから PWA を表示して起動することができます。


### オプション 2: Visual Studio

無料のフル機能の[Visual Studio コミュニティ 2017](https://visualstudio.microsoft.com/vs/community/)には、windows 10 開発者ツール、ユニバーサルアプリテンプレート、コードエディター、強力なデバッガー、Windows Mobile エミュレーター、豊富な言語のサポートなどが用意されています。これらはすべて実稼働環境で使用できます。 [*プロフェッショナル*と*エンタープライズ*](https://visualstudio.microsoft.com/vs/compare/)のバージョンには、さらに多くの機能が用意されています。

#### 要件

 - [**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
): 無料の*コミュニティ*エディションを含む任意のバージョン。
 - [**Windows 10 SDK**](/windows/uwp/xbox-apps/development-environment-setup): *Visual Studio 2017 インストーラー*でこのオプションコンポーネントを選択します。

#### セットアップ

1. 手順に従って、 [PWA をユニバーサル Windows アプリとしてセットアップし、実行](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app)します。 これにより、ユニバーサル Windows Api にアクセスできる、完全に機能する Windows 10 アプリが完成します。

2. [Visual Studio リモートデバッガー](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017
)を使って、(他の Windows 10 リモートデバイスと同じように) Xbox ONE に PWA (UWP アプリとして) を展開してデバッグできるようになりました。 または、次の手順を使用して、 [Xbox 用 Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox)を使用して PWA をインストールすることもできます。

3. Xbox の Device Portal で、[ホーム] > [& アプリ > 追加] に移動して、*アプリパッケージと依存関係*をアップロードするオプションを選びます。

4. 手順1でアプリ用に生成したパッケージフォルダーに移動し、アップロードする *.appx*ファイルを選びます。 [ *.Appx*ファイル](/windows/uwp/packaging/packaging-uwp-apps)は UWP アプリパッケージファイルであり、テスト目的で任意のデバイスでサイドローディングできます。

5. 次に、[**依存関係**] ボタンをタップして、アプリの [*依存関係*] サブフォルダーを選び、それぞれアップロードします。 この手順は、Xbox 用 Device Portal からアプリを展開する場合にのみ必要です。 Visual Studio では、リモートデバッグとエンドユーザーのコンピューターが、Microsoft Store から配信されたときに、これらの依存関係を既にインストールしている場合に依存関係が提供されます。

6. アプリパッケージと依存関係がアップロードされた状態で、[*展開*] セクションの下にある [**移動**] ボタンをクリックすると、アプリがインストールされます。 Xbox からアプリを起動する準備ができました。

## 「PWAs for Xbox」の UX の考慮事項

### "10 フィートエクスペリエンス" の設計

Xbox One は "10 フィートエクスペリエンス" と見なされます。つまり、ユーザーは画面から少なくとも10フィート離れていることが考えられます。 そのため、マウスとキーボードを使用した従来のデスクトップ web ブラウザー操作と比べて、その距離でアプリを使う方法を検討してください。 デザインと UX のガイダンスについては、「 [Xbox およびテレビ向け設計](/windows/uwp/design/devices/designing-for-tv)」をご覧ください。

### "TV SafeZone" について理解する

テレビの製造元は、アプリをクリップできるコンテンツの周りに["セーフゾーン"](/windows/uwp/design/devices/designing-for-tv#tv-safe-area)を適用します。 既定では、アプリの周囲に安全な境界線が適用されますが、このためには、アプリが次のように呼び出してすべての画面サイズを使用できるようにする必要が [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode) あります。

```JavaScript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```

詳しくは、「名前空間のドキュメント」をご覧 [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) ください。

### XY フォーカスとナビゲーションを管理する

Xbox のユーザー入力方式は、ゲームパッドまたはリモートコントロールであり、 [XY ナビゲーションシステム](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)を使用しているため、ユーザーはフォーカスを ctrl キーを押しながら上下左右に移動してコントロールに切り替えることができます。

したがって、XY ナビゲーションでアプリが適切に動作することを確認してください。 また、UWP アプリでは既定でオンになっている[*マウスモード*を無効](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)にします (アプリの Xbox エクスペリエンスには適用されない場合もあります)。

次のコードは、 `mouse` モードをオフにして、ゲームパッド入力を有効にして、DOM キーボードイベントを生成します。

```JavaScript
navigator.gamepadInputEmulation = "keyboard";
```

または、 `gamepad` マウスをオフにして、DOM キーボードイベントを生成せず、標準の web または WinRT のゲームパッド api を使用できるように指定することもできます。

方向ナビゲーションを有効にするには、 [TVJS ライブラリ](#tvjs)について、次の説明を参照してください。

### TVJS

TVJS は、テレビ用の web アプリケーションを簡単に構築できるようにする[ヘルパーライブラリのコレクション](https://github.com/Microsoft/TVHelpers)です。 Xbox でも実行されるホストされた web アプリを作成している場合、TVJS は*方向ナビゲーション*のサポートを追加するのに役立ちます。また、テレビ上のコンテンツを簡単に操作するためのいくつかのコントロールも用意されています。

[方向ナビゲーション](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)は、テレビアプリのページ内での自動2次元のナビゲーションを提供する TVJS 機能です。 この機能を使うと、アプリのページ内でのナビゲーションをトラップして処理する必要がなくなります。また、UI の各要素のすべての有効なフォーカスターゲットを明示的に指定する必要もありません。 自動フォーカス処理により、ユーザーは直感的で確実な方法で移動できます。

ユーザーがコントローラーの方向ボタンを使ってアプリの UI に移動すると、自動フォーカスアルゴリズムは、一連の潜在的なフォーカスターゲットを確認し、移動先の次の要素を特定し、自動的にフォーカスをその要素に設定します。 次の要素を決定するために、アルゴリズムは、方向入力、過去のフォーカス履歴、およびページ上の UI 要素の物理レイアウトを組み合わせたものです。

方向ナビゲーションを有効にするには、次のスクリプト参照を含めます。

```HTML
<script src="directionalnavigation-1.0.0.0.js"></script>
```

既定では、、、、、 `<a>` `<button>` `<input>` `<select>` および `<textarea>` 要素のみがフォーカス可能になります。 他の要素にフォーカスを設定するには、有効な[tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)を割り当てます。

```HTML
<div tabindex="0″>This div is eligible for focus</div>
```

ルート要素の変更、初期フォーカスの設定、次のフォーカスの上書き、フォーカス用コントロールの最適化、入力のカスタマイズ方法については、「 [direction」ナビゲーション](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation)ドキュメントをご覧ください。 さらに多くの便利なサンプルも用意されています。

## メディア p が Xbox にありました

Xbox One 向けに PWA 再生メディアを作成している場合は、次の点に注意してください。

### ブラウザーの暗号化されたメディア拡張機能 (EME)

Xbox One の Microsoft Edge ブラウザーは、[暗号化されたメディア拡張機能](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)(EME) をサポートしていません。 メディア PWA でデジタル著作権管理 (DRM) に使用されている場合は、Xbox のブラウザーから実行することはできません。 代わりに、前に説明したように、 [PWABuilder または Visual Studio を使って Xbox One アプリ](#deploying-and-testing-pwas-on-xbox)としてプロトタイプし、テストします。 また、Windows の Microsoft Edge ブラウザーで EME が完全にサポートされている場合にも実行できます。

### システムメディアトランスポートコントロールとの統合

アプリがメディアアプリの場合、アプリは、ユーザーが開始したメディアコントロールに対して、画面上のボタン、 [Cortana の音声コマンド](https://support.xbox.com/xbox-one/console/cortana-voice-commands)、ナビゲーションウィンドウの[システムメディアトランスポートコントロール](/windows/uwp/audio-video-camera/system-media-transport-controls)、またはその他のデバイス上にある[Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
)と[xbox One smartglass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2)アプリを使って応答することが重要です。 これらのコントロールと自動的に統合される、 [TVJS ライブラリ](#tvjs)の[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)コントロールを見てみます。 または、手動で[システムメディアトランスポートコントロールと統合](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls)することもできます。

### PlayReady コンテンツの暗号化

このドキュメントを作成した時点では、エンコードのサポートは XBox One の PlayReady クライアント (バージョン1709以上) に[ `cbcs` 制限され](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme)ています。 PWA のメディアが*cbcs*暗号化のみをサポートしている場合は、Windows でアプリの機能が制限される (または完全に利用できない) 可能性があることに注意してください。



## 関連項目
[サウス Ridge video](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): web サーバー上で動作する .js でホストされている Xbox 用のサンプルビデオアプリ。

[Xbox およびテレビ向け設計](/windows/uwp/design/devices/designing-for-tv): xbox One とテレビ画面で適切に動作するように、ユニバーサル Windows プラットフォーム (UWP) アプリを設計します。

[Xbox のベストプラクティス](/windows/uwp/xbox-apps/tailoring-for-xbox): 以下のベストプラクティスに従って、xbox One 用にアプリを調整してください。

[Microsoft store で](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store)動作しています。ここでは、microsoft ストアに PWA を提出する方法 (およびその理由) について説明します。

[Xbox one の uwp](/windows/uwp/xbox-apps/): xbox one の uwp アプリ開発の包括的なガイドです。
