---
description: デバッガーを使用して、コードの手順とトラブルシューティングを行います。
title: デバッガー - DevTools (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, デバッガー, デバッグ, ブレークポイント, ウォッチ, サービス ワーカー, キャッシュ API, Web ストレージ, Cookie
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cc2d7ef0d3ee5c16b8cbc73745a8f9ea30bd9d09
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235060"
---
# <span data-ttu-id="7c4a8-104">デバッガー - DevTools (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-104">Debugger - DevTools (EdgeHTML)</span></span>

<span data-ttu-id="7c4a8-105">デバッガーを **使って** 、コードのステップ実行、ウォッチとブレークポイントの設定、コードのライブ 編集、キャッシュの検査を行います。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-105">Use the **Debugger** to step through code, set watches and breakpoints, live edit your code and inspect your caches.</span></span> <span data-ttu-id="7c4a8-106">次の方法でコードをテストおよびトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-106">Test and troubleshoot your code by:</span></span>

- <span data-ttu-id="7c4a8-107">[読み込](#resource-picker)[まれたソース ファイル](#file-search)からのコードの参照と検索</span><span class="sxs-lookup"><span data-stu-id="7c4a8-107">[Browsing](#resource-picker) and [searching](#file-search) code from your loaded source files</span></span>
- <span data-ttu-id="7c4a8-108">[コードをステップ実行する場合](#toolbar) の実行フローの制御</span><span class="sxs-lookup"><span data-stu-id="7c4a8-108">[Controlling the execution flow](#toolbar) as you step through your code</span></span>
- <span data-ttu-id="7c4a8-109">[サービス ワーカーとキャッシュ、Cookie、Web](./storage.md#cache-manager)ストレージなど、ページ ストレージ[リソース](./storage.md#cookies-list)[の管理](./storage.md#local-and-session-storage-managers)[](./service-workers.md)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-109">[Managing page storage resources](./storage.md#cache-manager), including the [service workers and cache](./service-workers.md), [cookies](./storage.md#cookies-list) and [web storage](./storage.md#local-and-session-storage-managers)</span></span>  
- <span data-ttu-id="7c4a8-110">[ブレークポイントを設定し、コードの実行](#debug-window) に合ったライブ編集を行う</span><span class="sxs-lookup"><span data-stu-id="7c4a8-110">[Setting breakpoints and live editing](#debug-window) your code as it runs</span></span>
- <span data-ttu-id="7c4a8-111">[デバッグ時のローカル変数の追跡](#watches) と編集</span><span class="sxs-lookup"><span data-stu-id="7c4a8-111">[Tracking and editing local variables](#watches) as you debug</span></span>
- <span data-ttu-id="7c4a8-112">[必要に応じて、呼び出し履歴](#call-stack) の非同期コードとライブラリ コードを非表示または表示する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-112">[Hiding or showing asynchronous code and library code](#call-stack) from your callstack as needed</span></span>
- <span data-ttu-id="7c4a8-113">[XmlHttpRequests、](#breakpoints) イベント、DOM の変更に特化 [したブレークポイントを追加する](#dom-breakpoints)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-113">[Adding specialized breakpoints](#breakpoints) for XmlHttpRequests, events and [DOM mutations](#dom-breakpoints)</span></span>

![Microsoft Edge DevTools デバッガー](./media/debugger.png)

<span data-ttu-id="7c4a8-115">デバッグ セッションを開始するには、3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-115">There are three ways to begin a debugging session.</span></span>

1. **<span data-ttu-id="7c4a8-116">ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-116">Set a breakpoint.</span></span>** <span data-ttu-id="7c4a8-117">コードの実行が到達すると、デバッガーを入力し、コードをステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-117">When the execution of your code reaches it, you'll enter the debugger and be able to step through your code.</span></span>
2. **<span data-ttu-id="7c4a8-118">コードのブレークを開始します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-118">Initiate a break in code.</span></span>** <span data-ttu-id="7c4a8-119">Click the [**Break**](#toolbar) *(pause* icon) toolbar button or `Ctrl+Shift+B` .</span><span class="sxs-lookup"><span data-stu-id="7c4a8-119">Click the [**Break**](#toolbar) (*pause* icon) toolbar button or `Ctrl+Shift+B`.</span></span> <span data-ttu-id="7c4a8-120">デバッガーは、次の実行ステートメントでブレークします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-120">The debugger will break on the next statement of execution.</span></span>
3. **<span data-ttu-id="7c4a8-121">例外の動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-121">Set exception behavior.</span></span>** <span data-ttu-id="7c4a8-122">コードで [**例外がスロー**](#toolbar) された場合にデバッガーに割り込むには、[例外動作の変更] メニュー ( `Ctrl+Shift+E` ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-122">Use the [**Change exception behavior**](#toolbar) menu (`Ctrl+Shift+E`) to break into the debugger when your code throws an exception.</span></span> <span data-ttu-id="7c4a8-123">既定では、デバッガーは例外でブレーク\*\* しないに設定されますが、コンソールに記録されます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-123">By default, the debugger is set to *Never break on exceptions*, but they are logged to the console.</span></span>

## <span data-ttu-id="7c4a8-124">リソースピッカー</span><span class="sxs-lookup"><span data-stu-id="7c4a8-124">Resource picker</span></span>

<span data-ttu-id="7c4a8-125">多くの場合、デバッグの最初の手順は、トラブルシューティングを行うコードにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-125">Often the first step in debugging is to set breakpoints in the code you're looking to troubleshoot.</span></span> <span data-ttu-id="7c4a8-126">ページによって現在読み込まれているすべてのコード ファイルは、.html、.css、.js ファイルなど、[リソースの選択] ウィンドウ*から検索*できます。 \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="7c4a8-126">You can find all the code files currently loaded by the page from the *Resource picker* pane, including *.html, .css* and *.js* files.</span></span>

 <span data-ttu-id="7c4a8-127">ファイル エントリをクリックすると、そのファイルのタブが [[デバッグ](#debug-window) ] ウィンドウに開き、ファイル名のテキストが太字で表示されます *(devtools ガイド* のファイル名は上記の図を参照)。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-127">Clicking on a file entry will open a tab for that file in the [Debug window](#debug-window) and bold the text of the file name to indicate this (as *devtools-guide* file name is in the illustration above).</span></span> <span data-ttu-id="7c4a8-128">その後、[デバッグ] ウィンドウからそのファイル内にブレークポイントを [設定できます](#debug-window)。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-128">You can then set breakpoints within that file from the [Debug window](#debug-window).</span></span>

![デバッガー リソース ピッカー](./media/debugger_resource_picker.png)

<span data-ttu-id="7c4a8-130">リソース*ピッカー*のコンテキスト メニューから、ファイルをライブラリ コード **(** ) としてマークすることもできます。デバッガーでこのコードをスキップして、[呼び出し履歴] ウィンドウで非表示にすることもできます `Ctrl+L` [](#debug-window)。 [ \*\*\*\* ](#call-stack)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-130">From the *Resource picker* context menu, you can also mark a file as **library code** (`Ctrl+L`), giving you the option to [skip over that code in the debugger](#debug-window) and [hide it from the **Call stack** pane](#call-stack).</span></span> <span data-ttu-id="7c4a8-131">(または) を再びクリックすると、ファイルをコードまたはライブラリ コードとして以前の値 `Ctrl+L` *に\*\*戻します*。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-131">Clicking (or `Ctrl+L`) again will toggle the file back to its previous value as *my code* or *library code*.</span></span>

### <span data-ttu-id="7c4a8-132">ファイル検索</span><span class="sxs-lookup"><span data-stu-id="7c4a8-132">File search</span></span>

<span data-ttu-id="7c4a8-133">ソースで*検索しようとしている*特定のコード文字列がある場合は、[ファイル内の検索] コマンド ( `Ctrl` + `Shift` + `F` ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-133">Use the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="7c4a8-134">ツール バーには、正規表現を含むさまざまな検索オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-134">The toolbar provides different search options, including regular expressions.</span></span> <span data-ttu-id="7c4a8-135">検索結果をクリックすると、指定したファイルと行 *に* [デバッグ] ウィンドウがフォーカスされます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-135">Clicking on a search result will focus the *Debug window* on the specified file and line.</span></span>

![デバッガー ファイル検索ウィンドウ](./media/debugger_file_search.png)

## <span data-ttu-id="7c4a8-137">[デバッグ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7c4a8-137">Debug window</span></span>

<span data-ttu-id="7c4a8-138">[ *デバッグ] ウィンドウ* では、ブレークポイントの設定、コードのステップ実行、デバッグ時のスクリプトのライブ 編集を行います。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-138">The *Debug window* is where you set your breakpoints, step through code, and live edit your script as you debug.</span></span> <span data-ttu-id="7c4a8-139">任意のスクリプト コマンドの左側をクリックして、ブレークポイントを追加 (または削除) **します**。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-139">Click to the left of any script command to add (or remove) a **Breakpoint**.</span></span> <span data-ttu-id="7c4a8-140">右クリックのコンテキスト メニューまたは [[**ブレークポイント**](#breakpoints)]\*\* ウィンドウを使用して、デバッガーが*True*と評価された場合にデバッガーがブレークする論理式を指定して、ブレークポイントに条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-140">Use the right-click context menu or [**Breakpoints**](#breakpoints) pane to *Add a condition* to the breakpoint by supplying a logical expression that causes the debugger to break if it evaluates *True* at that location.</span></span>

![デバッグ ウィンドウ コマンド](./media/debugger_window.png)

<span data-ttu-id="7c4a8-142">デバッグ ウィンドウのその他の機能には、次のコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-142">Other features of the debug window include controls for:</span></span>

### <span data-ttu-id="7c4a8-143">1. コード編集</span><span class="sxs-lookup"><span data-stu-id="7c4a8-143">1. Code editing</span></span>

<span data-ttu-id="7c4a8-144">デバッグ セッション中に JavaScript ライブを編集できます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-144">You can edit your JavaScript live during a debugging session.</span></span> <span data-ttu-id="7c4a8-145">変更を行った後、[保存 ( ) ] をクリックして、コードのそのセクションが次に実行される時 <strong> </strong> に変更 `Ctrl+S` をテストします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-145">Once you make your changes, click <strong>Save</strong> (`Ctrl+S`) to test your changes next time that section of code runs.</span></span> <span data-ttu-id="7c4a8-146">保存されていないコード変更がある場合は、[デバッグ] ウィンドウタブのファイル名の前にアスタリスク (\*) *が表示* されます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-146">If you have unsaved code changes, an asterisk (\*) will appear before the file name in the *Debug window* tab.</span></span>

<span data-ttu-id="7c4a8-147">[元 **のドキュメントと比較] ボタン** をクリックして、変更した変更の違いを表示します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-147">Click the **Compare document to original** button to view the diff of what you changed.</span></span>

![デバッガーで編集されたコードの差分ビュー](./media/debugger_edit_code.png)

<span data-ttu-id="7c4a8-149">次の制約に注意してください。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-149">Please be aware of the following constraints:</span></span>

- <span data-ttu-id="7c4a8-150">スクリプトの編集は、外部 *の .js ファイル* でのみ機能します (.html に `<script>` 埋め込 *まれているのではなく*)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-150">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span></span>
- <span data-ttu-id="7c4a8-151">編集内容はメモリに保存され、ドキュメントが再読み込みされた場合にフラッシュされます。そのため、ハンドラー内で編集を実行できません。たとえば、 `DOMContentLoaded`</span><span class="sxs-lookup"><span data-stu-id="7c4a8-151">Edits are saved in memory and flushed when the document is reloaded, thus you won't be able to run edits inside a `DOMContentLoaded` handler, for example</span></span>
- <span data-ttu-id="7c4a8-152">現在、DevTools からディスクに編集\*\*\*\* 内容を保存する方法 ([名前を付けて保存] オプションなど) はありません。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-152">Currently there's no way (such as a **Save As** option) to save your edits to disk from the DevTools</span></span>

### <span data-ttu-id="7c4a8-153">2. コードの書式設定</span><span class="sxs-lookup"><span data-stu-id="7c4a8-153">2. Code formatting</span></span>

<span data-ttu-id="7c4a8-154">以下のコントロールを使用して、デバッグ時に読みやすさを向上するために、コードの形式を変更します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-154">Use these controls to format minified code for better readability as you debug:</span></span>

#### <span data-ttu-id="7c4a8-155">Pretty print ( `Ctrl+Shift+P` )</span><span class="sxs-lookup"><span data-stu-id="7c4a8-155">Pretty print (`Ctrl+Shift+P`)</span></span> 
<span data-ttu-id="7c4a8-156">JavaScript の規則に従って改行と中かっこの配置を追加します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-156">Adds line breaks and curly brace alignment per JavaScript conventions.</span></span> <span data-ttu-id="7c4a8-157">このオプションで読み取りが可能な圧縮コードでも、元のソース コードとは大きな違いがある関数名、セレクター名、変数名を持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-157">Even compressed code that's been made more readable with this option may have function, selector, and variable names that are much different than in your original source code.</span></span> <span data-ttu-id="7c4a8-158">このような場合は、[ソース マップの [*切り替え*](#source-maps) ] オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-158">In these cases, the [*Toggle source maps*](#source-maps) option might be available.</span></span>

#### <span data-ttu-id="7c4a8-159">Word の折り返し ( `Alt+W` )</span><span class="sxs-lookup"><span data-stu-id="7c4a8-159">Word wrap (`Alt+W`)</span></span>
<span data-ttu-id="7c4a8-160">デバッグ ウィンドウの現在の余白に収まるコードを調整します (水平方向のスクロールは不要です)。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-160">Adjusts code to fit within the current margins of the debug window (eliminating the need for horizontal scrolling).</span></span>

### <span data-ttu-id="7c4a8-161">3. コードのスコープ</span><span class="sxs-lookup"><span data-stu-id="7c4a8-161">3. Code scoping</span></span>

<span data-ttu-id="7c4a8-162">[ライブラリ コード ( ) としてマーク\*\*\*\*] ボタンを使用して、特定のファイルを無視するようにデバッガー `Ctrl+L` に指示できます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-162">You can direct the debugger to ignore certain files with the **Mark as library code** (`Ctrl+L`) button.</span></span> <span data-ttu-id="7c4a8-163">既定では、[デバッグ[\*\*\*\*](#toolbar)] ツール バー ボタンがオンになっています。つまり、デバッガーはライブラリ コードとしてマークしたファイル\*\* をスキップし、デバッガー呼び出しスタックに表示[されません](#call-stack)。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-163">By default, the [**Debug just my code**](#toolbar) toolbar button is on, meaning that the debugger will skip over any files that you mark as *library code* and they will not appear in the debugger [call stack](#call-stack).</span></span> <span data-ttu-id="7c4a8-164">ボタン ([**コードとしてマーク])** を押すと `Ctrl+L` 、このフラグが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-164">Depressing the button (**Mark as my code**, `Ctrl+L`) will remove this flag.</span></span>

<span data-ttu-id="7c4a8-165">デバッグ セッション全体でライブラリを追跡するには、これらのファイルを編集して既定のリストを維持するか、ドメインまたはファイルの種類に対するワイルドカードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-165">For keeping track of libraries across debugging sessions, you can edit these files to maintain a default list or add wildcards for a domain or file type:</span></span>

```JavaScript
%APPDATA%\..\LocalLow\Microsoft\F12\header\MyCode.json and %APPDATA%\..\Local\Microsoft\F12\header\MyCode.json
```

#### <span data-ttu-id="7c4a8-166">ソース マップ</span><span class="sxs-lookup"><span data-stu-id="7c4a8-166">Source maps</span></span>

<span data-ttu-id="7c4a8-167">JavaScript または\*\*\*\* CSS にコンパイルされ、ソース マップ *(元*のソースへの中間ファイル マッピング) を提供する言語で記述されたコードに対して、[ソース マップの切り替え] ボタンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-167">You will see the **Toggle source maps** button enabled for code written in a language that compiles to JavaScript or CSS and that provides a *source map* (an intermediate file mapping to the original source).</span></span> <span data-ttu-id="7c4a8-168">このオプションは、デバッグに使用する元のソース (ブラウザーで実際に実行されているコンパイル済みファイルではなく)\*\* をデバッガーに表示します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-168">This option directs the debugger to present the original source to use for debugging (rather than the compiled file that's *actually* running in the browser).</span></span>

<span data-ttu-id="7c4a8-169">DevTools は、JavaScript ファイルを生成したコンパイラに、マップ ファイルの名前のコメントが含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-169">The DevTools will check if the compiler that generated the JavaScript file included a comment with the name of the map file.</span></span> <span data-ttu-id="7c4a8-170">たとえば、コンパイラが *myfile.js* から *myfile.min.js*に圧縮されている場合は、次のようなマップ ファイル *myfile.min.js.map* を生成し、圧縮ファイルにコメントを含めることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-170">For example, if a compiler compressed *myfile.js* to *myfile.min.js*, it might also generate a map file, *myfile.min.js.map* and include a comment in the compressed file like this:</span></span>

```JavaScript
//# sourceMappingURL=myfile.min.js.map
```

![[デバッグ ファイル] タブのショートカット メニュー](./media/debug_file_contextmenu.png)

<span data-ttu-id="7c4a8-172">DevTools がマップを自動的に見つからない場合は、そのファイルのソース マップを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-172">If the DevTools can't find the map automatically, you can choose a source map for that file.</span></span> <span data-ttu-id="7c4a8-173">ファイルのタブを右クリックして、[ソース マップの選択 **] オプションを探** します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-173">Right-click the file's tab to find the **Choose source map** option.</span></span> 

## <span data-ttu-id="7c4a8-174">ツール バー</span><span class="sxs-lookup"><span data-stu-id="7c4a8-174">Toolbar</span></span>

<span data-ttu-id="7c4a8-175">デバッガーツール バー *を使用* して、コードのステップ実行方法と、ステップ実行または無視するコードを制御します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-175">Use the debugger *Toolbar* to control how you step through code, and what code to step through or ignore.</span></span> <span data-ttu-id="7c4a8-176">ここから、コード ファイル全体で特定の文字列を検索するフルテキスト検索を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-176">From here you can also do a full text search across your code files for specific strings.</span></span>

![デバッガー ツール バー](./media/debugger_toolbar.png)

### <span data-ttu-id="7c4a8-178">1. 続行 ( `F5` ) / ブレーク ( `Ctrl+Shift+B` )</span><span class="sxs-lookup"><span data-stu-id="7c4a8-178">1. Continue (`F5`) / Break (`Ctrl+Shift+B`)</span></span>
 <span data-ttu-id="7c4a8-179">**Continue** ( `F5` ) は、コードの実行を次のブレークポイントまで続行します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-179">**Continue** (`F5`) continues code execution to the next breakpoint.</span></span> <span data-ttu-id="7c4a8-180">押し続 `F5` けすると、解放されるまで、過去の区切りが繰り返し移動します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-180">Holding down `F5` will repeatedly move past breaks until you release it.</span></span> 

 <span data-ttu-id="7c4a8-181">**Break** ( `Ctrl+Shift+B` ) は、次のステートメントの実行後にデバッガーに割り込みます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-181">**Break** (`Ctrl+Shift+B`) will break into the debugger after running the next statement.</span></span>

### <span data-ttu-id="7c4a8-182">2. ステップ関数 ( `F11` , `Ctrl+F10` , `Shift+F11` )</span><span class="sxs-lookup"><span data-stu-id="7c4a8-182">2. Step functions (`F11`, `Ctrl+F10`, `Shift+F11`)</span></span>
 <span data-ttu-id="7c4a8-183">**呼び出** される `F11` 関数に () ステップ 実行します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-183">**Step into** (`F11`) steps into the function being called.</span></span> 

 <span data-ttu-id="7c4a8-184">**呼び** 出される `Ctrl+F10` 関数をステップ オーバー () します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-184">**Step over** (`Ctrl+F10`) steps over the function being called.</span></span> 

 <span data-ttu-id="7c4a8-185">**ステップ アウト** ( `Shift+F11` ) は、現在の関数から呼び出し元の関数にステップ アウトします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-185">**Step out** (`Shift+F11`) steps out of the current function and into the calling function.</span></span> 

 <span data-ttu-id="7c4a8-186">デバッガーは、これらのコマンドが使用されている場合に関数に含されていない場合は、次のステートメントにステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-186">The debugger will step to the next statement if it is not at a function when these commands are used.</span></span>

### <span data-ttu-id="7c4a8-187">3. 新しいワーカーを壊す ( `Ctrl+Shift+W` )</span><span class="sxs-lookup"><span data-stu-id="7c4a8-187">3. Break on new worker (`Ctrl+Shift+W`)</span></span>
 <span data-ttu-id="7c4a8-188">新しい Web ワーカーの作成を [行います](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers)。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-188">Breaks on the creation of a new [web worker](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers).</span></span>

### <span data-ttu-id="7c4a8-189">4. 例外コントロール</span><span class="sxs-lookup"><span data-stu-id="7c4a8-189">4. Exception control</span></span>
<span data-ttu-id="7c4a8-190">**例外の動作** を変更する ( `Ctrl+Shift+E` ) オプションを開き、デバッガーが例外に対応する方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-190">**Change exception behavior** (`Ctrl+Shift+E`) opens options to change how the debugger reacts to exceptions.</span></span> <span data-ttu-id="7c4a8-191">既定では、デバッガーによって例外が無視され、コンソールに記録 [**されます**](./console.md)。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-191">By default exceptions are ignored by the debugger and logged to the [**Console**](./console.md).</span></span> <span data-ttu-id="7c4a8-192">すべての例外に対して *Break*を実行するか、コード内のステートメントによって処理されない例外 (未処理の例外でブレーク) を `try...catch` *選択できます*。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-192">You can choose to *Break on all exceptions*, or just those not being handled by `try...catch` statements in your code (*Break on unhandled exceptions*).</span></span>

### <span data-ttu-id="7c4a8-193">5. 検索結果を表示する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-193">5. View search results</span></span>
<span data-ttu-id="7c4a8-194">(現在無効になっています。) **結果の表示/非表示を切** り替えるには、ファイルの [*検索結果で検索の表示を*](#6-find-in-files-ctrlf) 切り替える。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-194">(Currently disabled.) **Show/Hide results** toggles the display of [*Find in files*](#6-find-in-files-ctrlf) search results.</span></span>

### <span data-ttu-id="7c4a8-195">6. ファイル内の検索 ( `Ctrl+F` )</span><span class="sxs-lookup"><span data-stu-id="7c4a8-195">6. Find in files (`Ctrl+F`)</span></span>
 <span data-ttu-id="7c4a8-196">**Find in files** ( `Ctrl+F` ) runs a text search through all the loaded files within the Resource [*picker*](#resource-picker).</span><span class="sxs-lookup"><span data-stu-id="7c4a8-196">**Find in files** (`Ctrl+F`) runs a text search through all the loaded files within the [*Resource picker*](#resource-picker).</span></span> <span data-ttu-id="7c4a8-197">テキストが見つかった場合は、検索文字列に一致する最初のファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-197">If the text is found, it opens the first file matching the search string.</span></span> <span data-ttu-id="7c4a8-198">次 `Enter` のマッチ `F3` に移動するか押します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-198">Pressing `Enter` or `F3` takes you to the next match.</span></span>

### <span data-ttu-id="7c4a8-199">7. 自分のコード ( ) をデバッグする `Ctrl+J`</span><span class="sxs-lookup"><span data-stu-id="7c4a8-199">7. Debug just my code (`Ctrl+J`)</span></span>
 <span data-ttu-id="7c4a8-200">**デバッグ専用のコード**( ) は、デバッガーをステップ実行する間にライブラリ コードとしてマークされているファイルを含めるか除外するかの切り `Ctrl+J` 替えとして機能します。 [](#3-code-scoping)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-200">**Debug just my code** (`Ctrl+J`) acts as a toggle to include or exclude all the files that have been marked as [library code](#3-code-scoping) as you step through the debugger.</span></span>

### <span data-ttu-id="7c4a8-201">8. デバッガー接続</span><span class="sxs-lookup"><span data-stu-id="7c4a8-201">8. Debugger connection</span></span>
<span data-ttu-id="7c4a8-202">**切断/接続デバッガーは** 、基本的にデバッガーのオン/オフ スイッチです。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-202">**Disconnect/Connect debugger** is essentially the on/off switch for the debugger.</span></span>

## <span data-ttu-id="7c4a8-203">ウォッチ</span><span class="sxs-lookup"><span data-stu-id="7c4a8-203">Watches</span></span>

<span data-ttu-id="7c4a8-204">ウォッチ ウィンドウを **使用** して、デバッガーの現在のブレークのフォーカスであるステートメントで使用できる、ローカル スコープとグローバル スコープの両方のすべてのオブジェクトと変数 (**ローカル**) のカタログを参照します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-204">Use the **Watches** pane to browse a catalog of all objects and variables (**Locals**), both in the local and global scope, available to the statement that is the focus of the current break in the debugger.</span></span>

![[ウォッチ] ウィンドウ](./media/debugger_watches.png)

<span data-ttu-id="7c4a8-206">特定の変数の値をスコープ外に渡す場合は、ウォッチ **(** ウォッチの追加 , ) を追加し、編集可能な値を変更するには、変数をダブルクリックするか、コンテキスト メニューから [値の編集] を選択します。 `Ctrl+W` \*\*\*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="7c4a8-206">You can track the value of specific variables as they pass in and out of scope by adding a watch (**Add watch**, `Ctrl+W`) and modify any editable values by double-clicking on it or by selecting **Edit value** from the *Context menu*.</span></span> <span data-ttu-id="7c4a8-207">Delete ( ) / **Delete** all buttons or from the context menu を使ってウォッチ `Ctrl+D` をクリアします。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7c4a8-207">Clear your watches using the **Delete** (`Ctrl+D`) / **Delete all** buttons or from the context menu.</span></span> 

## <span data-ttu-id="7c4a8-208">詳細</span><span class="sxs-lookup"><span data-stu-id="7c4a8-208">Details</span></span>

<span data-ttu-id="7c4a8-209">[*詳細]* ウィンドウには、[[**コールスタック] タブ、[ブレークポイント**](#call-stack)[**] タブ、[DOM**](#breakpoints) [**ブレークポイント] タブがあります**](#dom-breakpoints)。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-209">The *Details* pane includes the [**Callstack**](#call-stack), [**Breakpoints**](#breakpoints) and [**DOM breakpoints**](#dom-breakpoints) tabs.</span></span>

### <span data-ttu-id="7c4a8-210">コール スタック</span><span class="sxs-lookup"><span data-stu-id="7c4a8-210">Call stack</span></span>

<span data-ttu-id="7c4a8-211">[ **呼び出し履歴** ] タブには、現在の実行ポイントに導いた関数のチェーンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-211">The **Call stack** tab shows the chain of functions that led to the current point of execution.</span></span> <span data-ttu-id="7c4a8-212">現在の関数は一番上に表示され、呼び出し元の関数は逆の順序でその下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-212">The current function appears at the top, and the calling functions appear below it in reverse order.</span></span>

![コール スタック ウィンドウ](./media/debugger_callstack.png)

<span data-ttu-id="7c4a8-214">[ **ライブラリ フレームの表示/非表示]** ボタン ( ) は、呼び出し履歴からライブラリ コードの `Ctrl+Shift+J` [出力を](#3-code-scoping) 切り替えます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-214">The **Show/Hide library frames** button (`Ctrl+Shift+J`) toggles the output of [library code](#3-code-scoping) from the call stack.</span></span> <span data-ttu-id="7c4a8-215">右クリック**のコンテキスト メニュー**の [ライブラリ コード] オプション ( ) を使用して、選択したフレームのソースをライブラリ コードとしてマーク (またはマーク解除 `Ctrl+L` )\*\* します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-215">Use the **Library code** option (`Ctrl+L`) from the right-click *Context menu* to mark (or unmark) the source of the selected frame as library code.</span></span> 

<span data-ttu-id="7c4a8-216">非同期 **関数呼び出しのルート** の表示を切り替えるには、[非同期フレームの表示/非表示] ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-216">The **Show/Hide async frames** button toggles the display of roots for asynchronous function calls.</span></span>

### <span data-ttu-id="7c4a8-217">ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="7c4a8-217">Breakpoints</span></span>

<span data-ttu-id="7c4a8-218">[ **ブレークポイント]** タブでは、ブレークポイントとイベント トレースポイント (条件の設定、無効化、削除など) を管理できます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-218">From the **Breakpoints** tab, you can manage you breakpoints and event tracepoints, including setting conditions, disabling and deleting them.</span></span>

![[ブレークポイント] タブ](./media/debugger_breakpoints.png)

<span data-ttu-id="7c4a8-220">デバッグに使用できるさまざまな種類のブレークポイントの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-220">Here's a summary of the different types of breakpoints you can use for debugging.</span></span>

<span data-ttu-id="7c4a8-221">ブレークポイントの種類</span><span class="sxs-lookup"><span data-stu-id="7c4a8-221">Breakpoint type</span></span> | <span data-ttu-id="7c4a8-222">説明</span><span class="sxs-lookup"><span data-stu-id="7c4a8-222">Description</span></span> | <span data-ttu-id="7c4a8-223">設定方法</span><span class="sxs-lookup"><span data-stu-id="7c4a8-223">How to set it</span></span>
:------------ | :------------ | :--------
**<span data-ttu-id="7c4a8-224">ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="7c4a8-224">Breakpoint</span></span>** | <span data-ttu-id="7c4a8-225">指定したコード行が実行される直前にデバッガーに割り込みます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-225">Breaks into the debugger just before the specified line of code is executed.</span></span> <span data-ttu-id="7c4a8-226">1 行に 1 つのステートメントがある場合は、通常のブレークポイントを設定するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-226">Regular breakpoints are easiest to set if you have one statement per line.</span></span> | <span data-ttu-id="7c4a8-227">[ [デバッグ] ウィンドウで](#debug-window)、コード内の任意の行番号の横にある左余白をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-227">From the [Debug window](#debug-window), click in the left margin next to any line number in the code.</span></span> <span data-ttu-id="7c4a8-228">赤いドットが表示され、ブレークポイントが設定されます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-228">A red dot appears and the breakpoint is set.</span></span> <span data-ttu-id="7c4a8-229">ブレークポイントのソースにジャンプするには、その青いテキストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-229">You can jump into the source of any breakpoint by clicking on its blue text.</span></span>
**<span data-ttu-id="7c4a8-230">条件付きブレークポイント</span><span class="sxs-lookup"><span data-stu-id="7c4a8-230">Conditional breakpoint</span></span>** | <span data-ttu-id="7c4a8-231">指定した条件が true と評価された場合に区切 *りを返します*。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-231">Breaks if the specified condition evaluates to *true*.</span></span> <span data-ttu-id="7c4a8-232">これは、基本的に `if(condition)`  デバッガーを分割する場合の 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-232">This is essentially an `if(condition)`  for breaking into the debugger.</span></span>  | <span data-ttu-id="7c4a8-233">[ブレークポイント[](#breakpoints)] タブで、既存のブレークポイントをポイントし、[鉛筆] ボタン *(この*ブレークポイントに条件を追加) をクリックし、既存のブレークポイントを右クリックし、コンテキスト メニューから [**条件**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-233">From the [Breakpoints](#breakpoints) tab, hover over an existing breakpoint and click the "pencil" button (*Add a condition to this breakpoint*), right-click an existing breakpoint and select **Condition...** from the context menu.</span></span> <span data-ttu-id="7c4a8-234">ブレークポイントの場所で評価する "if" 条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-234">Specify the "if" condition to be evaluated at the breakpoint location.</span></span> 
<span data-ttu-id="7c4a8-235">**XMLHttpRequest ブレークポイント** (オプションの条件)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-235">**XMLHttpRequest breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="7c4a8-236">XMLHttpRequest (XHR) 要求が満たされるたびに、このイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-236">Breaks whenever a XMLHttpRequest (XHR) request has been fulfilled.</span></span> <span data-ttu-id="7c4a8-237">[ウォッチ] ウィンドウから XHR `response` オブジェクト [**を検査**](#watches) できます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-237">You can inspect the XHR `response` object from the [**Watches**](#watches) pane.</span></span> | <span data-ttu-id="7c4a8-238">[[ブレークポイント] タブで](#breakpoints)*、[XMLHttpRequest*ブレークポイント] ボタン (上矢印/下矢印付きの円) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-238">From the [Breakpoints](#breakpoints) tab, click the *XMLHttpRequest breakpoint* button (circle with up/down arrows).</span></span> <span data-ttu-id="7c4a8-239">上記のように、 *条件付きブレークポイント* に変換できます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-239">You can turn it into a *Conditional breakpoint* as described above.</span></span>
**<span data-ttu-id="7c4a8-240">イベント トレースポイント</span><span class="sxs-lookup"><span data-stu-id="7c4a8-240">Event tracepoint</span></span>** | <span data-ttu-id="7c4a8-241">特定 [`console.log()`](./console/console-api.md#logging-custom-messages) のイベントへの応答として、指定された文字列を使用して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-241">Calls [`console.log()`](./console/console-api.md#logging-custom-messages) with a specified string in response to a specific event.</span></span> <span data-ttu-id="7c4a8-242">これは、イベント ハンドラー コードに直接保存しない一時的なコンソール ログ ステートメントに使用します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-242">Use this for temporary console logging statements that you don't want to save directly in your event handler code.</span></span> | <span data-ttu-id="7c4a8-243">[ [ブレークポイント] タブで](#breakpoints) 、[ *イベント* トレースポイント] ボタン (稲妻付きひし形) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-243">From the [Breakpoints](#breakpoints) tab, click the *Event tracepoint* button (diamond with lightning bolt).</span></span> <span data-ttu-id="7c4a8-244">トリガーの **イベントの** 種類とログ記録用 **の Trace** ステートメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-244">Select an **Event** type for the trigger and a **Trace** statement for logging.</span></span>
<span data-ttu-id="7c4a8-245">**イベントのブレークポイント** (オプションの条件)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-245">**Event breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="7c4a8-246">指定したイベントが発生するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-246">Breaks whenever a specified event is fired.</span></span> | <span data-ttu-id="7c4a8-247">[ブレークポイント[] タブで](#breakpoints)、[イベント\*\* のブレークポイント] ボタン (稲妻付き円) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-247">From the [Breakpoints](#breakpoints) tab, click the *Event breakpoint* button (circle with lightning bolt).</span></span> <span data-ttu-id="7c4a8-248">トリガーの **イベントの** 種類を選択し、必要に応じて Condition ステートメントを **指定** します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-248">Select an **Event** type for the trigger and optionally, specify a **Condition** statement.</span></span> 
**<span data-ttu-id="7c4a8-249">DOM ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="7c4a8-249">DOM breakpoint</span></span>** | <span data-ttu-id="7c4a8-250">サブツリーが変更された場合、その属性が変更された場合、DOM からデタッチされた場合など、ページ上の指定した要素が変更されるたびに、区切ります。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-250">Breaks whenever a specified element on the page is mutated, such as when its subtree is modified, its attributes change, or when it is detached from the DOM.</span></span> | <span data-ttu-id="7c4a8-251">[ [要素] タブ](./elements/dom-breakpoints.md) で、ソース要素を右クリックし *、[DOM ブレークポイント] オプションから選択* します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-251">From the [Elements](./elements/dom-breakpoints.md) tab, right-click on a source element and select from the *DOM Breakpoints* options.</span></span> <span data-ttu-id="7c4a8-252">ブレークポイントを[**管理するには、**](#dom-breakpoints)デバッガー パネルまたは\*\**要素*パネルの [DOM ブレークポイント] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-252">Use the [**DOM breakpoints**](#dom-breakpoints) tab in either the *Debugger* or *Elements* panels to manage your breakpoints.</span></span> 

<span data-ttu-id="7c4a8-253">条件付きブレークポイントとトレースポイントは、デバッガーに割り込むときに、現在スコープ内のすべてのローカル変数とグローバル変数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-253">Conditional breakpoints and tracepoints have access to all the local and global variables currently in scope when they break into the debugger.</span></span>

### <span data-ttu-id="7c4a8-254">DOM ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="7c4a8-254">DOM breakpoints</span></span>

<span data-ttu-id="7c4a8-255">DOM のブレークポイントの無効化、削除、再バインドなど **、DOM** のブレークポイント タブからブレークポイントを管理します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-255">Manage your DOM mutation breakpoints from the **DOM breakpoints** tab, including disabling, deleting and rebinding them.</span></span>  <span data-ttu-id="7c4a8-256">[DOM のブレークポイントは、[要素](./elements/dom-breakpoints.md) ] パネルの *HTML* ツリー ビューから **設定** できます。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-256">[DOM breakpoints can be set](./elements/dom-breakpoints.md) from the *HTML tree view* in the **Elements** panel.</span></span>

![[DOM ブレークポイント] タブ](./media/debugger_dom_breakpoints.png)

<span data-ttu-id="7c4a8-258">デバッガー *の [DOM ブレークポイント* ] タブは、[ **要素** ] パネルの \*[DOM ブレークポイント\*\*] タブと同等の機能 **を提供** します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-258">The *DOM breakpoints* tab in the **Debugger** provides equivalent functionality to the *DOM breakpoints*\* tab on the **Elements** panel.</span></span>

<span data-ttu-id="7c4a8-259">DOM のブレークポイントの種類の詳細 [を次に示します](./elements/dom-breakpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-259">Here's more on the different types of [DOM breakpoints](./elements/dom-breakpoints.md).</span></span>

## <span data-ttu-id="7c4a8-260">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-260">Shortcuts</span></span>

### <span data-ttu-id="7c4a8-261">ツール バーのショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-261">Toolbar shortcuts</span></span>

<span data-ttu-id="7c4a8-262">操作</span><span class="sxs-lookup"><span data-stu-id="7c4a8-262">Action</span></span> | <span data-ttu-id="7c4a8-263">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-263">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="7c4a8-264">検索</span><span class="sxs-lookup"><span data-stu-id="7c4a8-264">Find</span></span> | `Ctrl` + `F`
<span data-ttu-id="7c4a8-265">続行 (ブレークポイントから)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-265">Continue (from breakpoint)</span></span> | `F5` <span data-ttu-id="7c4a8-266">または</span><span class="sxs-lookup"><span data-stu-id="7c4a8-266">or</span></span> `F8`
<span data-ttu-id="7c4a8-267">高速続行</span><span class="sxs-lookup"><span data-stu-id="7c4a8-267">Fast continue</span></span> | <span data-ttu-id="7c4a8-268">保留 `F5` または</span><span class="sxs-lookup"><span data-stu-id="7c4a8-268">Hold `F5` or</span></span> `F8`
<span data-ttu-id="7c4a8-269">続行して更新する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-269">Continue and refresh</span></span> | `Ctrl` + `Shift` + `F5`
<span data-ttu-id="7c4a8-270">Break</span><span class="sxs-lookup"><span data-stu-id="7c4a8-270">Break</span></span> | `Ctrl` + `Shift` + `B`
<span data-ttu-id="7c4a8-271">ステップ 実行</span><span class="sxs-lookup"><span data-stu-id="7c4a8-271">Step into</span></span> | `F11`
<span data-ttu-id="7c4a8-272">ステップ オーバー</span><span class="sxs-lookup"><span data-stu-id="7c4a8-272">Step over</span></span> | `F10`
<span data-ttu-id="7c4a8-273">ステップ アウト</span><span class="sxs-lookup"><span data-stu-id="7c4a8-273">Step out</span></span> | `Shift` + `F11`
<span data-ttu-id="7c4a8-274">新しいワーカーで作業を行う</span><span class="sxs-lookup"><span data-stu-id="7c4a8-274">Break on new worker</span></span> | `Ctrl` + `Shift` + `W`
<span data-ttu-id="7c4a8-275">例外の動作を変更する (メニューを開く)</span><span class="sxs-lookup"><span data-stu-id="7c4a8-275">Change exception behavior (opens menu)</span></span> | `Ctrl` + `Shift` + `E`
<span data-ttu-id="7c4a8-276">自分のコードをデバッグする</span><span class="sxs-lookup"><span data-stu-id="7c4a8-276">Debug just my code</span></span> | `Ctrl` + `J`

### <span data-ttu-id="7c4a8-277">リソース ピッカーのショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-277">Resource picker shortcuts</span></span>

<span data-ttu-id="7c4a8-278">操作</span><span class="sxs-lookup"><span data-stu-id="7c4a8-278">Action</span></span> | <span data-ttu-id="7c4a8-279">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-279">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="7c4a8-280">自分のコード/ライブラリ コードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="7c4a8-280">Mark as my code / library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="7c4a8-281">ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="7c4a8-281">Open file</span></span> | `Ctrl`<span data-ttu-id="7c4a8-282"> + `O`, `Ctrl` + </span><span class="sxs-lookup"><span data-stu-id="7c4a8-282"> + `O`, `Ctrl` + </span></span>`P`
<span data-ttu-id="7c4a8-283">すべてのファイルを検索する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-283">Search all files</span></span> | `Ctrl` + `Shift` + `F`

### <span data-ttu-id="7c4a8-284">デバッグ ウィンドウのショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-284">Debug window shortcuts</span></span>

<span data-ttu-id="7c4a8-285">操作</span><span class="sxs-lookup"><span data-stu-id="7c4a8-285">Action</span></span> | <span data-ttu-id="7c4a8-286">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-286">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="7c4a8-287">ブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-287">Remove breakpoint</span></span> | `F9`
<span data-ttu-id="7c4a8-288">ブレークポイントを無効にする</span><span class="sxs-lookup"><span data-stu-id="7c4a8-288">Disable breakpoint</span></span> | `Ctrl` + `F9`
<span data-ttu-id="7c4a8-289">条件付きブレークポイント</span><span class="sxs-lookup"><span data-stu-id="7c4a8-289">Conditional breakpoint...</span></span> | `Alt` + `F9`
<span data-ttu-id="7c4a8-290">コピー</span><span class="sxs-lookup"><span data-stu-id="7c4a8-290">Copy</span></span> | `Ctrl` + `C`
<span data-ttu-id="7c4a8-291">Save</span><span class="sxs-lookup"><span data-stu-id="7c4a8-291">Save</span></span> | `Ctrl` + `S`
<span data-ttu-id="7c4a8-292">行... に移動します。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-292">Go to line...</span></span> | `Ctrl` + `G`
<span data-ttu-id="7c4a8-293">次のステートメントを表示する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-293">Show next statement</span></span> | `Alt` + `Num` + `*`
<span data-ttu-id="7c4a8-294">カーソル位置まで実行</span><span class="sxs-lookup"><span data-stu-id="7c4a8-294">Run to cursor</span></span> | `Ctrl` + `F10`
<span data-ttu-id="7c4a8-295">Set next ステートメント</span><span class="sxs-lookup"><span data-stu-id="7c4a8-295">Set next statement</span></span> | `Ctrl` + `Shift` + `F10`
<span data-ttu-id="7c4a8-296">ファイル ピッカーに表示する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-296">Show in file picker</span></span> | `Ctrl` + `Alt` + `P`
<span data-ttu-id="7c4a8-297">ファイル内の定義に移動する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-297">Go to definition in file</span></span> | `Ctrl`+`D`
<span data-ttu-id="7c4a8-298">ファイル内の参照を検索する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-298">Find references in file</span></span> | `Ctrl` + `Shift` + `D`
<span data-ttu-id="7c4a8-299">印刷が美しい</span><span class="sxs-lookup"><span data-stu-id="7c4a8-299">Pretty print</span></span> | `Ctrl` + `Shift` + `P`
<span data-ttu-id="7c4a8-300">Word の折り返し</span><span class="sxs-lookup"><span data-stu-id="7c4a8-300">Word wrap</span></span> | `Alt` + `W`
<span data-ttu-id="7c4a8-301">コード/ライブラリ コードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="7c4a8-301">Mark as my code/library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="7c4a8-302">エディターでタブを無効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-302">Disable/Enable tabs in the editor.</span></span> <span data-ttu-id="7c4a8-303">**注:** キーボードを使ってデバッガー内を移動している場合は、タブ移動を無効にするまでエディターからタブアウトできません。</span><span class="sxs-lookup"><span data-stu-id="7c4a8-303">**Note:** if you're using the keyboard to navigate in the Debugger, you won't be able to tab out of the editor until you disable tabbing</span></span> | `Ctrl` + `M`

### <span data-ttu-id="7c4a8-304">[ウォッチ] ウィンドウのショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-304">Shortcuts for Watches pane</span></span>

<span data-ttu-id="7c4a8-305">操作</span><span class="sxs-lookup"><span data-stu-id="7c4a8-305">Action</span></span> | <span data-ttu-id="7c4a8-306">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-306">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="7c4a8-307">ウォッチを追加する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-307">Add watch</span></span> | `Ctrl` + `W`
<span data-ttu-id="7c4a8-308">ウォッチを削除する</span><span class="sxs-lookup"><span data-stu-id="7c4a8-308">Delete watch</span></span> | `Ctrl` + `D`

### <span data-ttu-id="7c4a8-309">[詳細] ウィンドウのショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-309">Shortcuts for Details pane</span></span>

| <span data-ttu-id="7c4a8-310">操作</span><span class="sxs-lookup"><span data-stu-id="7c4a8-310">Action</span></span>                             | <span data-ttu-id="7c4a8-311">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7c4a8-311">Shortcut</span></span>                 |
|:-----------------------------------|:-------------------------|
| <span data-ttu-id="7c4a8-312">ライブラリ コードのフレームの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="7c4a8-312">Show/Hide frames from library code</span></span> | `Ctrl` + `Shift` + `J`   |
| <span data-ttu-id="7c4a8-313">すべてのブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="7c4a8-313">Enable all breakpoints</span></span>             | `Ctrl` + `Shift` + `F11` |
