---
description: エミュレーション パネルを使用して、さまざまなブラウザー プロファイル、画面サイズと解像度、GPS 位置座標をテストする
title: DevTools - エミュレーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, デバイス エミュレーション, レスポンシブ デザイン, 位置情報, 解像度
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: af740472f22a8b322c03cb672a3da909ef195fac
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234587"
---
# <span data-ttu-id="7e3dc-104">エミュレーション</span><span class="sxs-lookup"><span data-stu-id="7e3dc-104">Emulation</span></span>  

> [!NOTE]
> <span data-ttu-id="7e3dc-105">新しい Microsoft Edge は Chromium を使用して構築され、バージョン 75 から始まります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-105">The new Microsoft Edge is built using Chromium, and starts at version 75.</span></span>  <span data-ttu-id="7e3dc-106">詳細については、新 [しい Microsoft Edge をダウンロード][MicrosoftNewEdge]して、新しい [Microsoft Edge (Chromium) 開発者ツールを試してください][DevtoolsGuideChromium]。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-106">For more information, [download the new Microsoft Edge][MicrosoftNewEdge], and try out the new [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromium].</span></span>  
> 
> <span data-ttu-id="7e3dc-107">新しい DevTools でさまざまなデバイス、ブラウザー、画面サイズ、解像度をエミュレートするには [、Microsoft Edge \(Chromium\) DevTools][DevtoolsGuideChromiumDeviceMode]でモバイル デバイスをエミュレートするに移動します。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-107">To emulate different devices, browsers, screen sizes, and resolutions in the new DevTools, navigate to [Emulate Mobile Devices in Microsoft Edge \(Chromium\) DevTools][DevtoolsGuideChromiumDeviceMode].</span></span>  

<span data-ttu-id="7e3dc-108">エミュレーション **パネルは** 、次のアクティビティに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-108">The **Emulation** panel helps with the following activities.</span></span>    

