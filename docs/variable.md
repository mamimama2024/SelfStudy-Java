# 変数

## Rubyの変数との違い
- [動的型付け言語](#dynamic)：Ruby
- [静的型付け言語](#static)：Java

## データ型
データ型とは、変数に格納するデータの種類のこと

Javaの基本データ型は８種類

データ型
- 基本データ型
- 参照データ型
※ここでは基本データ型を学習する

### データ型はコンピュータのリソースを効率よく使うための仕組み

- プログラムを実行すると、変数の値はコンピュータ内の「メモリ」と呼ばれるパーツに保存される。
- データ型があることで、このメモリを効率よく使用することができる。
- この際の数値は、人が普段使っている「10進数」ではなく「2進数」に変換してから扱われる。
- これから使用する変数にどのような範囲の値を格納するのか事前に決めておき、それに適した数の箱を確保することでメモリを効率的に使用できる。

## Javaの基本データ型の種類
| データ型 | bit数 | 値 |
| ---- | ---- | ---- |
| boolean | 1bit | true あるいは false |
| char | 16bit | 文字 |
| byte | 8bit | 整数（扱える範囲は -128～127） |
| short | 16bit | 整数（扱える範囲は-32,768～32,767） |
| int | 32bit | 整数（扱える範囲は-2,147,483,648～2,147,483,647） |
| long | 64bit | 整数（扱える範囲は-9223372036854775808～9223372036854775807） |
| float | 32bit | 小数（精度低） |
| double | 64bit | 小数（精度高） |  


使用頻度が高いのはint型とlong型
- 小さめの数値を扱うint型では「32bit」のメモリを使用する
- 大きめの数値を扱うlong型では「64bit」のメモリを使用する

Javaで変数を使用する際は、その変数をどのデータ型として扱うのかプログラムに伝えるため、あらかじめ「宣言」してから使用する

## <a id="dynamic" style="text-decoration:none;">動的型付け言語</a>
動的型付け言語は、プログラムの実行時に変数のデータ型を決定する方式で、Rubyはこちらに含まれる。  
「プログラムの実行時に変数のデータ型が決定される仕組み」を採用している言語。

```Ruby
a = 1
puts(a * 2)
# 2と出力される

a = "alphabet"
puts(a * 2)
# alphabetalphabetと出力される
```
どのような値が代入されたかによって、変数のデータ型が柔軟に変更され、そのデータ型に基づいて処理が行われている

## <a id="static" style="text-decoration:none;">静的型付け言語</a>

変数のデータ型を最初に決定したら変更できない仕組み。Javaはこちらに含まれる。

柔軟性はないが、処理が高速になったり、データ型の不整合によるエラーを実行前に検知できるなどのメリットがある。

Javaは静的型付け言語なので、変数を使用し始める際は「型の宣言」が必要になる。

### 変数の宣言と使い方
```Java
型名 変数名;
```
Javaでは**命令の終わりにセミコロンが必要**で書き忘れるとエラーになる

```Java
class Main {
  public static void main(string[] args) {
    //ここに処理を記述する
  }
}
```

```Java
// Main.java

class Main {
  public static void main(string[] args) {
    int radius;
    radius = 5;
    System.put.println(radius * radius * 3.14);
  }
}
```
- コードを記述できたら、エディタ上部の「Run」ボタンをクリックしてコードを実行する

### 型推論
Javaには「型推論」と呼ばれる仕組みがあり、宣言に関するコードを省略することができる

```Java
// 型推論を利用した変数の宣言方法

var 変数名 = 値

// 「var」を使って宣言を行い、初期値を代入
```
この記述を行うと、値の種類によってデータ型が推論され、推論されたデータ型で宣言が行われる

```Java
// 型推論を使ったコードに変更
// Main.java

class Main {
  public static void main(string[] args) {
    var radius = 5;
    System.put.println(radius * radius * 3.14);
  }
}
```

### データ型の種類の確認
```Java
// Main.java

class Main {
  public static void main(string[] args) {
    var radius = 5;
    System.put.println(radius * radius * 3.14);

    System.out.println(((Object)radius).getClass().getSimpleName());
  }
}
```

## まとめ
- Javaで変数を使用する際は宣言が必要
- ただし、宣言と同時に初期値を代入する場合は、省略することも可能