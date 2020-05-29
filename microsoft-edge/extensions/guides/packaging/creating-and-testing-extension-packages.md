---
ms.assetid: 5eefa3d8-8626-4486-bd90-1361400d6468
description: Microsoft Edge 拡張機能を手動でパッケージ化して、正しくパッケージされているかどうかをテストする方法について説明します。
title: 拡張パッケージの作成とテスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者、パッケージ
ms.custom: seodec18
ms.openlocfilehash: a76737d76c8f08c8e79992f0804fdbd34d4ed970
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569450"
---
# <span data-ttu-id="90790-104">Microsoft Edge 拡張機能 AppX パッケージの作成とテスト</span><span class="sxs-lookup"><span data-stu-id="90790-104">Creating and testing a Microsoft Edge extension AppX package</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="90790-105">Microsoft Edge extensions は、ユニバーサル Windows アプリのパッケージの場合と同様に、AppX としてパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="90790-105">Microsoft Edge extensions are packaged as AppX, similar to how Universal Windows Apps are packaged.</span></span> <span data-ttu-id="90790-106">Windows 10 記念日更新時には、appx に対して新しいスキーマが導入され、appx に Microsoft Edge extension をコンテンツとして含めることができます。</span><span class="sxs-lookup"><span data-stu-id="90790-106">As of Windows 10 Anniversary Update, a new schema has been introduced for AppX that allows an AppX to include a Microsoft Edge extension as its content.</span></span>

<span data-ttu-id="90790-107">Microsoft Edge extension AppXs の作成方法がわかっている場合は、「 [ManifoldJS を使って拡張子をパッケージ化する](./using-manifoldjs-to-package-extensions.md)」を参照してください。これを行うには、node.js ベースのツールを使用する方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="90790-107">If you already know how Microsoft Edge extension AppXs are created, you can skip to [Using ManifoldJS to package extension](./using-manifoldjs-to-package-extensions.md) to learn how to use a Node.js based tool to do all of this for you!</span></span>

