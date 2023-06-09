# 型引数

型引数宣言を持つ項目の本体の中では、その型引数の名前は型になります:

```rust
fn to_vec<A: Clone>(xs: &[A]) -> Vec<A> {
    if xs.is_empty() {
        return vec![];
    }
    let first: A = xs[0].clone();
    let mut rest: Vec<A> = to_vec(&xs[1..]);
    rest.insert(0, first);
    rest
}
```

ここで `first` は、`to_vec` の型引数 `A` を参照して、型 `A` を持っています。さらに `rest` は、要素の型が `A` であるベクタの型 `Vec<A>` を持っています。
