## Kotlin の概要

参考
https://developer.android.com/courses/android-basics-compose/course?authuser=1&%3Bhl=ja&hl=ja

### 書き方

- 関数名はキャメルケース。
- 動詞または動詞句を使用。
- 関数の先頭行の末尾には、開き中かっこ{}が必要。
- 開き中かっこの前にはスペースが必要。
- 関数本体は、スペース 4 つ分インデントする。（タブは使わない）

### 文法

- if:単純な条件式に適しており、主に二択や条件が少ない場合に使われます。
- when:複数の条件やパターンマッチングに便利で、範囲や型、リテラルなどさまざまな条件に対応できます。
- null 値非許容型: nullを許さない！！！
- null 値許容型: ?を付けるとnullを許容する。

```
  var name: String? = "mochi"
  name = null // これはOK
```

- 安全呼び出し演算子(?).

```
  val length: Int? = name?.length // name が null の場合は length に null が入る
```

- 強制的に非null型として扱う演算子(!!)
- もし、変数が実際にnullであった場合、KotlinはNullPointerException（NPE）を発生させます。

```
  var name: String? = "mochi"
  val length: Int = name!!.length  // 強制的に非null型として扱う
```

- エルビス演算子（?:）nullの値が見つかった場合に代替の値を指定することができる。

```
  val name: String? = null
  val result: String = name ?: "Unknown"
  println(result) // "Unknown" が出力される
```

下のコードと同じ

```
val result = if (name != null) name else "Unknown"
```

- クラス名は PascalCase（各単語が大文字で始まり、単語間にスペースがない）
- クラスの定義とインスタンス化

```
// クラスの定義
class Car(val brand: String, val model: String)

fun main() {
    // インスタンス化
    val car1 = Car("Toyota", "Corolla")
    val car2 = Car("Honda", "Civic")

    // オブジェクトのプロパティにアクセスして出力
    println(car1.brand)  // "Toyota"
    println(car2.model)  // "Civic"
}
```

- ゲッター（get）やセッター（set）
- field：プロパティの値そのもの（バックフィールド）を指します。

```
fun main() {
    var speakerVolume = 2
        get() = field
        set(value) {
            field = value
        }

    // 値を取得する（ゲッターが呼ばれる）
    println(speakerVolume)  // 2

    // 値を設定する（セッターが呼ばれる）
    speakerVolume = 5
    println(speakerVolume)  // 5
}
```

- class の前にopen キーワードを追加すると拡張できる。
- override : Kotlinで親クラスのメソッドやプロパティを子クラスで再定義（上書き）するために使用される。

```
// 親クラス
open class Animal {
    open fun makeSound() {
        println("Animal is making a sound")
    }
}

// 子クラス
class Dog : Animal() {
    override fun makeSound() {
        println("Dog is barking")
    }
}

fun main() {
    val animal: Animal = Animal()
    val dog: Animal = Dog()

    animal.makeSound()  // Animal is making a sound
    dog.makeSound()     // Dog is barking
}
```

- IS-A 関係
  「犬は動物である」（Dog IS-A Animal）という関係では、  
  Dog クラスは Animal クラスから特性や振る舞いを継承します。
- HAS-A 関係
  「車はエンジンを持っている」（Car HAS-A Engine）という関係では、  
  Car クラスは Engine クラスのオブジェクトを含んでいることを示します。

- super キーワード
  親クラスのメソッドやプロパティを参照するために使用されます。

```
// 親クラス
open class Animal {
    open fun makeSound() {
        println("Animal makes a sound")
    }
}

// 子クラス
class Dog : Animal() {
    override fun makeSound() {
        super.makeSound()  // 親クラスのメソッドを呼び出す
        println("Dog barks")  // 子クラスの独自の処理
    }
}

fun main() {
    val dog = Dog()
    dog.makeSound()
}

```

- 可視性修飾子（Visibility Modifiers） は、Kotlinでクラス、メソッド、プロパティなどの  
   アクセスレベルを制御するために使用されるキーワード
  | 修飾子 | アクセス可能範囲 |
  |-------------|--------------------------------------------------------------|
  | `public` | すべての場所からアクセス可能。デフォルトの修飾子。 |
  | `private` | 同じクラス内でのみアクセス可能。 |
  | `protected` | 親クラスとそのサブクラスからアクセス可能。クラス外からは不可。 |
  | `internal` | 同じモジュール内でのみアクセス可能。 |

- クラスとメソッドの違い
  | 項目 | クラス | メソッド |
  |-----------|------------------------------------------|----------------------------------------------|
  | 定義 | オブジェクトを生成するための設計図 | クラスの内部にある、オブジェクトの動作を定義する関数 |
  | 役割 | データ（プロパティ）と機能（メソッド）をまとめる | オブジェクトの動作や機能を定義する |
  | 使い方 | インスタンス化してオブジェクトを作成する | クラスのインスタンスから呼び出され、動作する |
  | 構成要素 | プロパティ、メソッドなどを含む | プロパティを操作するために使われる |

- プロパティ委譲
  プロパティ委譲は、あるクラスのプロパティの処理（getterやsetterの動作）を別のクラスに任せる仕組みです。  
  これにより、プロパティの共通処理を一箇所にまとめて管理できます。  
  具体的には、byキーワードを使って、プロパティの処理を別のクラスに委譲します。
