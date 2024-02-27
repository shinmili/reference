# キーワード

Rust はキーワードを 3 つのカテゴリに分類します:

- [厳密な (strict)](#strict-keywords)
- [予約済み (reserved)](#reserved-keywords)
- [弱い (weak)](#weak-keywords)

## 厳密なキーワード

これらのキーワードは、それぞれの正しい文脈でのみ使用できます。厳密なキーワードは以下の名前としては使用できません:

- [項目]
- [変数]と関数仮引数
- フィールドと[バリアント]
- [型仮引数]
- ライフタイム仮引数または[ループラベル]
- [マクロ]または[属性]
- [マクロプレースホルダ]
- [クレート]

> **<sup>字句:</sup>**<sup></sup><br> KW_AS             : `as`<br> KW_BREAK          : `break`<br> KW_CONST          : `const`<br> KW_CONTINUE       : `continue`<br> KW_CRATE          : `crate`<br> KW_ELSE           : `else`<br> KW_ENUM           : `enum`<br> KW_EXTERN         : `extern`<br> KW_FALSE          : `false`<br> KW_FN             : `fn`<br> KW_FOR            : `for`<br> KW_IF             : `if`<br> KW_IMPL           : `impl`<br> KW_IN             : `in`<br> KW_LET            : `let`<br> KW_LOOP           : `loop`<br> KW_MATCH          : `match`<br> KW_MOD            : `mod`<br> KW_MOVE           : `move`<br> KW_MUT            : `mut`<br> KW_PUB            : `pub`<br> KW_REF            : `ref`<br> KW_RETURN         : `return`<br> KW_SELFVALUE      : `self`<br> KW_SELFTYPE       : `Self`<br> KW_STATIC         : `static`<br> KW_STRUCT         : `struct`<br> KW_SUPER          : `super`<br> KW_TRAIT          : `trait`<br> KW_TRUE           : `true`<br> KW_TYPE           : `type`<br> KW_UNSAFE         : `unsafe`<br> KW_USE            : `use`<br> KW_WHERE          : `where`<br> KW_WHILE          : `while`

以下のキーワードは 2018 エディションから追加されました。

> **<sup>字句 2018+</sup>**<br> KW_ASYNC          : `async`<br> KW_AWAIT          : `await`<br> KW_DYN            : `dyn`

## 予約済みキーワード

これらのキーワードはまだ使用されていませんが、将来の使用のために予約されています。予約済みキーワードは厳密なキーワードと同じ制約を持ちます。この分類が存在する理由は、現行のプログラムでこれらのキーワードの使用を禁止することによって、プログラムに将来の Rust のバージョンとの前方互換性を持たせるためです。

> **<sup>字句</sup>**<br> KW_ABSTRACT       : `abstract`<br> KW_BECOME         : `become`<br> KW_BOX            : `box`<br> KW_DO             : `do`<br> KW_FINAL          : `final`<br> KW_MACRO          : `macro`<br> KW_OVERRIDE       : `override`<br> KW_PRIV           : `priv`<br> KW_TYPEOF         : `typeof`<br> KW_UNSIZED        : `unsized`<br> KW_VIRTUAL        : `virtual`<br> KW_YIELD          : `yield`

以下のキーワードは 2018 エディションから予約済みです。

> **<sup>字句 2018+</sup>**<br> KW_TRY   : `try`

## 弱いキーワード

これらのキーワードは、特定の文脈でのみ特別な意味を持ちます。例えば、`union` という名前を持つ変数やメソッドを宣言することは可能です。

- `macro_rules` はカスタム[マクロ](macros.md)を作成するために使用されます。

- `union` は[共用体]を宣言するために使用され、共用体宣言で使用されたときだけキーワードとなります。

- `'static` は static ライフタイムのために使用され、[ジェネリックライフタイム仮引数]または[ループラベル]として使用することはできません。

    ```compile_fail
    // error[E0262]: invalid lifetime parameter name: `'static`
    fn invalid_lifetime_parameter<'static>(s: &'static str) -> &'static str { s }
    ```

- 2015 エディションでは、[`dyn`] は `::` で始まらないパスに続く型の位置で使用されるときだけキーワードとなります。

    2018 エディションから、`dyn` は厳密なキーワードに昇格しました。

> **<sup>字句</sup>**<br> KW_MACRO_RULES    : `macro_rules`<br> KW_UNION          : `union`<br> KW_STATICLIFETIME : `'static`
>
> **<sup>字句 2015</sup>**<br> KW_DYN            : `dyn`


[項目]: items.md
[変数]: variables.md
[型仮引数]: types/parameters.md
[ループラベル]: expressions/loop-expr.md#loop-labels
[マクロ]: macros.md
[属性]: attributes.md
[マクロプレースホルダ]: macros-by-example.md
[クレート]: crates-and-source-files.md
[共用体]: items/unions.md
[バリアント]: items/enumerations.md
[`dyn`]: types/trait-object.md
[ループラベル]: expressions/loop-expr.md#loop-labels
[ジェネリックライフタイム仮引数]: items/generics.md