---
description: リモート デバッグ Windows 10 デバイスの使用を開始する
title: Windows 10 デバイスのリモート デバッグの開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/23/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, リモート, デバッグ, Windows 10, windows, device portal
ms.openlocfilehash: e3f60f07ba96aaed8cd9d7348eee1b0a846faecf
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519265"
---
# <a name="get-started-with-remote-debugging-windows-10-devices"></a>Windows 10 デバイスのリモート デバッグの開始  

Windows または macOS コンピューターから Windows 10 デバイスでライブ コンテンツをリモート デバッグします。  このチュートリアルでは、次のタスクについて説明します。  

*   リモート デバッグ用に Windows 10 デバイスをセットアップし、開発マシンから Windows 10 デバイスに接続します。  
*   開発マシンから Windows 10 デバイスのライブ コンテンツを検査およびデバッグします。  
*   Windows 10 デバイスから開発マシン上の DevTools インスタンスにコンテンツをスクリーンキャストします。  
    
## <a name="step-1-set-up-the-host-debuggee-machine"></a>手順 1: ホストをセットアップする (デバッグ先コンピューター)  

ホストまたはデバッグ先のコンピューターは、デバッグする Windows 10 デバイスです。  物理的にアクセスするのが困難なリモート デバイスや、キーボードとマウスの周辺機器がインストールされていない場合、そのデバイスで Microsoft Edge DevTools とやり取りするのが難しい場合があります。  ホスト \(debuggee\) コンピューターをセットアップするには、次のアクションを実行する必要があります。  

*   Microsoft Edge ( [クロム) のインストールと構成][MicrosoftEdgeMain]  
*   Microsoft Store から Microsoft Edge 用リモート ツール [(ベータ)][MicrosoftStoreApps9p6cmfv44zlt] を [インストールする][MicrosoftStoreAppsWindows]  
*   開発者 [モードをアクティブ化][WindowsAppsGetStartedEnableYourDeviceForDevelopment] し、 [デバイス ポータルを有効にする][WindowsUwpDebugTestPerfDevicePortal]  
    
### <a name="install-and-configure-microsoft-edge-chromium"></a>Microsoft Edge (クロム) のインストールと構成  

まだインストールしていない場合は、このページから Microsoft Edge \(Chromium\) を [インストールします][MicrosoftEdgeMain]。  ホスト \(debuggee\) コンピューターでプレインストールバージョンの Microsoft Edge を使用している場合は、Microsoft Edge \(Chromium\) ではなく Microsoft Edge \(EdgeHTML\) がインストールされていることを確認します。  簡単に確認するには、ブラウザーに読み込み、バージョン番号が 75 以上である必要 `edge://settings/help` があります。  

次に `edge://flags` 、Microsoft Edge \(Chromium\) に移動します。  [ **検索フラグ]** に **、「Windows デバイス ポータルでリモート デバッグを有効にする」と入力します**。  このフラグを [有効] **に設定します**。  次に、[再起動] **ボタンを** クリックして Microsoft Edge \(Chromium\) を再起動します。  

:::image type="complex" source="../media/remote-debugging-windows-media-edge-flags-on-host.msft.png" alt-text="[Windows デバイス ポータル経由でリモート デバッグを有効にする] フラグを [有効] に設定する" lightbox="../media/remote-debugging-windows-media-edge-flags-on-host.msft.png":::
   **[Windows デバイス ポータル経由でリモート デバッグを有効にする**] フラグを [有効] に**設定する**  
:::image-end:::  

### <a name="install-the-remote-tools-for-microsoft-edge-beta"></a>Microsoft Edge 用リモート ツールのインストール (ベータ)  

Microsoft Store [から Microsoft Edge 用リモート ツール (ベータ)][MicrosoftStoreApps9p6cmfv44zlt] を [インストールします][MicrosoftStoreAppsWindows]。  

> [!NOTE]
> Windows **** 10 バージョン 1809 以前の場合、リモート ツール for Microsoft Edge (ベータ) の[[Get]][MicrosoftStoreApps9p6cmfv44zlt]ボタンが無効になる場合があります。  ホスト \(debuggee\) コンピューターをセットアップするには、Windows 10 バージョン 1903 以降を実行している必要があります。  ホスト \(debuggee\) コンピューターを更新して、Microsoft Edge 用リモート ツール [(Beta) を取得します][MicrosoftStoreApps9p6cmfv44zlt]。  

