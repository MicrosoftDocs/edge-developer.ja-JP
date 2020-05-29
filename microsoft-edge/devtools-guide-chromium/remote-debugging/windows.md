---
title: Windows 10 デバイスのリモートデバッグの概要
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、リモート、デバッグ、windows 10、windows、device portal
ms.openlocfilehash: b944e1f16d4c26f4db83e3eb131f1da8ea938c97
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569763"
---
# Windows 10 デバイスのリモートデバッグの概要  

Windows または macOS コンピューターから Windows 10 デバイスのリモートデバッグライブコンテンツ。  このチュートリアルでは、次の方法について説明します。  

*   リモートデバッグ用に Windows 10 デバイスをセットアップし、開発用コンピューターから接続します。  
*   開発用コンピューターから Windows 10 デバイス上のライブコンテンツを検査およびデバッグします。  
*   Windows 10 デバイスのコンテンツを開発用コンピューターの DevTools インスタンスに Screencast します。  

## 手順 1: ホスト (デバッグ用コンピューター) をセットアップする  

ホストまたはデバッガーマシンは、デバッグする Windows 10 デバイスです。  物理的にアクセスするのが難しいリモートデバイスの場合もあれば、キーボードとマウスの周辺機器を持っていない場合は、そのデバイスで Microsoft Edge の DevTools を操作することも困難です。  ホスト (デバッグ対象) コンピューターをセットアップするには、次のことを行う必要があります。  

