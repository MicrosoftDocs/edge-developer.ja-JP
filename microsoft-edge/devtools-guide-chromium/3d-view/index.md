---
description: すべての 3D ビューとそれを使用する方法について。
title: 3D View (3D ビュー)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bd91939a19f02a426834a85ef92eca388f8f1eda
ms.sourcegitcommit: 5e218b24fb21fcfa9c82b99f17373fed1ba5a21c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "11203971"
---
# <a name="3d-view"></a>3D View (3D ビュー)  

**3D ビューを使用して**、ドキュメント オブジェクト モデル[(DOM)][MDNDocumentObjectModel]または[z-index][MDNZIndex]スタック コンテキストを移動して Web アプリをデバッグします。  この機能を使用すると、次のタスクを実行できます。  

*   [3D パースペクティブに翻訳された Web ページを確認する](#3d-dom)  
*   [z-index スタック コンテキストに基づくデバッグ](#z-index)  
*   [複合レイヤーを使用して 3D ビューから Layers ツールの機能にアクセスする](#composited-layers)  
*   [DOM ウィンドウまたは z-index ウィンドウ](#changing-your-view) の混乱 [の一部をクリアする](#change-the-scope-of-your-exploration)  
*   [DOM の問題や z-index の](#dom-color-type) 問題を最適にデバッグするために [配色を選ぶ](#z-index-color-type)  

3D View プロジェクトの初期プロトタイプを確認し、コードを自分で実行する場合は [、[3D ビュー][GithubMicrosoftedgeDevtoolssamples3dview]サンプル] に移動します。  

左側には、デバッグ エクスペリエンスに使用できる 3 つのウィンドウがあります。  

*   [Z インデックス ウィンドウ](#z-index)。  z-index コンテキストを念頭に置いて、Web アプリ内のさまざまな要素を移動します。  **Z インデックス ウィンドウは**既定のウィンドウです。  
*   [3D DOM](#3d-dom)ウィンドウ。  すべての要素に簡単にアクセスできる DOM 全体を探索します。  ウィンドウにアクセスするには **、Z** インデックス ウィンドウの横にある **DOM ウィンドウを選択** します。  
*   [ [複合レイヤー] ウィンドウ](#composited-layers) 。  別の 3D 要素を追加して、レイヤーの観点からより包括的なエクスペリエンスを作成します。  ウィンドウにアクセスするには、DOM ウィンドウの **横にある [複合レイヤー** ] ウィンドウ **を選択** します。  
    
右側に、Z-index、3D [DOM、](#3d-dom)またはコンポジット レイヤーから選択した項目[が表示されます](#composited-layers)。 [](#z-index)  

## <a name="navigating-the-canvas"></a>キャンバスの移動  

:::image type="complex" source="../media/3d-view-canvas.msft.png" alt-text="3D ビューのキャンバス" lightbox="../media/3d-view-canvas.msft.png":::
   3D ビューのキャンバス  
:::image-end:::  

### <a name="keyboard-shortcuts"></a>キーボード ショートカット  

*   DOM を回転する: 水平方向に回転するには、キーとキー `left-arrow` を `right-arrow` 選択します。  垂直方向に回転するには、キーとキー `up-arrow` を `down-arrow` 選択します。  
*   DOM を移動する: 隣接する要素を移動するには、要素を選択し、キーとキー `up-arrow` を選択 `down-arrow` します。  

### <a name="mouse-controls"></a>マウス コントロール  

*   DOM を回転する: キャンバス空間を選択してドラッグします。  
*   DOM の周囲をパンする: コンテキスト メニュー \(右クリック\) を開き、DOM を移動する方向にドラッグします。  
*   ズーム: タッチパッドを 2 本指でドラッグするか、マウスのスクロール ホイールを使用します。  

### <a name="on-screen-controls"></a>オンスクリーン コントロール  

:::image type="complex" source="../media/3d-view-controls-small.msft.png" alt-text="オンスクリーン コントロール" lightbox="../media/3d-view-controls-small.msft.png":::
   オンスクリーン コントロール  
:::image-end:::  

*   キャンバス ビューを元のビューにリセットする: **** [カメラのリセット] ボタンを選択するか、[カメラの表示と中央に戻**す]** \(横向き更新アイコン\) ボタンを選択します。  
*   キャンバスを更新する \(ブラウザーが変更された場合やデバイス エミュレーター ビューに切り替えた場合など****)。[スナップショットの再取得]**** ボタンを選択するか、[新しいスナップショットを取得] ボタン \(refresh icon\) を選択します。  

## <a name="z-index"></a>Z-index  

:::image type="complex" source="../media/3d-view-z-index-view-box.msft.png" alt-text="Z-index ビュー" lightbox="../media/3d-view-z-index-view-box.msft.png":::
   Z-index ビュー  
:::image-end:::  

Z **インデックス ウィンドウには** **3D DOM** ウィンドウとの共有機能が含まれていますが、ペインには依然として、そのウィンドウに固有の要素があります。  

### <a name="highlight-elements-with-stacking-context"></a>スタック コンテキストを使用して要素を強調表示する  

[ **コンテキストを重ね合** った要素を強調表示する] 設定を使用すると、キャンバス上の要素の z-index タグを \(and off\) オンにできます。  このチェック ボックスは既定で選択されます。  

### <a name="change-the-scope-of-your-exploration"></a>探索の範囲を変更する  

[ **すべての要素を表示** ] ボタンは、その下の設定を変更した後に DOM のすべての要素を表示する最も簡単な方法です。  

[ **コンテキストをスタックする要素のみを** 表示] ボタンは、コンテキストを積み重ねることなく要素を削除し、DOM をフラット化してナビゲーションを容易にします。  

[ **選択した要素を分離する** ] ボタンは、基本的に 1 つの 3 つのボタンです。  [選択した要素を分離する****] ボタンの下には、[**** すべての親を表示する] チェック ボックスと [新しいスタック コンテキストを持つ親のみを保持する] チェック ボックスの下に**2 つのチェック ボックス**があります。  

[ **すべての親を表示する]** チェック ボックスは既定でオンになっています。  キャンバスに要素と親を表示するには、要素を選択し、[選択した要素を分離] ボタン **を選択** します。  

キャンバスに新しいスタック コンテキストを持つ要素と親を表示するには、[新しいスタック コンテキスト**** を使用して親のみを保持する] 設定をオンにし、[選択した要素を分離] ボタンを**選択します。**  

キャンバスに選択した要素を表示するには、両方の設定をオフにし、[選択した要素を分離] ボタン **を選択** します。  

**3D DOM**ウィンドウの下部で、[親と同じペイント順序の要素を非表示**にする] チェック ボックスをオン**にします。  チェック ボックスを選択して選択解除すると、選択に基づいて要素が更新されます。  選択すると、ペイント順序を共有する要素は親にフラット化されます。  

このオプションは、より複雑な Web ページがキャンバスに作成する混乱の一部をクリアするためのものになります。  

### <a name="z-index-color-type"></a>Z インデックスの色の種類  

キャンバス内の DOM に使用できるさまざまな視覚エフェクトを示します。  楽しみのために使うのか、視覚エフェクトを使って DOM をよりよく視覚化するのに役立つのかに関わり、DevTools にはさまざまな色と背景色を使用する**オプションがあります。**  **Z インデックス ウィンドウは**、**紫から白**、**** 背景色を**3D DOM ウィンドウと共有**します。  z-index ラベルの視覚的要素が追加された場合、フィードバックによって色オプションの数が減少しました。  新しい簡略化により、z-index デバッグ エクスペリエンスが向上します。  ラジオ ボタンを使用すると、オプションを切り替え、色の種類を選択できます。  色の種類は、プロジェクトに最も適した色か、最も好きな色の種類のいずれかです。  

## <a name="3d-dom"></a>3D DOM  

:::image type="complex" source="../media/3d-view-dom-purple-box.msft.png" alt-text="DOM ビュー" lightbox="../media/3d-view-dom-purple-box.msft.png":::
   DOM ビュー  
:::image-end:::  

z-index エクスペリエンスではなく、より多くの一般的なデバッグ ビューを使用する場合 **、3D DOM** は DOM の全体的な外観を提供します。  z-index コンテキストが削除されたので、DOM は、より密接に、クリーンにスタックされます。  **3D DOM**ウィンドウにも同様の機能がありますが、いくつかのニュアンスがあります。  

### <a name="changing-your-view"></a>ビューの変更  

**[3D DOM]** ウィンドウ**** の [選択した要素を分離する] ボタンには、[子を含**める]** チェック ボックスと [親を含める]**チェック ボックス**があります。  どちらのチェック ボックスも既定でオンになっています。  つまり、要素を選択した**** 後で [選択した要素を分離] ボタンを選択すると、選択した要素、要素の親、要素の子がキャンバスに表示されます。  [子を**含める]** 設定を**** オフにし、[選択した要素を分離する] ボタンを再度選択すると、選択した要素と要素の親が表示されます。  [子を含める] 設定をオンにし****、[親を含める] 設定**** をオフにし、[選択した要素を分離する] ボタンを選択すると、要素と子がキャンバスに表示されます。 ****  両方の設定をオフにし、[選択**** した要素を分離] ボタンを選択すると、キャンバスには以前に選択した要素だけが表示されます。  

コントロール ウィンドウの [ページの入れ子レベル] という名前のスライダー **で、** その横に数値を指定します。  数値は、ドキュメントのレイヤー数を示します。  スライダーを左にドラッグすると、最も外側のレイヤーは、入れ子レベルが設定され、DOM 内の最も遠い背面要素だけが表示されるまではがれ出します `1` 。  混乱の一部を削除するには、スライダーをドラッグします。  これは、下位レベルで何が起こっているかを詳しく見るのに役立ちます。  

### <a name="dom-color-type"></a>DOM の色の種類  

**3D DOM ウィンドウには**、次のオプションが表示されます。  

*   3 つの異なるカラーウェイ。  
    *   **ヒートマップ - 紫から白へ**  
    *   **ヒートマップ - 青から黄色**  
    *   **ヒートマップ - 虹**  
*   **背景色を使用する**  
*   **画面テクスチャの使用**  
    
[ **画面テクスチャを使用する]** オプションは、デバッグ エクスペリエンスにコンテキストを追加します。  Web ページのコンテンツを要素に直接表示します。  

## <a name="composited-layers"></a>複合レイヤー

:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[複合レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   **[コンポジット レイヤー]** ウィンドウ
:::image-end:::  

[ **複合レイヤー] ウィンドウは** 、コンテキストを変更せずにレイヤー ツール **の** 要素を開きます。  引き続き各レイヤーの詳細にアクセスし、スロー スクロールを下げ、ペイント******することができます**。

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

Microsoft Edge Devtools チームは、UI に取り組み、フィードバックに基づいて 3D ビューにさらに機能を追加しています。  フィードバックを送信して、Microsoft Edge DevTools の改善に役立ちます。  DevTools**で [** フィードバックの送信] アイコンを選択するか、Windows/Linux または macOS で選択し `Alt` + `Shift` + `I` `Option` + `Shift` + `I` 、DevTools に対するフィードバックまたは機能要求を入力します。  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft Edge DevTools 3D ビュー - MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