:::image type="complex" source="../media/remote-debugging-windows-media-remote-tools-in-store.msft.png" alt-text="Microsoft Store の Microsoft Edge 用リモート ツール \(Beta\)" lightbox="../media/remote-debugging-windows-media-remote-tools-in-store.msft.png":::
   Microsoft Store[の Microsoft Edge 用リモート ツール (][MicrosoftStoreApps9p6cmfv44zlt][ベータ][MicrosoftStoreAppsWindows])  
:::image-end:::  

Microsoft [Edge のリモート ツール (Beta)][MicrosoftStoreApps9p6cmfv44zlt] を起動し、メッセージが表示されたら、アプリの [アクセス許可] ダイアログを受け入れる。  これで、Microsoft Edge 用のリモート ツール [(Beta)][MicrosoftStoreApps9p6cmfv44zlt] を閉じ、将来のリモート デバッグ セッション用に開く必要がなくなっています。

### <a name="activate-developer-mode-and-enable-device-portal"></a>開発者モードをアクティブ化し、デバイス ポータルを有効にする  

WiFi ネットワークを使用している場合は、ネットワークが [ドメイン] または [プライベート] のいずれかとして**マークされている必要****があります**。  Windows セキュリティ アプリを開き、**ファイアウォール** **&** ネットワーク保護を選択し、ネットワークがドメイン ネットワークまたはプライベート ネットワークとして一覧表示される**** のを確認することで、状態を**確認**できます。  

[パブリック] と表示**** されている場合は、[**** 設定] ネットワーク & [インターネット Wi-Fi] に移動し、ネットワーク上で選択し、[ネットワーク プロファイル] ボタンを [プライベート]  >  ****  >  **** に切り替**わります**。 ****  

次に、設定アプリ **を開** きます。  [ **設定の検索]** で、設定 `Developer settings` を入力して選択します。  開発者モードを **切り替えます**。  [ローカル エリア ネットワーク**** 接続でリモート診断を有効にする] を [オン] に設定して、デバイス ポータル**を**有効**にできます**。  オプションで認証を有効に**** し、クライアント \(debugger\) デバイスがこのデバイスに接続するための正しい資格情報を提供する必要があります。  

> [!NOTE]
> ローカル **エリア ネットワーク接続でリモート診断を有効にする場合。** 以前に有効にした場合は、デバイス ポータルで Microsoft Edge**** 用リモート ツール (Beta) を操作するには、無効にし、もう一度オン[にする必要があります][MicrosoftStoreApps9p6cmfv44zlt]。  [設定]**に [** 開発者向け****]**** セクションが表示されない場合は、デバイス ポータルが既に有効になっている可能性があります。代わりに Windows 10 デバイスを再起動してみてください。

:::image type="complex" source="../media/remote-debugging-windows-media-host-settings.msft.png" alt-text="開発者モードとデバイス ポータルが構成された設定アプリ" lightbox="../media/remote-debugging-windows-media-host-settings.msft.png":::
   開発者**モードと**デバイス**ポータルが**構成**された設定アプリ**  
:::image-end:::  

[接続] の下に表示されるコンピューターの IP アドレスと接続**ポートに注意してください。**  次の図の IP アドレスは、 `192.168.86.78` 接続ポートです `50080` 。  

:::image type="complex" source="../media/remote-debugging-windows-media-host-settings-ip-address.msft.png" alt-text="[設定] で IP アドレスと接続ポートをメモする" lightbox="../media/remote-debugging-windows-media-host-settings-ip-address.msft.png":::
   [設定] で IP アドレスと接続ポートをメモ **する**  
:::image-end:::  

