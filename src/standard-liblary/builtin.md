# 組み込み関数

組み込み関数は、識別名の後に「`!`」を付けることで呼び出すことができる。

## `print!`

内部で`System.Console.Write()`を呼び出し、コンソールに標準出力を行う。  
第一引数に`string`型を指定した場合、コンパイル時にフォーマットを検査する。

| 引数                  | 説明                                  |
| :-------------------- | :------------------------------------ |
| `print!(i32)`         | `Write(Int32)`と同等の処理            |
| `print!(f32)`         | `Write(Single)`と同等の処理           |
| `print!(bool)`        | `Write(Boolean)`と同等の処理          |
| `print!(char)`        | `Write(Char)`と同等の処理             |
| `print!(string)`      | `Write(String)`と同等の処理           |
| `print!(string, ...)` | `Write(String, Object[])`と同等の処理 |

```rust
print!("hello");
print!(42);
print!("{}", 42);
```

## `println!`

内部で`System.Console.WriteLine()`を呼び出し、コンソールに標準出力を行う。  
第一引数に`string`型を指定した場合、コンパイル時にフォーマットを検査する。

| 引数                    | 説明                                      |
| :---------------------- | :---------------------------------------- |
| `println!()`            | `WriteLine()`と同等の処理                 |
| `println!(i32)`         | `WriteLine(Int32)`と同等の処理            |
| `println!(f32)`         | `WriteLine(Single)`と同等の処理           |
| `println!(bool)`        | `WriteLine(Boolean)`と同等の処理          |
| `println!(char)`        | `WriteLine(Char)`と同等の処理             |
| `println!(string)`      | `WriteLine(String)`と同等の処理           |
| `println!(string, ...)` | `WriteLine(String, Object[])`と同等の処理 |

```rust
println!();
println!("hello");
println!(42);
println!("{}", 42);
```

## `read_line!`

内部で`System.Console.ReadLine()`を呼び出し、コンソールからの入力を待つ。

| 引数                    | 説明                                 |
| :---------------------- | :----------------------------------- |
| `read_line!()`          | `ReadLine()`を呼び、`string`を返す。 |

```rust
let input: string = read_line!();
```

## `assert!`

実行時に、与えられた真偽値が`true`であることをアサートする。  
アサートに失敗した場合は`panic!`し、プログラムは終了する。

```rust
assert!(true);
assert!(1 == 1);
assert!(1 != 2);
```

## `assert_eq!`

実行時に、与えられた両辺が同値であることをアサートする。  
アサートに失敗した場合は`panic!`し、プログラムは終了する。

```rust
assert_eq!(true, true);
assert_eq!(1, 1);
assert_eq!("foo", "foo");
```

## `panic!`

内部で`System.Environment.Exit(Int32)`を呼び出し、現在のプログラムを終了する。

```rust
panic!();
panic!("panic with a message: {}", 42);
```
