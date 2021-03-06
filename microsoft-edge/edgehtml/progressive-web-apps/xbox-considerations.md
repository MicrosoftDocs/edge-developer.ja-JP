---
description: PWA が Xbox に優れたエクスペリエンスを提供するようにする
title: Xbox One 用プログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ Web アプリ、PWA、Edge、Windows、UWP、Xbox、Xbox One、TVJS
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3ac4174c821f221d6d666a25880867275ca5cbd5
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397672"
---
# <a name="progressive-web-apps-for-xbox-one"></a>Xbox One 用プログレッシブ Web アプリ  

既存のフレームワーク、CDN、サーバー バックエンドを引き続き使用しながら、Web アプリケーションを拡張し、Microsoft Store 経由で Xbox One アプリとして利用できます。  また、すべてのユニバーサル Windows プラットフォーム \(UWP\) アプリと同様に、Xbox One で実行されているプログレッシブ Web アプリ \(PWAs\) もネイティブ Windows 10 API を呼び出す可能性があります。  特にメディア再生アプリのカテゴリでは、Xbox One で使用可能な PWA [が既に多数存在します](#media-pwas-on-xbox)。  

ほとんどの場合[、PWA](https://www.pwabuilder.com)ビルダー ツールまたは Visual Studio IDE を使用して PWA を[UWP](https://visualstudio.microsoft.com/vs)アプリとして実行するために必要なファイルを生成して[、Windows](./windows-features.md)と同じ方法で Xbox One 用の PWA をパッケージ化できます。 `appxmanifest`  ただし、このガイドではいくつかの重要な違いがあります。  

## <a name="deploying-and-testing-pwas-on-xbox"></a>Xbox での PWA の展開とテスト  

開始するには、次の手順に [従って *Xbox One 開発者モードをアクティブにします*](/windows/uwp/xbox-apps/devkit-activation)。  開発者モードをアクティブ化した状態 [で *、Xbox*](/windows/uwp/debug-test-perf/device-portal-xbox) 用デバイス ポータルをセットアップして、開発環境のブラウザーから Xbox にリモート アクセスできます。  

これで、PWA ビルダーまたはアプリを使用してテスト用にアプリを展開するVisual Studio。  

### <a name="option-1--pwa-builder"></a>オプション 1: PWA ビルダー  

[PWA Builder](https://www.pwabuilder.com) は、ノード Node.js \(NPM\) からインストールパッケージ マネージャーアプリです。  Web サイトのメタデータを使用して、Android、iOS、Windows 全体でネイティブホスト型アプリを生成します。  サイトに既に [Web](https://developer.mozilla.org/docs/Web/Manifest)アプリ マニフェストがある場合、PWA ビルダーは Web アプリ マニフェストを使用してプラットフォーム固有のインストール パッケージを生成します。  それ以外の場合、PWA ビルダーはサイトの特性に `manifest.json` 基づいて基本的なファイルを生成します。  

#### <a name="requirements"></a>要件  

*   [Node.js](https://nodejs.org)NPM を含む。  

#### <a name="setup"></a>セットアップ  

1.  ノード コマンド プロンプトを開き、PWA ビルダーをインストールします。  
    
    ```shell
    npm install pwabuilder --global
    ```  
    
1.  Web サイトの URL で PWA ビルダーを実行します。  
    
    ```shell
    pwabuilder https://example.com/ -windows10
    ```  
    
    *-windows10 フラグは*、パッケージの生成を Windows 10 \(UWP\) に制限します。  iOS や Android を含む、サポートされているプラットフォーム全体でパッケージを生成するには、パッケージを省略できます。  詳細については [、PWA Builder ドキュメント](https://docs.pwabuilder.com) を参照してください。  
    
1.  Xbox 用デバイス[ポータル](/windows/uwp/debug-test-perf/device-portal-xbox)で、[ホーム**** マイ ゲーム & アプリの追加] に移動し、緩いファイルをアップロードするオプションを選択し、現在のディレクトリで PWA ビルダーによって生成された  >  ****  >  **** Windows 10**** アプリ マニフェスト フォルダーを選択します。  
1.  ウィザードの手順を実行して、インストール プロセスを完了します。  一度インストールします。  Xbox One ダッシュボードから PWA を表示および起動できます。  
    
### <a name="option-2--visual-studio"></a>オプション 2: Visual Studio  

無料のフル機能の [Visual Studio コミュニティ 2017](https://visualstudio.microsoft.com/vs/community) には、Windows 10 開発者ツール、ユニバーサル アプリ テンプレート、コード エディター、強力なデバッガー、Windows Mobile エミュレーター、豊富な言語サポートなど、すべてが実稼働環境で使用できます。  プロフェッショナル [バージョンとエンタープライズ バージョンでは](https://visualstudio.microsoft.com/vs/compare) 、さらに多くの機能が提供されます。  

#### <a name="requirements"></a>要件  

*   [Visual Studio 2017:](https://visualstudio.microsoft.com/vs)無料のコミュニティ エディションを含む任意のバージョン。  
*   [Windows 10 SDK](/windows/uwp/xbox-apps/development-environment-setup): 2017 インストーラーでこのオプション コンポーネントVisual Studio選択します。  

#### <a name="setup"></a>セットアップ  

1.  手順に従って [、ユニバーサル Windows アプリとして PWA をセットアップして実行します](./windows-features.md#set-up-and-run-your-universal-windows-app)。  これにより、ユニバーサル Windows API にアクセスできる完全に機能する Windows 10 アプリが用意されています。  
1.  これで、Windows リモート デバッガーを使用して、Xbox One \(他の Windows 10 リモート デバイス\と同様に [Visual Studio)](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017&preserve-view=true
)で PWA \(UWP アプリ\) を展開およびデバッグできます。  または、次の手順を使用して Xbox 用デバイス ポータルを使用して [PWA](/windows/uwp/debug-test-perf/device-portal-xbox) をインストールすることもできます。  
1.  Xbox のデバイス ポータルで、[ホーム**** マイ ゲーム] \& [アプリの追加] に移動し、[アプリ パッケージと依存関係] をアップロードするオプション  >  ****  >  ******を選択します**。  
1.  手順 1 でアプリ用に生成したパッケージ フォルダーに移動し、アップロードする `.appx` ファイルを選択します。  [.appx ファイルは](/windows/uwp/packaging/packaging-uwp-apps)、テスト目的で任意のデバイスにサイドロードできる UWP アプリ パッケージ ファイルです。  
1.  次に、[ **依存関係] ボタンを** タップし、アプリのサブフォルダーを選択し `dependencies` 、それぞれをアップロードします。  この手順は、Xbox 用デバイス ポータルからアプリを展開する場合にのみ必要です。  Visual Studio、リモート デバッグ時に依存関係が提供され、エンド ユーザーのコンピューターは Microsoft Store から配信された場合に既にこれらの依存関係がインストールされます。  
1.  アプリ パッケージと依存関係がアップロードされた場合は、[展開] セクションの**[**移動**] ボタンをクリックすると、アプリがインストールされます。  Xbox からアプリを起動する準備ができました。  

## <a name="ux-considerations-for-pwas-on-xbox"></a>Xbox の PWA の UX に関する考慮事項  

### <a name="design-for-the-10-foot-experience"></a>"10-Foot Experience" の設計  

Xbox One は"10 フィートのエクスペリエンス" と見なされます。つまり、ユーザーは画面から少なくとも 10 フィート離れた場所に座っている可能性があります。  そのため、マウスとキーボードを使用した従来のデスクトップ Web ブラウザーエクスペリエンスとは対照的に、アプリをその距離でどのように使用する可能性があるのか検討してください。  デザインと UX のガイダンスについては [、「Xbox とテレビのデザイン」を参照してください](/windows/uwp/design/devices/designing-for-tv)。  

### <a name="understand-the-tv-safezone"></a>"TV SafeZone" を理解する  

テレビメーカーは、アプリを [クリップできる](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) コンテンツの周囲にセーフ ゾーンを適用します。  既定では、これを考慮するためにアプリの周囲に安全な枠線を適用しますが [、setDesiredBoundsMode](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) を呼び出して [useCoreWindow](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode)を指定することで、アプリが画面全体のサイズを取得できます。  

```javascript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```  

詳細については [、Windows.UI.ViewManagement 名前空間のドキュメントを](/uwp/api/windows.ui.viewmanagement) 参照してください。  

### <a name="manage-xy-focus-and-navigation"></a>XY フォーカスとナビゲーションの管理  

Xbox のユーザー入力方法はゲームパッドまたはリモート コントロールであり [、XY](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)ナビゲーション システムを使用して、ユーザーは上、下、左、右に移動して、コントロールからコントロールにフォーカスを移動できます。  

そのため、アプリが XY ナビゲーションとうまく機能する必要があります。  また、マウス モードを無効に [してください。これは](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)、UWP アプリの既定でオンになっています 。また、アプリの Xbox エクスペリエンス\には当てはめられない可能性があります)。  

次のコードはモードをオフ `mouse` にし、ゲームパッド入力で DOM キーボード イベントを生成できます。  

```javascript
navigator.gamepadInputEmulation = "keyboard";
```  

または、マウスをオフにし、DOM キーボード イベントを生成しない、標準の Web または WinRT ゲームパッド API を使用することもできます `gamepad` 。  

方向ナビゲーションを有効にするには、次に説明する [TVJS ライブラリ](#tvjs)を参照してください。  

### <a name="tvjs"></a>TVJS  

[TVJS は、テレビ用](https://github.com/Microsoft/TVHelpers) の Web アプリケーションを簡単に構築できるヘルパー ライブラリのコレクションです。  Xbox でも実行されるホスト型 Web アプリを構築する場合、TVJS は方向ナビゲーションの** サポートを追加したり、テレビ上のコンテンツを操作しやすくするための複数のコントロールを提供したりするのに役立ちます。  

[方向ナビゲーション](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) は、テレビ アプリのページ内で自動 2 次元ナビゲーションを提供する TVJS 機能です。  この機能を使用すると、アプリのページ内のナビゲーションをトラップして処理したり、UI 内の各要素の有効なフォーカス ターゲットを明示的に指定する必要はありません。  自動フォーカス処理により、ユーザーは直感的で堅牢な方法で移動できます。  

ユーザーがコントローラーの方向ボタンを使用してアプリ UI を移動すると、自動フォーカス アルゴリズムは、一連の潜在的なフォーカス ターゲットを確認し、移動する次の要素を決定し、その要素にフォーカスを自動的に設定します。  次の要素を決定するために、アルゴリズムは、方向入力、過去のフォーカス履歴、ページ上の UI 要素の物理的なレイアウトを組み合わせたものになります。  

方向ナビゲーションを有効にするには、次のスクリプト参照を含める必要があります。  

```html
<script src="directionalnavigation-1.0.0.0.js"></script>
```  

既定では、、 `<a>` 、 `<button>` 、 `<input>` `<select>` 、、および要素 `<textarea>` だけがフォーカス可能です。  他の要素にフォーカスを設定するには、有効な [tabindex を割り当てる必要があります](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)。  

```html
<div tabindex="0″>This div is eligible for focus</div>
```  

ルート要素の変更、初期フォーカスの設定、次のフォーカスの上書き、フォーカスのコントロールの最適化、入力のカスタマイズ方法については [、DirectionalNavigation](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation) のドキュメントを参照してください。  他にも役立つサンプルも多数用意されています。

## <a name="media-pwas-on-xbox"></a>Xbox のメディア PWA  

Xbox One 用のメディア再生 PWA を作成する場合は、次の考慮事項に注意してください。  

### <a name="encrypted-media-extensions-eme-in-the-browser"></a>ブラウザーの暗号化されたメディア拡張機能 (EME)  

Xbox One の Microsoft Edge[](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)ブラウザーでは、暗号化メディア拡張機能 \(EME\) はサポートされていません。  メディア PWA がデジタル著作権管理 \(DRM\) に使用している場合、Xbox のブラウザーからメディアを実行できません。  代わりに、前述のように [、PWABuilder](#deploying-and-testing-pwas-on-xbox)またはアプリを使用して Xbox One アプリVisual Studioテストします。  EME が完全にサポートされている Windows の Microsoft Edge ブラウザーでも実行できます。  

### <a name="integrating-with-system-media-transport-controls"></a>システム メディア トランスポート コントロールとの統合  

アプリがメディア アプリの場合は、アプリが画面のボタン [、Cortana](https://support.xbox.com/xbox-one/console/cortana-voice-commands)音声コマンド、ナビゲーション ウィンドウの System [Media Transport Controls、](/windows/uwp/audio-video-camera/system-media-transport-controls) または他のデバイスの [Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) と [Xbox One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2) アプリを介してユーザーによって開始されたメディア コントロールに応答することが重要です。  これらのコントロールと自動的に統合される[TVJS](#tvjs)ライブラリから[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)コントロールを確認します。  または、システム メディア トランスポート コントロール [と手動で統合することもできます](/windows/uwp/audio-video-camera/system-media-transport-controls)。  

### <a name="playready-content-encryption"></a>PlayReady コンテンツの暗号化  

この記事の執筆時点では [、cbcs エンコード](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme) サポートは XBox One 用の PlayReady クライアント \(バージョン 1709 以上\) に制限されています。  PWA のメディアが **cbcs** 暗号化のみをサポートしている場合は、Windows でアプリの機能が制限される可能性が高い \(または完全に使用できない\) に注意してください。  

## <a name="see-also"></a>関連項目  

[サウス リッジ ビデオ](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): Web サーバー上でホストされている、React.js Xbox 用のサンプル ビデオ アプリ。  

[Xbox とテレビ](/windows/uwp/design/devices/designing-for-tv)向けデザイン : ユニバーサル Windows プラットフォーム \(UWP\) アプリを設計して、Xbox One とテレビ画面でうまく機能するようにします。  

[Xbox のベスト プラクティス](/windows/uwp/xbox-apps/tailoring-for-xbox): Xbox One 用にアプリを調整するには、次のベスト プラクティスに従います。  

[Microsoft ストアの PWA](./microsoft-store.md): PWA を Microsoft ストアに送信する方法を次に示します。  

[Xbox One の UWP: Xbox](/windows/uwp/xbox-apps/index)One 用の UWP アプリ開発の完全なガイド。  