クライアント \(debugger\) デバイスの情報を次のセクションに [入力します](#step-2-set-up-the-client-debugger-machine)。  クライアント \(debugger\) コンピューターからデバッグするホスト \(debugee\) コンピューターの Microsoft Edge とプログレッシブ Web アプリ [(PWA)][DevtoolsProgressiveWebApps] でタブを開きます。  

## <a name="step-2-set-up-the-client-debugger-machine"></a>手順 2: クライアントをセットアップする (デバッガー コンピューター)  

クライアントまたはデバッガー コンピューターは、デバッグするデバイスです。  このデバイスは、毎日の開発マシンか、自宅で作業するときに PC または MacBook にすることもできます。  

クライアント \(debugger\) マシンをセットアップするには、まだインストールしていない場合は、このページから[][MicrosoftEdgeMain]Microsoft Edge \(Chromium\) をインストールします。  ホスト \(debuggee\) コンピューターでプレインストールバージョンの Microsoft Edge を使用している場合は、Microsoft Edge \(Chromium\) ではなく Microsoft Edge \(EdgeHTML\) がインストールされていることを確認します。  簡単に確認するには、ブラウザーに読み込み、バージョン番号が 75 以上である必要 `edge://settings/help` があります。  

次に `edge://flags` 、Microsoft Edge \(Chromium\) に移動します。  [**検索フラグ]** に、「リモート Windows デバイスのデバッグを有効にする」と入力**edge://inspect。**  このフラグを [有効] **に設定します**。  次に、[再起動] **ボタンを** クリックして Microsoft Edge \(Chromium\) を再起動します。  

:::image type="complex" source="../media/remote-debugging-windows-media-edge-flags-on-client.msft.png" alt-text="[リモート Windows デバイスのデバッグを有効にする] フラグを [有効 edge://inspect する] に設定する" lightbox="../media/remote-debugging-windows-media-edge-flags-on-client.msft.png":::
   [リモート **Windows デバイスのデバッグを有効にする** ] フラグを [有効 edge://inspect する] に **設定する**  
:::image-end:::  

次に `edge://inspect` 、Microsoft Edge \(Chromium\) のページに移動します。  既定では、[デバイス] セクションに **アクセスする必要** があります。  [ **リモート Windows デバイスへの**接続] で、次のパターンに従って、ホスト \(debuggee\) コンピューターの IP アドレスと接続ポートをテキスト ボックスに入力します。http:// `IP address` : `connection port` 。  [デバイスに **接続] を選択します**。  

:::image type="complex" source="../media/remote-debugging-windows-media-edge-inspect.msft.png" alt-text="クライアント edge://inspect ページ" lightbox="../media/remote-debugging-windows-media-edge-inspect.msft.png":::
   クライアント `edge://inspect` のページ  
:::image-end:::  

ホスト \(debuggee\) コンピューターの認証を設定すると、クライアント \(debugger\)**** コンピューター**** のユーザー名とパスワードを入力して正常に接続するように求められます。  

### <a name="using-https-instead-of-http"></a>http の代わりに https を使用する  

代わりに使用してホスト \(debuggee\) コンピューターに接続する場合は、クライアント `https` `http` \(debugger\) コンピューターの Microsoft Edge に移動する `http://IP address:50080/config/rootcertificate` 必要があります。  これにより、という名前のセキュリティ証明書が自動的にダウンロードされます `rootcertificate.cer` 。

を選択します `rootcertificate.cer` 。  これにより [、Windows 証明書マネージャー ツールが開きます][DotnetFrameworkWcfFeatureDetailsHowToViewCertificatesWithMmcSnapInViewCertificatesWithCertificateManagerTool]。

[ **証明書のインストール...] を選択し**、[現在の **ユーザー** ] がオンになっていることを確認し、[次へ] を **選択します**。  次に、[**すべての証明書を次のストアに配置する] を選択し、[****参照]を選択します**。 [信頼された**ルート証明機関] ストアを選択し****、[OK] を選択します**。  [次 **へ] を** 選択し、[完了] **を選択します**。  メッセージが表示されたら、この証明書を信頼されたルート証明機関ストア **にインストールする必要があります** 。

ここで、ページを使用してクライアント \(debugger\) コンピューターからホスト \(debuggee\) コンピューターに接続する場合は、別の値 `edge://inspect` を使用する必要 `connection port` があります。  既定では、デスクトップ Windows の場合、デバイス ポータルは `50080` for として使用 `connection port` されます `http` 。  [ `https` デバイス ポータル] では、次 `50043` のパターンに従って使用します。https://: `IP address` `50043` をページに表示 `edge://inspect` します。  [デバイス ポータルで使用される既定のポートの詳細については、以下を参照してください][WindowsUwpDebugTestPerfDevicePortalSetup]。  

> [!NOTE]
> 既定のポートは is および default port is ですが、デバイス上の既存のポート クレームとの競合を防止するために、一時的な範囲 `http` `50080` `https` `50043` \(\>50,000\) のデスクトップ クレーム ポートの Device Portal と必ずしも同じではありません。  詳細については、Windows デスクトップの  [デバイス ポータルの][WindowsUwpDebugTestPerfDevicePortalDesktopRegistryBasedConfigurationForDevicePortal] [ポート設定] セクションに移動します。  

## <a name="step-3-debug-content-on-the-host-from-the-client"></a>手順 3: クライアントからホスト上のコンテンツをデバッグする  

クライアント \(debugger\) コンピューターがホスト \(debuggee\) コンピューターに正常に接続すると、クライアントのページに Microsoft Edge のタブの一覧とホスト上の開いている PWA が表示されます。 `edge://inspect`  

:::image type="complex" source="../media/remote-debugging-windows-media-edge-inspect-connected.msft.png" alt-text="クライアント edge://inspect ページには、ホスト上の Microsoft Edge と PWA のタブが表示されます。" lightbox="../media/remote-debugging-windows-media-edge-inspect-connected.msft.png":::
   クライアント `edge://inspect` のページには、ホスト上の Microsoft Edge と PWA のタブが表示されます。  
:::image-end:::  

デバッグするコンテンツを決定し、[検査] を **選択します**。  Microsoft Edge DevTools は新しいタブで開き、ホスト \(debuggee\) コンピューターからクライアント \(debugger\) コンピューターにコンテンツをスクリーンキャストします。  これで、ホスト上で実行されているコンテンツに対して、クライアントで Microsoft Edge DevTools のフル パワーを使用できます。  Microsoft Edge DevTools の使い方の詳細については、こちらを参照 [してください][DevtoolsIndex]。  

:::image type="complex" source="../media/remote-debugging-windows-media-devtools-client.msft.png" alt-text="ホスト上の Microsoft Edge のタブをデバッグするクライアントの Microsoft Edge DevTools" lightbox="../media/remote-debugging-windows-media-devtools-client.msft.png":::
   ホスト [上の Microsoft Edge][DevtoolsIndex] のタブをデバッグするクライアントの Microsoft Edge DevTools  
:::image-end:::  

### <a name="inspect-elements"></a>要素を検査する  

たとえば、要素の検査を試してみてください。  クライアント上の **DevTools** インスタンスの Elements ツールに移動し、要素をホバーしてホスト デバイスのビューポートで強調表示します。  

ホスト デバイス画面で要素をタップして、[要素] **ツールで選択** することもできます。  クライアント **の DevTools** インスタンスで [要素の選択] を選択し、ホスト デバイス画面で要素をタップします。  

> [!NOTE]
> **[要素の** 選択] は最初のタッチ後に無効になっているので、この機能を使用する度にもう一度有効にする必要があります。  

> [!IMPORTANT]
> Windows 10**バージョン**1903 では、[要素] ツールの [イベント リスナー] ウィンドウが空白になります。 ****  これは既知の問題であり、チームはサービス更新プログラムの****[イベント リスナー] ウィンドウを Windows 10 バージョン 1903 に修正する予定です。  

## <a name="step-4-screencast-your-host-screen-to-your-client-device"></a>手順 4: ホスト画面をクライアント デバイスにスクリーンキャストする  

既定では、クライアントの DevTools インスタンスにスクリーンキャストが有効になっているので、クライアント デバイスの DevTools インスタンスのホスト デバイス上のコンテンツを表示できます。  [ **画面キャストの切り替え** ] を選択して、この機能をオフまたはオンにします。  

:::image type="complex" source="../media/remote-debugging-windows-media-toggle-screencast.msft.png" alt-text="クライアントの Microsoft Edge DevTools の [画面キャストの切り替え] ボタン" lightbox="../media/remote-debugging-windows-media-toggle-screencast.msft.png":::
   クライアント **の Microsoft Edge** DevTools の [画面キャストの切り替え] ボタン  
:::image-end:::  

スクリーンキャストを複数の方法で操作できます。  
*   選択はタップに変換され、デバイスで適切なタッチ イベントが発生します。  
*   コンピューター上のキーストロークがデバイスに送信されます。  
*   ピンチ ジェスチャをシミュレートするには、ドラッグ中 `Shift` に保持します。  
*   スクロールするには、トラックパッドまたはマウス ホイールを使用するか、マウス ポインターを使用します。  

スクリーンキャストに関する注意事項:  
*   スクリーンキャストは、ページコンテンツのみを表示します。  スクリーン キャストの透明な部分は、Microsoft Edge アドレス バー、Windows 10 タスク バー、Windows 10 キーボードなどのデバイス インターフェイスを表します。  
*   スクリーンキャストはフレーム レートに悪影響を及ぼします。  スクロールやアニメーションの測定中にスクリーンキャストを無効にして、ページのパフォーマンスをより正確に把握します。  
*   ホスト デバイスの画面がロックされている場合、スクリーン キャストのコンテンツは消えます。  ホスト デバイスの画面のロックを解除して、スクリーンキャストを自動的に再開します。  

## <a name="known-issues"></a>既知の問題  

Windows 10**バージョン**1903 では、[要素] ツールの [イベント リスナー] ウィンドウが空白になります。 ****  チームは、サービス更新プログラムの **[イベント** リスナー] ウィンドウを Windows 10 バージョン 1903 に修正する予定です。  

Windows **** 10**** バージョン 1903 の [アプリケーション] パネルの [Cookie] ウィンドウは空白です。  チームは、サービス更新プログラム **の Cookie** ウィンドウを Windows 10 バージョン 1903 に修正する予定です。  

[**監査]** ツール **、3D ビュー**ツール、設定の [**** エミュレートされたデバイス]**** セクション、および [**** 要素] ツールの [アクセシビリティ] ツリー ウィンドウは、現在期待通り動作していません。 ****  チームは、Microsoft Edge の今後の更新プログラムで、リストされているツールを修正する予定です。  

リモート デバッグ時に、エクスプローラーは Sources ツール**** の DevTools から、または**セキュリティ**パネルでは起動されません。  チームは、Microsoft Edge の今後の更新プログラムでツールを修正する予定です。  

<!-- links -->

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツールの概要 | Microsoft Docs"  
[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "プログレッシブ Web アプリのデバッグ |Microsoft Docs"  

[DotnetFrameworkWcfFeatureDetailsHowToViewCertificatesWithMmcSnapInViewCertificatesWithCertificateManagerTool]: /dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in#view-certificates-with-the-certificate-manager-tool "[証明書マネージャー] ツールを使用して証明書を表示する - [方法] MMC スナップイン ツールを使用して証明書を表示|Microsoft Docs"  

[WindowsAppsGetStartedEnableYourDeviceForDevelopment]: /windows/apps/get-started/enable-your-device-for-development "デバイスを開発用に有効|Microsoft Docs"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows デバイス ポータルの概要|Microsoft Docs"  
[WindowsUwpDebugTestPerfDevicePortalSetup]: /windows/uwp/debug-test-perf/device-portal#setup "セットアップ - Windows デバイス ポータルの概要|Microsoft Docs"  
[WindowsUwpDebugTestPerfDevicePortalDesktopRegistryBasedConfigurationForDevicePortal]: /windows/uwp/debug-test-perf/device-portal-desktop#registry-based-configuration-for-device-portal "デバイス ポータルのレジストリ ベースの構成 - Windows デスクトップ アプリケーションのデバイス ポータル|Microsoft Docs"  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MicrosoftStoreAppsWindows]: https://www.microsoft.com/store/apps/windows "Windows Apps |Microsoft Store"  

[MicrosoftStoreApps9p6cmfv44zlt]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge のリモート ツール (ベータ) |Microsoft Store"  
