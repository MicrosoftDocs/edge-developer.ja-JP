---
description: Microsoft Edge DevTools を使用してページの HTTP Cookie を表示、編集、および削除する方法について説明します。
title: Microsoft Edge DevTools で Cookie を表示、編集、および削除する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c208ca628fe91ed5922bc36566be2b9bdd20ec0b
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439683"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="view-edit-and-delete-cookies-with-microsoft-edge-devtools"></a>Microsoft Edge DevTools で Cookie を表示、編集、および削除する  

[HTTP Cookie は][MDNHTTPCookies] 、主にユーザー セッションの管理、ユーザーの個人用設定の保存、ユーザーの動作の追跡に使用されます。  Cookie は、このページが Web 全体で見つかった **Cookie** 同意フォームを使用しているすべての迷惑な原因です。  次のガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使用して Web ページの HTTP Cookie を表示、編集、および削除する方法について説明します。  

## <a name="open-the-cookies-pane"></a>Cookie ウィンドウを開く  

1.  [DevTools を開きます][DevToolsOpen]。  
1.  [アプリケーション] **タブを** 選択して、[アプリケーション] パネル **を開** きます。  [ **マニフェスト] ウィンドウ** が開きます。  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest-empty.msft.png":::
       図 1: マニフェスト ウィンドウ  
    :::image-end:::  

1.  [記憶域 **] で** **[Cookie] を展開**し、原点を選択します。  
    
    :::image type="complex" source="../media/storage-application-storage-cookies-selected.msft.png" alt-text="[Cookie] ウィンドウ" lightbox="../media/storage-application-storage-cookies-selected.msft.png":::
       図 2: Cookie ウィンドウ  
    :::image-end:::  

## <a name="fields"></a>フィールド  

Cookie **テーブルには** 、次のフィールドが含まれています。  

*   **[名前]**。  Cookie の名前。  
*   **値**。  Cookie の値。  
*   **ドメイン**.  Cookie の受信を許可されているホスト。  [Cookie の [スコープ] に移動します][MDNHTTPCookiesScope]。  
*   **Path**.  ヘッダーを送信するために要求された URL に存在する必要 `Cookie` がある URL。  [Cookie の [スコープ] に移動します][MDNHTTPCookiesScope]。  
*   **有効期限 / 最大経過時間**。  Cookie の有効期限または最大有効期限。  [永続的な [Cookie] に移動します][MDNHTTPCookiesPermanent]。  セッション [Cookie の場合、][MDNHTTPCookiesSession] この値は常にです `Session` 。  
*   **サイズ**.  Cookie のサイズ (バイト単位)。  
*   **HTTP**.  true の場合、このフィールドは Cookie を HTTP でのみ使用し、JavaScript の変更は許可されません。  [HttpOnly Cookie に移動します][MDNHTTPCookiesSecure]。  
*   **セキュリティで保護されています**。  true の場合、このフィールドは、セキュリティで保護された HTTPS 接続経由でのみ Cookie をサーバーに送信する必要があります。  [セキュリティで保護 [された Cookie] に移動します][MDNHTTPCookiesSecure]。  
*   **SameSite**.  Cookie が `strict` 実験的 `lax` な Samesite 属性を使用している場合 [またはを含][MDNHTTPCookiesSamesite] む。  
*   **優先度**。  \(default\)、または Cookie が非推奨の Cookie Priority 属性を使用 `low` `medium` `high` [している場合を含][ChromiumIssue232693] む。

## <a name="filter-cookies"></a>フィルター Cookie  

[フィルター]**テキスト ボックス**を使用して、名前または値で**Cookie を****フィルター処理します**。  他のフィールドによるフィルター処理はサポートされていません。  

:::image type="complex" source="../media/storage-application-storage-cookies-filter-id.msft.png" alt-text="テキスト ID を含む Cookie をフィルター処理する" lightbox="../media/storage-application-storage-cookies-filter-id.msft.png":::
   図 3: テキストを含む Cookie をフィルター処理する `ID`  
:::image-end:::  

## <a name="edit-a-cookie"></a>Cookie を編集する  

[**名前]、[****値****]、[ドメイン****]、[パス**]、および **[有効期限] / [最大年齢**] フィールドは編集可能です。  
フィールドをダブルクリックして編集します。  

:::image type="complex" source="../media/storage-application-storage-cookies-rename.msft.png" alt-text="Cookie の名前を DEVTOOLS に設定する!" lightbox="../media/storage-application-storage-cookies-rename.msft.png":::
   図 4: Cookie の名前をに設定する `DEVTOOLS!`  
:::image-end:::  

## <a name="delete-cookies"></a>Cookie を削除する  

Cookie を選択し **、[Delete Selected** \( Delete Selected \) ] を選択して、特定の Cookie ![ ](../media/delete-icon.msft.png) を削除します。  

:::image type="complex" source="../media/storage-application-storage-cookies-delete-selected.msft.png" alt-text="特定の Cookie の削除" lightbox="../media/storage-application-storage-cookies-delete-selected.msft.png":::
   図 5: 特定の Cookie の削除  
:::image-end:::  

[ **すべてクリア]** \( ![ Clear All ](../media/clear-icon.msft.png) \) を選択して、すべての Cookie を削除します。  

:::image type="complex" source="../media/storage-application-storage-cookies-clear-all.msft.png" alt-text="すべての Cookie のクリア" lightbox="../media/storage-application-storage-cookies-clear-all.msft.png":::
   図 6: すべての Cookie をクリアする  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (クロム) 開発者ツール"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  

[ChromiumIssue232693]: https://bugs.chromium.org/p/chromium/issues/detail?id=232693 "クロムの問題 232693: Cookie の優先度フィールドの実装|クロム バグ"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP cookie |MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP Cookie - 永続的な cookie |MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP Cookie - SameSite cookie |MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookie - Cookie の範囲と|MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP Cookie - セキュリティで保護された HttpOnly |MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP Cookie - セッション cookie |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cookies) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
