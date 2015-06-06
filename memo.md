### 実際のコード
https://github.com/HirotakaTakayama/HirotakaTakayama-sezemi-2015-readable-code

・memo1

```c
exit( EXIT_FAILURE );
```

・memo2

```c
#define ARG_NUM 1
if( argc != ARG_NUM + 1 ) {
```


### どうしてリーダブルだと思っているかの説明

・memo1

コマンドの終了ステータスは、正常終了するときは`0`、異常終了するときは
`0`以外の値を返すのが通例です。そのため、このコードは次のようにしても
通例通りの動きになります。

```c
exit(1);
```
これでも動きますが、`EXIT_FAILURE`とすれば、ファイルオープンに
失敗した時にこのコードが実行されるということがわかりやすく、リーダブル
であると考えました。

・memo2

引数の数は、 ./a.outを含めて2つになりますが、取り込むテキストは1つであり、
./a.out以外で必要とする引数を指定するために、ARG_NUMという定数を使用し、
リーダブルにしようと考えました。


### この書き方の一言説明

自己記述的定数名


--------
ここからtiwawan

# 1

### 実際のコード
https://github.com/HirotakaTakayama/HirotakaTakayama-sezemi-2015-readable-code
```
FILE *fp;
```

### リーダブルだと思った理由
fpという名前はC言語でFILE構造体のポインタの名前としてよく使われるので、C言語を使っている人なら何を意味するかすぐわかる。

### この書き方の一言説明
常識的な名前

 
# 2

### 実際のコード
https://github.com/HirotakaTakayama/HirotakaTakayama-sezemi-2015-readable-code
```
	while( fscanf( fp, "%s", recipe_data ) != EOF ) {
```

### リーダブルだと思った理由
recipe_dataに読み込んでそのままfscanfの戻り値を比較するのは、一時変数にfscanfの戻り値を一旦入れるより簡潔で、おそらくCプログラマはこのような書き方には慣れていると思うので。

### この書き方の一言説明
短い

# 3

### 実際のコード
https://github.com/HirotakaTakayama/HirotakaTakayama-sezemi-2015-readable-code

### リーダブルだと思った理由
変数宣言、引数の数のチェック、ファイルを開く、レシピ名の出力、終了処理のそれぞれの中では改行がなく、それらの間では一行開けるという一貫した改行の方針がとられている。

### この書き方の一言説明
改行のルールに従う


# 4

### 実際のコード
https://github.com/HirotakaTakayama/HirotakaTakayama-sezemi-2015-readable-code
```
	if( argc != ARG_NUM + 1 ) {
		printf("指定する引数の数が違います.\n");
		exit( EXIT_FAILURE );
	}
```

### リーダブルだと思った理由
括弧の前後にスペースが入っていたりいなかったりするが、これはダブルクォーテーションは空白部分が大きくスペースに近い見た目をしているのでカッコと ダブルクォーテーションが連続するときはあえてスペースを入れていないのだと思う。

### この書き方の一言説明
見た目を考慮した空白のルール


# 5

### 実際のコード
https://github.com/tiwawan/HirotakaTakayama-sezemi-2015-readable-code
if( recipe_selected == -1 || recipe_selected == recipe_id){

### リーダブルだと思う理由
IDが-1というのは普通ではないので、recipe_selected == -1という式がtrueのときは選択されているレシピがないということを意味するつもりで書いた。私と同じ感覚を持っている人にはリーダブルだと思う。

### この書き方の一言説明
数字のイメージ






