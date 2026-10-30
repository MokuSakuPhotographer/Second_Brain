---
tags:
  - "技術/プログラミング"
  - "技術/ソフトウェア"
source:
  - "https://developer.mozilla.org/ja/docs/Web/HTML](https://developer.mozilla.org/ja/docs/Web/HTML"
  - "https://developer.mozilla.org/ja/docs/Learn_web_development/Core/Styling_basics/What_is_CSS](https://developer.mozilla.org/ja/docs/Learn_web_development/Core/Styling_basics/What_is_CSS"
  - "https://developer.mozilla.org/ja/docs/Learn_web_development/Core/Scripting/What_is_JavaScript](https://developer.mozilla.org/ja/docs/Learn_web_development/Core/Scripting/What_is_JavaScript"
  - "https://www.php.net/manual/ja/introduction.php](https://www.php.net/manual/ja/introduction.php"
  - "https://developer.mozilla.org/ja/docs/Learn_web_development/Extensions/Server-side/First_steps/Introduction](https://developer.mozilla.org/ja/docs/Learn_web_development/Extensions/Server-side/First_steps/Introduction"
  - "https://developer.mozilla.org/ja/docs/Learn_web_development/Extensions/Server-side/First_steps/Client-Server_overview](https://developer.mozilla.org/ja/docs/Learn_web_development/Extensions/Server-side/First_steps/Client-Server_overview"
created: 2026-10-29
updated: 2026-10-29
aliases: []
関連:
  - "[[静的・動的サイトの仕組みと違い]]"
sort_yomi: えいちてぃーえむえるしーえすえすじゃばすくりぷとぴーえいちぴーのちがいとやくわり
status: review
---

# HTML・CSS・JavaScript・PHPの違いと役割

## 1. 概要

Webサイトは、複数の技術を組み合わせて構築されている。

その中でも代表的な技術が、**HTML・CSS・JavaScript・PHP**の4つである。

これらは似た用途で使われることもあるが、それぞれ担当する役割が異なる。

|技術|正式名称|主な役割|例え|
|---|---|---|---|
|**HTML**|HyperText Markup Language|ページの構造を作る|建物の骨組み|
|**CSS**|Cascading Style Sheets|見た目を整える|壁紙・内装|
|**JavaScript**|JavaScript|動作や処理を実装する|電気設備・自動ドア|
|**PHP**|PHP: Hypertext Preprocessor|サーバー側で情報を処理する|裏方スタッフ|

> [!IMPORTANT] 基本的な考え方
> 
> - **HTML：何を表示するか**
>     
> - **CSS：どのように見せるか**
>     
> - **JavaScript：どのように動かすか**
>     
> - **PHP：サーバー側で何を処理するか**
>     
> 
> ただし、JavaScriptはブラウザだけでなくサーバー側でも実行できる。

---

## 2. HTMLとは？

### HTMLの役割

HTML（HyperText Markup Language）は、**Webページの構造や内容を定義するマークアップ言語**である。

例えば、以下の要素を作成する。

- 見出し
    
- 文章
    
- 画像
    
- リンク
    
- ボタン
    
- 入力フォーム
    

HTMLはプログラミング言語ではなく、マークアップ言語に分類される。

### HTMLのコード例

```
<h1>ホテルのご案内</h1>
<p>当ホテルへようこそ。</p>
<button>予約する</button>
```

このコードでは、見出し・文章・ボタンを定義している。

ただし、HTMLだけでは、予約ボタンを押した際に予約情報を保存する処理までは実装されない。

### HTMLの特徴

HTMLはWebサイトの土台となる技術であり、ブラウザがページの構造を理解するために利用される。

---

## 3. CSSとは？

### CSSの役割

CSS（Cascading Style Sheets）は、**HTMLなどで作成された要素の見た目や配置を指定するスタイルシート言語**である。

例えば、以下の設定に利用される。

- 文字の色や大きさ
    
- 背景色
    
- ボタンの形状
    
- 余白
    
- 要素の配置
    
- アニメーション
    

### CSSのコード例

```
button {
    background-color: blue;
    color: white;
    border-radius: 10px;
    padding: 10px 20px;
}
```

このコードをHTMLのボタンに適用すると、次のように表示が変化する。

|設定|変更内容|
|---|---|
|background-color|背景を青色にする|
|color|文字を白色にする|
|border-radius|角を丸くする|
|padding|ボタン内部に余白を作る|

### CSSの特徴

CSSはHTMLの構造を変更せずに、見た目を変更できる。

また、CSSだけでもアニメーションを実装できる。

そのため、Webサイトに動きがあるからといって、必ずJavaScriptが使用されているとは限らない。

---

## 4. JavaScriptとは？

### JavaScriptの役割

JavaScriptは、**Webページに操作性や動的な機能を追加できるプログラミング言語**である。

代表的な用途は以下のとおり。

- ボタンを押した際の処理
    
- メニューの開閉
    
- 画像の切り替え
    
- 入力内容の確認
    
- APIからの情報取得
    
- 画面の自動更新
    
