# ホワイトスペース

ホワイトスペースは、[`Pattern_White_Space`] Unicode プロパティを持つ文字のみを含む、空でない任意の文字列です。[`Pattern_White_Space`](https://www.unicode.org/reports/tr31/) Unicode プロパティを持つ文字とは、具体的には:

- `U+0009` (水平タブ、`'\t'`)
- `U+000A` (改行、`'\n'`)
- `U+000B` (垂直タブ)
- `U+000C` (書式送り)
- `U+000D` (復帰、`'\r'`)
- `U+0020` (スペース、`' '`)
- `U+0085` (next line)
- `U+200E` (left-to-right mark)
- `U+200F` (right-to-left mark)
- `U+2028` (line separator)
- `U+2029` (paragraph separator)

Rust は「フリーフォーム」な言語です。ホワイトスペースのすべての形式は文法上で*トークン*を分離するためだけに使用され、意味論的な重要性はありません。

Rust プログラムは、その各ホワイトスペースの要素がスペース 1 文字などの別の合法なホワイトスペース要素に置き換えられたとしても、まったく同じ意味を持ちます。


[`Pattern_White_Space`]: https://www.unicode.org/reports/tr31/