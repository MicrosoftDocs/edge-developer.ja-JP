---
description: エミュレーションパネルを使用して、さまざまなブラウザープロファイル、画面サイズと解像度、GPS 位置座標をテストする
title: DevTools-エミュレーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/04/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、デバイスエミュレーション、応答性の高いデザイン、位置情報、解像度
ms.custom: seodec18
ms.openlocfilehash: 6eaa8d79cfd64473dcc52beff5659b39054e2a48
ms.sourcegitcommit: 912609aa49864e3363aaa3b245ff2aa4bec3fc3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104848"
---
# <span data-ttu-id="8caf8-104">エミュレーション</span><span class="sxs-lookup"><span data-stu-id="8caf8-104">Emulation</span></span>  

> [!NOTE]
> <span data-ttu-id="8caf8-105">新しい Microsoft Edge は Chromium を使って構築され、バージョン75から始まります。</span><span class="sxs-lookup"><span data-stu-id="8caf8-105">The new Microsoft Edge is built using Chromium, and starts at version 75.</span></span>  <span data-ttu-id="8caf8-106">詳細については、 [新しい Microsoft edge をダウンロード][MicrosoftNewEdge]して、新しい [Microsoft edge (Chromium) 開発者ツール][DevtoolsGuideChromium]をお試しください。</span><span class="sxs-lookup"><span data-stu-id="8caf8-106">For more information, [download the new Microsoft Edge][MicrosoftNewEdge], and try out the new [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromium].</span></span>  
> 
> <span data-ttu-id="8caf8-107">新しい DevTools でさまざまなデバイス、ブラウザー、画面サイズ、および解像度をエミュレートするには、「 [Microsoft Edge \ (Chromium) DevTools でモバイルデバイスをエミュレートする」][DevtoolsGuideChromiumDeviceMode]に移動します。</span><span class="sxs-lookup"><span data-stu-id="8caf8-107">To emulate different devices, browsers, screen sizes, and resolutions in the new DevTools, navigate to [Emulate Mobile Devices in Microsoft Edge \(Chromium\) DevTools][DevtoolsGuideChromiumDeviceMode].</span></span>  

<span data-ttu-id="8caf8-108">**エミュレーション**パネルでは、次のアクティビティを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8caf8-108">The **Emulation** panel helps with the following activities.</span></span>    