- アニメーション
    

### JavaScriptのコード例

```
document.querySelector("button").addEventListener("click", () => {
    alert("予約画面へ進みます");
});
```

このコードでは、ボタンがクリックされるとメッセージが表示される。

HTMLだけでは定義されていなかったクリック時の動作を、JavaScriptによって追加している。

### JavaScriptの特徴

JavaScriptは主にブラウザ上で利用されるが、実行環境によってはサーバー側でも動作する。

例えば、以下の技術が存在する。

|技術|役割|
|---|---|
|ブラウザのJavaScript|画面操作・表示更新|
|Node.js|サーバー側などでJavaScriptを実行する環境|
|Cloudflare Workers|サーバー側の処理を実行できるサービス|

> [!NOTE] 補足  
> JavaScriptは画面操作専用の言語ではない。
> 
> サーバー側で使用すれば、PHPと同様にAPIや認証などの処理を実装できる。

---

## 5. PHPとは？

### PHPの役割

PHP（PHP: Hypertext Preprocessor）は、**主にWebサーバー上で動作するプログラミング言語**である。

代表的な用途は以下のとおり。

- ログイン認証
    
- データベースへのアクセス
    
- 予約情報の保存
    
- 商品情報の取得
    
- 問い合わせフォームの処理
    
- HTMLの動的生成
    

### PHPのコード例

```
<?php
$name = "山田";

echo "ようこそ、" . $name . "様";
?>
```

このコードをPHPが実行すると、次の文字列が出力される。

```
ようこそ、山田様
```

サーバーで生成された結果をブラウザへ送信できる。

### PHPの特徴

PHPは、一般的なWebサイトではサーバー側で実行される。

そのため、通常はPHPのソースコードそのものをブラウザへ送信するのではなく、処理結果を送信する。

処理結果はHTMLに限らず、JSONなどのデータ形式にもできる。

### PHPが使用される代表例

**WordPress**が挙げられる。

WordPressでは、PHPを利用して記事情報の取得やページ生成などを行っている。

ただし、PHPはWebサイトを構築するための必須技術ではない。

JavaScriptやPythonなど、ほかの言語でもサーバー側の機能を実装できる。

---

## 6. 4つの技術はどのように連携するのか？

Webサイトでは、各技術が役割を分担して動作する。

以下は、PHPを使ってページを生成する場合の基本的な仕組みである。

```
flowchart TD
    A["利用者がWebサイトへアクセス"]
    B["Webサーバー"]
    C["PHP：必要な情報を処理"]
    D[("データベース")]
    E["HTML：ページの構造"]
    F["CSS：見た目を整える"]
    G["JavaScript：操作や表示更新"]
    H["利用者のブラウザ"]

    A --> B
    B --> C
    C <-->|必要に応じて情報を取得・保存| D
    C -->|HTMLを生成| E
    E --> H
    F --> H
    G --> H
```

※CSSやJavaScriptは、通常、ブラウザがサーバーなどから取得する。PHPの使用やデータベースへの接続は必須ではない。

### ブラウザとサーバーの役割

|技術|主な実行・処理場所|
|---|---|
|HTML|ブラウザが解析・表示|
|CSS|ブラウザが解析・適用|
|JavaScript|ブラウザ、またはサーバー|
|PHP|主にサーバー|

HTMLとCSSは、JavaScriptやPHPのような汎用プログラミング言語ではない。

また、HTML・CSS・JavaScript・PHPが必ず決まった順番で実行されるわけではない。

---

## 7. ホテルの予約サイトを例に比較する

4つの技術の違いは、ホテルの予約サイトを例にすると理解しやすい。

### ① HTML：予約画面を作る

HTMLによって以下の要素を定義する。

- 宿泊日の入力欄
    
- 宿泊人数の選択欄
    
- 予約ボタン
    

### ② CSS：予約画面をデザインする

CSSによって以下の表示を整える。

- ボタンの色
    
- 入力欄の大きさ
    
- 文字の配置
    
- スマートフォン向けのレイアウト
    

### ③ JavaScript：予約画面を操作できるようにする

JavaScriptによって以下の機能を追加する。

- カレンダーの表示
    
- 宿泊人数の変更
    
- 入力漏れの確認
    
- 画面を再読み込みせずに検索結果を更新
    

### ④ PHP：予約情報をサーバー側で処理する

PHPによって以下の処理を実装できる。

- 空室状況の取得
    
- 予約料金の計算
    
- 予約情報の保存
    
- 利用者の認証
    

ただし、これらはPHPで実装した場合の例であり、ほかのサーバー側プログラミング言語でも実現できる。

### 処理の流れ

```
sequenceDiagram
    participant U as 利用者
    participant B as ブラウザ
    participant S as サーバー（PHP）
    participant D as データベース

    U->>B: 宿泊日を入力
    Note over B: HTMLで入力欄を表示
    Note over B: CSSでデザインを適用

    U->>B: 検索ボタンを押す
    Note over B: JavaScriptで入力内容を確認

    B->>S: 検索条件を送信
    S->>D: 空室状況を問い合わせ
    D-->>S: 空室データを返す
    S-->>B: 検索結果を送信

    Note over B: JavaScriptで検索結果を表示
```

