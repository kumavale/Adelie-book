# データ型

Adelieでは全てのプリミティブ型を.Net型に置き換えることができます。

## 値型

### 整数型

| Adelie | 範囲                            | サイズ               | .NET型       |
| :----- | :------------------------------ | :------------------- | :----------- |
| i32    | -2,147,483,648 ～ 2,147,483,647 | 符号付き32ビット整数 | System.Int32 |

整数型は10進数での指定ができます。

```rust
let a: i32 = 42;
```

### 浮動小数点数型

| Adelie | おおよその範囲                  | 有効桁数 | サイズ   | .NET型        |
| :----- | :------------------------------ | :------- | :------- | :------------ |
| f32    | ±1.5 x 10−45 から ±3.4 x 1038 | ～6-9 桁 | 4 バイト | System.Single |

Adelieの浮動小数点数型はリテラルを記述する際に **接尾辞を付けることが必須** になります。

```rust
let a: f32 = 3.14f32;
```

### 論理値型

| Adelie | .NET型         |
| :----- | :------------- |
| bool   | System.Boolean |

`true`または`false`を指定することができます。

```rust
let a: bool = true;
let a: bool = false;
```

### 文字型

| Adelie | 範囲             | サイズ   | .NET型         |
| :----- | :--------------- | :------- | :------------- |
| char   | U+0000 ～ U+FFFF | 16ビット | System.Char    |

`char`型は内部でUnicode UTF-16文字を表します。

「`'`(シングルクォート)」で囲った一文字を指定できます。

```rust
let a: char = 'a';
let a: char = '☺';
```

### 構造体型

| Adelie | .NET型           |
| :----- | :--------------- |
| struct | System.ValueType |

```rust
// 構造体定義
struct Rectangle {
    width: i32,
    height: i32,
}
// メソッド定義
impl Rectangle {
    fn new(w: i32, h: i32) -> Rectangle {
        Rectangle {
            w,
            h,
        }
    }
    fn area(&self) -> i32 {
        self.width * self.height
    }
}
fn main() {
    // インスタンス化
    let rect1: Rectangle = Rectangle::new(30, 50);
    assert_eq!(rect1.area(), 150);
}
```

### 列挙型

| Adelie | .NET型      |
| :----- | :---------- |
| enum   | System.Enum |

内部では「0」からの連番を振られた名前付き定数になります。

```rust
enum Color {
    Red,
    Green,
    Blue,
}
fn main() {
    let blue: Color = Color::Blue;
    assert_eq!(blue as i32, 2);
}
```

## 参照型

### 文字列型

| Adelie | .NET型        |
| :----- | :------------ |
| string | System.String |

Adelieでは`string`型はUTF-16のシーケンスを表します。

```rust
let a: string = "foo";
```

### Box型

| Adelie | .NET型        |
| :----- | :------------ |
| Box    | System.Object |

```rust
let a: Box<i32> = Box::new(42);
assert_eq!(*a, 42);
```

### クラス型

| Adelie | .NET型        |
| :----- | :------------ |
| class  | System.Object |

後述する`extern`ブロック内でのみ宣言が可能です。

```rust
extern {
    class Foo {
        bar: i32
    }
}
```