*   <span data-ttu-id="8caf8-109">さまざまな[デバイスプロファイル](#device)、[ブラウザー](#browser-profile)、および[画面サイズと解像度](#display)をシミュレートする</span><span class="sxs-lookup"><span data-stu-id="8caf8-109">Simulate various [device profiles](#device), [browsers](#browser-profile), and [screen sizes and resolutions](#display)</span></span>  
*   <span data-ttu-id="8caf8-110">さまざまな[位置情報の設定と座標の](#geolocation)テスト</span><span class="sxs-lookup"><span data-stu-id="8caf8-110">Test different [geolocation settings and coordinates](#geolocation)</span></span>  

:::image type="complex" source="./media/emulation.png" alt-text="Microsoft Edge DevTools エミュレーションパネル" lightbox="./media/emulation.png":::
   <span data-ttu-id="8caf8-112">Microsoft Edge DevTools **エミュレーション** パネル</span><span class="sxs-lookup"><span data-stu-id="8caf8-112">The Microsoft Edge DevTools **Emulation** panel</span></span>  
:::image-end:::  

1.  <span data-ttu-id="8caf8-113">[ **エミュレーションの設定を保持** ] ボタンを使うと、開発者ツールを終了してもう一度開いた場合でも、既定のデスクトップエミュレーション設定で行ったすべての変更が保存されます。</span><span class="sxs-lookup"><span data-stu-id="8caf8-113">The **Persist Emulation settings** button saves any changes you made from the default desktop emulation settings, even when you close and reopen the DevTools.</span></span>  

1.  <span data-ttu-id="8caf8-114">[ **エミュレーション設定のリセット** ] ボタンをクリックすると、エミュレーションの設定が既定のデスクトップブラウザープロファイルと Microsoft Edge ユーザーエージェント文字列にリセットされ、GPS がオフになります。</span><span class="sxs-lookup"><span data-stu-id="8caf8-114">The **Reset Emulation settings** button resets your emulation settings back to the default Desktop browser profile and Microsoft Edge user agent string with GPS turned off.</span></span>  

1.  <span data-ttu-id="8caf8-115">これらのオプションのいずれかを既定値から変更した場合、[ **エミュレーション** ] タブには、ブラウザーの動作の一部がエミュレートされていることを示す情報アラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8caf8-115">When any of these options are changed from the default, the **Emulation** tab displays an informational alert to indicate that some aspect of the behavior of your browser is being emulated.</span></span>  

## <span data-ttu-id="8caf8-116">デバイス</span><span class="sxs-lookup"><span data-stu-id="8caf8-116">Device</span></span>  

<span data-ttu-id="8caf8-117">他のエミュレーションオプションを自動的に構成する、または独自の **カスタム** 構成を指定する、Windows デバイスプロファイルの事前設定リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="8caf8-117">Pick from a preset list of Windows device profiles that automatically configure the other emulation options or specify your own **Custom** configuration.</span></span>  <span data-ttu-id="8caf8-118">**既定**の状態に戻すには、すべてのエミュレーションツールをリセットします。</span><span class="sxs-lookup"><span data-stu-id="8caf8-118">Switch back to **Default** to reset all the emulation tools.</span></span>  

## <span data-ttu-id="8caf8-119">モード</span><span class="sxs-lookup"><span data-stu-id="8caf8-119">Mode</span></span>  

### <span data-ttu-id="8caf8-120">ブラウザプロファイル</span><span class="sxs-lookup"><span data-stu-id="8caf8-120">Browser profile</span></span>  

<span data-ttu-id="8caf8-121">Windows Phone デバイスで実行されているページをシミュレートする簡単な方法は、 **ブラウザーのプロファイル** 設定を **windows phone**に変更することです。</span><span class="sxs-lookup"><span data-stu-id="8caf8-121">A quick way to simulate your page running on a Windows Phone device is to change the **Browser profile** setting to **Windows Phone**.</span></span>  

#### <span data-ttu-id="8caf8-122">ユーザーエージェント文字列</span><span class="sxs-lookup"><span data-stu-id="8caf8-122">User agent string</span></span>  

<span data-ttu-id="8caf8-123">Microsoft Edge でのみ発生するエラーをデバッグするには、最初の手順として、ユーザーエージェント文字列を他のブラウザーに近いものにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8caf8-123">Modifying your user agent string to mimic another browser is a good first step in debugging errors that are only happening in Microsoft Edge.</span></span>  

<span data-ttu-id="8caf8-124">スクリプトは、ユーザーエージェント文字列を使って、使用されているブラウザーを検出します。</span><span class="sxs-lookup"><span data-stu-id="8caf8-124">Scripts use the user agent string to detect which browser is used.</span></span>  <span data-ttu-id="8caf8-125">スクリプトは、フロントエンド、バックエンド、フロントエンド、バックエンドのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="8caf8-125">Script may be front-end, back-end, or front-end and back-end.</span></span>  <span data-ttu-id="8caf8-126">コードではブラウザーの検出を使用していませんが、コードはサードパーティの JavaScript ライブラリまたはサーバー側スクリプトから継承している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8caf8-126">Although your code does not use browser detection, your code may inherit it from a third-party JavaScript library or server-side script.</span></span>  

<span data-ttu-id="8caf8-127">ブラウザーの検出に関する問題は、ブラウザーの機能について仮定を使って、web ページの機能をスケールバック (または変更) できるという点です。</span><span class="sxs-lookup"><span data-stu-id="8caf8-127">The problem with browser detection is that you may scale-back \(or change\) features in your webpage using assumptions about browser capabilities.</span></span> <span data-ttu-id="8caf8-128">代わりに、機能検出を使用してブラウザーの機能を検出することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="8caf8-128">Instead, you should consider using feature detection to detect the capabilities of your browser.</span></span>  <span data-ttu-id="8caf8-129">以下のいずれかの状況が原因で、予期しない動作が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="8caf8-129">Unexpected behavior may occur because of one of the following situations.</span></span>  

*   <span data-ttu-id="8caf8-130">Windows Internet Explorer 8 のコードは、Microsoft Edge では動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8caf8-130">Code targeted at Windows Internet Explorer 8 may run differently in Microsoft Edge.</span></span>  
*   <span data-ttu-id="8caf8-131">開発者によって想定されているため、ブラウザーでサポートする必要がある機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="8caf8-131">A feature that your browser should support is disabled, because of an assumption made by the developer.</span></span>  

<span data-ttu-id="8caf8-132">ユーザーエージェント文字列を変更すると問題が解消される場合は、ブラウザーの検出が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8caf8-132">If changing your user agent string clears up the problem, browser detection is likely culprit.</span></span>  

## <span data-ttu-id="8caf8-133">ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="8caf8-133">Display</span></span>  

<span data-ttu-id="8caf8-134">さまざまな画面サイズと解像度でサイトをプレビューするには、[エミュレーション] を表示します。</span><span class="sxs-lookup"><span data-stu-id="8caf8-134">Display emulation to preview your site on different screen sizes and resolutions.</span></span>  

*   <span data-ttu-id="8caf8-135">従来のデスクトップモニター</span><span class="sxs-lookup"><span data-stu-id="8caf8-135">conventional desktop monitors</span></span>  
*   <span data-ttu-id="8caf8-136">モバイルの小型画面</span><span class="sxs-lookup"><span data-stu-id="8caf8-136">smaller mobile screens</span></span>  
*   <span data-ttu-id="8caf8-137">より新しい高解像度ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="8caf8-137">newer high-resolution displays</span></span>  

<span data-ttu-id="8caf8-138">エミュレーションは、エミュレートされる画面の物理サイズと一致するように調整されます。</span><span class="sxs-lookup"><span data-stu-id="8caf8-138">Emulations are adapted to try to match the physical dimensions of the screens being emulated.</span></span>  <span data-ttu-id="8caf8-139">エミュレートされたピクセルは、圧縮または展開されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8caf8-139">Emulated pixels may appear compressed or expanded.</span></span> <span data-ttu-id="8caf8-140">ピクセルで正確な HTML 要素の配置をテストする必要がある場合は、エミュレーションは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="8caf8-140">Emulation is not recommended if you need to test pixel-perfect positioning of HTML elements.</span></span>  <span data-ttu-id="8caf8-141">ただし、エミュレーションは、応答性の高いデザインをテストし、要素の配置の大きな問題を特定するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="8caf8-141">Emulation is, however, good for testing responsive designs and identifying larger element positioning issues.</span></span>  

### <span data-ttu-id="8caf8-142">Orientation</span><span class="sxs-lookup"><span data-stu-id="8caf8-142">Orientation</span></span>  

<span data-ttu-id="8caf8-143">[ **横** ] または [ **縦** ] モードから選択します。</span><span class="sxs-lookup"><span data-stu-id="8caf8-143">Choose from **Landscape** or **Portrait** mode.</span></span>  

### <span data-ttu-id="8caf8-144">解決方法</span><span class="sxs-lookup"><span data-stu-id="8caf8-144">Resolution</span></span>  

<span data-ttu-id="8caf8-145">一般的なデバイスの解像度の事前設定リストから選ぶか、独自の **カスタム** 構成を指定します。 最大80インチおよび 3820 x 2160 の解像度がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8caf8-145">Choose from a preset list of popular device resolutions, or specify your own **Custom** config.  Resolutions of up to 80 inches and 3820 x 2160 are supported.</span></span>  

## <span data-ttu-id="8caf8-146">位置情報</span><span class="sxs-lookup"><span data-stu-id="8caf8-146">Geolocation</span></span>  

<span data-ttu-id="8caf8-147">Web サイトが位置情報に基づくサービスを提供するために位置情報 [API][MdnGeolocationUsing] を使用している場合は、デスクトップの便利なアクティビティを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8caf8-147">If your website uses the [Geolocation API][MdnGeolocationUsing] to provide location-based services, the following activities are available from the convenience of your desktop.</span></span>  

*   <span data-ttu-id="8caf8-148">さまざまな GPS 座標を簡単にテストする</span><span class="sxs-lookup"><span data-stu-id="8caf8-148">easily test different GPS coordinates</span></span>  
*   <span data-ttu-id="8caf8-149">さまざまなセンサーの状態を簡単にテストする</span><span class="sxs-lookup"><span data-stu-id="8caf8-149">easily test different sensor states</span></span>  

<span data-ttu-id="8caf8-150">設定は、位置情報をサポートするデバイス上の実際の GPS 座標とセンサーの状態を上書きします。</span><span class="sxs-lookup"><span data-stu-id="8caf8-150">The settings override any actual GPS coordinates and the sensor state on devices that support geolocation.</span></span>  

<span data-ttu-id="8caf8-151">デバイスの場所を使用する前に、web サイトでユーザーに要求し、アクセス許可を与えられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8caf8-151">Your website must request and be granted permission from a user before using the device location.</span></span>  <span data-ttu-id="8caf8-152">Microsoft Edge の [ **設定** ] パネルで、サイトの動作を確認し、場所の権限は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8caf8-152">Test how your site behaves with and without location permissions from the Microsoft Edge **Settings** panel.</span></span>  

<span data-ttu-id="8caf8-153">**...** > **設定**  > **詳細設定**  >  を表示する**Web サイトの権限**  > **管理**</span><span class="sxs-lookup"><span data-stu-id="8caf8-153">**...** > **Settings** > **View advanced settings** > **Website permissions** > **Manage**</span></span>  

:::image type="complex" source="./media/settings_manage_permissions.png" alt-text="Microsoft Edge DevTools エミュレーションパネル" lightbox="./media/settings_manage_permissions.png":::
   <span data-ttu-id="8caf8-155">Microsoft Edge の [ **設定** ] パネルから web サイトの権限を管理する</span><span class="sxs-lookup"><span data-stu-id="8caf8-155">Manage website permissions from the Microsoft Edge **Settings** panel</span></span>  
:::image-end:::  

## <span data-ttu-id="8caf8-156">ショートカット</span><span class="sxs-lookup"><span data-stu-id="8caf8-156">Shortcuts</span></span>

| <span data-ttu-id="8caf8-157">操作</span><span class="sxs-lookup"><span data-stu-id="8caf8-157">Action</span></span>  | <span data-ttu-id="8caf8-158">ショートカット</span><span class="sxs-lookup"><span data-stu-id="8caf8-158">Shortcut</span></span>  |  
|:--- |:--- |  
| <span data-ttu-id="8caf8-159">エミュレーション設定のリセット</span><span class="sxs-lookup"><span data-stu-id="8caf8-159">Reset Emulation settings</span></span> | `Ctrl`+`Shift`+`L` |  

<!-- links -->  


[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsGuideChromiumDeviceMode]: /microsoft-edge/devtools-guide-chromium/device-mode "Microsoft Edge DevTools でモバイルデバイスをエミュレートする |Microsoft ドキュメント"  

[MicrosoftNewEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MdnGeolocationUsing]: https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation "位置情報 API |MDN"  