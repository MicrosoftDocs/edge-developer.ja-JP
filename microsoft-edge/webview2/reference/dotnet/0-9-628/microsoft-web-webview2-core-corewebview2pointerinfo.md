---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2PointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2PointerInfo。
ms.openlocfilehash: 34ffa5fe0eabfe8e822db2792d2b25ab5106442a
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012251"
---
# WebView2 クラス (CoreWebView2PointerInfo クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

これは主に、win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO オブジェクトを組み合わせたものです。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[ButtonChangeKind](#buttonchangekind) | ポインターイベントの ButtonChangeKind。
[DisplayRect](#displayrect) | Windows SDK (winuser) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect。
[フレーム Id](#frameid) | ポインターイベントのフレーム Id。
[場所の HimetricLocation](#himetriclocation) | ポインターイベントの HimetricLocation。
[HimetricLocationRaw](#himetriclocationraw) | ポインターイベントのロウ Metriclocation。
[履歴カウント](#historycount) | ポインターイベントの履歴カウント。
[InputData](#inputdata) | ポインターイベントの InputData。
[KeyStates](#keystates) | ポインターイベントの KeyStates。
[ペンフラグ](#penflags) | ポインターイベントのペンフラグ。
[ペンマスク](#penmask) | ポインターイベントのペンマスク。
[ペンの筆圧](#penpressure) | ポインターイベントのペンの筆圧。
[ペンの回転](#penrotation) | ポインターイベントのペン回転。
[PenTiltX](#pentiltx) | ポインターイベントの PenTiltX。
[PenTiltY](#pentilty) | ポインターイベントの PenTiltY。
[PerformanceCount](#performancecount) | ポインターイベントの PerformanceCount。
[ピクセルの位置](#pixellocation) | ポインターイベントのピクセルの位置。
[ピクセルの場所 Raw](#pixellocationraw) | ポインターイベントのピクセルの場所。
[PointerDeviceRect](#pointerdevicerect) | Windows SDK で定義されている POINTER_INFO 構造体の sourceDevice プロパティの PointerDeviceRect です (winuser. h)。
[PointerFlags](#pointerflags) | ポインターイベントの PointerFlags。
[ポインター Id](#pointerid) | ポインターイベントのポインタ Id。
[ポインターの種類](#pointerkind) | ポインターイベントのポインターの種類。
[時間](#time) | ポインターイベントの時刻。
[TouchContact](#touchcontact) | ポインターイベントの TouchContact。
[TouchContactRaw](#touchcontactraw) | ポインターイベントの TouchContactRaw。
[TouchFlags](#touchflags) | ポインターイベントの TouchFlags。
[TouchMask](#touchmask) | ポインターイベントの TouchMask。
[TouchOrientation](#touchorientation) | ポインターイベントの TouchOrientation。
[TouchPressure](#touchpressure) | ポインターイベントの TouchPressure。

## Members

#### ButtonChangeKind 

ポインターイベントの ButtonChangeKind。

> パブリック int [ボタンの Changekind](#buttonchangekind)

これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。 この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。

#### DisplayRect 

Windows SDK (winuser) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect。

> パブリック四角形の [Displayrect](#displayrect)

#### フレーム Id 

ポインターイベントのフレーム Id。

> パブリック uint [フレーム id](#frameid)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。

#### 場所の HimetricLocation 

ポインターイベントの HimetricLocation。

> パブリックポイントの [Himetriclocation](#himetriclocation)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。

#### HimetricLocationRaw 

ポインターイベントのロウ Metriclocation。

> パブリックポイントの [Himetriclocationraw](#himetriclocationraw)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。

#### 履歴カウント 

ポインターイベントの履歴カウント。

> パブリック uint [履歴カウント](#historycount)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。

#### InputData 

ポインターイベントの InputData。

> パブリック int の [Inputdata](#inputdata)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。

#### KeyStates 

ポインターイベントの KeyStates。

> パブリック uint [Keystates](#keystates)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。

#### ペンフラグ 

ポインターイベントのペンフラグ。

> パブリック uint の [フラグ](#penflags)

これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。 これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。

#### ペンマスク 

ポインターイベントのペンマスク。

> パブリック uint の [マスク](#penmask)

これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。 これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。

#### ペンの筆圧 

ポインターイベントのペンの筆圧。

> 公開 uint の [気圧](#penpressure)

これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。

#### ペンの回転 

ポインターイベントのペン回転。

> 公開 uint の [回転](#penrotation)

これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。

#### PenTiltX 

ポインターイベントの PenTiltX。

> パブリック int [PenTiltX](#pentiltx)

これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。

#### PenTiltY 

ポインターイベントの PenTiltY。

> パブリック int [PenTiltY](#pentilty)

これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。

#### PerformanceCount 

ポインターイベントの PerformanceCount。

> パブリック ulong [PerformanceCount](#performancecount)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。

#### ピクセルの位置 

ポインターイベントのピクセルの位置。

> パブリックポイントの [ピクセルの位置](#pixellocation)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。

#### ピクセルの場所 Raw 

ポインターイベントのピクセルの場所。

> パブリックポイントのピクセルの位置の [raw](#pixellocationraw)

これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。

#### PointerDeviceRect 

Windows SDK で定義されている POINTER_INFO 構造体の sourceDevice プロパティの PointerDeviceRect です (winuser. h)。

> パブリック四角形 [PointerDeviceRect](#pointerdevicerect)

#### PointerFlags 

ポインターイベントの PointerFlags。

> パブリック uint [PointerFlags](#pointerflags)

これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。 これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。

#### ポインター Id 

ポインターイベントのポインタ Id。

> パブリック uint [ポインター id](#pointerid)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。

#### ポインターの種類 

ポインターイベントのポインターの種類。

> パブリック uint [ポインターの種類](#pointerkind)

これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。 この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。 PT_PEN と PT_TOUCH をサポートします。

#### 時間 

ポインターイベントの時刻。

> 公開 uint [時間](#time)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。

#### TouchContact 

ポインターイベントの TouchContact。

> パブリック四角形 [TouchContact](#touchcontact)

これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。

#### TouchContactRaw 

ポインターイベントの TouchContactRaw。

> パブリック四角形 [TouchContactRaw](#touchcontactraw)

これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。

#### TouchFlags 

ポインターイベントの TouchFlags。

> パブリック uint [TouchFlags](#touchflags)

これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。 これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。

#### TouchMask 

ポインターイベントの TouchMask。

> パブリック uint [TouchMask](#touchmask)

これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。 これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。

#### TouchOrientation 

ポインターイベントの TouchOrientation。

> パブリック uint [TouchOrientation](#touchorientation)

これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。

#### TouchPressure 

ポインターイベントの TouchPressure。

> パブリック uint [TouchPressure](#touchpressure)

これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。

