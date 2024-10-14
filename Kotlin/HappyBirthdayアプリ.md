## 参考

https://developer.android.com/codelabs/basic-android-kotlin-compose-text-composables?hl=ja&continue=https%3A%2F%2Fdeveloper.android.com%2Fcourses%2Fpathways%2Fandroid-basics-compose-unit-1-pathway-3%3Fhl%3Dja%23codelab-https%3A%2F%2Fdeveloper.android.com%2Fcodelabs%2Fbasic-android-kotlin-compose-text-composables#0

## メモ

- 後置ラムダ構文
  関数の最後の引数がラムダ式の場合に、関数呼び出しの括弧の外にラムダ式を記述できる構文です。

例えば、Scaffold という関数にラムダを渡すとき、通常は次のように書きます：

```
Scaffold(content = {
    // ここにラムダ式の処理を書く
})
```

後置ラムダ構文
Kotlinでは、最後の引数がラムダ式の場合、括弧の外にラムダを記述できます。この場合、次のように書けます：

```
Scaffold {
// ここにラムダ式の処理を書く
}
```

- 赤文字になっている部分にマウスオーバーすると○○のimportと出てくるのでクリック。importされる。
- 修飾子パラメータを渡す必要がある：  
  ColumnのようなレイアウトコンポーザブルにModifierを使って見た目や配置、サイズなどを調整するために  
  パラメータを渡すことを指します。

- 画像を取り入れる  
  tool→Resource Manager→Import drawables

- QUALIFIER TYPE：Density
- VALUE：No Density

- リソースtypeごとに適切なフォルダに入れる  
  https://developer.android.com/guide/topics/resources/available-resources?hl=ja&authuser=3

- contentDescription = null  
  背景は読み上げる必要はないのでTalkBack が Image コンポーザブルをスキップするために記述

- Box コンポーザブルで囲む  
  単語を右クリック→コンテキストアクションの表示→Surround with wedged→Surround with container
- ContentScale.Crop  
  画像の幅と高さが、それぞれ画面の幅と高さと等しいかそれ以上になるように、  
  アスペクト比を維持しながら均等に画像を拡大

- alpha：画像の不透明度設定　例）alpha = 0.5F

- ハードコードされた文字列の問題点

  1. アプリを他の言語に翻訳するのが難しくなる。
  2. アプリの文字列を別の場所で再利用するのが難しくなる。

  (解決策)単語マウスオーバー→電球→Extract Resourceで変数名と値を保存できる  
  保存場所はapp > res > values > strings.xml
