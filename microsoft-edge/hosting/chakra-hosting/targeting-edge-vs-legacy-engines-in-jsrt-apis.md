---
description: 'さまざまな Windows 10 JavaScript エンジンのターゲットを変更する方法について説明します。 '
title: JsRT Api での Microsoft Edge とレガシエンジンのターゲット設定Microsoft ドキュメント
ms.custom: ''
ms.date: 03/05/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cbc7df6c-0bc9-48f5-b9ad-b9ed31c42f92
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: ed0dc8c67b8189a7433d52185aa995997edb70a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569252"
---
# JsRT Api での Microsoft Edge とレガシエンジンのターゲット設定

Windows 10 では、次の2種類の JavaScript エンジンがサポートされています。

-   Internet Explorer 11 に付属していて、サポートされている古い Chakra エンジン (以下の*レガシエンジン*または jscript9 とも呼ばれます)。 このエンジンは時間内に凍結され、Win 8.1/IE11 release の場合とは基本的に変わりません。  
  
-   Windows 10 の Microsoft Edge の新しいブラウザーを同梱およびサポートしている新しい Chakra engine (以下の*Edge エンジン*または Chakra とも呼ばれます)。 このエンジンは継続的に更新され、"生きた"[エッジ](https://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx)エンジンをサポートします。 Microsoft edge エンジンは、従来のエンジンとは異なり、Microsoft Edge エンジンはどのような形式のバージョン管理スクリプト機能を備えていないかを示しています。  
  
 JavaScript Runtime ホスティング (JsRT) API を使ってアプリを作成する場合、レガシまたは Microsoft Edge のどちらのエンジンをターゲットにするかを選ぶことができます。  
  
-   既存のアプリケーションの下位互換性を強調する必要がある場合は、レガシエンジンをターゲットにします。  
  
-   アプリをすぐに使用できるようにする必要がある場合 (たとえば、ECMAScript 6 など)、新しい JavaScript 機能をサポートするには、Microsoft Edge エンジンをターゲットにします。  
  
 このトピックには、さまざまなエンジンのターゲットを指定する方法についての詳細が含まれています。  
  
## 希望するバージョンをターゲットにする  
 アプリを作成するときに、Microsoft Edge エンジンとレガシエンジンのいずれかをサポートする JsRT のバージョンを選ぶことができます。 上記のガイドラインに基づいて、JsRT のバージョンを選ぶことができます。 これらの違いに対応するために、、、およびに対して次の変更が加えられました `JsCreateRuntime` `JsCreateContext` `JsStartDebugging` 。  
  
 対象 `JsCreateRuntime` :  
  
-   従来のエンジンをターゲットとする場合、 `JsRuntimeVersionEdge` 列挙値は廃止され、代わりに値を使用するようにメッセージが表示され `JsRuntimeVersionInternetExplorer11` ます。  
  
-   Microsoft Edge エンジンをターゲットとして、関数から version パラメーターが省略されてい `JsCreateRuntime` ます。  
  
    ```cpp  
    JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
    ```  
  
 For `JsCreateContext` と `JsStartDebugging` :  
  
-   レガシエンジンをターゲットとする場合、 `IDebugApplication` インターフェイスは、独自のリモート以外のデバッグメソッドを提供するために使われます。 デバッグのために `JsCreateContext` 、 `JsStartDebugging` 関数は `IDebugApplication` パラメーターとして受け取ります。  
  
-   Microsoft Edge エンジンをターゲットとしている場合、 `IDebugApplication` インターフェイスは推奨されません。 Chakra エンジンは、ユーザーからの実装を必要とせずに、Visual Studio デバッガーでネイティブおよびスクリプトのデバッグ機能を有効にし `IDebugApplication` ます。 インターフェイスは、 `JsCreateContext` および結果としてのパラメーターではなくなりました `JsStartDebugging` 。  
  
 従来のエンジンの以前の Api のシグネチャは、次のようになります。  
  
```cpp  
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsRuntimeVersion version, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
  
JsErrorCode JsCreateContext(JsRuntimeHandle runtime, IDebugApplication *debugApplication, JsContextRef *newContext);  
  
JsErrorCode JsStartDebugging(IDebugApplication *debugApplication);  
```  
  
 Microsoft Edge エンジンの上にある Api のシグネチャは、次のようになります。  
  
```cpp  
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
  
JsErrorCode JsCreateContext(JsRuntimeHandle runtime, JsContextRef *newContext);  
  
JsErrorCode JsStartDebugging();  
```  
  
## Visual C++ を使って、好みのバージョンをコンパイルする  
 Visual C++ を使っている場合は、JsRT ヘッダーを含めることによって JsRT API をインポートし、リンカーの入力ファイルの一覧に JsRT が含まれていることを確認します。  
  
```cpp  
#include <jsrt.h>  
```  
  
 ![リンカー入力ファイルとして jsrt を追加する](../chakra-hosting/media/js-chakra.png "JS_Chakra_")  
  
 Microsoft Edge エンジンのバイナリをターゲットにする場合は、jsrt を含める前にマクロを定義する必要があります。 jsrt にリンクする代わりに、 `USE_EDGEMODE_JSRT` chakrart にリンクする必要があります。  
  
```cpp  
#define USE_EDGEMODE_JSRT  
#include <jsrt.h>  
```  
  
 ![リンカー入力ファイルとして chakrart を追加する](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting_")  
  
 新しいアプリケーションを初めて使用する場合は、JsRT API に対するコードの作成を開始することができるようになりました。  
  
## .NET を使って適切なバージョンをコンパイルする  
 .NET と P/Invoke を使っている場合は、JsRT API [DllImport] 宣言を変更して、jscript9 の代わりに chakra をインポートする必要があります。 さらに、の定義を変更して、 `JsCreateRuntime` `JsRuntimeVersion` パラメーターとの定義を削除し、パラメーターを削除し `JsCreateContext` `JsStartDebugging` `IDebugApplication` ます。  
  
 従来のエンジンの場合は、次のコードを使用します。  
  
```c#  
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
  
 Microsoft Edge エンジンの場合は、次のコードを使用します。  
  
```c#  
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
>  関数ポインター (LoadLibrary/GetProcAddress など) を手動でマーシャリングする場合は、メソッドの宣言を混同しないようにする必要があります。そうしないと、スタックの均衡が解除されるため、アプリのクラッシュの原因となる予期しない動作が発生する可能性があります。 インポートコードで jscript9 のインスタンスのグローバル検索と置換を実行した場合は、このパラメーターを見逃してしまうため、同じ問題が発生し `version` ます。  
  
## まとめ  
 Windows 10 では、JavaScript のホスト Api が2つに分かれています。 これらの Api では、"生きた" Microsoft edge エンジンがサポートされるようになりました。これは、Microsoft Edge の "生きた" Microsoft Edge エンジンと連携する言語機能を備えています。 デスクトップまたはストアアプリからこれらの機能を活用して、アプリケーションを拡張したり、既存のコードベースで最新の Web スキルを活用したりすることができます。 ただし、以前のバージョンには微妙な違いがあるため、Edge またはレガシエンジンをターゲットとする場合は、次の点に注意する必要があります。  
  
-   アプリは、プロセスごとに1つのバージョンの JsRT のみをサポートしています。  
  
     たとえば、Microsoft Edge エンジンランタイムとレガシエンジンランタイムを作成して、それらを同じプロセスで正常に実行することを想定することはできません。 これはサポートされていないため、2つ目の DLL を読み込むことができないなど、文書化されていない動作が発生する可能性があります。  
  
-   Microsoft Edge エンジンをターゲットとしている場合、基になるプラットフォームが自動的に更新されると、アプリの新機能が予期せずに取得されることがあります。  
  
     たとえば、従来のランタイムの Internet Explorer 11 モードでは、やなどのブロックスコープ変数の宣言がサポートされてい `let` `const` ます。 Microsoft Edge エンジンの自動バージョン管理動作が以前の標準になっていた場合、Internet Explorer 10 モードで使用したコードでは、ブロック範囲ルールが適用されていない場合は、プラットフォームが自動的にアップグレードされたときにエラーが発生する可能性があります。 使用するランタイムモデルを選択する際には、この点を考慮する必要があります。 可能な限り Microsoft Edge エンジンをターゲットにする必要があると思われますが、今後は無効になる可能性がある JavaScript コード構造を使用することに注意する必要があります。  
  
-   Windows ストアの JsRT では、Microsoft Edge エンジン (chakra) のみがサポートされています。 Jscript9 の任意の JsRT API にリンクしようとしているアプリは、認定に合格しません。  
  
-   Jscript9 と chakra の間の宣言を混同しないようにすることが重要です `JsCreateRuntime` `JsCreateContext` 。これは、 `JsStartDebugging` スタックが imbalancing となるためです。  
  
     C と C++ を使っている場合は、呼び出しなどの操作を実行していない限り、誤った宣言を使用しようとすると、リンカーエラーが発生し `LoadLibrary` `GetProcAddress` ます。 .NET 開発者がこの問題を簡単に見つけることができない場合は、この機能を使用するときにコードを二重確認してください。  
  
## 関連項目  
 [JavaScript ランタイムホスティング](../javascript-runtime-hosting.md)
 