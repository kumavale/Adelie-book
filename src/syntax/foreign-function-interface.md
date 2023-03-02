# 外部dll

`extern`を使用することで、外部のマネージドdllに定義されている、`class`,`struct`,`enum`,`function`を使用することができます。

```rust
#[link(name="System.Console.dll", publickeytoken="B0 3F 5F 7F 11 D5 0A 3A")]
extern {
    mod System {
        struct Console {}
        impl Console {
            fn WriteLine(_: string) {}
        }
    }
}

fn main() {
    System::Console::WriteLine("hello");
}
```

link属性にて`name`にdll名、`publickeytoken`にパブリックキートークンを指定します。  
.Netでいうところの「名前空間」は`mod`キーワードで再現します。  
dll内で定義されている全てを宣言する必要はありません。Adelie側で使用する構造体名やフィールド名のみの宣言で問題ありません。

