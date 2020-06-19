---
description: 'さまざまな Windows 10 JavaScript エンジンのターゲットを変更する方法について説明します。 '
title: JsRT Api での Microsoft Edge とレガシエンジンのターゲット設定
ms.date: 06/18/2020
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: cbc7df6c-0bc9-48f5-b9ad-b9ed31c42f92
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
ms.openlocfilehash: 99a3143dd5f995332524a99e5c6c5019b955fea8
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752228"
---
# <span data-ttu-id="0b65d-103">JsRT Api での Microsoft Edge とレガシエンジンのターゲット設定</span><span class="sxs-lookup"><span data-stu-id="0b65d-103">Targeting Microsoft Edge vs. Legacy engines in JsRT APIs</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="0b65d-104">Windows 10 では、次の2種類の JavaScript エンジンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0b65d-104">Windows 10 supports two different JavaScript engines:</span></span>  

*   <span data-ttu-id="0b65d-105">Internet Explorer 11 に付属していて、サポートされている古い Chakra エンジン (*従来のエンジン*または jscript9.dll とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="0b65d-105">The old Chakra engine (also called the *legacy engine* or jscript9.dll below) that ships with and supports Internet Explorer 11.</span></span> <span data-ttu-id="0b65d-106">このエンジンは時間内に凍結され、Win 8.1/IE11 release の場合とは基本的に変わりません。</span><span class="sxs-lookup"><span data-stu-id="0b65d-106">This engine is frozen in time and will remain fundamentally unchanged from Win8.1/IE11 release.</span></span>  
*   <span data-ttu-id="0b65d-107">Windows 10 の Microsoft Edge の新しいブラウザーを同梱およびサポートしている新しい Chakra engine ( *Edge エンジン*または以下の chakra.dll とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="0b65d-107">The new Chakra engine (also called the *Edge engine* or chakra.dll below) that ships with and supports the new browser in Windows 10, Microsoft Edge.</span></span> <span data-ttu-id="0b65d-108">このエンジンは継続的に更新され、"生きた"[エッジ](https://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx)エンジンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0b65d-108">This engine will be continually updated and will support a "living" [Edge](https://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx) engine.</span></span> <span data-ttu-id="0b65d-109">Microsoft edge エンジンは、従来のエンジンとは異なり、Microsoft Edge エンジンはどのような形式のバージョン管理スクリプト機能を備えていないかを示しています。</span><span class="sxs-lookup"><span data-stu-id="0b65d-109">A living Microsoft Edge engine implies that unlike the legacy engine, the Microsoft Edge engine would not carry forward any form of versioning script functionality to opt into.</span></span>  

 <span data-ttu-id="0b65d-110">JavaScript Runtime ホスティング (JsRT) API を使ってアプリを作成する場合、レガシまたは Microsoft Edge のどちらのエンジンをターゲットにするかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-110">When creating an app using the JavaScript Runtime Hosting (JsRT) API, you can choose to target either the legacy or the Microsoft Edge engine.</span></span>  

*   <span data-ttu-id="0b65d-111">既存のアプリケーションの下位互換性を強調する必要がある場合は、レガシエンジンをターゲットにします。</span><span class="sxs-lookup"><span data-stu-id="0b65d-111">If you need to emphasize backward compatibility of your existing applications, target the legacy engine.</span></span>  
*   <span data-ttu-id="0b65d-112">アプリをすぐに使用できるようにする必要がある場合 (たとえば、ECMAScript 6 など)、新しい JavaScript 機能をサポートするには、Microsoft Edge エンジンをターゲットにします。</span><span class="sxs-lookup"><span data-stu-id="0b65d-112">If you want your app to be forward looking and support new JavaScript features as they are released (for example, ECMAScript 6), target the Microsoft Edge engine.</span></span>  

<span data-ttu-id="0b65d-113">このトピックには、さまざまなエンジンのターゲットを指定する方法についての詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b65d-113">This topic includes details that describe how to target the different engines.</span></span>  

## <span data-ttu-id="0b65d-114">希望するバージョンをターゲットにする</span><span class="sxs-lookup"><span data-stu-id="0b65d-114">Target your preferred version</span></span>  

<span data-ttu-id="0b65d-115">アプリを作成するときに、Microsoft Edge エンジンとレガシエンジンのいずれかをサポートする JsRT のバージョンを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-115">When creating an app, you can select the version of the JsRT that supports either the Microsoft Edge engine or the legacy engine.</span></span> <span data-ttu-id="0b65d-116">上記のガイドラインに基づいて、JsRT のバージョンを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-116">You can choose the JsRT version based on the guidelines above.</span></span> <span data-ttu-id="0b65d-117">これらの違いに対応するために、、、およびに対して次の変更が加えられました `JsCreateRuntime` `JsCreateContext` `JsStartDebugging` 。</span><span class="sxs-lookup"><span data-stu-id="0b65d-117">To accommodate these distinctions, the following changes have been made to `JsCreateRuntime`, `JsCreateContext`, and `JsStartDebugging`.</span></span>  

<span data-ttu-id="0b65d-118">対象 `JsCreateRuntime` :</span><span class="sxs-lookup"><span data-stu-id="0b65d-118">For `JsCreateRuntime`:</span></span>  

*   <span data-ttu-id="0b65d-119">従来のエンジンをターゲットとする場合、 `JsRuntimeVersionEdge` 列挙値は廃止され、代わりに値を使用するようにメッセージが表示され `JsRuntimeVersionInternetExplorer11` ます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-119">When targeting the legacy engine, the `JsRuntimeVersionEdge` enumeration value is deprecated, and a message will suggest using the `JsRuntimeVersionInternetExplorer11` value instead.</span></span>  
*   <span data-ttu-id="0b65d-120">Microsoft Edge エンジンをターゲットとして、関数から version パラメーターが省略されてい `JsCreateRuntime` ます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-120">When targeting the Microsoft Edge engine, the version parameter is omitted from the `JsCreateRuntime` function.</span></span>  
    
    ```cpp
    JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);
    ```  
    
 <span data-ttu-id="0b65d-121">For `JsCreateContext` と `JsStartDebugging` :</span><span class="sxs-lookup"><span data-stu-id="0b65d-121">For `JsCreateContext` and `JsStartDebugging`:</span></span>  

*   <span data-ttu-id="0b65d-122">レガシエンジンをターゲットとする場合、 `IDebugApplication` インターフェイスは、独自のリモート以外のデバッグメソッドを提供するために使われます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-122">When targeting the legacy engine, the `IDebugApplication` interface is used to supply your own non-remote debugging methods.</span></span> <span data-ttu-id="0b65d-123">デバッグのために `JsCreateContext` 、 `JsStartDebugging` 関数は `IDebugApplication` パラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-123">For debugging purposes, `JsCreateContext` and `JsStartDebugging` functions take `IDebugApplication` as parameter.</span></span>  
*   <span data-ttu-id="0b65d-124">Microsoft Edge エンジンをターゲットとしている場合、 `IDebugApplication` インターフェイスは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="0b65d-124">When targeting the Microsoft Edge engine, the `IDebugApplication` interface is deprecated.</span></span> <span data-ttu-id="0b65d-125">Chakra エンジンは、ユーザーからの実装を必要とせずに、Visual Studio デバッガーでネイティブおよびスクリプトのデバッグ機能を有効にし `IDebugApplication` ます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-125">The Chakra engine enables native and script debugging capability with Visual Studio debugger without requiring an implementation of `IDebugApplication` from user.</span></span> <span data-ttu-id="0b65d-126">インターフェイスは、 `JsCreateContext` および結果としてのパラメーターではなくなりました `JsStartDebugging` 。</span><span class="sxs-lookup"><span data-stu-id="0b65d-126">The interface is no longer a parameter for `JsCreateContext` and `JsStartDebugging` as a result.</span></span>  

<span data-ttu-id="0b65d-127">従来のエンジンの以前の Api のシグネチャは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-127">The signatures for the preceding APIs in the legacy engine are as follows:</span></span>  

```cpp
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsRuntimeVersion version, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);

JsErrorCode JsCreateContext(JsRuntimeHandle runtime, IDebugApplication *debugApplication, JsContextRef *newContext);

JsErrorCode JsStartDebugging(IDebugApplication *debugApplication);
```  

<span data-ttu-id="0b65d-128">Microsoft Edge エンジンの上にある Api のシグネチャは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-128">The signatures for the preceding APIs in the Microsoft Edge engine are as follows:</span></span>  

```cpp
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);

JsErrorCode JsCreateContext(JsRuntimeHandle runtime, JsContextRef *newContext);

JsErrorCode JsStartDebugging();
```  

## <span data-ttu-id="0b65d-129">Visual C++ を使って、好みのバージョンをコンパイルする</span><span class="sxs-lookup"><span data-stu-id="0b65d-129">Compile for your preferred version using Visual C++</span></span>  

<span data-ttu-id="0b65d-130">Visual C++ を使っている場合は、JsRT ヘッダーを含めることによって JsRT API をインポートし、リンカーの入力ファイルの一覧に JsRT が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b65d-130">When using Visual C++, import the JsRT API by including the jsrt.h header, and ensure that jsrt.lib is included in your linker input files list:</span></span>  

```cpp
#include <jsrt.h>
```  

![リンカー入力ファイルとして jsrt を追加する](../chakra-hosting/media/js-chakra.png "JS_Chakra_")  

<span data-ttu-id="0b65d-132">Microsoft Edge エンジンのバイナリをターゲットにする場合は、jsrt を含める前にマクロを定義する必要があります。 jsrt にリンクする代わりに、 `USE_EDGEMODE_JSRT` chakrart にリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-132">If you want to target the Microsoft Edge engine binaries, you need to define the macro `USE_EDGEMODE_JSRT` before including jsrt.h, and instead of linking against jsrt.lib, you should link against chakrart.lib:</span></span>  

```cpp
#define USE_EDGEMODE_JSRT
#include <jsrt.h>
```  

![リンカー入力ファイルとして chakrart を追加する](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting_")  

<span data-ttu-id="0b65d-134">新しいアプリケーションを初めて使用する場合は、JsRT API に対するコードの作成を開始することができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0b65d-134">If you're starting with a new application, you are now ready to start writing code against the JsRT API.</span></span>  

## <span data-ttu-id="0b65d-135">.NET を使って適切なバージョンをコンパイルする</span><span class="sxs-lookup"><span data-stu-id="0b65d-135">Compile for your preferred version using .NET</span></span>  

<span data-ttu-id="0b65d-136">.NET と P/Invoke を使っている場合は、jscript9.dll の代わりに、JsRT API [DllImport] 宣言を変更して chakra.dll をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-136">If you're using .NET and P/Invoke, you must change your JsRT API [DllImport] declarations to import chakra.dll instead of jscript9.dll.</span></span> <span data-ttu-id="0b65d-137">さらに、の定義を変更して、 `JsCreateRuntime` `JsRuntimeVersion` パラメーターとの定義を削除し、パラメーターを削除し `JsCreateContext` `JsStartDebugging` `IDebugApplication` ます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-137">In addition, change the definition of `JsCreateRuntime` to remove the `JsRuntimeVersion` parameter and the definition of `JsCreateContext` and `JsStartDebugging` to remove the `IDebugApplication` parameter.</span></span>  

<span data-ttu-id="0b65d-138">従来のエンジンの場合は、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b65d-138">For the legacy engine, use the following code.</span></span>  

```csharp
[DllImport("jscript9.dll")]
public static extern JsErrorCode JsCreateRuntime(
    JsRuntimeAttributes attributes,
    JsRuntimeVersion version,
    JsThreadServiceCallback callback,
    out JsRuntimeSafeHandle runtime
);

[DllImport("jscript9.dll")]
public static extern JsErrorCode JsCreateContext(
    JsRuntimeSafeHandle runtime,
    IDebugApplication debugApplication,
    out JsContextRef newContext
);   

[DllImport("jscript9.dll")]
public static extern JsErrorCode JsStartDebugging(
    IDebugApplication debugApplication,
);
```  

<span data-ttu-id="0b65d-139">Microsoft Edge エンジンの場合は、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b65d-139">For the Microsoft Edge engine, use the following code.</span></span>  

```csharp
[DllImport("chakra.dll")]
public static extern JsErrorCode JsCreateRuntime(
    JsRuntimeAttributes attributes,
    JsThreadServiceCallback callback,
    out JsRuntimeSafeHandle runtime
);  

[DllImport("chakra.dll")]
public static extern JsErrorCode JsCreateContext(
    JsRuntimeSafeHandle runtime,
    out JsContextRef newContext
);

[DllImport("chakra.dll")]
public static extern JsErrorCode JsStartDebugging();
```  

> [!CAUTION]
> <span data-ttu-id="0b65d-140">関数ポインター (LoadLibrary/GetProcAddress など) を手動でマーシャリングする場合は、メソッドの宣言を混同しないようにする必要があります。そうしないと、スタックの均衡が解除されるため、アプリのクラッシュの原因となる予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-140">If you are manually marshaling the function pointer (such as via LoadLibrary/GetProcAddress), it is critical that you do not mix the declarations of the method, or else you will unbalance the stack, which will result in unpredictable behavior such as causing your app to crash.</span></span> <span data-ttu-id="0b65d-141">インポートコードで jscript9.dll のインスタンスのグローバル検索と置換を実行すると、パラメーターが削除されるため、同じ問題が発生し `version` ます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-141">The same problem will occur if you perform a global search-and-replace of instances of jscript9.dll in your import code, because you'll miss the `version` parameter being dropped.</span></span>  

## <span data-ttu-id="0b65d-142">まとめ</span><span class="sxs-lookup"><span data-stu-id="0b65d-142">Summary</span></span>  

<span data-ttu-id="0b65d-143">Windows 10 では、JavaScript のホスト Api が2つに分かれています。</span><span class="sxs-lookup"><span data-stu-id="0b65d-143">In Windows 10, the JavaScript Runtime Hosting APIs are splitting into two.</span></span> <span data-ttu-id="0b65d-144">これらの Api では、"生きた" Microsoft edge エンジンがサポートされるようになりました。これは、Microsoft Edge の "生きた" Microsoft Edge エンジンと連携する言語機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="0b65d-144">These APIs now support a "living" Microsoft Edge engine, whose language capabilities will be aligned with the "living" Microsoft Edge engine in the Microsoft Edge.</span></span> <span data-ttu-id="0b65d-145">デスクトップまたはストアアプリからこれらの機能を活用して、アプリケーションを拡張したり、既存のコードベースで最新の Web スキルを活用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-145">You can leverage these capabilities from your desktop or Store apps to create new and exciting ways to extend your application and to leverage modern Web skills in your existing code base.</span></span> <span data-ttu-id="0b65d-146">ただし、以前のバージョンには微妙な違いがあるため、Edge またはレガシエンジンをターゲットとする場合は、次の点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-146">However, because there are subtle differences between previous versions, you must be aware of the following points when targeting the Edge or legacy engine.</span></span>  

*   <span data-ttu-id="0b65d-147">アプリは、プロセスごとに1つのバージョンの JsRT のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0b65d-147">Your app can support only one version of JsRT per process.</span></span>  
    
    <span data-ttu-id="0b65d-148">たとえば、Microsoft Edge エンジンランタイムとレガシエンジンランタイムを作成して、それらを同じプロセスで正常に実行することを想定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b65d-148">For example, you can't create a Microsoft Edge engine runtime and then a legacy engine runtime and expect them to run correctly in the same process.</span></span> <span data-ttu-id="0b65d-149">これはサポートされていないため、2つ目の DLL を読み込むことができないなど、文書化されていない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-149">This is unsupported and may result in undocumented behavior, such as failure to load the second DLL.</span></span>  
    
*   <span data-ttu-id="0b65d-150">Microsoft Edge エンジンをターゲットとしている場合、基になるプラットフォームが自動的に更新されると、アプリの新機能が予期せずに取得されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-150">When targeting the Microsoft Edge engine, your app may unexpectedly acquire new features when the underlying platform is automatically updated.</span></span>  
    
    <span data-ttu-id="0b65d-151">たとえば、従来のランタイムの Internet Explorer 11 モードでは、やなどのブロックスコープ変数の宣言がサポートされてい `let` `const` ます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-151">For example, the Internet Explorer 11 mode of the legacy runtime supports block-scoping variable declarations such as `let` and `const`.</span></span> <span data-ttu-id="0b65d-152">Microsoft Edge エンジンの自動バージョン管理動作が以前の標準になっていた場合、Internet Explorer 10 モードで使用したコードでは、ブロック範囲ルールが適用されていない場合は、プラットフォームが自動的にアップグレードされたときにエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-152">If the Microsoft Edge engine automatic versioning behavior had been the standard previously, code that had worked in Internet Explorer 10 mode, which did not have block-scoping rules, may have started failing when the platform had automatically upgraded.</span></span> <span data-ttu-id="0b65d-153">使用するランタイムモデルを選択する際には、この点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-153">This must be a consideration when choosing which runtime model to use.</span></span> <span data-ttu-id="0b65d-154">可能な限り Microsoft Edge エンジンをターゲットにする必要があると思われますが、今後は無効になる可能性がある JavaScript コード構造を使用することに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b65d-154">While we believe you should target the Microsoft Edge engine whenever possible, you must be careful about using JavaScript code structures that may become invalid in the future.</span></span>  
    
*   <span data-ttu-id="0b65d-155">Windows ストアの JsRT では、Microsoft Edge エンジン (chakra.dll) のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0b65d-155">JsRT for the Windows Store only supports the Microsoft Edge engine (chakra.dll).</span></span> <span data-ttu-id="0b65d-156">jscript9.dll の任意の JsRT API にリンクしようとしているアプリは、認定に合格しません。</span><span class="sxs-lookup"><span data-stu-id="0b65d-156">Apps attempting to link against any JsRT API in jscript9.dll will fail certification.</span></span>  
*   <span data-ttu-id="0b65d-157">jscript9.dll と chakra.dll の宣言を混同しないようにすることが重要です。これにより、 `JsCreateRuntime` `JsCreateContext` `JsStartDebugging` スタックが正しく分散されるためです。</span><span class="sxs-lookup"><span data-stu-id="0b65d-157">It is critical that you do not confuse the declaration of `JsCreateRuntime`, `JsCreateContext`, and `JsStartDebugging` between jscript9.dll and chakra.dll, because it will result in imbalancing the stack.</span></span>  
    
    <span data-ttu-id="0b65d-158">C と C++ を使っている場合は、呼び出しなどの操作を実行していない限り、誤った宣言を使用しようとすると、リンカーエラーが発生し `LoadLibrary` `GetProcAddress` ます。</span><span class="sxs-lookup"><span data-stu-id="0b65d-158">When using C and C++, you will receive a linker error if you try to use the wrong declaration, as long as you're not doing something like calling `LoadLibrary` and then `GetProcAddress`.</span></span> <span data-ttu-id="0b65d-159">.NET 開発者がこの問題を簡単に見つけることができない場合は、この機能を使用するときにコードを二重確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b65d-159">.NET developers may not find this problem as easily, so double-check your code when using this feature.</span></span>  
    
## <span data-ttu-id="0b65d-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b65d-160">See also</span></span>  

*   [<span data-ttu-id="0b65d-161">JavaScript ランタイムのホスティング</span><span class="sxs-lookup"><span data-stu-id="0b65d-161">JavaScript Runtime Hosting</span></span>](../javascript-runtime-hosting.md)
 