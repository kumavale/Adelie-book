# 関数

`fn`から始まる文は関数宣言になります。  
Adelieでは`main()`から始まる関数がエントリーポイントになります。

```rust
fn main() {
    foo();
}
fn foo() {
    println!("foo!");
}
```

## 引数

仮引数名及び型名を指定することで、引数を受け取ることができます。

```rust
fn main() {
    area(30, 50);
}
fn area(width: i32, height: i32) {
    println!(width * height);
}
```

## 戻り値

戻り値を指定しない場合は、`void`が返されます。  
しかし、「`->`」の後に型名を指定することで、値を返すことができます。

```rust
fn main() {
    assert_eq!(area(30, 50), 150);
}
fn area(width: i32, height: i32) -> i32 {
    return width * height;
}
```

最後の式は`return`と`;`を省略することができます。

```rust
fn main() {
    assert_eq!(area(30, 50), 150);
}
fn area(width: i32, height: i32) -> i32 {
    width * height
}
```

