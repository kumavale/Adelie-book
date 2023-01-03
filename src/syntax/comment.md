# コメント

## 行コメント

`//`から行末までの文字は行コメントになります。

```rust
// this is a comment
println!(1 + 1);  // comment too
```

## ブロックコメント

`/*`から`*/`で囲まれた範囲の文字はブロックコメントになります。  
ネスト、複数行も可能です。

```rust
/* comment */
/*
    /* comment
       // comment
    */
*/
println!(/* 1 + */ 1);  // 1
```

