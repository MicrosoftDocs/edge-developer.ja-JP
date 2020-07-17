---
description: デバッガーを使って、コードのステップ実行とトラブルシューティングを行います。
title: デバッガー-DevTools (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、デバッガー、デバッグ、ブレークポイント、ウォッチ、サービスワーカー、キャッシュ api、web ストレージ、cookie
ms.custom: seodec18
ms.openlocfilehash: 722277618cd8d6d5d6dba4f2a8bd3a28b6466f77
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882920"
---
# <span data-ttu-id="a6bf6-104">デバッガー-DevTools (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="a6bf6-104">Debugger - DevTools (EdgeHTML)</span></span>

<span data-ttu-id="a6bf6-105">**デバッガー**を使ってコードをステップ実行し、ウォッチポイントとブレークポイントを設定して、コードをリアルタイムで編集してキャッシュを検査します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-105">Use the **Debugger** to step through code, set watches and breakpoints, live edit your code and inspect your caches.</span></span> <span data-ttu-id="a6bf6-106">次の方法でコードのテストとトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-106">Test and troubleshoot your code by:</span></span>

- <span data-ttu-id="a6bf6-107">読み込んだソースファイルからコードを[参照](#resource-picker)して[検索](#file-search)する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-107">[Browsing](#resource-picker) and [searching](#file-search) code from your loaded source files</span></span>
- <span data-ttu-id="a6bf6-108">コードのステップ[実行時に実行フローを制御](#toolbar)する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-108">[Controlling the execution flow](#toolbar) as you step through your code</span></span>
- <span data-ttu-id="a6bf6-109">[サービスワーカーとキャッシュ](./service-workers.md)、 [cookie](./storage.md#cookies-list) 、 [web ストレージ](./storage.md#local-and-session-storage-managers)などの[ページストレージリソースを管理する](./storage.md#cache-manager)</span><span class="sxs-lookup"><span data-stu-id="a6bf6-109">[Managing page storage resources](./storage.md#cache-manager), including the [service workers and cache](./service-workers.md), [cookies](./storage.md#cookies-list) and [web storage](./storage.md#local-and-session-storage-managers)</span></span>  
- <span data-ttu-id="a6bf6-110">[ブレークポイントを設定し](#debug-window)、実行時にコードをライブ編集する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-110">[Setting breakpoints and live editing](#debug-window) your code as it runs</span></span>
- <span data-ttu-id="a6bf6-111">デバッグ時に[ローカル変数を管理および編集](#watches)する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-111">[Tracking and editing local variables](#watches) as you debug</span></span>
- <span data-ttu-id="a6bf6-112">必要に応じて、呼び出し元からの[非同期コードおよびライブラリコードの表示と非表示を切り替える](#call-stack)</span><span class="sxs-lookup"><span data-stu-id="a6bf6-112">[Hiding or showing asynchronous code and library code](#call-stack) from your callstack as needed</span></span>
- <span data-ttu-id="a6bf6-113">XmlHttpRequests、イベント、 [DOM mutations](#dom-breakpoints)に[特殊なブレークポイントを追加する](#breakpoints)</span><span class="sxs-lookup"><span data-stu-id="a6bf6-113">[Adding specialized breakpoints](#breakpoints) for XmlHttpRequests, events and [DOM mutations](#dom-breakpoints)</span></span>

![Microsoft Edge DevTools デバッガー](./media/debugger.png)

<span data-ttu-id="a6bf6-115">デバッグセッションを開始するには、3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-115">There are three ways to begin a debugging session.</span></span>

1. **<span data-ttu-id="a6bf6-116">ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-116">Set a breakpoint.</span></span>** <span data-ttu-id="a6bf6-117">コードの実行に到達すると、デバッガーが開始され、コードをステップ実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-117">When the execution of your code reaches it, you'll enter the debugger and be able to step through your code.</span></span>
2. **<span data-ttu-id="a6bf6-118">コードで中断を開始します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-118">Initiate a break in code.</span></span>** <span data-ttu-id="a6bf6-119">[[**中断**](#toolbar)] (*一時停止*アイコン) ツールバーのボタンまたはをクリックし `Ctrl+Shift+B` ます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-119">Click the [**Break**](#toolbar) (*pause* icon) toolbar button or `Ctrl+Shift+B`.</span></span> <span data-ttu-id="a6bf6-120">デバッガーは、次の実行ステートメントで中断します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-120">The debugger will break on the next statement of execution.</span></span>
3. **<span data-ttu-id="a6bf6-121">例外動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-121">Set exception behavior.</span></span>** <span data-ttu-id="a6bf6-122">コードで例外がスローされたときにデバッガーを中断するには、[[**例外動作の変更**](#toolbar)] メニュー ( `Ctrl+Shift+E` ) を使います。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-122">Use the [**Change exception behavior**](#toolbar) menu (`Ctrl+Shift+E`) to break into the debugger when your code throws an exception.</span></span> <span data-ttu-id="a6bf6-123">既定では、デバッガーは*例外に対して中断しない*ように設定されていますが、コンソールには記録されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-123">By default, the debugger is set to *Never break on exceptions*, but they are logged to the console.</span></span>

## <span data-ttu-id="a6bf6-124">リソースピッカー</span><span class="sxs-lookup"><span data-stu-id="a6bf6-124">Resource picker</span></span>

<span data-ttu-id="a6bf6-125">多くの場合、デバッグの最初の手順は、トラブルシューティングするコードにブレークポイントを設定することです。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-125">Often the first step in debugging is to set breakpoints in the code you're looking to troubleshoot.</span></span> <span data-ttu-id="a6bf6-126">[*リソースの選択*] ウィンドウから、現在ページに読み込まれているすべてのコードファイル ( *.html、.css* 、 *.js*など) を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-126">You can find all the code files currently loaded by the page from the *Resource picker* pane, including *.html, .css* and *.js* files.</span></span>

 <span data-ttu-id="a6bf6-127">ファイルエントリをクリックすると、そのファイルのタブが [[デバッグ] ウィンドウ](#debug-window)に表示され、ファイル名のテキストが太字で表示されます ( *devtools-guide*ファイル名は上記の図のようになります)。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-127">Clicking on a file entry will open a tab for that file in the [Debug window](#debug-window) and bold the text of the file name to indicate this (as *devtools-guide* file name is in the illustration above).</span></span> <span data-ttu-id="a6bf6-128">次に、[デバッグウィンドウ](#debug-window)からそのファイル内にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-128">You can then set breakpoints within that file from the [Debug window](#debug-window).</span></span>

![デバッガリソースの選択](./media/debugger_resource_picker.png)

<span data-ttu-id="a6bf6-130">*リソースピッカー*のコンテキストメニューから、ファイルを**ライブラリコード**() としてマークすることもでき `Ctrl+L` ます。この[コードをデバッガーでスキップ](#debug-window)して、 [[**呼び出し履歴**] ウィンドウから非表示](#call-stack)にするオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-130">From the *Resource picker* context menu, you can also mark a file as **library code** (`Ctrl+L`), giving you the option to [skip over that code in the debugger](#debug-window) and [hide it from the **Call stack** pane](#call-stack).</span></span> <span data-ttu-id="a6bf6-131">[(または)] をもう一度クリックすると `Ctrl+L` 、ファイルが元の値に*マイコード*または*ライブラリコード*として再び切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-131">Clicking (or `Ctrl+L`) again will toggle the file back to its previous value as *my code* or *library code*.</span></span>

### <span data-ttu-id="a6bf6-132">ファイル検索</span><span class="sxs-lookup"><span data-stu-id="a6bf6-132">File search</span></span>

<span data-ttu-id="a6bf6-133">*Find in files* `Ctrl` + `Shift` + `F` ソースで検索しようとしている特定のコードの文字列がある場合は、[ファイル内を検索] コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-133">Use the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="a6bf6-134">ツールバーには、正規表現などのさまざまな検索オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-134">The toolbar provides different search options, including regular expressions.</span></span> <span data-ttu-id="a6bf6-135">検索結果をクリックすると、指定したファイルと行に*デバッグウィンドウ*がフォーカスされます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-135">Clicking on a search result will focus the *Debug window* on the specified file and line.</span></span>

![デバッガファイルの検索ウィンドウ](./media/debugger_file_search.png)

## <span data-ttu-id="a6bf6-137">デバッグウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a6bf6-137">Debug window</span></span>

<span data-ttu-id="a6bf6-138">*デバッグウィンドウ*では、デバッグ時にブレークポイント、ステップ間のコード、アクティブなスクリプトの編集を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-138">The *Debug window* is where you set your breakpoints, step through code, and live edit your script as you debug.</span></span> <span data-ttu-id="a6bf6-139">任意のスクリプトコマンドの左側をクリックして、**ブレークポイント**を追加 (または削除) します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-139">Click to the left of any script command to add (or remove) a **Breakpoint**.</span></span> <span data-ttu-id="a6bf6-140">右クリックのコンテキストメニューまたは [[**ブレークポイント**](#breakpoints)] ウィンドウを使って、その場所で*True*が評価された場合にデバッガーを中断させる論理式を指定して、ブレークポイントに*条件を追加*します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-140">Use the right-click context menu or [**Breakpoints**](#breakpoints) pane to *Add a condition* to the breakpoint by supplying a logical expression that causes the debugger to break if it evaluates *True* at that location.</span></span>

![デバッグウィンドウのコマンド](./media/debugger_window.png)

<span data-ttu-id="a6bf6-142">デバッグウィンドウのその他の機能には、次のコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-142">Other features of the debug window include controls for:</span></span>

### <span data-ttu-id="a6bf6-143">1. コードの編集</span><span class="sxs-lookup"><span data-stu-id="a6bf6-143">1. Code editing</span></span>

<span data-ttu-id="a6bf6-144">デバッグセッション中に JavaScript live を編集できます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-144">You can edit your JavaScript live during a debugging session.</span></span> <span data-ttu-id="a6bf6-145">変更が完了したら、[ <strong> 保存] () をクリックして、 </strong> `Ctrl+S` 次回のコードセクションの実行時に変更をテストします。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-145">Once you make your changes, click <strong>Save</strong> (`Ctrl+S`) to test your changes next time that section of code runs.</span></span> <span data-ttu-id="a6bf6-146">コードの変更を保存していない場合は、[*デバッグウィンドウ*] タブのファイル名の前にアスタリスク (\ \*) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-146">If you have unsaved code changes, an asterisk (\*) will appear before the file name in the *Debug window* tab.</span></span>

<span data-ttu-id="a6bf6-147">[**元の文書と比較**する] ボタンをクリックして、変更した内容の相違点を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-147">Click the **Compare document to original** button to view the diff of what you changed.</span></span>

![デバッガーでの編集されたコードの差分表示](./media/debugger_edit_code.png)

<span data-ttu-id="a6bf6-149">以下の制約に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-149">Please be aware of the following constraints:</span></span>

- <span data-ttu-id="a6bf6-150">スクリプト編集は、外部の *.js*ファイルでのみ機能します (.html 内に埋め込まれているわけではありません `<script>` ) *。*</span><span class="sxs-lookup"><span data-stu-id="a6bf6-150">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span></span>
- <span data-ttu-id="a6bf6-151">編集はメモリに保存され、ドキュメントの再読み込み時にフラッシュされるため、たとえば、ハンドラー内で編集を実行することはできません。 `DOMContentLoaded`</span><span class="sxs-lookup"><span data-stu-id="a6bf6-151">Edits are saved in memory and flushed when the document is reloaded, thus you won't be able to run edits inside a `DOMContentLoaded` handler, for example</span></span>
- <span data-ttu-id="a6bf6-152">現時点では、DevTools からディスクへの編集を保存する方法はありません ([**名前を付けて保存**] オプションなど)。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-152">Currently there's no way (such as a **Save As** option) to save your edits to disk from the DevTools</span></span>

### <span data-ttu-id="a6bf6-153">2. コードの書式設定</span><span class="sxs-lookup"><span data-stu-id="a6bf6-153">2.Code formatting</span></span>

<span data-ttu-id="a6bf6-154">以下のコントロールを使用して、表示形式を設定して、デバッグ時の読みやすさを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-154">Use these controls to format minified code for better readability as you debug:</span></span>

#### <span data-ttu-id="a6bf6-155">見栄えの良い印刷 ( `Ctrl+Shift+P` )</span><span class="sxs-lookup"><span data-stu-id="a6bf6-155">Pretty print (`Ctrl+Shift+P`)</span></span> 
<span data-ttu-id="a6bf6-156">JavaScript の規則に従って、改行と中かっこの配置を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-156">Adds line breaks and curly brace alignment per JavaScript conventions.</span></span> <span data-ttu-id="a6bf6-157">このオプションで読みやすくなった圧縮されたコードでも、元のソースコードとは大幅に異なる関数、セレクター、変数名が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-157">Even compressed code that's been made more readable with this option may have function, selector, and variable names that are much different than in your original source code.</span></span> <span data-ttu-id="a6bf6-158">このような場合、[[*ソースマップの切り替え*](#source-maps)] オプションを使用できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-158">In these cases, the [*Toggle source maps*](#source-maps) option might be available.</span></span>

#### <span data-ttu-id="a6bf6-159">ワードラップ ( `Alt+W` )</span><span class="sxs-lookup"><span data-stu-id="a6bf6-159">Word wrap (`Alt+W`)</span></span>
<span data-ttu-id="a6bf6-160">デバッグウィンドウの現在の余白内に収まるようにコードを調整します (水平方向にスクロールする必要がありません)。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-160">Adjusts code to fit within the current margins of the debug window (eliminating the need for horizontal scrolling).</span></span>

### <span data-ttu-id="a6bf6-161">3. コードのスコープ</span><span class="sxs-lookup"><span data-stu-id="a6bf6-161">3. Code scoping</span></span>

<span data-ttu-id="a6bf6-162">[ **Library としてマークを付ける**] () ボタンを使用して、特定のファイルを無視するようにデバッガーを設定することができ `Ctrl+L` ます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-162">You can direct the debugger to ignore certain files with the **Mark as library code** (`Ctrl+L`) button.</span></span> <span data-ttu-id="a6bf6-163">既定では、 [**[マイコードのみをデバッグ**](#toolbar)] ツールバーボタンがオンになっています。つまり、*ライブラリコード*としてマークしたファイルはデバッガーでスキップされ、デバッガーの[呼び出しスタック](#call-stack)には表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-163">By default, the [**Debug just my code**](#toolbar) toolbar button is on, meaning that the debugger will skip over any files that you mark as *library code* and they will not appear in the debugger [call stack](#call-stack).</span></span> <span data-ttu-id="a6bf6-164">ボタンを押し下げ (**[my code] としてマーク**する `Ctrl+L` )、このフラグを削除します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-164">Depressing the button (**Mark as my code**, `Ctrl+L`) will remove this flag.</span></span>

<span data-ttu-id="a6bf6-165">デバッグセッションでライブラリを追跡するために、これらのファイルを編集して既定のリストを保持したり、ドメインまたはファイルの種類に対してワイルドカードを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-165">For keeping track of libraries across debugging sessions, you can edit these files to maintain a default list or add wildcards for a domain or file type:</span></span>

```JavaScript
%APPDATA%\..\LocalLow\Microsoft\F12\header\MyCode.json and %APPDATA%\..\Local\Microsoft\F12\header\MyCode.json
```

#### <span data-ttu-id="a6bf6-166">ソースマップ</span><span class="sxs-lookup"><span data-stu-id="a6bf6-166">Source maps</span></span>

<span data-ttu-id="a6bf6-167">JavaScript または CSS にコンパイルされている言語で記述されたコードに対して [ソースマップの**切り替え**] ボタンが有効になり、*ソースマップ*(元のソースへの中間ファイルのマッピング) が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-167">You will see the **Toggle source maps** button enabled for code written in a language that compiles to JavaScript or CSS and that provides a *source map* (an intermediate file mapping to the original source).</span></span> <span data-ttu-id="a6bf6-168">このオプションを使うと、デバッガーは、デバッグに使用する元のソース (*実際*にはブラウザーで実行されているコンパイル済みのファイルではなく) を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-168">This option directs the debugger to present the original source to use for debugging (rather than the compiled file that's *actually* running in the browser).</span></span>

<span data-ttu-id="a6bf6-169">DevTools は、JavaScript ファイルを生成したコンパイラにマップファイルの名前のコメントが含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-169">The DevTools will check if the compiler that generated the JavaScript file included a comment with the name of the map file.</span></span> <span data-ttu-id="a6bf6-170">たとえば、コンパイラで圧縮された*myfile.js*を*myfile.min.js*する場合、マップファイルmyfile.min.js 生成されることもあり*ます。* これには、次のように圧縮ファイルにコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-170">For example, if a compiler compressed *myfile.js* to *myfile.min.js*, it might also generate a map file, *myfile.min.js.map* and include a comment in the compressed file like this:</span></span>

```JavaScript
//# sourceMappingURL=myfile.min.js.map
```

![[デバッグファイル] タブのコンテキストメニュー](./media/debug_file_contextmenu.png)

<span data-ttu-id="a6bf6-172">DevTools で自動的にマップが見つからない場合は、そのファイルのソースマップを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-172">If the DevTools can't find the map automatically, you can choose a source map for that file.</span></span> <span data-ttu-id="a6bf6-173">ファイルのタブを右クリックして、[**ソースマップの選択**] オプションを探します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-173">Right-click the file's tab to find the **Choose source map** option.</span></span> 

## <span data-ttu-id="a6bf6-174">ツール バー</span><span class="sxs-lookup"><span data-stu-id="a6bf6-174">Toolbar</span></span>

<span data-ttu-id="a6bf6-175">デバッガーの*ツールバー*を使用して、コードの手順を制御したり、ステップごとまたは無視するコードを制御したりします。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-175">Use the debugger *Toolbar* to control how you step through code, and what code to step through or ignore.</span></span> <span data-ttu-id="a6bf6-176">ここでは、コードファイル全体で特定の文字列を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-176">From here you can also do a full text search across your code files for specific strings.</span></span>

![デバッガツールバー](./media/debugger_toolbar.png)

### <span data-ttu-id="a6bf6-178">1. 続行 ( `F5` )/区切り ( `Ctrl+Shift+B` )</span><span class="sxs-lookup"><span data-stu-id="a6bf6-178">1. Continue (`F5`) / Break (`Ctrl+Shift+B`)</span></span>
 <span data-ttu-id="a6bf6-179">**Continue** ( `F5` ) では、コードの実行が次のブレークポイントまで継続されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-179">**Continue** (`F5`) continues code execution to the next breakpoint.</span></span> <span data-ttu-id="a6bf6-180">`F5`ボタンを押すと、過去の中断が繰り返し移動します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-180">Holding down `F5` will repeatedly move past breaks until you release it.</span></span> 

 <span data-ttu-id="a6bf6-181">**Break** ( `Ctrl+Shift+B` ) は、次のステートメントを実行した後でデバッガーに中断します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-181">**Break** (`Ctrl+Shift+B`) will break into the debugger after running the next statement.</span></span>

### <span data-ttu-id="a6bf6-182">2. 手順関数 ( `F11` , `Ctrl+F10` , `Shift+F11` )</span><span class="sxs-lookup"><span data-stu-id="a6bf6-182">2. Step functions (`F11`, `Ctrl+F10`, `Shift+F11`)</span></span>
 <span data-ttu-id="a6bf6-183">**Step into** `F11` 呼び出される関数のステップイン () を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-183">**Step into** (`F11`) steps into the function being called.</span></span> 

 <span data-ttu-id="a6bf6-184">**Step over** `Ctrl+F10` 呼び出される関数のステップオーバー () ステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-184">**Step over** (`Ctrl+F10`) steps over the function being called.</span></span> 

 <span data-ttu-id="a6bf6-185">**手順 out** ( `Shift+F11` ) は、現在の関数と呼び出し元の関数の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-185">**Step out** (`Shift+F11`) steps out of the current function and into the calling function.</span></span> 

 <span data-ttu-id="a6bf6-186">これらのコマンドが使用されているときに関数がない場合、デバッガーは次のステートメントに進みます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-186">The debugger will step to the next statement if it is not at a function when these commands are used.</span></span>

### <span data-ttu-id="a6bf6-187">3. 新しい worker () で休憩 `Ctrl+Shift+W`</span><span class="sxs-lookup"><span data-stu-id="a6bf6-187">3. Break on new worker (`Ctrl+Shift+W`)</span></span>
 <span data-ttu-id="a6bf6-188">新しい[web ワーカー](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers)の作成を中断します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-188">Breaks on the creation of a new [web worker](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers).</span></span>

### <span data-ttu-id="a6bf6-189">4. 例外制御</span><span class="sxs-lookup"><span data-stu-id="a6bf6-189">4. Exception control</span></span>
<span data-ttu-id="a6bf6-190">**例外動作の変更**( `Ctrl+Shift+E` ) デバッガーが例外にどのように反応するかを変更するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-190">**Change exception behavior** (`Ctrl+Shift+E`) opens options to change how the debugger reacts to exceptions.</span></span> <span data-ttu-id="a6bf6-191">既定では、例外はデバッガーによって無視され、[**コンソール**](./console.md)に記録されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-191">By default exceptions are ignored by the debugger and logged to the [**Console**](./console.md).</span></span> <span data-ttu-id="a6bf6-192">*すべての例外に対して中断*するか、コード内のステートメントで処理されていないものだけを選択する (処理されない `try...catch` *例外で中断*) ことができます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-192">You can choose to *Break on all exceptions*, or just those not being handled by `try...catch` statements in your code (*Break on unhandled exceptions*).</span></span>

### <span data-ttu-id="a6bf6-193">5. 検索結果を表示する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-193">5. View search results</span></span>
<span data-ttu-id="a6bf6-194">(現在は無効です。)[**結果の表示/非表示]** [*[ファイル*](#6-find-in-files-ctrlf)の検索] の検索結果の表示を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-194">(Currently disabled.) **Show/Hide results** toggles the display of [*Find in files*](#6-find-in-files-ctrlf) search results.</span></span>

### <span data-ttu-id="a6bf6-195">6. ファイル内で検索 ( `Ctrl+F` )</span><span class="sxs-lookup"><span data-stu-id="a6bf6-195">6. Find in files (`Ctrl+F`)</span></span>
 <span data-ttu-id="a6bf6-196">**[ファイル内を検索**] ( `Ctrl+F` )[*リソースピッカー*](#resource-picker)内で読み込まれたすべてのファイルを使用して、テキスト検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-196">**Find in files** (`Ctrl+F`) runs a text search through all the loaded files within the [*Resource picker*](#resource-picker).</span></span> <span data-ttu-id="a6bf6-197">テキストが見つかると、検索文字列に一致する最初のファイルが開かれます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-197">If the text is found, it opens the first file matching the search string.</span></span> <span data-ttu-id="a6bf6-198">を押す `Enter` か `F3` 、次の検索結果に移動します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-198">Pressing `Enter` or `F3` takes you to the next match.</span></span>

### <span data-ttu-id="a6bf6-199">7. 自分のコードのみをデバッグする ( `Ctrl+J` )</span><span class="sxs-lookup"><span data-stu-id="a6bf6-199">7. Debug just my code (`Ctrl+J`)</span></span>
 <span data-ttu-id="a6bf6-200">**[マイコードのみをデバッグ**] ( `Ctrl+J` ) は、デバッガーの手順に従って、[ライブラリコード](#3-code-scoping)としてマークされているすべてのファイルを含めたり除外したりするためのトグルとして機能します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-200">**Debug just my code** (`Ctrl+J`) acts as a toggle to include or exclude all the files that have been marked as [library code](#3-code-scoping) as you step through the debugger.</span></span>

### <span data-ttu-id="a6bf6-201">8. デバッガー接続</span><span class="sxs-lookup"><span data-stu-id="a6bf6-201">8. Debugger connection</span></span>
<span data-ttu-id="a6bf6-202">**切断/接続デバッガー**は、基本的にはデバッガーのオン/オフスイッチです。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-202">**Disconnect/Connect debugger** is essentially the on/off switch for the debugger.</span></span>

## <span data-ttu-id="a6bf6-203">式</span><span class="sxs-lookup"><span data-stu-id="a6bf6-203">Watches</span></span>

<span data-ttu-id="a6bf6-204">[**ウォッチ**] ウィンドウを使って、ローカルとグローバルの両方のスコープにあるすべてのオブジェクトと変数 (**ローカル**) のカタログを参照し、デバッガーで現在の中断の対象となるステートメントで利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-204">Use the **Watches** pane to browse a catalog of all objects and variables (**Locals**), both in the local and global scope, available to the statement that is the focus of the current break in the debugger.</span></span>

![ウォッチウィンドウ](./media/debugger_watches.png)

<span data-ttu-id="a6bf6-206">ウォッチ (**ウォッチ式の追加**) を追加して、 `Ctrl+W` 編集可能な値をダブルクリックするか、*コンテキストメニュー*から [**値の編集**] を選ぶことで、特定の変数の値を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-206">You can track the value of specific variables as they pass in and out of scope by adding a watch (**Add watch**, `Ctrl+W`) and modify any editable values by double-clicking on it or by selecting **Edit value** from the *Context menu*.</span></span> <span data-ttu-id="a6bf6-207">[**削除**] ( `Ctrl+D` )/[**すべて削除**] ボタンを使用するか、コンテキストメニューからウォッチを消去します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-207">Clear your watches using the **Delete** (`Ctrl+D`) / **Delete all** buttons or from the context menu.</span></span> 

## <span data-ttu-id="a6bf6-208">詳細</span><span class="sxs-lookup"><span data-stu-id="a6bf6-208">Details</span></span>

<span data-ttu-id="a6bf6-209">*詳細*ウィンドウには、[[**呼び出し履歴**](#call-stack)]、[[**ブレーク**](#breakpoints)ポイント]、[ [**DOM ブレークポイント**](#dom-breakpoints)] の各タブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-209">The *Details* pane includes the [**Callstack**](#call-stack), [**Breakpoints**](#breakpoints) and [**DOM breakpoints**](#dom-breakpoints) tabs.</span></span>

### <span data-ttu-id="a6bf6-210">通話スタック</span><span class="sxs-lookup"><span data-stu-id="a6bf6-210">Call stack</span></span>

<span data-ttu-id="a6bf6-211">[**通話スタック**] タブには、現在の実行時点に到達した関数のチェーンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-211">The **Call stack** tab shows the chain of functions that led to the current point of execution.</span></span> <span data-ttu-id="a6bf6-212">現在の関数が一番上に表示され、呼び出し関数は逆の順序で下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-212">The current function appears at the top, and the calling functions appear below it in reverse order.</span></span>

![呼び出し履歴ウィンドウ](./media/debugger_callstack.png)

<span data-ttu-id="a6bf6-214">[ **Library フレームの表示/非表示**] ボタン () は、 `Ctrl+Shift+J` コールスタックからの[ライブラリコード](#3-code-scoping)の出力を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-214">The **Show/Hide library frames** button (`Ctrl+Shift+J`) toggles the output of [library code](#3-code-scoping) from the call stack.</span></span> <span data-ttu-id="a6bf6-215">右クリックのコンテキストメニューの**ライブラリコード**オプション () を使用して、選択した `Ctrl+L` フレームのソースをライブラリコードとしてマーク (またはアンマーク) することができます。 *Context menu*</span><span class="sxs-lookup"><span data-stu-id="a6bf6-215">Use the **Library code** option (`Ctrl+L`) from the right-click *Context menu* to mark (or unmark) the source of the selected frame as library code.</span></span> 

<span data-ttu-id="a6bf6-216">[**非同期フレームの表示/非**表示] ボタンをクリックすると、非同期関数の呼び出しのルートの表示が切り替わります。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-216">The **Show/Hide async frames** button toggles the display of roots for asynchronous function calls.</span></span>

### <span data-ttu-id="a6bf6-217">ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a6bf6-217">Breakpoints</span></span>

<span data-ttu-id="a6bf6-218">[**ブレークポイント**] タブから、条件の設定、条件の設定、無効化、削除などのブレークポイントとイベントのトレースポイントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-218">From the **Breakpoints** tab, you can manage you breakpoints and event tracepoints, including setting conditions, disabling and deleting them.</span></span>

![[ブレークポイント] タブ](./media/debugger_breakpoints.png)

<span data-ttu-id="a6bf6-220">ここでは、デバッグに使用できるさまざまな種類のブレークポイントの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-220">Here's a summary of the different types of breakpoints you can use for debugging.</span></span>

<span data-ttu-id="a6bf6-221">ブレークポイントの種類</span><span class="sxs-lookup"><span data-stu-id="a6bf6-221">Breakpoint type</span></span> | <span data-ttu-id="a6bf6-222">説明</span><span class="sxs-lookup"><span data-stu-id="a6bf6-222">Description</span></span> | <span data-ttu-id="a6bf6-223">設定方法</span><span class="sxs-lookup"><span data-stu-id="a6bf6-223">How to set it</span></span>
:------------ | :------------ | :--------
**<span data-ttu-id="a6bf6-224">まで</span><span class="sxs-lookup"><span data-stu-id="a6bf6-224">Breakpoint</span></span>** | <span data-ttu-id="a6bf6-225">指定したコード行が実行される直前に、デバッガーを中断します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-225">Breaks into the debugger just before the specified line of code is executed.</span></span> <span data-ttu-id="a6bf6-226">1行に1つのステートメントがある場合は、通常のブレークポイントを設定するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-226">Regular breakpoints are easiest to set if you have one statement per line.</span></span> | <span data-ttu-id="a6bf6-227">[デバッグウィンドウ](#debug-window)で、コードの任意の行番号の横にある左余白をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-227">From the [Debug window](#debug-window), click in the left margin next to any line number in the code.</span></span> <span data-ttu-id="a6bf6-228">赤い点が表示され、ブレークポイントが設定されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-228">A red dot appears and the breakpoint is set.</span></span> <span data-ttu-id="a6bf6-229">青色のテキストをクリックすると、任意のブレークポイントのソースにジャンプできます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-229">You can jump into the source of any breakpoint by clicking on its blue text.</span></span>
**<span data-ttu-id="a6bf6-230">条件付きブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a6bf6-230">Conditional breakpoint</span></span>** | <span data-ttu-id="a6bf6-231">指定した条件が*true*と評価された場合は、中断します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-231">Breaks if the specified condition evaluates to *true*.</span></span> <span data-ttu-id="a6bf6-232">これは、 `if(condition)` デバッガーに分割するための基本的な方法です。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-232">This is essentially an `if(condition)`  for breaking into the debugger.</span></span>  | <span data-ttu-id="a6bf6-233">[[ブレークポイント](#breakpoints)] タブで、既存のブレークポイントの上にマウスポインターを置き、[鉛筆] をクリックします (*このブレークポイントに条件を追加*します)。既存のブレークポイントを右クリックして、コンテキストメニューから [条件] を選び**ます**。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-233">From the [Breakpoints](#breakpoints) tab, hover over an existing breakpoint and click the "pencil" button (*Add a condition to this breakpoint*), right-click an existing breakpoint and select **Condition...** from the context menu.</span></span> <span data-ttu-id="a6bf6-234">ブレークポイントの場所で評価する "if" 条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-234">Specify the "if" condition to be evaluated at the breakpoint location.</span></span> 
<span data-ttu-id="a6bf6-235">**XMLHttpRequest ブレークポイント**(オプションの条件付き)</span><span class="sxs-lookup"><span data-stu-id="a6bf6-235">**XMLHttpRequest breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="a6bf6-236">XMLHttpRequest (XHR) 要求が処理されるたびに中断します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-236">Breaks whenever a XMLHttpRequest (XHR) request has been fulfilled.</span></span> <span data-ttu-id="a6bf6-237">XHR `response` オブジェクトは[**ウォッチ**](#watches)ウィンドウから調べることができます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-237">You can inspect the XHR `response` object from the [**Watches**](#watches) pane.</span></span> | <span data-ttu-id="a6bf6-238">[[ブレークポイント](#breakpoints)] タブで、[ *XMLHttpRequest ブレークポイント*] をクリックします (上向き/下向き矢印の付いた丸)。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-238">From the [Breakpoints](#breakpoints) tab, click the *XMLHttpRequest breakpoint* button (circle with up/down arrows).</span></span> <span data-ttu-id="a6bf6-239">上で説明したように、*条件付きブレークポイント*に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-239">You can turn it into a *Conditional breakpoint* as described above.</span></span>
**<span data-ttu-id="a6bf6-240">イベントトレースポイント</span><span class="sxs-lookup"><span data-stu-id="a6bf6-240">Event tracepoint</span></span>** | <span data-ttu-id="a6bf6-241">[`console.log()`](./console/console-api.md#logging-custom-messages)特定のイベントに応答して、指定された文字列を使って呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-241">Calls [`console.log()`](./console/console-api.md#logging-custom-messages) with a specified string in response to a specific event.</span></span> <span data-ttu-id="a6bf6-242">これは、イベントハンドラーコードに直接保存しない一時的なコンソールのログ記録ステートメントに使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-242">Use this for temporary console logging statements that you don't want to save directly in your event handler code.</span></span> | <span data-ttu-id="a6bf6-243">[[ブレークポイント](#breakpoints)] タブで、[*イベントトレースポイント*] (ひし形が稲妻の菱形) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-243">From the [Breakpoints](#breakpoints) tab, click the *Event tracepoint* button (diamond with lightning bolt).</span></span> <span data-ttu-id="a6bf6-244">トリガーの**イベント**の種類とログの**トレース**ステートメントを選びます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-244">Select an **Event** type for the trigger and a **Trace** statement for logging.</span></span>
<span data-ttu-id="a6bf6-245">**イベントのブレークポイント**(オプションの条件付き)</span><span class="sxs-lookup"><span data-stu-id="a6bf6-245">**Event breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="a6bf6-246">指定されたイベントが発生するたびに中断します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-246">Breaks whenever a specified event is fired.</span></span> | <span data-ttu-id="a6bf6-247">[[ブレークポイント](#breakpoints)] タブで、[*イベントブレークポイント*] ボタン (稲妻のマーク付き円) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-247">From the [Breakpoints](#breakpoints) tab, click the *Event breakpoint* button (circle with lightning bolt).</span></span> <span data-ttu-id="a6bf6-248">トリガーの**イベント**の種類を選び、必要に応じて**条件**ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-248">Select an **Event** type for the trigger and optionally, specify a **Condition** statement.</span></span> 
**<span data-ttu-id="a6bf6-249">DOM ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a6bf6-249">DOM breakpoint</span></span>** | <span data-ttu-id="a6bf6-250">サブツリーが変更された場合、その属性が変更された場合、または DOM からデタッチされた場合など、ページで指定した要素が変更されるたびに中断します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-250">Breaks whenever a specified element on the page is mutated, such as when its subtree is modified, its attributes change, or when it is detached from the DOM.</span></span> | <span data-ttu-id="a6bf6-251">[[要素](./elements/dom-breakpoints.md)] タブで、ソース要素を右クリックし、[ *DOM ブレーク*ダウン] オプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-251">From the [Elements](./elements/dom-breakpoints.md) tab, right-click on a source element and select from the *DOM Breakpoints* options.</span></span> <span data-ttu-id="a6bf6-252">*デバッガー*または*要素*パネルの [ [**DOM ブレークポイント**](#dom-breakpoints)] タブを使って、ブレークポイントを管理します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-252">Use the [**DOM breakpoints**](#dom-breakpoints) tab in either the *Debugger* or *Elements* panels to manage your breakpoints.</span></span> 

<span data-ttu-id="a6bf6-253">条件付きブレークポイントとトレースポイントは、デバッガーに侵入したときにスコープ内にあるすべてのローカル変数とグローバル変数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-253">Conditional breakpoints and tracepoints have access to all the local and global variables currently in scope when they break into the debugger.</span></span>

### <span data-ttu-id="a6bf6-254">DOM ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a6bf6-254">DOM breakpoints</span></span>

<span data-ttu-id="a6bf6-255">Dom の変異のブレークポイントを、無効化、削除、再バインドなどの**dom [ブレークポイント**] タブから管理します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-255">Manage your DOM mutation breakpoints from the **DOM breakpoints** tab, including disabling, deleting and rebinding them.</span></span>  <span data-ttu-id="a6bf6-256">[DOM ブレークポイント](./elements/dom-breakpoints.md)は、[**要素**] パネルの*HTML ツリービュー*から設定できます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-256">[DOM breakpoints can be set](./elements/dom-breakpoints.md) from the *HTML tree view* in the **Elements** panel.</span></span>

![[DOM ブレークポイント] タブ](./media/debugger_dom_breakpoints.png)

<span data-ttu-id="a6bf6-258">**デバッガー**の [ *dom ブレークポイント*] タブには、[**要素**] パネルの [ *dom ブレークポイント*] タブと同等の機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-258">The *DOM breakpoints* tab in the **Debugger** provides equivalent functionality to the *DOM breakpoints*\* tab on the **Elements** panel.</span></span>

<span data-ttu-id="a6bf6-259">ここでは、さまざまな種類の[DOM ブレークポイント](./elements/dom-breakpoints.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-259">Here's more on the different types of [DOM breakpoints](./elements/dom-breakpoints.md).</span></span>

## <span data-ttu-id="a6bf6-260">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-260">Shortcuts</span></span>

### <span data-ttu-id="a6bf6-261">ツールバーのショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-261">Toolbar shortcuts</span></span>

<span data-ttu-id="a6bf6-262">操作</span><span class="sxs-lookup"><span data-stu-id="a6bf6-262">Action</span></span> | <span data-ttu-id="a6bf6-263">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-263">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="a6bf6-264">検索</span><span class="sxs-lookup"><span data-stu-id="a6bf6-264">Find</span></span> | `Ctrl` + `F`
<span data-ttu-id="a6bf6-265">続行 (ブレークポイントから)</span><span class="sxs-lookup"><span data-stu-id="a6bf6-265">Continue (from breakpoint)</span></span> | `F5` <span data-ttu-id="a6bf6-266">または</span><span class="sxs-lookup"><span data-stu-id="a6bf6-266">or</span></span> `F8`
<span data-ttu-id="a6bf6-267">クイック続行</span><span class="sxs-lookup"><span data-stu-id="a6bf6-267">Fast continue</span></span> | <span data-ttu-id="a6bf6-268">保留 `F5` または</span><span class="sxs-lookup"><span data-stu-id="a6bf6-268">Hold `F5` or</span></span> `F8`
<span data-ttu-id="a6bf6-269">続行して更新する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-269">Continue and refresh</span></span> | `Ctrl` + `Shift` + `F5`
<span data-ttu-id="a6bf6-270">開拓</span><span class="sxs-lookup"><span data-stu-id="a6bf6-270">Break</span></span> | `Ctrl` + `Shift` + `B`
<span data-ttu-id="a6bf6-271">手順</span><span class="sxs-lookup"><span data-stu-id="a6bf6-271">Step into</span></span> | `F11`
<span data-ttu-id="a6bf6-272">ステップオーバー</span><span class="sxs-lookup"><span data-stu-id="a6bf6-272">Step over</span></span> | `F10`
<span data-ttu-id="a6bf6-273">ステップアウト</span><span class="sxs-lookup"><span data-stu-id="a6bf6-273">Step out</span></span> | `Shift` + `F11`
<span data-ttu-id="a6bf6-274">新しい作業者による休憩</span><span class="sxs-lookup"><span data-stu-id="a6bf6-274">Break on new worker</span></span> | `Ctrl` + `Shift` + `W`
<span data-ttu-id="a6bf6-275">例外動作を変更する (メニューを開く)</span><span class="sxs-lookup"><span data-stu-id="a6bf6-275">Change exception behavior (opens menu)</span></span> | `Ctrl` + `Shift` + `E`
<span data-ttu-id="a6bf6-276">マイコードのみをデバッグする</span><span class="sxs-lookup"><span data-stu-id="a6bf6-276">Debug just my code</span></span> | `Ctrl` + `J`

### <span data-ttu-id="a6bf6-277">リソース選択のショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-277">Resource picker shortcuts</span></span>

<span data-ttu-id="a6bf6-278">操作</span><span class="sxs-lookup"><span data-stu-id="a6bf6-278">Action</span></span> | <span data-ttu-id="a6bf6-279">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-279">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="a6bf6-280">自分のコード/ライブラリコードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="a6bf6-280">Mark as my code / library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="a6bf6-281">ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="a6bf6-281">Open file</span></span> | `Ctrl`<span data-ttu-id="a6bf6-282"> + `O`, `Ctrl` + </span><span class="sxs-lookup"><span data-stu-id="a6bf6-282"> + `O`, `Ctrl` + </span></span>`P`
<span data-ttu-id="a6bf6-283">すべてのファイルを検索する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-283">Search all files</span></span> | `Ctrl` + `Shift` + `F`

### <span data-ttu-id="a6bf6-284">デバッグウィンドウのショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-284">Debug window shortcuts</span></span>

<span data-ttu-id="a6bf6-285">操作</span><span class="sxs-lookup"><span data-stu-id="a6bf6-285">Action</span></span> | <span data-ttu-id="a6bf6-286">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-286">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="a6bf6-287">ブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-287">Remove breakpoint</span></span> | `F9`
<span data-ttu-id="a6bf6-288">ブレークポイントを無効にする</span><span class="sxs-lookup"><span data-stu-id="a6bf6-288">Disable breakpoint</span></span> | `Ctrl` + `F9`
<span data-ttu-id="a6bf6-289">条件付きブレークポイント...</span><span class="sxs-lookup"><span data-stu-id="a6bf6-289">Conditional breakpoint...</span></span> | `Alt` + `F9`
<span data-ttu-id="a6bf6-290">コピー</span><span class="sxs-lookup"><span data-stu-id="a6bf6-290">Copy</span></span> | `Ctrl` + `C`
<span data-ttu-id="a6bf6-291">Save</span><span class="sxs-lookup"><span data-stu-id="a6bf6-291">Save</span></span> | `Ctrl` + `S`
<span data-ttu-id="a6bf6-292">行に移動...</span><span class="sxs-lookup"><span data-stu-id="a6bf6-292">Go to line...</span></span> | `Ctrl` + `G`
<span data-ttu-id="a6bf6-293">次のステートメントを表示する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-293">Show next statement</span></span> | `Alt` + `Num` + `*`
<span data-ttu-id="a6bf6-294">カーソルの実行</span><span class="sxs-lookup"><span data-stu-id="a6bf6-294">Run to cursor</span></span> | `Ctrl` + `F10`
<span data-ttu-id="a6bf6-295">次のステートメントを設定する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-295">Set next statement</span></span> | `Ctrl` + `Shift` + `F10`
<span data-ttu-id="a6bf6-296">ファイルピッカーに表示</span><span class="sxs-lookup"><span data-stu-id="a6bf6-296">Show in file picker</span></span> | `Ctrl` + `Alt` + `P`
<span data-ttu-id="a6bf6-297">ファイルの定義に移動する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-297">Go to definition in file</span></span> | `Ctrl`+`D`
<span data-ttu-id="a6bf6-298">ファイルで参照を検索する</span><span class="sxs-lookup"><span data-stu-id="a6bf6-298">Find references in file</span></span> | `Ctrl` + `Shift` + `D`
<span data-ttu-id="a6bf6-299">きれいに印刷</span><span class="sxs-lookup"><span data-stu-id="a6bf6-299">Pretty print</span></span> | `Ctrl` + `Shift` + `P`
<span data-ttu-id="a6bf6-300">ワードラップ</span><span class="sxs-lookup"><span data-stu-id="a6bf6-300">Word wrap</span></span> | `Alt` + `W`
<span data-ttu-id="a6bf6-301">自分のコード/ライブラリコードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="a6bf6-301">Mark as my code/library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="a6bf6-302">エディターでタブを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-302">Disable/Enable tabs in the editor.</span></span> <span data-ttu-id="a6bf6-303">**注:** キーボードを使ってデバッガー内を移動している場合は、tab キーを使用してタブ表示を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-303">**Note:** if you're using the keyboard to navigate in the Debugger, you won't be able to tab out of the editor until you disable tabbing</span></span> | `Ctrl` + `M`

### <span data-ttu-id="a6bf6-304">ウォッチウィンドウのショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-304">Shortcuts for Watches pane</span></span>

<span data-ttu-id="a6bf6-305">操作</span><span class="sxs-lookup"><span data-stu-id="a6bf6-305">Action</span></span> | <span data-ttu-id="a6bf6-306">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-306">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="a6bf6-307">ウォッチ式の追加</span><span class="sxs-lookup"><span data-stu-id="a6bf6-307">Add watch</span></span> | `Ctrl` + `W`
<span data-ttu-id="a6bf6-308">ウォッチ式の削除</span><span class="sxs-lookup"><span data-stu-id="a6bf6-308">Delete watch</span></span> | `Ctrl` + `D`

### <span data-ttu-id="a6bf6-309">詳細ウィンドウのショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-309">Shortcuts for Details pane</span></span>

| <span data-ttu-id="a6bf6-310">操作</span><span class="sxs-lookup"><span data-stu-id="a6bf6-310">Action</span></span>                             | <span data-ttu-id="a6bf6-311">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a6bf6-311">Shortcut</span></span>                 |
|:-----------------------------------|:-------------------------|
| <span data-ttu-id="a6bf6-312">ライブラリコードからフレームを表示/非表示にする</span><span class="sxs-lookup"><span data-stu-id="a6bf6-312">Show/Hide frames from library code</span></span> | `Ctrl` + `Shift` + `J`   |
| <span data-ttu-id="a6bf6-313">すべてのブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="a6bf6-313">Enable all breakpoints</span></span>             | `Ctrl` + `Shift` + `F11` |
