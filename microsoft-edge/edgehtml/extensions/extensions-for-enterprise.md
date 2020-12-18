---
ms.assetid: 8e2f75c4-fb7f-4892-a6c2-23bac081581a
description: Microsoft Edge 拡張機能のエンタープライズ固有の側面について説明し、UWP アプリとどのように似ているかについて説明します。
title: エンタープライズ向け拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7c23bc24e20b7b00b8779f209dcac8c795067fd5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235043"
---
# エンタープライズ向け拡張機能  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

Microsoft Edge 拡張機能は、他のエンタープライズ UWP アプリと比較した場合と同様のワークフローを持っています。 次の情報では、Microsoft Edge 拡張機能のエンタープライズ固有の側面について詳しい説明を示します。

## 前提条件
エンタープライズ向け Microsoft Edge 拡張機能を開発、パッケージ化、展開するには、次の項目をお勧めしています。

+ Windows デベロッパー ポータル アカウント。拡張情報に署名してエンタープライズ プライベート ストアにリリースします。 詳細 [については、「開発者アカウントを開く](/windows/uwp/publish/opening-a-developer-account) 」を参照してください。
+ ビジネスまたは教育向け Microsoft Store。企業にアプリケーションを配布します。 詳細については [、ビジネスおよび教育向け Microsoft Store のドキュメント](/microsoft-store/) を参照してください。
+ Microsoft Edge 拡張機能を実行する Windows 10 のバージョンを特定します。 既存 [の Windows 10 リリース](https://www.microsoft.com/itpro/windows-10/release-information) の一覧については、Windows 10 のリリース情報をご覧ください。

> [!NOTE]
> サイドローディングは、Windows デベロッパー ポータルを使用して拡張機能のリリースに署名する代わりに使用できます。 詳しくは、以下のサイドローディング拡張機能の動作をご覧ください。

## Windows 情報保護
現在、Microsoft Edge 拡張機能は Windows 情報保護 (WIP) の設定を受け入れることはできません。 企業がデータ保護を懸念している場合、Microsoft Edge に対して拡張機能のサポートを有効にしることはできません。

従業員の拡張機能を無効にするには、グループ ポリシーと Microsoft Intune の設定を構成します。 構成するポリシーについて詳しくは、「Microsoft Edge で使用可能な [ポリシー」をご覧ください](https://technet.microsoft.com/itpro/microsoft-edge/available-policies)。

## 拡張機能のパッケージ化
企業が拡張機能を従業員に配布するには、まずパッケージ化する必要があります。 パッケージ拡張機能の手順については、パッケージ ガイドをご [覧](./guides/packaging.md) ください。

> [!TIP]
> 配布する前に、すべてのバージョンの Windows 10 で拡張機能のインストールと実行をテストし、期待した動作を確認してください。

## 拡張機能の配布
拡張機能がパッケージ化された後は、Microsoft Store、ビジネス向け Microsoft Store、またはサイドロードを通じて従業員に配布できます。

ビジネス向け Microsoft Store を使って配布される拡張機能は、従業員に割り当てるか、すべての従業員がアクセスできるプライベート ストアに追加できます。 これは、「LOB [(Line-of-Business)](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) アプリを企業に配布する」ガイドに従って行います。

拡張機能をサイドロードするには、サイドローディング用にデバイス (非管理対象または管理) のロックを解除する必要があります。 パッケージ [化された拡張機能をサイドロードする方法について詳しくは、Windows 10](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) の LOB アプリのサイドロードに関するページをご覧ください。

> [!IMPORTANT]
> 企業が拡張機能を内部で開発および配布している場合、企業にはビジネス向け Microsoft Store (または Education) と Windows デベロッパー ポータル アカウントの両方が必要です。

### サイドロードされた拡張機能の動作
Microsoft Store (またはビジネス向け Microsoft Store) を通じて配布される拡張機能とは異なり、サイドローディングされた拡張機能は Microsoft Edge で異なる方法で扱います。

最初の違いは、インストール後のサイドロードされた拡張機能の動作に影響します。 Microsoft Store の拡張機能とは異なり、サイドローディングされた拡張機能では、すぐに "新しい拡張機能があります" という通知が表示されるのではなく、ユーザーが手動で有効にしている必要があります。

拡張機能を有効にする場合は、[その他 **] (...)** メニューを開き、[拡張機能 **]** を選択すると、インストールされている拡張機能の一覧にサイドロードされた拡張機能が表示されます。 拡張機能をクリックし、有効にしてください。

2 つ目の違いは、ブラウザーでのサイドローディングされた拡張機能の表示方法に影響します。 たとえば、"新しい拡張機能があります" という通知とインストールされている拡張機能の一覧の両方に、拡張機能が不明なソースからの拡張であることを示す追加の警告が含まれます。

![サイドロード警告 1](./media/sideload-permissionflyout.PNG)

![サイドロード警告 2](./media/sideload-l1warning.PNG)

3 番目と最後の違いは、ブラウザー起動時のサイドローディングされた拡張機能の動作に影響します。 ドメインに参加しているデバイスまたは MDM が有効になっているデバイスでサイドロードされた拡張機能は、Microsoft Store の拡張機能と同様に動作します。 ただし、ドメインに参加していないデバイスや MDM が有効になっているデバイスでサイドロードされた拡張機能は、ブラウザーの起動時にオフにされ、ユーザーが明示的なアクションを実行する必要があります。

ブラウザーの起動後 (非アクティブな状態が最大 10 秒後) の直後に、ウィンドウの下部近くに次の通知が表示されます。

![サイドロード通知](./media/sideload-scareUI.PNG)

Microsoft Edge が起動されるたび、ユーザーは拡張機能を使用するために [オンにする] を選択する必要があります。
