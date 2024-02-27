# 推論される型

> **<sup>構文</sup>**<br> *InferredType* : `_`

推論される型は、利用可能な周囲の情報に基づいてコンパイラが型を推論することができるなら、そうするように要求します。項目のシグネチャでは使用できません。これはジェネリック引数でよく使用されます:

```rust
let x: Vec<_> = (0..10).collect();
```

<!--
  What else should be said here?
  The only documentation I am aware of is https://rustc-dev-guide.rust-lang.org/type-inference.html
  There should be a broader discussion of type inference somewhere.
-->
