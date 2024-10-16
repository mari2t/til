## 参考

https://developer.android.com/codelabs/basic-android-kotlin-compose-build-a-dice-roller-app?authuser=3&continue=https%3A%2F%2Fdeveloper.android.com%2Fcourses%2Fpathways%2Fandroid-basics-compose-unit-2-pathway-2%3Fauthuser%3D3&hl=ja#0

## メモ

- プロジェクトを作って立ち上げたところcode,split,designが表示されなかったが、再起動したら表示された。
- Compose は、その性質上、UI コンポーネントを順番に配置します。→上から表示される順に書く。
- コールバック：関数を引数として渡す
- 数字の範囲指定　例）result = (1..6).random()
- remember：Compose内で一度生成した値を再コンポーズの際に忘れないようにメモリに保持するために使います。
- mutableStateOfは、UIが自動で再描画されるようにする「オブザーバブル」を作成します。  
  このオブザーバブルの値が変わると、Composeがその変更を感知してUIを更新します。
