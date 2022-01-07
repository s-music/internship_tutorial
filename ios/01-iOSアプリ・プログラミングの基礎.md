# イントロダクション

## iOSアプリ開発

iOSアプリの開発ではMacで利用可能なIDE(統合開発環境)[^1]の<font color="Green">Xcode</font>を使用します。<br>
また、使用するプログラミング言語は<font color="Green">Swift</font>とObjective-Cのいずれかを選択できますが、現在はSwiftが主流となっています。<br>
(2020年12月時点でXcodeはVersion 12.2、SwiftはSwift5が最新版となっています。)<br>

実際にXcodeでアプリを作ってみましょう。<br>

## 新規プロジェクトの作成

#### 1. Xcodeを起動すると次のような画面が開きます。

![xcode-1-1](./images/xcode-1-1.png)

#### 2. "Create a new Xcode project"を選択すると、プロジェクトのテンプレートを選択する画面が表示されます。

![xcode-1-2](./images/xcode-1-2.png)

いくつかのテンプレートが用意されていますが、ここではもっとも基本的な"App"を選択します。<br>

#### 3. テンプレートを選択し、"Next"を押すとプロジェクトの名前などを設定する画面が表示されます。

![xcode-1-3](./images/xcode-1-3.png)

※ Xcode 11から、ボタンの配置などUI(User Interface)の作成に<font color="Green">Storyboard</font>と<font color="Green">Swift UI</font>のいずれかが選択可能となりました。<br>
今回の研修ではStoryboardを使って開発を行なっていきたいと思います。<br>

入力を終えて"Next"を押すと、プロジェクトの保存場所を選択になりますが、特にこだわりがない場合はデフォルトで選択されている場所に保存して構いません。<br>
保存場所決定すると、iOSアプリのプロジェクトが作成されます。<br>

## Xcodeの各画面の説明

![xcode-1-4](./images/xcode-1-4.png)


#### 1. ツールバー
アプリの起動・停止などの操作を行うボタンなどが存在するエリアです。<br>

#### 2. ナビゲーションエリア
プロジェクト(アプリ)を構成するフォルダやファイルの一覧を表示するエリアです。<br>

#### 3. エディタエリア
ファイルを編集するエリアです。<br>

#### 4. ユーティリティエリア
ファイルのプロパティなどを設定するエリアです。<br>

## アプリの起動

プロジェクトを作成した時点でiOSアプリをMac上で起動することができます。<br>
ツールバーの"▶︎"を押してアプリを起動してみましょう。真っ白な画面が出てきたら成功です。<br>
※シュミレータがインストールされていない場合は、インストールしてから起動する必要があります。<br>

![xcode-1-5](./images/xcode-1-5.png)
![xcode-1-6](./images/xcode-1-6.png)


### 実機での起動

また、AppleIDとpasswordをお持ちの方は実機でテストすることもできます。<br>
1.General > SigningのTeamで自分のアカウントを設定する<br>
2.ツールバーからDeviceを接続している端末に設定し、build<br>
3.設定 > 一般 > プロファイルとデバイスの管理から、デベロッパAPPで自分のアカウントを信頼する。<br>

アプリの起動を確認できたので、ここからアプリに様々な変更を加えていきたいと思います。<br>

<!-- Annotations -->
[^1]:開発に必要なツールがひとまとめになったソフトウェア

# iOSアプリ開発・プログラミングの基礎

iOSアプリは基本的に以下の手順を繰り返して作り込んでいきます。<br>

#### UIの作成(パーツの配置) → 配置したUIパーツとユーザー(アプリ利用者)のアクションに対して処理を紐づける → 紐づけた処理を実装する(コーディング)

まずは簡単なUIパーツを配置して、アプリを動かしてみましょう。<br>

## ラベル(文字)

#### 1. Main.storyboardを開く

![xcode-2-1](./images/xcode-2-1.png)

Main.storyboardはアプリの画面を設定するファイルです。<br>
ここに表示されているiPhoneの画面に対してパーツを配置していきます。<br>

#### 2. Labelを配置する

ツールバーの+ボタンを押してメニューを表示し、Labelをドラッグアンドドロップで画面に配置します。<br>