> [!NOTE]
> <span data-ttu-id="90790-108">Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="90790-108">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="90790-109">お客様の内線番号の作成、パッケージ化、テストが完了したら、[延長申請フォーム](https://aka.ms/extension-request)でリクエストを送信してください。</span><span class="sxs-lookup"><span data-stu-id="90790-109">Once you've created, packaged and tested your extension, please submit a request on our [extension submission form](https://aka.ms/extension-request).</span></span>



## <span data-ttu-id="90790-110">申請フォルダーの準備</span><span class="sxs-lookup"><span data-stu-id="90790-110">Preparing the submission folder</span></span>

<span data-ttu-id="90790-111">申請のために拡張機能を準備するには、次の構造のフォルダーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90790-111">To prepare your extension for submission, you need to create a folder with the following structure:</span></span>

![フォルダー構造の画像。](./../../media/packaging_folder-structure.png)

<span data-ttu-id="90790-114">フォルダーのルートに、Package.appxmanifest ファイルを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="90790-114">At the root of the folder, you should include an AppXManifest.xml file.</span></span> <span data-ttu-id="90790-115">このファイルは、パッケージのコンテンツとレイアウトを指定するために使われます。</span><span class="sxs-lookup"><span data-stu-id="90790-115">This file is used to specify the contents and layout of the package.</span></span>

<span data-ttu-id="90790-116">また、Microsoft Store で使用される UI アセットを含む [アセット] フォルダーと、拡張機能のファイル (スクリプト、アイコンなど) が含まれる拡張フォルダーも用意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="90790-116">You should also have an Assets folder which contains the UI assets to be used in the Microsoft Store, and an Extension folder that contains your extension's files (scripts, icons, etc).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90790-117">パッケージ用の別のフォルダー構造を作成することはできますが、フォルダー構造は Package.appxmanifest 値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90790-117">You can create a different folder structure for your package, but the folder structure must match the AppXManifest values.</span></span>

### <span data-ttu-id="90790-118">Package.appxmanifest</span><span class="sxs-lookup"><span data-stu-id="90790-118">AppXManifest.xml</span></span>
<span data-ttu-id="90790-119">Package.appxmanifest ファイルは、Windows アプリを展開、表示、または更新するためにシステムが必要とする情報が含まれている XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="90790-119">The AppXManifest file is an XML document that contains info the system needs to deploy, display, or update a Windows app.</span></span> <span data-ttu-id="90790-120">このファイルには、パッケージ id、機能、およびビジュアル要素も含まれます。</span><span class="sxs-lookup"><span data-stu-id="90790-120">This file also includes package identity, capabilities, and visual elements.</span></span> <span data-ttu-id="90790-121">すべてのアプリパッケージには、1つの Package.appxmanifest ファイルが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="90790-121">Every app package must include one AppXManifest file.</span></span>

<span data-ttu-id="90790-122">開発者は、Package.appxmanifest ファイルに次のテンプレートを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="90790-122">Developers can use the following template for their AppXManifest.xml file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
  xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
  xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
  xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
  IgnorableNamespaces="uap3">

  <Identity
    Name="[REPLACE WITH PACKAGE/IDENTITYNAME]"
    Publisher="[REPLACE WITH PACKAGE/IDENTITY/PUBLISHER]"
    Version="[REPLACE WITH PACKAGE VERSION in the form X.X.X.0]"/>

  <Properties>
    <DisplayName>[REPLACE WITH RESERVED STORE NAME]</DisplayName>
    <PublisherDisplayName>[REPLACE WITH PACKAGE/PROPERTIES/PUBLISHERDISPLAYNAME]</PublisherDisplayName>
    <Logo>[REPLACE WITH RELATIVE PATH TO 50x50 ICON]</Logo>
  </Properties>

  <Dependencies>
    <TargetDeviceFamily Name="Windows.Desktop"
      MinVersion="10.0.14393.0"
      MaxVersionTested="10.0.14800.0" />
  </Dependencies>

  <Resources>
    <Resource Language="en-us"/>
  </Resources>

  <Applications>
    <Application Id="App">
      <uap:VisualElements
        AppListEntry="none"
        DisplayName="[REPLACE WITH RESERVED STORE NAME]"
        Square150x150Logo="[REPLACE WITH RELATIVE PATH TO 150x150 ICON]"
        Square44x44Logo="[REPLACE WITH RELATIVE PATH TO 44x44 ICON]"
        Description="This is the description of the extension"
        BackgroundColor="white">
      </uap:VisualElements>
    <Extensions>
    <uap3:Extension Category="windows.appExtension">
    <uap3:AppExtension Name="com.microsoft.edge.extension"
        Id="EdgeExtension"
        PublicFolder="Extension"
      DisplayName="[REPLACE WITH RESERVED STORE NAME]">
    </uap3:AppExtension>
    </uap3:Extension>
    </Extensions>
 </Application>
</Applications>
</Package>
```

#### <span data-ttu-id="90790-123">アプリ id テンプレートの値</span><span class="sxs-lookup"><span data-stu-id="90790-123">App identity template values</span></span>
<span data-ttu-id="90790-124">Windows デベロッパーセンターを通じて[拡張機能の名前を予約](./extensions-in-the-windows-dev-center.md#name-reservation)すると、package.appxmanifest で次の値を置き換えるために必要なパッケージ id 情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="90790-124">Once you've [reserved the name of your extension](./extensions-in-the-windows-dev-center.md#name-reservation) through the Windows Dev Center, you'll be able to find the necessary package identity information needed to replace the following values in AppXManifest.xml:</span></span>

- `Name`
- `Publisher`
- `DisplayName`
- `PublisherDisplayName`

<span data-ttu-id="90790-125">[アプリ id] ページにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="90790-125">You can access your App identity page using the following steps:</span></span>

1. <span data-ttu-id="90790-126">[Windows デベロッパーセンター](https://developer.microsoft.com/windows/)に移動します。</span><span class="sxs-lookup"><span data-stu-id="90790-126">Navigate to [Windows Dev Center](https://developer.microsoft.com/windows/).</span></span>
2. <span data-ttu-id="90790-127">開発者アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="90790-127">Sign in to your developer account.</span></span>
3. <span data-ttu-id="90790-128">ダッシュボードに移動します。</span><span class="sxs-lookup"><span data-stu-id="90790-128">Navigate to the Dashboard.</span></span>
4. <span data-ttu-id="90790-129">拡張機能の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="90790-129">Select the name of your extension.</span></span>

   ![内線番号リスト](./../../media/select-app.png)
5. <span data-ttu-id="90790-131">アプリを登録した後、[アプリの管理] セクションの下にある [アプリ id] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="90790-131">Navigate to the App identity page which is under the App management section (after you've registered your app).</span></span>

   ![アプリ id ページ](./../../media/app-identity.png)


<span data-ttu-id="90790-133">テンプレートに示されているように、[アプリ id] ページから値を Package.appxmanifest テンプレートに設定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="90790-133">You can now populate the AppXManifest template with values from the App identity page, as indicated in the template:</span></span>


```xml
<Identity
  Name="37369abigailc.MyExtension"
  Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
  Version="[REPLACE WITH PACKAGE VERSION in the form X.X.X.0]" />

<Properties>
  <DisplayName>My Extension</DisplayName>
  <PublisherDisplayName>abigailc</PublisherDisplayName>
  <Logo>[REPLACE WITH RELATIVE PATH TO 50x50 ICON]</Logo>
</Properties>
```

#### <span data-ttu-id="90790-134">JSON マニフェストのテンプレート値</span><span class="sxs-lookup"><span data-stu-id="90790-134">JSON manifest template values</span></span>
<span data-ttu-id="90790-135">Package.appxmanifest の一部の値は、JSON マニフェストで定義されている値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90790-135">Some values in the AppXManifest need to match those that are defined in the JSON manifest.</span></span> <span data-ttu-id="90790-136">拡張機能の JSON マニフェストに基づいて、package.appxmanifest 内の次の値を更新してください。</span><span class="sxs-lookup"><span data-stu-id="90790-136">Please update the following values in appxmanifest.xml based on your extension JSON manifest:</span></span>

- `Version` <span data-ttu-id="90790-137">-これは、拡張機能の JSON マニフェストに記載されているバージョンです。</span><span class="sxs-lookup"><span data-stu-id="90790-137">- This is the version listed in your extension's JSON manifest.</span></span> <span data-ttu-id="90790-138">文字列は、最後の整数が0になるように、x.x.x.x の形式と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90790-138">The string needs to match the X.X.X.X format where the last integer has to be 0.</span></span> <span data-ttu-id="90790-139">例:</span><span class="sxs-lookup"><span data-stu-id="90790-139">E.g.</span></span> <span data-ttu-id="90790-140">1.2.3.0</span><span class="sxs-lookup"><span data-stu-id="90790-140">1.2.3.0</span></span>

   ```xml
   <Identity
     Name="37369abigailc.MyExtension"
     Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
     Version="1.0.0.0" />
   ```

- `Description` <span data-ttu-id="90790-141">-これは、拡張機能の JSON マニフェストの説明のコピーです。</span><span class="sxs-lookup"><span data-stu-id="90790-141">- This is a copy of the description in your extension's JSON manifest.</span></span>

  ```xml
  <uap:VisualElements
    AppListEntry="none"
    DisplayName="My Extension"
    Square150x150Logo="[REPLACE WITH RELATIVE PATH TO 150x150 ICON]"
    Square44x44Logo="[REPLACE WITH RELATIVE PATH TO 44x44 ICON]"
    Description="This extension will allow you to quickly print by clicking the browser action."
    BackgroundColor="white">
  </uap:VisualElements>
  ```


### <span data-ttu-id="90790-142">資産フォルダー</span><span class="sxs-lookup"><span data-stu-id="90790-142">Assets folder</span></span>

<span data-ttu-id="90790-143">[アセット] フォルダーでは、3つの異なるアイコンサイズが必要です。</span><span class="sxs-lookup"><span data-stu-id="90790-143">Within the Assets folder you will need three different icon sizes.</span></span> <span data-ttu-id="90790-144">これらのアイコンは、Microsoft ストアと Windows UI で使用されます。</span><span class="sxs-lookup"><span data-stu-id="90790-144">These icons will be used in the Microsoft Store and the Windows UI.</span></span> <span data-ttu-id="90790-145">これらのアイコンの詳細については、[デザイン](./../design.md#icons-for-packaging)ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="90790-145">For more information on these icons, see the [Design](./../design.md#icons-for-packaging) guide.</span></span>

![3つのアイコンサイズがある [アセット] フォルダー](./../../media/assets-folder.png)

<span data-ttu-id="90790-147">必要な UI アセットを作成したら、Package.appxmanifest を更新して適切なファイルをポイントします。</span><span class="sxs-lookup"><span data-stu-id="90790-147">Once you've created the necessary UI assets, update AppXManifest.xml to point to the correct files:</span></span>

- <span data-ttu-id="90790-148">44 x 44</span><span class="sxs-lookup"><span data-stu-id="90790-148">44x44</span></span>

   ```xml
   Square44x44Logo="Assets/icon_44.png"
   ```

- <span data-ttu-id="90790-149">場合は</span><span class="sxs-lookup"><span data-stu-id="90790-149">50x50</span></span>

  ```xml
   <Logo>Assets/icon_50.png</Logo>
  ```

- <span data-ttu-id="90790-150">150 x 150</span><span class="sxs-lookup"><span data-stu-id="90790-150">150x150</span></span>

  ```xml
  Square150x150Logo="Assets/icon_150.png"
  ```


### <span data-ttu-id="90790-151">拡張機能フォルダー</span><span class="sxs-lookup"><span data-stu-id="90790-151">Extension folder</span></span>
<span data-ttu-id="90790-152">拡張機能ファイル (フォルダー構造の保持) を拡張機能フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="90790-152">Copy your extension files (keeping the folder structure) into the Extension folder.</span></span> <span data-ttu-id="90790-153">`manifest.json`[Extension folder] のルートにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90790-153">Make sure `manifest.json` is at the root your Extension folder.</span></span>

![すべての拡張ファイルが含まれる extension フォルダー](./../../media/extension-folder.png)


### <span data-ttu-id="90790-155">複数のロケールのサポート</span><span class="sxs-lookup"><span data-stu-id="90790-155">Supporting more than one locale</span></span>
<span data-ttu-id="90790-156">拡張機能が複数の言語をサポートしている場合は、必要なすべてのロケールを使用して AppX パッケージを構成し、Microsoft Store で適切にローカライズされたアイコンと説明を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="90790-156">If your extension supports more than one language, you may want to configure the AppX package with all the locales that you need so that the correct localized icon and description appear in the Microsoft Store.</span></span> <span data-ttu-id="90790-157">詳細については、「[ローカライズ拡張機能パッケージ](./localizing-extension-packages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90790-157">See [Localizing extension packages](./localizing-extension-packages.md) for more information.</span></span>

### <span data-ttu-id="90790-158">Appx の作成</span><span class="sxs-lookup"><span data-stu-id="90790-158">Creating an Appx</span></span>

<span data-ttu-id="90790-159">Appx を作成するには、makeappx のパスを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="90790-159">To create an Appx, you'll need to find the path for makeappx.</span></span> <span data-ttu-id="90790-160">これは通常、64ビットコンピューターを使用している場合に、次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="90790-160">This is usually located in the following location if you're on a 64-bit machine.</span></span>

`C:\Program Files (x86)\Windows Kits\10\bin\x64`

<span data-ttu-id="90790-161">拡張機能の AppX パッケージを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="90790-161">Execute the following command to create the AppX package for your extension:</span></span>

`[Path to makeappx] makeappx pack /h SHA256 /d [Path to package folder created in #1] /p [Path to the appx file that you want to create]`

<span data-ttu-id="90790-162">パスの入力が完了すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="90790-162">This should look something like this once you've filled in the paths:</span></span>

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe pack /h SHA256 /d "C:\Extension\My Extension" /p C:\Extension\MyExtension.appx`

### <span data-ttu-id="90790-163">Appx を展開する</span><span class="sxs-lookup"><span data-stu-id="90790-163">Unpacking an Appx</span></span>
<span data-ttu-id="90790-164">以前に生成された AppX を展開して、延長の次のイテレーションの出発点として使用したり、AppX が正しく作成されたことを確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="90790-164">You may want to unpack a previously generated AppX and use it as a starting point for the next iteration of your extension or to confirm that the AppX was created correctly.</span></span>

<span data-ttu-id="90790-165">これを行うには、次のコマンドを実行して、Microsoft Edge 拡張機能の AppX パッケージをアンパックします。</span><span class="sxs-lookup"><span data-stu-id="90790-165">To do this, you can execute the following command to unpack the AppX package of your Microsoft Edge extension:</span></span>

`[Path to makeappx] makeappx unpack /v /p [Path to appx file you want to unpack] /d [Path to the location where you want to create the package folder]`

<span data-ttu-id="90790-166">入力した内容は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="90790-166">This should look something like this when filled out:</span></span>

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe unpack /v /p "C:\Extension\MyExtension.appx" /d "C:\Extension\My Extension"`





## <span data-ttu-id="90790-167">AppX パッケージのテスト</span><span class="sxs-lookup"><span data-stu-id="90790-167">Testing an AppX package</span></span>

<span data-ttu-id="90790-168">Microsoft edge 拡張機能 AppX パッケージは、Microsoft Edge でサイドローディングしてテストできます。</span><span class="sxs-lookup"><span data-stu-id="90790-168">You can test your Microsoft Edge extension AppX package by sideloading it in Microsoft Edge.</span></span> <span data-ttu-id="90790-169">サイドローディング拡張 AppX パッケージは、ユニバーサル Windows アプリのサイドローディングと似ています。</span><span class="sxs-lookup"><span data-stu-id="90790-169">Sideloading the extension AppX package is similar to sideloading a Universal Windows app.</span></span> <span data-ttu-id="90790-170">パッケージに署名するための証明書を作成し、Windows にパッケージを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90790-170">You will need to create a certificate for signing the package, and then add the package to Windows.</span></span>

### <span data-ttu-id="90790-171">付き</span><span class="sxs-lookup"><span data-stu-id="90790-171">Signing</span></span>

<span data-ttu-id="90790-172">パッケージの署名と認定プロセスの詳細については、「[アプリパッケージ署名証明書を作成する方法](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx)と、 [SignTool を使ってアプリパッケージに署名する](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx)方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90790-172">See [How to create an app package signing certificate](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx) and [How to sign an app package using SignTool](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx) for info on the signing and certification process for packages.</span></span>

> [!NOTE]
> <span data-ttu-id="90790-173">Microsoft Store に提出する前に、拡張パッケージに署名する必要はありません。ストア取り込みプロセスは、お客に対応しています。</span><span class="sxs-lookup"><span data-stu-id="90790-173">You do not need to sign an extension package before submitting it to the Microsoft Store; the Store ingestion process will take care of that for you!</span></span>

<span data-ttu-id="90790-174">作成した証明書を使用してパッケージに署名した後も、ローカルコンピューターの信頼された証明書ストアにインストールするまでは、アプリパッケージの展開については、その証明書はローカルコンピューターによって信頼されません。</span><span class="sxs-lookup"><span data-stu-id="90790-174">After you've signed the package with the certificate that you created, the certificate is still not trusted by the local machine for deployment of app packages until you install it into the trusted certificates store of the local computer.</span></span> <span data-ttu-id="90790-175">この操作を行うには、Windows に付属している Certutil を使用できます。</span><span class="sxs-lookup"><span data-stu-id="90790-175">You can use Certutil.exe, which comes with Windows to do this.</span></span>

<span data-ttu-id="90790-176">WindowsCertutil で証明書をインストールするには、管理者として Cmd.exe を実行し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="90790-176">To install certificates with WindowsCertutil.exe, run Cmd.exe as administrator and run the following command:</span></span>

`Certutil -addStore TrustedPeople MyKey.cer`

<span data-ttu-id="90790-177">証明書が使用されなくなったら、管理者のコマンドプロンプトから次のコマンドを実行して、証明書を削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90790-177">Once the certificates are no longer in use, it is recommended that you remove them by running the following command from an administrator command prompt:</span></span>

`Certutil -delStore TrustedPeople certID`

<span data-ttu-id="90790-178">CertID は、証明書のシリアル番号です。</span><span class="sxs-lookup"><span data-stu-id="90790-178">The certID is the serial number of the certificate.</span></span> <span data-ttu-id="90790-179">証明書のシリアル番号を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="90790-179">To determine the certificate serial number, run the following command:</span></span>

`Certutil -store TrustedPeople`

### <span data-ttu-id="90790-180">展開</span><span class="sxs-lookup"><span data-stu-id="90790-180">Deploying</span></span>
<span data-ttu-id="90790-181">Microsoft Edge 拡張機能 AppX パッケージを展開するには、PowerShell で次のコマンドを実行します (管理者として)。</span><span class="sxs-lookup"><span data-stu-id="90790-181">You can deploy the Microsoft Edge Extension AppX package by running the following command in PowerShell (as administrator):</span></span>

`Add-AppxPackage [path to AppX]`

## <span data-ttu-id="90790-182">WebDriver を使った自動テスト</span><span class="sxs-lookup"><span data-stu-id="90790-182">Automated testing with WebDriver</span></span>

<span data-ttu-id="90790-183">お客様は、お客様が Microsoft edge を webdriver モードで起動したときに自動的に拡張テストを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="90790-183">As of the Anniversary Update, you can programmatically sideload your extension in Microsoft Edge with WebDriver, enabling automated testing of extensions when Microsoft Edge is launched in WebDriver mode.</span></span> <span data-ttu-id="90790-184">これにより、ページ上のコンテンツを操作するすべての拡張機能の自動テストを設定し、適切な動作が行われていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="90790-184">This will allow you to set up automated tests for any extension that manipulates content on a page and verify that the correct behavior is exhibited.</span></span>

<span data-ttu-id="90790-185">自動テストのために拡張機能をサイドローディングには、の下に拡張機能のフォルダーを保存する必要があり `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\` ます。</span><span class="sxs-lookup"><span data-stu-id="90790-185">To sideload your extension for automated testing, you'll need to store your extension's folder under `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\`.</span></span> <span data-ttu-id="90790-186">拡張機能がディレクトリ内にある場合は、 `LocalState` オブジェクトを作成して機能を追加する必要があり [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) `extensionPaths` ます。</span><span class="sxs-lookup"><span data-stu-id="90790-186">Once your extension is in the `LocalState` directory, you'll need to create an [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) object, and add the `extensionPaths` capability to it.</span></span> <span data-ttu-id="90790-187">この機能の値は、 `LocalState` Microsoft Edge が WebDriver モードで開始されたときに、サイドローディングを行う必要がある拡張子 (ディレクトリ内) への絶対パスの配列です。</span><span class="sxs-lookup"><span data-stu-id="90790-187">The value of this capability is an array of absolute paths to the extensions (in the `LocalState` directory) you wish to have side loaded when Microsoft Edge starts in WebDriver mode.</span></span>

<span data-ttu-id="90790-188">WebDriver を使った Microsoft Edge のサイドローディング拡張機能の完全なサンプルについては、次の[C# ファイル](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="90790-188">Check out the following [C# file](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs) for a complete sample on side loading extensions in Microsoft Edge with WebDriver.</span></span>
