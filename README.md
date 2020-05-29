# Microsoft Edge ドキュメント

## Microsoft オープンソースコードの実施

このプロジェクトは、 [Microsoft Open Source Code の倫理](https://opensource.microsoft.com/codeofconduct/)規定を採用しています。
詳細については、「[よく寄せ](https://opensource.microsoft.com/codeofconduct/faq/)られる質問 (faq)」を参照するか、その他の質問やコメントで[opencode@microsoft.com](mailto:opencode@microsoft.com)を参照してください。

## 法的通知
Microsoft およびすべての投稿者は、[Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode) (クリエイティブ コモンズ ライセンス 4.0 インターナショナル パブリック ライセンス) に基づいて、このリポジトリにある Microsoft のドキュメントおよび他の内容に関するライセンスをユーザーに付与します ([LICENSE](LICENSE) ファイルをご覧ください)。また、[MIT ライセンス](https://opensource.org/licenses/MIT)に基づいて、リポジトリにあるすべてのコードに関するライセンスを付与します ([LICENSE-CODE](LICENSE-CODE) ファイルをご覧ください)。

ドキュメント内で参照されている Microsoft、Windows、Microsoft Azure、および他の Microsoft 製品やサービスは、米国 Microsoft Corporation の米国およびその他の国における商標または登録商標です。
このプロジェクトのライセンスは、すべての Microsoft の名称、ロゴ、または商標を使用する権利を許諾するものではありません。
Microsoft の一般的な商標のガイドラインについては、を参照 https://go.microsoft.com/fwlink/?LinkID=254653 してください。

プライバシーに関する情報は、にあります。https://privacy.microsoft.com

Microsoft およびすべての投稿者は、黙示、禁反言、またはその他によるかを問わず、他のすべての権利を (それらの権利がそれぞれの著作権、特許権、商標に基づくものであるかどうかに関係なく)、留保します。

## 寄稿

これは、でホストされている Microsoft Edge**ドキュメント**のリポジトリです [https://docs.microsoft.com/microsoft-edge/](https://docs.microsoft.com/microsoft-edge/) 。

新しいカバーを表示したい場合やフィードバックがある場合は、[**投稿**](/CONTRIBUTING.md)を検討してください。  既存のコンテンツを編集したり、新しいコンテンツを追加したり、または新しい[問題](https://github.com/MicrosoftDocs/edge-developer/issues)を作成したりすることができます。 お客様からの提案を確認し、共同作業を行ってドキュメントに組み込みます。

ページのデータを [`Status`](https://dev.windows.com/microsoft-edge/platform/status/) 次の場所で https://github.com/MicrosoftEdge/Status 見つけます。 この `Status` ページでは、最新の実装状態と、Microsoft Edge の web platform 機能の今後の計画について説明します。

### 規則

- ページを追加するときは、そのページを表示するために、 [toc.md](microsoft-edge/toc.md)でそのページのエントリを追加する必要があります。
- フォルダーには、その他のフォルダーまたは s を含めることができます。 `readme.md`
- フォルダー/ディレクトリ名はダッシュ区切り (例: `f12-tools` ) および小文字です。 Docs.microsoft.com サイトの Url で使用されます。 アンダースコアまたは文字の例/camelCase は使用しないでください。

### その他のテキスト要素

その他のテキスト要素には、次のようなスタイルがあります。

* 順序なしリスト
* 通常の箇条書きを設定する
   * 箇条書きを入れ子にすることもできます。
   * 箇条書きリストには複数のエントリを含める必要があります。
* 標準

1. 番号付きリスト。
2. 標準の ol ' 西洋スタイルの段落番号を使用します。
3. リストに実際の順序が設定されている場合にのみ使用します。

_________________________

水平ルールを使用できます。 低優先メール機能を使用することをお勧めします。
横方向ルールを見出しタグと組み合わせることはできません。既に使用されているビジュアル階層の線スタイル。

### コードの表示

インライン `code` マークダウン構文 (バックチック付き) を使うことができます。

または、次のようにコードのブロックを表示することもできます。

```css
body {
    background: #fff;
}
```

### 示し

| 操作     | ヘッダーを使用する | 表の場合    |
|-------------|-------------|-------------:|
| 左揃え| いない場合#  | 456          |
| テキスト値  | その他のテキスト   | $0.00        |

### 備考

メモを多用しないでください。 これは、"見落としてはなりません" 情報を強調するように設計されています。

現在、次の4つの異なるバージョンのメモがあります。
- 注
- 警告
- メモ
- 重要

それぞれ、次のように表示します。

![メモのパターン](./media/notes.png)

```
> [!WARNING]
> Hello. Yes. I am a warning note that has been automagically created. My text may wrap to more than one line when the Markdown is parsed, but I must include all my information within a single (sometimes very long line) in the Markdown itself.```

For multi-line blockquote notes, use a > in front of each line of the notes as seen in the example below.

```


### 画像

画像はフォルダーに保存 `media` し、相対パスで参照する必要があります。

`![Note patterns](media/notes.png)`
