---
description: Microsoft Edge の拡張機能に対する自動更新について説明します。
title: Microsoft Edge の拡張機能を自動更新する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 0f3f140cd3a2a079cd09f4d61e46a420342e15e0
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461543"
---
<!-- Copyright A. W. Fuchs

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="auto-update-extensions-in-microsoft-edge"></a>Microsoft Edge の拡張機能を自動更新する  

拡張機能を自動的に更新すると、Microsoft Edge を自動的に更新するのと同じ利点がいくつか共有されます。   

*   バグとセキュリティの修正プログラムを組み込む。  
*   新しい機能やパフォーマンスの強化を追加します。  
*   ユーザー インターフェイスを改善します。  

以前は、ストアベース以外の拡張機能がサポートされている場合、ネイティブ バイナリと拡張機能を同時に更新する可能性がありました。  これで、これらの拡張機能は Microsoft Edge アドオン ストアでホストされ、Microsoft Edge が使用するのと同じメカニズムを使用して更新が行われた。これは制御できない。  ネイティブ バイナリに依存する拡張機能を更新する場合は注意が必要です。  

> [!NOTE]
> このトピックは、パートナー センター ダッシュボードを使用して発行された拡張機能 [には適用][MicrosoftPartnerCenter] されません。  ダッシュボードを使用して、更新されたバージョンをユーザーと Microsoft Edge アドオン ストアにリリースできます。

## <a name="overview"></a>概要  

数時間ごとに、インストールされている各拡張機能またはアプリに更新 URL が含されているかどうかを Microsoft Edge がチェックします。  拡張機能では、マニフェストのフィールドを使用して更新 URL を指定できます。これは、更新チェックを実行する場所 `update_url` を示します。  それぞれについて `update_url` 、更新されたマニフェスト XML ファイルの要求を送信します。  更新マニフェスト XML ファイルにインストールされているバージョンよりも新しいバージョンが一覧表示されている場合、Microsoft Edge は新しいバージョンをダウンロードしてインストールします。  手動更新でも同じプロセスが機能します。新しいファイルには、現在インストールされているバージョンと同じプライベート キー `.crx` で署名する必要があります。  

> [!NOTE]
> ユーザーのプライバシーを維持するために、Microsoft Edge はマニフェスト要求を自動更新するヘッダーを送信しません。また、それらの要求に対する応答のヘッダー `Cookie` `Set-Cookie` は無視されます。  

## <a name="update-url"></a>URL の更新  

独自の拡張機能またはアプリをホストする場合は、フィールドを `update_url` ファイルに追加する必要 `manifest.json` があります。  の例については、次のコード スニペットを確認 `update_url` してください。  

```json
{
  "name": "My extension",
  ... 
  "update_url": "http://contoso.com/mytestextension/updates.xml",
  ... 
}
```  

## <a name="updated-manifest"></a>更新されたマニフェスト  

サーバーによって返される更新されたマニフェストは、XML ドキュメントである必要があります。  更新されたマニフェスト XML ファイルの例については、次のコード スニペットを確認してください。  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.microsoft.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' />
  </app>
</gupdate>
```  

次の表では、更新されたマニフェスト XML ファイルの属性について説明します。  

| 属性 | 詳細 | 
|:--- |:--- |  
| `appid` | 拡張 ID は、公開キーのハッシュに基づいて生成されます。  拡張機能の ID を見つけるには、Microsoft Edge を開き、 に移動します `edge://extensions` 。 |  
| `codebase` | ファイルの `.crx` URL。 |  
| `version` | この属性値は、Microsoft Edge によって指定されたファイルをダウンロードするかどうかを `.crx` 決定するために使用されます `codebase` 。  ファイルのファイルの値 `version` と `manifest.json` 一致する必要 `.crx` があります。 |  

更新マニフェスト XML ファイルには、複数の要素を含めて複数の拡張子に関する情報が含まれている場合があります。  

## <a name="testing"></a>テスト  

既定の更新チェックの頻度は数時間です。  強制的に更新するには、[拡張機能を今すぐ更新する] ボタン `edge://extensions` **に移動して選択** します。  

## <a name="advanced-usage-request-parameters"></a>高度な使用法: 要求パラメーター  

基本的な自動更新メカニズムは、静的 XML ファイルを Apache などの任意の Web サーバーにドロップし、拡張機能の新しいバージョンをリリースする場合と同じ方法で XML ファイルを更新するのと同じほど簡単です。  

拡張 ID とバージョンを示す更新マニフェスト要求にパラメーターが追加されるという事実を利用できます。 静的 XML ファイルの代わりに、すべての拡張機能に同じ更新 URL を使用できます。  すべての拡張機能に同じ更新 URL を使用するには、動的サーバー側コードを実行する URL をポイントして、これらのパラメーターをテストします。  

次の例は、更新 URL の要求パラメーターの形式を示しています `?x={extension_data}` 。

この例では `{extension_data}` 、次の形式を使用する URL エンコードされた文字列です `id={id}&v={version}` 。

たとえば、次の 2 つの拡張機能は両方とも同じ更新 URL を指しています `http://contoso.com/extension_updates.php` 。  

*  内線番号 1 - ID: "aaaaaaaaaa" バージョン: "1.1"
*  拡張 2 - ID: "bbbbbbbb" バージョン: "0.4"


各拡張機能を更新する要求を次に示します。  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1
```  

```https
http://contoso.com/extension_updates.php?x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

また、一意の更新 URL ごとに 1 つの要求に複数の拡張機能を一覧表示することもできます。  次の使用例は、前の要求を 1 つの要求にマージします。  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1&x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

1 つの要求を送信し、同じ更新 URL を使用するインストール済み拡張機能の数が長すぎる場合、更新プログラムのチェックは、より多くの要求を `GET` 発行します。  要求 `GET` URL が約 2000 文字の場合は長すぎます。  

> [!NOTE]
> 将来、1 つの要求で `POST` 複数の要求が `GET` 置き換わる可能性があります。  要求 `POST` には、本文に要求パラメーターが含 `POST` まれている場合があります。  

## <a name="advanced-usage-minimum-browser-version"></a>高度な使用法: 最小ブラウザー バージョン  

Microsoft Edge 拡張機能システムの新しい API リリースとして、新しい Microsoft Edge バージョンでのみ動作する拡張機能またはアプリの更新バージョンをリリースできます。  Microsoft Edge が自動更新される場合、ほとんどのユーザーが新しいリリースに更新されるまで数日かかる場合があります。  特定の更新プログラムが特定のバージョンより最新または新しい Microsoft Edge バージョンにのみ適用される場合は、更新マニフェストに属性 `prodversionmin` を追加します。  次のコード スニペットでは、属性の値は、ユーザーが Microsoft Edge 以降を実行している場合にのみ、アプリがバージョンに `prodversionmin` `3.0.193.0` 自動更新するように `2.0` `3.0.193.0` 指定します。  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' prodversionmin='3.0.193.0' />
  </app>
</gupdate>
```  

<!-- links -->  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナー センター"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページは次 [のページに表示されます](https://developer.chrome.com/docs/apps/autoupdate/)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
