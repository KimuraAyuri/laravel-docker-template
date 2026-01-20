# Laravel Lesson レビュー②

## Todo編集機能

### @method('PUT')を記述した行に何が出力されているか
<input type="hidden" name="_method" value="PUT">のinputタグが出力されている。
HTMLのフォームタグではGETとPOSTしか使う事ができないため、POSTとして送るが、
中身を見てPUTとして扱う仕組みになっている。

### findメソッドの引数に指定しているIDは何のIDか
todosテーブルのidカラムの値。ルート定義のURLの{id}から来ている。
{id}はプレースホルダ

### findメソッドで実行しているSQLは何か
選んだidのレコードの1件だけ選ぶSELECT文

### findメソッドで取得できる値は何か
todosテーブルの1行を表すTodoモデルのインスタンスを1件、データ型はオブジェクト

### saveメソッドは何を基準にINSERTとUPDATEを切り替えているのか
idが存在しているかどうか

## Todo論理削除

### traitとclassの違いとは
traitはclassと異なり、インスタンス化ができず、継承できない。classに取り込んで使うもの。

### traitを使用するメリットとは
継承では表現しずらい共通処理を、必要なクラスにだけ安全に使いまわせる

## その他

### TodoControllerクラスのコンストラクタはどのタイミングで実行されるか
TodoControllerクラスのコンストラクタはどのタイミングで実行されるか判断された瞬間

### RequestクラスからFormRequestクラスに変更した理由
リクエストを受け取った直後、コントローラーの処理に入る前に自動でバリテーションを行えるから

### $errorsのhasメソッドの引数・返り値は何か
引数はcontent、フォームのname属性
返り値はtrueかfalseのbool型

### $errorsのfirstメソッドの引数・返り値は何か
引数はcontent、フォームのname属性
返り値はstring型、その項目の最初のエラーメッセージ

### フレームワークとは何か
アプリを作成するための土台セット
よく使う処理をすでに用意できているため、安全・効率的にアプリが作れる。複数人で開発しやすい。

### MVCはどういったアーキテクチャか
役割ごとに処理を分けている
ModelはDBとの接続部分
Viewは画面表示
Controller処理の司令塔

### ORMとは何か、またLaravelが使用しているORMは何か
DBのテーブルを、プログラミング言語「オブジェクト」として扱えるようにする仕組み

### composer.json, composer.lockとは何か
composer.jsonは使いたいライブラリの設計図
composer.lockは実際に入れたライブラリのリスト

### composerでインストールしたパッケージ（ライブラリ）はどのディレクトリに格納されるのか
Vendorディレクトリに格納される