この例では、各技術が異なる役割を担当しながら、1つの予約システムとして動作している。

---

## 8. JavaScriptとPHPの違い

4つの技術の中でも、特に混同しやすいのがJavaScriptとPHPである。

両方ともプログラミング言語であり、情報の処理や条件分岐などを実装できる。

ただし、一般的なWeb開発における主な用途が異なる。

|比較項目|JavaScript|PHP|
|---|---|---|
|主な用途|画面操作・Webアプリの処理|サーバー側のWeb処理|
|ブラウザで実行|可能|通常は不可|
|サーバーで実行|可能|可能|
|HTMLの変更|ブラウザ上で可能|HTMLを生成して送信可能|
|データベース操作|サーバー側では可能|可能|
|APIの実装|可能|可能|
|アニメーション|ブラウザ上で実装可能|通常は直接担当しない|

### 最大の違い

**JavaScriptはブラウザとサーバーの両方で利用できるが、PHPは主にサーバー側の処理に使用される。**

なお、ブラウザ上のJavaScriptによる入力チェックだけでは、不正なリクエストを防止できない。

ログイン認証や重要な入力内容の検証は、サーバー側でも実行する必要がある。

---

## 9. 静的サイトと動的サイトとの関係

HTML・CSS・JavaScript・PHPの違いは、静的サイトと動的サイトの仕組みにも関係する。

### 静的サイト

事前に生成したHTMLを配信するサイトである。

HTML・CSS・JavaScriptを使用するだけでも構築できる。

```
HTML
 ├─ CSS
 └─ JavaScript
      ↓
   ブラウザに表示
```

### 動的サイト

アクセス時にサーバー側で処理を実行し、必要なページやデータを生成するサイトである。

PHPなどのサーバー側プログラムを使用できる。

```
ブラウザ
   ↓
Webサーバー
   ↓
PHPなどのプログラム
   ↓
データベース（必要な場合）
   ↓
処理結果をブラウザへ返す
```

> [!IMPORTANT] 注意点  
> PHPを使用していなくても、動的サイトは構築できる。
> 
> また、静的サイトでもJavaScriptによって画面を動的に変更できる。
> 
> したがって、JavaScriptやPHPの使用有無だけで、静的サイト・動的サイトを分類することはできない。

---

## 10. まとめ
![[Pasted image 20261029062120.png]]

HTML・CSS・JavaScript・PHPは、Webサイトを構築するための異なる役割を持った技術である。

|技術|最も重要な役割|
|---|---|
|**HTML**|Webページの構造と内容を定義する|
|**CSS**|Webページの見た目を整える|
|**JavaScript**|動作・操作・プログラムによる処理を実装する|
|**PHP**|主にサーバー側で情報を処理する|

### 覚え方

> [!SUMMARY] 4つの技術の違い  
> **HTMLは骨組み、CSSはデザイン、JavaScriptは動作、PHPはサーバー側の処理である。**
> 
> HTML・CSS・JavaScriptはWebページを構成する中心的な技術である。
> 
> 一方、PHPは必要に応じて使用するサーバー側のプログラミング言語であり、Webサイトに必須ではない。

---

## 出典・参考資料

以下はMDN Web DocsおよびPHP公式マニュアルの資料である。

1. **MDN Web Docs — HTML: ハイパーテキストマークアップ言語**  
    [https://developer.mozilla.org/ja/docs/Web/HTML](https://developer.mozilla.org/ja/docs/Web/HTML)
    
2. **MDN Web Docs — CSSとは何か**  
    [https://developer.mozilla.org/ja/docs/Learn_web_development/Core/Styling_basics/What_is_CSS](https://developer.mozilla.org/ja/docs/Learn_web_development/Core/Styling_basics/What_is_CSS)
    
3. **MDN Web Docs — JavaScriptとは**  
    [https://developer.mozilla.org/ja/docs/Learn_web_development/Core/Scripting/What_is_JavaScript](https://developer.mozilla.org/ja/docs/Learn_web_development/Core/Scripting/What_is_JavaScript)
    
4. **PHP公式マニュアル — PHP入門**  
    [https://www.php.net/manual/ja/introduction.php](https://www.php.net/manual/ja/introduction.php)
    
5. **MDN Web Docs — サーバーサイドの概要**  
    [https://developer.mozilla.org/ja/docs/Learn_web_development/Extensions/Server-side/First_steps/Introduction](https://developer.mozilla.org/ja/docs/Learn_web_development/Extensions/Server-side/First_steps/Introduction)
    
6. **MDN Web Docs — クライアント・サーバーの概要**  
    [https://developer.mozilla.org/ja/docs/Learn_web_development/Extensions/Server-side/First_steps/Client-Server_overview](https://developer.mozilla.org/ja/docs/Learn_web_development/Extensions/Server-side/First_steps/Client-Server_overview)