![xcode-gif-2-1](./gifs/xcode-gif-2-1.gif)

#### 3. 文字を編集する

デフォルトでは「Label」の文字が入っているため、ここに任意の文字を入力してみます。<br>

![xcode-gif-2-2](./gifs/xcode-gif-2-2.gif)

#### 4. 実行

この状態でアプリを起動してみましょう先ほど入力した文字が表示されるはずです。<br>
※現時点では端末によって配置した場所からずれて表示される場合があります。<br>

![xcode-2-2](./images/xcode-2-2.png)

#### 5. 色を変更する

右側のユーティリティエリアから画面や配置したパーツの設定をいじることができます。背景色や文字色を変化させてみましょう。<br>
背景色 → 「View」を選択し、ユーティリティエリアから「Background」を変更します。<br>
文字色 → 「Label」を選択し、ユーティリティエリアから「Color」を変更します。<br>

![xcode-2-3](./images/xcode-2-3.png)

## ボタン

#### 1. Buttonを配置する

ツールバーのLibraryボタンを押してメニューを表示し、Buttonをドラッグアンドドロップで画面に配置します。<br>

![xcode-gif-2-3](./gifs/xcode-gif-2-3.gif)

配置が終わったら、Labelと同じ様にユーティリティエリアからTitle, Text Color, Background Colorなどを変更して見た目を整えてください<br>

![xcode-2-4](./images/xcode-2-4.png)

#### 2. ボタンを押した時の処理を実装する

ボタンを配置できたので、このボタンを押した時、Labelの文字を変更する処理を実装してみましょう。(プログラミング)<br>
実装手順はいくつも考えられますが、今回は以下の手順で作っていきます。<br>

1. 画面に紐づくソースコードを開く
2. 変更対象のラベルをソースコードに紐づける
3. <u>「ボタンを押して離す」</u>というアクションをソースコードに紐づける
4. ソースコードに紐づけたラベルのTextにアクセスして、文字を変更する処理を記述する。
5. 実行してみて動作を確認する。

#### ソースコードの表示

まず、画面に紐づくソースコードを表示してみます。<br>
以下のように画面上部のハンバーガーメニューから「Assistant」を選択することで、ソースコードを表示することが可能です。<br>

![xcode-gif-2-4](./gifs/xcode-gif-2-4.gif)


※ ここで開いたソースコードはナビゲーションエリアに表示されている「ViewController.swift」です。<br>

#### ラベルの紐づけ

Main.storyboard上のLabelをctrlキーを押しながらクリックし、ソースコードに向かって引っ張ります。<br>
メニューが表示されるので、ソースコード上でこのラベルを扱うための名前を入力すると、ソースコード上に一行追加されます。<br>
●がつけば紐づけ完了です。<br>

![xcode-gif-2-5](./gifs/xcode-gif-2-5.gif)

#### アクションの紐づけ

Main.storyboard上のButtonを選択し、ユーティリティエリアの一番左の「→」ボタンをクリックすると、そのボタンに対するアクションの一覧が表示されます。<br>
この一覧の中の「Touch Up Inside」(UIパーツの上で指を離すアクション)の○マークをクリックし、ソースコードに向かって引っ張ります。<br>
●がつけば紐づけ完了です。<br>

![xcode-gif-2-6](./gifs/xcode-gif-2-6.gif)

#### 処理の記述

最後にラベルの文字列を変更する処理を記述します。<br>
アクションに紐づけた部分の{}の間に以下の様な記述を加えてください。<br>

```swift
@IBAction func onPushButton(_ sender: Any) {
  label.text = "Goodbye"
}
```

これは<font color="red">代入</font>と呼ばれる処理になります。<br>
ボタンが押された時にラベルのテキスト(表示する文字)に対して"Goodbye"という文字列を代入しています。<br>

#### 3. 実行

ここまでできたら実際に動かして確認してみましょう。ボタンを押した時にLabelの文字が変化するはずです。<br>

![xcode-2-5](./images/xcode-2-5.png)

## テキストボックス

次にテキストボックスを使ってユーザーから入力された文字列をラベルに設定する処理を実装してみましょう。<br>

