---
description: PWA が Xbox に優れたエクスペリエンスを提供するようにする
title: Xbox One 用の段階的な Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 段階的な Web アプリ、PWA、Edge、Windows、UWP、Xbox、Xbox One、TVJS
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f1c46fe49f335373323de106b1b2a84418b97577
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235076"
---
# Xbox One 用の段階的な Web アプリ  

既存のフレームワーク、CDN、サーバー バックエンドを引き続き使用しながら、Web アプリケーションを拡張し、Microsoft Store 経由で Xbox One アプリとして利用できます。  また、すべてのユニバーサル Windows プラットフォーム (UWP) アプリと同様に、Xbox One で実行される段階的な Web アプリ (PAP) も、ネイティブの Windows 10 API を呼び出す可能性があります。  Xbox One では、特にメディア再生アプリのカテゴリに多数の [PAS が既に用意されています](#media-pwas-on-xbox)。  

ほとんどの場合、Windows の場合と同じ方法で Xbox One[](./windows-features.md)用の PWA をパッケージ化できます。PWA [Builder](https://www.pwabuilder.com/)ツールまたは[Visual Studio](https://visualstudio.microsoft.com/vs/) IDE を使用して、PWA を UWP アプリとして実行するために必要な*appxmanifest*ファイルを生成します。 ただし、このガイドではいくつかの重要な違いについて説明します。

## Xbox での PAS の展開とテスト

開始するには、次の手順に [従って *Xbox One 開発者モードをアクティブ化します*](/windows/uwp/xbox-apps/devkit-activation) 。 開発者モードをアクティブ化した状態で[*、Xbox 用 Device Portal を*](/windows/uwp/debug-test-perf/device-portal-xbox)セットアップして、お使いの環境のブラウザーから Xbox にリモート アクセスします。

これで *、PWA* Builder または Visual Studio を使用して、テスト用にアプリを展開*する準備が整Visual Studio。*

### オプション 1: PWA Builder

[PWA Builder](https://www.pwabuilder.com/) は、node Node.js (NPM) からインストールできるパッケージ マネージャーアプリです。 Web サイトのメタデータを使用して、Android、iOS、Windows 全体でネイティブでホストされるアプリを生成します。 サイトに既に [Web](https://developer.mozilla.org/docs/Web/Manifest)アプリ マニフェストがある場合、PWA Builder は Web アプリ マニフェストを使用してプラットフォーム固有のインストール パッケージを生成します。 それ以外の場合、PWA Builder は、サイト * のmanifest.js* に基づいてファイルに基づいて基本的なファイルを生成します。

#### 要件

 - [Node.js](https://nodejs.org/en/)NPM を含む。

#### セットアップ

1.  Node コマンド プロンプトを開き、PWA ビルダーをインストールします。
    
    ```shell
    npm install pwabuilder --global
    ```  
    
2.  Web サイトの URL で PWA Builder を実行します。
    
    ```shell
    pwabuilder https://example.com/ -windows10
    ```  
    
    *-windows10 フラグは*、パッケージの生成を Windows 10 (UWP) に制限します。 iOS や Android を含む、サポートされているプラットフォーム全体でパッケージを生成する場合は省略できます。 詳細については [、PWA Builder のドキュメント](https://docs.pwabuilder.com/) を参照してください。
    
3.  Xbox[用 Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox)で****、[ホーム マイ ゲーム] & アプリの [追加] に移動し、ルーズ ファイルをアップロードするオプションを選択し、現在のディレクトリで PWA Builder によって生成された  >  ****  >  **** Windows 10** アプリ マニフェスト フォルダーを選択します。

4.  ウィザードをステップ実行してインストール プロセスを完了します。 インストール後。 Xbox One ダッシュボードから PWA を表示して起動できます。
    
### オプション 2: Visual Studio

無料のフル機能を備える [Visual Studio Community 2017](https://visualstudio.microsoft.com/vs/community/) には、Windows 10 開発者ツール、ユニバーサル アプリ テンプレート、コード エディター、強力なデバッガー、Windows Mobile エミュレーター、豊富な言語サポートなど、すべて実稼働環境で使用できる状態が含まれています。 Professional [*および* *Enterprise のバージョンでは*](https://visualstudio.microsoft.com/vs/compare/) 、さらに多くの機能が提供されます。

#### 要件

-   [**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
    ): 無料の *Community* エディションを含む任意のバージョン。
-   [**Windows 10 SDK:**](/windows/uwp/xbox-apps/development-environment-setup)Visual Studio *2017 インストーラーでこのオプション コンポーネントを選択します*。
    
#### セットアップ

1.  手順に従って [、PWA をユニバーサル Windows アプリとしてセットアップして実行します](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app)。 これにより、ユニバーサル Windows API にアクセスできる完全に機能する Windows 10 アプリが提供されます。
2.  [Visual Studio リモート デバッガー](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017 &preserve-view=true) を使用して、(他の Windows 10 リモート デバイスと同様に) Xbox One で PWA を展開およびデバッグできます。 または、次の手順を使用して [、Xbox 用 Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox) を使用して PWA をインストールすることもできます。
3.  Xbox 用 Device Portal で、[ホーム] > [マイ ゲーム] & [> 追加] に移動し、アプリ パッケージと依存関係をアップロードするオプション *を選択します*。
4.  手順 1 でアプリ用に生成したパッケージ フォルダーに移動し、アップロードする *.appx* ファイルを選択します。 [ *.appx ファイルは*](/windows/uwp/packaging/packaging-uwp-apps)、テスト目的で任意のデバイスにサイドロードできる UWP アプリ パッケージ ファイルです。
5.  次に、[**依存関係] ボタンを**タップ** し、アプリの依存関係サブフォルダーを選択し、それぞれをアップロードします。 この手順は、Xbox 用 Device Portal からアプリを展開する場合にのみ必要です。 Visual Studioデバッグとエンド ユーザーのコンピューターが Microsoft Store から配信される場合に、これらの依存関係が既にインストールされている場合に、依存関係が提供されます。
6.  アプリ パッケージと依存関係がアップロードされた後、[展開] セクションの下** の [**移動**] ボタンをクリックすると、アプリがインストールされます。 Xbox からアプリを起動する準備ができました。
    
## Xbox の PAS の UX に関する考慮事項

### "10 フィート エクスペリエンス" の設計

Xbox One は "10 フィート エクスペリエンス" と見なされます。つまり、ユーザーは画面から少なくとも 10 フィート離れた場所に座っている可能性があります。 そのため、マウスとキーボードを使った従来のデスクトップ Web ブラウザー エクスペリエンスとは対照的に、アプリをその距離でどのように使うのか検討します。 設計と UX のガイダンスについては [、Xbox およびテレビ向け設計を参照してください](/windows/uwp/design/devices/designing-for-tv)。

### "TV SafeZone" について

テレビの製造元は、アプリ [をクリップできるコンテンツ](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) の周囲に「セーフ ゾーン」を適用します。 既定では、アプリの周囲に安全な境界線が適用されます。ただし、次を呼び出して指定することで、アプリが全画面サイズを取る [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) 必要があります [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode) 。

```javascript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```  

詳細については、名前空間のドキュメント [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) を参照してください。

### XY フォーカスとナビゲーションを管理する

Xbox のユーザー入力方法はゲームパッドまたはリモコンで [、XY](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)ナビゲーション システムを使います。ユーザーは、上、下、左、右に移動して、フォーカスをコントロールからコントロールに移動できます。

そのため、アプリが XY ナビゲーションで正常に動作する必要があります。 また、必ずマウス[** モード](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)を無効にしてください。マウス モードは、UWP アプリに対して既定でオンになっています (アプリの Xbox エクスペリエンスには適用されない可能性があります)。

次のコードはモードをオフ `mouse` にし、ゲームパッド入力で DOM キーボード イベントを生成できます。

```javascript
navigator.gamepadInputEmulation = "keyboard";
```  

または、マウスをオフにしたり、DOM キーボード イベントを生成したり、標準の Web や WinRT ゲームパッド API を使用したりすることもできます `gamepad` 。

方向ナビゲーションを有効にするには、次に説明 [する TVJS ライブラリ](#tvjs)を確認してください。

### TVJS

[TVJS は、テレビ用](https://github.com/Microsoft/TVHelpers) の Web アプリケーションを簡単に構築できるヘルパー ライブラリのコレクションです。 Xbox でも実行されるホストされた Web アプリを構築している場合、TVJS は方向ナビゲーションの** サポートを追加したり、テレビのコンテンツを操作しやすくするコントロールを提供したりするのに役立ちます。

[方向ナビゲーション](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) は、テレビ アプリのページ内で自動 2 次元ナビゲーションを提供する TVJS 機能です。 アプリでは、アプリのページ内のナビゲーションをトラップして処理したり、UI の各要素の有効なフォーカス ターゲットを明示的に指定したりする必要はありません。 自動フォーカス処理により、ユーザーは直感的で堅牢な方法で移動できます。

ユーザーがコントローラーの方向ボタンを使ってアプリ UI を移動すると、自動フォーカス アルゴリズムは潜在的なフォーカス ターゲットのセットを見て、移動先の次の要素を決定し、自動的にその要素にフォーカスを設定します。 次の要素を決定するために、このアルゴリズムは、方向入力、過去のフォーカス履歴、ページ上の UI 要素の物理的なレイアウトを組み合わせたものになります。

方向ナビゲーションを有効にするには、次のスクリプト リファレンスを含める必要があります。

```html
<script src="directionalnavigation-1.0.0.0.js"></script>
```  

既定では、フォーカス可能な要素は 、 `<a>` `<button>` `<input>` `<select>` `<textarea>` 。 他の要素にフォーカスを設定するには、有効な [tabindex を割り当てる必要があります](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)。

```html
<div tabindex="0″>This div is eligible for focus</div>
```  

ルート要素の変更、初期フォーカスの設定、次のフォーカスの上書き、フォーカス用のコントロールの最適化、入力のカスタマイズを行う方法については [、DirectionalNavigation](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation) のドキュメントを参照してください。 その他にも役立つサンプルが多数用意されています。

## Xbox のメディア PAS

Xbox One 用のメディア再生 PWA を構築する場合は、次の考慮事項に注意してください。

### ブラウザーでの暗号化されたメディア拡張機能 (EME)

Xbox One の Microsoft Edge ブラウザーは、 [暗号化](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API) メディア拡張機能 (EME) をサポートしていない。 メディア PWA がデジタル著作権管理 (DRM) にメディアを使用している場合、Xbox のブラウザーから実行できません。 代わりに、前述のように [、PWABuilder](#deploying-and-testing-pwas-on-xbox)または Visual Studioを使用して Xbox One アプリとしてプロトタイプを作成してテストします。 EME が完全にサポートされている Windows の Microsoft Edge ブラウザーでも実行できます。

### システム メディア トランスポート コントロールとの統合

アプリがメディア アプリの場合は、アプリが画面ボタン[、Cortana](https://support.xbox.com/xbox-one/console/cortana-voice-commands)音声コマンド、ナビゲーション ウィンドウのシステム メディア トランスポート コントロール、または他のデバイス上の[](/windows/uwp/audio-video-camera/system-media-transport-controls)Xbox および[Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) [One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2)アプリを介して、ユーザーによって開始されたメディア コントロールに応答することが重要です。 TVJS ライブラリから[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)コントロール[](#tvjs)を見て、これらのコントロールと自動的に統合されます。 または、システム メディア トランスポート [コントロールと手動で統合することもできます](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls)。

### PlayReady コンテンツの暗号化

この記事の執筆時点では、[ `cbcs` ](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme)エンコードのサポートは XBox One (バージョン 1709 以上) の PlayReady クライアントに制限されています。 PWA のメディアが *cbcs* 暗号化のみをサポートしている場合、Windows ではアプリの機能が制限されている (または完全に利用できない) 可能性があります。

## 関連項目
[South South South Video](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): React.js を使用して構築され、Web サーバーでホストされる Xbox 用のサンプル ビデオ アプリです。

[Xbox とテレビ向け](/windows/uwp/design/devices/designing-for-tv)設計: ユニバーサル Windows プラットフォーム (UWP) アプリを設計して、Xbox One とテレビ画面で見栄えよく機能するようにします。

[Xbox のベスト プラクティス](/windows/uwp/xbox-apps/tailoring-for-xbox): 次のベスト プラクティスに従って、Xbox One 用にアプリを調整します。

[Microsoft Store の PWA](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store): PWA を Microsoft Store に提出する方法 (および理由) を次に示します。

[Xbox One の UWP: Xbox One](/windows/uwp/xbox-apps/)向け UWP アプリ開発の完全なガイド。