*   <span data-ttu-id="7e3dc-109">さまざまなデバイス [プロファイル、ブラウザー](#device) [、画面サイズ](#browser-profile)と解像度 [をシミュレートする](#display)</span><span class="sxs-lookup"><span data-stu-id="7e3dc-109">Simulate various [device profiles](#device), [browsers](#browser-profile), and [screen sizes and resolutions](#display)</span></span>  
*   <span data-ttu-id="7e3dc-110">さまざまな地理 [位置情報の設定と座標をテストする](#geolocation)</span><span class="sxs-lookup"><span data-stu-id="7e3dc-110">Test different [geolocation settings and coordinates](#geolocation)</span></span>  

:::image type="complex" source="./media/emulation.png" alt-text="Microsoft Edge DevTools エミュレーション パネル" lightbox="./media/emulation.png":::
   <span data-ttu-id="7e3dc-112">Microsoft Edge DevTools **エミュレーション** パネル</span><span class="sxs-lookup"><span data-stu-id="7e3dc-112">The Microsoft Edge DevTools **Emulation** panel</span></span>  
:::image-end:::  

1.  <span data-ttu-id="7e3dc-113">[Persist **Emulation settings] ボタン** は、DevTools を閉じて再度開いた場合でも、既定のデスクトップ エミュレーション設定から行った変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-113">The **Persist Emulation settings** button saves any changes you made from the default desktop emulation settings, even when you close and reopen the DevTools.</span></span>  

1.  <span data-ttu-id="7e3dc-114">エミュレーション **設定のリセット** ボタンは、エミュレーション設定を既定のデスクトップ ブラウザー プロファイルにリセットし、GPS をオフにした Microsoft Edge ユーザー エージェント文字列に戻します。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-114">The **Reset Emulation settings** button resets your emulation settings back to the default Desktop browser profile and Microsoft Edge user agent string with GPS turned off.</span></span>  

1.  <span data-ttu-id="7e3dc-115">これらのオプションが既定から変更された場合、[ **エミュレーション** ] タブには情報アラートが表示され、ブラウザーの動作のいくつかの側面がエミュレートされています。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-115">When any of these options are changed from the default, the **Emulation** tab displays an informational alert to indicate that some aspect of the behavior of your browser is being emulated.</span></span>  

## <span data-ttu-id="7e3dc-116">デバイス</span><span class="sxs-lookup"><span data-stu-id="7e3dc-116">Device</span></span>  

<span data-ttu-id="7e3dc-117">他のエミュレーション オプションを自動的に構成する Windows デバイス プロファイルの既定の一覧から選択するか、独自のカスタム構成 **を指定** します。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-117">Pick from a preset list of Windows device profiles that automatically configure the other emulation options or specify your own **Custom** configuration.</span></span>  <span data-ttu-id="7e3dc-118">Default に戻 **り、** すべてのエミュレーション ツールをリセットします。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-118">Switch back to **Default** to reset all the emulation tools.</span></span>  

## <span data-ttu-id="7e3dc-119">モード</span><span class="sxs-lookup"><span data-stu-id="7e3dc-119">Mode</span></span>  

### <span data-ttu-id="7e3dc-120">ブラウザー プロファイル</span><span class="sxs-lookup"><span data-stu-id="7e3dc-120">Browser profile</span></span>  

<span data-ttu-id="7e3dc-121">Windows Phone デバイスで実行されているページをシミュレートする簡単な方法は、 **ブラウザー** プロファイルの設定を Windows Phone に **変更することです**。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-121">A quick way to simulate your page running on a Windows Phone device is to change the **Browser profile** setting to **Windows Phone**.</span></span>  

#### <span data-ttu-id="7e3dc-122">ユーザー エージェント文字列</span><span class="sxs-lookup"><span data-stu-id="7e3dc-122">User agent string</span></span>  

<span data-ttu-id="7e3dc-123">別のブラウザーを模倣するようにユーザー エージェント文字列を変更すると、Microsoft Edge でのみ発生するエラーをデバッグする最初の手順として役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-123">Modifying your user agent string to mimic another browser is a good first step in debugging errors that are only happening in Microsoft Edge.</span></span>  

<span data-ttu-id="7e3dc-124">スクリプトは、ユーザー エージェント文字列を使用して、使用されているブラウザーを検出します。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-124">Scripts use the user agent string to detect which browser is used.</span></span>  <span data-ttu-id="7e3dc-125">スクリプトには、フロントエンド、バック エンド、またはフロントエンドとバック エンドがあります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-125">Script may be front-end, back-end, or front-end and back-end.</span></span>  <span data-ttu-id="7e3dc-126">コードはブラウザー検出を使用しませんが、サード パーティの JavaScript ライブラリまたはサーバー側スクリプトからコードを継承する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-126">Although your code does not use browser detection, your code may inherit it from a third-party JavaScript library or server-side script.</span></span>  

<span data-ttu-id="7e3dc-127">ブラウザー検出の問題は、ブラウザー機能に関する前提を使用して、Web ページの \(または変更\) 機能をスケールバックする可能性があるという問題です。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-127">The problem with browser detection is that you may scale-back \(or change\) features in your webpage using assumptions about browser capabilities.</span></span> <span data-ttu-id="7e3dc-128">代わりに、機能検出を使用してブラウザーの機能を検出する方法を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-128">Instead, you should consider using feature detection to detect the capabilities of your browser.</span></span>  <span data-ttu-id="7e3dc-129">次のいずれかの状況が原因で、予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-129">Unexpected behavior may occur because of one of the following situations.</span></span>  

*   <span data-ttu-id="7e3dc-130">Windows Internet Explorer 8を対象としたコードは、Microsoft Edge で異なる方法で実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-130">Code targeted at Windows Internet Explorer 8 may run differently in Microsoft Edge.</span></span>  
*   <span data-ttu-id="7e3dc-131">開発者による想定のため、ブラウザーでサポートする機能が無効になります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-131">A feature that your browser should support is disabled, because of an assumption made by the developer.</span></span>  

<span data-ttu-id="7e3dc-132">ユーザー エージェント文字列を変更すると問題が解決する場合、ブラウザーの検出が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-132">If changing your user agent string clears up the problem, browser detection is likely culprit.</span></span>  

## <span data-ttu-id="7e3dc-133">ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="7e3dc-133">Display</span></span>  

<span data-ttu-id="7e3dc-134">エミュレーションを表示して、さまざまな画面サイズと解像度でサイトをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-134">Display emulation to preview your site on different screen sizes and resolutions.</span></span>  

*   <span data-ttu-id="7e3dc-135">従来のデスクトップ モニター</span><span class="sxs-lookup"><span data-stu-id="7e3dc-135">conventional desktop monitors</span></span>  
*   <span data-ttu-id="7e3dc-136">小さいモバイル画面</span><span class="sxs-lookup"><span data-stu-id="7e3dc-136">smaller mobile screens</span></span>  
*   <span data-ttu-id="7e3dc-137">新しい高解像度ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="7e3dc-137">newer high-resolution displays</span></span>  

<span data-ttu-id="7e3dc-138">エミュレーションは、エミュレートされる画面の物理的な次元と一致しようとして調整されます。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-138">Emulations are adapted to try to match the physical dimensions of the screens being emulated.</span></span>  <span data-ttu-id="7e3dc-139">エミュレートされたピクセルは、圧縮または拡張された形式で表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-139">Emulated pixels may appear compressed or expanded.</span></span> <span data-ttu-id="7e3dc-140">HTML 要素のピクセルを完全に配置する必要がある場合は、エミュレーションをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-140">Emulation is not recommended if you need to test pixel-perfect positioning of HTML elements.</span></span>  <span data-ttu-id="7e3dc-141">ただし、エミュレーションは、レスポンシブ デザインをテストし、より大きな要素配置の問題を特定するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-141">Emulation is, however, good for testing responsive designs and identifying larger element positioning issues.</span></span>  

### <span data-ttu-id="7e3dc-142">Orientation</span><span class="sxs-lookup"><span data-stu-id="7e3dc-142">Orientation</span></span>  

<span data-ttu-id="7e3dc-143">横モードまたは**縦モード\*\*\*\*から選択**します。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-143">Choose from **Landscape** or **Portrait** mode.</span></span>  

### <span data-ttu-id="7e3dc-144">解決方法</span><span class="sxs-lookup"><span data-stu-id="7e3dc-144">Resolution</span></span>  

<span data-ttu-id="7e3dc-145">一般的なデバイス解像度の既定の一覧から選択するか、独自のカスタム構成 **を指定** します。 最大 80 インチと 3820 x 2160 の解像度がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-145">Choose from a preset list of popular device resolutions, or specify your own **Custom** config.  Resolutions of up to 80 inches and 3820 x 2160 are supported.</span></span>  

## <span data-ttu-id="7e3dc-146">位置情報</span><span class="sxs-lookup"><span data-stu-id="7e3dc-146">Geolocation</span></span>  

<span data-ttu-id="7e3dc-147">Web サイトで位置情報 API を [使用して位置情報][MdnGeolocationUsing] ベースのサービスを提供する場合、デスクトップの利便性から次のアクティビティを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-147">If your website uses the [Geolocation API][MdnGeolocationUsing] to provide location-based services, the following activities are available from the convenience of your desktop.</span></span>  

*   <span data-ttu-id="7e3dc-148">さまざまな GPS 座標を簡単にテストする</span><span class="sxs-lookup"><span data-stu-id="7e3dc-148">easily test different GPS coordinates</span></span>  
*   <span data-ttu-id="7e3dc-149">さまざまなセンサーの状態を簡単にテストする</span><span class="sxs-lookup"><span data-stu-id="7e3dc-149">easily test different sensor states</span></span>  

<span data-ttu-id="7e3dc-150">この設定は、位置情報をサポートするデバイス上の実際の GPS 座標とセンサーの状態を上書きします。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-150">The settings override any actual GPS coordinates and the sensor state on devices that support geolocation.</span></span>  

<span data-ttu-id="7e3dc-151">Web サイトは、デバイスの場所を使用する前に、ユーザーにアクセス許可を要求して付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-151">Your website must request and be granted permission from a user before using the device location.</span></span>  <span data-ttu-id="7e3dc-152">Microsoft Edge の [設定] パネルで、場所のアクセス許可の使用と設定がない場合のサイトの動作を **テスト** します。</span><span class="sxs-lookup"><span data-stu-id="7e3dc-152">Test how your site behaves with and without location permissions from the Microsoft Edge **Settings** panel.</span></span>  

<span data-ttu-id="7e3dc-153">**...** > **設定**  > **詳細設定を表示する**  > **Web サイトのアクセス許可**  > **管理**</span><span class="sxs-lookup"><span data-stu-id="7e3dc-153">**...** > **Settings** > **View advanced settings** > **Website permissions** > **Manage**</span></span>  

:::image type="complex" source="./media/settings_manage_permissions.png" alt-text="Microsoft Edge の [設定] パネルから Web サイトのアクセス許可を管理する" lightbox="./media/settings_manage_permissions.png":::
   <span data-ttu-id="7e3dc-155">Microsoft Edge の [設定] パネルから Web サイトのアクセス許可 **を管理** する</span><span class="sxs-lookup"><span data-stu-id="7e3dc-155">Manage website permissions from the Microsoft Edge **Settings** panel</span></span>  
:::image-end:::  

## <span data-ttu-id="7e3dc-156">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7e3dc-156">Shortcuts</span></span>

| <span data-ttu-id="7e3dc-157">操作</span><span class="sxs-lookup"><span data-stu-id="7e3dc-157">Action</span></span>  | <span data-ttu-id="7e3dc-158">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7e3dc-158">Shortcut</span></span>  |  
|:--- |:--- |  
| <span data-ttu-id="7e3dc-159">エミュレーション設定のリセット</span><span class="sxs-lookup"><span data-stu-id="7e3dc-159">Reset Emulation settings</span></span> | `Ctrl`+`Shift`+`L` |  

<!-- links -->  


[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsGuideChromiumDeviceMode]: /microsoft-edge/devtools-guide-chromium/device-mode "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  

[MicrosoftNewEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MdnGeolocationUsing]: https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation "位置情報 API |MDN"  
