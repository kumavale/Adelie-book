# インストール

## Windows10

### 必要なもの

- [Visual Studio](https://visualstudio.microsoft.com/downloads/) (`ilasm.exe`を使用)
- [Cargo](https://www.rust-lang.org/tools/install)

### ビルド

```
$ git clone https://github.com/kumavale/Adelie
```

```
$ make build
```

## Linux

### 必要なもの

- [Mono](https://www.mono-project.com/download/stable/) (`ilasm`を使用)
- [Cargo](https://www.rust-lang.org/tools/install)

### ビルド

```
$ git clone https://github.com/kumavale/Adelie
```

```
$ make build
```

---

## 近いうちにこうしたい

現状だとMakefileを使用しないと標準ライブラリ（組み込み関数）がビルド使えない。

```
$ cargo install --git https://github.com/kumavale/Adelie
$ adelie [file]...
```