#### 1.TextFieldを配置する

ツールバーのLibraryボタンを押してメニューを表示し、Text Fieldをドラッグアンドドロップで画面に配置します。<br>

![xcode-2-6](./images/xcode-2-6.png)

#### 2.テキストボックスの紐づけ

ラベルの時と同様に、Main.storyboard上のText Fieldをctrlキーを押しながらクリックし、ソースコードに向かって引っ張って紐付けを行います。<br>

![xcode-2-7](./images/xcode-2-7.png)

#### 3.処理の記述

先ほどボタンを押した時の処理を記述した部分を、テキストボックスの値を設定するように修正します。<br>

```swift
@IBAction func onPushButton(_ sender: Any) {
  label.text = textField.text
}
```

#### 4. 実行

## 計算機アプリ

ここまでで大体の流れが掴めたと思うので、もう少し実用的なアプリにしてみましょう。<br>
三つのテキストボックスを用意し、二つの入力値を使って四則演算を行うアプリを作ります。<br>

<!-- TODO: 完成イメージのgifを用意 -->

#### 1. TextFieldを配置し、コードに紐づける

まずは、演算子と第二項を入力するためのテキストボックスを二つ用意します。<br>

![xcode-2-8](./images/xcode-2-8.png)

配置し終えたらコードへの紐づけも行いましょう。<br>

#### 2. 処理の記述

ボタンを押した際の処理を、テキストボックスの入力値を元に四則演算を行う処理に書き換えていきます。<br>
まず、それぞれのテキストフィールドの入力値を取得してみましょう。以下の様に記述してください。<br>
(警告が表示されますが、気にせず記述してください。)<br>

```swift
@IBAction func onPushButton(_ sneder: Any) {
  let text = textField.text
  let text2 = textField2.text
  let text3 = textField3.text
}
```

この`let text = textField.text`は<font color="red">変数定義</font>と呼ばれます。<br>
変数は、処理の中で値に名前をつけて保持しておく為に使用されます。<br>
この変数の中身を見てみましょう。<br>
ラベルの書き換えでは、テキストボックスの値を画面に表示しましたが、xcode上から値を参照することもできます。<br>
以下の様に記述を変更してください。<br>

```swift
@IBAction func onPushButton(_ sender: Any) {
  let text = textField.text
  let text2 = textField2.text
  let text3 = textField3.text
  print(text)
  print(text2)
  print(text3)
}
```

この状態で実行すると、以下の様にエディタエリアの下(デバッグエリア)に文字が表示されます。<br>
printを使用すると()の中に記述した値がデバッグエリアに表示されます。<br>

![xcode-2-9](./images/xcode-2-9.png)

ここで`Optional("a")`と表示されていますが、Optionalは値が取れるかどうか不確定なものに付与されるもので、<br>
テキストボックスの値を取得した際、その値が確実に取得できることが保証されていないため、この様な表示になっています。<br>

次に取得した値を使って計算を行いますが、このままでは計算を行うことができません。<br>
というのも、swiftには<font color="red">データ型</font>という概念があり、それぞれの値がどういった種類のデータなのかが厳格に区別されているからです。<br>
テキストボックスの値は<font color="red">String型(文字列型)</font>という種類のデータで、計算を行う為には<font color="red">Int型(整数型)</font>に変換する必要があります。<br>
また、Optionalもデータ型の一種で、テキストボックスの値は正確には<font color="red">Optional\<String\>型</font>です。<br>
このため、計算を行う為にはOptional\<String\>型 → String型 → Int型の変換処理をコードに記述する必要があります。<br>
まずはOptional\<String\>型 → String型の変換処理です。<br>

```swift
@IBAction func onPushButton(_ sender: Any) {
  let text = textField.text ?? ""
  let text2 = textField2.text ?? ""
  let text3 = textField3.text ?? ""
  print(text)
  print(text2)
  print(text3)  
}
```

Optional\<String\>型 → String型の変換は`Optional値 ?? 値が取れなかった場合の代替値`とすることで変換可能です。<br>
`let text = textField.text ?? ""`は、テキストボックスの入力値が正しく取得できた場合、その値を、取得できなかった場合""(空文字)を変数textとして保持しておきます。[^1]<br>
次にString型 → Int型の変換処理です。<br>

