# 制御フロー

## if式

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

## loop, while

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

