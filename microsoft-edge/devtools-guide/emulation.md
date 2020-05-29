---
description: エミュレーションパネルを使用して、さまざまなブラウザープロファイル、画面サイズと解像度、GPS 位置座標をテストする
title: DevTools-エミュレーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、デバイスエミュレーション、応答性の高いデザイン、位置情報、解像度
ms.custom: seodec18
ms.openlocfilehash: d66646600aeaac279acaf622527f829c69f33286
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569704"
---
# <span data-ttu-id="a9b50-104">エミュレーション</span><span class="sxs-lookup"><span data-stu-id="a9b50-104">Emulation</span></span>

<span data-ttu-id="a9b50-105">*エミュレーション*パネルでは、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9b50-105">The *Emulation* panel helps you to:</span></span>
 - <span data-ttu-id="a9b50-106">さまざまな[デバイスプロファイル](#device)、[ブラウザー](#browser-profile)、[画面サイズ、解像度](#display)をシミュレートする</span><span class="sxs-lookup"><span data-stu-id="a9b50-106">Simulate various [device profiles](#device), [browsers](#browser-profile), [screen sizes and resolutions](#display)</span></span>
 - <span data-ttu-id="a9b50-107">さまざまな[位置情報の設定と座標の](#geolocation)テスト</span><span class="sxs-lookup"><span data-stu-id="a9b50-107">Test different [geolocation settings and coordinates](#geolocation)</span></span>

![Microsoft Edge DevTools エミュレーションパネル](./media/emulation.png)

1. <span data-ttu-id="a9b50-109">[**エミュレーションの設定を保持**する] ボタンをクリックすると、既定のデスクトップエミュレーション設定で行った変更がすべて保存されます。これは、devtools を閉じてもう一度開いた場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="a9b50-109">The **Persist Emulation settings** button will save any changes you made from the default desktop emulation settings, even when you close and reopen the DevTools.</span></span> 

2. <span data-ttu-id="a9b50-110">[**エミュレーション設定のリセット**] ボタンを使うと、エミュレーションの設定が既定の*デスクトップ*ブラウザープロファイルと Microsoft Edge ユーザーエージェント文字列にリセットされ、GPS が無効になります。</span><span class="sxs-lookup"><span data-stu-id="a9b50-110">The **Reset Emulation settings** button will reset your emulation settings back to the default *Desktop* browser profile and Microsoft Edge user agent string with GPS turned off.</span></span>

3. <span data-ttu-id="a9b50-111">これらのオプションのいずれかを既定値から変更した場合、[**エミュレーション**] タブには、ブラウザーの動作の一部がエミュレートされていることを示す情報アラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9b50-111">When any of these options are changed from the default, the **Emulation** tab will show an informational alert to indicate that some aspect of your browser's behavior is being emulated.</span></span>

## <span data-ttu-id="a9b50-112">デバイス</span><span class="sxs-lookup"><span data-stu-id="a9b50-112">Device</span></span>

<span data-ttu-id="a9b50-113">他のエミュレーションオプションを自動的に構成する、または独自の*カスタム*構成を指定する、Windows デバイスプロファイルの事前設定リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="a9b50-113">Pick from a preset list of Windows device profiles which  automatically configure the other emulation options or specify your own *Custom* configuation.</span></span> <span data-ttu-id="a9b50-114">*既定*の状態に戻すには、すべてのエミュレーションツールをリセットします。</span><span class="sxs-lookup"><span data-stu-id="a9b50-114">Switch back to *Default* to reset all the emulation tools.</span></span>

## <span data-ttu-id="a9b50-115">モード</span><span class="sxs-lookup"><span data-stu-id="a9b50-115">Mode</span></span>

### <span data-ttu-id="a9b50-116">ブラウザプロファイル</span><span class="sxs-lookup"><span data-stu-id="a9b50-116">Browser profile</span></span>
<span data-ttu-id="a9b50-117">Windows Phone デバイスで実行されているページをシミュレートする簡単な方法は、**ブラウザーのプロファイル**設定を*windows phone*に変更することです。</span><span class="sxs-lookup"><span data-stu-id="a9b50-117">A quick way to simulate your page running on a Windows Phone device is to change the **Browser profile** setting to *Windows Phone*.</span></span>

#### <span data-ttu-id="a9b50-118">ユーザーエージェント文字列</span><span class="sxs-lookup"><span data-stu-id="a9b50-118">User agent string</span></span>

<span data-ttu-id="a9b50-119">Microsoft Edge でのみ発生するエラーをデバッグするには、最初の手順として、ユーザーエージェント文字列を他のブラウザーに近いものにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9b50-119">Modifying your user agent string to mimic another browser is a good first step in debugging errors that are only happening in Microsoft Edge.</span></span> 

<span data-ttu-id="a9b50-120">フロントエンドおよびバックエンドスクリプトでは、ユーザーエージェント文字列を使って、使用しているブラウザーを検出することができます。</span><span class="sxs-lookup"><span data-stu-id="a9b50-120">Front end and/or back end scripts sometimes use the user agent string  to detect which browser you're using.</span></span> <span data-ttu-id="a9b50-121">また、独自のコードでブラウザーの検出を使用していない場合でも、サードパーティの JavaScript ライブラリまたはサーバー側のスクリプトを使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9b50-121">And even when you're not using browser detection in your own code, you may be using a third-party JavaScript library or server-side script that does.</span></span>

<span data-ttu-id="a9b50-122">ブラウザーの検出に関する問題は、ブラウザーで実際に機能検出を使用して実行できる操作を検出するのではなく、開発者がどのようにして web ページの機能を拡大または変更するためによく使われることです。</span><span class="sxs-lookup"><span data-stu-id="a9b50-122">The problem with browser detection is that it's often used to scale back or change the features in a webpage based on what the developer writing the script thinks your browser can do, rather than detecting what your browser can actually do using feature detection.</span></span> <span data-ttu-id="a9b50-123">これにより、Microsoft Edge では、Windows Internet Explorer 8 でターゲットとなるコードの動作が大幅に異なるため、予期しない動作が発生することがあります。または、開発者によって実現されたため、お使いのブラウザーでサポートされている機能は無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="a9b50-123">This can cause unexpected behavior, because code targeted at Windows Internet Explorer 8 can run very differently in Microsoft Edge; or a feature your browser is perfectly capable of supporting might be disabled because of an assumption made by the developer.</span></span>

<span data-ttu-id="a9b50-124">ユーザーエージェント文字列を変更すると問題が解消される場合は、ブラウザーの検出が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9b50-124">If changing your user agent string clears up the problem, browser detection is likely culprit.</span></span>

## <span data-ttu-id="a9b50-125">ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="a9b50-125">Display</span></span>

<span data-ttu-id="a9b50-126">ディスプレイエミュレーション機能を使用すると、従来のデスクトップモニターから小さいモバイル画面やより新しい高解像度ディスプレイなど、さまざまな画面サイズと解像度でサイトをプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="a9b50-126">Display emulation lets you preview your site on different screen sizes and resolutions: from conventional desktop monitors to smaller mobile screens or newer high-resolution displays.</span></span>

<span data-ttu-id="a9b50-127">エミュレーションは、エミュレートされる画面の物理サイズと一致するように調整されます。</span><span class="sxs-lookup"><span data-stu-id="a9b50-127">Emulations are adapted to try and match the physical dimensions of the screens being emulated.</span></span> <span data-ttu-id="a9b50-128">エミュレートされたピクセルは、圧縮または拡張されたように見える場合があります。また、HTML 要素のピクセルにぴったりな配置をテストする必要がある場合は、エミュレーションをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="a9b50-128">Emulated pixels might appear compressed or expanded, and emulation is not recommended if you need to test pixel-perfect positioning of HTML elements.</span></span> <span data-ttu-id="a9b50-129">ただし、エミュレーションは、応答性の高いデザインをテストし、要素の配置の大きな問題を特定するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="a9b50-129">Emulation is, however, good for testing responsive designs and identifying larger element positioning issues.</span></span>

### <span data-ttu-id="a9b50-130">Orientation</span><span class="sxs-lookup"><span data-stu-id="a9b50-130">Orientation</span></span>

<span data-ttu-id="a9b50-131">[*横*] または [*縦*] モードから選択します。</span><span class="sxs-lookup"><span data-stu-id="a9b50-131">Choose from *Landscape* or *Portrait* mode.</span></span>

### <span data-ttu-id="a9b50-132">解決方法</span><span class="sxs-lookup"><span data-stu-id="a9b50-132">Resolution</span></span>

<span data-ttu-id="a9b50-133">一般的なデバイスの解像度の事前設定リストから選ぶか、独自の*カスタム*構成を指定します。最大80インチおよび 3820 x 2160 の解像度がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a9b50-133">Choose from a preset list of popular device resolutions, or specify your own *Custom* config. Resolutions of up to 80 inches and 3820 x 2160 are supported.</span></span>

## <span data-ttu-id="a9b50-134">位置情報</span><span class="sxs-lookup"><span data-stu-id="a9b50-134">Geolocation</span></span>

<span data-ttu-id="a9b50-135">サイトで位置情報に基づくサービスを提供するために位置情報[API](https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation)を使用している場合、デスクトップの便利な GPS 座標とセンサーの状態を簡単にテストできます。</span><span class="sxs-lookup"><span data-stu-id="a9b50-135">If your site uses the [Geolocation API](https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation) to provide location-based services, you can easily test different GPS coordinates and sensor states from the convenience of your desktop.</span></span> <span data-ttu-id="a9b50-136">これらの設定は、位置情報をサポートするコンピューター上の実際の GPS 座標とセンサーの状態を上書きします。</span><span class="sxs-lookup"><span data-stu-id="a9b50-136">These settings will override any actual GPS coordinates and the sensor state on machines that support geolocation.</span></span> 

<span data-ttu-id="a9b50-137">Web 上の個人データを使用する場合と同じように、ユーザーはまず、場所を使用するためのサイトのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9b50-137">As with any usage of personal data on the web, your users will first need to grant your site permission to use their location.</span></span> <span data-ttu-id="a9b50-138">Microsoft Edge の [*設定*] パネルで、サイトの位置情報を確認しながら、サイトの動作をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b50-138">You can test how your site behaves with and without location permissions from the Microsoft Edge *Settings* panel:</span></span>

<span data-ttu-id="a9b50-139">**...** > **設定**  > **詳細設定**  >  を表示する**Web サイトの権限**  > **管理**</span><span class="sxs-lookup"><span data-stu-id="a9b50-139">**...** > **Settings** > **View advanced settings** > **Website permissions** > **Manage**</span></span>

![Microsoft Edge の [設定] パネルから web サイトの権限を管理する](./media/settings_manage_permissions.png)

## <span data-ttu-id="a9b50-141">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a9b50-141">Shortcuts</span></span>

| <span data-ttu-id="a9b50-142">操作</span><span class="sxs-lookup"><span data-stu-id="a9b50-142">Action</span></span>                   | <span data-ttu-id="a9b50-143">キー</span><span class="sxs-lookup"><span data-stu-id="a9b50-143">Shortcut</span></span>               |
|:-------------------------|:-----------------------|
| <span data-ttu-id="a9b50-144">エミュレーション設定のリセット</span><span class="sxs-lookup"><span data-stu-id="a9b50-144">Reset Emulation settings</span></span> | `CTRL` + `SHIFT` + `L` |
