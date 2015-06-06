### 実際のコード(spec 3)
https://github.com/HirotakaTakayama/HirotakaTakayama-sezemi-2015-readable-code


```spec3 memo1
exit( EXIT_FAILURE );
```

```spec3 memo2
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