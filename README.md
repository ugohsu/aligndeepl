# テキストをうまく整形して Deepl にかけるスクリプト

## 名前

aligndeepl

## 説明

aligndeepl は標準入力から英文のテキストを受け取り、各パラグラフに日本語訳を加えたテキストを標準出力に返します。訳出はパラグラフごとにおこないますが、ひとつのパラグラフの文字数が閾値以上である場合には、パラグラフを分割します。パラグラフは空行を区切り文字として認識されます。具体的には以下の例を確認してください。

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

aligndeepl takes English text from the standard input
and returns the text with a Japanese translation for
each paragraph to the standard output. The translation
is done paragraph by paragraph, but if the number 
of characters in a paragraph exceeds a threshold, 
the paragraph is split. Paragraphs are recognized 
with blank lines as separators. See the following 
example for more details. 
```

上記のテキストの翻訳結果は以下のようにまとめられます。

```
> aligndeepl takes English text from the standard input and returns the text with a Japanese translation for each paragraph to the standard output. The translation is done paragraph by paragraph, but if the number of characters in a paragraph exceeds a threshold, the paragraph is split. Paragraphs are recognized with blank lines as separators. See the following example for more details. 

aligndeepl は標準入力から英文のテキストを受け取り、各パラグラフに日本語訳を加えたテキストを標準出力に返します。訳出はパラグラフごとにおこないますが、ひとつのパラグラフの文字数が閾値以上である場合には、パラグラフを分割します。パラグラフは空行を区切り文字として認識されます。具体的には以下の例を確認してください。

- - -

> aligndeepl takes English text from the standard input and returns the text with a Japanese translation for each paragraph to the standard output. The translation is done paragraph by paragraph, but if the number of characters in a paragraph exceeds a threshold, the paragraph is split. Paragraphs are recognized with blank lines as separators. See the following example for more details. 

aligndeepl は標準入力から英文のテキストを受け取り、各パラグラフに日本語訳を加えたテキストを標準出力に返します。訳出はパラグラフごとにおこないますが、ひとつのパラグラフの文字数が閾値以上である場合には、パラグラフを分割します。パラグラフは空行を区切り文字として認識されます。具体的には以下の例を確認してください。

- - -
```
