---
description: 標準ベースの Chakra JavaScript エンジンを使って、Windows アプリケーションにスクリプト機能を追加します。
title: JavaScript ランタイムのホスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/15/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30ec744e-57cc-4ef5-8fe1-d2c27b946548
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9077284d96ff0d9ae22e152329efe9304081ae39
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569416"
---
# JavaScript ランタイムのホスト
JavaScript Runtime (JsRT) Api は、Windows オペレーティングシステムで実行されているデスクトップ、Windows ストア、サーバー側アプリケーションのための手段を提供します。これは、Microsoft Edge と Internet Explorer でも利用される標準ベースの Chakra JavaScript エンジンを使って、アプリケーションにスクリプト機能を追加します。 これらの Api は、Windows 10 と、Internet Explorer バージョン11.0 がコンピューターにインストールされているすべてのバージョンの Windows オペレーティングシステムで使用できます。 詳しくは、「[リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)」をご覧ください。 Windows ストアアプリでの JsRT の使用について詳しくは、「 [JsRT とユニバーサル Windows プラットフォーム](#Windows)」をご覧ください。  
  
> [!NOTE]
>  このドキュメントでは、JavaScript の言語についてよく理解していることを前提としています。  
  
## 概念  
 JsRT Api を使って JavaScript エンジンをホストする方法については、次の2つの主要な概念 (ランタイムと実行コンテキスト) に依存します。  
  
 *ランタイム*は、完全な JavaScript 実行環境を表します。 作成される各ランタイムには、独自の分離されたガベージコレクションのヒープと、既定で、専用のジャストインタイム (JIT) コンパイラスレッドとガベージコレクター (GC) スレッドがあります。 *実行コンテキスト*は、他のすべての実行コンテキストとは異なる独自の javascript グローバルオブジェクトを持つ javascript 環境を表します。 1つのランタイムには複数の実行コンテキストが含まれている可能性があります。その場合、すべての実行コンテキストは、ランタイムに関連付けられている JIT コンパイラと GC スレッドを共有します。  
  
 ランタイムは、1つの実行スレッドを表します。 特定のスレッドでアクティブにできるランタイムは一度に1つだけであり、ランタイムは一度に1つのスレッドでのみアクティブにすることができます。 ランタイムはレンタルスレッドであるため、現在スレッドでアクティブになっていないランタイム (つまり、JavaScript コードが実行されていないか、ホストからのすべての呼び出しに応答しない) は、アクティブなランタイムをまだ持っていないすべてのスレッドで使うことができます。  
  
 実行コンテキストは、特定のランタイムに関連付けられ、そのランタイム内でコードを実行します。 ランタイムとは異なり、一度に複数の実行コンテキストをスレッドでアクティブにすることができます。 そのため、ホストは実行コンテキストに呼び出しを行うことができます。これにより、実行コンテキストはホストにコールバックすることができ、ホストは別の実行コンテキストに呼び出すことができます。  
  
 ![複数の実行コンテキスト](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting")  
  
 実際には、ホストが分離された環境でコードを実行する必要がない限り、1つの実行コンテキストを使うことができます。 同様に、ホストで複数のコードを同時に実行する必要がない場合は、1つのランタイムで十分です。  
  
## メモリ管理  
 JavaScript はガベージコレクションされた言語であるため、別の言語の JsRT Api を使用する際に考慮する必要があるいくつかの考慮事項があります。  
  
 主な考慮事項は、JavaScript のガベージコレクターは、実行時のヒープとスタックという2つの場所の値への参照のみを見ることができることです。 そのため、別の JavaScript 値またはスタックのローカル変数に格納されている JavaScript 値への参照は、常にガベージコレクターによって表示されます。 ただし、ホストやシステムによって管理されるヒープなど、他の場所に保存されている参照は、ガベージコレクターによっては表示されず、ホストでまだ使用されている値の収集が早すぎる可能性があります。  
  
> [!IMPORTANT]
>  一部の言語コンパイラ (Visual Studio C++ コンパイラなど) では、可能な限りローカル変数を最適化します。 JavaScript の値を参照するローカル変数は、それらの値を保持する必要がある場合は、スタック上にあることを確認する必要があります。  
  
 JavaScript 値への参照がガベージコレクターに表示されない場所に格納される場合は、ホストは JsRT Api を使って参照を手動で追加および削除する必要があります。  
  
## 例外処理  
 スクリプトの実行中に JavaScript 例外が発生すると、それを含むランタイムが例外の状態になります。 例外状態では、コードが実行されることはありません。また、ホストが `JsErrorInExceptionState` api を使って例外を取得してクリアするまで、すべての api 呼び出しがエラーコードで失敗し `JsGetAndClearException` ます。 ホストが、例外状態からランタイムをクリアせずに JavaScript コールバックから返された場合、コントロールが JavaScript エンジンに戻されるとすぐに、JavaScript 例外が再スローされます。 これにより、ホストコールバックは、ランタイムを例外の状態に設定してから、ホストのコールバックから返すことで、JavaScript 例外を "スロー" することもできます。  
  
 ホストは、独自の内部例外をホストコールバック間で伝達することはできません。すべてのコールバックメソッドは、コントロールをランタイムに返す前にすべてのホスト例外をキャッチする必要があります。  
  
## ランタイムリソースの使用状況  
 JsRT Api は、ランタイムがリソースを使う方法を監視および変更するためのさまざまな方法を公開します。 通常は、次のカテゴリに分類されます。  
  
-   **スレッドの使用**。 既定では、各ランタイムは専用の JIT コンパイラスレッドと、そのランタイムを処理する専用の GC スレッドを作成します。 このフラグを使ってランタイムを作成した場合、JIT と GC の動作は、それぞれの `JsRuntimeAttributeDisableBackgroundWork` 1 つについて別個のバックグラウンドスレッドではなく、ランタイムスレッド自体で実行されます。 また、ホストは、呼び出しへのスレッドサービスコールバックを提供することもできます。これによって、 `JsCreateRuntime` ホストは JIT と GC の動作を適切な方法でスケジュールすることができます。  
  
-   **メモリ使用量**。 ランタイムのメモリ使用量を監視し、変更するには、いくつかの方法があります。 ランタイムが長時間実行されている場合は、ホストで `JsRuntimeAttributeEnableIdleProcessing` ランタイムを作成するときにフラグを指定し、 `JsIdle` ホストがアイドル状態のときに呼び出すことができます。 これにより、エンジンは、一部のメモリクリーンアップと簿記の処理をアイドル時間まで延期することができます。  
  
     ホストは、を呼び出してガベージコレクションを監視でき `JsSetRuntimeBeforeCollectCallback` ます。 また、を呼び出してヒープによって行われた割り当てを監視することもでき `JsSetRuntimeMemoryAllocationCallback` ます。 この API は、すべての JavaScript の割り当てについては呼び出されません。つまり、ランタイムのヒープで割り当てる必要のある領域がさらに必要な場合だけです。 メモリ割り当てのコールバックでは、要求を拒否することができます。これにより、ガベージコレクションがトリガーされ、メモリが利用できない場合、ランタイムにメモリ不足のエラーが発生します。  
  
     ホストは、ランタイムが `JsSetRuntimeMemoryLimit` 使うことができるメモリの量に対する制限を設定するために呼び出すこともできます。 ランタイムが制限をヒットすると、ガベージコレクションがトリガーされ、メモリが利用できない場合、ランタイムによってメモリ不足のエラーがスローされます。  
  
-   **スクリプトの中断と評価**。 ホストは、 `JsDisableRuntimeExecution` ランタイム内で実行を終了するために呼び出すことができます。 この通話は、どのスレッドからでもいつでも行うことができます。 スクリプトの終了は、コードに挿入されたガードポイントへの到達に依存するため、スクリプトは正確な瞬間に終了しないことがありますが、その後すぐに実行されます。 既定では、終了ガードポイントは、生成されたコード conservatively 内に配置され、無限ループなど、すべての状況をカバーすることはできません。 このフラグを使ってランタイムを作成 `JsRuntimeAttributeAllowScriptInterrupt` すると、実行時に無限ループの追加チェックが挿入され、多くの場合、パフォーマンスがわずかに低下します。  
  
     ホストで JIT コンパイラによるネイティブコードの生成を許可しない場合は、フラグを指定でき `JsRuntimeAttributeDisableNativeCodeGeneration` ます。 また、ホストでは、フラグを指定することによって、動的に実行されるスクリプト自体からスクリプトを拒否することもでき `JsRuntimeAttributeDisableEval` ます。  
  
## デバッグとプロファイリング  
 JsRT Api では、アクティブなスクリプトテクノロジによるデバッグとプロファイリングがサポートされています。  
  
 Windows 10 以降では、Chakra JavaScript エンジンは従来の Internet Explorer (MSHTML) エンジンと新しい Microsoft Edge (EdgeHTML) エンジンをサポートしており、JsRT のいずれかをターゲットにできます (詳しくは、「 [Microsoft edge とレガシエンジン](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)のターゲット設定」をご覧ください)。 Visual Studio でのスクリプトのデバッグは、従来のエンジンと Microsoft Edge のエンジンでは動作が異なります。 従来のエンジンでは、ホストは[Iprocessdebugmanager インターフェイス](/scripting/winscript/reference/iprocessdebugmanager-interface)インスタンスから取得できる[IDebugApplication Interface](/scripting/winscript/reference/idebugapplication-interface)ポインターを提供する必要があります。 Microsoft Edge エンジンで `IDebugApplication` は廃止され、Chakra エンジンは、ユーザーからの実装を必要とせずに、Visual Studio デバッガーを通じてネイティブおよびスクリプトのデバッグ機能を有効にし `IDebugApplication` ます。  
  
 実行コンテキストのスクリプトをデバッグ可能にするには、Chakra engine では、効率の低いコード実行メソッドを使用するように切り替える必要があります。 したがって、通常、デバッグ可能なコードは、デバッグできないコードよりも動作が遅くなります。 この結果、従来のエンジンでは、ホストは、最初にポインターを前に移動することによって、最初の実行コンテキストでデバッグを開始するか `IDebugApplication` 、デバッグが必要になってから呼び出すかを選択でき `JsCreateContext` `JsStartDebugging` ます。 Microsoft Edge エンジンでは、パラメーターが不要になった `JsCreateContext` `IDebugApplication` ため、その結果として、が呼び出された後にのみ、スクリプトはデバッグ可能になり `JsStartDebugging` ます。 Visual Studio を使ってデバッグする場合は、"Script" デバッガーオプションを有効にする必要があります。  
  
 実行コンテキストの JavaScript コードは、次の2つの方法のいずれかでプロファイリングできます。 Windows 8.1 以降のバージョンでは、コマンドラインの Visual Studio Profiler (vsperf) を使用して、アプリケーションで実行される JavaScript コードのターゲットとなるレポートを生成できます。 または、ホストが直接呼び出すことができ `JsStartProfiling` `JsStopProfiling` ます。また、コールバックを提供してプロファイリングを行うこともできます。 ホストは、呼び出しによってガベージコレクションされたヒープの状態を調査することもでき `JsEnumerateHeap` ます。 JsRT でのプロファイリングは、従来と Microsoft Edge エンジンと同じ方法で動作します。 ただし、ユニバーサル Windows アプリでは、JsRT のプロファイリング api (、、、など `JsStartProfiling` `JsStopProfiling` `JsEnumerateHeap` `JsIsEnumeratingHeap` ) は使用できません。  
  
<a name="Windows"></a>   
## JsRT とユニバーサル Windows プラットフォーム  

JsRT Api を使って、ユニバーサル Windows アプリにスクリプト機能を追加することができます。 JsRT Api を使うユニバーサル Windows アプリでは、Microsoft Edge JSRT Api をターゲットとして指定する必要があります。これは、Edge Chakra engine をターゲットとしています。 詳細については、「 [Microsoft Edge とレガシエンジンのターゲット](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)設定」を参照してください。 完全な JsRT API は、ユニバーサル Windows アプリで利用できます。ただし、プロファイリングとヒープ列挙のサポート (、、、 `JsStartProfiling` `JsStopProfiling` はサポートされ `JsEnumerateHeap` `JsIsEnumeratingHeap` ていません)。  
  
また、Microsoft Edge JsRT API を使用して API 名前空間を公開した後、JsRT によって、スクリプトは[ユニバーサル Windows プラットフォーム (UWP) api](https://msdn.microsoft.com/library/windows/apps/br211377.aspx)にネイティブにアクセスでき `JsProjectWinRTNamespace` ます。 ユニバーサル Windows アプリケーションでは、必要な名前空間を設定する必要はありませんが、従来の (Win32) Windows アプリケーションでは、COM で初期化されたデリゲートメカニズムを有効にして、イベントと非同期 Api を有効にする必要があり `JsSetProjectionEnqueueCallback` ます。 次の Win32 サンプルでは、非同期 UWP Api を使って、Uri からコンテンツを取得するための http クライアントを作成しています。  
  
```cpp  
typedef struct _jsCall {  
    JsProjectionCallback jsCallback;  
    JsProjectionCallbackContext jsContext;  
    HANDLE event;  
} jsCall;  
  
// Set up delegated pumping mechanism; not necessary in UWP applications.  
jsCall outstandingCall = {};  
CoInitializeEx(nullptr, COINIT_MULTITHREADED);  
JsSetProjectionEnqueueCallback([](JsProjectionCallback jsCallback,   
JsProjectionCallbackContext jsContext, void *callbackState) {  
    jsCall* call = (jsCall*)callbackState;  
    call->jsCallback = jsCallback;  
    call->jsContext = jsContext;  
    SetEvent(call->event);  
    },  
&outstandingCall);  
HANDLE event = CreateEventEx(NULL, NULL, CREATE_EVENT_MANUAL_RESET, EVENT_ALL_ACCESS);  
outstandingCall.event = event;  
  
// Project necessary namespaces.  
JsProjectWinRTNamespace(L"Windows.Foundation");  
JsProjectWinRTNamespace(L"Windows.Web");  
  
// Get content from an Uri.  
JsRunScript(L"var uri = new Windows.Foundation.Uri(\"http://somedatasource.com\"); " \  
    L"var httpClient = new Windows.Web.Http.HttpClient();" \  
    L"httpClient.getStringAsync(uri).done(function (content) { " \  
    L"    // do something with the string content " \    
    L"}, onError); " \  
    L"function onError(reason) { " \  
    L"    // error handling " \        
    L"}",   
    currentSourceContext, L"", &result);  
  
// Wait for async call to come in and then execute; not necessary in UWP applications.  
WaitForSingleObjectEx(outstandingCall.event, 10000, FALSE) == WAIT_OBJECT_0;  
outstandingCall.jsCallback(outstandingCall.jsContext);  
  
```  
  
## 関連項目  
 [JavaScript ランタイムサンプルアプリ](https://go.microsoft.com/fwlink/p/?LinkID=306674&clcid=0x409)   
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)   
 [JavaScript ランタイムホスティング](../javascript-runtime-hosting.md)  
 