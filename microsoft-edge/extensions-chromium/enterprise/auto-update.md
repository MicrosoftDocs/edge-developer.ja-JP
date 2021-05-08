---
description: 拡張機能の自動更新について詳しくは、Microsoft Edge
title: 拡張機能を自動的に更新Microsoft Edge
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 74d7b61c8eca1155b545b7e81627a652bf336e66
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483073"
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
# <a name="automatically-update-extensions-in-microsoft-edge"></a>拡張機能を自動的に更新Microsoft Edge  

拡張機能を自動的に更新するように設定すると、拡張機能は自動的に更新するように設定されている場合Microsoft Edgeと次の利点を共有します。  

*   バグとセキュリティの修正プログラムを組み込む。  
*   新しい機能やパフォーマンスの強化を追加します。  
*   ユーザー インターフェイスを改善します。  

以前は、ストアベース以外の拡張機能がサポートされました。  また、ネイティブ バイナリと拡張機能を同時に更新しました。  

これで、Microsoft Edgeアドオン ストアが拡張機能をホストし、拡張機能を更新するには、拡張機能と同じメカニズムをMicrosoft Edge。  更新メカニズムは制御しない。  ネイティブ バイナリに依存する拡張機能を更新する場合は注意してください。  

> [!NOTE]
> この記事は、パートナー センター ダッシュボードを使用して発行する拡張機能 [には適用][MicrosoftPartnerDashboardMicrosoftedgePublicLoginRefDd] されません。  ダッシュボードを使用して、更新されたバージョンをユーザーとアドオン ストアMicrosoft Edgeリリースできます。  詳細については、「拡張機能を更新 [または削除する」に移動します][ExtensionsPublishUpdateExtension]。  

## <a name="overview"></a>概要  

数時間ごとに、インストールMicrosoft Edgeアプリに更新 URL が含されているかどうかを確認できます。  拡張機能の更新 URL を指定するには、マニフェスト `update_url` のフィールドを使用します。  マニフェスト `update_url` 内のフィールドは、更新チェックを完了する場所をポイントします。  それぞれについて `update_url` 、更新されたマニフェスト XML ファイルの要求を送信します。  更新マニフェスト XML ファイルにインストールされているバージョンより新しいバージョンが一覧表示されている場合は、Microsoft Edgeバージョンをダウンロードしてインストールします。  手動更新でも同じプロセスが機能します。新しいファイルには、現在インストールされているバージョンと同じプライベート キー `.crx` で署名する必要があります。  

> [!NOTE]
> ユーザーのプライバシーを維持するために、Microsoft Edge はマニフェストの自動更新要求を含むヘッダーを送信しません。また、これらの要求に対する応答のヘッダーは `Cookie` `Set-Cookie` 無視されます。  

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
| `appid` | 拡張 ID は、公開キーのハッシュに基づいて生成されます。  拡張機能の ID を見つけるには、拡張機能を開Microsoft Edgeに移動します `edge://extensions` 。 |  
| `codebase` | ファイルの `.crx` URL。 |  
| `version` | この属性値は、Microsoft Edgeファイルをダウンロードするかどうかを決定するために `.crx` 使用されます `codebase` 。  ファイルのファイルの値 `version` と `manifest.json` 一致する必要 `.crx` があります。 |  

更新マニフェスト XML ファイルには、複数の要素を含めて複数の拡張子に関する情報が含まれている場合があります。  

## <a name="testing"></a>テスト  

既定の更新チェックの頻度は数時間です。  強制的に更新するには、[拡張機能を今すぐ更新する] ボタン `edge://extensions` **に移動して選択** します。  

## <a name="advanced-usage-request-parameters"></a>高度な使用法: 要求パラメーター  

基本的なメカニズムは簡単です。  拡張機能を自動的に更新するには、次の操作を実行します。  

1.  アップロードなどの静的 XML ファイルを Web サーバー上に保存します。  
1.  拡張機能の新しいバージョンをリリースする場合は、XML ファイルを更新します。  
    
更新マニフェスト要求に追加された一部のパラメーターが拡張機能とを示しているという事実を利用 `ID` します `version` 。  静的 XML ファイルの `update URL` 代わりに、すべての拡張機能で同じ機能を使用できます。  すべての拡張機能で同じ機能を使用するには、動的サーバー側コードを実行する URL をポイントしてパラメーター `update URL` をテストします。  

次の例は、更新 URL の要求パラメーターの形式を示しています。  

```url
?x={extension_data}
```  

この例では `{extension_data}` 、次の形式を使用する URL エンコード文字列を指定します。  

```url
id={id}&v={version}
```  

たとえば、次の 2 つの拡張機能は両方とも同じ更新 URL を指しています `http://contoso.com/extension_updates.php` 。  

*   拡張機能 1  
    *   ID: `aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa`  
    *   更新 URL: `http://contoso.com/extension_updates.php`
    *   バージョン: `1.1`  
*   拡張機能 2  
    *   ID: `bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb`  
    *   更新 URL: `http://contoso.com/extension_updates.php`
    *   バージョン: `0.4`  


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

Microsoft Edge 拡張機能システムの新しい API リリースとして、新しい拡張機能または新しいバージョンでのみ動作する拡張機能またはアプリの更新Microsoft Edgeがあります。  ユーザー Microsoft Edge自動的に更新される場合、ほとんどのユーザーが新しいリリースに更新されるまで数日かかる場合があります。  特定の更新プログラムが特定のバージョンMicrosoft Edgeバージョンよりも新しいバージョンにのみ適用するようにするには、更新マニフェストに属性 `prodversionmin` を追加します。  次のコード スニペットでは、属性の値は、ユーザーが新しいアプリを実行している場合にのみ、アプリが自動的にバージョン `prodversionmin` `3.0.193.0` `2.0` Microsoft Edge `3.0.193.0` 指定します。  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' prodversionmin='3.0.193.0' />
  </app>
</gupdate>
```  

<!-- links -->  

[ExtensionsPublishUpdateExtension]: ../publish/update-extension.md "拡張機能の更新または削除|Microsoft Docs"  

[MicrosoftPartnerDashboardMicrosoftedgePublicLoginRefDd]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナー センター"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページは次 [のページに表示されます](https://developer.chrome.com/docs/apps/autoupdate)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
