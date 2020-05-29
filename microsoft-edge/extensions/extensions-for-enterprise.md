---
ms.assetid: 8e2f75c4-fb7f-4892-a6c2-23bac081581a
description: Microsoft Edge Extensions のエンタープライズ固有の側面について説明し、それが UWP アプリとどのように類似しているかを確認します。
title: エンタープライズ向けの拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: 8f50c282fce11d2654f990bf135941e0616af3f3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569521"
---
# エンタープライズ向けの拡張機能  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

Microsoft Edge extensions のワークフローは、他のエンタープライズ UWP アプリと比較した場合に似ています。 以下では、Microsoft Edge extensions のエンタープライズ固有の側面について詳しく説明します。

## 前提条件
エンタープライズ向け Microsoft Edge 拡張機能を開発、パッケージ化、展開するには、次の項目を提案します。

+ Windows デベロッパーポータルアカウント。エンタープライズプライベートストアの内線番号に署名してリリースします。 詳細については[、「開発者アカウントを開く](/windows/uwp/publish/opening-a-developer-account)」を参照してください。
+ ビジネスまたは教育機関向けの Microsoft ストア。アプリケーションを企業に配布します。 詳細については、「一般[法人向け Microsoft ストアと教育機関向けドキュメント](/microsoft-store/)」を参照してください。
+ Microsoft Edge 拡張機能を実行する Windows 10 のバージョンを確認します。 既存の Windows 10 リリースの一覧については、「 [windows 10 リリース情報](https://www.microsoft.com/itpro/windows-10/release-information)」を参照してください。

> [!NOTE]
> サイドローディングは、Windows 開発者ポータルを使用して延長をリリースする代わりの方法と考えることができます。 詳細については、以下のサイドローディング拡張機能の動作を参照してください。

## Windows 情報保護
Microsoft Edge extensions は現在、Windows Information Protection (WIP) 設定を受け入れません。 企業がデータ保護を懸念している場合は、Microsoft Edge で拡張機能のサポートを有効にすることはできません。

従業員の内線番号を無効にするには、グループポリシーと Microsoft Intune の設定を構成します。 構成するポリシーの詳細については、「 [Microsoft Edge で利用可能なポリシー](https://technet.microsoft.com/itpro/microsoft-edge/available-policies)」を参照してください。

## パッケージ化の拡張機能
企業が、内線番号を従業員に配布するには、最初にパッケージ化する必要があります。 パッケージ化の拡張については、「[パッケージ](./guides/packaging.md)ガイド」を参照してください。

> [!TIP]
> 配布前に正常に動作するように、Windows 10 のすべてのバージョンで拡張機能をインストールして実行してください。

## 内線番号の配布
パッケージ化された拡張機能は、Microsoft Store、一般法人向け Microsoft Store、またはサイドローディングによって従業員に配布できます。

一般法人向け Microsoft Store で配布された拡張機能は、従業員に割り当てるか、すべての従業員がアクセスできるプライベートストアに追加することができます。 これを行うには、 [「基幹業務 (LOB) アプリを企業向けガイドに配布する](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises)」を参照してください。

サイドローディングの拡張機能を使用するには、サイドローディングについてデバイス (非管理または管理されているもの) のロックを解除する パッケージ化された拡張機能のサイドローディング方法の詳細については、「 [Windows 10 のサイドローディング LOB アプリ](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10)」を参照してください。

> [!IMPORTANT]
> 企業が社内で拡張機能の開発と配布を行っている場合、企業は、一般法人向け Microsoft Store (または教育機関) と Windows 開発者ポータルアカウントの両方を必要とします。

### サイドローディング Extensions の動作
Microsoft Store (または一般法人向け Microsoft Store) 経由で配布された拡張機能とは異なり、Microsoft Edge では、サイドローディング extensions の取り扱いは異なります。

最初の違いは、インストール後のサイドローディングの拡張機能の動作に影響します。 Microsoft Store の拡張機能とは異なり、サイドローディング extensions では "新しい拡張子を持っています" という通知はすぐには表示されず、ユーザーが手動で有効にする必要があります。

拡張機能を有効にするには、[**詳細 (...)** ] メニューを開き、[**拡張機能**] を選択すると、インストールされている拡張機能の一覧にサイドローディング拡張子が表示されます。 拡張機能をクリックして有効にします。

2つ目の違いは、ブラウザーでのサイドローディング extensions の表示方法に影響します。 たとえば、"新しい拡張機能" 通知とインストールされている拡張機能の一覧には、不明なソースからの拡張機能であることを示す警告が追加されます。

![サイドローディング警告1](./media/sideload-permissionflyout.PNG)

![サイドローディング警告2](./media/sideload-l1warning.PNG)

第3の違いは、ブラウザーの起動時にサイドローディングの拡張機能がどのように動作するかに影響します。 ドメイン参加または MDM 対応のデバイス上のサイドローディング拡張機能は、Microsoft Store の拡張機能と同様に動作します。 ただし、ドメインに参加していないデバイス、または MDM が有効になっているデバイス上のサイドローディング拡張機能は、ブラウザーの起動時にオフになり、ユーザーが明示的に操作を行う必要があります。

ブラウザーの起動時のまもなく (アイドル状態が10秒未満の場合)、次の通知がウィンドウの下部付近に表示されます。

![サイドローディング通知](./media/sideload-scareUI.PNG)

Microsoft Edge が起動されるたびに、拡張機能を使用するために、ユーザーは "このままオンにする" を選ぶ必要があります。
