# docs

## 作成モードの時

以下の図の流れに沿って画面の作成、モードの遷移が行われる。

![作成モードの時](./img/edit-mode.png)

各イベントからラダー図を作成していく、そして遷移する際にラダー図を実行用にコンバート、そして実行モードへと移る。


## 実行モードの時

実行モードの時の見取り図。この流れに沿って処理をする。

![実行モードの時](./img/execute-mode.png)

### interface

図では`input channel`と`observer`がGoのプログラムのエントリーポイントとなる。ラダー図の処理をする内部部分は他のところでも使いまわしたいためライブラリとして実装し、それのインターフェースとなる。
インターフェースより上はライブラリが担う部分

#### `ladder state` について

ここに実行するラダー図が格納される。ラダー図そのまま格納するのではなく実行形式のデータ構造にして格納する。そしてそのデータを利用してラダー図をシミュレートする。