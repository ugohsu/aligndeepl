# テキストをうまく整形して Deepl にかけるスクリプト

## 名前

aligndeepl

## 説明

aligndeepl は標準入力から英文のテキストを受け取り、各パラグラフに日本語訳を加えたテキストを標準出力に返します。訳出はパラグラフごとにおこないますが、ひとつのパラグラフの文字数が閾値以上である場合には、パラグラフを分割します。パラグラフは空行を区切り文字として認識されます。具体的には以下の例を確認してください。

Deepl Pro にログインして翻訳を実行する場合には、ホームディレクトリに `.aligndeepl` というファイルを作成し、以下のような json 形式の記述をおこなってください。

```{json}
{
    "id": "[your email adress]",
    "password": "[your password]"
}
```

## 例

以下のテキストを入力した場合、空行を区切り文字として 2 つのパラグラフが認識されます。パラグラフ内での改行は無視され、複数行の文章がひとつの文章として取り扱われます。

```
aligndeepl takes English text from the standard input
and returns the text with a Japanese translation for
each paragraph to the standard output. The translation
is done paragraph by paragraph, but if the number 
of characters in a paragraph exceeds a threshold, 
the paragraph is split. Paragraphs are recognized 
with blank lines as separators. See the following 
example for more details. 

If you enter the following text, two paragraphs will 
be recognized with a blank line as the separator. 
Line breaks within a paragraph will be ignored, 
and multiple lines of text will be treated as a 
single sentence. 
```

上記のテキストの翻訳結果は以下のようにまとめられます。

```
> aligndeepl takes English text from the standard input and returns the text with a Japanese translation for each paragraph to the standard output. The translation is done paragraph by paragraph, but if the number of characters in a paragraph exceeds a threshold, the paragraph is split. Paragraphs are recognized with blank lines as separators. See the following example for more details. 

aligndeepl は標準入力から英文のテキストを受け取り、各パラグラフに日本語訳を加えたテキストを標準出力に返します。訳出はパラグラフごとにおこないますが、ひとつのパラグラフの文字数が閾値以上である場合には、パラグラフを分割します。パラグラフは空行を区切り文字として認識されます。具体的には以下の例を確認してください。

- - -

> If you enter the following text, two paragraphs will be recognized with a blank line as the separator.  Line breaks within a paragraph will be ignored, and multiple lines of text will be treated as a single sentence. 

以下のテキストを入力した場合、空行を区切り文字として 2 つのパラグラフが認識されます。パラグラフ内での改行は無視され、複数行の文章がひとつの文章として取り扱われます。

- - -
```

## 変更履歴

- (2021.03.16) タイムアウトの設定を追加; 翻訳ごとにドライバを開きなおすように変更。
- (2021.03.16.1) Deepl Pro にログインする設定を追加; それにともない、ドライバを開きなおさないように変更
- (2022.05.11) セレクタを変更 (加えて、ループを抜けるルールも変更)。さらに、ログインは xpath を使用するように変更
