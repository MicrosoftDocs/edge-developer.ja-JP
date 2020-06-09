---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: ef0546c03e2d2ccc87677125772b1663f2ec6362
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699058"
---
# インターフェイス ICoreWebView2ExperimentalPointerInfo 

> [!NOTE]
> これは、プレリリース SDK バージョン0.9.538 に同梱されている実験的な API です。

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

これは主に、win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO オブジェクトを組み合わせたものです。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_ButtonChangeKind](#get_buttonchangekind) | ポインターイベントの ButtonChangeKind を取得します。
[get_DisplayRect](#get_displayrect) | Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。
[get_FrameId](#get_frameid) | ポインターイベントのフレーム Id を取得します。
[get_HimetricLocation](#get_himetriclocation) | ポインターイベントの HimetricLocation を取得します。
[get_HimetricLocationRaw](#get_himetriclocationraw) | ポインターイベントの HimetricLocationRaw を取得します。
[get_HistoryCount](#get_historycount) | ポインターイベントの履歴カウントを取得します。
[get_InputData](#get_inputdata) | ポインターイベントの InputData を取得します。
[get_KeyStates](#get_keystates) | ポインターイベントの KeyStates を取得します。
[get_PenFlags](#get_penflags) | ポインターイベントのペンフラグを取得します。
[get_PenMask](#get_penmask) | ポインターイベントのペンマスクを取得します。
[get_PenPressure](#get_penpressure) | ポインターイベントの筆圧を取得します。
[get_PenRotation](#get_penrotation) | ポインターイベントのペン回転を取得します。
[get_PenTiltX](#get_pentiltx) | ポインターイベントの PenTiltX を取得します。
[get_PenTiltY](#get_pentilty) | ポインターイベントの PenTiltY を取得します。
[get_PerformanceCount](#get_performancecount) | ポインターイベントの PerformanceCount を取得します。
[get_PixelLocation](#get_pixellocation) | ポインターイベントのピクセルの位置を取得します。
[get_PixelLocationRaw](#get_pixellocationraw) | ポインターイベントのピクセルの場所を取得します。
[get_PointerDeviceRect](#get_pointerdevicerect) | Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。
[get_PointerFlags](#get_pointerflags) | ポインターイベントの PointerFlags を取得します。
[get_PointerId](#get_pointerid) | ポインターイベントのポインタ Id を取得します。
[get_PointerKind](#get_pointerkind) | ポインターイベントのポインターの種類を取得します。
[get_Time](#get_time) | ポインターイベントの時刻を取得します。
[get_TouchContact](#get_touchcontact) | ポインターイベントの TouchContact を取得します。
[get_TouchContactRaw](#get_touchcontactraw) | ポインターイベントの TouchContactRaw を取得します。
[get_TouchFlags](#get_touchflags) | ポインターイベントの TouchFlags を取得します。
[get_TouchMask](#get_touchmask) | ポインターイベントの TouchMask を取得します。
[get_TouchOrientation](#get_touchorientation) | ポインターイベントの TouchOrientation を取得します。
[get_TouchPressure](#get_touchpressure) | ポインターイベントの TouchPressure を取得します。
[put_ButtonChangeKind](#put_buttonchangekind) | ポインターイベントの ButtonChangeKind を設定します。
[put_DisplayRect](#put_displayrect) | Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。
[put_FrameId](#put_frameid) | ポインターイベントのフレーム Id を設定します。
[put_HimetricLocation](#put_himetriclocation) | ポインターイベントの HimetricLocation を設定します。
[put_HimetricLocationRaw](#put_himetriclocationraw) | ポインターイベントの HimetricLocationRaw を設定します。
[put_HistoryCount](#put_historycount) | ポインターイベントの履歴カウントを設定します。
[put_InputData](#put_inputdata) | ポインターイベントの InputData を設定します。
[put_KeyStates](#put_keystates) | ポインターイベントの KeyStates を設定します。
[put_PenFlags](#put_penflags) | ポインターイベントのペンフラグを設定します。
[put_PenMask](#put_penmask) | ポインターイベントの "ペンマスク" を設定します。
[put_PenPressure](#put_penpressure) | ポインターイベントの "ペンの筆圧" を設定します。
[put_PenRotation](#put_penrotation) | ポインターイベントのペン回転を設定します。
[put_PenTiltX](#put_pentiltx) | ポインターイベントの PenTiltX を設定します。
[put_PenTiltY](#put_pentilty) | ポインターイベントの PenTiltY を設定します。
[put_PerformanceCount](#put_performancecount) | ポインターイベントの PerformanceCount を設定します。
[put_PixelLocation](#put_pixellocation) | ポインターイベントのピクセルの位置を設定します。
[put_PixelLocationRaw](#put_pixellocationraw) | ポインターイベントのピクセルの場所を設定します。
[put_PointerDeviceRect](#put_pointerdevicerect) | Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。
[put_PointerFlags](#put_pointerflags) | ポインターイベントの PointerFlags を設定します。
[put_PointerId](#put_pointerid) | ポインターイベントのポインタ Id を設定します。
[put_PointerKind](#put_pointerkind) | ポインターイベントのポインターの種類を設定します。
[put_Time](#put_time) | ポインターイベントの時刻を設定します。
[put_TouchContact](#put_touchcontact) | ポインターイベントの TouchContact を設定します。
[put_TouchContactRaw](#put_touchcontactraw) | ポインターイベントの TouchContactRaw を設定します。
[put_TouchFlags](#put_touchflags) | ポインターイベントの TouchFlags を設定します。
[put_TouchMask](#put_touchmask) | ポインターイベントの TouchMask を設定します。
[put_TouchOrientation](#put_touchorientation) | ポインターイベントの TouchOrientation を設定します。
[put_TouchPressure](#put_touchpressure) | ポインターイベントの TouchPressure を設定します。

この例では、3つのフィールドをすべて受け取り、HWND やハンドルなどの win32 固有のデータ型を除外しています。 注: sourceDevice は使用されますが、PointerDeviceRect と DisplayRect で sourceDevice の既存のユースケースをカバーすることを前提としています。 また、point または rect のいずれかの場所が、webview の物理座標であることが想定されているという大きな違いがあります。 つまり、webview と DPI のスケーリングが適用された相対的な座標です。

## Members

#### get_ButtonChangeKind 

ポインターイベントの ButtonChangeKind を取得します。

> パブリック HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 * buttonChangeKind)

これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。 この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。

#### get_DisplayRect 

Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の sourceDevice プロパティの DisplayRect を取得します。

> パブリック HRESULT [get_DisplayRect](#get_displayrect)(RECT * displayrect)

#### get_FrameId 

ポインターイベントのフレーム Id を取得します。

> パブリック HRESULT [get_FrameId](#get_frameid)(UINT32 * フレーム id)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。

#### get_HimetricLocation 

ポインターイベントの HimetricLocation を取得します。

> パブリック HRESULT [get_HimetricLocation](#get_himetriclocation)(ポイント * himetricLocation)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。

#### get_HimetricLocationRaw 

ポインターイベントの HimetricLocationRaw を取得します。

> パブリック HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(ポイント * himetricLocationRaw)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。

#### get_HistoryCount 

ポインターイベントの履歴カウントを取得します。

> パブリック HRESULT [get_HistoryCount](#get_historycount)(UINT32 * 履歴カウント)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。

#### get_InputData 

ポインターイベントの InputData を取得します。

> パブリック HRESULT [get_InputData](#get_inputdata)(INT32 * inputdata)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。

#### get_KeyStates 

ポインターイベントの KeyStates を取得します。

> パブリック HRESULT [get_KeyStates](#get_keystates)(DWORD * keystates)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。

#### get_PenFlags 

ポインターイベントのペンフラグを取得します。

> パブリック HRESULT [get_PenFlags](#get_penflags)(UINT32 * ペンフラグ)

これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。 これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。

#### get_PenMask 

ポインターイベントのペンマスクを取得します。

> パブリック HRESULT [get_PenMask](#get_penmask)(UINT32 * ペンマスク)

これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。 これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。

#### get_PenPressure 

ポインターイベントの筆圧を取得します。

> パブリック HRESULT [get_PenPressure](#get_penpressure)(UINT32 * の筆圧)

これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。

#### get_PenRotation 

ポインターイベントのペン回転を取得します。

> パブリック HRESULT [get_PenRotation](#get_penrotation)(UINT32 * の回転回転)

これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。

#### get_PenTiltX 

ポインターイベントの PenTiltX を取得します。

> パブリック HRESULT [get_PenTiltX](#get_pentiltx)(INT32 * PenTiltX)

これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。

#### get_PenTiltY 

ポインターイベントの PenTiltY を取得します。

> パブリック HRESULT [get_PenTiltY](#get_pentilty)(INT32 * PenTiltY)

これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。

#### get_PerformanceCount 

ポインターイベントの PerformanceCount を取得します。

> パブリック HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 * PerformanceCount)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。

#### get_PixelLocation 

ポインターイベントのピクセルの位置を取得します。

> パブリック HRESULT [get_PixelLocation](#get_pixellocation)(ポイント * ピクセルの場所)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。

#### get_PixelLocationRaw 

ポインターイベントのピクセルの場所を取得します。

> パブリック HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(ポイント * ピクセルの場所 raw)

これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。

#### get_PointerDeviceRect 

Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを取得します。

> パブリック HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT * PointerDeviceRect)

#### get_PointerFlags 

ポインターイベントの PointerFlags を取得します。

> パブリック HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 * PointerFlags)

これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。 これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。

#### get_PointerId 

ポインターイベントのポインタ Id を取得します。

> パブリック HRESULT [get_PointerId](#get_pointerid)(UINT32 * ポインター id)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。

#### get_PointerKind 

ポインターイベントのポインターの種類を取得します。

> パブリック HRESULT [get_PointerKind](#get_pointerkind)(DWORD * ポインター kind)

これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。 この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。 PT_PEN と PT_TOUCH をサポートします。

#### get_Time 

ポインターイベントの時刻を取得します。

> パブリック HRESULT [get_Time](#get_time)(DWORD * 時刻)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。

#### get_TouchContact 

ポインターイベントの TouchContact を取得します。

> パブリック HRESULT [get_TouchContact](#get_touchcontact)(RECT * TouchContact)

これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。

#### get_TouchContactRaw 

ポインターイベントの TouchContactRaw を取得します。

> パブリック HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT * TouchContactRaw)

これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。

#### get_TouchFlags 

ポインターイベントの TouchFlags を取得します。

> パブリック HRESULT [get_TouchFlags](#get_touchflags)(UINT32 * TouchFlags)

これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。 これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。

#### get_TouchMask 

ポインターイベントの TouchMask を取得します。

> パブリック HRESULT [get_TouchMask](#get_touchmask)(UINT32 * TouchMask)

これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。 これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。

#### get_TouchOrientation 

ポインターイベントの TouchOrientation を取得します。

> パブリック HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 * TouchOrientation)

これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。

#### get_TouchPressure 

ポインターイベントの TouchPressure を取得します。

> パブリック HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 * TouchPressure)

これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。

#### put_ButtonChangeKind 

ポインターイベントの ButtonChangeKind を設定します。

> パブリック HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)

これは、POINTER_INFO 構造体の ButtonChangeKind プロパティに対応しています。 この値は、Windows SDK (winuser) の POINTER_BUTTON_CHANGE_KIND 列挙型で定義されます。

#### put_DisplayRect 

Windows SDK (winuser) で定義されている POINTER_INFO struct の sourceDevice プロパティの DisplayRect を設定します。

> パブリック HRESULT [put_DisplayRect](#put_displayrect)(RECT displayrect)

#### put_FrameId 

ポインターイベントのフレーム Id を設定します。

> パブリック HRESULT [put_FrameId](#put_frameid)(UINT32 フレーム id)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のフレーム Id プロパティに対応しています。

#### put_HimetricLocation 

ポインターイベントの HimetricLocation を設定します。

> パブリック HRESULT [put_HimetricLocation](#put_himetriclocation)(ポイント himetricLocation)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。

#### put_HimetricLocationRaw 

ポインターイベントの HimetricLocationRaw を設定します。

> パブリック HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(ポイント himetricLocationRaw)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。

#### put_HistoryCount 

ポインターイベントの履歴カウントを設定します。

> パブリック HRESULT [put_HistoryCount](#put_historycount)(UINT32 履歴カウント)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の履歴カウントプロパティに対応しています。

#### put_InputData 

ポインターイベントの InputData を設定します。

> パブリック HRESULT [put_InputData](#put_inputdata)(INT32 inputdata)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の InputData プロパティに対応しています。

#### put_KeyStates 

ポインターイベントの KeyStates を設定します。

> パブリック HRESULT [put_KeyStates](#put_keystates)(DWORD keystates)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体の dwKeyStates プロパティに対応しています。

#### put_PenFlags 

ポインターイベントのペンフラグを設定します。

> パブリック HRESULT [put_PenFlags](#put_penflags)(UINT32 のフラグ)

これは、POINTER_PEN_INFO 構造体の "ペン" プロパティに対応しています。 これらの値は、Windows SDK (winuser) の PEN_FLAGS 定数によって定義されます。

#### put_PenMask 

ポインターイベントの "ペンマスク" を設定します。

> パブリック HRESULT [put_PenMask](#put_penmask)(UINT32 のマスク)

これは POINTER_PEN_INFO 構造体の "ペンマスク" プロパティに対応します。 これらの値は、Windows SDK (winuser) の PEN_MASK 定数によって定義されます。

#### put_PenPressure 

ポインターイベントの "ペンの筆圧" を設定します。

> パブリック HRESULT [put_PenPressure](#put_penpressure)(UINT32)

これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の圧力プロパティに対応しています。

#### put_PenRotation 

ポインターイベントのペン回転を設定します。

> パブリック HRESULT [put_PenRotation](#put_penrotation)(UINT32 の回転)

これは、Windows SDK (winuser .h) で定義されている POINTER_PEN_INFO 構造体の rotation プロパティに対応しています。

#### put_PenTiltX 

ポインターイベントの PenTiltX を設定します。

> パブリック HRESULT [put_PenTiltX](#put_pentiltx)(INT32 PenTiltX)

これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。

#### put_PenTiltY 

ポインターイベントの PenTiltY を設定します。

> パブリック HRESULT [put_PenTiltY](#put_pentilty)(INT32 PenTiltY)

これは、Windows SDK (winuser) で定義されている POINTER_PEN_INFO 構造体のプロパティに対応しています。

#### put_PerformanceCount 

ポインターイベントの PerformanceCount を設定します。

> パブリック HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 PerformanceCount)

これは、Windows SDK (winuser) で定義されている POINTER_INFO 構造体のプロパティに対応しています。

#### put_PixelLocation 

ポインターイベントのピクセルの位置を設定します。

> パブリック HRESULT [put_PixelLocation](#put_pixellocation)(ポイントピクセルの場所)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO struct の Ptの Location プロパティに対応しています。

#### put_PixelLocationRaw 

ポインターイベントのピクセルの場所を設定します。

> パブリック HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(ポイントのピクセルの位置に raw)

これは、Windows SDK (winuser .h) で定義された POINTER_INFO struct の Ptピクセルの Raw プロパティに対応しています。

#### put_PointerDeviceRect 

Windows SDK (winuser) で定義されているように、POINTER_INFO 構造体の sourceDevice プロパティのを設定します。

> パブリック HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT PointerDeviceRect)

#### put_PointerFlags 

ポインターイベントの PointerFlags を設定します。

> パブリック HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 PointerFlags)

これは POINTER_INFO 構造体の pointerFlags プロパティに対応しています。 これらの値は、Windows SDK (winuser) の POINTER_FLAGS 定数によって定義されます。

#### put_PointerId 

ポインターイベントのポインタ Id を設定します。

> パブリック HRESULT [put_PointerId](#put_pointerid)(UINT32 ポインター id)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体のポインター Id プロパティに対応しています。

#### put_PointerKind 

ポインターイベントのポインターの種類を設定します。

> パブリック HRESULT [put_PointerKind](#put_pointerkind)(DWORD ポインター kind)

これは、POINTER_INFO 構造体のポインター Kind プロパティに対応しています。 この値は、Windows SDK (winuser) の POINTER_INPUT_KIND 列挙型で定義されます。 PT_PEN と PT_TOUCH をサポートします。

#### put_Time 

ポインターイベントの時刻を設定します。

> パブリック HRESULT [put_Time](#put_time)(DWORD 時刻)

これは、Windows SDK (winuser .h) で定義されている POINTER_INFO 構造体の dwTime プロパティに対応しています。

#### put_TouchContact 

ポインターイベントの TouchContact を設定します。

> パブリック HRESULT [put_TouchContact](#put_touchcontact)(RECT TouchContact)

これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の rcContact プロパティに対応しています。

#### put_TouchContactRaw 

ポインターイベントの TouchContactRaw を設定します。

> パブリック HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT TouchContactRaw)

これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO 構造体のプロパティに対応しています。

#### put_TouchFlags 

ポインターイベントの TouchFlags を設定します。

> パブリック HRESULT [put_TouchFlags](#put_touchflags)(UINT32 TouchFlags)

これは POINTER_TOUCH_INFO 構造体の touchFlags プロパティに対応しています。 これらの値は、Windows SDK (winuser) の TOUCH_FLAGS 定数によって定義されます。

#### put_TouchMask 

ポインターイベントの TouchMask を設定します。

> パブリック HRESULT [put_TouchMask](#put_touchmask)(UINT32 TouchMask)

これは POINTER_TOUCH_INFO 構造体の touchMask プロパティに対応しています。 これらの値は、Windows SDK (winuser) の TOUCH_MASK 定数によって定義されます。

#### put_TouchOrientation 

ポインターイベントの TouchOrientation を設定します。

> パブリック HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 TouchOrientation)

これは、Windows SDK (winuser) で定義されている POINTER_TOUCH_INFO struct の orientation プロパティに対応しています。

#### put_TouchPressure 

ポインターイベントの TouchPressure を設定します。

> パブリック HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 TouchPressure)

これは、Windows SDK (winuser .h) で定義されている POINTER_TOUCH_INFO 構造体の圧力プロパティに対応しています。

