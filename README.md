## 各ファイルについて

### .env
ここにグラフや繰り返し回数など各パラメータを書いています。

### framework.py
ほとんど、rigidpy の frameworkライブラリそのもので、計算を軽くするために scipy の csr形式の疎行列で framework デフォルトで作るようにしています。

### max_eigenvalue_lib.py
ここで固有値の最適化をしています。
max_p_eigenvalue_lib 関数で p を MAX_ITER_FOR_EIGENVALUE 回更新しています。
armijo 関数で p を armijo 条件を使って更新しています。
ascent_dir 関数で p の上昇方向を計算しています。

### test_max_eigenvalue.py
この関数を実行して実験をします。グラフなどを初期化したのち、最適化計算関数を呼び出して、最後に結果を描画します。

### visualize.py
結果を描画するための関数です。

### pyproject.toml, poetry.lock
poetry という python の仮想環境管理ツールを使っており、その設定ファイルとロックファイルです。ライブラリやインタープリターの依存関係はここにすべて書かれています。

## poetry を使って実行する場合
- poetry を install します。
- このディレクトリのルートディレクトリで poetry install を実行してライブラリをインストールします。
- poetry run python test_max_eigenvalue.py で実験を開始できます。
- pip などを使って実行することも可能です。pyproject.toml に書かれたいライブラリをインストールして python test_max_eigenvalue.py を実行します。