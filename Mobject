# Mobject

JSONからオブジェクト  
オブジェクトからJSON  
に双方変換するためのライブラリ

処理に```Gson```を利用しています。

ゲーム毎にオリジナルの値を保存したい要望を受けたが予め定義された値以外、追加・変更は不可能だった。そこで
- **環境に応じて値を保存、取得を行えるようにした。**　
- **キーが存在しなかった場合はそのデータを破棄しない**  

を実装したライブラリを2017年後期に作ったが、より実装側に当たり障りのない機能を提供したくて作り直したのが**Mobject**

以下のコードサンプルはKotlinで実装。(たぶんJavaでも動くはず)

## 利用する。
Mobjectクラスを継承します。
```kotlin
class Sample: Mobject()
```

### 利用する値をキーと共に登録  
変数・定数で定義し、出力するJSONに値を含める場合はSerializeアノテーションを付与してください。
```kotlin
//変数・定数として定義する場合 (共通部分)
@Serialize val example = string("hello data lib!") //String
@Serialize val example = number(512) //Number (Int, Double, Float, Short, Long, Byte etc...)
@Serialize val example = boolean(true) //Boolean 
@Serialize val example = list(arrayListOf(number(1),number(2))) //List
@Serialize val example = array(number(1),number(2)) //List (可変長引数で定義)
@Serialize val mobject = mobject(Mobject()) //Mobject

//Mobjectで定義する場合 (ある一定の場面のみ値を必要と場合などに利用)
"example" mo "hello data lib!" //String
"example" mo 512 //Number (Int, Double, Float, Short, Long, Byte etc...)
"example" mo true //Boolean
"example" mo arrayListOf(number(1),number(2)) //ArrayList<Int>
"example" mo array(number(1),number(2)) //List (可変長引数で定義)
"example" mo Mobject() //Mobject
```

予め定義しておくことでシステムは
JSONからオブジェクトに変換されたときに値はフィールドにセットします

### フィールドで定義した値を取得 
(例としてString型の「example」というキーの値を取得します。)
```kotlin
print(example.toString) //out: hello data lib!
```

Mutantクラスが返されます

### 定義した値(フィールド・Mobject内)を取得 
(例としてString型の「example」というキーの値を取得します。)
```kotlin
//定数・変数で定義されていない値はMobject内部で定義されます
get("example") //キーが存在しなかった場合はスルーされます(NoSuchFieldException)を吐きます。
find("example") //キーが存在しなかった場合はnullを返します。

print(get("example").toString) //out: hello data lib!

```
Mutantクラスが返されます


### 登録した値を更新 
(例としてString型の「example」というキーの値を更新します。)
```kotlin
//変数・定数として定義した場合
example set "更新したよ"
print(example.toString) //out: 更新したよ

//Mobjectで定義した場合
"example" mo "更新したよ" //定義時と同じ
print(find("example").toString) //out: 更新したよ
```

### 登録されているキーと値のペアを消去 
(例として「example」というキーの値を消去します)
```kotlin
//Mobjectで定義した場合
remove("example")
```

### 実用例 
人間のクラスをJSONで出力したり、読み込んだり...
```kotlin
// 準備中
```
上記の結果: 
```kotlin
// 準備中
```




