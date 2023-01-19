# 変数

## 宣言と代入

変数は`let`を使用して宣言します。  
多くの場合、型名は省略可能です。

```rust
fn main() {
    let a: i32 = 42;
    let b = 42;
}
```

初期化は必須ではありませんが、未初期化の状態で変数を参照することはできません。

```rust
fn main() {
    let a: i32;
    let b: i32 = a;  // compile error
}
```

## 可変性

変数は標準で **不変** になります。

```rust
fn main() {
    let a: i32 = 42;
    a = 57;  // compile error
}
```

値を変更したい場合は、`mut`キーワードを使用して可変にすることができます。

```rust
fn main() {
    let mut a: i32 = 42;
    a = 57;  // OK!!
}
```

## シャドーイング

スコープ毎に現れた同名の変数は前の変数を覆い隠します。  
また、変数の型は同一である必要はありません。

```rust
fn main() {
    let a: i32 = 1;
    let a: i32 = a + 1;

    {
        let a: i32 = 5;
        assert_eq!(a, 5);
    }

    assert_eq!(a, 2);
}
```

