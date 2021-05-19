# <a name="microsoft-edge-documentation"></a>Microsoft Edge ドキュメント  

## <a name="microsoft-open-source-code-of-conduct"></a>Microsoft Open Source Code of Conduct  

Microsoft Open Source Code of Conduct の詳細については、「Microsoft Open Source Code [of Conduct」を参照してください](CODE_OF_CONDUCT.md)。  

## <a name="legal-notices"></a>法的通知  

Microsoft および任意の投稿者は、クリエイティブ コモンズ アトリビューション[4.0](https://creativecommons.org/licenses/by/4.0/legalcode)インターナショナル パブリック ライセンスの下で、このリポジトリ内の Microsoft ドキュメントおよび他のコンテンツにライセンスを付与し[、LICENSE](./LICENSE)ファイルに移動し、MIT ライセンスの下のリポジトリ内の任意のコードにライセンスを付与し[、LICENSE-CODE](./LICENSE-CODE)ファイルに移動します。 [](https://opensource.org/licenses/MIT)  

ドキュメント内で参照されている Microsoft、Windows、Microsoft Azure、および他の Microsoft 製品やサービスは、米国 Microsoft Corporation の米国およびその他の国における商標または登録商標です。  
このプロジェクトのライセンスは、すべての Microsoft の名称、ロゴ、または商標を使用する権利を許諾するものではありません。  
Microsoft の一般的な商標ガイドラインは、 に記載されています [https://go.microsoft.com/fwlink/?LinkID=254653](https://go.microsoft.com/fwlink/?LinkID=254653) 。  

プライバシーに関する情報は、 で確認できます [https://privacy.microsoft.com](https://privacy.microsoft.com) 。  

Microsoft およびすべての投稿者は、黙示、禁反言、またはその他によるかを問わず、他のすべての権利を (それらの権利がそれぞれの著作権、特許権、商標に基づくものであるかどうかに関係なく)、留保します。  

## <a name="contributing"></a>寄稿  

これは、ホストされているドキュメントMicrosoft Edge**リポジトリ**です [https://docs.microsoft.com/microsoft-edge](https://docs.microsoft.com/microsoft-edge/index) 。  

新しいカバレッジを含めるか、フィードバックを得る場合は、貢献を [検討してください](./CONTRIBUTING.md)。  既存のコンテンツを編集したり、新しいコンテンツを追加したり、新しい問題を [作成したりすることができます](https://github.com/MicrosoftDocs/edge-developer/issues)。  このMicrosoft Edgeチームは、提案を確認し、提案をドキュメントに組み込むのに役立っています。  

[状態] Web ページの [データを次](https://developer.microsoft.com/microsoft-edge/status) の場所で検索します  [https://github.com/MicrosoftEdge/Status](https://github.com/MicrosoftEdge/Status) 。  Web `Status` ページには、Web プラットフォーム機能の最新の実装状態と今後の計画Microsoft Edge。

### <a name="conventions"></a>規則  

*   Web ページを追加する場合は、Web ページにエントリを追加 toc.md [追加する](./microsoft-edge/toc.yml) 必要があります。
*   ディレクトリには、より多くのディレクトリまたは複数のディレクトリが含 `readme.md` まれている場合があります。
*   フォルダー/ディレクトリ名は、ダッシュ区切り \(\ `f12-tools` など) と小文字です。  ディレクトリは、サイトの URL で使用 `docs.microsoft.com` されます。  アンダースコア、PascalCase、camelCase は使用しないようにします。  

### <a name="other-text-elements"></a>その他のテキスト要素  

次の他のテキスト要素では、スタイルを使用できます。  

*   順序なしリスト  
*   通常の箇条書きがある  
    *   箇条書きを入れ子にできます。  
    *   箇条書きリストには、複数のエントリが必要です。  
*   標準の配置 
    
1.  順序付きリスト。  
1.  通常の洋式の番号を使用します。  
1.  リストが本当に注文を持つ場合にのみ使用する必要があります。  
    
---  

水平方向のルールを使用できます。  水平ルールを使用して、煩雑な問題を軽減します。  
見出しタグで水平方向のルールを使用しないようにします。一部の見出しでは、視覚的階層に線のスタイルが既に使用されています。  

### <a name="displaying-code"></a>コードの表示  

インライン マークダウン構文 `code` \(backticks\) を使用できます。  

または、コードのブロックを表示する場合があります。  次のコード スニペットは css の例です。  

```css
body {
    background: #fff;
}
```  

### <a name="tables"></a>テーブル  

| お客様は、 | ヘッダーを使用する | テーブル上 |  
|:--- |:--- |:--- |  
| 左揃え | ない限り、# | 456 |  
| テキスト値 | その他のテキスト | $0.00 |  

### <a name="notes"></a>注  

メモは注意して使用してください。  ブロックは、"見逃すな" 情報を強調表示するように設計されています。  

現在、4 つの異なるバージョンのノートのスタイルが設定されています。  

*   注  
*   警告  
*   ヒント  
*   重要  
    
それぞれ、メモは次のコード スニペットのようになります。  

```md
> [!NOTE]
> This is a NOTE  
```  

```md
> [!WARNING]
> This is a WARNING  
```  

```md
> [!TIP]
> This is a TIP  
```  

```md
> [!IMPORTANT]
> This is IMPORTANT  
```  

![ノート パターン](./media/notes.png)

複数行のブロッククォート ノートの場合は、次の例に示すノートの各行の前に大きい `>` \( \) 文字を使用します。  

```md
> This is a line in a blockquote.  
> My text may wrap to more than one line when the markdown is parsed, but I must include all my information within a single \(sometimes very long line\) in the markdown.  
> This is another line in a blockquote.  
```  

### <a name="images"></a>画像  

イメージはディレクトリに格納し、イメージ スクリプトを使用 `media` して相対パスで参照する必要があります。  

<!--  `![Note patterns](media/notes.png)`  -->  

```md
:::image type="complex" source="./media/notes.png" alt-text="Note patterns" lightbox="./media/notes.png":::
   Note patterns  
:::image-end:::  
```  
