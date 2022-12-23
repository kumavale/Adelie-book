# 制御フロー

## if式

Adelieの`if`は **式** であるため、値を返します。  
`if`と`else`の型が一致している場合のみコンパイルが通り、変数に束縛することができます。

```rust
fn main() {
    let num: i32 = 42;

    if num % 15 == 0 {
        println!("FizzBuzz");
    } else if num % 3 == 0 {
        println!("Fizz");
    } else if num % 5 == 0 {
        println!("Buzz");
    } else {
        println!(num);
    }
}
```

```rust
fn main() {
    let winner: bool = true;
    let score: i32 = if winner { 33 } else { 4 };

    assert_eq!(score, 33);
}
```

## ループ

ループには`loop`または`while`を使用できます。  

> `for`文の対応はしばしお待ちを！

```rust
fn main() {
    loop {
        break;
    }

    let mut i: i32 = 3;
    while i > 0 {
        i -= 1;
    }
}
```