*   Microsoft Edge をインストールして構成する[(Chromium)](https://www.microsoft.com/edge)  
*   Microsoft [Store](https://www.microsoft.com/store/apps/windows)から[Microsoft Edge 用リモートツール (ベータ版)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)をインストールする  
*   [開発者モード](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development)をアクティブ化し、 [Device Portal](https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal)を有効にする  

### Microsoft Edge をインストールして構成する (Chromium)  

まだインストールしていない場合は、[このページ](https://www.microsoft.com/edge)から Microsoft Edge (Chromium) をインストールしてください。  ホスト (デバッグ対象) コンピューターでプレインストールされているバージョンの Microsoft Edge を使用している場合は、microsoft edge (Chromium) がインストールされていて、Microsoft Edge (EdgeHTML) を使用していることを確認してください。  簡単に確認するには、 `edge://settings/help` ブラウザーに読み込み、バージョン番号が75以上であることを確認します。  

次に、 `edge://flags` [Microsoft Edge (Chromium)] に移動します。  [**検索フラグ**] に「 **Windows Device Portal 経由のリモートデバッグを有効にする**」を入力します。  フラグを**Enabled**に設定します。  次に、[**再起動**] ボタンをクリックして、Microsoft Edge (Chromium) を再起動します。  

> ##### 図 1  
> [ **Windows Device Portal でリモートデバッグを有効**にする] フラグを [**有効**] に設定する  
> ![[Windows Device Portal でリモートデバッグを有効にする] フラグを [有効] に設定する](./windows-media/edge-flags-on-host.png)  

### Microsoft Edge 用リモートツールをインストールする (ベータ版)  

[Microsoft Store](https://www.microsoft.com/store/apps/windows)から[Microsoft Edge 用リモートツール (ベータ版)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)をインストールします。  

> [!NOTE]
> Windows 10 バージョン1809またはそれ以前のバージョンを使用している場合、 [Microsoft Edge 用リモートツール (ベータ版)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)の [ **Get** ] ボタンが無効になることがあります。  ホスト (デバッグ対象) コンピューターをセットアップするには、Windows 10 バージョン1903以降を実行している必要があります。  ホスト (デバッグ対象) コンピューターを更新して、 [Microsoft Edge (ベータ版) のリモートツール](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)を取得します。  

> ##### 図 2  
> [Microsoft Store](https://www.microsoft.com/store/apps/windows)の[Microsoft Edge (ベータ版) のリモートツール](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)  
> ![Microsoft Store の Microsoft Edge (ベータ版) のリモートツール](./windows-media/remote-tools-in-store.png)  

[Microsoft Edge 用リモートツール](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)を起動し、メッセージが表示されたら、アプリの [アクセス許可] ダイアログボックスを承諾します。 これで、 [Microsoft Edge 用リモートツール (ベータ版)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)を閉じることができるようになりました。今後のリモートデバッグセッションでは、それを開く必要はありません。

### 開発者モードをアクティブ化し、Device Portal を有効にする  

WiFi ネットワークを使用している場合は、ネットワークが [**ドメイン**] または [**プライベート**] に設定されていることを確認します。  これを確認するには、 **Windows セキュリティ**アプリを開き、[**ファイアウォール & ネットワーク保護**] をクリックして、使用しているネットワークが**ドメイン**ネットワークと**プライベート**ネットワークのどちらであるかを確認します。  

**パブリック**として表示される場合は、[**設定**  >  **ネットワーク & インターネット**  >  **wi-fi**] に移動し、使用しているネットワークをクリックして、[**ネットワークプロファイル**] ボタンを [**プライベート**] に切り替えます。  

次に、**設定**アプリを開きます。  [**設定の検索**] で、[**開発者向け設定**] を入力して選択します。  **開発者モード**で切り替えます。  [**ローカルエリアネットワーク接続でのリモート診断**を有効にする] を **[** オン] に設定して、 **Device Portal**を有効にできるようになりました。  必要に**応じて、** クライアント (デバッガー) デバイスがこのデバイスに接続するための正しい資格情報を提供する必要があります。  

> [!NOTE]
> 「**ローカルエリアネットワーク接続を介してリモート診断を有効にする」をオンにします。** は以前有効になっていました。これを無効にして、 **Device Portal**が[Microsoft Edge 用リモートツール (ベータ版)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)で動作するようにする必要があります。 [**設定**] に [**開発者向け**] セクションが表示されない場合は、 **device Portal**が既に有効になっている可能性があります。代わりに、Windows 10 デバイスを再起動してみてください。

> ##### 図 3  
> **開発者モード**と**Device Portal**が構成された**設定**アプリ  
> ![開発者モードと Device Portal が構成された設定アプリ](./windows-media/host-settings.png)  

[**接続の方法:**] の下に、コンピューターの IP アドレスと接続ポートが表示されていることを確認します。  以下の画像の IP アドレス `192.168.86.78` と接続ポートは、 `50080` です。  

> ##### 図 4  
> [**設定**] の IP アドレスと接続ポートを確認します。  
> ![[設定] の IP アドレスと接続ポートを確認します。](./windows-media/host-settings-ip-address.png)  

この情報は、[次のセクション](#step-2-set-up-the-client-debugger-machine)でクライアント (デバッガー) デバイスに入力します。  クライアント (デバッガー) コンピューターからデバッグするホスト (デバッグ対象) コンピューター上で、Microsoft Edge および[プログレッシブ Web アプリ (PWAs)](../progressive-web-apps.md)でタブを開きます。  

## 手順 2: クライアントをセットアップする (デバッガーコンピューター)  

クライアントまたはデバッガーマシンが、デバッグ元のデバイスです。  このデバイスは、日常の開発マシンである場合や、自宅で作業しているときに PC または MacBook である場合があります。  

クライアント (デバッガー) コンピューターをセットアップするには、[このページ](https://www.microsoft.com/edge)から Microsoft Edge (Chromium) をインストールしてください (まだインストールしていない場合)。  ホスト (デバッグ対象) コンピューターでプレインストールされているバージョンの Microsoft Edge を使用している場合は、microsoft edge (Chromium) がインストールされていて、Microsoft Edge (EdgeHTML) を使用していることを確認してください。  簡単に確認するには、 `edge://settings/help` ブラウザーに読み込み、バージョン番号が75以上であることを確認します。  

次に、 `edge://flags` [Microsoft Edge (Chromium)] に移動します。  [**検索フラグ**] に「 **edge://inspect でのリモート Windows デバイスのデバッグを有効にする**」と入力します。  フラグを**Enabled**に設定します。  次に、[**再起動**] ボタンをクリックして、Microsoft Edge (Chromium) を再起動します。  

> ##### 図 5  
> Edge://inspect フラグを**有効**にして、[**リモート Windows デバイスのデバッグを有効**にする] を設定する  
> ![Edge://inspect フラグを有効にして、[リモート Windows デバイスのデバッグを有効にする] を設定する](./windows-media/edge-flags-on-client.png)  

次に、 `edge://inspect` Microsoft Edge (Chromium) のページに移動します。  既定では、[**デバイス**] セクションに表示されます。  [**リモート Windows デバイスに接続する**] の下で、[http://:] のようなボックスに、ホスト (デバッグ対象) マシンの IP アドレスと接続ポートを入力します。 `IP address` `connection port`  次**に、[デバイスに接続] を**クリックします。  

> ##### 図 6  
> `edge://inspect`クライアントのページ  
> ![クライアントの edge://inspect ページ](./windows-media/edge-inspect.png)  

ホスト (デバッグ対象) マシンの認証を設定すると、クライアント (デバッガー) マシンの**ユーザー名**と**パスワード**を入力するように求めるメッセージが表示され、正常に接続されます。  

### Http ではなく https を使用する  

代わりに、の代わりにホスト (デバッグ対象) コンピューターに接続する場合は `https` `http` 、 `http://IP address:50080/config/rootcertificate` クライアント (デバッガー) コンピューターで Microsoft Edge に、[] を選択する必要があります。 これにより、という名前のセキュリティ証明書が自動的にダウンロードされ `rootcertificate.cer` ます。

[オン] をクリックし `rootcertificate.cer` ます。 [Windows 証明書マネージャーツール](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in#view-certificates-with-the-certificate-manager-tool)が開きます。

[**証明書のインストール**] をクリックし、[**現在のユーザー** ] が選択されていることを確認して、[**次へ**] をクリックします。 **次に、[証明書をすべて次のストアに配置する**] を選択し、[**参照.**..] をクリックします。[**信頼されたルート証明機関**] ストアを選択し、[ **OK]** をクリックします。 **[次へ]**、**[完了]** の順にクリックします。 メッセージが表示されたら、**信頼されたルート証明機関**ストアにこの証明書をインストールすることを確認します。

これで、ページを使用してクライアント (デバッガー) コンピューターからホスト (デバッグ対象) コンピューターに接続するときに、 `edge://inspect` 別の値を使用する必要があり `connection port` ます。  既定では、デスクトップウィンドウについて、Device Portal は `50080` for のとして使用され `connection port` `http` ます。  の場合 `https` 、Device Portal では、 `50043` `IP address` `50043` ページ上の https://: というパターンに従い `edge://inspect` ます。  [詳細については、Device Portal で使用される既定のポートに関する情報を参照](https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal#setup)してください。  

> [!NOTE]
> の既定のポートはですが、の既定のポートはですが、 `http` `50080` `https` `50043` デバイス上の既存のポート要求との競合を防ぐために、デスクトップのデバイスポータル (>5万) では常に、このようなことはありません。  詳細については、「Windows デスクトップの Device Portal の[ポートの設定](https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal-desktop#registry-based-configuration-for-device-portal)」セクションを参照してください。  

## 手順 3: クライアントからホストのコンテンツをデバッグする  

クライアント (デバッガー) のコンピューターがホスト (デバッグ対象) コンピューターに正常に接続された場合、 `edge://inspect` クライアントのページには Microsoft Edge のタブの一覧と、開いている PWAs がホストに表示されます。  

> ##### 図 7  
> `edge://inspect`クライアントのページに Microsoft Edge のタブと PWAs がホストされている  
> ![クライアントの edge://inspect ページには、Microsoft Edge のタブと PWAs がホストに表示されています。](./windows-media/edge-inspect-connected.png)  

デバッグするコンテンツを決定し、[**検査**] をクリックします。  Microsoft Edge DevTools が新しいタブで開き、ホスト (デバッグ対象) マシンからクライアント (デバッガー) コンピューターにコンテンツが screencast されます。  これで、クライアントで Microsoft Edge DevTools の全機能を使用して、ホストで実行されているコンテンツを使用できるようになりました。  Microsoft Edge DevTools の使い方については、[こちら](../../devtools-guide-chromium.md)を参照してください。  

> ##### 図 8  
> ホスト上の Microsoft Edge のタブをデバッグしているクライアントの[Microsoft Edge DevTools](../../devtools-guide-chromium.md)  
> ![ホスト上の Microsoft Edge のタブをデバッグしているクライアントの Microsoft Edge DevTools](./windows-media/devtools-client.png)  

### 要素を検査する  

たとえば、要素を調べてみます。  クライアント上の DevTools インスタンスの**要素**パネルに移動し、要素の上にマウスポインターを置いて、ホストデバイスのビューポートでその要素を強調表示します。  

また、ホストデバイスの画面で要素をタップして、[**要素**] パネルで選ぶこともできます。  クライアント上の DevTools インスタンスで [**要素の選択**] をクリックし、ホストデバイス画面で要素をタップします。  **[要素の選択]** は、最初のタッチの後に無効になっているため、この機能を使うたびに有効にする必要があります。  

> [!IMPORTANT]
> Windows 10 バージョン1903では、[**要素**] パネルの [**イベントリスナー** ] ウィンドウが空白になっています。  これは既知の問題であり、Windows 10 バージョン1903へのサービス更新プログラムの [**イベントリスナー** ] ウィンドウを修正します。  

## 手順 4: ホスト画面をクライアントデバイスに Screencast する  

既定では、クライアント上の DevTools インスタンスは screencasting に切り替えられます。これにより、クライアントデバイス上の DevTools インスタンスのホストデバイスでコンテンツを表示できます。  [ **Screencast の切り替え**] をクリックしてオフにするか、この機能をオンにします。  

> ##### 図 9  
> クライアント上の Microsoft Edge DevTools の [ **Screencast の切り替え**] ボタン  
> ![クライアント上の Microsoft Edge DevTools の [Screencast の切り替え] ボタン](./windows-media/toggle-screencast.png)  

Screencast はさまざまな方法で操作できます。  
*   クリックは、デバイスで適切なタッチイベントを発生させるために、タップに変換されます。  
*   コンピューターのキーボード操作がデバイスに送信されます。  
*   ピンチジェスチャをシミュレートするには、 `Shift` ドラッグ中にホールドします。  
*   スクロールするには、トラックパッドまたはマウスホイール、またはマウスポインターでフリックを使用します。  

スクリーンキャストに関する注意事項:  
*   スクリーンキャストは、ページコンテンツを表示します。  Screencast の透明部分は、Microsoft Edge のアドレスバー、Windows 10 タスクバー、Windows 10 キーボードなどのデバイスインターフェイスを表します。  
*   スクリーンキャストはフレームレートに悪影響を与えます。  スクロールまたはアニメーションの計測中に screencasting を無効にすると、ページのパフォーマンスがより正確に表示されます。  
*   ホストデバイスの画面がロックされている場合、screencast のコンテンツは表示されなくなります。  [ホストデバイス] 画面のロックを解除して、screencast を自動的に再開します。  

## 既知の問題  

Windows 10 バージョン1903では、[**要素**] パネルの [**イベントリスナー** ] ウィンドウが空白になっています。  Windows 10 バージョン1903へのサービス更新プログラムで、[**イベントリスナー** ] ウィンドウを修正します。  

Windows 10 バージョン1903では、**アプリケーション**パネルの [ **cookie** ] ウィンドウが空白になっています。  Windows 10 バージョン1903へのサービス更新プログラムでは、[ **cookie** ] ウィンドウが修正されます。  

[**監査**] パネル、[ **3d ビュー** ] パネル、[**設定**] のエミュレートされた**デバイス**セクション、[**要素**] パネルの [**アクセシビリティツリー** ] ウィンドウは、現時点では期待どおりに動作していません。  これらのツールは、Microsoft Edge の今後の更新プログラムで修正されます。  

リモートデバッグの場合、ファイルエクスプローラーは、[**ソース**] パネルまたは [**セキュリティ**] パネルの devtools から起動されません。  これらのツールは、Microsoft Edge の今後の更新プログラムで修正されます。  
