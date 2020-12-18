---
description: Windows 10 Fall Creators Update (EdgeHTML 16) の Microsoft Edge DevTools に追加された機能
title: EdgeHTML 16 の DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, edgehtml 16
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2d24b6851e843f491e470b18ccc18d559ed5533d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234430"
---
# <span data-ttu-id="84b82-104">Windows 10 Fall Creators Update の DevTools (EdgeHTML 16)</span><span class="sxs-lookup"><span data-stu-id="84b82-104">DevTools in the Windows 10 Fall Creators Update (EdgeHTML 16)</span></span>

<span data-ttu-id="84b82-105">このリリースでは、堅牢性とパフォーマンスの向上に向けた主要な DevTools リファクタリング作業を開始し、今すぐ使用を開始できる一連の新機能も追加しました。</span><span class="sxs-lookup"><span data-stu-id="84b82-105">With this release we started a major DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today!</span></span> 

<span data-ttu-id="84b82-106">[Windows 10 Fall Creators Update](/windows/uwp/whats-new/windows-10-build-16299) [(EdgeHTML 16)](https://aka.ms/devguide_edgehtml_16)に同梱されている Microsoft Edge DevTools の機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="84b82-106">Here are the Microsoft Edge DevTools features that shipped with the [Windows 10 Fall Creators Update](/windows/uwp/whats-new/windows-10-build-16299) ([EdgeHTML 16](https://aka.ms/devguide_edgehtml_16)).</span></span>

## <span data-ttu-id="84b82-107">先祖イベント リスナー</span><span class="sxs-lookup"><span data-stu-id="84b82-107">Ancestor event listeners</span></span> 

<span data-ttu-id="84b82-108">[**イベント**] ウィンドウに、現在選択されている要素の先祖 (要素パネル) に登録されているイベント リスナー\*\*\*\* と、要素自体に登録されているイベント リスナーを表示するオプションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="84b82-108">The **Events** pane now adds the option to view event listeners registered on any ancestor of the currently selected element (in the **Elements** panel), in addition to those on the element itself.</span></span> <span data-ttu-id="84b82-109">さらに、イベント リスナーの表示を Event または *Element* でグループ化 *できます*。</span><span class="sxs-lookup"><span data-stu-id="84b82-109">Additionally, you can now group the event listener display by either *Event* or *Element*.</span></span> 

![イベント リスナー検査ウィンドウ](../media/elements_ancestor_events.png)

## <span data-ttu-id="84b82-111">DOM のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="84b82-111">DOM mutation breakpoints</span></span>

<span data-ttu-id="84b82-112">DOM のブレークポイントを設定して、選択した要素ノードが変更されるたびにデバッガーにブレークすることができます。</span><span class="sxs-lookup"><span data-stu-id="84b82-112">You can now set DOM mutation breakpoints to break into the Debugger whenever a selected element node changes.</span></span> <span data-ttu-id="84b82-113">[ **要素]** パネルで、DOM ツリー ビューの任意の要素を rt-click して、次の 1 つ以上を選択します。</span><span class="sxs-lookup"><span data-stu-id="84b82-113">From the **Elements** panel, rt-click on any element in the DOM tree view and select one or more of the following:</span></span>

 - <span data-ttu-id="84b82-114">ノードの削除時にブレーク</span><span class="sxs-lookup"><span data-stu-id="84b82-114">Break on Node removed</span></span>
 - <span data-ttu-id="84b82-115">変更されたサブツリーでブレーク</span><span class="sxs-lookup"><span data-stu-id="84b82-115">Break on Subtree modified</span></span>
 - <span data-ttu-id="84b82-116">属性の変更時にブレーク</span><span class="sxs-lookup"><span data-stu-id="84b82-116">Break on Attribute modified</span></span>

<span data-ttu-id="84b82-117">[要素] パネルまたはデバッガー パネルの **[DOM** ブレークポイント] ウィンドウから、ブレークポイント **の** ブレークポイント **を管理** できます。</span><span class="sxs-lookup"><span data-stu-id="84b82-117">You can manage your mutation breakpoints from the **DOM breakpoints** pane in the **Elements** or **Debugger** panels.</span></span>

![[DOM ブレークポイント] ウィンドウ](../media/elements_dom_breakpoints.png)

## <span data-ttu-id="84b82-119">CSS のルールでのサポート</span><span class="sxs-lookup"><span data-stu-id="84b82-119">CSS at-rule support</span></span>

<span data-ttu-id="84b82-120">CSS "at" (@) ルールは、アニメーション ルール\*\*\*\* `@keyframes` (現在は読み取り専用に制限されています)、機能クエリ、クエリなど、スタイル ウィンドウの他の CSS ルール宣言の中で表されます。 `@supports` `@media`</span><span class="sxs-lookup"><span data-stu-id="84b82-120">CSS "at" (@) rules are now represented among other CSS rule declarations on the **Styles** pane, including animation `@keyframes` rules (currently limited to read-only), `@supports` feature queries, and `@media` queries.</span></span>

![DevTools スタイル ウィンドウからの CSS 規則の検査](../media/elements_at_rules.png)

## <span data-ttu-id="84b82-122">[CSS フォント] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="84b82-122">CSS fonts pane</span></span>

<span data-ttu-id="84b82-123">CSS ルールには、フォントの読み込み先 (ローカルまたはネットワーク) とそのフォントを使用している文字の数を表示する専用のフォント ウィンドウが `@font-face` 追加されました。 \*\*\*\* \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="84b82-123">CSS `@font-face` rules now have their own dedicated **Fonts** pane that displays where the font is loaded from (*Local* or *Network*) and how many characters are using it.</span></span> <span data-ttu-id="84b82-124">フォントがネットワークから読み込まれると、DevTools は、エイリアスとフォントの種類と共にインポートしたルールを表示します。</span><span class="sxs-lookup"><span data-stu-id="84b82-124">If a font is loaded from the network,  DevTools will display the rule that imported it along with its alias and font type.</span></span>

![CSS フォント情報](../media/elements_fonts.png)

## <span data-ttu-id="84b82-126">CSS 擬似要素のサポート</span><span class="sxs-lookup"><span data-stu-id="84b82-126">CSS pseudo-element support</span></span>

<span data-ttu-id="84b82-127">スタイル **ウィンドウ** では、独自の見出しの下に擬似要素がグループ化され、そのコンテンツがクロスアウトとして表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="84b82-127">The **Styles** pane now groups pseudo-elements under their own headings and no longer displays their content as crossed out.</span></span>

**<span data-ttu-id="84b82-128">変更前:</span><span class="sxs-lookup"><span data-stu-id="84b82-128">Before:</span></span>**
<br>
![生成されたコンテンツが以前にクロスアウトされた](../media/gc_before.png)

**<span data-ttu-id="84b82-130">変更後:</span><span class="sxs-lookup"><span data-stu-id="84b82-130">After:</span></span>**
<br>
![生成されたコンテンツが取り消し線付きで表示されなくなった](../media/gc_after.png)

## <span data-ttu-id="84b82-132">コンソールの機能強化</span><span class="sxs-lookup"><span data-stu-id="84b82-132">Console improvements</span></span>

<span data-ttu-id="84b82-133">コンソール **パネル** では、操作性を向上し、Intellisense エクスペリエンスをより高速で充実させた UX オーバーホールを利用しました。</span><span class="sxs-lookup"><span data-stu-id="84b82-133">The **Console** panel got a UX overhaul for improved usability and a faster, richer Intellisense experience.</span></span>

<span data-ttu-id="84b82-134">**前:** 
![以前の本体</span><span class="sxs-lookup"><span data-stu-id="84b82-134">**Before:**
![Previous console</span></span>](../media/console_old.png)

<span data-ttu-id="84b82-135">**後:** 
![新しいコンソール</span><span class="sxs-lookup"><span data-stu-id="84b82-135">**After:**
![New console</span></span>](../media/console_new.png)

<span data-ttu-id="84b82-136">さらに、次の機能強化が追加されました。</span><span class="sxs-lookup"><span data-stu-id="84b82-136">We also added these improvements:</span></span>

 -  <span data-ttu-id="84b82-137">コマンド `Shift + Enter` を実行する前に、追加の行をコマンドに追加するために使用します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="84b82-137">Use `Shift + Enter` to add an additional line to a command before executing it with `Enter`.</span></span> <span data-ttu-id="84b82-138">(以前は、複数行モード *または単一行モードへの切り替えボタン* があります)。</span><span class="sxs-lookup"><span data-stu-id="84b82-138">(Formerly there was a *Switch to multiline/single-line mode* toggle button.)</span></span>

 - <span data-ttu-id="84b82-139">次の新しい API がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="84b82-139">The following new APIs are supported:</span></span>
    - <span data-ttu-id="84b82-140">[ **console.table(**_object_*_)_*](../console/console-api.md#organizing-log-output)メソッド</span><span class="sxs-lookup"><span data-stu-id="84b82-140">[**console.table(**_object_*_)_*](../console/console-api.md#organizing-log-output) method</span></span>
    - <span data-ttu-id="84b82-141">[ **getEventListeners(**_object_*_)_*](../console/command-line.md#event-listeners)コマンド</span><span class="sxs-lookup"><span data-stu-id="84b82-141">[**getEventListeners(**_object_*_)_*](../console/command-line.md#event-listeners) command</span></span>
    - <span data-ttu-id="84b82-142">[ **keys(**_object_*_)_*](../console/command-line.md#object-inspection)コマンド</span><span class="sxs-lookup"><span data-stu-id="84b82-142">[**keys(**_object_*_)_*](../console/command-line.md#object-inspection) command</span></span>
    - <span data-ttu-id="84b82-143">[ **values(**_object_*_)_*](../console/command-line.md#object-inspection)コマンド</span><span class="sxs-lookup"><span data-stu-id="84b82-143">[**values(**_object_*_)_*](../console/command-line.md#object-inspection) command</span></span>
    - <span data-ttu-id="84b82-144">[ **$x(**_xpath 式_*_)_*](../console/command-line.md#dom-selectors)セレクター</span><span class="sxs-lookup"><span data-stu-id="84b82-144">[**$x(**_xpath expression_*_)_*](../console/command-line.md#dom-selectors) selector</span></span>

 - <span data-ttu-id="84b82-145">[**%c()**](../console/console-api.md#logging-custom-messages)書式設定パラメーターがサポートされる</span><span class="sxs-lookup"><span data-stu-id="84b82-145">The [**%c()**](../console/console-api.md#logging-custom-messages) formatting parameter is now supported</span></span>

## <span data-ttu-id="84b82-146">デバッグの機能強化</span><span class="sxs-lookup"><span data-stu-id="84b82-146">Debugging improvements</span></span>

<span data-ttu-id="84b82-147">[デバッガーは、PWA](#progressive-web-app-debugging)サービス ワーカーとキャッシュをデバッグする一部の新機能に加えて、次の機能を追加しました。</span><span class="sxs-lookup"><span data-stu-id="84b82-147">In addition to a suite of new features for debugging your [PWA service workers and cache](#progressive-web-app-debugging), the Debugger added these features:</span></span>

### <span data-ttu-id="84b82-148">共有リソースの統合デバッグ</span><span class="sxs-lookup"><span data-stu-id="84b82-148">Consolidated debugging for shared resources</span></span>

<span data-ttu-id="84b82-149">CDN から読み込まれたファイルなどのリソースがコード全体で複数回参照されている場合でも、DevTools はそのファイルに対して 1 つのデバッグ インスタンスを提供し、そのファイルが参照されている場所に関係なくヒットする一般的なブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="84b82-149">Even when a resource, such as a file loaded from CDN, is referenced multiple times throughout your code,  DevTools will now provide a single debugging instance for that file where you can then set common breakpoints which will be hit regardless of where that file is referenced.</span></span> <span data-ttu-id="84b82-150">(以前は、各スクリプト参照は固有のリソースと見なされ、別のブレークポイントのセットにマップされます)。</span><span class="sxs-lookup"><span data-stu-id="84b82-150">(Previously each script reference was considered a unique resource would map to a separate set of breakpoints.)</span></span>

### <span data-ttu-id="84b82-151">アイドル時編集を使用して JavaScript *をライブ編集する*</span><span class="sxs-lookup"><span data-stu-id="84b82-151">Live edit JavaScript with *Edit-on-idle*</span></span>

<span data-ttu-id="84b82-152">これで、デバッグ セッション中に JavaScript ライブを編集できます。</span><span class="sxs-lookup"><span data-stu-id="84b82-152">You can now edit your JavaScript live during a debugging session.</span></span> <span data-ttu-id="84b82-153">この機能は、[以前の](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97)*(Windows 10 Creators Update)* リリースで (フラグの背後で) 試験的に利用可能であり、現在は永続的な機能です。</span><span class="sxs-lookup"><span data-stu-id="84b82-153">This feature was experimentally available (behind a flag) in the [previous](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) (*Windows 10 Creators Update*) release and now its a permanent feature.</span></span> <span data-ttu-id="84b82-154">デバッガー パネルから任意のスクリプト\*\*\*\* ファイルを選択し、編集し、[保存] **(または**) をクリックして、次にコードのセクションが実行される時に変更 `Ctrl+S` をテストします。</span><span class="sxs-lookup"><span data-stu-id="84b82-154">Simply select any script file from the **Debugger** panel, edit, then click **Save** (or `Ctrl+S`) to test your changes next time that section of code runs.</span></span> 

![デバッガーを使用すると、ライブ編集スクリプトを有効にし、変更を比較できます。](../media/debugger_edit_buttons.png) 

<span data-ttu-id="84b82-156">[元 **のドキュメントと比較] ボタン** をクリックして、変更した変更の違いを表示します。</span><span class="sxs-lookup"><span data-stu-id="84b82-156">Click the **Compare document to original** button to view the diff of what you changed.</span></span>

![デバッガーで編集されたコードの差分ビュー](../media/debugger_edit_code.png) 

<span data-ttu-id="84b82-158">次の制約に注意してください。</span><span class="sxs-lookup"><span data-stu-id="84b82-158">Please be aware of the following constraints:</span></span>

- <span data-ttu-id="84b82-159">スクリプトの編集は、外部 *の .js ファイル* でのみ機能します (.html に `<script>` 埋め込 *まれているのではなく*)</span><span class="sxs-lookup"><span data-stu-id="84b82-159">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span></span>
- <span data-ttu-id="84b82-160">編集内容はメモリに保存され、ドキュメントが再読み込みされた場合にフラッシュされます。そのため、ハンドラー内で編集を実行できません。たとえば、 `DOMContentLoaded`</span><span class="sxs-lookup"><span data-stu-id="84b82-160">Edits are saved in memory and flushed when the document is reloaded, thus you won’t be able to run edits inside a `DOMContentLoaded` handler, for example</span></span>
- <span data-ttu-id="84b82-161">現時点では、DevTools からディスクに\*\*\*\* 編集内容を保存する方法 ([名前を付けて保存] オプションなど) はありません。</span><span class="sxs-lookup"><span data-stu-id="84b82-161">Currently there’s no way (such as a **Save As** option) to save your edits to disk from  DevTools</span></span>

## <span data-ttu-id="84b82-162">ショートカット</span><span class="sxs-lookup"><span data-stu-id="84b82-162">Shortcuts</span></span>

<span data-ttu-id="84b82-163">他の主要なブラウザーと同様に、DevTools を前回表示したパネル ( ) またはコンソール ( ) に直接 `Ctrl+Shift+I` `Ctrl+Shift+J` 起動できます。</span><span class="sxs-lookup"><span data-stu-id="84b82-163">You can now launch DevTools to the last viewed panel (`Ctrl+Shift+I`) or directly to the Console (`Ctrl+Shift+J`) just like you would on other major browsers.</span></span>

## <span data-ttu-id="84b82-164">段階的な Web アプリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="84b82-164">Progressive Web App debugging</span></span>

<span data-ttu-id="84b82-165">Microsoft Edge と DevTools での段階的な Web アプリ (PAS) の\*\*\*\* 試験的なサポートをテストするには、[サービス ワーカーを有効にする] オプションを選択 `about:flags` し、Microsoft Edge を再起動します。</span><span class="sxs-lookup"><span data-stu-id="84b82-165">Test out the experimental support for Progressive Web Apps (PWAs) in Microsoft Edge and  DevTools by selecting the **Enable service workers** option from `about:flags` (and restarting Microsoft Edge).</span></span> <span data-ttu-id="84b82-166">サイトでサービス ワーカーや\*\*\*\* キャッシュ**API**を利用する場合、Web ストレージや Cookie\*\*\*\* の検査の動作と同様に、各オリジンのデバッガー パネルにエントリが設定されます。</span><span class="sxs-lookup"><span data-stu-id="84b82-166">If a site makes use of **Service Workers** and/or the **Cache** API,  will populate entries in the **Debugger** panel for each origin, similar to how web storage and cookie inspection work.</span></span>

<span data-ttu-id="84b82-167">特定のサービス ワーカー エントリをクリックすると、 **サービス**ワーカーの概要が開き、指定したスコープのサービス ワーカー登録を管理し、テスト プッシュ通知を強制できます。</span><span class="sxs-lookup"><span data-stu-id="84b82-167">Clicking on a specific service worker entry will open up the **Service Worker Overview**, where you can manage the service worker registration for the given scope and force a test push notification.</span></span> <span data-ttu-id="84b82-168">個々のサービス**ワーカー** / **を停止**し、個別\*\*\*\* のデバッガー ウィンドウから検査することもできます。</span><span class="sxs-lookup"><span data-stu-id="84b82-168">You can also **Stop**/**Start** individual service workers and **Inspect** them from a separate debugger window:</span></span>

![[サービス ワーカーの概要] ウィンドウ](../media/debugger_sw_overview.png)

<span data-ttu-id="84b82-170">サービス ワーカーのデバッグについては、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="84b82-170">Please note the following about service worker debugging:</span></span>

 - <span data-ttu-id="84b82-171">サービス ワーカーは複数のタブで共有できるので、サービス ワーカーをデバッグすると、ページのツールとは別に DevTools の新しいインスタンスが起動します。</span><span class="sxs-lookup"><span data-stu-id="84b82-171">Debugging a service worker will launch a new instance of the DevTools separate from the page's tools because service workers can be shared across multiple tabs.</span></span> 
 - <span data-ttu-id="84b82-172">要素[と](../elements.md)[エミュレーション](../emulation.md)パネルは、サービス ワーカーがバックグラウンドで実行され、アプリのフロントエンドを直接制御しなことを考えると、サービス ワーカー デバッガーから離れたものになります。</span><span class="sxs-lookup"><span data-stu-id="84b82-172">The [Elements](../elements.md) and [Emulation](../emulation.md) panels are absent from the service worker debugger, given that service workers run in the background and do not directly control the front-end of your app.</span></span>
 - <span data-ttu-id="84b82-173">現在、サービス ワーカーのネットワーク トラフィックは、そのワーカーの DevTools デバッグ インスタンスからのみ報告され、ページ自体の中央インスタンスからのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="84b82-173">Currently network traffic for a service worker is only reported from the DevTools debugging instance for that worker, and not from the central instance for the page itself.</span></span>

<span data-ttu-id="84b82-174">特定のキャッシュ エントリをクリックすると、キャッシュ\*\*\*\* マネージャーが開き、キャッシュ エントリ *(要求*キーと応答キー/値\*\* のペア) を検査し、必要に応じて削除できます。</span><span class="sxs-lookup"><span data-stu-id="84b82-174">Clicking on a specific cache entry will open up the **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs).</span></span>