```swift
@IBAction func onPushButton(_ sender: Any) {
  // 変数名を変更
  let num1 = Int(textField.text ?? "") ?? 0
  let num2 = Int(textField2.text ?? "") ?? 0
  let num3 = Int(textField3.text ?? "") ?? 0
  print(num1)
  print(num2)
  print(num3)
}
```

String型 → Int型の変換処理は、`Int(String型の値)`とすれば良いのですが、注意しなければならないのが、この変換後の値がOptional\<Int\>となることです。<br>
String型 → Int型の変換処理では、1という文字を1という数値に変換することはできても、aという文字に対応する数値がないため、値をうまく変換することができないことがあるからです。<br> 
そのため、`?? 0`をつけて代替値を用意する必要があります。<br>
<br>
ここまでできると、四則演算が可能となります。<br>
例えば足し算は以下のようにします。<br>

```swift
@IBAction func onPushButton(_ sender: Any) {
  let num1 = Int(textField.text ?? "") ?? 0
  let num2 = Int(textField2.text ?? "") ?? 0
  let num3 = Int(textField3.text ?? "") ?? 0
  print(num1 + num3)
}
```

その他の演算は以下の通りです。<br>

| 演算子 | 演算 |
| :-: | :-- |
| - | 引き算 |
| * | 掛け算 |
| / | 割り算(商のみ) |

四則演算ができたので、残るは演算子の判定のみです。<br>
textField2.textに演算子が入力されるとして、この値によって行う演算を変化させる処理を記述します。<br>
以下のようにプログラムを変更してください。<br>

```swift
@IBAction func onPushButton(_ sender: Any) {
  let num1 = Int(textField.text ?? "") ?? 0
  let op = textField2.text ?? "" // 演算子は文字列なのでInt型に変換しない
  let num2 = Int(textField3.text ?? "") ?? 0 // 変数名を変更
  // opの値によって処理を分岐させる
  switch (op) {
  case "+":
    label.text = String(num1 + num2) // label.textはString(?)型のため、計算結果をString型に変換してから設定
  case "-":
    label.text = String(num1 - num2)
  case "*":
    label.text = String(num1 * num2)
  case "/":
    label.text = String(num1 / num2)
  default:
    label.text = "エラー" // +, -, *, /のどれにも当てはまらない場合はエラーを設定
  }
}
```

これは<font color="red">switch文</font>と呼ばれる構文で、*switch()*内に指定した値が*case*で列挙した値のどれかに当てはまる場合コロン(:)以降の処理を実行します。<br>
コロン(:)以降の処理については複数行記述でき、以下のように変数定義もできます。<br>

```swift
~ 省略 ~

case "+":
  let result = num1 + num2
  label.text = String(result)

~ 省略 ~
```

また、同じ処理を以下のように記述することもできます。<br>

```swift
@IBAction func onPushButton(_ sender: Any) {
  let num1 = Int(textField.text ?? "") ?? 0
  let op = textField2.text ?? ""
  let num2 = Int(textField3.text ?? "") ?? 0
  if (op == "+") { // opと+が同一の値かどうか比較を行なっている
    label.text = String(num1 + num2)
  } else if (op == "-") {
    label.text = String(num1 - num2)
  } else if (op == "*") {
    label.text = String(num1 * num2)
  } else if (op == "/") {
    label.text = String(num1 / num2)
  } else {
    label.text = "エラー"
  }
}
```

こちらは<font color="red">if文</font>と呼ばれる構文で、最初は*if()*、それ以降は*else if()*に値の値の比較などの実行条件を記述することで、その条件が真の場合に*{}*で囲まれた部分の処理を行います。<br>
*else*はif, else ifのどの条件にも該当しない場合に実行されます。<br>
今回は*==(等号)*を使って値を比較しましたが、他には以下のような比較があります。<br>

| 演算子 | 演算 |
| :-: | :-- |
| a != b | aとbは等しくない |
| a > b | aはbより大きい |
| a >= b | aはb以上 |
| a < b | aはbより小さい |
| a <= b | aは以下 |
